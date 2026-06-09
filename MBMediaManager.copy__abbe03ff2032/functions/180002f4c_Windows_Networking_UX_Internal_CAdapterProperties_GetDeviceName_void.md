# Windows::Networking::UX::Internal::CAdapterProperties::GetDeviceName(void)

- ea: `0x180002f4c`
- end: `0x180003101`
- name: `?GetDeviceName@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `437`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000217c`

## callees

- `0x180002f4c`
- `0x18001cb10`
- `0x18001f47c`
- `0x18001f5b8`
- `0x180023018`
- `0x180026608`
- `0x180026ab8`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000302f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000302f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003050`
- `RPCRT4!UuidToStringW` at `0x180002f7c`
- `RPCRT4!UuidToStringW` at `0x180002f7c`
- `RPCRT4!RpcStringFreeW` at `0x180002fbe`
- `RPCRT4!RpcStringFreeW` at `0x1800030ba`
- `RPCRT4!RpcStringFreeW` at `0x180002fbe`
- `RPCRT4!RpcStringFreeW` at `0x1800030ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetDeviceName(
        Windows::Networking::UX::Internal::CAdapterProperties *this)
{
  RPC_STATUS v2; // ebx
  int v3; // ebx
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  RPC_WSTR v9; // [rsp+20h] [rbp-48h] BYREF
  RPC_WSTR String; // [rsp+28h] [rbp-40h] BYREF
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-38h] BYREF
  UINT32 length[4]; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = 0;
  v2 = UuidToStringW((const UUID *)this + 2, &v9);
  if ( v2 )
  {
    v3 = v2 | 0x10000000;
    if ( v3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
        (const char *)(unsigned int)v3,
        (int)v9);
    if ( v9 )
    {
      String = v9;
      RpcStringFreeW(&String);
    }
    return (unsigned int)v3;
  }
  else
  {
    *(_OWORD *)sourceString = 0;
    *(_OWORD *)length = 0;
    std::wstring::_Construct<1,unsigned short const *>(sourceString, L"\\Device\\{", 9);
    v5 = -1;
    do
      ++v5;
    while ( v9[v5] );
    std::wstring::_Append<unsigned short>(sourceString);
    std::wstring::_Append<unsigned short>(sourceString);
    WindowsDeleteString(*((HSTRING *)this + 12));
    *((_QWORD *)this + 12) = 0;
    v6 = (const WCHAR *)sourceString;
    if ( *(_QWORD *)&length[2] > 7u )
      v6 = sourceString[0];
    v7 = WindowsCreateString(v6, length[0], (HSTRING *)this + 12);
    v8 = v7;
    if ( v7 >= 0 )
    {
      std::wstring::_Tidy_deallocate(sourceString);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B7,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
        (const char *)(unsigned int)v7,
        (int)v9);
      if ( *(_QWORD *)&length[2] > 7u )
        std::_Deallocate<16>(sourceString[0], 2LL * *(_QWORD *)&length[2] + 2);
      *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(sourceString[0]) = 0;
      if ( v9 )
      {
        String = v9;
        RpcStringFreeW(&String);
      }
      return v8;
    }
  }
}

```

## disassembly

```asm
0x180002f4c  mov     r11, rsp
0x180002f4f  mov     [r11+10h], rbx
0x180002f53  mov     [r11+18h], rsi
0x180002f57  push    rdi
0x180002f58  sub     rsp, 60h
0x180002f5c  mov     rax, cs:__security_cookie
0x180002f63  xor     rax, rsp
0x180002f66  mov     [rsp+68h+var_18], rax
0x180002f6b  mov     rdi, rcx
0x180002f6e  xor     esi, esi
0x180002f70  mov     [r11-48h], rsi
0x180002f74  add     rcx, 20h ; ' '; Uuid
0x180002f78  lea     rdx, [r11-48h]; StringUuid
0x180002f7c  call    cs:__imp_UuidToStringW
0x180002f82  mov     ebx, eax
0x180002f84  test    eax, eax
0x180002f86  jz      short loc_180002FCB
0x180002f88  or      ebx, 10000000h
0x180002f8e  jge     short loc_180002FAA
0x180002f90  mov     rcx, [rsp+68h]; this
0x180002f95  mov     r9d, ebx; char *
0x180002f98  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180002f9f  mov     edx, 3B1h; void *
0x180002fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002fa9  nop
0x180002faa  mov     rax, [rsp+68h+var_48]
0x180002faf  test    rax, rax
0x180002fb2  jz      short loc_180002FC4
0x180002fb4  mov     [rsp+68h+String], rax
0x180002fb9  lea     rcx, [rsp+68h+String]; String
0x180002fbe  call    cs:__imp_RpcStringFreeW
0x180002fc4  mov     eax, ebx
0x180002fc6  jmp     loc_1800030E1
0x180002fcb  xorps   xmm0, xmm0
0x180002fce  movups  xmmword ptr [rsp+68h+sourceString], xmm0
0x180002fd3  xorps   xmm1, xmm1
0x180002fd6  movdqu  xmmword ptr [rsp+68h+length], xmm1
0x180002fdc  mov     r8d, 9
0x180002fe2  lea     rdx, aDevice; "\\Device\\{"
0x180002fe9  lea     rcx, [rsp+68h+sourceString]
0x180002fee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180002ff3  nop
0x180002ff4  mov     rdx, [rsp+68h+var_48]
0x180002ff9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002ffd  inc     r8
0x180003000  cmp     [rdx+r8*2], si
0x180003005  jnz     short loc_180002FFD
0x180003007  lea     rcx, [rsp+68h+sourceString]; Src
0x18000300c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003011  mov     r8d, 1
0x180003017  lea     rdx, asc_180060E0C; "}"
0x18000301e  lea     rcx, [rsp+68h+sourceString]; Src
0x180003023  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180003028  lea     rbx, [rdi+60h]
0x18000302c  mov     rcx, [rbx]; string
0x18000302f  call    cs:__imp_WindowsDeleteString
0x180003035  mov     [rbx], rsi
0x180003038  lea     rcx, [rsp+68h+sourceString]
0x18000303d  cmp     qword ptr [rsp+68h+length+8], 7
0x180003043  cmova   rcx, [rsp+68h+sourceString]; sourceString
0x180003049  mov     r8, rbx; string
0x18000304c  mov     edx, [rsp+68h+length]; length
0x180003050  call    cs:__imp_WindowsCreateString
0x180003056  mov     ebx, eax
0x180003058  test    eax, eax
0x18000305a  jns     short loc_1800030C4
0x18000305c  mov     rcx, [rsp+68h]; this
0x180003061  mov     r9d, eax; char *
0x180003064  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18000306b  mov     edx, 3B7h; void *
0x180003070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003075  nop
0x180003076  mov     rdx, qword ptr [rsp+68h+length+8]
0x18000307b  cmp     rdx, 7
0x18000307f  jbe     short loc_180003093
0x180003081  lea     rdx, ds:2[rdx*2]
0x180003089  mov     rcx, [rsp+68h+sourceString]
0x18000308e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180003093  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000309b  movdqu  xmmword ptr [rsp+68h+length], xmm0
0x1800030a1  mov     word ptr [rsp+68h+sourceString], si
0x1800030a6  mov     rax, [rsp+68h+var_48]
0x1800030ab  test    rax, rax
0x1800030ae  jz      short loc_1800030C0
0x1800030b0  mov     [rsp+68h+String], rax
0x1800030b5  lea     rcx, [rsp+68h+String]; String
0x1800030ba  call    cs:__imp_RpcStringFreeW
0x1800030c0  mov     eax, ebx
0x1800030c2  jmp     short loc_1800030E1
0x1800030c4  lea     rcx, [rsp+68h+sourceString]
0x1800030c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800030ce  nop
0x1800030cf  lea     rcx, [rsp+68h+var_48]
0x1800030d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800030d9  xor     eax, eax
0x1800030db  jmp     short loc_1800030E1
0x1800030dd  mov     eax, dword ptr [rsp+68h+var_48]
0x1800030e1  mov     rcx, [rsp+68h+var_18]
0x1800030e6  xor     rcx, rsp; StackCookie
0x1800030e9  call    __security_check_cookie
0x1800030ee  lea     r11, [rsp+68h+var_8]
0x1800030f3  mov     rbx, [r11+18h]
0x1800030f7  mov     rsi, [r11+20h]
0x1800030fb  mov     rsp, r11
0x1800030fe  pop     rdi
0x1800030ff  retn
```

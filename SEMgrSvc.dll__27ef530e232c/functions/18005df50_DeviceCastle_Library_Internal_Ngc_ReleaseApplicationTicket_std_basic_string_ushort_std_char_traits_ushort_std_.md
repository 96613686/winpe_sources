# DeviceCastle::Library::Internal::Ngc::ReleaseApplicationTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18005df50`
- end: `0x18005e059`
- name: `?ReleaseApplicationTicket@Ngc@Internal@Library@DeviceCastle@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180051960`
- `0x18005f834`

## callees

- `0x1800049a0`
- `0x180013274`
- `0x180018e80`
- `0x18005df50`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18005e02a`
- `ncrypt!NCryptFreeObject` at `0x18005e02a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005dfd3`
- `ncrypt!NCryptOpenStorageProvider` at `0x18005dfd3`
- `ncrypt!NCryptSetProperty` at `0x18005dffe`
- `ncrypt!NCryptSetProperty` at `0x18005dffe`

## string_xrefs

- `0x18005dff7`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall DeviceCastle::Library::Internal::Ngc::ReleaseApplicationTicket(const WCHAR *a1, __int64 a2)
{
  NCRYPT_PROV_HANDLE v4; // rcx
  unsigned __int64 v5; // rbp
  SECURITY_STATUS v6; // ebx
  BYTE *v7; // rsi
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v10[2]; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v10[0] = 0;
  v5 = *(_QWORD *)(a2 + 16);
  LOWORD(v10[0]) = 0;
  phProvider = 0;
  v10[1] = _mm_load_si128((const __m128i *)&_xmm);
  if ( v5 )
  {
    if ( v5 > 0xFFFFFFFF )
    {
      v6 = -2147024362;
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v7 = (BYTE *)a2;
      else
        v7 = *(BYTE **)a2;
      if ( *((_QWORD *)a1 + 3) > 7u )
        a1 = *(const WCHAR **)a1;
      v6 = NCryptOpenStorageProvider(&phProvider, a1, 0);
      if ( v6 >= 0 )
      {
        v6 = NCryptSetProperty(phProvider, L"PinCacheFreeApplicationTicket", v7, 2 * v5 + 2, 0);
        if ( v6 >= 0 )
        {
          std::wstring::operator=(a2, v10);
          v6 = 0;
        }
      }
      v4 = phProvider;
    }
    if ( v4 )
      NCryptFreeObject(v4);
  }
  else
  {
    v6 = -2147024809;
  }
  std::wstring::~wstring(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005df50  mov     [rsp+arg_10], rbx
0x18005df55  push    rbp
0x18005df56  push    rsi
0x18005df57  push    rdi
0x18005df58  sub     rsp, 60h
0x18005df5c  mov     rax, cs:__security_cookie
0x18005df63  xor     rax, rsp
0x18005df66  mov     [rsp+78h+var_20], rax
0x18005df6b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005df73  mov     rdi, rdx
0x18005df76  xor     eax, eax
0x18005df78  mov     rdx, rcx
0x18005df7b  xor     ecx, ecx; hObject
0x18005df7d  xorps   xmm0, xmm0
0x18005df80  movups  [rsp+78h+var_40], xmm0
0x18005df85  mov     rbp, [rdi+10h]
0x18005df89  mov     word ptr [rsp+78h+var_40], ax
0x18005df8e  mov     [rsp+78h+phProvider], rcx
0x18005df93  movdqu  [rsp+78h+var_30], xmm1
0x18005df99  test    rbp, rbp
0x18005df9c  jnz     short loc_18005DFA8
0x18005df9e  mov     ebx, 80070057h
0x18005dfa3  jmp     loc_18005E030
0x18005dfa8  mov     eax, 0FFFFFFFFh
0x18005dfad  cmp     rbp, rax
0x18005dfb0  ja      short loc_18005E020
0x18005dfb2  cmp     qword ptr [rdi+18h], 7
0x18005dfb7  jbe     short loc_18005DFBE
0x18005dfb9  mov     rsi, [rdi]
0x18005dfbc  jmp     short loc_18005DFC1
0x18005dfbe  mov     rsi, rdi
0x18005dfc1  cmp     qword ptr [rdx+18h], 7
0x18005dfc6  jbe     short loc_18005DFCB
0x18005dfc8  mov     rdx, [rdx]; pszProviderName
0x18005dfcb  xor     r8d, r8d; dwFlags
0x18005dfce  lea     rcx, [rsp+78h+phProvider]; phProvider
0x18005dfd3  call    cs:__imp_NCryptOpenStorageProvider
0x18005dfd9  mov     ebx, eax
0x18005dfdb  test    eax, eax
0x18005dfdd  js      short loc_18005E019
0x18005dfdf  mov     rcx, [rsp+78h+phProvider]; hObject
0x18005dfe4  lea     r9d, ds:2[rbp*2]; cbInput
0x18005dfec  mov     r8, rsi; pbInput
0x18005dfef  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18005dff7  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x18005dffe  call    cs:__imp_NCryptSetProperty
0x18005e004  mov     ebx, eax
0x18005e006  test    eax, eax
0x18005e008  js      short loc_18005E019
0x18005e00a  lea     rdx, [rsp+78h+var_40]
0x18005e00f  mov     rcx, rdi
0x18005e012  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005e017  xor     ebx, ebx
0x18005e019  mov     rcx, [rsp+78h+phProvider]
0x18005e01e  jmp     short loc_18005E025
0x18005e020  mov     ebx, 80070216h
0x18005e025  test    rcx, rcx
0x18005e028  jz      short loc_18005E030
0x18005e02a  call    cs:__imp_NCryptFreeObject
0x18005e030  lea     rcx, [rsp+78h+var_40]
0x18005e035  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005e03a  mov     eax, ebx
0x18005e03c  mov     rcx, [rsp+78h+var_20]
0x18005e041  xor     rcx, rsp; StackCookie
0x18005e044  call    __security_check_cookie
0x18005e049  mov     rbx, [rsp+78h+arg_10]
0x18005e051  add     rsp, 60h
0x18005e055  pop     rdi
0x18005e056  pop     rsi
0x18005e057  pop     rbp
0x18005e058  retn
```

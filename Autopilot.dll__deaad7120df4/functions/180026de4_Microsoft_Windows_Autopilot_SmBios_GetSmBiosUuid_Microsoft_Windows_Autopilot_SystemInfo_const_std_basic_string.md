# Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(Microsoft::Windows::Autopilot::SystemInfo const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026de4`
- end: `0x180026ee6`
- name: `?GetSmBiosUuid@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSystemInfo@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026a64`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x1800098e7`
- `0x180010764`
- `0x1800192a4`
- `0x180026de4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026e35`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026e35`

## string_xrefs

- `0x180026e4f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::SmBios::GetSmBiosUuid(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  unsigned __int64 v5; // rdx
  char *v6; // rdi
  __int64 v7; // rbx
  GUID rguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  rguid = *(GUID *)(a1 + 8);
  memset_0(sz, 0, 0x4Eu);
  if ( StringFromGUID2(&rguid, sz, 39) )
  {
    v5 = -1;
    do
      ++v5;
    while ( sz[v5] );
    if ( v5 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)a2,
        v5,
        v3,
        sz);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v6 = (char *)a2;
      else
        v6 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v5;
      v7 = 2 * v5;
      memmove_0(v6, sz, 2 * v5);
      *(_WORD *)&v6[v7] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)0x8000FFFFLL,
      rguid.Data1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180026de4  mov     [rsp+arg_10], rbx
0x180026de9  mov     [rsp+arg_18], rsi
0x180026dee  push    rdi
0x180026def  sub     rsp, 90h
0x180026df6  mov     rax, cs:__security_cookie
0x180026dfd  xor     rax, rsp
0x180026e00  mov     [rsp+98h+var_18], rax
0x180026e08  movups  xmm0, xmmword ptr [rcx+8]
0x180026e0c  mov     rbx, rdx
0x180026e0f  lea     rcx, [rsp+98h+sz]; void *
0x180026e14  xor     edx, edx; Val
0x180026e16  movdqu  xmmword ptr [rsp+98h+rguid.Data1], xmm0; int
0x180026e1c  lea     r8d, [rdx+4Eh]; Size
0x180026e20  call    memset_0
0x180026e25  mov     r8d, 27h ; '''; cchMax
0x180026e2b  lea     rdx, [rsp+98h+sz]; lpsz
0x180026e30  lea     rcx, [rsp+98h+rguid]; rguid
0x180026e35  call    cs:__imp_StringFromGUID2
0x180026e3c  nop     dword ptr [rax+rax+00h]
0x180026e41  xor     esi, esi
0x180026e43  test    eax, eax
0x180026e45  jnz     short loc_180026E6C
0x180026e47  mov     rcx, [rsp+98h]; this
0x180026e4f  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026e56  mov     ebx, 8000FFFFh
0x180026e5b  mov     edx, 132h; void *
0x180026e60  mov     r9d, ebx; char *
0x180026e63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e68  mov     eax, ebx
0x180026e6a  jmp     short loc_180026EC0
0x180026e6c  lea     rax, [rsp+98h+sz]
0x180026e71  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026e75  inc     rdx
0x180026e78  cmp     [rax+rdx*2], si
0x180026e7c  jnz     short loc_180026E75
0x180026e7e  cmp     rdx, [rbx+18h]
0x180026e82  ja      short loc_180026EB1
0x180026e84  cmp     qword ptr [rbx+18h], 7
0x180026e89  jbe     short loc_180026E90
0x180026e8b  mov     rdi, [rbx]
0x180026e8e  jmp     short loc_180026E93
0x180026e90  mov     rdi, rbx
0x180026e93  mov     [rbx+10h], rdx
0x180026e97  mov     rcx, rdi; void *
0x180026e9a  lea     rbx, [rdx+rdx]
0x180026e9e  mov     r8, rbx; Size
0x180026ea1  lea     rdx, [rsp+98h+sz]; Src
0x180026ea6  call    memmove_0
0x180026eab  mov     [rbx+rdi], si
0x180026eaf  jmp     short loc_180026EBE
0x180026eb1  lea     r9, [rsp+98h+sz]
0x180026eb6  mov     rcx, rbx
0x180026eb9  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180026ebe  xor     eax, eax
0x180026ec0  mov     rcx, [rsp+98h+var_18]
0x180026ec8  xor     rcx, rsp; StackCookie
0x180026ecb  call    __security_check_cookie
0x180026ed0  lea     r11, [rsp+98h+var_8]
0x180026ed8  mov     rbx, [r11+20h]
0x180026edc  mov     rsi, [r11+28h]
0x180026ee0  mov     rsp, r11
0x180026ee3  pop     rdi
0x180026ee4  retn
```

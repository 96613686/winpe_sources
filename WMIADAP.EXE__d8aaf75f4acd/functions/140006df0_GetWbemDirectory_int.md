# GetWbemDirectory(int)

- ea: `0x140006df0`
- end: `0x14000701e`
- name: `?GetWbemDirectory@@YAPEAGH@Z`
- size: `558`
- prototype: `unsigned __int16 *__fastcall(int, HKEY)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140006d24`
- `0x1400083dc`
- `0x14000a67c`
- `0x14000a828`
- `0x14000a96c`

## callees

- `0x140006284`
- `0x140006a78`
- `0x140006df0`
- `0x14000723c`
- `0x140007294`
- `0x1400075f8`

## import_xrefs

- `msvcrt!wcslen` at `0x140006f2f`
- `msvcrt!wcslen` at `0x140006f2f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006fcd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006fdf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006fcd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006fdf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006e95`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006ef2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006f4d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006f94`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006e95`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006ef2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006f4d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140006f94`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140006ed4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140006f12`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140006ed4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140006f12`

## pseudocode

```c
unsigned __int16 *__fastcall GetWbemDirectory(int a1, HKEY a2)
{
  unsigned __int16 *v3; // rbx
  const unsigned __int16 *v4; // r8
  WCHAR *v5; // rax
  const unsigned __int16 *v6; // r8
  WCHAR *v7; // rdi
  DWORD v8; // eax
  DWORD v9; // r14d
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rsi
  DWORD v12; // r14d
  unsigned int v13; // r15d
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r8
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // r14
  unsigned __int16 *v18; // rax
  unsigned int v20; // [rsp+20h] [rbp-58h]
  WCHAR *v21; // [rsp+30h] [rbp-48h]
  _BYTE v22[64]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int16 *v24; // [rsp+90h] [rbp+18h]
  WCHAR *v25; // [rsp+98h] [rbp+20h]

  memset(v22, 0, 24);
  v3 = 0;
  v24 = 0;
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v22, a2, L"SOFTWARE\\Microsoft\\Wbem\\CIMOM", 0x20019u, v20) )
    goto LABEL_17;
  v25 = 0;
  v21 = 0;
  v23 = 0;
  if ( (unsigned int)ATL::CRegKey::QueryValue((ATL::CRegKey *)v22, 0, v4, &v23) )
    goto LABEL_17;
  try
  {
    v5 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(2LL * v23, 2u));
    v7 = v5;
    v25 = v5;
    if ( v5 )
    {
      if ( (unsigned int)ATL::CRegKey::QueryValue((ATL::CRegKey *)v22, v5, v6, &v23) )
        goto LABEL_16;
      v8 = ExpandEnvironmentStringsW(v7, 0, 0);
      v9 = v8;
      if ( !v8 )
        goto LABEL_16;
      v10 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8, 2u));
      v11 = v10;
      v21 = v10;
      if ( !v10 )
        goto LABEL_16;
      v12 = ExpandEnvironmentStringsW(v7, v10, v9);
      if ( v12 )
      {
        if ( a1 )
        {
          v13 = v12 + wcslen(L"\\Performance\\") + 1;
          v14 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v13, 2u));
          v3 = v14;
          v24 = v14;
          if ( v14 )
          {
            StringCchCopyW(v14, v12, v11);
            v15 = L"\\Performance\\";
            v16 = v13;
LABEL_14:
            StringCchCatW(v3, v16, v15);
          }
        }
        else
        {
          v17 = v12 + 2;
          v18 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v17, 2u));
          v3 = v18;
          v24 = v18;
          if ( v18 )
          {
            StringCchCopyW(v18, (unsigned int)v17, v11);
            v15 = L"\\";
            v16 = (unsigned int)v17;
            goto LABEL_14;
          }
        }
      }
      CWin32DefaultArena::WbemMemFree(v11);
      v21 = 0;
LABEL_16:
      CWin32DefaultArena::WbemMemFree(v7);
      v25 = 0;
    }
  }
  catch ( ... )
  {
    if ( v25 )
      CWin32DefaultArena::WbemMemFree(v25);
    if ( v21 )
      CWin32DefaultArena::WbemMemFree(v21);
    if ( v24 )
    {
      CWin32DefaultArena::WbemMemFree(v24);
      v24 = 0;
    }
    v3 = v24;
  }
LABEL_17:
  ATL::CRegKey::Close((ATL::CRegKey *)v22);
  return v3;
}

```

## disassembly

```asm
0x140006df0  mov     rax, rsp
0x140006df3  mov     [rax+8], rbx
0x140006df7  push    rsi
0x140006df8  push    rdi
0x140006df9  push    r13
0x140006dfb  push    r14
0x140006dfd  push    r15
0x140006dff  sub     rsp, 50h
0x140006e03  mov     r15d, ecx
0x140006e06  mov     qword ptr [rax-40h], 0
0x140006e0e  mov     qword ptr [rax-38h], 0
0x140006e16  mov     qword ptr [rax-30h], 0
0x140006e1e  xor     ebx, ebx
0x140006e20  mov     [rsp+78h+arg_10], rbx
0x140006e28  mov     r9d, 20019h; unsigned int
0x140006e2e  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Wbem\\CIMOM"
0x140006e35  lea     rcx, [rax-40h]; this
0x140006e39  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x140006e3e  test    eax, eax
0x140006e40  jnz     loc_140006FFB
0x140006e46  mov     [rsp+78h+arg_18], rbx
0x140006e4e  mov     [rsp+78h+var_48], rbx
0x140006e53  mov     [rsp+78h+arg_8], ebx
0x140006e5a  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x140006e62  xor     edx, edx; unsigned __int16 *
0x140006e64  lea     rcx, [rsp+78h+var_40]; this
0x140006e69  call    ?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z; ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x140006e6e  test    eax, eax
0x140006e70  jnz     loc_140006FFB
0x140006e76  mov     ecx, [rsp+78h+arg_8]
0x140006e7d  add     rcx, rcx
0x140006e80  lea     r13d, [rbx+2]
0x140006e84  mov     eax, r13d
0x140006e87  mul     rcx
0x140006e8a  lea     rsi, [rbx-1]
0x140006e8e  cmovb   rax, rsi
0x140006e92  mov     rcx, rax
0x140006e95  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140006e9b  mov     rdi, rax
0x140006e9e  mov     [rsp+78h+arg_18], rax
0x140006ea6  test    rax, rax
0x140006ea9  jz      loc_140006FF1
0x140006eaf  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x140006eb7  mov     rdx, rax; unsigned __int16 *
0x140006eba  lea     rcx, [rsp+78h+var_40]; this
0x140006ebf  call    ?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z; ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x140006ec4  test    eax, eax
0x140006ec6  jnz     loc_140006FDC
0x140006ecc  xor     r8d, r8d; nSize
0x140006ecf  xor     edx, edx; lpDst
0x140006ed1  mov     rcx, rdi; lpSrc
0x140006ed4  call    cs:__imp_ExpandEnvironmentStringsW
0x140006eda  mov     r14d, eax
0x140006edd  test    eax, eax
0x140006edf  jz      loc_140006FDC
0x140006ee5  mov     eax, r13d
0x140006ee8  mul     r14
0x140006eeb  cmovb   rax, rsi
0x140006eef  mov     rcx, rax
0x140006ef2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140006ef8  mov     rsi, rax
0x140006efb  mov     [rsp+78h+var_48], rax
0x140006f00  test    rax, rax
0x140006f03  jz      loc_140006FDC
0x140006f09  mov     r8d, r14d; nSize
0x140006f0c  mov     rdx, rax; lpDst
0x140006f0f  mov     rcx, rdi; lpSrc
0x140006f12  call    cs:__imp_ExpandEnvironmentStringsW
0x140006f18  mov     r14d, eax
0x140006f1b  test    eax, eax
0x140006f1d  jz      loc_140006FCA
0x140006f23  test    r15d, r15d
0x140006f26  jz      short loc_140006F7D
0x140006f28  lea     rcx, aPerformance; "\\Performance\\"
0x140006f2f  call    cs:__imp_wcslen
0x140006f35  lea     r15d, [rax+1]
0x140006f39  add     r15d, r14d
0x140006f3c  mov     eax, r13d
0x140006f3f  mul     r15
0x140006f42  lea     rcx, [rbx-1]
0x140006f46  cmovb   rax, rcx
0x140006f4a  mov     rcx, rax
0x140006f4d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140006f53  mov     rbx, rax
0x140006f56  mov     [rsp+78h+arg_10], rax
0x140006f5e  test    rax, rax
0x140006f61  jz      short loc_140006FCA
0x140006f63  mov     edx, r14d; unsigned __int64
0x140006f66  mov     r8, rsi; unsigned __int16 *
0x140006f69  mov     rcx, rax; unsigned __int16 *
0x140006f6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140006f71  lea     r8, aPerformance; "\\Performance\\"
0x140006f78  mov     edx, r15d
0x140006f7b  jmp     short loc_140006FC2
0x140006f7d  add     r14d, r13d
0x140006f80  mov     rax, r13
0x140006f83  mul     r14
0x140006f86  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140006f8d  cmovb   rax, rcx
0x140006f91  mov     rcx, rax
0x140006f94  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140006f9a  mov     rbx, rax
0x140006f9d  mov     [rsp+78h+arg_10], rax
0x140006fa5  test    rax, rax
0x140006fa8  jz      short loc_140006FCA
0x140006faa  mov     r8, rsi; unsigned __int16 *
0x140006fad  mov     edx, r14d; unsigned __int64
0x140006fb0  mov     rcx, rax; unsigned __int16 *
0x140006fb3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140006fb8  lea     r8, asc_14001A9B8; "\\"
0x140006fbf  mov     edx, r14d; unsigned __int64
0x140006fc2  mov     rcx, rbx; unsigned __int16 *
0x140006fc5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006fca  mov     rcx, rsi
0x140006fcd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006fd3  mov     [rsp+78h+var_48], 0
0x140006fdc  mov     rcx, rdi
0x140006fdf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006fe5  mov     [rsp+78h+arg_18], 0
0x140006ff1  jmp     short loc_140006FFB
0x140006ff3  mov     rbx, [rsp+78h+arg_10]
0x140006ffb  lea     rcx, [rsp+78h+var_40]; this
0x140007000  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140007005  nop
0x140007006  mov     rax, rbx
0x140007009  mov     rbx, [rsp+78h+arg_0]
0x140007011  add     rsp, 50h
0x140007015  pop     r15
0x140007017  pop     r14
0x140007019  pop     r13
0x14000701b  pop     rdi
0x14000701c  pop     rsi
0x14000701d  retn
```

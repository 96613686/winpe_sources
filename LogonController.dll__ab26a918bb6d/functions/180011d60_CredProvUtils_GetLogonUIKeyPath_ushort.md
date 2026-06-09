# CredProvUtils::GetLogonUIKeyPath(ushort * *)

- ea: `0x180011d60`
- end: `0x180012110`
- name: `?GetLogonUIKeyPath@CredProvUtils@@YAJPEAPEAG@Z`
- size: `944`
- prototype: `__int64 __fastcall(CredProvUtils *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180011d60`
- `0x18002bc20`
- `0x18005d488`
- `0x18005d5a0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f77`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011fe0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012042`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001208b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800120ef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011f77`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011fe0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012042`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001208b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800120ef`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011f00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120fd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180011f45`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800120bf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180011f45`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800120bf`

## string_xrefs

- `0x180011eac`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180011f5e`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180011ffe`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180012028`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180012072`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800120d5`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`

## pseudocode

```c
__int64 __fastcall CredProvUtils::GetLogonUIKeyPath(CredProvUtils *this, unsigned __int16 **a2)
{
  unsigned __int64 v3; // rsi
  __int16 *v4; // rbx
  void *v5; // r14
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdi
  _WORD *v8; // rax
  int v9; // ebp
  unsigned __int64 v10; // rcx
  _WORD *v11; // rdx
  __int16 v12; // ax
  _WORD *v13; // rcx
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v16; // ebx
  void *v17; // rbx
  unsigned int v18; // eax
  unsigned int v19; // ebx
  SIZE_T *p_cb; // [rsp+20h] [rbp-58h]
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-40h]
  unsigned __int64 v23; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  SIZE_T cb; // [rsp+80h] [rbp+8h] BYREF

  if ( !this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
      (const char *)0x80004003LL,
      (int)p_cb);
    return 2147500035LL;
  }
  v3 = -1;
  v4 = (__int16 *)pv;
  if ( !pv || !*(_WORD *)pv )
  {
    AcquireSRWLockExclusive(&stru_1800D43B8);
    if ( !pv || !*(_WORD *)pv )
    {
      LODWORD(cb) = 0;
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                     L"LogonUI",
                                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
                                     0,
                                     0);
      if ( !PersistedRegistryLocationW )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)0x8000FFFFLL,
          (int)&cb);
        ReleaseSRWLockExclusive(&stru_1800D43B8);
        return 2147549183LL;
      }
      if ( PersistedRegistryLocationW != 234 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x27,
                (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
                (const char *)PersistedRegistryLocationW,
                (unsigned int)&cb);
        ReleaseSRWLockExclusive(&stru_1800D43B8);
        return v16;
      }
      v17 = CoTaskMemAlloc((unsigned int)cb);
      if ( !v17 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)0x8007000ELL,
          (int)&cb);
        ReleaseSRWLockExclusive(&stru_1800D43B8);
        return 2147942414LL;
      }
      p_cb = &cb;
      v18 = GetPersistedRegistryLocationW(
              L"LogonUI",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
              v17,
              (unsigned int)cb);
      if ( v18 )
      {
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x32,
                (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
                (const char *)v18,
                (unsigned int)&cb);
        ReleaseSRWLockExclusive(&stru_1800D43B8);
        return v19;
      }
      if ( pv )
        CoTaskMemFree(pv);
      pv = v17;
      qword_1800D40F0 = -1;
      qword_1800D40E8 = -1;
    }
    ReleaseSRWLockExclusive(&stru_1800D43B8);
    v4 = (__int16 *)pv;
  }
  v5 = 0;
  v22 = 0;
  v23 = 0;
  v6 = qword_1800D40E8;
  if ( qword_1800D40E8 == -1 )
  {
    if ( v4 )
    {
      v6 = -1;
      do
        ++v6;
      while ( v4[v6] );
    }
    else
    {
      v6 = 0;
    }
  }
  if ( !v4 )
    goto LABEL_39;
  do
    ++v3;
  while ( v4[v3] );
  if ( v6 == -1 )
  {
    v6 = v3;
  }
  else if ( v6 < v3 )
  {
    v3 = v6;
  }
  v7 = v6 + 1;
  if ( v6 + 1 >= v6 && is_mul_ok(v7, 2u) )
  {
    v8 = CoTaskMemAlloc(2 * v7);
    if ( !v8 )
    {
      v9 = -2147024882;
      goto LABEL_28;
    }
    v9 = 0;
    v23 = v7;
    v5 = v8;
    *v8 = 0;
    if ( v7 )
    {
      if ( v7 > 0x7FFFFFFF || v3 > 0x7FFFFFFE )
      {
        *v8 = 0;
      }
      else
      {
        v10 = v3;
        v11 = v8;
        do
        {
          if ( !v10 )
            break;
          v12 = *v4;
          if ( !*v4 )
            break;
          ++v4;
          *v11++ = v12;
          --v10;
          --v7;
        }
        while ( v7 );
        v13 = v11 - 1;
        if ( v7 )
          v13 = v11;
        *v13 = 0;
      }
    }
    v22 = v3;
  }
  else
  {
    v9 = -2147024362;
  }
  if ( v9 >= 0 )
  {
LABEL_39:
    v21 = 0;
    v23 = 0;
    v22 = 0;
    *(_QWORD *)this = v5;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
    return 0;
  }
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x39,
    (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
    (const char *)(unsigned int)v9,
    (int)p_cb);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011d60  mov     [rsp+arg_8], rbx
0x180011d65  mov     [rsp+arg_10], rbp
0x180011d6a  push    rsi
0x180011d6b  push    rdi
0x180011d6c  push    r12
0x180011d6e  push    r14
0x180011d70  push    r15
0x180011d72  sub     rsp, 50h
0x180011d76  mov     r15, rcx
0x180011d79  test    rcx, rcx
0x180011d7c  jz      loc_180011FF3
0x180011d82  xor     r12d, r12d
0x180011d85  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180011d8c  mov     rbx, cs:pv
0x180011d93  test    rbx, rbx
0x180011d96  jz      loc_180011EF9
0x180011d9c  cmp     [rbx], r12w
0x180011da0  jz      loc_180011EF9
0x180011da6  mov     r14, r12
0x180011da9  mov     [rsp+78h+var_40], r12
0x180011dae  mov     [rsp+78h+var_38], r12
0x180011db3  mov     rax, cs:qword_1800D40E8
0x180011dba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011dbe  jnz     short loc_180011DDA
0x180011dc0  test    rbx, rbx
0x180011dc3  jz      loc_180012108
0x180011dc9  mov     rax, rsi
0x180011dcc  nop     dword ptr [rax+00h]
0x180011dd0  inc     rax
0x180011dd3  cmp     [rbx+rax*2], r12w
0x180011dd8  jnz     short loc_180011DD0
0x180011dda  test    rbx, rbx
0x180011ddd  jz      loc_180011F88
0x180011de3  inc     rsi
0x180011de6  cmp     [rbx+rsi*2], r12w
0x180011deb  jnz     short loc_180011DE3
0x180011ded  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011df1  jnz     loc_180011EE6
0x180011df7  mov     rax, rsi
0x180011dfa  lea     rdi, [rax+1]
0x180011dfe  cmp     rdi, rax
0x180011e01  jb      loc_180011E97
0x180011e07  mov     eax, 2
0x180011e0c  mul     rdi
0x180011e0f  test    rdx, rdx
0x180011e12  jnz     loc_180011E97
0x180011e18  mov     rcx, rax; cb
0x180011e1b  call    cs:__imp_CoTaskMemAlloc
0x180011e21  test    rax, rax
0x180011e24  jz      loc_180011EF2
0x180011e2a  mov     ebp, r12d
0x180011e2d  mov     [rsp+78h+var_38], rdi
0x180011e32  mov     r14, rax
0x180011e35  mov     [rax], r12w
0x180011e39  test    rdi, rdi
0x180011e3c  jz      short loc_180011E90
0x180011e3e  cmp     rdi, 7FFFFFFFh
0x180011e45  ja      loc_180011FAB
0x180011e4b  cmp     rsi, 7FFFFFFEh
0x180011e52  ja      loc_180011FAB
0x180011e58  mov     rcx, rsi
0x180011e5b  mov     rdx, rax
0x180011e5e  xchg    ax, ax
0x180011e60  test    rcx, rcx
0x180011e63  jz      short loc_180011E81
0x180011e65  movzx   eax, word ptr [rbx]
0x180011e68  test    ax, ax
0x180011e6b  jz      short loc_180011E81
0x180011e6d  add     rbx, 2
0x180011e71  mov     [rdx], ax
0x180011e74  add     rdx, 2
0x180011e78  dec     rcx
0x180011e7b  sub     rdi, 1
0x180011e7f  jnz     short loc_180011E60
0x180011e81  lea     rcx, [rdx-2]
0x180011e85  test    rdi, rdi
0x180011e88  cmovnz  rcx, rdx
0x180011e8c  mov     [rcx], r12w
0x180011e90  mov     [rsp+78h+var_40], rsi
0x180011e95  jmp     short loc_180011E9C
0x180011e97  mov     ebp, 80070216h
0x180011e9c  test    ebp, ebp
0x180011e9e  jns     loc_180011F88
0x180011ea4  mov     rcx, [rsp+78h]; this
0x180011ea9  mov     r9d, ebp; char *
0x180011eac  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180011eb3  mov     edx, 39h ; '9'; void *
0x180011eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ebd  test    r14, r14
0x180011ec0  jz      short loc_180011ECB
0x180011ec2  mov     rcx, r14; pv
0x180011ec5  call    cs:__imp_CoTaskMemFree
0x180011ecb  mov     eax, ebp
0x180011ecd  lea     r11, [rsp+78h+var_28]
0x180011ed2  mov     rbx, [r11+38h]
0x180011ed6  mov     rbp, [r11+40h]
0x180011eda  mov     rsp, r11
0x180011edd  pop     r15
0x180011edf  pop     r14
0x180011ee1  pop     r12
0x180011ee3  pop     rdi
0x180011ee4  pop     rsi
0x180011ee5  retn
0x180011ee6  cmp     rax, rsi
0x180011ee9  cmovb   rsi, rax
0x180011eed  jmp     loc_180011DFA
0x180011ef2  mov     ebp, 8007000Eh
0x180011ef7  jmp     short loc_180011EA4
0x180011ef9  lea     rcx, stru_1800D43B8; SRWLock
0x180011f00  call    cs:__imp_AcquireSRWLockExclusive
0x180011f06  mov     rax, cs:pv
0x180011f0d  test    rax, rax
0x180011f10  jz      short loc_180011F1C
0x180011f12  cmp     [rax], r12w
0x180011f16  jnz     loc_180011FD9
0x180011f1c  mov     dword ptr [rsp+78h+cb], r12d
0x180011f24  lea     rax, [rsp+78h+cb]
0x180011f2c  mov     qword ptr [rsp+78h+var_58], rax; int
0x180011f31  xor     r9d, r9d
0x180011f34  xor     r8d, r8d
0x180011f37  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180011f3e  lea     rcx, aLogonui; "LogonUI"
0x180011f45  call    cs:__imp_GetPersistedRegistryLocationW
0x180011f4b  test    eax, eax
0x180011f4d  jnz     loc_180012019
0x180011f53  mov     rcx, [rsp+78h]; this
0x180011f58  mov     r9d, 8000FFFFh; char *
0x180011f5e  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180011f65  mov     edx, 23h ; '#'; void *
0x180011f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f6f  nop
0x180011f70  lea     rcx, stru_1800D43B8; SRWLock
0x180011f77  call    cs:__imp_ReleaseSRWLockExclusive
0x180011f7d  nop
0x180011f7e  mov     eax, 8000FFFFh
0x180011f83  jmp     loc_180011ECD
0x180011f88  mov     [rsp+78h+var_48], r12
0x180011f8d  mov     [rsp+78h+var_38], r12
0x180011f92  mov     [rsp+78h+var_40], r12
0x180011f97  mov     [r15], r14
0x180011f9a  lea     rcx, [rsp+78h+var_48]
0x180011f9f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180011fa4  xor     eax, eax
0x180011fa6  jmp     loc_180011ECD
0x180011fab  mov     [rax], r12w
0x180011faf  jmp     loc_180011E90
0x180011fb4  mov     rcx, cs:pv; pv
0x180011fbb  test    rcx, rcx
0x180011fbe  jnz     loc_1800120FD
0x180011fc4  mov     cs:pv, rbx
0x180011fcb  mov     cs:qword_1800D40F0, rsi
0x180011fd2  mov     cs:qword_1800D40E8, rsi
0x180011fd9  lea     rcx, stru_1800D43B8; SRWLock
0x180011fe0  call    cs:__imp_ReleaseSRWLockExclusive
0x180011fe6  nop
0x180011fe7  mov     rbx, cs:pv
0x180011fee  jmp     loc_180011DA6
0x180011ff3  mov     rcx, [rsp+78h]; this
0x180011ff8  mov     r9d, 80004003h; char *
0x180011ffe  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180012005  mov     edx, 13h; void *
0x18001200a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001200f  mov     eax, 80004003h
0x180012014  jmp     loc_180011ECD
0x180012019  cmp     eax, 0EAh
0x18001201e  jz      short loc_180012050
0x180012020  mov     rcx, [rsp+78h]; this
0x180012025  mov     r9d, eax; char *
0x180012028  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x18001202f  mov     edx, 27h ; '''; void *
0x180012034  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012039  mov     ebx, eax
0x18001203b  lea     rcx, stru_1800D43B8; SRWLock
0x180012042  call    cs:__imp_ReleaseSRWLockExclusive
0x180012048  nop
0x180012049  mov     eax, ebx
0x18001204b  jmp     loc_180011ECD
0x180012050  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x180012057  call    cs:__imp_CoTaskMemAlloc
0x18001205d  mov     rbx, rax
0x180012060  test    rax, rax
0x180012063  jnz     short loc_180012099
0x180012065  mov     rcx, [rsp+78h]; this
0x18001206a  mov     ebp, 8007000Eh
0x18001206f  mov     r9d, ebp; char *
0x180012072  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180012079  mov     edx, 2Bh ; '+'; void *
0x18001207e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012083  nop
0x180012084  lea     rcx, stru_1800D43B8; SRWLock
0x18001208b  call    cs:__imp_ReleaseSRWLockExclusive
0x180012091  nop
0x180012092  mov     eax, ebp
0x180012094  jmp     loc_180011ECD
0x180012099  lea     rax, [rsp+78h+cb]
0x1800120a1  mov     qword ptr [rsp+78h+var_58], rax; unsigned int
0x1800120a6  mov     r9d, dword ptr [rsp+78h+cb]
0x1800120ae  mov     r8, rbx
0x1800120b1  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800120b8  lea     rcx, aLogonui; "LogonUI"
0x1800120bf  call    cs:__imp_GetPersistedRegistryLocationW
0x1800120c5  test    eax, eax
0x1800120c7  jz      loc_180011FB4
0x1800120cd  mov     rcx, [rsp+78h]; this
0x1800120d2  mov     r9d, eax; char *
0x1800120d5  lea     r8, aOnecoreShellAu_0; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800120dc  mov     edx, 32h ; '2'; void *
0x1800120e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800120e6  mov     ebx, eax
0x1800120e8  lea     rcx, stru_1800D43B8; SRWLock
0x1800120ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800120f5  nop
0x1800120f6  mov     eax, ebx
0x1800120f8  jmp     loc_180011ECD
0x1800120fd  call    cs:__imp_CoTaskMemFree
0x180012103  jmp     loc_180011FC4
0x180012108  mov     rax, r12
0x18001210b  jmp     loc_180011DDA
```

# AipRunOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800028d0`
- end: `0x180002a73`
- name: `?AipRunOnceCallback@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `419`
- prototype: `__int64 __fastcall(union _RTL_RUN_ONCE *, void *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800028d0`
- `0x180004154`
- `0x180004ca0`
- `0x180004de4`
- `0x180004f4c`
- `0x1800051fc`
- `0x18000957a`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180002965`
- `ntdll!RtlInitializeSRWLock` at `0x180002965`
- `ntdll!RtlGetNtSystemRoot` at `0x180002994`
- `ntdll!RtlGetNtSystemRoot` at `0x180002994`
- `ntdll!RtlInitUnicodeString` at `0x1800029a1`
- `ntdll!RtlInitUnicodeString` at `0x1800029a1`

## string_xrefs

- `0x18000290d`: `%SYSTEM32%`
- `0x180002923`: `%WINDIR%\System32`

## pseudocode

```c
__int64 __fastcall AipRunOnceCallback(union _RTL_RUN_ONCE *a1, void *a2, void **a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *NtSystemRoot; // rax
  int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-60h] BYREF
  __int64 v11; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v13[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-20h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF

  AipDllInitialized = 1;
  v13[1] = L"%WINDIR%\\System32";
  v13[0] = 2359330;
  v14[1] = L"%WINDIR%\\SysWOW64";
  DestinationString = 0;
  v14[0] = 2359330;
  memset_0(&AipPathMacroList, 0, 0x48u);
  RtlInitializeSRWLock(&qword_180010830);
  AipPathMacroListInitialized = 1;
  qword_180010840 = (__int64)&P;
  P = &P;
  dword_180010804 = 1;
  NtSystemRoot = (const WCHAR *)RtlGetNtSystemRoot(
                                  v4,
                                  v3,
                                  v5,
                                  v6,
                                  1441812,
                                  L"%SYSTEM32%",
                                  1179664,
                                  L"%WINDIR%",
                                  1310738,
                                  L"%OSDRIVE%");
  RtlInitUnicodeString(&DestinationString, NtSystemRoot);
  v8 = AipAddPathMacro(&v11, &DestinationString, 12);
  if ( v8 >= 0 )
  {
    xmmword_180010808 = (__int128)DestinationString;
    LOWORD(xmmword_180010808) = 4;
    v8 = AipConvertToNtPath(&xmmword_180010808, &String2);
    if ( v8 >= 0 )
    {
      v8 = AipAddPathMacro(&v12, &String2, 12);
      if ( v8 >= 0 )
      {
        v8 = AipAddPathMacro(&v10, v13, 8);
        if ( v8 >= 0 )
        {
          if ( !dword_180010804 || (v8 = AipAddPathMacro(&v10, v14, 8), v8 >= 0) )
          {
            v8 = AipExpandPathMacros();
            if ( v8 >= 0 )
              v8 = AiInitializeSoftwarePathMacroList();
          }
        }
      }
    }
  }
  AipDllInitializeStatus = v8;
  if ( v8 >= 0 )
    AipDllInitializeStatus = AiInitializeLib();
  return 1;
}

```

## disassembly

```asm
0x1800028d0  push    rbp
0x1800028d2  mov     rbp, rsp
0x1800028d5  sub     rsp, 80h
0x1800028dc  lea     rax, aOsdrive; "%OSDRIVE%"
0x1800028e3  mov     cs:?AipDllInitialized@@3KA, 1; ulong AipDllInitialized
0x1800028ed  mov     [rbp+var_38], rax
0x1800028f1  lea     rcx, AipPathMacroList; void *
0x1800028f8  lea     rax, aWindir; "%WINDIR%"
0x1800028ff  mov     [rbp+var_40], 140012h
0x180002907  mov     [rbp+var_48], rax
0x18000290b  xor     edx, edx; Val
0x18000290d  lea     rax, aSystem32; "%SYSTEM32%"
0x180002914  mov     [rbp+var_50], 120010h
0x18000291c  mov     [rbp+var_58], rax
0x180002920  xorps   xmm0, xmm0
0x180002923  lea     rax, aWindirSystem32; "%WINDIR%\\System32"
0x18000292a  mov     [rbp+var_60], 160014h
0x180002932  mov     [rbp+var_28], rax
0x180002936  lea     r8d, [rdx+48h]; Size
0x18000293a  lea     rax, aWindirSyswow64; "%WINDIR%\\SysWOW64"
0x180002941  mov     [rbp+var_30], 240022h
0x180002949  mov     [rbp+var_18], rax
0x18000294d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002951  mov     [rbp+var_20], 240022h
0x180002959  call    memset_0
0x18000295e  lea     rcx, qword_180010830
0x180002965  call    cs:__imp_RtlInitializeSRWLock
0x18000296b  lea     rax, P
0x180002972  mov     cs:AipPathMacroListInitialized, 1
0x18000297c  mov     cs:qword_180010840, rax
0x180002983  mov     cs:P, rax
0x18000298a  mov     cs:dword_180010804, 1
0x180002994  call    cs:__imp_RtlGetNtSystemRoot
0x18000299a  mov     rdx, rax; SourceString
0x18000299d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800029a1  call    cs:__imp_RtlInitUnicodeString
0x1800029a7  mov     r8d, 0Ch
0x1800029ad  lea     rdx, [rbp+DestinationString]
0x1800029b1  lea     rcx, [rbp+var_50]
0x1800029b5  call    AipAddPathMacro
0x1800029ba  test    eax, eax
0x1800029bc  js      loc_180002A50
0x1800029c2  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x1800029c6  mov     eax, 4
0x1800029cb  lea     rdx, String2
0x1800029d2  lea     rcx, xmmword_180010808
0x1800029d9  movdqu  cs:xmmword_180010808, xmm0
0x1800029e1  mov     word ptr cs:xmmword_180010808, ax
0x1800029e8  call    AipConvertToNtPath
0x1800029ed  test    eax, eax
0x1800029ef  js      short loc_180002A50
0x1800029f1  mov     r8d, 0Ch
0x1800029f7  lea     rdx, String2
0x1800029fe  lea     rcx, [rbp+var_40]
0x180002a02  call    AipAddPathMacro
0x180002a07  test    eax, eax
0x180002a09  js      short loc_180002A50
0x180002a0b  mov     r8d, 8
0x180002a11  lea     rdx, [rbp+var_30]
0x180002a15  lea     rcx, [rbp+var_60]
0x180002a19  call    AipAddPathMacro
0x180002a1e  test    eax, eax
0x180002a20  js      short loc_180002A50
0x180002a22  cmp     cs:dword_180010804, 0
0x180002a29  jz      short loc_180002A42
0x180002a2b  mov     r8d, 8
0x180002a31  lea     rdx, [rbp+var_20]
0x180002a35  lea     rcx, [rbp+var_60]
0x180002a39  call    AipAddPathMacro
0x180002a3e  test    eax, eax
0x180002a40  js      short loc_180002A50
0x180002a42  call    AipExpandPathMacros
0x180002a47  test    eax, eax
0x180002a49  js      short loc_180002A50
0x180002a4b  call    AiInitializeSoftwarePathMacroList
0x180002a50  mov     cs:?AipDllInitializeStatus@@3JA, eax; long AipDllInitializeStatus
0x180002a56  test    eax, eax
0x180002a58  js      short loc_180002A65
0x180002a5a  call    AiInitializeLib
0x180002a5f  mov     cs:?AipDllInitializeStatus@@3JA, eax; long AipDllInitializeStatus
0x180002a65  mov     eax, 1
0x180002a6a  add     rsp, 80h
0x180002a71  pop     rbp
0x180002a72  retn
```

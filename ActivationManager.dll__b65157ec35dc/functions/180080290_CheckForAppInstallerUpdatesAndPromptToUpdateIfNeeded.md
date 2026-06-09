# CheckForAppInstallerUpdatesAndPromptToUpdateIfNeeded

- ea: `0x180080290`
- end: `0x1800803ec`
- name: `CheckForAppInstallerUpdatesAndPromptToUpdateIfNeeded`
- size: `348`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpString1@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026580`

## callees

- `0x18000b5c0`
- `0x18005d2d4`
- `0x180080290`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800802da`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800802f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080318`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080337`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800802da`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800802f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080318`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080337`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x18008038b`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x18008038b`

## string_xrefs

- `0x18008032a`: `Windows.CommandLineLaunch`
- `0x18008030b`: `Windows.Protocol`

## pseudocode

```c
__int64 __fastcall CheckForAppInstallerUpdatesAndPromptToUpdateIfNeeded(
        LPCWCH lpString1,
        int a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        _DWORD *a6)
{
  _QWORD *v6; // r14
  bool v10; // bl
  int v12; // eax
  unsigned int v13; // ebx
  _DWORD *v15; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v17; // [rsp+68h] [rbp+10h] BYREF

  v6 = a5;
  v10 = 1;
  *a5 = 0;
  if ( CompareStringOrdinal(lpString1, -1, L"Windows.Launch", -1, 1) != 2
    && CompareStringOrdinal(lpString1, -1, L"Windows.File", -1, 1) != 2
    && CompareStringOrdinal(lpString1, -1, L"Windows.Protocol", -1, 1) != 2 )
  {
    v10 = CompareStringOrdinal(lpString1, -1, L"Windows.CommandLineLaunch", -1, 1) == 2;
  }
  if ( (a2 & 0x53090000) == 0 && v10 && (unsigned __int8)IsCheckForUpdatesAndWaitForInstallerIfNeededPresent() )
  {
    v17 = 0;
    LODWORD(a5) = 0;
    v12 = CheckForUpdatesAndWaitForInstallerIfNeeded(a4, a3, v6, &v17);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
        (const char *)(unsigned int)v12,
        (int)&a5);
      return v13;
    }
    v15 = a6;
    if ( v17 )
      *a6 |= 0x10u;
    if ( (_DWORD)a5 )
      *v15 |= 0x20u;
  }
  return 0;
}

```

## disassembly

```asm
0x180080290  mov     [rsp+arg_0], rbx
0x180080295  mov     [rsp+arg_10], rbp
0x18008029a  push    rsi
0x18008029b  push    rdi
0x18008029c  push    r13
0x18008029e  push    r14
0x1800802a0  push    r15
0x1800802a2  sub     rsp, 30h
0x1800802a6  mov     r14, [rsp+58h+arg_20]
0x1800802ae  or      r13d, 0FFFFFFFFh
0x1800802b2  mov     rbp, r9
0x1800802b5  mov     r15d, r8d
0x1800802b8  mov     esi, edx
0x1800802ba  lea     r8, String2; "Windows.Launch"
0x1800802c1  mov     ebx, 1
0x1800802c6  mov     r9d, r13d; cchCount2
0x1800802c9  mov     edx, r13d; cchCount1
0x1800802cc  mov     qword ptr [r14], 0
0x1800802d3  mov     rdi, rcx
0x1800802d6  mov     [rsp+58h+bIgnoreCase], ebx; bIgnoreCase
0x1800802da  call    cs:__imp_CompareStringOrdinal
0x1800802e0  cmp     eax, 2
0x1800802e3  jz      short loc_180080344
0x1800802e5  mov     r9d, r13d; cchCount2
0x1800802e8  mov     [rsp+58h+bIgnoreCase], ebx; bIgnoreCase
0x1800802ec  lea     r8, aWindowsFile; "Windows.File"
0x1800802f3  mov     edx, r13d; cchCount1
0x1800802f6  mov     rcx, rdi; lpString1
0x1800802f9  call    cs:__imp_CompareStringOrdinal
0x1800802ff  cmp     eax, 2
0x180080302  jz      short loc_180080344
0x180080304  mov     r9d, r13d; cchCount2
0x180080307  mov     [rsp+58h+bIgnoreCase], ebx; bIgnoreCase
0x18008030b  lea     r8, sourceString; "Windows.Protocol"
0x180080312  mov     edx, r13d; cchCount1
0x180080315  mov     rcx, rdi; lpString1
0x180080318  call    cs:__imp_CompareStringOrdinal
0x18008031e  cmp     eax, 2
0x180080321  jz      short loc_180080344
0x180080323  mov     r9d, r13d; cchCount2
0x180080326  mov     [rsp+58h+bIgnoreCase], ebx; bIgnoreCase
0x18008032a  lea     r8, aWindowsCommand; "Windows.CommandLineLaunch"
0x180080331  mov     edx, r13d; cchCount1
0x180080334  mov     rcx, rdi; lpString1
0x180080337  call    cs:__imp_CompareStringOrdinal
0x18008033d  cmp     eax, 2
0x180080340  jz      short loc_180080344
0x180080342  xor     bl, bl
0x180080344  test    esi, 53090000h
0x18008034a  jnz     loc_1800803D3
0x180080350  test    bl, bl
0x180080352  jz      short loc_1800803D3
0x180080354  call    IsCheckForUpdatesAndWaitForInstallerIfNeededPresent
0x180080359  test    al, al
0x18008035b  jz      short loc_1800803D3
0x18008035d  lea     rax, [rsp+58h+arg_20]
0x180080365  mov     [rsp+58h+arg_8], 0
0x18008036d  lea     r9, [rsp+58h+arg_8]
0x180080372  mov     qword ptr [rsp+58h+bIgnoreCase], rax; int
0x180080377  mov     r8, r14
0x18008037a  mov     dword ptr [rsp+58h+arg_20], 0
0x180080385  mov     edx, r15d
0x180080388  mov     rcx, rbp
0x18008038b  call    cs:__imp_CheckForUpdatesAndWaitForInstallerIfNeeded
0x180080391  mov     ebx, eax
0x180080393  test    eax, eax
0x180080395  jns     short loc_1800803B4
0x180080397  mov     rcx, [rsp+58h]; this
0x18008039c  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800803a3  mov     r9d, eax; char *
0x1800803a6  mov     edx, 0EBh; void *
0x1800803ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800803b0  mov     eax, ebx
0x1800803b2  jmp     short loc_1800803D5
0x1800803b4  cmp     [rsp+58h+arg_8], 0
0x1800803b9  mov     rax, [rsp+58h+arg_28]
0x1800803c1  jz      short loc_1800803C6
0x1800803c3  or      dword ptr [rax], 10h
0x1800803c6  cmp     dword ptr [rsp+58h+arg_20], 0
0x1800803ce  jz      short loc_1800803D3
0x1800803d0  or      dword ptr [rax], 20h
0x1800803d3  xor     eax, eax
0x1800803d5  mov     rbx, [rsp+58h+arg_0]
0x1800803da  mov     rbp, [rsp+58h+arg_10]
0x1800803df  add     rsp, 30h
0x1800803e3  pop     r15
0x1800803e5  pop     r14
0x1800803e7  pop     r13
0x1800803e9  pop     rdi
0x1800803ea  pop     rsi
0x1800803eb  retn
```

# UpdatePackageForFailedValidation(HKEY__ *)

- ea: `0x14000f2a4`
- end: `0x14000f3b1`
- name: `?UpdatePackageForFailedValidation@@YAXPEAUHKEY__@@@Z`
- size: `269`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140009e70`
- `0x14000ed9c`
- `0x140011bf9`

## callees

- `0x14000c2c0`
- `0x14000f2a4`
- `0x14000fbb0`
- `0x14000fc20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000f32d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000f32d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f2dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f38e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f2dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000f38e`

## string_xrefs

- `0x14000f2b7`: `LastValidationAttemptTime`

## pseudocode

```c
void __fastcall UpdatePackageForFailedValidation(HKEY hKey)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  int v4; // eax
  bool v5; // cl
  unsigned int v6; // eax
  unsigned int v7; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  int lpDataa; // [rsp+20h] [rbp-18h]
  unsigned int lpDatab; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v12; // [rsp+48h] [rbp+10h] BYREF
  DWORD v13; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 Data; // [rsp+58h] [rbp+20h] BYREF

  Data = GetCurrentSystemTime();
  v2 = RegSetValueExW(hKey, L"LastValidationAttemptTime", 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x28A, v3, (const char *)v2, lpData);
  v12 = 0;
  v13 = 4;
  v4 = RegQueryValueExW(hKey, L"FailedValiationCount", 0, 0, (LPBYTE)&v12, &v13);
  v5 = (v4 & 0xFFFFFFFD) == 0;
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( !v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v4,
      lpDataa);
  ++v12;
  v6 = RegSetValueExW(hKey, L"FailedValiationCount", 0, 4u, (const BYTE *)&v12, 4u);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x293, v7, (const char *)v6, lpDatab);
}

```

## disassembly

```asm
0x14000f2a4  push    rbx
0x14000f2a6  sub     rsp, 30h
0x14000f2aa  mov     rbx, rcx
0x14000f2ad  call    ?GetCurrentSystemTime@@YA_KXZ; GetCurrentSystemTime(void)
0x14000f2b2  mov     [rsp+38h+Data], rax
0x14000f2b7  lea     rdx, ValueName; "LastValidationAttemptTime"
0x14000f2be  lea     rax, [rsp+38h+Data]
0x14000f2c3  mov     [rsp+38h+cbData], 8; cbData
0x14000f2cb  mov     r9d, 0Bh; dwType
0x14000f2d1  mov     [rsp+38h+lpData], rax; unsigned int
0x14000f2d6  xor     r8d, r8d; Reserved
0x14000f2d9  mov     rcx, rbx; hKey
0x14000f2dc  call    cs:__imp_RegSetValueExW
0x14000f2e2  test    eax, eax
0x14000f2e4  jz      short loc_14000F2F9
0x14000f2e6  mov     rcx, [rsp+38h]; this
0x14000f2eb  mov     r9d, eax; char *
0x14000f2ee  mov     edx, 28Ah; void *
0x14000f2f3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f2f9  lea     rax, [rsp+38h+arg_10]
0x14000f2fe  mov     [rsp+38h+arg_8], 0
0x14000f306  mov     qword ptr [rsp+38h+cbData], rax; lpcbData
0x14000f30b  lea     rdx, aFailedvaliatio; "FailedValiationCount"
0x14000f312  lea     rax, [rsp+38h+arg_8]
0x14000f317  mov     [rsp+38h+arg_10], 4
0x14000f31f  xor     r9d, r9d; lpType
0x14000f322  mov     [rsp+38h+lpData], rax; int
0x14000f327  xor     r8d, r8d; lpReserved
0x14000f32a  mov     rcx, rbx; hKey
0x14000f32d  call    cs:__imp_RegQueryValueExW
0x14000f333  test    eax, 0FFFFFFFDh
0x14000f338  setz    cl
0x14000f33b  test    eax, eax
0x14000f33d  jle     short loc_14000F347
0x14000f33f  movzx   eax, ax
0x14000f342  or      eax, 80070000h
0x14000f347  test    cl, cl
0x14000f349  jnz     short loc_14000F365
0x14000f34b  mov     rcx, [rsp+38h]; this
0x14000f350  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000f357  mov     r9d, eax; char *
0x14000f35a  mov     edx, 290h; void *
0x14000f35f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000f365  inc     [rsp+38h+arg_8]
0x14000f369  lea     rax, [rsp+38h+arg_8]
0x14000f36e  mov     [rsp+38h+cbData], 4; cbData
0x14000f376  lea     rdx, aFailedvaliatio; "FailedValiationCount"
0x14000f37d  mov     r9d, 4; dwType
0x14000f383  mov     [rsp+38h+lpData], rax; unsigned int
0x14000f388  xor     r8d, r8d; Reserved
0x14000f38b  mov     rcx, rbx; hKey
0x14000f38e  call    cs:__imp_RegSetValueExW
0x14000f394  test    eax, eax
0x14000f396  jz      short loc_14000F3AB
0x14000f398  mov     rcx, [rsp+38h]; this
0x14000f39d  mov     r9d, eax; char *
0x14000f3a0  mov     edx, 293h; void *
0x14000f3a5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000f3ab  add     rsp, 30h
0x14000f3af  pop     rbx
0x14000f3b0  retn
```

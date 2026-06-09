# IsExtensionDriverPackage

- ea: `0x140014238`
- end: `0x140014317`
- name: `IsExtensionDriverPackage`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140014e08`

## callees

- `0x140014238`
- `0x140045ec6`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400142cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400142cd`
- `drvstore!DriverPackageClose` at `0x1400142c5`
- `drvstore!DriverPackageClose` at `0x1400142c5`
- `drvstore!DriverPackageOpenW` at `0x140014286`
- `drvstore!DriverPackageOpenW` at `0x140014286`
- `drvstore!DriverPackageGetVersionInfoW` at `0x1400142b0`
- `drvstore!DriverPackageGetVersionInfoW` at `0x1400142b0`

## pseudocode

```c
_BOOL8 __fastcall IsExtensionDriverPackage(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  DWORD LastError; // ebx
  _DWORD v6[178]; // [rsp+30h] [rbp-708h] BYREF
  _BYTE Buf1[1064]; // [rsp+2F8h] [rbp-440h] BYREF

  memset_0(v6, 0, 0x6F0u);
  v2 = DriverPackageOpenW(a1, 0xFFFF, 0, 1, 0);
  v3 = v2;
  if ( v2 )
  {
    v6[0] = 1776;
    LastError = 0;
    if ( !(unsigned int)DriverPackageGetVersionInfoW(v2, v6) )
      LastError = GetLastError();
    DriverPackageClose(v3);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return memcmp_0(Buf1, &GUID_DEVCLASS_EXTENSION, 0x10u) == 0;
}

```

## disassembly

```asm
0x140014238  mov     [rsp+arg_8], rbx
0x14001423d  push    rdi
0x14001423e  sub     rsp, 730h
0x140014245  mov     rax, cs:__security_cookie
0x14001424c  xor     rax, rsp
0x14001424f  mov     [rsp+738h+var_18], rax
0x140014257  mov     rbx, rcx
0x14001425a  xor     edx, edx; Val
0x14001425c  lea     rcx, [rsp+738h+var_708]; void *
0x140014261  mov     r8d, 6F0h; Size
0x140014267  call    memset_0
0x14001426c  mov     edx, 0FFFFh
0x140014271  mov     [rsp+738h+var_718], 0
0x14001427a  mov     r9d, 1
0x140014280  xor     r8d, r8d
0x140014283  mov     rcx, rbx
0x140014286  call    cs:__imp_DriverPackageOpenW
0x14001428c  mov     rdi, rax
0x14001428f  test    rax, rax
0x140014292  jnz     short loc_14001429E
0x140014294  call    cs:__imp_GetLastError
0x14001429a  mov     ebx, eax
0x14001429c  jmp     short loc_1400142CB
0x14001429e  lea     rdx, [rsp+738h+var_708]
0x1400142a3  mov     [rsp+738h+var_708], 6F0h
0x1400142ab  mov     rcx, rdi
0x1400142ae  xor     ebx, ebx
0x1400142b0  call    cs:__imp_DriverPackageGetVersionInfoW
0x1400142b6  test    eax, eax
0x1400142b8  jnz     short loc_1400142C2
0x1400142ba  call    cs:__imp_GetLastError
0x1400142c0  mov     ebx, eax
0x1400142c2  mov     rcx, rdi
0x1400142c5  call    cs:__imp_DriverPackageClose
0x1400142cb  mov     ecx, ebx; dwErrCode
0x1400142cd  call    cs:__imp_SetLastError
0x1400142d3  mov     r8d, 10h; Size
0x1400142d9  lea     rdx, GUID_DEVCLASS_EXTENSION; Buf2
0x1400142e0  lea     rcx, [rsp+738h+Buf1]; Buf1
0x1400142e8  call    memcmp_0
0x1400142ed  xor     ecx, ecx
0x1400142ef  test    eax, eax
0x1400142f1  setz    cl
0x1400142f4  mov     eax, ecx
0x1400142f6  mov     rcx, [rsp+738h+var_18]
0x1400142fe  xor     rcx, rsp; StackCookie
0x140014301  call    __security_check_cookie
0x140014306  mov     rbx, [rsp+738h+arg_8]
0x14001430e  add     rsp, 730h
0x140014315  pop     rdi
0x140014316  retn
```

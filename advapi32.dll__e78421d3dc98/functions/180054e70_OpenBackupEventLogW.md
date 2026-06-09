# OpenBackupEventLogW

- ea: `0x180054e70`
- end: `0x180054f2e`
- name: `OpenBackupEventLogW`
- size: `190`
- prototype: `HANDLE __stdcall(LPCWSTR lpUNCServerName, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x180054a68`
- `0x180054e70`
- `0x180055bd4`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180054ec4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180054ec4`
- `ntdll!RtlFreeHeap` at `0x180054f07`
- `ntdll!RtlFreeHeap` at `0x180054f07`
- `ntdll!RtlInitUnicodeString` at `0x180054ea0`
- `ntdll!RtlInitUnicodeString` at `0x180054eac`
- `ntdll!RtlInitUnicodeString` at `0x180054ea0`
- `ntdll!RtlInitUnicodeString` at `0x180054eac`
- `KERNEL32!SetLastError` at `0x180054ed1`
- `KERNEL32!SetLastError` at `0x180054ed1`

## pseudocode

```c
HANDLE __stdcall OpenBackupEventLogW(LPCWSTR lpUNCServerName, LPCWSTR lpFileName)
{
  int v4; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  void *v7; // [rsp+58h] [rbp+18h] BYREF

  DestinationString = 0;
  v7 = 0;
  NtPathName = 0;
  RtlInitUnicodeString(&DestinationString, lpUNCServerName);
  RtlInitUnicodeString(&NtPathName, 0);
  if ( lpFileName && !RtlDosPathNameToNtPathName_U(lpFileName, &NtPathName, 0, 0) )
  {
    SetLastError(0x7Bu);
    return 0;
  }
  v4 = OpenBackupEventLogW_Client(&DestinationString, &NtPathName, &v7);
  if ( NtPathName.MaximumLength )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v4 < 0 )
  {
    BaseSetLastNTError_0((unsigned int)v4);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180054e70  mov     [rsp-8+arg_0], rbx
0x180054e75  mov     [rsp-8+arg_10], rdi
0x180054e7a  push    rbp
0x180054e7b  mov     rbp, rsp
0x180054e7e  sub     rsp, 40h
0x180054e82  mov     rbx, rdx
0x180054e85  xorps   xmm0, xmm0
0x180054e88  mov     rdx, rcx; SourceString
0x180054e8b  xorps   xmm1, xmm1
0x180054e8e  xor     edi, edi
0x180054e90  lea     rcx, [rbp+DestinationString]; DestinationString
0x180054e94  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180054e98  mov     [rbp+arg_8], rdi
0x180054e9c  movups  xmmword ptr [rbp+NtPathName.Length], xmm1
0x180054ea0  call    cs:__imp_RtlInitUnicodeString
0x180054ea6  xor     edx, edx; SourceString
0x180054ea8  lea     rcx, [rbp+NtPathName]; DestinationString
0x180054eac  call    cs:__imp_RtlInitUnicodeString
0x180054eb2  test    rbx, rbx
0x180054eb5  jz      short loc_180054EDB
0x180054eb7  xor     r9d, r9d; DirectoryInfo
0x180054eba  lea     rdx, [rbp+NtPathName]; NtPathName
0x180054ebe  xor     r8d, r8d; NtFileNamePart
0x180054ec1  mov     rcx, rbx; DosPathName
0x180054ec4  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180054eca  test    al, al
0x180054ecc  jnz     short loc_180054EDB
0x180054ece  lea     ecx, [rdi+7Bh]; dwErrCode
0x180054ed1  call    cs:__imp_SetLastError
0x180054ed7  xor     eax, eax
0x180054ed9  jmp     short loc_180054F1E
0x180054edb  lea     r8, [rbp+arg_8]
0x180054edf  lea     rdx, [rbp+NtPathName]
0x180054ee3  lea     rcx, [rbp+DestinationString]
0x180054ee7  call    OpenBackupEventLogW_Client
0x180054eec  mov     ebx, eax
0x180054eee  cmp     [rbp+NtPathName.MaximumLength], di
0x180054ef2  jz      short loc_180054F0D
0x180054ef4  mov     rcx, gs:60h
0x180054efd  xor     edx, edx; Flags
0x180054eff  mov     r8, [rbp+NtPathName.Buffer]; P
0x180054f03  mov     rcx, [rcx+30h]; HeapHandle
0x180054f07  call    cs:__imp_RtlFreeHeap
0x180054f0d  test    ebx, ebx
0x180054f0f  jns     short loc_180054F1A
0x180054f11  mov     ecx, ebx
0x180054f13  call    BaseSetLastNTError_0
0x180054f18  jmp     short loc_180054ED7
0x180054f1a  mov     rax, [rbp+arg_8]
0x180054f1e  mov     rbx, [rsp+40h+arg_0]
0x180054f23  mov     rdi, [rsp+40h+arg_10]
0x180054f28  add     rsp, 40h
0x180054f2c  pop     rbp
0x180054f2d  retn
```

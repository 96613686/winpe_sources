# OpenBackupEventLogW

- ea: `0x180060ca0`
- end: `0x180060d7d`
- name: `OpenBackupEventLogW`
- size: `221`
- prototype: `HANDLE __stdcall(LPCWSTR lpUNCServerName, LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800607b0`
- `0x180060ca0`
- `0x180061b38`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180060d00`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180060d00`
- `ntdll!RtlFreeHeap` at `0x180060d4f`
- `ntdll!RtlFreeHeap` at `0x180060d4f`
- `ntdll!RtlInitUnicodeString` at `0x180060cd0`
- `ntdll!RtlInitUnicodeString` at `0x180060ce2`
- `ntdll!RtlInitUnicodeString` at `0x180060cd0`
- `ntdll!RtlInitUnicodeString` at `0x180060ce2`
- `KERNEL32!SetLastError` at `0x180060d13`
- `KERNEL32!SetLastError` at `0x180060d13`

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
0x180060ca0  mov     [rsp-8+arg_0], rbx
0x180060ca5  mov     [rsp-8+arg_10], rdi
0x180060caa  push    rbp
0x180060cab  mov     rbp, rsp
0x180060cae  sub     rsp, 40h
0x180060cb2  mov     rbx, rdx
0x180060cb5  xorps   xmm0, xmm0
0x180060cb8  mov     rdx, rcx; SourceString
0x180060cbb  xorps   xmm1, xmm1
0x180060cbe  xor     edi, edi
0x180060cc0  lea     rcx, [rbp+DestinationString]; DestinationString
0x180060cc4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180060cc8  mov     [rbp+arg_8], rdi
0x180060ccc  movups  xmmword ptr [rbp+NtPathName.Length], xmm1
0x180060cd0  call    cs:__imp_RtlInitUnicodeString
0x180060cd7  nop     dword ptr [rax+rax+00h]
0x180060cdc  xor     edx, edx; SourceString
0x180060cde  lea     rcx, [rbp+NtPathName]; DestinationString
0x180060ce2  call    cs:__imp_RtlInitUnicodeString
0x180060ce9  nop     dword ptr [rax+rax+00h]
0x180060cee  test    rbx, rbx
0x180060cf1  jz      short loc_180060D23
0x180060cf3  xor     r9d, r9d; DirectoryInfo
0x180060cf6  lea     rdx, [rbp+NtPathName]; NtPathName
0x180060cfa  xor     r8d, r8d; NtFileNamePart
0x180060cfd  mov     rcx, rbx; DosPathName
0x180060d00  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180060d07  nop     dword ptr [rax+rax+00h]
0x180060d0c  test    al, al
0x180060d0e  jnz     short loc_180060D23
0x180060d10  lea     ecx, [rdi+7Bh]; dwErrCode
0x180060d13  call    cs:__imp_SetLastError
0x180060d1a  nop     dword ptr [rax+rax+00h]
0x180060d1f  xor     eax, eax
0x180060d21  jmp     short loc_180060D6C
0x180060d23  lea     r8, [rbp+arg_8]
0x180060d27  lea     rdx, [rbp+NtPathName]
0x180060d2b  lea     rcx, [rbp+DestinationString]
0x180060d2f  call    OpenBackupEventLogW_Client
0x180060d34  mov     ebx, eax
0x180060d36  cmp     [rbp+NtPathName.MaximumLength], di
0x180060d3a  jz      short loc_180060D5B
0x180060d3c  mov     rcx, gs:60h
0x180060d45  xor     edx, edx; Flags
0x180060d47  mov     r8, [rbp+NtPathName.Buffer]; P
0x180060d4b  mov     rcx, [rcx+30h]; HeapHandle
0x180060d4f  call    cs:__imp_RtlFreeHeap
0x180060d56  nop     dword ptr [rax+rax+00h]
0x180060d5b  test    ebx, ebx
0x180060d5d  jns     short loc_180060D68
0x180060d5f  mov     ecx, ebx
0x180060d61  call    BaseSetLastNTError_0
0x180060d66  jmp     short loc_180060D1F
0x180060d68  mov     rax, [rbp+arg_8]
0x180060d6c  mov     rbx, [rsp+40h+arg_0]
0x180060d71  mov     rdi, [rsp+40h+arg_10]
0x180060d76  add     rsp, 40h
0x180060d7a  pop     rbp
0x180060d7b  retn
```

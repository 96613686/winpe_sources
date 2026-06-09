# PlatformFileOperationBroker::SetFileIntegrityMedium(ushort const *)

- ea: `0x180029da0`
- end: `0x180029e3e`
- name: `?SetFileIntegrityMedium@PlatformFileOperationBroker@@UEAAJPEBG@Z`
- size: `158`
- prototype: `__int64 __fastcall(PlatformFileOperationBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e428`
- `0x180029ce8`
- `0x180029da0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e0e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029de8`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029de8`

## pseudocode

```c
__int64 __fastcall PlatformFileOperationBroker::SetFileIntegrityMedium(
        PlatformFileOperationBroker *this,
        const unsigned __int16 *a2)
{
  int PIC; // ebx
  void *File2; // rax
  void *v5; // rdi
  signed int LastError; // eax
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v8);
  if ( PIC >= 0 )
  {
    File2 = (void *)CreateFile2(a2, 917504, 0, 3, 0);
    v5 = File2;
    if ( File2 == (void *)-1LL )
    {
      LastError = GetLastError();
      PIC = LastError;
      if ( LastError > 0 )
        PIC = (unsigned __int16)LastError | 0x80070000;
      if ( PIC == -2147024891 )
        return 1;
    }
    else
    {
      anonymous_namespace_::SetFileIntegrityLevel(File2);
      PIC = 1;
      CloseHandle(v5);
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180029da0  mov     rax, rsp
0x180029da3  mov     [rax+8], rbx
0x180029da7  mov     [rax+10h], rsi
0x180029dab  push    rdi
0x180029dac  sub     rsp, 30h
0x180029db0  mov     rdi, rdx
0x180029db3  mov     dword ptr [rax+18h], 0
0x180029dba  mov     esi, 1
0x180029dbf  lea     rdx, [rax+18h]; unsigned int *
0x180029dc3  mov     ecx, esi; unsigned int
0x180029dc5  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180029dca  mov     ebx, eax
0x180029dcc  test    eax, eax
0x180029dce  js      short loc_180029E2C
0x180029dd0  lea     r9d, [rsi+2]
0x180029dd4  mov     [rsp+38h+var_18], 0
0x180029ddd  xor     r8d, r8d
0x180029de0  mov     edx, 0E0000h
0x180029de5  mov     rcx, rdi
0x180029de8  call    cs:__imp_CreateFile2
0x180029dee  mov     rdi, rax
0x180029df1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029df5  jz      short loc_180029E0E
0x180029df7  xor     edx, edx
0x180029df9  mov     rcx, rax; Handle
0x180029dfc  call    _anonymous_namespace___SetFileIntegrityLevel
0x180029e01  mov     rcx, rdi; hObject
0x180029e04  mov     ebx, esi
0x180029e06  call    cs:__imp_CloseHandle
0x180029e0c  jmp     short loc_180029E2C
0x180029e0e  call    cs:__imp_GetLastError
0x180029e14  mov     ebx, eax
0x180029e16  test    eax, eax
0x180029e18  jle     short loc_180029E23
0x180029e1a  movzx   ebx, ax
0x180029e1d  or      ebx, 80070000h
0x180029e23  cmp     ebx, 80070005h
0x180029e29  cmovz   ebx, esi
0x180029e2c  mov     rsi, [rsp+38h+arg_8]
0x180029e31  mov     eax, ebx
0x180029e33  mov     rbx, [rsp+38h+arg_0]
0x180029e38  add     rsp, 30h
0x180029e3c  pop     rdi
0x180029e3d  retn
```

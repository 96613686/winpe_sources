# FileOperationBroker::GetReadableFileHandle(ulong,ushort const *,unsigned __int64 *)

- ea: `0x1800287c0`
- end: `0x18002887a`
- name: `?GetReadableFileHandle@FileOperationBroker@@UEAAJKPEBGPEA_K@Z`
- size: `186`
- prototype: `int(FileOperationBroker *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000e428`
- `0x1800287c0`
- `0x18002ae4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028826`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002880e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18002880e`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::GetReadableFileHandle(
        FileOperationBroker *this,
        DWORD a2,
        const unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  int PIC; // ecx
  void *File2; // rbx
  DWORD CurrentProcessId; // eax
  unsigned int v10; // r9d
  signed int LastError; // eax
  unsigned int v13; // [rsp+20h] [rbp-28h]
  void *v14[3]; // [rsp+30h] [rbp-18h] BYREF

  LODWORD(v14[0]) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)v14);
  if ( PIC >= 0 )
  {
    File2 = (void *)CreateFile2(a3, 0x80000000LL, 1, 3, 0);
    if ( File2 == (void *)-1LL )
    {
      LastError = GetLastError();
      PIC = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v14[0] = 0;
      CurrentProcessId = GetCurrentProcessId();
      PIC = DuplicateHandleForMarshaling(CurrentProcessId, File2, a2, v10, v13, v14);
      if ( PIC >= 0 )
        *a4 = (unsigned __int64)v14[0];
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x1800287c0  mov     rax, rsp
0x1800287c3  mov     [rax+8], rbx
0x1800287c7  mov     [rax+10h], rsi
0x1800287cb  push    rdi
0x1800287cc  sub     rsp, 40h
0x1800287d0  mov     esi, edx
0x1800287d2  mov     dword ptr [rax-18h], 0
0x1800287d9  lea     rdx, [rax-18h]; unsigned int *
0x1800287dd  mov     ecx, 1; unsigned int
0x1800287e2  mov     rdi, r9
0x1800287e5  mov     rbx, r8
0x1800287e8  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x1800287ed  mov     ecx, eax
0x1800287ef  test    eax, eax
0x1800287f1  js      short loc_180028868
0x1800287f3  mov     r9d, 3
0x1800287f9  mov     qword ptr [rsp+48h+var_28], 0; unsigned int
0x180028802  mov     edx, 80000000h
0x180028807  mov     rcx, rbx
0x18002880a  lea     r8d, [r9-2]
0x18002880e  call    cs:__imp_CreateFile2
0x180028814  mov     rbx, rax
0x180028817  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002881b  jz      short loc_180028853
0x18002881d  mov     [rsp+48h+var_18], 0
0x180028826  call    cs:__imp_GetCurrentProcessId
0x18002882c  mov     r8d, esi; DWORD
0x18002882f  mov     rdx, rbx; hObject
0x180028832  mov     ecx, eax; dwProcessId
0x180028834  lea     rax, [rsp+48h+var_18]
0x180028839  mov     [rsp+48h+var_20], rax; void **
0x18002883e  call    ?DuplicateHandleForMarshaling@@YAJKPEAXKKKPEAPEAX@Z; DuplicateHandleForMarshaling(ulong,void *,ulong,ulong,ulong,void * *)
0x180028843  mov     ecx, eax
0x180028845  test    eax, eax
0x180028847  js      short loc_180028868
0x180028849  mov     rax, [rsp+48h+var_18]
0x18002884e  mov     [rdi], rax
0x180028851  jmp     short loc_180028868
0x180028853  call    cs:__imp_GetLastError
0x180028859  mov     ecx, eax
0x18002885b  test    eax, eax
0x18002885d  jle     short loc_180028868
0x18002885f  movzx   ecx, ax
0x180028862  or      ecx, 80070000h
0x180028868  mov     rbx, [rsp+48h+arg_0]
0x18002886d  mov     eax, ecx
0x18002886f  mov     rsi, [rsp+48h+arg_8]
0x180028874  add     rsp, 40h
0x180028878  pop     rdi
0x180028879  retn
```

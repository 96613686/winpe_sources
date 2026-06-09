# CfpGetSyncRootInfoByPath

- ea: `0x18000f7c4`
- end: `0x18000f856`
- name: `CfpGetSyncRootInfoByPath`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f610`
- `0x180011e18`

## callees

- `0x18000446c`
- `0x18000f6fc`
- `0x18000f7c4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000f800`
- `ntdll!RtlNtStatusToDosError` at `0x18000f800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f845`

## pseudocode

```c
__int64 __fastcall CfpGetSyncRootInfoByPath(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS v5; // eax
  signed int v6; // eax
  signed int SyncRootInfoByHandle; // ebx
  __int64 v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+30h] [rbp-58h]
  HANDLE hObject; // [rsp+50h] [rbp-38h] BYREF

  hObject = (HANDLE)-1LL;
  v5 = CfpCreateFile(a1, a2, 0, 7u, v9, 0x20u, v10, &hObject);
  v6 = RtlNtStatusToDosError(v5);
  SyncRootInfoByHandle = v6;
  if ( v6 > 0 )
    SyncRootInfoByHandle = (unsigned __int16)v6 | 0x80070000;
  if ( SyncRootInfoByHandle >= 0 )
    SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, a5);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return (unsigned int)SyncRootInfoByHandle;
}

```

## disassembly

```asm
0x18000f7c4  push    rbx
0x18000f7c6  push    rbp
0x18000f7c7  push    rsi
0x18000f7c8  push    rdi
0x18000f7c9  sub     rsp, 68h
0x18000f7cd  lea     rax, [rsp+88h+hObject]
0x18000f7d2  mov     [rsp+88h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000f7db  mov     edi, r9d
0x18000f7de  mov     [rsp+88h+var_50], rax
0x18000f7e3  mov     rsi, r8
0x18000f7e6  mov     [rsp+88h+var_60], 20h ; ' '
0x18000f7ee  mov     r9d, 7
0x18000f7f4  xor     r8d, r8d
0x18000f7f7  mov     ebp, edx
0x18000f7f9  call    CfpCreateFile
0x18000f7fe  mov     ecx, eax; Status
0x18000f800  call    cs:__imp_RtlNtStatusToDosError
0x18000f806  mov     ebx, eax
0x18000f808  test    eax, eax
0x18000f80a  jle     short loc_18000F815
0x18000f80c  movzx   ebx, ax
0x18000f80f  or      ebx, 80070000h
0x18000f815  test    ebx, ebx
0x18000f817  js      short loc_18000F83A
0x18000f819  mov     rax, [rsp+88h+arg_20]
0x18000f821  mov     r9d, edi
0x18000f824  mov     rcx, [rsp+88h+hObject]; hFile
0x18000f829  mov     r8, rsi
0x18000f82c  mov     edx, ebp
0x18000f82e  mov     [rsp+88h+var_68], rax; __int64
0x18000f833  call    CfpGetSyncRootInfoByHandle
0x18000f838  mov     ebx, eax
0x18000f83a  mov     rcx, [rsp+88h+hObject]; hObject
0x18000f83f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f843  jz      short loc_18000F84B
0x18000f845  call    cs:__imp_CloseHandle
0x18000f84b  mov     eax, ebx
0x18000f84d  add     rsp, 68h
0x18000f851  pop     rdi
0x18000f852  pop     rsi
0x18000f853  pop     rbp
0x18000f854  pop     rbx
0x18000f855  retn
```

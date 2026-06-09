# ServiceManager::UpdateMapsRepairAttempts(void)

- ea: `0x18001dad0`
- end: `0x18001db5a`
- name: `?UpdateMapsRepairAttempts@ServiceManager@@AEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180013870`

## callees

- `0x18001dad0`

## import_xrefs

- `MosStorage!MosStorageResetPreferredLocationIfDefined` at `0x18001db35`
- `MosStorage!MosStorageResetPreferredLocationIfDefined` at `0x18001db35`
- `MosStorage!MosStorageSetMapsRepairAttempts` at `0x18001db1a`
- `MosStorage!MosStorageSetMapsRepairAttempts` at `0x18001db1a`
- `MosStorage!MosStorageGetMapsRepairAttempts` at `0x18001daea`
- `MosStorage!MosStorageGetMapsRepairAttempts` at `0x18001daea`
- `MosStorage!MosStorageResetCacheValues` at `0x18001db47`
- `MosStorage!MosStorageResetCacheValues` at `0x18001db47`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001db06`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001db06`

## string_xrefs

- `0x18001dafd`: `ServiceManager::UpdateMapsRepairAttempts`

## pseudocode

```c
__int64 __fastcall ServiceManager::UpdateMapsRepairAttempts(ServiceManager *this)
{
  int MapsRepairAttempts; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  MapsRepairAttempts = MosStorageGetMapsRepairAttempts(&v6);
  if ( MapsRepairAttempts >= 0 )
  {
    MapsRepairAttempts = MosStorageSetMapsRepairAttempts(++v6);
    if ( MapsRepairAttempts >= 0 )
    {
      v4 = 0;
      if ( v6 <= 3 )
        return v4;
      MapsRepairAttempts = MosStorageResetPreferredLocationIfDefined();
      if ( MapsRepairAttempts >= 0 )
      {
        MosStorageResetCacheValues();
        return v4;
      }
      v3 = 4116;
    }
    else
    {
      v3 = 4111;
    }
  }
  else
  {
    v3 = 4110;
  }
  return (unsigned int)ZTraceReportPropagation(MapsRepairAttempts, "ServiceManager::UpdateMapsRepairAttempts", v3, this);
}

```

## disassembly

```asm
0x18001dad0  mov     [rsp+arg_0], rbx
0x18001dad5  push    rdi
0x18001dad6  sub     rsp, 20h
0x18001dada  mov     rdi, rcx
0x18001dadd  mov     [rsp+28h+arg_8], 0
0x18001dae5  lea     rcx, [rsp+28h+arg_8]
0x18001daea  call    cs:__imp_?MosStorageGetMapsRepairAttempts@@YAJPEAK@Z; MosStorageGetMapsRepairAttempts(ulong *)
0x18001daf0  test    eax, eax
0x18001daf2  jns     short loc_18001DB10
0x18001daf4  mov     r8d, 100Eh
0x18001dafa  mov     r9, rdi
0x18001dafd  lea     rdx, aServicemanager_7; "ServiceManager::UpdateMapsRepairAttempt"...
0x18001db04  mov     ecx, eax
0x18001db06  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001db0c  mov     ebx, eax
0x18001db0e  jmp     short loc_18001DB4D
0x18001db10  mov     ecx, [rsp+28h+arg_8]
0x18001db14  inc     ecx
0x18001db16  mov     [rsp+28h+arg_8], ecx
0x18001db1a  call    cs:__imp_?MosStorageSetMapsRepairAttempts@@YAJK@Z; MosStorageSetMapsRepairAttempts(ulong)
0x18001db20  test    eax, eax
0x18001db22  jns     short loc_18001DB2C
0x18001db24  mov     r8d, 100Fh
0x18001db2a  jmp     short loc_18001DAFA
0x18001db2c  xor     ebx, ebx
0x18001db2e  cmp     [rsp+28h+arg_8], 3
0x18001db33  jbe     short loc_18001DB4D
0x18001db35  call    cs:__imp_?MosStorageResetPreferredLocationIfDefined@@YAJXZ; MosStorageResetPreferredLocationIfDefined(void)
0x18001db3b  test    eax, eax
0x18001db3d  jns     short loc_18001DB47
0x18001db3f  mov     r8d, 1014h
0x18001db45  jmp     short loc_18001DAFA
0x18001db47  call    cs:__imp_?MosStorageResetCacheValues@@YAXXZ; MosStorageResetCacheValues(void)
0x18001db4d  mov     eax, ebx
0x18001db4f  mov     rbx, [rsp+28h+arg_0]
0x18001db54  add     rsp, 20h
0x18001db58  pop     rdi
0x18001db59  retn
```

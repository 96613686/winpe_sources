# POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(_GUID const &,void * *)

- ea: `0x18001ab40`
- end: `0x18001abb0`
- name: `?CreateDataSource@UnifiedStoreAggregateDataSource@POOMIndexing@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013254`
- `0x1800150d8`

## callees

- `0x18000428c`
- `0x18001ab40`
- `0x18001abb8`
- `0x18001b400`

## import_xrefs

- `unistore!CreateStoreManager` at `0x18001ab64`
- `unistore!CreateStoreManager` at `0x18001ab64`

## pseudocode

```c
__int64 __fastcall POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(const struct _GUID *a1, void **a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int DataSource; // ebx
  struct IUSStoreManager *v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v4 = CreateStoreManager(0, &v8);
  DataSource = v4;
  if ( v4 >= 0 )
    DataSource = POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(v8, a1, a2);
  else
    Log_HREvent_6((unsigned int)v4, 1, v5, 58);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
  return DataSource;
}

```

## disassembly

```asm
0x18001ab40  mov     rax, rsp
0x18001ab43  mov     [rax+8], rbx
0x18001ab47  mov     [rax+10h], rsi
0x18001ab4b  push    rdi
0x18001ab4c  sub     rsp, 30h
0x18001ab50  mov     rdi, rdx
0x18001ab53  mov     qword ptr [rax+18h], 0
0x18001ab5b  mov     rsi, rcx
0x18001ab5e  lea     rdx, [rax+18h]
0x18001ab62  xor     ecx, ecx
0x18001ab64  call    cs:__imp_CreateStoreManager
0x18001ab6a  mov     ebx, eax
0x18001ab6c  test    eax, eax
0x18001ab6e  jns     short loc_18001AB82
0x18001ab70  mov     edx, 1
0x18001ab75  mov     ecx, eax
0x18001ab77  lea     r9d, [rdx+39h]
0x18001ab7b  call    Log_HREvent_6
0x18001ab80  jmp     short loc_18001AB94
0x18001ab82  mov     rcx, [rsp+38h+arg_10]; struct IUSStoreManager *
0x18001ab87  mov     r8, rdi; void **
0x18001ab8a  mov     rdx, rsi; struct _GUID *
0x18001ab8d  call    ?CreateDataSource@UnifiedStoreAggregateDataSource@POOMIndexing@@SAJPEAUIUSStoreManager@@AEBU_GUID@@PEAPEAX@Z; POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(IUSStoreManager *,_GUID const &,void * *)
0x18001ab92  mov     ebx, eax
0x18001ab94  lea     rcx, [rsp+38h+arg_10]
0x18001ab99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ab9e  mov     rsi, [rsp+38h+arg_8]
0x18001aba3  mov     eax, ebx
0x18001aba5  mov     rbx, [rsp+38h+arg_0]
0x18001abaa  add     rsp, 30h
0x18001abae  pop     rdi
0x18001abaf  retn
```

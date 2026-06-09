# CMetaData::mdGetAllMetaData(IRowset *)

- ea: `0x180002b1c`
- end: `0x180002ccb`
- name: `?mdGetAllMetaData@CMetaData@@QEAAXPEAUIRowset@@@Z`
- size: `431`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x180007010`
- `0x18001adfc`

## callees

- `0x18000261c`
- `0x18000266c`
- `0x180002a24`
- `0x180002b1c`
- `0x180002f8c`
- `0x1800030c4`
- `0x180003638`
- `0x180003af4`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002c98`
- `ole32!CoTaskMemFree` at `0x180002ca3`
- `ole32!CoTaskMemFree` at `0x180002cae`
- `ole32!CoTaskMemFree` at `0x180002c98`
- `ole32!CoTaskMemFree` at `0x180002ca3`
- `ole32!CoTaskMemFree` at `0x180002cae`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdGetAllMetaData(CMetaData *this, struct IRowset *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // ebx
  int v8; // ebx
  CMetaData *v9; // rcx
  unsigned int v10; // ebx
  struct IRowset *v11; // rdx
  LPVOID v12; // rax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v15; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  struct tagDBCOLUMNINFO *v17; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v17 = 0;
  pv = 0;
  v15 = 0;
  if ( !(unsigned int)CMetaData::mdGetColumnsUpdateInfo(this, a2, (unsigned __int16 **)&pv, &v15) )
  {
    v4 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsInfo,
           &v13);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048498[0] )
          bidTraceW(off_1800481B8[0], 203776, off_180048498[0], (unsigned int)v4, 199);
      }
      ThrowHR(v5);
    }
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagDBCOLUMNINFO **, LPVOID *))(*(_QWORD *)v13 + 24LL))(
           v13,
           &v14,
           &v17,
           &pv);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048490[0] )
        bidTraceW(off_1800481B8[0], 206848, off_180048490[0], (unsigned int)v6, 202);
      ThrowHR(v7);
    }
    v8 = DownsizeToULONGThrow<unsigned __int64>(v14);
    v10 = CMetaData::mdGetHiddenCount(v9, a2) + v8;
    if ( (unsigned int)CMetaData::mdFNeedColumnsRowset(this, a2, v10, v17) )
      CMetaData::mdGetColumnsRowsetData(this, a2, v10);
    if ( !*((_QWORD *)this + 4) )
      CMetaData::mdGetColumnsInfo(this, v11, v10, v17);
  }
  v12 = pv;
  pv = 0;
  *((_QWORD *)this + 2) = v12;
  *((_QWORD *)this + 3) = v15;
  CoTaskMemFree(0);
  CoTaskMemFree(pv);
  CoTaskMemFree(v17);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v13);
}

```

## disassembly

```asm
0x180002b1c  mov     [rsp-18h+arg_0], rbx
0x180002b21  push    rbp
0x180002b22  push    rsi
0x180002b23  push    rdi
0x180002b24  mov     rbp, rsp
0x180002b27  sub     rsp, 50h
0x180002b2b  mov     rsi, rdx
0x180002b2e  mov     rdi, rcx
0x180002b31  mov     [rbp+var_20], 0
0x180002b39  mov     [rbp+arg_18], 0
0x180002b41  mov     [rbp+pv], 0
0x180002b49  mov     [rbp+var_10], 0
0x180002b51  lea     r9, [rbp+var_10]; unsigned __int8 **
0x180002b55  lea     r8, [rbp+pv]; unsigned __int16 **
0x180002b59  call    ?mdGetColumnsUpdateInfo@CMetaData@@AEAAHPEAUIRowset@@PEAPEAGPEAPEAE@Z; CMetaData::mdGetColumnsUpdateInfo(IRowset *,ushort * *,uchar * *)
0x180002b5e  test    eax, eax
0x180002b60  jnz     loc_180002C7E
0x180002b66  mov     rax, [rsi]
0x180002b69  lea     r8, [rbp+var_20]
0x180002b6d  lea     rdx, IID_IColumnsInfo
0x180002b74  mov     rcx, rsi
0x180002b77  mov     rax, [rax]
0x180002b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7f  mov     ebx, eax
0x180002b81  test    eax, eax
0x180002b83  jns     short loc_180002BC5
0x180002b85  test    byte ptr cs:_bidGblFlags, 2
0x180002b8c  jz      short loc_180002BBD
0x180002b8e  mov     rcx, cs:off_180048498; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002b95  test    rcx, rcx
0x180002b98  jz      short loc_180002BBD
0x180002b9a  mov     [rsp+50h+var_30], 0C7h
0x180002ba2  mov     r9d, eax
0x180002ba5  mov     r8, cs:off_180048498; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002bac  mov     edx, 31C00h
0x180002bb1  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002bb8  call    _bidTraceW
0x180002bbd  mov     ecx, ebx; int
0x180002bbf  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180002bc5  mov     [rbp+var_18], 0
0x180002bcd  mov     rcx, [rbp+var_20]
0x180002bd1  mov     rax, [rcx]
0x180002bd4  lea     r9, [rbp+pv]
0x180002bd8  lea     r8, [rbp+arg_18]
0x180002bdc  lea     rdx, [rbp+var_18]
0x180002be0  mov     rax, [rax+18h]
0x180002be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be9  mov     ebx, eax
0x180002beb  test    eax, eax
0x180002bed  jns     short loc_180002C2F
0x180002bef  test    byte ptr cs:_bidGblFlags, 2
0x180002bf6  jz      short loc_180002C27
0x180002bf8  mov     rcx, cs:off_180048490; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002bff  test    rcx, rcx
0x180002c02  jz      short loc_180002C27
0x180002c04  mov     [rsp+50h+var_30], 0CAh
0x180002c0c  mov     r9d, eax
0x180002c0f  mov     r8, cs:off_180048490; "<CMetaData::mdGetAllMetaData|ADO|ERR>  "...
0x180002c16  mov     edx, 32800h
0x180002c1b  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002c22  call    _bidTraceW
0x180002c27  mov     ecx, ebx; int
0x180002c29  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180002c2f  mov     rcx, [rbp+var_18]
0x180002c33  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180002c38  mov     ebx, eax
0x180002c3a  mov     rdx, rsi; struct IRowset *
0x180002c3d  call    ?mdGetHiddenCount@CMetaData@@AEAAKPEAUIRowset@@@Z; CMetaData::mdGetHiddenCount(IRowset *)
0x180002c42  add     ebx, eax
0x180002c44  mov     r9, [rbp+arg_18]; struct tagDBCOLUMNINFO *
0x180002c48  mov     r8d, ebx; unsigned int
0x180002c4b  mov     rdx, rsi; struct IRowset *
0x180002c4e  mov     rcx, rdi; this
0x180002c51  call    ?mdFNeedColumnsRowset@CMetaData@@AEAAHPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z; CMetaData::mdFNeedColumnsRowset(IRowset *,ulong,tagDBCOLUMNINFO *)
0x180002c56  test    eax, eax
0x180002c58  jz      short loc_180002C68
0x180002c5a  mov     r8d, ebx; unsigned int
0x180002c5d  mov     rdx, rsi; struct IRowset *
0x180002c60  mov     rcx, rdi; this
0x180002c63  call    ?mdGetColumnsRowsetData@CMetaData@@AEAAXPEAUIRowset@@K@Z; CMetaData::mdGetColumnsRowsetData(IRowset *,ulong)
0x180002c68  cmp     qword ptr [rdi+20h], 0
0x180002c6d  jnz     short loc_180002C7E
0x180002c6f  mov     r9, [rbp+arg_18]; struct tagDBCOLUMNINFO *
0x180002c73  mov     r8d, ebx; unsigned int
0x180002c76  mov     rcx, rdi; this
0x180002c79  call    ?mdGetColumnsInfo@CMetaData@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z; CMetaData::mdGetColumnsInfo(IRowset *,ulong,tagDBCOLUMNINFO *)
0x180002c7e  mov     rax, [rbp+pv]
0x180002c82  mov     [rbp+pv], 0
0x180002c8a  mov     [rdi+10h], rax
0x180002c8e  mov     rax, [rbp+var_10]
0x180002c92  mov     [rdi+18h], rax
0x180002c96  xor     ecx, ecx; pv
0x180002c98  call    cs:__imp_CoTaskMemFree
0x180002c9e  nop
0x180002c9f  mov     rcx, [rbp+pv]; pv
0x180002ca3  call    cs:__imp_CoTaskMemFree
0x180002ca9  nop
0x180002caa  mov     rcx, [rbp+arg_18]; pv
0x180002cae  call    cs:__imp_CoTaskMemFree
0x180002cb4  nop
0x180002cb5  lea     rcx, [rbp+var_20]
0x180002cb9  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180002cbe  mov     rbx, [rsp+50h+arg_0]
0x180002cc3  add     rsp, 50h
0x180002cc7  pop     rdi
0x180002cc8  pop     rsi
0x180002cc9  pop     rbp
0x180002cca  retn
```

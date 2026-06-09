# POOMIndexing::UnifiedStoreAggregateDataSource::EndTransaction(int)

- ea: `0x18001ad50`
- end: `0x18001af32`
- name: `?EndTransaction@UnifiedStoreAggregateDataSource@POOMIndexing@@UEAAJH@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct IUnknown *this, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000428c`
- `0x18000502c`
- `0x1800067c0`
- `0x18000c5b8`
- `0x18000d510`
- `0x18000e660`
- `0x18001aa3c`
- `0x18001ad50`
- `0x18001b3c0`
- `0x18001b400`
- `0x18001b830`
- `0x180022010`

## import_xrefs

- `PIMSTORE!GetAggregateCache` at `0x18001aee3`
- `PIMSTORE!GetAggregateCache` at `0x18001aee3`

## pseudocode

```c
__int64 __fastcall POOMIndexing::UnifiedStoreAggregateDataSource::EndTransaction(
        struct IUnknown *this,
        unsigned int a2)
{
  POOMIndexing::UnifiedStoreAggregateDataSource *v3; // rdi
  void *v4; // rax
  int v5; // ebx
  _QWORD *v6; // rsi
  int v7; // r15d
  struct IUnknown *v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  int AggregateCache; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  char v18; // [rsp+38h] [rbp-8h]
  struct IUnknown *v19; // [rsp+70h] [rbp+30h] BYREF
  int v20; // [rsp+78h] [rbp+38h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF

  v3 = (POOMIndexing::UnifiedStoreAggregateDataSource *)this;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v4 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v4, 0);
  }
  v5 = 0;
  v6 = (_QWORD *)((char *)v3 + 48);
  v7 = 0;
  v21 = 0;
  if ( *((_QWORD *)v3 + 6) )
  {
    v8 = (struct IUnknown *)*((_QWORD *)v3 + 4);
    v19 = 0;
    if ( !v8 || (ATL::AtlComQIPtrAssign(&v19, v8, &GUID_06f447be_544b_4f86_b05e_99eaa5a46fc0), (this = v19) == 0) )
    {
      Log_AssertionEvent_4(this, v8, 392);
      this = v19;
    }
    v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))this->lpVtbl[1].AddRef)(this, &v21);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
      LOBYTE(v7) = v5 >= 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  }
  if ( a2 )
  {
    v9 = *((_QWORD *)v3 + 4);
    v20 = *((_DWORD *)v3 + 15);
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64))(*(_QWORD *)v9 + 216LL))(v9, 0, &v20, 1);
    if ( v5 < 0 )
      goto LABEL_23;
    v17 = *(_QWORD *)lambda_7255da319444d40a48fc2fbaf62da9e9_::_lambda_7255da319444d40a48fc2fbaf62da9e9_(&v19, v3);
    v10 = POOMIndexing::UnifiedStoreAggregateDataSource::SaveGeneration(v3);
    if ( v10 < 0 )
      Log_HREvent_6((unsigned int)v10, 0, v11, 416);
    v12 = *((_QWORD *)v3 + 4);
    v18 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 224LL))(v12, a2, 0);
    tlx::_UndoSolo__lambda_7255da319444d40a48fc2fbaf62da9e9___::__UndoSolo__lambda_7255da319444d40a48fc2fbaf62da9e9___(&v17);
  }
  if ( v5 >= 0 && *v6 )
  {
    if ( a2 )
    {
      AggregateCache = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 88LL))(*v6);
      if ( AggregateCache >= 0 )
        goto LABEL_23;
      v15 = 432;
    }
    else
    {
      ATL::AtlComPtrAssign((struct IUnknown **)v3 + 6, 0);
      AggregateCache = GetAggregateCache(0, *((_QWORD *)v3 + 5));
      v5 = AggregateCache;
      if ( AggregateCache >= 0 )
        goto LABEL_23;
      v15 = 443;
    }
    Log_HREvent_6((unsigned int)AggregateCache, 0, v14, v15);
  }
LABEL_23:
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 56LL))(v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ad50  mov     [rsp-28h+arg_18], rbx
0x18001ad55  push    rbp
0x18001ad56  push    rsi
0x18001ad57  push    rdi
0x18001ad58  push    r14
0x18001ad5a  push    r15
0x18001ad5c  mov     rbp, rsp
0x18001ad5f  sub     rsp, 40h
0x18001ad63  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18001ad6a  mov     r14d, edx
0x18001ad6d  mov     rdi, rcx
0x18001ad70  jz      short loc_18001AD9B
0x18001ad72  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18001ad77  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001ad7b  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18001ad82  mov     [rsp+40h+var_18], r9
0x18001ad87  mov     rdx, rax; void *
0x18001ad8a  xor     r8d, r8d
0x18001ad8d  mov     [rsp+40h+var_20], 0
0x18001ad96  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18001ad9b  xor     ebx, ebx
0x18001ad9d  lea     rsi, [rdi+30h]
0x18001ada1  xor     r15d, r15d
0x18001ada4  mov     [rbp+arg_10], rbx
0x18001ada8  cmp     [rsi], rbx
0x18001adab  jz      short loc_18001AE19
0x18001adad  mov     rdx, [rdi+20h]; struct IUnknown *
0x18001adb1  mov     [rbp+arg_0], rbx
0x18001adb5  test    rdx, rdx
0x18001adb8  jz      short loc_18001ADD3
0x18001adba  lea     r8, _GUID_06f447be_544b_4f86_b05e_99eaa5a46fc0; struct _GUID *
0x18001adc1  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x18001adc5  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18001adca  mov     rcx, [rbp+arg_0]
0x18001adce  test    rcx, rcx
0x18001add1  jnz     short loc_18001ADE2
0x18001add3  mov     r8d, 188h
0x18001add9  call    Log_AssertionEvent_4
0x18001adde  mov     rcx, [rbp+arg_0]
0x18001ade2  mov     rax, [rcx]
0x18001ade5  lea     rdx, [rbp+arg_10]
0x18001ade9  mov     rax, [rax+20h]
0x18001aded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adf2  mov     ebx, eax
0x18001adf4  test    eax, eax
0x18001adf6  js      short loc_18001AE10
0x18001adf8  mov     rcx, [rbp+arg_10]
0x18001adfc  mov     rax, [rcx]
0x18001adff  mov     rax, [rax+30h]
0x18001ae03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae08  test    eax, eax
0x18001ae0a  mov     ebx, eax
0x18001ae0c  setns   r15b
0x18001ae10  lea     rcx, [rbp+arg_0]
0x18001ae14  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ae19  test    r14d, r14d
0x18001ae1c  jz      loc_18001AEA7
0x18001ae22  mov     eax, [rdi+3Ch]
0x18001ae25  lea     r8, [rbp+arg_8]
0x18001ae29  mov     rcx, [rdi+20h]
0x18001ae2d  mov     r9d, 1
0x18001ae33  mov     [rbp+arg_8], eax
0x18001ae36  xor     edx, edx
0x18001ae38  mov     rax, [rcx]
0x18001ae3b  mov     rax, [rax+0D8h]
0x18001ae42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae47  mov     ebx, eax
0x18001ae49  test    eax, eax
0x18001ae4b  js      loc_18001AEFE
0x18001ae51  mov     rdx, rdi
0x18001ae54  lea     rcx, [rbp+arg_0]
0x18001ae58  call    _lambda_7255da319444d40a48fc2fbaf62da9e9____lambda_7255da319444d40a48fc2fbaf62da9e9_
0x18001ae5d  mov     rcx, [rax]
0x18001ae60  mov     [rbp+var_10], rcx
0x18001ae64  mov     rcx, rdi; this
0x18001ae67  call    ?SaveGeneration@UnifiedStoreAggregateDataSource@POOMIndexing@@AEAAJXZ; POOMIndexing::UnifiedStoreAggregateDataSource::SaveGeneration(void)
0x18001ae6c  test    eax, eax
0x18001ae6e  jns     short loc_18001AE7F
0x18001ae70  xor     edx, edx
0x18001ae72  mov     r9d, 1A0h
0x18001ae78  mov     ecx, eax
0x18001ae7a  call    Log_HREvent_6
0x18001ae7f  mov     rcx, [rdi+20h]
0x18001ae83  xor     r8d, r8d
0x18001ae86  mov     edx, r14d
0x18001ae89  mov     [rbp+var_8], 0
0x18001ae8d  mov     rax, [rcx]
0x18001ae90  mov     rax, [rax+0E0h]
0x18001ae97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae9c  lea     rcx, [rbp+var_10]
0x18001aea0  mov     ebx, eax
0x18001aea2  call    tlx___UndoSolo__lambda_7255da319444d40a48fc2fbaf62da9e9_______UndoSolo__lambda_7255da319444d40a48fc2fbaf62da9e9___
0x18001aea7  test    ebx, ebx
0x18001aea9  js      short loc_18001AEFE
0x18001aeab  mov     rcx, [rsi]
0x18001aeae  test    rcx, rcx
0x18001aeb1  jz      short loc_18001AEFE
0x18001aeb3  test    r14d, r14d
0x18001aeb6  jz      short loc_18001AED0
0x18001aeb8  mov     rax, [rcx]
0x18001aebb  mov     rax, [rax+58h]
0x18001aebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aec4  test    eax, eax
0x18001aec6  jns     short loc_18001AEFE
0x18001aec8  mov     r9d, 1B0h
0x18001aece  jmp     short loc_18001AEF5
0x18001aed0  xor     edx, edx; struct IUnknown *
0x18001aed2  mov     rcx, rsi; struct IUnknown **
0x18001aed5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001aeda  mov     rdx, [rdi+28h]
0x18001aede  mov     r8, rsi
0x18001aee1  xor     ecx, ecx
0x18001aee3  call    cs:__imp_GetAggregateCache
0x18001aee9  mov     ebx, eax
0x18001aeeb  test    eax, eax
0x18001aeed  jns     short loc_18001AEFE
0x18001aeef  mov     r9d, 1BBh
0x18001aef5  xor     edx, edx
0x18001aef7  mov     ecx, eax
0x18001aef9  call    Log_HREvent_6
0x18001aefe  test    r15d, r15d
0x18001af01  jz      short loc_18001AF13
0x18001af03  mov     rcx, [rbp+arg_10]
0x18001af07  mov     rax, [rcx]
0x18001af0a  mov     rax, [rax+38h]
0x18001af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af13  lea     rcx, [rbp+arg_10]
0x18001af17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001af1c  mov     eax, ebx
0x18001af1e  mov     rbx, [rsp+40h+arg_18]
0x18001af26  add     rsp, 40h
0x18001af2a  pop     r15
0x18001af2c  pop     r14
0x18001af2e  pop     rdi
0x18001af2f  pop     rsi
0x18001af30  pop     rbp
0x18001af31  retn
```

# GetMetadataFunction::Evaluate(IXPathEvaluationContext *,tagVARIANT *)

- ea: `0x18000e368`
- end: `0x18000e58b`
- name: `?Evaluate@GetMetadataFunction@@AEAAJPEAUIXPathEvaluationContext@@PEAUtagVARIANT@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(GetMetadataFunction *__hidden this, struct IXPathEvaluationContext *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000e730`
- `0x18000e7d0`

## callees

- `0x1800021a4`
- `0x180007160`
- `0x180009650`
- `0x18000e368`
- `0x18000fd68`
- `0x180012ea8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall GetMetadataFunction::Evaluate(
        GetMetadataFunction *this,
        struct IXPathEvaluationContext *a2,
        struct tagVARIANT *a3)
{
  int v5; // edi
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, struct IXPathEvaluationContext *, __int64 *))(**((_QWORD **)this + 2) + 48LL))(
         *((_QWORD *)this + 2),
         a2,
         &v15);
  if ( v5 < 0 )
  {
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    return (unsigned int)v5;
  }
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IXPathEvaluationContext *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v16);
  v8 = v7;
  if ( v7 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    return v8;
  }
  try
  {
    v13 = 0;
    v9 = AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(
           v16,
           &v13);
    if ( v9 < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
      ScopedBSTR::Reset((ScopedBSTR *)&v15);
      return (unsigned int)v9;
    }
    if ( v13 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, struct tagVARIANT *))(**(_QWORD **)(v13 + 48) + 80LL))(
        *(_QWORD *)(v13 + 48),
        *(_QWORD *)(v13 + 40),
        v15,
        a3);
    }
    else
    {
      v14[0] = 0;
      v10 = AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(
              v16,
              v14);
      if ( v10 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
        ScopedBSTR::Reset((ScopedBSTR *)&v15);
        return (unsigned int)v10;
      }
      if ( !v14[0] )
      {
        v11 = AppHostNavigatorException::SetFunctionInvalidArgumentException(L"get-metadata");
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
        ScopedBSTR::Reset((ScopedBSTR *)&v15);
        return v11;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, struct tagVARIANT *))(**(_QWORD **)(v14[0] + 48LL) + 80LL))(
        *(_QWORD *)(v14[0] + 48LL),
        *(_QWORD *)(v14[0] + 40LL),
        v15,
        a3);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    result = 0;
  }
  catch ( long v12 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    return v12;
  }
  catch ( ... )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000e368  mov     r11, rsp
0x18000e36b  mov     [r11+10h], rbx
0x18000e36f  mov     [r11+18h], rsi
0x18000e373  push    rdi
0x18000e374  sub     rsp, 50h
0x18000e378  mov     rsi, r8
0x18000e37b  mov     rbx, rdx
0x18000e37e  mov     qword ptr [r11+8], 0
0x18000e386  mov     rcx, [rcx+10h]
0x18000e38a  mov     rax, [rcx]
0x18000e38d  lea     r8, [r11+8]
0x18000e391  mov     rax, [rax+30h]
0x18000e395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e39a  mov     edi, eax
0x18000e39c  test    eax, eax
0x18000e39e  jns     short loc_18000E3B1
0x18000e3a0  lea     rcx, [rsp+58h+arg_0]; this
0x18000e3a5  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e3aa  mov     eax, edi
0x18000e3ac  jmp     loc_18000E57B
0x18000e3b1  mov     [rsp+58h+arg_18], 0
0x18000e3ba  mov     rax, [rbx]
0x18000e3bd  lea     rdx, [rsp+58h+arg_18]
0x18000e3c2  mov     rcx, rbx
0x18000e3c5  mov     rax, [rax+18h]
0x18000e3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3ce  mov     ebx, eax
0x18000e3d0  test    eax, eax
0x18000e3d2  jns     short loc_18000E3F0
0x18000e3d4  lea     rcx, [rsp+58h+arg_18]
0x18000e3d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e3de  nop
0x18000e3df  lea     rcx, [rsp+58h+arg_0]; this
0x18000e3e4  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e3e9  mov     eax, ebx
0x18000e3eb  jmp     loc_18000E57B
0x18000e3f0  mov     [rsp+58h+var_20], 0
0x18000e3f9  lea     rdx, [rsp+58h+var_20]
0x18000e3fe  mov     rcx, [rsp+58h+arg_18]
0x18000e403  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostMergedConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostMergedConfigNavigator * *)
0x18000e408  mov     ebx, eax
0x18000e40a  test    eax, eax
0x18000e40c  jns     short loc_18000E435
0x18000e40e  lea     rcx, [rsp+58h+var_20]
0x18000e413  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e418  nop
0x18000e419  lea     rcx, [rsp+58h+arg_18]
0x18000e41e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e423  nop
0x18000e424  lea     rcx, [rsp+58h+arg_0]; this
0x18000e429  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e42e  mov     eax, ebx
0x18000e430  jmp     loc_18000E57B
0x18000e435  mov     rdx, [rsp+58h+var_20]
0x18000e43a  test    rdx, rdx
0x18000e43d  jz      short loc_18000E460
0x18000e43f  mov     rcx, [rdx+30h]
0x18000e443  mov     rax, [rcx]
0x18000e446  mov     r9, rsi
0x18000e449  mov     r8, [rsp+58h+arg_0]
0x18000e44e  mov     rdx, [rdx+28h]
0x18000e452  mov     rax, [rax+50h]
0x18000e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45b  jmp     loc_18000E522
0x18000e460  mov     [rsp+58h+var_18], 0
0x18000e469  lea     rdx, [rsp+58h+var_18]
0x18000e46e  mov     rcx, [rsp+58h+arg_18]
0x18000e473  call    ?TryCastAsDerivedType@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@SAJPEAUIXPathNavigator@@PEAPEAVAppHostRawConfigNavigator@@@Z; AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::TryCastAsDerivedType(IXPathNavigator *,AppHostRawConfigNavigator * *)
0x18000e478  mov     ebx, eax
0x18000e47a  test    eax, eax
0x18000e47c  jns     short loc_18000E4B0
0x18000e47e  lea     rcx, [rsp+58h+var_18]
0x18000e483  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e488  nop
0x18000e489  lea     rcx, [rsp+58h+var_20]
0x18000e48e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e493  nop
0x18000e494  lea     rcx, [rsp+58h+arg_18]
0x18000e499  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e49e  nop
0x18000e49f  lea     rcx, [rsp+58h+arg_0]; this
0x18000e4a4  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e4a9  mov     eax, ebx
0x18000e4ab  jmp     loc_18000E57B
0x18000e4b0  mov     rdx, [rsp+58h+var_18]
0x18000e4b5  test    rdx, rdx
0x18000e4b8  jnz     short loc_18000E4FA
0x18000e4ba  lea     rcx, aGetMetadata; "get-metadata"
0x18000e4c1  call    ?SetFunctionInvalidArgumentException@AppHostNavigatorException@@SAJPEBG@Z; AppHostNavigatorException::SetFunctionInvalidArgumentException(ushort const *)
0x18000e4c6  mov     ebx, eax
0x18000e4c8  lea     rcx, [rsp+58h+var_18]
0x18000e4cd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e4d2  nop
0x18000e4d3  lea     rcx, [rsp+58h+var_20]
0x18000e4d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e4dd  nop
0x18000e4de  lea     rcx, [rsp+58h+arg_18]
0x18000e4e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e4e8  nop
0x18000e4e9  lea     rcx, [rsp+58h+arg_0]; this
0x18000e4ee  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e4f3  mov     eax, ebx
0x18000e4f5  jmp     loc_18000E57B
0x18000e4fa  mov     rcx, [rdx+30h]
0x18000e4fe  mov     rax, [rcx]
0x18000e501  mov     r9, rsi
0x18000e504  mov     r8, [rsp+58h+arg_0]
0x18000e509  mov     rdx, [rdx+28h]
0x18000e50d  mov     rax, [rax+50h]
0x18000e511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e516  nop
0x18000e517  lea     rcx, [rsp+58h+var_18]
0x18000e51c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e521  nop
0x18000e522  lea     rcx, [rsp+58h+var_20]
0x18000e527  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e52c  nop
0x18000e52d  lea     rcx, [rsp+58h+arg_18]
0x18000e532  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e537  nop
0x18000e538  lea     rcx, [rsp+58h+arg_0]; this
0x18000e53d  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e542  xor     eax, eax
0x18000e544  jmp     short loc_18000E57B
0x18000e546  lea     rcx, [rsp+58h+arg_18]
0x18000e54b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e550  nop
0x18000e551  lea     rcx, [rsp+58h+arg_0]; this
0x18000e556  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e55b  mov     eax, [rsp+58h+var_28]
0x18000e55f  jmp     short loc_18000E57B
0x18000e561  lea     rcx, [rsp+58h+arg_18]
0x18000e566  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e56b  nop
0x18000e56c  lea     rcx, [rsp+58h+arg_0]; this
0x18000e571  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000e576  mov     eax, 8000FFFFh
0x18000e57b  mov     rbx, [rsp+58h+arg_8]
0x18000e580  mov     rsi, [rsp+58h+arg_10]
0x18000e585  add     rsp, 50h
0x18000e589  pop     rdi
0x18000e58a  retn
```

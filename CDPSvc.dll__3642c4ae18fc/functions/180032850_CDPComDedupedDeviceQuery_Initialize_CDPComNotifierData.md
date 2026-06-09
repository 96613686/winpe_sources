# CDPComDedupedDeviceQuery::Initialize(CDPComNotifierData *)

- ea: `0x180032850`
- end: `0x1800329e4`
- name: `?Initialize@CDPComDedupedDeviceQuery@@UEAAJPEAUCDPComNotifierData@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(CDPComDedupedDeviceQuery *this, struct CDPComNotifierData *, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003e60`
- `0x18000cb8c`
- `0x180017fc4`
- `0x18001b7b4`
- `0x18001bc28`
- `0x1800320a4`
- `0x180032374`
- `0x180032608`
- `0x180032850`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800329c8`
- `msvcp_win!_Mtx_unlock` at `0x1800329c8`
- `cdp!CDPCreateDedupedDeviceQueryInternal` at `0x180032936`
- `cdp!CDPCreateDedupedDeviceQueryInternal` at `0x180032936`

## pseudocode

```c
__int64 __fastcall CDPComDedupedDeviceQuery::Initialize(
        CDPComDedupedDeviceQuery *this,
        struct CDPComNotifierData *a2,
        __int64 a3,
        int a4)
{
  struct _Mtx_internal_imp_t *v6; // r15
  int v7; // edx
  int v8; // ecx
  int v9; // r9d
  unsigned int v10; // ebx
  int v11; // edx
  int v12; // ecx
  int v13; // r9d
  struct CDPComNotifierData *v14; // rsi
  int Internal; // r14d
  int v16; // eax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  struct CDPComNotifierData *v20; // [rsp+30h] [rbp-20h] BYREF
  std::_Ref_count_base *v21; // [rsp+38h] [rbp-18h]
  _QWORD v22[2]; // [rsp+40h] [rbp-10h] BYREF
  struct CDPComNotifierData *v23; // [rsp+88h] [rbp+38h] BYREF
  int v24; // [rsp+90h] [rbp+40h] BYREF

  v23 = a2;
  if ( !a2 )
  {
    LODWORD(v23) = -2147024809;
    v24 = 53;
    Log<long &,char const (&)[31],int>((_DWORD)this, 0, (unsigned int)&v23, a4, (__int64)&v24);
    return (unsigned int)v23;
  }
  v6 = (CDPComDedupedDeviceQuery *)((char *)this + 48);
  std::_Mutex_base::lock((CDPComDedupedDeviceQuery *)((char *)this + 48));
  if ( *((_QWORD *)this + 4) )
  {
    LODWORD(v23) = -2147221245;
    v24 = 56;
    Log<long &,char const (&)[31],int>(v8, v7, (unsigned int)&v23, v9, (__int64)&v24);
    v10 = (unsigned int)v23;
  }
  else
  {
    cdp::MakeSharedNoThrow<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback,CDPComNotifierData * &>(&v20, &v23);
    v14 = v20;
    if ( v20 )
    {
      v22[0] = 0;
      v22[1] = (char *)this + 32;
      Internal = CDPCreateDedupedDeviceQueryInternal(v22);
      cdp::detail::address_of<ICDPDedupedDeviceQuery>::~address_of<ICDPDedupedDeviceQuery>(v22);
      if ( Internal >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, struct CDPComNotifierData *))(**((_QWORD **)this + 4) + 24LL))(
                *((_QWORD *)this + 4),
                v14);
        if ( v16 >= 0 )
        {
          v23 = v14;
          v17 = (__int64 *)std::make_unique<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>,CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback *,0>(
                             &v24,
                             &v23);
          v18 = *v17;
          *v17 = 0;
          v19 = *((_QWORD *)this + 3);
          *((_QWORD *)this + 3) = v18;
          if ( v19 )
            std::default_delete<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>::operator()();
          std::unique_ptr<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>::~unique_ptr<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>(&v24);
          if ( v21 )
            std::_Ref_count_base::_Decref(v21);
          v10 = 0;
          goto LABEL_18;
        }
        LODWORD(v23) = v16;
        v24 = 62;
      }
      else
      {
        LODWORD(v23) = Internal;
        v24 = 61;
      }
    }
    else
    {
      LODWORD(v23) = -2147024882;
      v24 = 59;
    }
    Log<long &,char const (&)[31],int>(v12, v11, (unsigned int)&v23, v13, (__int64)&v24);
    v10 = (unsigned int)v23;
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
  }
LABEL_18:
  _Mtx_unlock(v6);
  return v10;
}

```

## disassembly

```asm
0x180032850  mov     [rsp-28h+arg_0], rbx
0x180032855  mov     [rsp-28h+arg_8], rdx
0x18003285a  push    rbp
0x18003285b  push    rsi
0x18003285c  push    rdi
0x18003285d  push    r14
0x18003285f  push    r15
0x180032861  mov     rbp, rsp
0x180032864  sub     rsp, 50h
0x180032868  mov     rbx, rcx
0x18003286b  test    rdx, rdx
0x18003286e  jnz     short loc_180032898
0x180032870  mov     dword ptr [rbp+arg_8], 80070057h
0x180032877  mov     [rbp+arg_10], 35h ; '5'
0x18003287e  lea     rax, [rbp+arg_10]
0x180032882  mov     [rsp+50h+var_30], rax
0x180032887  lea     r8, [rbp+arg_8]
0x18003288b  call    ??$Log@AEAJAEAY0BP@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BP@$$CBD$$QEAH@Z; Log<long &,char const (&)[31],int>(CDPLogLevel,char const *,long &,char const (&)[31],int &&)
0x180032890  mov     eax, dword ptr [rbp+arg_8]
0x180032893  jmp     loc_1800329D0
0x180032898  lea     r15, [rcx+30h]
0x18003289c  mov     rcx, r15; this
0x18003289f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800328a4  lea     rdi, [rbx+20h]
0x1800328a8  cmp     qword ptr [rdi], 0
0x1800328ac  jz      short loc_1800328D6
0x1800328ae  mov     dword ptr [rbp+arg_8], 80040103h
0x1800328b5  mov     [rbp+arg_10], 38h ; '8'
0x1800328bc  lea     rax, [rbp+arg_10]
0x1800328c0  mov     [rsp+50h+var_30], rax
0x1800328c5  lea     r8, [rbp+arg_8]
0x1800328c9  call    ??$Log@AEAJAEAY0BP@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BP@$$CBD$$QEAH@Z; Log<long &,char const (&)[31],int>(CDPLogLevel,char const *,long &,char const (&)[31],int &&)
0x1800328ce  mov     ebx, dword ptr [rbp+arg_8]
0x1800328d1  jmp     loc_1800329C5
0x1800328d6  lea     rdx, [rbp+arg_8]
0x1800328da  lea     rcx, [rbp+var_20]
0x1800328de  call    ??$MakeSharedNoThrow@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@AEAPEAUCDPComNotifierData@@@cdp@@YA?AV?$shared_ptr@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@std@@AEAPEAUCDPComNotifierData@@@Z; cdp::MakeSharedNoThrow<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback,CDPComNotifierData * &>(CDPComNotifierData * &)
0x1800328e3  mov     rsi, [rbp+var_20]
0x1800328e7  test    rsi, rsi
0x1800328ea  jnz     short loc_180032926
0x1800328ec  mov     dword ptr [rbp+arg_8], 8007000Eh
0x1800328f3  mov     [rbp+arg_10], 3Bh ; ';'
0x1800328fa  lea     rax, [rbp+arg_10]
0x1800328fe  mov     [rsp+50h+var_30], rax
0x180032903  lea     r8, [rbp+arg_8]
0x180032907  call    ??$Log@AEAJAEAY0BP@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BP@$$CBD$$QEAH@Z; Log<long &,char const (&)[31],int>(CDPLogLevel,char const *,long &,char const (&)[31],int &&)
0x18003290c  mov     ebx, dword ptr [rbp+arg_8]
0x18003290f  mov     rcx, [rbp+var_18]; this
0x180032913  test    rcx, rcx
0x180032916  jz      loc_1800329C5
0x18003291c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032921  jmp     loc_1800329C5
0x180032926  mov     [rbp+var_10], 0
0x18003292e  mov     [rbp+var_8], rdi
0x180032932  lea     rcx, [rbp+var_10]
0x180032936  call    cs:__imp_CDPCreateDedupedDeviceQueryInternal
0x18003293c  mov     r14d, eax
0x18003293f  lea     rcx, [rbp+var_10]
0x180032943  call    ??1?$address_of@VICDPDedupedDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDedupedDeviceQuery>::~address_of<ICDPDedupedDeviceQuery>(void)
0x180032948  test    r14d, r14d
0x18003294b  jns     short loc_18003295A
0x18003294d  mov     dword ptr [rbp+arg_8], r14d
0x180032951  mov     [rbp+arg_10], 3Dh ; '='
0x180032958  jmp     short loc_1800328FA
0x18003295a  mov     rcx, [rdi]
0x18003295d  mov     rax, [rcx]
0x180032960  mov     rdx, rsi
0x180032963  mov     rax, [rax+18h]
0x180032967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003296c  test    eax, eax
0x18003296e  jns     short loc_18003297F
0x180032970  mov     dword ptr [rbp+arg_8], eax
0x180032973  mov     [rbp+arg_10], 3Eh ; '>'
0x18003297a  jmp     loc_1800328FA
0x18003297f  mov     [rbp+arg_8], rsi
0x180032983  lea     rdx, [rbp+arg_8]
0x180032987  lea     rcx, [rbp+arg_10]
0x18003298b  call    ??$make_unique@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@PEAVDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@$0A@@std@@YA?AV?$unique_ptr@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@U?$default_delete@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@@std@@@0@$$QEAPEAVDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@Z; std::make_unique<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>,CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback *,0>(CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback * &&)
0x180032990  mov     rcx, [rax]
0x180032993  mov     qword ptr [rax], 0
0x18003299a  mov     rdx, [rbx+18h]
0x18003299e  mov     [rbx+18h], rcx
0x1800329a2  test    rdx, rdx
0x1800329a5  jz      short loc_1800329AC
0x1800329a7  call    ??R?$default_delete@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@@std@@QEBAXPEAV?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@@Z; std::default_delete<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>::operator()(cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback> *)
0x1800329ac  lea     rcx, [rbp+arg_10]
0x1800329b0  call    ??1?$unique_ptr@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@U?$default_delete@V?$weak_ref@VDedupedDeviceQueryCallback@CDPComDedupedDeviceQuery@@@cdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>::~unique_ptr<cdp::weak_ref<CDPComDedupedDeviceQuery::DedupedDeviceQueryCallback>>(void)
0x1800329b5  mov     rcx, [rbp+var_18]; this
0x1800329b9  test    rcx, rcx
0x1800329bc  jz      short loc_1800329C3
0x1800329be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800329c3  xor     ebx, ebx
0x1800329c5  mov     rcx, r15; _Mtx_t
0x1800329c8  call    cs:__imp__Mtx_unlock
0x1800329ce  mov     eax, ebx
0x1800329d0  mov     rbx, [rsp+50h+arg_0]
0x1800329d8  add     rsp, 50h
0x1800329dc  pop     r15
0x1800329de  pop     r14
0x1800329e0  pop     rdi
0x1800329e1  pop     rsi
0x1800329e2  pop     rbp
0x1800329e3  retn
```

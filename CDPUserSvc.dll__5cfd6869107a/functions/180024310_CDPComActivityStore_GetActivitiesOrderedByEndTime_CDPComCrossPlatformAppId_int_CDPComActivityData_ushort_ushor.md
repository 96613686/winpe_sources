# CDPComActivityStore::GetActivitiesOrderedByEndTime(CDPComCrossPlatformAppId *,int,CDPComActivityData * *,ushort,ushort *)

- ea: `0x180024310`
- end: `0x180024576`
- name: `?GetActivitiesOrderedByEndTime@CDPComActivityStore@@UEAAJPEAUCDPComCrossPlatformAppId@@HPEAPEAUCDPComActivityData@@GPEAG@Z`
- size: `614`
- prototype: `__int64 __fastcall(CDPComActivityStore *__hidden this, struct CDPComCrossPlatformAppId *, int, struct CDPComActivityData **, unsigned __int16, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800097d0`
- `0x18000b270`
- `0x1800112cc`
- `0x180011450`
- `0x180013908`
- `0x180014cdc`
- `0x180023b70`
- `0x180024310`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002438a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002438a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800244a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800244a0`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetActivitiesOrderedByEndTime(
        RTL_SRWLOCK *this,
        struct CDPComCrossPlatformAppId *a2,
        int a3,
        struct CDPComActivityData **a4,
        unsigned __int16 a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v11; // r15
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // r8
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  int v18; // eax
  int v19; // r14d
  bool v20; // r13
  unsigned __int16 v21; // bx
  int v22; // eax
  __int64 v23; // rdi
  __int64 v24; // r8
  void *v25; // rbx
  unsigned __int16 v26; // si
  int v27; // esi
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-59h]
  unsigned __int16 v30; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-29h] BYREF
  RTL_SRWLOCK *v33; // [rsp+60h] [rbp-19h] BYREF
  std::_Ref_count_base *v34[2]; // [rsp+68h] [rbp-11h] BYREF
  unsigned int v35; // [rsp+E8h] [rbp+6Fh] BYREF

  if ( !a4 )
  {
    LODWORD(pv) = 867;
LABEL_3:
    v35 = -2147467261;
    Log<long &,char const (&)[27],int>((__int64)this, (__int64)a2, &v35, (__int64)a4, &pv);
    return v35;
  }
  v11 = a6;
  if ( !a6 )
  {
    LODWORD(pv) = 868;
    goto LABEL_3;
  }
  *a6 = 0;
  *a4 = 0;
  v30 = 0;
  v12 = this + 4;
  AcquireSRWLockShared(this + 4);
  v33 = v12;
  *(_OWORD *)v34 = 0;
  if ( !a2 )
    goto LABEL_11;
  v32[0] = 0;
  v32[1] = v34;
  v14 = CDPCrossPlatformAppIdFromComCrossPlatformAppId(a2, v32);
  cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(v32);
  v18 = 0;
  if ( v14 != -2147024809 )
    v18 = v14;
  if ( v18 < 0 )
  {
    v35 = v18;
    LODWORD(pv) = 887;
    Log<long &,char const (&)[27],int>(v16, v15, &v35, v17, &pv);
    v19 = v35;
  }
  else
  {
LABEL_11:
    v20 = a3 != 0;
    v21 = a5;
    LOBYTE(v13) = a3 != 0;
    v22 = (*(__int64 (__fastcall **)(PVOID, std::_Ref_count_base *, __int64, _QWORD, unsigned __int16, unsigned __int16 *))(*(_QWORD *)this[2].Ptr + 96LL))(
            this[2].Ptr,
            v34[0],
            v13,
            0,
            a5,
            &v30);
    v19 = v22;
    if ( v30 < v21 )
      v21 = v30;
    if ( v22 >= 0 && v21 )
    {
      std::make_unique<ICDPActivity * [0],0>(v32, v21);
      LOWORD(v35) = 0;
      LOWORD(v29) = v21;
      v23 = v32[0];
      LOBYTE(v24) = v20;
      v19 = (*(__int64 (__fastcall **)(PVOID, std::_Ref_count_base *, __int64, _QWORD, int, unsigned int *))(*(_QWORD *)this[2].Ptr + 96LL))(
              this[2].Ptr,
              v34[0],
              v24,
              v32[0],
              v29,
              &v35);
      if ( v19 >= 0 )
      {
        v25 = CoTaskMemAlloc(232LL * (unsigned __int16)v35);
        pv = v25;
        if ( v25 )
        {
          v26 = 0;
          if ( (_WORD)v35 )
          {
            do
            {
              v19 = CDPActivityToComActivityData(*(__int64 **)(v23 + 8LL * v26), (__int64)v25 + 232 * v26);
              if ( v19 < 0 )
                break;
              ++v26;
            }
            while ( v26 < (unsigned __int16)v35 );
            v11 = a6;
          }
          pv = 0;
          *a4 = (struct CDPComActivityData *)v25;
          *v11 = v26;
        }
        else
        {
          v19 = -2147024882;
        }
        v27 = 0;
        if ( (_WORD)v35 )
        {
          do
          {
            v28 = *(_QWORD *)(v23 + 8LL * v27);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            ++v27;
          }
          while ( v27 < (unsigned __int16)v35 );
          if ( pv )
            CoTaskMemFree(pv);
        }
      }
      std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(v32);
    }
  }
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v33);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180024310  push    rbp
0x180024312  push    rbx
0x180024313  push    rsi
0x180024314  push    rdi
0x180024315  push    r12
0x180024317  push    r13
0x180024319  push    r14
0x18002431b  push    r15
0x18002431d  lea     rbp, [rsp-0Fh]
0x180024322  sub     rsp, 88h
0x180024329  mov     r12, r9
0x18002432c  mov     r14d, r8d
0x18002432f  mov     rdi, rdx
0x180024332  mov     rsi, rcx
0x180024335  xor     r13d, r13d
0x180024338  test    r9, r9
0x18002433b  jnz     short loc_180024365
0x18002433d  mov     dword ptr [rbp+47h+pv], 363h
0x180024344  mov     [rbp+47h+arg_18], 80004003h
0x18002434b  lea     rax, [rbp+47h+pv]
0x18002434f  mov     [rsp+0C0h+var_A0], rax
0x180024354  lea     r8, [rbp+47h+arg_18]
0x180024358  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18002435d  mov     eax, [rbp+47h+arg_18]
0x180024360  jmp     loc_180024562
0x180024365  mov     r15, [rbp+47h+arg_28]
0x180024369  test    r15, r15
0x18002436c  jnz     short loc_180024377
0x18002436e  mov     dword ptr [rbp+47h+pv], 364h
0x180024375  jmp     short loc_180024344
0x180024377  mov     [r15], r13w
0x18002437b  mov     [r9], r13
0x18002437e  mov     [rbp+47h+var_80], r13w
0x180024383  lea     rbx, [rcx+20h]
0x180024387  mov     rcx, rbx; SRWLock
0x18002438a  call    cs:__imp_AcquireSRWLockShared
0x180024390  mov     [rbp+47h+var_60], rbx
0x180024394  xorps   xmm0, xmm0
0x180024397  movdqu  xmmword ptr [rbp+47h+var_58], xmm0
0x18002439c  test    rdi, rdi
0x18002439f  jz      short loc_1800243F9
0x1800243a1  mov     [rbp+47h+var_70], r13
0x1800243a5  lea     rax, [rbp+47h+var_58]
0x1800243a9  mov     [rbp+47h+var_68], rax
0x1800243ad  lea     rdx, [rbp+47h+var_70]
0x1800243b1  mov     rcx, rdi
0x1800243b4  call    CDPCrossPlatformAppIdFromComCrossPlatformAppId
0x1800243b9  mov     ebx, eax
0x1800243bb  lea     rcx, [rbp+47h+var_70]
0x1800243bf  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x1800243c4  mov     eax, r13d
0x1800243c7  cmp     ebx, 80070057h
0x1800243cd  cmovnz  eax, ebx
0x1800243d0  test    eax, eax
0x1800243d2  jns     short loc_1800243F9
0x1800243d4  mov     [rbp+47h+arg_18], eax
0x1800243d7  mov     dword ptr [rbp+47h+pv], 377h
0x1800243de  lea     rax, [rbp+47h+pv]
0x1800243e2  mov     [rsp+0C0h+var_A0], rax
0x1800243e7  lea     r8, [rbp+47h+arg_18]
0x1800243eb  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800243f0  mov     r14d, [rbp+47h+arg_18]
0x1800243f4  jmp     loc_180024548
0x1800243f9  mov     rcx, [rsi+10h]
0x1800243fd  test    r14d, r14d
0x180024400  setnz   r13b
0x180024404  mov     rax, [rcx]
0x180024407  lea     rdx, [rbp+47h+var_80]
0x18002440b  mov     [rsp+0C0h+var_98], rdx
0x180024410  movzx   ebx, [rbp+47h+arg_20]
0x180024414  mov     word ptr [rsp+0C0h+var_A0], bx
0x180024419  xor     r9d, r9d
0x18002441c  mov     r8b, r13b
0x18002441f  mov     rdx, [rbp+47h+var_58]
0x180024423  mov     rax, [rax+60h]
0x180024427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002442c  mov     r14d, eax
0x18002442f  cmp     [rbp+47h+var_80], bx
0x180024433  cmovb   bx, [rbp+47h+var_80]
0x180024438  xor     edi, edi
0x18002443a  test    eax, eax
0x18002443c  js      loc_180024548
0x180024442  test    bx, bx
0x180024445  jz      loc_180024548
0x18002444b  movzx   edx, bx
0x18002444e  lea     rcx, [rbp+47h+var_70]
0x180024452  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x180024457  mov     word ptr [rbp+47h+arg_18], di
0x18002445b  mov     rcx, [rsi+10h]
0x18002445f  mov     rax, [rcx]
0x180024462  lea     rdx, [rbp+47h+arg_18]
0x180024466  mov     [rsp+0C0h+var_98], rdx
0x18002446b  mov     word ptr [rsp+0C0h+var_A0], bx
0x180024470  mov     rdi, [rbp+47h+var_70]
0x180024474  mov     r9, rdi
0x180024477  mov     r8b, r13b
0x18002447a  mov     rdx, [rbp+47h+var_58]
0x18002447e  mov     rax, [rax+60h]
0x180024482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024487  mov     r14d, eax
0x18002448a  xor     r13d, r13d
0x18002448d  test    eax, eax
0x18002448f  js      loc_18002453F
0x180024495  movzx   eax, word ptr [rbp+47h+arg_18]
0x180024499  imul    rcx, rax, 0E8h; cb
0x1800244a0  call    cs:__imp_CoTaskMemAlloc
0x1800244a6  mov     rbx, rax
0x1800244a9  mov     [rbp+47h+pv], rax
0x1800244ad  test    rax, rax
0x1800244b0  jnz     short loc_1800244BA
0x1800244b2  mov     r14d, 8007000Eh
0x1800244b8  jmp     short loc_180024501
0x1800244ba  mov     esi, r13d
0x1800244bd  cmp     r13w, word ptr [rbp+47h+arg_18]
0x1800244c2  jnb     short loc_1800244F5
0x1800244c4  mov     r15d, 1
0x1800244ca  movzx   ecx, si
0x1800244cd  imul    rdx, rcx, 0E8h
0x1800244d4  add     rdx, rbx
0x1800244d7  mov     rcx, [rdi+rcx*8]
0x1800244db  call    CDPActivityToComActivityData
0x1800244e0  mov     r14d, eax
0x1800244e3  test    eax, eax
0x1800244e5  js      short loc_1800244F1
0x1800244e7  add     si, r15w
0x1800244eb  cmp     si, word ptr [rbp+47h+arg_18]
0x1800244ef  jb      short loc_1800244CA
0x1800244f1  mov     r15, [rbp+47h+arg_28]
0x1800244f5  mov     [rbp+47h+pv], r13
0x1800244f9  mov     [r12], rbx
0x1800244fd  mov     [r15], si
0x180024501  mov     esi, r13d
0x180024504  cmp     r13w, word ptr [rbp+47h+arg_18]
0x180024509  jnb     short loc_18002453F
0x18002450b  movsxd  rax, esi
0x18002450e  mov     rcx, [rdi+rax*8]
0x180024512  test    rcx, rcx
0x180024515  jz      short loc_180024523
0x180024517  mov     rax, [rcx]
0x18002451a  mov     rax, [rax+10h]
0x18002451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024523  inc     esi
0x180024525  movzx   eax, word ptr [rbp+47h+arg_18]
0x180024529  cmp     esi, eax
0x18002452b  jl      short loc_18002450B
0x18002452d  mov     rbx, [rbp+47h+pv]
0x180024531  test    rbx, rbx
0x180024534  jz      short loc_18002453F
0x180024536  mov     rcx, rbx; pv
0x180024539  call    cs:__imp_CoTaskMemFree
0x18002453f  lea     rcx, [rbp+47h+var_70]
0x180024543  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x180024548  mov     rcx, [rbp+47h+var_58+8]; this
0x18002454c  test    rcx, rcx
0x18002454f  jz      short loc_180024556
0x180024551  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180024556  lea     rcx, [rbp+47h+var_60]
0x18002455a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18002455f  mov     eax, r14d
0x180024562  add     rsp, 88h
0x180024569  pop     r15
0x18002456b  pop     r14
0x18002456d  pop     r13
0x18002456f  pop     r12
0x180024571  pop     rdi
0x180024572  pop     rsi
0x180024573  pop     rbx
0x180024574  pop     rbp
0x180024575  retn
```

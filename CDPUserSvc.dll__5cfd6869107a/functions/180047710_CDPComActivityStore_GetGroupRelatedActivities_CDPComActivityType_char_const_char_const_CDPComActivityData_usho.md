# CDPComActivityStore::GetGroupRelatedActivities(CDPComActivityType,char const *,char const *,CDPComActivityData * *,ushort *)

- ea: `0x180047710`
- end: `0x180047903`
- name: `?GetGroupRelatedActivities@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEBD1PEAPEAUCDPComActivityData@@PEAG@Z`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800112cc`
- `0x180013908`
- `0x180014cdc`
- `0x180023b70`
- `0x180047710`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004777d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004777d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800478d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800478d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047840`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetGroupRelatedActivities(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned __int16 *a6)
{
  unsigned int v8; // r14d
  _QWORD *v10; // r12
  unsigned __int16 *v12; // r15
  __int64 v13; // rbx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rdi
  void *v17; // rbx
  unsigned __int16 v18; // si
  int v19; // esi
  __int64 v20; // rcx
  int v21; // [rsp+28h] [rbp-40h]
  unsigned __int16 v22; // [rsp+40h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF
  __int64 v24; // [rsp+50h] [rbp-18h] BYREF
  __int64 v25; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+50h]

  v26 = a2;
  v8 = a2;
  v10 = a5;
  if ( !a5 )
  {
    LODWORD(pv) = 715;
LABEL_3:
    LODWORD(a5) = -2147467261;
    Log<long &,char const (&)[27],int>(a1, a2, &a5, a4, &pv);
    return (unsigned int)a5;
  }
  v12 = a6;
  if ( !a6 )
  {
    LODWORD(pv) = 716;
    goto LABEL_3;
  }
  v13 = a1 + 32;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  v25 = v13;
  *v12 = 0;
  *v10 = 0;
  v22 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, _WORD, unsigned __int16 *))(**(_QWORD **)(a1 + 16) + 80LL))(
          *(_QWORD *)(a1 + 16),
          v8,
          a3,
          a4,
          0,
          0,
          &v22);
  if ( v14 >= 0 && v22 )
  {
    std::make_unique<ICDPActivity * [0],0>(&v24, v22);
    LOWORD(a5) = 0;
    v15 = *(_QWORD *)(a1 + 16);
    LOWORD(v21) = v22;
    v16 = v24;
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, int, _QWORD **))(*(_QWORD *)v15 + 80LL))(
            v15,
            v26,
            a3,
            a4,
            v24,
            v21,
            &a5);
    if ( v14 >= 0 && v22 )
    {
      v17 = CoTaskMemAlloc(232LL * (unsigned __int16)a5);
      pv = v17;
      if ( v17 )
      {
        v18 = 0;
        if ( (_WORD)a5 )
        {
          do
          {
            v14 = CDPActivityToComActivityData(*(__int64 **)(v16 + 8LL * v18), (__int64)v17 + 232 * v18);
            if ( v14 < 0 )
              break;
            ++v18;
          }
          while ( v18 < (unsigned __int16)a5 );
          v12 = a6;
        }
        pv = 0;
        *v10 = v17;
        *v12 = v18;
      }
      else
      {
        v14 = -2147024882;
      }
      v19 = 0;
      if ( (_WORD)a5 )
      {
        do
        {
          v20 = *(_QWORD *)(v16 + 8LL * v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          ++v19;
        }
        while ( v19 < (unsigned __int16)a5 );
        if ( pv )
          CoTaskMemFree(pv);
      }
    }
    std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(&v24);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180047710  mov     [rsp-40h+arg_8], edx
0x180047714  push    rbp
0x180047715  push    rbx
0x180047716  push    rsi
0x180047717  push    rdi
0x180047718  push    r12
0x18004771a  push    r13
0x18004771c  push    r14
0x18004771e  push    r15
0x180047720  mov     rbp, rsp
0x180047723  sub     rsp, 68h
0x180047727  mov     rsi, r9
0x18004772a  mov     r13, r8
0x18004772d  mov     r14d, edx
0x180047730  mov     rdi, rcx
0x180047733  mov     r12, [rbp+arg_20]
0x180047737  test    r12, r12
0x18004773a  jnz     short loc_180047764
0x18004773c  mov     dword ptr [rbp+pv], 2CBh
0x180047743  mov     dword ptr [rbp+arg_20], 80004003h
0x18004774a  lea     rax, [rbp+pv]
0x18004774e  mov     [rsp+68h+var_48], rax
0x180047753  lea     r8, [rbp+arg_20]
0x180047757  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18004775c  mov     eax, dword ptr [rbp+arg_20]
0x18004775f  jmp     loc_1800478F2
0x180047764  mov     r15, [rbp+arg_28]
0x180047768  test    r15, r15
0x18004776b  jnz     short loc_180047776
0x18004776d  mov     dword ptr [rbp+pv], 2CCh
0x180047774  jmp     short loc_180047743
0x180047776  lea     rbx, [rcx+20h]
0x18004777a  mov     rcx, rbx; SRWLock
0x18004777d  call    cs:__imp_AcquireSRWLockShared
0x180047783  mov     [rbp+var_10], rbx
0x180047787  xor     ebx, ebx
0x180047789  mov     [r15], bx
0x18004778d  mov     [r12], rbx
0x180047791  mov     [rbp+var_28], bx
0x180047795  mov     rcx, [rdi+10h]
0x180047799  mov     rax, [rcx]
0x18004779c  lea     r8, [rbp+var_28]
0x1800477a0  mov     [rsp+68h+var_38], r8
0x1800477a5  mov     [rsp+68h+var_40], bx
0x1800477aa  mov     [rsp+68h+var_48], rbx
0x1800477af  mov     r9, rsi
0x1800477b2  mov     r8, r13
0x1800477b5  mov     edx, r14d
0x1800477b8  mov     rax, [rax+50h]
0x1800477bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477c1  mov     r14d, eax
0x1800477c4  test    eax, eax
0x1800477c6  js      loc_1800478E6
0x1800477cc  movzx   eax, [rbp+var_28]
0x1800477d0  test    ax, ax
0x1800477d3  jz      loc_1800478E6
0x1800477d9  mov     edx, eax
0x1800477db  lea     rcx, [rbp+var_18]
0x1800477df  call    ??$make_unique@$$BY0A@PEAVICDPActivity@@$0A@@std@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@0@_K@Z; std::make_unique<ICDPActivity * [0],0>(unsigned __int64)
0x1800477e4  mov     word ptr [rbp+arg_20], bx
0x1800477e8  mov     rcx, [rdi+10h]
0x1800477ec  movzx   edx, [rbp+var_28]
0x1800477f0  mov     rax, [rcx]
0x1800477f3  lea     r8, [rbp+arg_20]
0x1800477f7  mov     [rsp+68h+var_38], r8
0x1800477fc  mov     [rsp+68h+var_40], dx
0x180047801  mov     rdi, [rbp+var_18]
0x180047805  mov     [rsp+68h+var_48], rdi
0x18004780a  mov     r9, rsi
0x18004780d  mov     r8, r13
0x180047810  mov     edx, [rbp+arg_8]
0x180047813  mov     rax, [rax+50h]
0x180047817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004781c  mov     r14d, eax
0x18004781f  xor     r13d, r13d
0x180047822  test    eax, eax
0x180047824  js      loc_1800478DD
0x18004782a  cmp     [rbp+var_28], r13w
0x18004782f  jbe     loc_1800478DD
0x180047835  movzx   eax, word ptr [rbp+arg_20]
0x180047839  imul    rcx, rax, 0E8h; cb
0x180047840  call    cs:__imp_CoTaskMemAlloc
0x180047846  mov     rbx, rax
0x180047849  mov     [rbp+pv], rax
0x18004784d  test    rax, rax
0x180047850  jz      short loc_180047899
0x180047852  mov     esi, r13d
0x180047855  cmp     r13w, word ptr [rbp+arg_20]
0x18004785a  jnb     short loc_18004788B
0x18004785c  lea     r15d, [r13+1]
0x180047860  movzx   ecx, si
0x180047863  imul    rdx, rcx, 0E8h
0x18004786a  add     rdx, rbx
0x18004786d  mov     rcx, [rdi+rcx*8]
0x180047871  call    CDPActivityToComActivityData
0x180047876  mov     r14d, eax
0x180047879  test    eax, eax
0x18004787b  js      short loc_180047887
0x18004787d  add     si, r15w
0x180047881  cmp     si, word ptr [rbp+arg_20]
0x180047885  jb      short loc_180047860
0x180047887  mov     r15, [rbp+arg_28]
0x18004788b  mov     [rbp+pv], r13
0x18004788f  mov     [r12], rbx
0x180047893  mov     [r15], si
0x180047897  jmp     short loc_18004789F
0x180047899  mov     r14d, 8007000Eh
0x18004789f  mov     esi, r13d
0x1800478a2  cmp     r13w, word ptr [rbp+arg_20]
0x1800478a7  jnb     short loc_1800478DD
0x1800478a9  movsxd  rax, esi
0x1800478ac  mov     rcx, [rdi+rax*8]
0x1800478b0  test    rcx, rcx
0x1800478b3  jz      short loc_1800478C1
0x1800478b5  mov     rax, [rcx]
0x1800478b8  mov     rax, [rax+10h]
0x1800478bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478c1  inc     esi
0x1800478c3  movzx   eax, word ptr [rbp+arg_20]
0x1800478c7  cmp     esi, eax
0x1800478c9  jl      short loc_1800478A9
0x1800478cb  mov     rbx, [rbp+pv]
0x1800478cf  test    rbx, rbx
0x1800478d2  jz      short loc_1800478DD
0x1800478d4  mov     rcx, rbx; pv
0x1800478d7  call    cs:__imp_CoTaskMemFree
0x1800478dd  lea     rcx, [rbp+var_18]
0x1800478e1  call    ??1?$unique_ptr@$$BY0A@PEAVICDPActivity@@U?$default_delete@$$BY0A@PEAVICDPActivity@@@std@@@std@@QEAA@XZ; std::unique_ptr<ICDPActivity * [0]>::~unique_ptr<ICDPActivity * [0]>(void)
0x1800478e6  lea     rcx, [rbp+var_10]
0x1800478ea  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800478ef  mov     eax, r14d
0x1800478f2  add     rsp, 68h
0x1800478f6  pop     r15
0x1800478f8  pop     r14
0x1800478fa  pop     r13
0x1800478fc  pop     r12
0x1800478fe  pop     rdi
0x1800478ff  pop     rsi
0x180047900  pop     rbx
0x180047901  pop     rbp
0x180047902  retn
```

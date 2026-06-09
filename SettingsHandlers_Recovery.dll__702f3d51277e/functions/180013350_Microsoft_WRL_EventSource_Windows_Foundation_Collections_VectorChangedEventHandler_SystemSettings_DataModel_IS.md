# Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *> *,void *,EventRegistrationToken *)

- ea: `0x180013350`
- end: `0x180013568`
- name: `?AddInternal@?$EventSource@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `536`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022490`
- `0x180022510`
- `0x1800225b0`

## callees

- `0x18000fca4`
- `0x180013350`
- `0x18001dd30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013383`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800134fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013383`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800134fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800133ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013530`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001353e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800133ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013530`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001353e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v5; // r15
  RTL_SRWLOCK *v8; // rbp
  __int64 v9; // rcx
  int v10; // esi
  _QWORD *Ptr; // rax
  _QWORD *v13; // rsi
  _QWORD *v14; // rcx
  _QWORD *i; // r15
  bool v16; // zf
  __int64 v17; // r14
  __int64 *v18; // r12
  __int64 v19; // rcx
  __int64 *v20; // r14
  __int64 v21; // rcx
  PVOID v22; // rbx
  PVOID v23; // rcx
  char v24; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v25; // [rsp+70h] [rbp+8h] BYREF
  __int64 v26; // [rsp+80h] [rbp+18h]
  __int64 v27; // [rsp+88h] [rbp+20h] BYREF

  v26 = a3;
  v5 = a3;
  *a4 = 0;
  v8 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v25 = 0;
  if ( a1->Ptr )
    v9 = ((__int64)(*((_QWORD *)a1->Ptr + 3) - *((_QWORD *)a1->Ptr + 2)) >> 3) + 1;
  else
    v9 = 1;
  v27 = v9;
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v25,
          &v27);
  if ( v10 >= 0 )
  {
    Ptr = a1->Ptr;
    v13 = v25;
    if ( a1->Ptr )
    {
      v14 = (_QWORD *)Ptr[4];
      for ( i = (_QWORD *)Ptr[2]; ; ++i )
      {
        v16 = i == (_QWORD *)Ptr[3];
        v25 = v14;
        if ( v16 )
          break;
        v27 = *v14;
        v17 = *i;
        v18 = (__int64 *)v13[3];
        if ( *v18 != *i )
        {
          if ( v17 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*i);
          v19 = *v18;
          *v18 = v17;
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        *(_QWORD *)(v13[4] + 8 * ((__int64)(v13[3] - v13[2]) >> 3)) = v27;
        v13[3] += 8LL;
        v14 = v25 + 1;
        Ptr = a1->Ptr;
      }
      v5 = v26;
    }
    *a4 = a2;
    v20 = (__int64 *)v13[3];
    if ( *v20 != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
      v21 = *v20;
      *v20 = a2;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    *(_QWORD *)(v13[4] + 8 * ((__int64)(v13[3] - v13[2]) >> 3)) = v5;
    v13[3] += 8LL;
    AcquireSRWLockExclusive(a1 + 1);
    v22 = 0;
    if ( &v24 != (char *)a1 )
    {
      v22 = a1->Ptr;
      a1->Ptr = 0;
    }
    v23 = a1->Ptr;
    a1->Ptr = v13;
    if ( v23 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v23);
    if ( a1 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(a1 + 1);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    if ( v22 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v22);
    return 0;
  }
  else
  {
    if ( v25 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v25);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180013350  mov     [rsp+arg_8], rbx
0x180013355  mov     [rsp+arg_10], r8
0x18001335a  push    rbp
0x18001335b  push    rsi
0x18001335c  push    rdi
0x18001335d  push    r12
0x18001335f  push    r13
0x180013361  push    r14
0x180013363  push    r15
0x180013365  sub     rsp, 30h
0x180013369  mov     r13, r9
0x18001336c  mov     r15, r8
0x18001336f  mov     rbx, rdx
0x180013372  mov     rdi, rcx
0x180013375  mov     qword ptr [r9], 0
0x18001337c  lea     rbp, [rcx+10h]
0x180013380  mov     rcx, rbp; SRWLock
0x180013383  call    cs:__imp_AcquireSRWLockExclusive
0x180013389  mov     [rsp+68h+arg_0], 0
0x180013392  mov     rcx, [rdi]
0x180013395  test    rcx, rcx
0x180013398  jnz     short loc_1800133A1
0x18001339a  mov     ecx, 1
0x18001339f  jmp     short loc_1800133B5
0x1800133a1  mov     rax, [rcx+18h]
0x1800133a5  sub     rax, [rcx+10h]
0x1800133a9  sar     rax, 3
0x1800133ad  mov     ecx, 1
0x1800133b2  add     rcx, rax
0x1800133b5  mov     [rsp+68h+arg_18], rcx
0x1800133bd  lea     rdx, [rsp+68h+arg_18]
0x1800133c5  lea     rcx, [rsp+68h+arg_0]
0x1800133ca  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x1800133cf  mov     esi, eax
0x1800133d1  test    eax, eax
0x1800133d3  jns     short loc_1800133F9
0x1800133d5  mov     rcx, [rsp+68h+arg_0]
0x1800133da  test    rcx, rcx
0x1800133dd  jz      short loc_1800133E4
0x1800133df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800133e4  test    rbp, rbp
0x1800133e7  jz      short loc_1800133F2
0x1800133e9  mov     rcx, rbp; SRWLock
0x1800133ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800133f2  mov     eax, esi
0x1800133f4  jmp     loc_180013553
0x1800133f9  mov     rax, [rdi]
0x1800133fc  mov     rsi, [rsp+68h+arg_0]
0x180013401  test    rax, rax
0x180013404  jz      loc_1800134A2
0x18001340a  mov     rcx, [rax+20h]
0x18001340e  mov     r15, [rax+10h]
0x180013412  cmp     r15, [rax+18h]
0x180013416  mov     [rsp+68h+arg_0], rcx
0x18001341b  jz      short loc_18001349A
0x18001341d  mov     rax, [rcx]
0x180013420  mov     [rsp+68h+arg_18], rax
0x180013428  mov     r14, [r15]
0x18001342b  mov     r12, [rsi+18h]
0x18001342f  cmp     [r12], r14
0x180013433  jz      short loc_180013464
0x180013435  test    r14, r14
0x180013438  jz      short loc_18001344A
0x18001343a  mov     rax, [r14]
0x18001343d  mov     rcx, r14
0x180013440  mov     rax, [rax+8]
0x180013444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013449  nop
0x18001344a  mov     rcx, [r12]
0x18001344e  mov     [r12], r14
0x180013452  test    rcx, rcx
0x180013455  jz      short loc_180013464
0x180013457  mov     rax, [rcx]
0x18001345a  mov     rax, [rax+10h]
0x18001345e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013463  nop
0x180013464  mov     rcx, [rsi+18h]
0x180013468  sub     rcx, [rsi+10h]
0x18001346c  sar     rcx, 3
0x180013470  mov     rax, [rsi+20h]
0x180013474  mov     rdx, [rsp+68h+arg_18]
0x18001347c  mov     [rax+rcx*8], rdx
0x180013480  add     qword ptr [rsi+18h], 8
0x180013485  mov     rcx, [rsp+68h+arg_0]
0x18001348a  add     rcx, 8
0x18001348e  add     r15, 8
0x180013492  mov     rax, [rdi]
0x180013495  jmp     loc_180013412
0x18001349a  mov     r15, [rsp+68h+arg_10]
0x1800134a2  mov     [r13+0], rbx
0x1800134a6  mov     r14, [rsi+18h]
0x1800134aa  cmp     [r14], rbx
0x1800134ad  jz      short loc_1800134DC
0x1800134af  test    rbx, rbx
0x1800134b2  jz      short loc_1800134C4
0x1800134b4  mov     rax, [rbx]
0x1800134b7  mov     rcx, rbx
0x1800134ba  mov     rax, [rax+8]
0x1800134be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c3  nop
0x1800134c4  mov     rcx, [r14]
0x1800134c7  mov     [r14], rbx
0x1800134ca  test    rcx, rcx
0x1800134cd  jz      short loc_1800134DC
0x1800134cf  mov     rax, [rcx]
0x1800134d2  mov     rax, [rax+10h]
0x1800134d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134db  nop
0x1800134dc  mov     rcx, [rsi+18h]
0x1800134e0  sub     rcx, [rsi+10h]
0x1800134e4  sar     rcx, 3
0x1800134e8  mov     rax, [rsi+20h]
0x1800134ec  mov     [rax+rcx*8], r15
0x1800134f0  add     qword ptr [rsi+18h], 8
0x1800134f5  lea     r14, [rdi+8]
0x1800134f9  mov     rcx, r14; SRWLock
0x1800134fc  call    cs:__imp_AcquireSRWLockExclusive
0x180013502  xor     ebx, ebx
0x180013504  lea     rax, [rsp+68h+var_48]
0x180013509  cmp     rax, rdi
0x18001350c  jz      short loc_180013518
0x18001350e  mov     rbx, [rdi]
0x180013511  mov     qword ptr [rdi], 0
0x180013518  mov     rcx, [rdi]
0x18001351b  mov     [rdi], rsi
0x18001351e  test    rcx, rcx
0x180013521  jz      short loc_180013528
0x180013523  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180013528  test    r14, r14
0x18001352b  jz      short loc_180013536
0x18001352d  mov     rcx, r14; SRWLock
0x180013530  call    cs:__imp_ReleaseSRWLockExclusive
0x180013536  test    rbp, rbp
0x180013539  jz      short loc_180013544
0x18001353b  mov     rcx, rbp; SRWLock
0x18001353e  call    cs:__imp_ReleaseSRWLockExclusive
0x180013544  test    rbx, rbx
0x180013547  jz      short loc_180013551
0x180013549  mov     rcx, rbx
0x18001354c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180013551  xor     eax, eax
0x180013553  mov     rbx, [rsp+68h+arg_8]
0x180013558  add     rsp, 30h
0x18001355c  pop     r15
0x18001355e  pop     r14
0x180013560  pop     r13
0x180013562  pop     r12
0x180013564  pop     rdi
0x180013565  pop     rsi
0x180013566  pop     rbp
0x180013567  retn
```

# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *> *,void *,EventRegistrationToken *)

- ea: `0x18000cc9c`
- end: `0x18000cf1b`
- name: `?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x1800021ac`
- `0x18000cc9c`
- `0x18000d890`
- `0x18000dc70`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ceaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ccd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ceaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cee3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cee3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cef1`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // r13
  RTL_SRWLOCK *v7; // r12
  unsigned __int64 v8; // rbx
  volatile signed __int32 *v9; // rax
  Microsoft::WRL::Details::EventTargetArray *v10; // rdi
  int v11; // ebp
  volatile signed __int32 *v12; // r14
  Microsoft::WRL::Details::EventTargetArray *v13; // rbx
  signed __int32 v14; // eax
  _QWORD *Ptr; // rax
  __int64 *v17; // r13
  _QWORD *i; // r14
  __int64 v19; // rdi
  __int64 *v20; // rbp
  __int64 v21; // rcx
  __int64 *v22; // rdi
  __int64 v23; // rcx
  PVOID v24; // rdi
  PVOID v25; // rcx
  char v26; // [rsp+20h] [rbp-48h] BYREF
  __int64 v27; // [rsp+70h] [rbp+8h]

  v4 = a3;
  *a4 = 0;
  v7 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  if ( a1->Ptr )
    v8 = ((__int64)(*((_QWORD *)a1->Ptr + 3) - *((_QWORD *)a1->Ptr + 2)) >> 3) + 1;
  else
    v8 = 1;
  v9 = (volatile signed __int32 *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (Microsoft::WRL::Details::EventTargetArray *)v9;
  if ( !v9 )
  {
    v11 = -2147024882;
LABEL_17:
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    return (unsigned int)v11;
  }
  v12 = v9 + 3;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v10 = &Microsoft::WRL::Details::EventTargetArray::`vftable';
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 0;
  *((_QWORD *)v10 + 4) = 0;
  v11 = Microsoft::WRL::Details::EventTargetArray::RuntimeClassInitialize(v10, v8);
  if ( v11 >= 0 )
  {
    v13 = v10;
    do
    {
      if ( *v12 == 0x7FFFFFFF )
        break;
      v14 = *v12;
    }
    while ( v14 != _InterlockedCompareExchange(v12, v14 + 1, v14) );
    v11 = 0;
  }
  else
  {
    v13 = 0;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v10);
  if ( v11 < 0 )
  {
    if ( v13 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v13);
    goto LABEL_17;
  }
  Ptr = a1->Ptr;
  if ( a1->Ptr )
  {
    v17 = (__int64 *)Ptr[4];
    for ( i = (_QWORD *)Ptr[2]; i != (_QWORD *)Ptr[3]; ++i )
    {
      v27 = *v17;
      v19 = *i;
      v20 = (__int64 *)*((_QWORD *)v13 + 3);
      if ( *v20 != *i )
      {
        if ( v19 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(*i);
        v21 = *v20;
        *v20 = v19;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      *(_QWORD *)(*((_QWORD *)v13 + 4) + 8 * ((__int64)(*((_QWORD *)v13 + 3) - *((_QWORD *)v13 + 2)) >> 3)) = v27;
      *((_QWORD *)v13 + 3) += 8LL;
      ++v17;
      Ptr = a1->Ptr;
    }
    v4 = a3;
  }
  *a4 = a2;
  v22 = (__int64 *)*((_QWORD *)v13 + 3);
  if ( *v22 != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v23 = *v22;
    *v22 = a2;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  *(_QWORD *)(*((_QWORD *)v13 + 4) + 8 * ((__int64)(*((_QWORD *)v13 + 3) - *((_QWORD *)v13 + 2)) >> 3)) = v4;
  *((_QWORD *)v13 + 3) += 8LL;
  AcquireSRWLockExclusive(a1 + 1);
  v24 = 0;
  if ( &v26 != (char *)a1 )
  {
    v24 = a1->Ptr;
    a1->Ptr = 0;
  }
  v25 = a1->Ptr;
  a1->Ptr = v13;
  if ( v25 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v25);
  if ( a1 != (RTL_SRWLOCK *)-8LL )
    ReleaseSRWLockExclusive(a1 + 1);
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  if ( v24 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v24);
  return 0;
}

```

## disassembly

```asm
0x18000cc9c  mov     [rsp+arg_8], rbx
0x18000cca1  mov     [rsp+arg_18], r9
0x18000cca6  mov     [rsp+arg_10], r8
0x18000ccab  push    rbp
0x18000ccac  push    rsi
0x18000ccad  push    rdi
0x18000ccae  push    r12
0x18000ccb0  push    r13
0x18000ccb2  push    r14
0x18000ccb4  push    r15
0x18000ccb6  sub     rsp, 30h
0x18000ccba  mov     r13, r8
0x18000ccbd  mov     r15, rdx
0x18000ccc0  mov     rsi, rcx
0x18000ccc3  mov     qword ptr [r9], 0
0x18000ccca  lea     r12, [rcx+10h]
0x18000ccce  mov     rcx, r12; SRWLock
0x18000ccd1  call    cs:__imp_AcquireSRWLockExclusive
0x18000ccd7  mov     rax, [rsi]
0x18000ccda  test    rax, rax
0x18000ccdd  jnz     short loc_18000CCE4
0x18000ccdf  lea     ebx, [rax+1]
0x18000cce2  jmp     short loc_18000CCF3
0x18000cce4  mov     rbx, [rax+18h]
0x18000cce8  sub     rbx, [rax+10h]
0x18000ccec  sar     rbx, 3
0x18000ccf0  inc     rbx
0x18000ccf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ccfa  mov     ecx, 28h ; '('; unsigned __int64
0x18000ccff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cd04  mov     rdi, rax
0x18000cd07  test    rax, rax
0x18000cd0a  jnz     short loc_18000CD16
0x18000cd0c  mov     ebp, 8007000Eh
0x18000cd11  jmp     loc_18000CDA7
0x18000cd16  lea     r14, [rax+0Ch]
0x18000cd1a  mov     dword ptr [r14], 1
0x18000cd21  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18000cd28  mov     [rdi], rax
0x18000cd2b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000cd32  xor     ebp, ebp
0x18000cd34  test    rcx, rcx
0x18000cd37  jz      short loc_18000CD46
0x18000cd39  mov     rax, [rcx]
0x18000cd3c  mov     rax, [rax+8]
0x18000cd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd45  nop
0x18000cd46  lea     rax, ??_7EventTargetArray@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::EventTargetArray::`vftable'
0x18000cd4d  mov     [rdi], rax
0x18000cd50  mov     [rdi+10h], rbp
0x18000cd54  mov     [rdi+18h], rbp
0x18000cd58  mov     [rdi+20h], rbp
0x18000cd5c  mov     rdx, rbx; unsigned __int64
0x18000cd5f  mov     rcx, rdi; this
0x18000cd62  call    ?RuntimeClassInitialize@EventTargetArray@Details@WRL@Microsoft@@QEAAJ_K@Z; Microsoft::WRL::Details::EventTargetArray::RuntimeClassInitialize(unsigned __int64)
0x18000cd67  mov     ebp, eax
0x18000cd69  test    eax, eax
0x18000cd6b  jns     short loc_18000CD71
0x18000cd6d  xor     ebx, ebx
0x18000cd6f  jmp     short loc_18000CD8E
0x18000cd71  mov     rbx, rdi
0x18000cd74  mov     edx, 7FFFFFFFh
0x18000cd79  jmp     short loc_18000CD85
0x18000cd7b  lea     ecx, [rax+1]
0x18000cd7e  lock cmpxchg [r14], ecx
0x18000cd83  jz      short loc_18000CD8C
0x18000cd85  mov     eax, [r14]
0x18000cd88  cmp     eax, edx
0x18000cd8a  jnz     short loc_18000CD7B
0x18000cd8c  xor     ebp, ebp
0x18000cd8e  mov     rcx, rdi
0x18000cd91  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000cd96  test    ebp, ebp
0x18000cd98  jns     short loc_18000CDBC
0x18000cd9a  test    rbx, rbx
0x18000cd9d  jz      short loc_18000CDA7
0x18000cd9f  mov     rcx, rbx
0x18000cda2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000cda7  test    r12, r12
0x18000cdaa  jz      short loc_18000CDB5
0x18000cdac  mov     rcx, r12; SRWLock
0x18000cdaf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdb5  mov     eax, ebp
0x18000cdb7  jmp     loc_18000CF06
0x18000cdbc  mov     rax, [rsi]
0x18000cdbf  test    rax, rax
0x18000cdc2  jz      loc_18000CE4E
0x18000cdc8  mov     r13, [rax+20h]
0x18000cdcc  mov     r14, [rax+10h]
0x18000cdd0  cmp     r14, [rax+18h]
0x18000cdd4  jz      short loc_18000CE46
0x18000cdd6  mov     rax, [r13+0]
0x18000cdda  mov     [rsp+68h+arg_0], rax
0x18000cddf  mov     rdi, [r14]
0x18000cde2  mov     rbp, [rbx+18h]
0x18000cde6  cmp     [rbp+0], rdi
0x18000cdea  jz      short loc_18000CE1B
0x18000cdec  test    rdi, rdi
0x18000cdef  jz      short loc_18000CE01
0x18000cdf1  mov     rax, [rdi]
0x18000cdf4  mov     rcx, rdi
0x18000cdf7  mov     rax, [rax+8]
0x18000cdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce00  nop
0x18000ce01  mov     rcx, [rbp+0]
0x18000ce05  mov     [rbp+0], rdi
0x18000ce09  test    rcx, rcx
0x18000ce0c  jz      short loc_18000CE1B
0x18000ce0e  mov     rax, [rcx]
0x18000ce11  mov     rax, [rax+10h]
0x18000ce15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1a  nop
0x18000ce1b  mov     rcx, [rbx+18h]
0x18000ce1f  sub     rcx, [rbx+10h]
0x18000ce23  sar     rcx, 3
0x18000ce27  mov     rax, [rbx+20h]
0x18000ce2b  mov     rdx, [rsp+68h+arg_0]
0x18000ce30  mov     [rax+rcx*8], rdx
0x18000ce34  add     qword ptr [rbx+18h], 8
0x18000ce39  add     r13, 8
0x18000ce3d  add     r14, 8
0x18000ce41  mov     rax, [rsi]
0x18000ce44  jmp     short loc_18000CDD0
0x18000ce46  mov     r13, [rsp+68h+arg_10]
0x18000ce4e  mov     rax, [rsp+68h+arg_18]
0x18000ce56  mov     [rax], r15
0x18000ce59  mov     rdi, [rbx+18h]
0x18000ce5d  cmp     [rdi], r15
0x18000ce60  jz      short loc_18000CE8F
0x18000ce62  test    r15, r15
0x18000ce65  jz      short loc_18000CE77
0x18000ce67  mov     rax, [r15]
0x18000ce6a  mov     rcx, r15
0x18000ce6d  mov     rax, [rax+8]
0x18000ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce76  nop
0x18000ce77  mov     rcx, [rdi]
0x18000ce7a  mov     [rdi], r15
0x18000ce7d  test    rcx, rcx
0x18000ce80  jz      short loc_18000CE8F
0x18000ce82  mov     rax, [rcx]
0x18000ce85  mov     rax, [rax+10h]
0x18000ce89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce8e  nop
0x18000ce8f  mov     rcx, [rbx+18h]
0x18000ce93  sub     rcx, [rbx+10h]
0x18000ce97  sar     rcx, 3
0x18000ce9b  mov     rax, [rbx+20h]
0x18000ce9f  mov     [rax+rcx*8], r13
0x18000cea3  add     qword ptr [rbx+18h], 8
0x18000cea8  lea     rbp, [rsi+8]
0x18000ceac  mov     rcx, rbp; SRWLock
0x18000ceaf  call    cs:__imp_AcquireSRWLockExclusive
0x18000ceb5  xor     edi, edi
0x18000ceb7  lea     rax, [rsp+68h+var_48]
0x18000cebc  cmp     rax, rsi
0x18000cebf  jz      short loc_18000CECB
0x18000cec1  mov     rdi, [rsi]
0x18000cec4  mov     qword ptr [rsi], 0
0x18000cecb  mov     rcx, [rsi]
0x18000cece  mov     [rsi], rbx
0x18000ced1  test    rcx, rcx
0x18000ced4  jz      short loc_18000CEDB
0x18000ced6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000cedb  test    rbp, rbp
0x18000cede  jz      short loc_18000CEE9
0x18000cee0  mov     rcx, rbp; SRWLock
0x18000cee3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cee9  test    r12, r12
0x18000ceec  jz      short loc_18000CEF7
0x18000ceee  mov     rcx, r12; SRWLock
0x18000cef1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cef7  test    rdi, rdi
0x18000cefa  jz      short loc_18000CF04
0x18000cefc  mov     rcx, rdi
0x18000ceff  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000cf04  xor     eax, eax
0x18000cf06  mov     rbx, [rsp+68h+arg_8]
0x18000cf0b  add     rsp, 30h
0x18000cf0f  pop     r15
0x18000cf11  pop     r14
0x18000cf13  pop     r13
0x18000cf15  pop     r12
0x18000cf17  pop     rdi
0x18000cf18  pop     rsi
0x18000cf19  pop     rbp
0x18000cf1a  retn
```

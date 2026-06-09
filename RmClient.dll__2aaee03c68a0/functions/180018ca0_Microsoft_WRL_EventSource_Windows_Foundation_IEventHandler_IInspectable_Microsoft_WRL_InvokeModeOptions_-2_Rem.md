# Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x180018ca0`
- end: `0x180018e12`
- name: `?Remove@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, struct IUnknown *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180017d78`
- `0x180019140`
- `0x180019160`

## callees

- `0x18000a474`
- `0x18000a640`
- `0x18000fb40`
- `0x1800105e8`
- `0x180013594`
- `0x180018ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ded`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2)
{
  volatile int *v4; // rdx
  _QWORD *Ptr; // rax
  struct IUnknown **v6; // rcx
  __int64 v7; // r15
  RTL_SRWLOCK *v8; // r15
  bool v9; // r14
  int v10; // esi
  struct IUnknown **v12; // rsi
  void **v13; // r12
  Microsoft::WRL::Details::EventTargetArray *v14; // [rsp+60h] [rbp+40h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+48h] BYREF
  __int64 v16; // [rsp+70h] [rbp+50h] BYREF
  PSRWLOCK v17; // [rsp+78h] [rbp+58h] BYREF

  v16 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 2);
  Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  v6 = (struct IUnknown **)Ptr[2];
  v7 = Ptr[3] - (_QWORD)v6;
  v14 = 0;
  v8 = (RTL_SRWLOCK *)((v7 >> 3) - 1);
  v17 = v8;
  if ( !v8 )
  {
    v9 = *v6 == a2;
    goto LABEL_19;
  }
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(
          &v14,
          &v17);
  if ( v10 >= 0 )
  {
    v9 = 0;
    v12 = (struct IUnknown **)*((_QWORD *)a1->Ptr + 2);
    v13 = (void **)*((_QWORD *)a1->Ptr + 4);
    if ( v12 == *((struct IUnknown ***)a1->Ptr + 3) )
    {
LABEL_22:
      if ( v14 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
          (__int64)v14,
          v4);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v16 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v16, v4);
      return 0;
    }
    do
    {
      if ( v9 || a2 != *v12 )
      {
        if ( !v8 )
          break;
        Microsoft::WRL::Details::EventTargetArray::AddTail(v14, *v12, *v13++);
        v8 = (RTL_SRWLOCK *)((char *)v8 - 1);
      }
      else
      {
        v9 = 1;
      }
      ++v12;
    }
    while ( v12 != *((struct IUnknown ***)a1->Ptr + 3) );
LABEL_19:
    if ( v9 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v17, a1 + 1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v16, (char *)a1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=((__int64 *)a1, (char *)&v14);
      if ( v17 )
        ReleaseSRWLockExclusive(v17);
    }
    goto LABEL_22;
  }
  if ( v14 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
      (__int64)v14,
      v4);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018ca0  push    rbp
0x180018ca2  push    rbx
0x180018ca3  push    rsi
0x180018ca4  push    rdi
0x180018ca5  push    r12
0x180018ca7  push    r14
0x180018ca9  push    r15
0x180018cab  mov     rbp, rsp
0x180018cae  sub     rsp, 20h
0x180018cb2  mov     rbx, rdx
0x180018cb5  mov     [rbp+arg_10], 0
0x180018cbd  lea     rdx, [rcx+10h]
0x180018cc1  mov     rdi, rcx
0x180018cc4  lea     rcx, [rbp+SRWLock]
0x180018cc8  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180018ccd  mov     rax, [rdi]
0x180018cd0  test    rax, rax
0x180018cd3  jnz     short loc_180018CED
0x180018cd5  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018cd9  test    rcx, rcx
0x180018cdc  jz      loc_180018E01
0x180018ce2  call    cs:__imp_ReleaseSRWLockExclusive
0x180018ce8  jmp     loc_180018E01
0x180018ced  mov     rcx, [rax+10h]
0x180018cf1  mov     r15, [rax+18h]
0x180018cf5  sub     r15, rcx
0x180018cf8  mov     [rbp+arg_0], 0
0x180018d00  sar     r15, 3
0x180018d04  sub     r15, 1
0x180018d08  mov     [rbp+arg_18], r15
0x180018d0c  jnz     short loc_180018D1A
0x180018d0e  cmp     [rcx], rbx
0x180018d11  setz    r14b
0x180018d15  jmp     loc_180018D9D
0x180018d1a  lea     rdx, [rbp+arg_18]
0x180018d1e  lea     rcx, [rbp+arg_0]
0x180018d22  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@AEA_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@AEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &)
0x180018d27  mov     esi, eax
0x180018d29  test    eax, eax
0x180018d2b  jns     short loc_180018D51
0x180018d2d  mov     rcx, [rbp+arg_0]
0x180018d31  test    rcx, rcx
0x180018d34  jz      short loc_180018D3B
0x180018d36  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018d3b  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018d3f  test    rcx, rcx
0x180018d42  jz      short loc_180018D4A
0x180018d44  call    cs:__imp_ReleaseSRWLockExclusive
0x180018d4a  mov     eax, esi
0x180018d4c  jmp     loc_180018E03
0x180018d51  mov     rax, [rdi]
0x180018d54  xor     r14b, r14b
0x180018d57  mov     rsi, [rax+10h]
0x180018d5b  mov     r12, [rax+20h]
0x180018d5f  cmp     rsi, [rax+18h]
0x180018d63  jz      short loc_180018DD6
0x180018d65  test    r14b, r14b
0x180018d68  jnz     short loc_180018D74
0x180018d6a  cmp     rbx, [rsi]
0x180018d6d  jnz     short loc_180018D74
0x180018d6f  mov     r14b, 1
0x180018d72  jmp     short loc_180018D90
0x180018d74  test    r15, r15
0x180018d77  jz      short loc_180018D9D
0x180018d79  mov     r8, [r12]; void *
0x180018d7d  mov     rdx, [rsi]; struct IUnknown *
0x180018d80  mov     rcx, [rbp+arg_0]; this
0x180018d84  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180018d89  add     r12, 8
0x180018d8d  dec     r15
0x180018d90  mov     rax, [rdi]
0x180018d93  add     rsi, 8
0x180018d97  cmp     rsi, [rax+18h]
0x180018d9b  jnz     short loc_180018D65
0x180018d9d  test    r14b, r14b
0x180018da0  jz      short loc_180018DD6
0x180018da2  lea     rdx, [rdi+8]
0x180018da6  lea     rcx, [rbp+arg_18]
0x180018daa  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180018daf  mov     rdx, rdi
0x180018db2  lea     rcx, [rbp+arg_10]
0x180018db6  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180018dbb  lea     rdx, [rbp+arg_0]
0x180018dbf  mov     rcx, rdi
0x180018dc2  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180018dc7  mov     rcx, [rbp+arg_18]; SRWLock
0x180018dcb  test    rcx, rcx
0x180018dce  jz      short loc_180018DD6
0x180018dd0  call    cs:__imp_ReleaseSRWLockExclusive
0x180018dd6  mov     rcx, [rbp+arg_0]
0x180018dda  test    rcx, rcx
0x180018ddd  jz      short loc_180018DE4
0x180018ddf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018de4  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018de8  test    rcx, rcx
0x180018deb  jz      short loc_180018DF3
0x180018ded  call    cs:__imp_ReleaseSRWLockExclusive
0x180018df3  mov     rcx, [rbp+arg_10]
0x180018df7  test    rcx, rcx
0x180018dfa  jz      short loc_180018E01
0x180018dfc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018e01  xor     eax, eax
0x180018e03  add     rsp, 20h
0x180018e07  pop     r15
0x180018e09  pop     r14
0x180018e0b  pop     r12
0x180018e0d  pop     rdi
0x180018e0e  pop     rsi
0x180018e0f  pop     rbx
0x180018e10  pop     rbp
0x180018e11  retn
```

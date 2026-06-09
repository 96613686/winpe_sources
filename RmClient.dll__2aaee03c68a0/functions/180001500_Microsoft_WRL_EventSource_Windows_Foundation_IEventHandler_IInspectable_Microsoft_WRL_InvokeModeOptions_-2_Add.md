# Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<IInspectable *> *,void *,EventRegistrationToken *)

- ea: `0x180001500`
- end: `0x180001663`
- name: `?AddInternal@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(char *, struct IUnknown *, void *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000145c`

## callees

- `0x180001500`
- `0x18000a474`
- `0x18000a4b4`
- `0x18000a640`
- `0x18000fb40`
- `0x1800105e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000159a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001619`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000159a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001619`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001636`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        char *a1,
        struct IUnknown *a2,
        void *a3,
        struct IUnknown **a4)
{
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  _QWORD *v12; // rax
  void **v13; // rsi
  struct IUnknown **i; // rdi
  Microsoft::WRL::Details::EventTargetArray *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-10h] BYREF
  PSRWLOCK v17; // [rsp+28h] [rbp-8h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v18; // [rsp+60h] [rbp+30h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp+48h] BYREF

  *a4 = 0;
  v16 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 16);
  v8 = *(_QWORD **)a1;
  v18 = 0;
  if ( v8 )
    v9 = ((__int64)(v8[3] - v8[2]) >> 3) + 1;
  else
    v9 = 1;
  v17 = (PSRWLOCK)v9;
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v18,
          &v17);
  if ( v10 >= 0 )
  {
    v12 = *(_QWORD **)a1;
    if ( *(_QWORD *)a1 )
    {
      v13 = (void **)v12[4];
      for ( i = (struct IUnknown **)v12[2]; i != (struct IUnknown **)v12[3]; ++i )
      {
        Microsoft::WRL::Details::EventTargetArray::AddTail(v18, *i, *v13);
        v12 = *(_QWORD **)a1;
        ++v13;
      }
    }
    v15 = v18;
    *a4 = a2;
    Microsoft::WRL::Details::EventTargetArray::AddTail(v15, a2, a3);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v17, a1 + 8);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v16, a1);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=((__int64 *)a1, (char *)&v18);
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    if ( v18 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v16 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    return 0;
  }
  else
  {
    if ( v18 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180001500  mov     [rsp-28h+arg_8], rbx
0x180001505  mov     [rsp-28h+arg_10], rsi
0x18000150a  push    rbp
0x18000150b  push    rdi
0x18000150c  push    r12
0x18000150e  push    r14
0x180001510  push    r15
0x180001512  mov     rbp, rsp
0x180001515  sub     rsp, 30h
0x180001519  mov     r15, rdx
0x18000151c  mov     qword ptr [r9], 0
0x180001523  lea     rdx, [rcx+10h]
0x180001527  mov     [rbp+var_10], 0
0x18000152f  mov     rbx, rcx
0x180001532  mov     r14, r9
0x180001535  lea     rcx, [rbp+SRWLock]
0x180001539  mov     r12, r8
0x18000153c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180001541  mov     rcx, [rbx]
0x180001544  mov     [rbp+arg_0], 0
0x18000154c  test    rcx, rcx
0x18000154f  jnz     short loc_180001558
0x180001551  mov     ecx, 1
0x180001556  jmp     short loc_18000156C
0x180001558  mov     rax, [rcx+18h]
0x18000155c  sub     rax, [rcx+10h]
0x180001560  mov     ecx, 1
0x180001565  sar     rax, 3
0x180001569  add     rcx, rax
0x18000156c  mov     [rbp+var_8], rcx
0x180001570  lea     rdx, [rbp+var_8]
0x180001574  lea     rcx, [rbp+arg_0]
0x180001578  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x18000157d  mov     edi, eax
0x18000157f  test    eax, eax
0x180001581  jns     short loc_1800015A7
0x180001583  mov     rcx, [rbp+arg_0]
0x180001587  test    rcx, rcx
0x18000158a  jz      short loc_180001591
0x18000158c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180001591  mov     rcx, [rbp+SRWLock]; SRWLock
0x180001595  test    rcx, rcx
0x180001598  jz      short loc_1800015A0
0x18000159a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800015a0  mov     eax, edi
0x1800015a2  jmp     loc_18000164C
0x1800015a7  mov     rax, [rbx]
0x1800015aa  test    rax, rax
0x1800015ad  jz      short loc_1800015D9
0x1800015af  mov     rsi, [rax+20h]
0x1800015b3  mov     rdi, [rax+10h]
0x1800015b7  jmp     short loc_1800015D3
0x1800015b9  mov     r8, [rsi]; void *
0x1800015bc  mov     rdx, [rdi]; struct IUnknown *
0x1800015bf  mov     rcx, [rbp+arg_0]; this
0x1800015c3  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x1800015c8  mov     rax, [rbx]
0x1800015cb  lea     rsi, [rsi+8]
0x1800015cf  add     rdi, 8
0x1800015d3  cmp     rdi, [rax+18h]
0x1800015d7  jnz     short loc_1800015B9
0x1800015d9  mov     rcx, [rbp+arg_0]; this
0x1800015dd  mov     r8, r12; void *
0x1800015e0  mov     rdx, r15; struct IUnknown *
0x1800015e3  mov     [r14], r15
0x1800015e6  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x1800015eb  lea     rdx, [rbx+8]
0x1800015ef  lea     rcx, [rbp+var_8]
0x1800015f3  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800015f8  mov     rdx, rbx
0x1800015fb  lea     rcx, [rbp+var_10]
0x1800015ff  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180001604  lea     rdx, [rbp+arg_0]
0x180001608  mov     rcx, rbx
0x18000160b  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180001610  mov     rcx, [rbp+var_8]; SRWLock
0x180001614  test    rcx, rcx
0x180001617  jz      short loc_18000161F
0x180001619  call    cs:__imp_ReleaseSRWLockExclusive
0x18000161f  mov     rcx, [rbp+arg_0]
0x180001623  test    rcx, rcx
0x180001626  jz      short loc_18000162D
0x180001628  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000162d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180001631  test    rcx, rcx
0x180001634  jz      short loc_18000163C
0x180001636  call    cs:__imp_ReleaseSRWLockExclusive
0x18000163c  mov     rcx, [rbp+var_10]
0x180001640  test    rcx, rcx
0x180001643  jz      short loc_18000164A
0x180001645  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000164a  xor     eax, eax
0x18000164c  mov     rbx, [rsp+30h+arg_8]
0x180001651  mov     rsi, [rsp+30h+arg_10]
0x180001656  add     rsp, 30h
0x18000165a  pop     r15
0x18000165c  pop     r14
0x18000165e  pop     r12
0x180001660  pop     rdi
0x180001661  pop     rbp
0x180001662  retn
```

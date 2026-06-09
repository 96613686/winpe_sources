# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *> *,void *,EventRegistrationToken *)

- ea: `0x18001b0c4`
- end: `0x18001b222`
- name: `?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusNavigatingEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextFocusNavigatingEventArgs@23456@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `350`
- prototype: ``
- caller_count: `31`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025b60`
- `0x180025b90`
- `0x180025bc0`
- `0x180025bf0`
- `0x180025c20`
- `0x180025c50`
- `0x180025c80`
- `0x180025cb0`
- `0x180025ce0`
- `0x180025d10`
- `0x180025d40`
- `0x180025d70`
- `0x180025da0`
- `0x180025dd0`
- `0x180025e00`
- `0x180025e30`
- `0x180025e60`
- `0x180025e90`
- `0x180025ec0`
- `0x180025ef0`
- `0x180025f20`
- `0x180025f50`
- `0x180025f80`
- `0x180025fb0`
- `0x180025fe0`
- `0x180026010`
- `0x180026040`
- `0x180026070`
- `0x1800260a0`
- `0x1800260d0`
- `0x180026100`

## callees

- `0x180019118`
- `0x18001b0c4`
- `0x18001b300`
- `0x180024b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b15b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b15b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b0f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b0f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1b6`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextFocusNavigatingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2,
        void *a3,
        struct IUnknown **a4)
{
  RTL_SRWLOCK *v4; // rbp
  _QWORD *Ptr; // rcx
  __int64 v10; // rcx
  int v11; // ebx
  _QWORD *v13; // rax
  Microsoft::WRL::Details::EventTargetArray *v14; // rdi
  void **v15; // r14
  struct IUnknown **i; // rbx
  _QWORD *v17; // rbx
  RTL_SRWLOCK v18; // rcx
  char v19; // [rsp+20h] [rbp-48h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v20; // [rsp+70h] [rbp+8h] BYREF
  __int64 v21; // [rsp+88h] [rbp+20h] BYREF

  v4 = a1 + 2;
  *a4 = 0;
  AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1->Ptr;
  v20 = 0;
  if ( Ptr )
    v10 = ((__int64)(Ptr[3] - Ptr[2]) >> 3) + 1;
  else
    v10 = 1;
  v21 = v10;
  v11 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v20,
          &v21);
  if ( v11 >= 0 )
  {
    v13 = a1->Ptr;
    v14 = v20;
    if ( a1->Ptr )
    {
      v15 = (void **)v13[4];
      for ( i = (struct IUnknown **)v13[2]; i != (struct IUnknown **)v13[3]; ++i )
      {
        Microsoft::WRL::Details::EventTargetArray::AddTail(v14, *i, *v15);
        v13 = a1->Ptr;
        ++v15;
      }
    }
    *a4 = a2;
    Microsoft::WRL::Details::EventTargetArray::AddTail(v14, a2, a3);
    AcquireSRWLockExclusive(a1 + 1);
    v17 = 0;
    if ( &v19 != (char *)a1 )
    {
      v17 = a1->Ptr;
      a1->Ptr = 0;
    }
    v18.Ptr = a1->Ptr;
    a1->Ptr = v14;
    if ( v18.Ptr )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v18.Ptr);
    if ( a1 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(a1 + 1);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v17 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v17);
    return 0;
  }
  else
  {
    if ( v20 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v20);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18001b0c4  mov     [rsp+arg_8], rbx
0x18001b0c9  push    rbp
0x18001b0ca  push    rsi
0x18001b0cb  push    rdi
0x18001b0cc  push    r12
0x18001b0ce  push    r13
0x18001b0d0  push    r14
0x18001b0d2  push    r15
0x18001b0d4  sub     rsp, 30h
0x18001b0d8  lea     rbp, [rcx+10h]
0x18001b0dc  mov     qword ptr [r9], 0
0x18001b0e3  mov     rsi, rcx
0x18001b0e6  mov     r15, r9
0x18001b0e9  mov     rcx, rbp; SRWLock
0x18001b0ec  mov     r13, r8
0x18001b0ef  mov     r12, rdx
0x18001b0f2  call    cs:__imp_AcquireSRWLockExclusive
0x18001b0f8  mov     rcx, [rsi]
0x18001b0fb  mov     [rsp+68h+arg_0], 0
0x18001b104  test    rcx, rcx
0x18001b107  jnz     short loc_18001B110
0x18001b109  mov     ecx, 1
0x18001b10e  jmp     short loc_18001B124
0x18001b110  mov     rax, [rcx+18h]
0x18001b114  sub     rax, [rcx+10h]
0x18001b118  mov     ecx, 1
0x18001b11d  sar     rax, 3
0x18001b121  add     rcx, rax
0x18001b124  mov     [rsp+68h+arg_18], rcx
0x18001b12c  lea     rdx, [rsp+68h+arg_18]
0x18001b134  lea     rcx, [rsp+68h+arg_0]
0x18001b139  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x18001b13e  mov     ebx, eax
0x18001b140  test    eax, eax
0x18001b142  jns     short loc_18001B168
0x18001b144  mov     rcx, [rsp+68h+arg_0]
0x18001b149  test    rcx, rcx
0x18001b14c  jz      short loc_18001B153
0x18001b14e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001b153  test    rbp, rbp
0x18001b156  jz      short loc_18001B161
0x18001b158  mov     rcx, rbp; SRWLock
0x18001b15b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b161  mov     eax, ebx
0x18001b163  jmp     loc_18001B20D
0x18001b168  mov     rax, [rsi]
0x18001b16b  mov     rdi, [rsp+68h+arg_0]
0x18001b170  test    rax, rax
0x18001b173  jz      short loc_18001B19E
0x18001b175  mov     r14, [rax+20h]
0x18001b179  mov     rbx, [rax+10h]
0x18001b17d  jmp     short loc_18001B198
0x18001b17f  mov     r8, [r14]; void *
0x18001b182  mov     rcx, rdi; this
0x18001b185  mov     rdx, [rbx]; struct IUnknown *
0x18001b188  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18001b18d  mov     rax, [rsi]
0x18001b190  lea     r14, [r14+8]
0x18001b194  add     rbx, 8
0x18001b198  cmp     rbx, [rax+18h]
0x18001b19c  jnz     short loc_18001B17F
0x18001b19e  mov     r8, r13; void *
0x18001b1a1  mov     [r15], r12
0x18001b1a4  mov     rdx, r12; struct IUnknown *
0x18001b1a7  mov     rcx, rdi; this
0x18001b1aa  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x18001b1af  lea     r14, [rsi+8]
0x18001b1b3  mov     rcx, r14; SRWLock
0x18001b1b6  call    cs:__imp_AcquireSRWLockExclusive
0x18001b1bc  lea     rax, [rsp+68h+var_48]
0x18001b1c1  xor     ebx, ebx
0x18001b1c3  cmp     rax, rsi
0x18001b1c6  jz      short loc_18001B1D2
0x18001b1c8  mov     rbx, [rsi]
0x18001b1cb  mov     qword ptr [rsi], 0
0x18001b1d2  mov     rcx, [rsi]
0x18001b1d5  mov     [rsi], rdi
0x18001b1d8  test    rcx, rcx
0x18001b1db  jz      short loc_18001B1E2
0x18001b1dd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001b1e2  test    r14, r14
0x18001b1e5  jz      short loc_18001B1F0
0x18001b1e7  mov     rcx, r14; SRWLock
0x18001b1ea  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b1f0  test    rbp, rbp
0x18001b1f3  jz      short loc_18001B1FE
0x18001b1f5  mov     rcx, rbp; SRWLock
0x18001b1f8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b1fe  test    rbx, rbx
0x18001b201  jz      short loc_18001B20B
0x18001b203  mov     rcx, rbx
0x18001b206  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001b20b  xor     eax, eax
0x18001b20d  mov     rbx, [rsp+68h+arg_8]
0x18001b212  add     rsp, 30h
0x18001b216  pop     r15
0x18001b218  pop     r14
0x18001b21a  pop     r13
0x18001b21c  pop     r12
0x18001b21e  pop     rdi
0x18001b21f  pop     rsi
0x18001b220  pop     rbp
0x18001b221  retn
```

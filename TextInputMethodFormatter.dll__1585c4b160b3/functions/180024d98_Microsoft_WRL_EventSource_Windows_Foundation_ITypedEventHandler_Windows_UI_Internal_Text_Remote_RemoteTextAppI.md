# Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x180024d98`
- end: `0x180024f21`
- name: `?Remove@?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextHostOperationAcknowledgedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `393`
- prototype: ``
- caller_count: `32`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180018cd0`
- `0x180026dc0`
- `0x180026de0`
- `0x180026e00`
- `0x180026e20`
- `0x180026e40`
- `0x180026e60`
- `0x180026e80`
- `0x180026ea0`
- `0x180026ec0`
- `0x180026ee0`
- `0x180026f00`
- `0x180026f20`
- `0x180026f40`
- `0x180026f60`
- `0x180026f80`
- `0x180026fa0`
- `0x180026fc0`
- `0x180026fe0`
- `0x180027000`
- `0x180027020`
- `0x180027040`
- `0x180027060`
- `0x180027080`
- `0x1800270a0`
- `0x1800270c0`
- `0x1800270e0`
- `0x180027100`
- `0x180027120`
- `0x180027140`
- `0x180027160`
- `0x180027180`

## callees

- `0x180019118`
- `0x18001b300`
- `0x180024b70`
- `0x180024d98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024e4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024e6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ec3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024e4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024e6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ec3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024db9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024db9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e18`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextHostOperationAcknowledgedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2)
{
  RTL_SRWLOCK *v2; // rsi
  RTL_SRWLOCK v5; // rax
  struct IUnknown **v6; // rcx
  Microsoft::WRL::Details::EventTargetArray *v7; // rbp
  __int64 v8; // r12
  __int64 v9; // r12
  bool v10; // r15
  RTL_SRWLOCK v11; // rbx
  RTL_SRWLOCK v12; // rcx
  Microsoft::WRL::Details::EventTargetArray *v13; // rax
  int v15; // ebp
  RTL_SRWLOCK v16; // rax
  void **v17; // r13
  struct IUnknown **i; // r14
  char v19; // [rsp+20h] [rbp-48h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v20; // [rsp+70h] [rbp+8h] BYREF
  __int64 v21; // [rsp+78h] [rbp+10h] BYREF

  v2 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v5.Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  v6 = (struct IUnknown **)*((_QWORD *)v5.Ptr + 2);
  v7 = 0;
  v8 = *((_QWORD *)v5.Ptr + 3) - (_QWORD)v6;
  v20 = 0;
  v9 = (v8 >> 3) - 1;
  v21 = v9;
  if ( !v9 )
  {
    v10 = *v6 == a2;
LABEL_6:
    v11.Ptr = 0;
    if ( v10 )
    {
      AcquireSRWLockExclusive(a1 + 1);
      if ( &v19 != (char *)a1 )
      {
        v11.Ptr = a1->Ptr;
        a1->Ptr = 0;
      }
      v12.Ptr = a1->Ptr;
      v13 = v7;
      v7 = 0;
      a1->Ptr = v13;
      if ( v12.Ptr )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v12.Ptr);
      if ( a1 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(a1 + 1);
    }
    if ( v7 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v7);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    if ( v11.Ptr )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11.Ptr);
    return 0;
  }
  v15 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
          &v20,
          &v21);
  if ( v15 >= 0 )
  {
    v16.Ptr = a1->Ptr;
    v10 = 0;
    v7 = v20;
    v17 = (void **)*((_QWORD *)a1->Ptr + 4);
    for ( i = (struct IUnknown **)*((_QWORD *)a1->Ptr + 2); i != *((struct IUnknown ***)v16.Ptr + 3); ++i )
    {
      if ( v10 || a2 != *i )
      {
        if ( !v9 )
          goto LABEL_6;
        Microsoft::WRL::Details::EventTargetArray::AddTail(v7, *i, *v17++);
        --v9;
      }
      else
      {
        v10 = 1;
      }
      v16.Ptr = a1->Ptr;
    }
    goto LABEL_6;
  }
  if ( v20 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v20);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180024d98  mov     [rsp+arg_10], rbx
0x180024d9d  push    rbp
0x180024d9e  push    rsi
0x180024d9f  push    rdi
0x180024da0  push    r12
0x180024da2  push    r13
0x180024da4  push    r14
0x180024da6  push    r15
0x180024da8  sub     rsp, 30h
0x180024dac  lea     rsi, [rcx+10h]
0x180024db0  mov     rdi, rcx
0x180024db3  mov     rcx, rsi; SRWLock
0x180024db6  mov     rbx, rdx
0x180024db9  call    cs:__imp_AcquireSRWLockExclusive
0x180024dbf  mov     rax, [rdi]
0x180024dc2  test    rax, rax
0x180024dc5  jnz     short loc_180024DDE
0x180024dc7  test    rsi, rsi
0x180024dca  jz      loc_180024E7D
0x180024dd0  mov     rcx, rsi; SRWLock
0x180024dd3  call    cs:__imp_ReleaseSRWLockExclusive
0x180024dd9  jmp     loc_180024E7D
0x180024dde  mov     rcx, [rax+10h]
0x180024de2  xor     ebp, ebp
0x180024de4  mov     r12, [rax+18h]
0x180024de8  sub     r12, rcx
0x180024deb  mov     [rsp+68h+arg_0], rbp
0x180024df0  sar     r12, 3
0x180024df4  sub     r12, 1
0x180024df8  mov     [rsp+68h+arg_8], r12
0x180024dfd  jnz     loc_180024E97
0x180024e03  cmp     [rcx], rbx
0x180024e06  setz    r15b
0x180024e0a  xor     ebx, ebx
0x180024e0c  test    r15b, r15b
0x180024e0f  jz      short loc_180024E55
0x180024e11  lea     r14, [rdi+8]
0x180024e15  mov     rcx, r14; SRWLock
0x180024e18  call    cs:__imp_AcquireSRWLockExclusive
0x180024e1e  lea     rax, [rsp+68h+var_48]
0x180024e23  cmp     rax, rdi
0x180024e26  jz      short loc_180024E32
0x180024e28  mov     rbx, [rdi]
0x180024e2b  mov     qword ptr [rdi], 0
0x180024e32  mov     rcx, [rdi]
0x180024e35  mov     rax, rbp
0x180024e38  xor     ebp, ebp
0x180024e3a  mov     [rdi], rax
0x180024e3d  test    rcx, rcx
0x180024e40  jz      short loc_180024E47
0x180024e42  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180024e47  test    r14, r14
0x180024e4a  jz      short loc_180024E55
0x180024e4c  mov     rcx, r14; SRWLock
0x180024e4f  call    cs:__imp_ReleaseSRWLockExclusive
0x180024e55  test    rbp, rbp
0x180024e58  jz      short loc_180024E62
0x180024e5a  mov     rcx, rbp
0x180024e5d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180024e62  test    rsi, rsi
0x180024e65  jz      short loc_180024E70
0x180024e67  mov     rcx, rsi; SRWLock
0x180024e6a  call    cs:__imp_ReleaseSRWLockExclusive
0x180024e70  test    rbx, rbx
0x180024e73  jz      short loc_180024E7D
0x180024e75  mov     rcx, rbx
0x180024e78  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180024e7d  xor     eax, eax
0x180024e7f  mov     rbx, [rsp+68h+arg_10]
0x180024e87  add     rsp, 30h
0x180024e8b  pop     r15
0x180024e8d  pop     r14
0x180024e8f  pop     r13
0x180024e91  pop     r12
0x180024e93  pop     rdi
0x180024e94  pop     rsi
0x180024e95  pop     rbp
0x180024e96  retn
0x180024e97  lea     rdx, [rsp+68h+arg_8]
0x180024e9c  lea     rcx, [rsp+68h+arg_0]
0x180024ea1  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x180024ea6  mov     ebp, eax
0x180024ea8  test    eax, eax
0x180024eaa  jns     short loc_180024ECD
0x180024eac  mov     rcx, [rsp+68h+arg_0]
0x180024eb1  test    rcx, rcx
0x180024eb4  jz      short loc_180024EBB
0x180024eb6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180024ebb  test    rsi, rsi
0x180024ebe  jz      short loc_180024EC9
0x180024ec0  mov     rcx, rsi; SRWLock
0x180024ec3  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ec9  mov     eax, ebp
0x180024ecb  jmp     short loc_180024E7F
0x180024ecd  mov     rax, [rdi]
0x180024ed0  xor     r15b, r15b
0x180024ed3  mov     rbp, [rsp+68h+arg_0]
0x180024ed8  mov     r13, [rax+20h]
0x180024edc  mov     r14, [rax+10h]
0x180024ee0  cmp     r14, [rax+18h]
0x180024ee4  jz      loc_180024E0A
0x180024eea  test    r15b, r15b
0x180024eed  jnz     short loc_180024EF9
0x180024eef  cmp     rbx, [r14]
0x180024ef2  jnz     short loc_180024EF9
0x180024ef4  mov     r15b, 1
0x180024ef7  jmp     short loc_180024F18
0x180024ef9  test    r12, r12
0x180024efc  jz      loc_180024E0A
0x180024f02  mov     r8, [r13+0]; void *
0x180024f06  mov     rcx, rbp; this
0x180024f09  mov     rdx, [r14]; struct IUnknown *
0x180024f0c  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180024f11  add     r13, 8
0x180024f15  dec     r12
0x180024f18  mov     rax, [rdi]
0x180024f1b  add     r14, 8
0x180024f1f  jmp     short loc_180024EE0
```

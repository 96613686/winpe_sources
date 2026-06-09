# EventMethod::FireEvent(ICallFrame *,EventInterface &)

- ea: `0x18000e6c0`
- end: `0x18000e9de`
- name: `?FireEvent@EventMethod@@QEAAJPEAUICallFrame@@AEAVEventInterface@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(EventMethod *__hidden this, struct ICallFrame *, struct EventInterface *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e5d0`

## callees

- `0x180003d54`
- `0x180008938`
- `0x18000e6c0`
- `0x18000e9e4`
- `0x18000eaf0`
- `0x18000ec88`
- `0x180010410`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e833`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e94e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e94e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e998`

## string_xrefs

- `0x18000e862`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000e976`: `com\complus\src\events\tier1\agent.cpp`
- `0x18000e9ab`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall EventMethod::FireEvent(EventMethod *this, struct ICallFrame *a2, struct EventInterface *a3)
{
  __int64 v3; // rax
  struct IMultiInterfacePublisherFilter *v7; // rbp
  char v8; // r14
  int v9; // eax
  int v10; // edi
  ParallelFiringControl *v11; // rax
  SerialFiringControl *v12; // rax
  struct IFiringControl *v13; // rbx
  __int64 result; // rax
  int v15; // r12d
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  SerialFiringControl *v19; // rax
  SerialFiringControl *v20; // rax
  SerialFiringControl *v21; // rsi
  SerialFiringControl *v22; // rax
  ParallelFiringControl *v23; // rax
  __int64 v24; // [rsp+90h] [rbp+18h] BYREF
  __int64 v25; // [rsp+98h] [rbp+20h] BYREF

  v3 = *((_QWORD *)a3 + 2);
  v7 = *(struct IMultiInterfacePublisherFilter **)(v3 + 128);
  v8 = *(_BYTE *)(v3 + 112);
  if ( v7 || *((_QWORD *)this + 2) )
  {
    if ( (v8 & 2) != 0 )
    {
      v11 = (ParallelFiringControl *)CoTaskMemAlloc(0xA0u);
      if ( v11 )
      {
        v12 = ParallelFiringControl::ParallelFiringControl(v11, this, a3, a2);
        goto LABEL_10;
      }
    }
    else
    {
      v22 = (SerialFiringControl *)CoTaskMemAlloc(0x38u);
      if ( v22 )
      {
        v12 = SerialFiringControl::SerialFiringControl(v22, this, a3, a2);
LABEL_10:
        v13 = (struct IFiringControl *)v12;
        if ( v12 )
        {
LABEL_11:
          v10 = EventMethod::FireSubscriptionsThruFilter(this, v7, a2, v13);
          if ( v10 >= 0 )
            v10 = ((__int64 (__fastcall *)(struct IFiringControl *))v13->lpVtbl[1].AddRef)(v13);
          ((void (__fastcall *)(struct IFiringControl *))v13->lpVtbl->Release)(v13);
          return (unsigned int)v10;
        }
LABEL_35:
        InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x52Cu, 0xC0001204, 0x12u);
        goto LABEL_11;
      }
    }
    v13 = 0;
    goto LABEL_35;
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v15 = 0;
    CSemExclusiveES::Lock((EventMethod *)((char *)this + 24));
    if ( !*((_QWORD *)this + 9) )
    {
      v16 = *((_QWORD *)a3 + 2);
      v17 = *((_QWORD *)this + 1);
      v18 = *((_QWORD *)this + 10);
      v24 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(
              v16,
              v18,
              v17,
              0,
              0,
              &v24);
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 72LL))(v24, (char *)this + 72);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 40LL))(*((_QWORD *)this + 9));
  if ( v9 < 0 )
  {
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x554u, 0x12u, v9);
  }
  else if ( v9 == 1 )
  {
    return 262658;
  }
  if ( (v8 & 2) != 0 )
  {
    v23 = (ParallelFiringControl *)CoTaskMemAlloc(0xA0u);
    if ( v23 )
    {
      v20 = ParallelFiringControl::ParallelFiringControl(v23, this, a3, a2);
LABEL_25:
      v21 = v20;
      if ( v20 )
        goto LABEL_26;
      goto LABEL_38;
    }
  }
  else
  {
    v19 = (SerialFiringControl *)CoTaskMemAlloc(0x38u);
    if ( v19 )
    {
      v20 = SerialFiringControl::SerialFiringControl(v19, this, a3, a2);
      goto LABEL_25;
    }
  }
  v21 = 0;
LABEL_38:
  InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x562u, 0xC0001204, 0x12u);
LABEL_26:
  v25 = 0;
  LODWORD(v24) = 0;
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64 *))(**((_QWORD **)this + 9) + 32LL))(
               *((_QWORD *)this + 9),
               1,
               &v25,
               &v24);
    if ( (int)result < 0 )
      break;
    if ( (_DWORD)result == 1 || (_DWORD)v24 != 1 )
    {
      v10 = (*(__int64 (__fastcall **)(SerialFiringControl *))(*(_QWORD *)v21 + 72LL))(v21);
      (*(void (__fastcall **)(SerialFiringControl *))(*(_QWORD *)v21 + 16LL))(v21);
      return (unsigned int)v10;
    }
    (*(void (__fastcall **)(SerialFiringControl *, __int64))(*(_QWORD *)v21 + 56LL))(v21, v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return result;
}

```

## disassembly

```asm
0x18000e6c0  push    rbx
0x18000e6c2  push    rbp
0x18000e6c3  push    rsi
0x18000e6c4  push    rdi
0x18000e6c5  push    r12
0x18000e6c7  push    r14
0x18000e6c9  push    r15
0x18000e6cb  sub     rsp, 40h
0x18000e6cf  mov     rax, [r8+10h]
0x18000e6d3  mov     rsi, r8
0x18000e6d6  mov     r15, rdx
0x18000e6d9  mov     rdi, rcx
0x18000e6dc  mov     rbp, [rax+80h]
0x18000e6e3  movzx   r14d, byte ptr [rax+70h]
0x18000e6e8  test    rbp, rbp
0x18000e6eb  jnz     short loc_18000E727
0x18000e6ed  cmp     [rcx+10h], rbp
0x18000e6f1  jnz     short loc_18000E727
0x18000e6f3  xor     ebx, ebx
0x18000e6f5  cmp     [rcx+48h], rbx
0x18000e6f9  jz      loc_18000E7AA
0x18000e6ff  mov     rcx, [rdi+48h]
0x18000e703  mov     rax, [rcx]
0x18000e706  mov     rax, [rax+28h]
0x18000e70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e70f  test    eax, eax
0x18000e711  js      loc_18000E85C
0x18000e717  cmp     eax, 1
0x18000e71a  jnz     loc_18000E876
0x18000e720  mov     edi, 40202h
0x18000e725  jmp     short loc_18000E799
0x18000e727  test    r14b, 2
0x18000e72b  jz      loc_18000E949
0x18000e731  mov     ecx, 0A0h; cb
0x18000e736  call    cs:__imp_CoTaskMemAlloc
0x18000e73c  test    rax, rax
0x18000e73f  jz      loc_18000E96F
0x18000e745  mov     r9, r15; struct ICallFrame *
0x18000e748  mov     r8, rsi; struct EventInterface *
0x18000e74b  mov     rdx, rdi; struct EventMethod *
0x18000e74e  mov     rcx, rax; this
0x18000e751  call    ??0ParallelFiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z; ParallelFiringControl::ParallelFiringControl(EventMethod &,EventInterface &,ICallFrame *)
0x18000e756  mov     rbx, rax
0x18000e759  test    rax, rax
0x18000e75c  jz      loc_18000E971
0x18000e762  mov     r9, rbx; struct IFiringControl *
0x18000e765  mov     r8, r15; struct ICallFrame *
0x18000e768  mov     rdx, rbp; struct IMultiInterfacePublisherFilter *
0x18000e76b  mov     rcx, rdi; this
0x18000e76e  call    ?FireSubscriptionsThruFilter@EventMethod@@AEAAJPEAUIMultiInterfacePublisherFilter@@PEAUICallFrame@@PEAUIFiringControl@@@Z; EventMethod::FireSubscriptionsThruFilter(IMultiInterfacePublisherFilter *,ICallFrame *,IFiringControl *)
0x18000e773  mov     edi, eax
0x18000e775  test    eax, eax
0x18000e777  js      short loc_18000E78A
0x18000e779  mov     rax, [rbx]
0x18000e77c  mov     rcx, rbx
0x18000e77f  mov     rax, [rax+48h]
0x18000e783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e788  mov     edi, eax
0x18000e78a  mov     rax, [rbx]
0x18000e78d  mov     rcx, rbx
0x18000e790  mov     rax, [rax+10h]
0x18000e794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e799  mov     eax, edi
0x18000e79b  add     rsp, 40h
0x18000e79f  pop     r15
0x18000e7a1  pop     r14
0x18000e7a3  pop     r12
0x18000e7a5  pop     rdi
0x18000e7a6  pop     rsi
0x18000e7a7  pop     rbp
0x18000e7a8  pop     rbx
0x18000e7a9  retn
0x18000e7aa  add     rcx, 18h; this
0x18000e7ae  mov     [rsp+78h+arg_0], r13
0x18000e7b6  mov     r12d, ebx
0x18000e7b9  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000e7be  cmp     [rdi+48h], rbx
0x18000e7c2  jnz     short loc_18000E82F
0x18000e7c4  mov     rcx, [rsi+10h]
0x18000e7c8  lea     rdx, [rsp+78h+arg_10]
0x18000e7d0  mov     r8, [rdi+8]
0x18000e7d4  xor     r9d, r9d
0x18000e7d7  mov     [rsp+78h+var_50], rdx
0x18000e7dc  mov     rdx, [rdi+50h]
0x18000e7e0  mov     [rsp+78h+arg_10], rbx
0x18000e7e8  mov     rax, [rcx]
0x18000e7eb  mov     [rsp+78h+var_58], rbx
0x18000e7f0  mov     rax, [rax+20h]
0x18000e7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f9  mov     r12d, eax
0x18000e7fc  test    eax, eax
0x18000e7fe  js      short loc_18000E82F
0x18000e800  mov     rcx, [rsp+78h+arg_10]
0x18000e808  lea     rdx, [rdi+48h]
0x18000e80c  mov     rax, [rcx]
0x18000e80f  mov     rax, [rax+48h]
0x18000e813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e818  mov     rcx, [rsp+78h+arg_10]
0x18000e820  mov     r12d, eax
0x18000e823  mov     rax, [rcx]
0x18000e826  mov     rax, [rax+10h]
0x18000e82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e82f  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000e833  call    cs:__imp_LeaveCriticalSection
0x18000e839  mov     r13, [rsp+78h+arg_0]
0x18000e841  test    r12d, r12d
0x18000e844  jns     loc_18000E6FF
0x18000e84a  mov     eax, r12d
0x18000e84d  add     rsp, 40h
0x18000e851  pop     r15
0x18000e853  pop     r14
0x18000e855  pop     r12
0x18000e857  pop     rdi
0x18000e858  pop     rsi
0x18000e859  pop     rbp
0x18000e85a  pop     rbx
0x18000e85b  retn
0x18000e85c  mov     r8d, 12h; unsigned __int16
0x18000e862  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000e869  mov     r9d, eax; int
0x18000e86c  mov     edx, 554h; unsigned int
0x18000e871  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000e876  test    r14b, 2
0x18000e87a  jnz     loc_18000E993
0x18000e880  mov     ecx, 38h ; '8'; cb
0x18000e885  call    cs:__imp_CoTaskMemAlloc
0x18000e88b  test    rax, rax
0x18000e88e  jz      loc_18000E9A3
0x18000e894  mov     r9, r15; struct ICallFrame *
0x18000e897  mov     r8, rsi; struct EventInterface *
0x18000e89a  mov     rdx, rdi; struct EventMethod *
0x18000e89d  mov     rcx, rax; this
0x18000e8a0  call    ??0SerialFiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z; SerialFiringControl::SerialFiringControl(EventMethod &,EventInterface &,ICallFrame *)
0x18000e8a5  mov     rsi, rax
0x18000e8a8  test    rax, rax
0x18000e8ab  jz      loc_18000E9A6
0x18000e8b1  mov     [rsp+78h+arg_18], rbx
0x18000e8b9  mov     dword ptr [rsp+78h+arg_10], ebx
0x18000e8c0  mov     rcx, [rdi+48h]
0x18000e8c4  lea     r9, [rsp+78h+arg_10]
0x18000e8cc  lea     r8, [rsp+78h+arg_18]
0x18000e8d4  mov     edx, 1
0x18000e8d9  mov     rax, [rcx]
0x18000e8dc  mov     rax, [rax+20h]
0x18000e8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8e5  test    eax, eax
0x18000e8e7  js      loc_18000E79B
0x18000e8ed  cmp     eax, 1
0x18000e8f0  jz      short loc_18000E929
0x18000e8f2  cmp     dword ptr [rsp+78h+arg_10], 1
0x18000e8fa  jnz     short loc_18000E929
0x18000e8fc  mov     rax, [rsi]
0x18000e8ff  mov     rcx, rsi
0x18000e902  mov     rdx, [rsp+78h+arg_18]
0x18000e90a  mov     rax, [rax+38h]
0x18000e90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e913  mov     rcx, [rsp+78h+arg_18]
0x18000e91b  mov     rax, [rcx]
0x18000e91e  mov     rax, [rax+10h]
0x18000e922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e927  jmp     short loc_18000E8C0
0x18000e929  mov     rax, [rsi]
0x18000e92c  mov     rcx, rsi
0x18000e92f  mov     rax, [rax+48h]
0x18000e933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e938  mov     rcx, [rsi]
0x18000e93b  mov     edi, eax
0x18000e93d  mov     rax, [rcx+10h]
0x18000e941  mov     rcx, rsi
0x18000e944  jmp     loc_18000E794
0x18000e949  mov     ecx, 38h ; '8'; cb
0x18000e94e  call    cs:__imp_CoTaskMemAlloc
0x18000e954  test    rax, rax
0x18000e957  jz      short loc_18000E96F
0x18000e959  mov     r9, r15; struct ICallFrame *
0x18000e95c  mov     r8, rsi; struct EventInterface *
0x18000e95f  mov     rdx, rdi; struct EventMethod *
0x18000e962  mov     rcx, rax; this
0x18000e965  call    ??0SerialFiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z; SerialFiringControl::SerialFiringControl(EventMethod &,EventInterface &,ICallFrame *)
0x18000e96a  jmp     loc_18000E756
0x18000e96f  xor     ebx, ebx
0x18000e971  mov     edx, 52Ch; unsigned int
0x18000e976  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000e97d  mov     r9d, 12h; unsigned __int16
0x18000e983  mov     r8d, 0C0001204h; unsigned int
0x18000e989  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000e98e  jmp     loc_18000E762
0x18000e993  mov     ecx, 0A0h; cb
0x18000e998  call    cs:__imp_CoTaskMemAlloc
0x18000e99e  test    rax, rax
0x18000e9a1  jnz     short loc_18000E9C8
0x18000e9a3  mov     rsi, rbx
0x18000e9a6  mov     edx, 562h; unsigned int
0x18000e9ab  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000e9b2  mov     r9d, 12h; unsigned __int16
0x18000e9b8  mov     r8d, 0C0001204h; unsigned int
0x18000e9be  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000e9c3  jmp     loc_18000E8B1
0x18000e9c8  mov     r9, r15; struct ICallFrame *
0x18000e9cb  mov     r8, rsi; struct EventInterface *
0x18000e9ce  mov     rdx, rdi; struct EventMethod *
0x18000e9d1  mov     rcx, rax; this
0x18000e9d4  call    ??0ParallelFiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z; ParallelFiringControl::ParallelFiringControl(EventMethod &,EventInterface &,ICallFrame *)
0x18000e9d9  jmp     loc_18000E8A5
```

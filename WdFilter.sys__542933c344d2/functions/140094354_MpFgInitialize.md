# MpFgInitialize

- ea: `0x140094354`
- end: `0x140094507`
- name: `MpFgInitialize`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x140094354`

## import_xrefs

- `ntoskrnl!KeInitializeTimerEx` at `0x1400944a4`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400944a4`
- `ntoskrnl!KeInitializeDpc` at `0x1400944c5`
- `ntoskrnl!KeInitializeDpc` at `0x1400944c5`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009441b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009441b`
- `ntoskrnl!KeInitializeEvent` at `0x140094453`
- `ntoskrnl!KeInitializeEvent` at `0x140094453`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009448b`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009448b`

## pseudocode

```c
__int64 MpFgInitialize()
{
  unsigned int v0; // ebx
  _DWORD *PoolWithTag; // rax
  char *v3; // rcx
  _DWORD *v4; // r8

  v0 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 8) == 0 )
    return 0;
  PoolWithTag = (_DWORD *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 576, 1732661325);
  DeferredContext = PoolWithTag;
  if ( PoolWithTag )
  {
    *PoolWithTag = 37804571;
    *((_QWORD *)PoolWithTag + 1) = 0;
    *((_QWORD *)PoolWithTag + 33) = 0;
    *((_BYTE *)PoolWithTag + 512) = 0;
    *((_BYTE *)PoolWithTag + 248) = 0;
    *((_BYTE *)PoolWithTag + 513) = 0;
    ExInitializeResourceLite((PERESOURCE)(PoolWithTag + 4));
    v3 = (char *)DeferredContext;
    *((_DWORD *)DeferredContext + 68) = 1;
    *((_QWORD *)v3 + 35) = 0;
    *((_DWORD *)v3 + 72) = 0;
    KeInitializeEvent((PRKEVENT)(v3 + 296), SynchronizationEvent, 0);
    ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)DeferredContext + 3, 0, 0, 0, 0x68u, 0x6146504Du, 0);
    KeInitializeTimerEx((PKTIMER)((char *)DeferredContext + 120), NotificationTimer);
    KeInitializeDpc((PRKDPC)((char *)DeferredContext + 184), MpFgEventTimerDpc, DeferredContext);
    v4 = DeferredContext;
    *((_QWORD *)DeferredContext + 32) = -10000LL * (unsigned int)dword_140026A0C;
    v4[63] = dword_140026A10;
  }
  else
  {
    v0 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
  }
  return v0;
}

```

## disassembly

```asm
0x140094354  mov     [rsp+arg_0], rbx
0x140094359  push    rdi
0x14009435a  sub     rsp, 40h
0x14009435e  mov     rax, cs:MpData
0x140094365  xor     ebx, ebx
0x140094367  mov     ecx, [rax+360h]
0x14009436d  test    cl, 8
0x140094370  jnz     short loc_140094379
0x140094372  xor     eax, eax
0x140094374  jmp     loc_1400944FB
0x140094379  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14009437f  mov     edx, 240h
0x140094384  mov     r8d, 6746504Dh
0x14009438a  call    MpAllocatePoolWithTag
0x14009438f  mov     cs:DeferredContext, rax
0x140094396  test    rax, rax
0x140094399  jnz     short loc_1400943F4
0x14009439b  mov     ebx, 0C000009Ah
0x1400943a0  mov     rax, cs:WPP_GLOBAL_Control
0x1400943a7  lea     rcx, WPP_GLOBAL_Control
0x1400943ae  cmp     rax, rcx
0x1400943b1  jz      loc_1400944F9
0x1400943b7  mov     eax, [rax+2Ch]
0x1400943ba  test    al, 1
0x1400943bc  jz      loc_1400944F9
0x1400943c2  mov     r9, gs:188h
0x1400943cb  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x1400943d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400943d9  mov     edx, 0Ah
0x1400943de  mov     dword ptr [rsp+48h+Size], 0C000009Ah
0x1400943e6  mov     rcx, [rcx+18h]
0x1400943ea  call    WPP_SF_qD
0x1400943ef  jmp     loc_1400944F9
0x1400943f4  mov     dword ptr [rax], 240DA1Bh
0x1400943fa  lea     rcx, [rax+10h]; Resource
0x1400943fe  mov     [rax+8], rbx
0x140094402  mov     [rax+108h], rbx
0x140094409  mov     [rax+200h], bl
0x14009440f  mov     [rax+0F8h], bl
0x140094415  mov     [rax+201h], bl
0x14009441b  call    cs:__imp_ExInitializeResourceLite
0x140094422  nop     dword ptr [rax+rax+00h]
0x140094427  mov     rcx, cs:DeferredContext
0x14009442e  xor     r8d, r8d; State
0x140094431  mov     dword ptr [rcx+110h], 1
0x14009443b  lea     edx, [r8+1]; Type
0x14009443f  mov     [rcx+118h], rbx
0x140094446  mov     [rcx+120h], ebx
0x14009444c  add     rcx, 128h; Event
0x140094453  call    cs:__imp_KeInitializeEvent
0x14009445a  nop     dword ptr [rax+rax+00h]
0x14009445f  mov     rcx, cs:DeferredContext
0x140094466  xor     r9d, r9d; Flags
0x140094469  mov     [rsp+48h+Depth], bx; Depth
0x14009446e  add     rcx, 180h; Lookaside
0x140094475  mov     [rsp+48h+Tag], 6146504Dh; Tag
0x14009447d  xor     r8d, r8d; Free
0x140094480  xor     edx, edx; Allocate
0x140094482  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x14009448b  call    cs:__imp_ExInitializePagedLookasideList
0x140094492  nop     dword ptr [rax+rax+00h]
0x140094497  mov     rcx, cs:DeferredContext
0x14009449e  xor     edx, edx; Type
0x1400944a0  add     rcx, 78h ; 'x'; Timer
0x1400944a4  call    cs:__imp_KeInitializeTimerEx
0x1400944ab  nop     dword ptr [rax+rax+00h]
0x1400944b0  mov     r8, cs:DeferredContext; DeferredContext
0x1400944b7  lea     rdx, MpFgEventTimerDpc; DeferredRoutine
0x1400944be  lea     rcx, [r8+0B8h]; Dpc
0x1400944c5  call    cs:__imp_KeInitializeDpc
0x1400944cc  nop     dword ptr [rax+rax+00h]
0x1400944d1  mov     ecx, cs:dword_140026A0C
0x1400944d7  mov     r8, cs:DeferredContext
0x1400944de  imul    rdx, rcx, 0FFFFFFFFFFFFD8F0h
0x1400944e5  mov     [r8+100h], rdx
0x1400944ec  mov     ecx, cs:dword_140026A10
0x1400944f2  mov     [r8+0FCh], ecx
0x1400944f9  mov     eax, ebx
0x1400944fb  mov     rbx, [rsp+48h+arg_0]
0x140094500  add     rsp, 40h
0x140094504  pop     rdi
0x140094505  retn
```

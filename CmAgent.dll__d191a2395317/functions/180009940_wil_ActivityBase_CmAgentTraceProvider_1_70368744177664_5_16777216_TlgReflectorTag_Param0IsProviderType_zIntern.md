# wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)

- ea: `0x180009940`
- end: `0x1800099cd`
- name: `?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `15`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008648`
- `0x18000877c`
- `0x18001bb20`
- `0x18001bc8c`
- `0x18001bdc0`
- `0x18001bfb4`
- `0x18001c0e8`
- `0x18001c21c`
- `0x18001c350`
- `0x18001c50c`
- `0x18001c640`
- `0x18001c774`
- `0x18001c8a8`
- `0x18001c9dc`
- `0x180022f5c`

## callees

- `0x180006fcc`
- `0x180007088`
- `0x180009940`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009995`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800099ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800099ba`

## pseudocode

```c
void __fastcall wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  RTL_SRWLOCK *v4; // rcx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v3 > 5u
    && (*(_QWORD *)(v3 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v3 + 24) & 0x400000000000LL) == *(_QWORD *)(v3 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  v4 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x180009940  push    rbx
0x180009942  sub     rsp, 20h
0x180009946  lea     rdx, [rsp+28h+SRWLock]
0x18000994b  mov     rbx, rcx
0x18000994e  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180009953  mov     rbx, [rbx+110h]
0x18000995a  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18000995f  mov     rdx, [rax+8]
0x180009963  mov     eax, [rdx]
0x180009965  cmp     eax, 5
0x180009968  jbe     short loc_1800099A3
0x18000996a  mov     rcx, [rdx+18h]
0x18000996e  mov     rax, [rdx+10h]
0x180009972  mov     rdx, 400000000000h
0x18000997c  test    rdx, rax
0x18000997f  jz      short loc_1800099A3
0x180009981  mov     rax, rcx
0x180009984  and     rax, rdx
0x180009987  cmp     rax, rcx
0x18000998a  jnz     short loc_1800099A3
0x18000998c  lea     rdx, [rbx+8]; ActivityId
0x180009990  mov     ecx, 3; ControlCode
0x180009995  call    cs:__imp_EventActivityIdControl
0x18000999c  nop     dword ptr [rax+rax+00h]
0x1800099a1  jmp     short loc_1800099AA
0x1800099a3  xorps   xmm0, xmm0
0x1800099a6  movups  xmmword ptr [rbx+8], xmm0
0x1800099aa  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x1800099af  mov     dword ptr [rbx], 1
0x1800099b5  test    rcx, rcx
0x1800099b8  jz      short loc_1800099C6
0x1800099ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800099c1  nop     dword ptr [rax+rax+00h]
0x1800099c6  add     rsp, 20h
0x1800099ca  pop     rbx
0x1800099cb  retn
```

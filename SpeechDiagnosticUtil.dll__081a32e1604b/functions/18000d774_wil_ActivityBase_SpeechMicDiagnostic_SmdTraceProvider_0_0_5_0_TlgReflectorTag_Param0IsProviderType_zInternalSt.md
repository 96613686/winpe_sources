# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)

- ea: `0x18000d774`
- end: `0x18000d7df`
- name: `?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `107`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009df0`
- `0x180009f44`
- `0x18000a098`
- `0x18000a1ec`
- `0x18000a340`
- `0x18000a494`
- `0x18000a5d4`
- `0x18000a714`
- `0x18000a868`

## callees

- `0x1800068cc`
- `0x180008c58`
- `0x18000d774`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d7cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d7cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d7a7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d7a7`

## pseudocode

```c
void __fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rbx
  RTL_SRWLOCK *v3; // rcx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  if ( **((_DWORD **)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1) <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  v3 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
}

```

## disassembly

```asm
0x18000d774  push    rbx
0x18000d776  sub     rsp, 20h
0x18000d77a  lea     rdx, [rsp+28h+SRWLock]
0x18000d77f  mov     rbx, rcx
0x18000d782  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d787  mov     rbx, [rbx+110h]
0x18000d78e  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000d793  mov     rcx, [rax+8]
0x18000d797  mov     eax, [rcx]
0x18000d799  cmp     eax, 5
0x18000d79c  jbe     short loc_18000D7B5
0x18000d79e  lea     rdx, [rbx+8]; ActivityId
0x18000d7a2  mov     ecx, 3; ControlCode
0x18000d7a7  call    cs:__imp_EventActivityIdControl
0x18000d7ae  nop     dword ptr [rax+rax+00h]
0x18000d7b3  jmp     short loc_18000D7BC
0x18000d7b5  xorps   xmm0, xmm0
0x18000d7b8  movups  xmmword ptr [rbx+8], xmm0
0x18000d7bc  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000d7c1  mov     dword ptr [rbx], 1
0x18000d7c7  test    rcx, rcx
0x18000d7ca  jz      short loc_18000D7D8
0x18000d7cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d7d3  nop     dword ptr [rax+rax+00h]
0x18000d7d8  add     rsp, 20h
0x18000d7dc  pop     rbx
0x18000d7dd  retn
```

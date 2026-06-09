# UbpmpCloseTriggerConsumer

- ea: `0x180012950`
- end: `0x180012b14`
- name: `UbpmpCloseTriggerConsumer`
- size: `452`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011640`
- `0x1800119a0`
- `0x180011a90`
- `0x1800136b0`
- `0x18002fde0`
- `0x180038380`
- `0x180038814`

## callees

- `0x1800017a4`
- `0x180001824`
- `0x180010400`
- `0x180012950`
- `0x18001af64`
- `0x180037a10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180012a5f`
- `ntdll!RtlFreeHeap` at `0x180012a83`
- `ntdll!RtlFreeHeap` at `0x180012a5f`
- `ntdll!RtlFreeHeap` at `0x180012a83`
- `ntdll!RtlFreeHeap` at `0x180012aa9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012960`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012960`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800129e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800129be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800129e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001296c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001296c`

## pseudocode

```c
BOOLEAN __fastcall UbpmpCloseTriggerConsumer(__int64 a1)
{
  signed __int64 v2; // rdi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  void *v7; // r8
  void *v8; // r8

  RtlAcquireSRWLockExclusive(a1 + 48);
  *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
  v2 = _InterlockedDecrement64((volatile signed __int64 *)(a1 + 64));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Siq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      v2,
      a1);
  if ( v2 || !(unsigned __int8)UbpmConsumerIsUnregistered(a1) )
  {
    *(_DWORD *)(a1 + 56) = 0;
    return RtlReleaseSRWLockExclusive(a1 + 48);
  }
  else
  {
    *(_BYTE *)(a1 + 104) = 1;
    *(_DWORD *)(a1 + 56) = 0;
    RtlReleaseSRWLockExclusive(a1 + 48);
    UbpmpAcquireListLockExclusive();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        g_cTotalConsumers);
    v4 = *(_QWORD *)(a1 + 8);
    v5 = (_QWORD *)(a1 + 8);
    if ( v4 != a1 + 8 )
    {
      if ( *(_QWORD **)(v4 + 8) != v5 || (v6 = *(_QWORD **)(a1 + 16), (_QWORD *)*v6 != v5) )
        __fastfail(3u);
      --g_cTotalConsumers;
      *v6 = v4;
      *(_QWORD *)(v4 + 8) = v6;
      *(_QWORD *)(a1 + 16) = a1 + 8;
      *v5 = v5;
    }
    UbpmpReleaseListLockExclusive(v4);
    v7 = *(void **)(a1 + 32);
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v8 = *(void **)(a1 + 24);
    if ( v8 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
  }
}

```

## disassembly

```asm
0x180012950  push    rbx
0x180012952  push    rbp
0x180012953  push    rsi
0x180012954  push    rdi
0x180012955  sub     rsp, 38h
0x180012959  mov     rsi, rcx
0x18001295c  add     rcx, 30h ; '0'
0x180012960  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012967  nop     dword ptr [rax+rax+00h]
0x18001296c  call    cs:__imp_GetCurrentThreadId
0x180012973  nop     dword ptr [rax+rax+00h]
0x180012978  mov     [rsi+38h], eax
0x18001297b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180012982  lock xadd [rsi+40h], rdi
0x180012988  dec     rdi
0x18001298b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012992  lea     rbp, WPP_GLOBAL_Control
0x180012999  cmp     rcx, rbp
0x18001299c  jz      short loc_1800129A8
0x18001299e  test    byte ptr [rcx+1Ch], 8
0x1800129a2  jnz     loc_180012ABC
0x1800129a8  test    rdi, rdi
0x1800129ab  jz      short loc_1800129CA
0x1800129ad  xor     eax, eax
0x1800129af  lea     rcx, [rsi+30h]
0x1800129b3  mov     [rsi+38h], eax
0x1800129b6  add     rsp, 38h
0x1800129ba  pop     rdi
0x1800129bb  pop     rsi
0x1800129bc  pop     rbp
0x1800129bd  pop     rbx
0x1800129be  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x1800129ca  mov     rcx, rsi
0x1800129cd  call    UbpmConsumerIsUnregistered
0x1800129d2  test    al, al
0x1800129d4  jz      short loc_1800129AD
0x1800129d6  xor     eax, eax
0x1800129d8  mov     byte ptr [rsi+68h], 1
0x1800129dc  lea     rcx, [rsi+30h]
0x1800129e0  mov     [rsi+38h], eax
0x1800129e3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800129ea  nop     dword ptr [rax+rax+00h]
0x1800129ef  call    UbpmpAcquireListLockExclusive
0x1800129f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129fb  cmp     rcx, rbp
0x1800129fe  jz      short loc_180012A0A
0x180012a00  test    byte ptr [rcx+1Ch], 4
0x180012a04  jnz     loc_180012AE8
0x180012a0a  mov     rcx, [rsi+8]
0x180012a0e  lea     rax, [rsi+8]
0x180012a12  cmp     rcx, rax
0x180012a15  jz      short loc_180012A42
0x180012a17  cmp     [rcx+8], rax
0x180012a1b  jnz     loc_180012AB5
0x180012a21  mov     rdx, [rax+8]
0x180012a25  cmp     [rdx], rax
0x180012a28  jnz     loc_180012AB5
0x180012a2e  dec     cs:g_cTotalConsumers
0x180012a34  mov     [rdx], rcx
0x180012a37  mov     [rcx+8], rdx
0x180012a3b  mov     [rax+8], rax
0x180012a3f  mov     [rax], rax
0x180012a42  call    UbpmpReleaseListLockExclusive
0x180012a47  mov     r8, [rsi+20h]; P
0x180012a4b  test    r8, r8
0x180012a4e  jz      short loc_180012A6B
0x180012a50  mov     rcx, gs:60h
0x180012a59  xor     edx, edx; Flags
0x180012a5b  mov     rcx, [rcx+30h]; HeapHandle
0x180012a5f  call    cs:__imp_RtlFreeHeap
0x180012a66  nop     dword ptr [rax+rax+00h]
0x180012a6b  mov     r8, [rsi+18h]; P
0x180012a6f  test    r8, r8
0x180012a72  jz      short loc_180012A8F
0x180012a74  mov     rcx, gs:60h
0x180012a7d  xor     edx, edx; Flags
0x180012a7f  mov     rcx, [rcx+30h]; HeapHandle
0x180012a83  call    cs:__imp_RtlFreeHeap
0x180012a8a  nop     dword ptr [rax+rax+00h]
0x180012a8f  mov     rcx, gs:60h
0x180012a98  mov     r8, rsi
0x180012a9b  xor     edx, edx
0x180012a9d  mov     rcx, [rcx+30h]
0x180012aa1  add     rsp, 38h
0x180012aa5  pop     rdi
0x180012aa6  pop     rsi
0x180012aa7  pop     rbp
0x180012aa8  pop     rbx
0x180012aa9  jmp     cs:__imp_RtlFreeHeap
0x180012ab5  mov     ecx, 3
0x180012aba  int     29h; Win8: RtlFailFast(ecx)
0x180012abc  mov     r9, [rsi+18h]
0x180012ac0  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180012ac7  mov     rcx, [rcx+10h]
0x180012acb  mov     edx, 7Ah ; 'z'
0x180012ad0  mov     [rsp+58h+var_30], rsi
0x180012ad5  mov     [rsp+58h+var_38], rdi
0x180012ada  mov     r9, [r9+8]
0x180012ade  call    WPP_SF_Siq
0x180012ae3  jmp     loc_1800129A8
0x180012ae8  mov     r9, [rsi+18h]
0x180012aec  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180012af3  mov     eax, cs:g_cTotalConsumers
0x180012af9  mov     edx, 7Bh ; '{'
0x180012afe  mov     rcx, [rcx+10h]
0x180012b02  mov     dword ptr [rsp+58h+var_38], eax
0x180012b06  mov     r9, [r9+8]
0x180012b0a  call    WPP_SF_Sd
0x180012b0f  jmp     loc_180012A0A
```

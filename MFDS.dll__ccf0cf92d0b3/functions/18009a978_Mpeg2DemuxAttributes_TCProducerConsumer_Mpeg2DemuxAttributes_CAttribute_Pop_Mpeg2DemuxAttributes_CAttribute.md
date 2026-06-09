# Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::Pop(Mpeg2DemuxAttributes::CAttribute * *)

- ea: `0x18009a978`
- end: `0x18009aaf4`
- name: `?Pop@?$TCProducerConsumer@PEAVCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@QEAAKPEAPEAVCAttribute@2@@Z`
- size: `380`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001f750`
- `0x18001fca0`
- `0x180020880`
- `0x1800209b0`

## callees

- `0x180022018`
- `0x180022110`
- `0x18002d6c0`
- `0x180073d0c`
- `0x180073d4c`
- `0x18009a978`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009aa15`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009aa15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009aa53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009aa53`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a9e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aa41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aad8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aa41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009aad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aa87`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::Pop(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  HANDLE *v6; // rax
  HANDLE *v7; // rdi
  HANDLE EventW; // rax
  unsigned int v9; // esi
  _QWORD *OwningThread; // rax
  _QWORD *v11; // r14
  _QWORD *v12; // rax

  *a2 = 0;
  EnterCriticalSection(lpCriticalSection);
  v4 = (_QWORD *)Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::ContainerAvailPop_(lpCriticalSection);
  if ( v4 )
  {
    *a2 = *v4;
    Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::ContainerPoolPush_(v5, v4);
    v9 = 0;
    goto LABEL_18;
  }
  if ( !LODWORD(lpCriticalSection[2].LockSemaphore) )
    goto LABEL_8;
  v6 = (HANDLE *)Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::RequestPoolPop_(v5, 0);
  v7 = v6;
  if ( v6 )
  {
    ResetEvent(*v6);
  }
  else
  {
    v7 = (HANDLE *)operator new(0x28u);
    if ( v7 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *v7 = EventW;
      if ( !EventW )
      {
        operator delete(v7);
        v7 = 0;
      }
    }
    if ( !v7 )
    {
LABEL_8:
      v9 = 31;
      goto LABEL_18;
    }
  }
  OwningThread = lpCriticalSection[2].OwningThread;
  v11 = v7 + 3;
  v7[3] = &lpCriticalSection[2].LockCount;
  v7[4] = OwningThread;
  *OwningThread = v7 + 3;
  ++HIDWORD(lpCriticalSection[2].LockSemaphore);
  lpCriticalSection[2].OwningThread = v7 + 3;
  LeaveCriticalSection(lpCriticalSection);
  if ( WaitForSingleObject(*v7, 0xFFFFFFFF) )
  {
    v9 = 31;
    EnterCriticalSection(lpCriticalSection);
  }
  else
  {
    EnterCriticalSection(lpCriticalSection);
    v9 = *((_DWORD *)v7 + 2);
    if ( !v9 )
      *a2 = v7[2];
  }
  if ( lpCriticalSection[3].LockCount >= SHIDWORD(lpCriticalSection[3].DebugInfo) )
  {
    operator delete(v7);
  }
  else
  {
    v12 = lpCriticalSection[1].OwningThread;
    *v11 = v12;
    v7[4] = &lpCriticalSection[1].OwningThread;
    v12[1] = v11;
    ++lpCriticalSection[3].LockCount;
    lpCriticalSection[1].OwningThread = v11;
  }
LABEL_18:
  LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x18009a978  push    rbx
0x18009a97a  push    rbp
0x18009a97b  push    rsi
0x18009a97c  push    rdi
0x18009a97d  push    r14
0x18009a97f  push    r15
0x18009a981  sub     rsp, 28h
0x18009a985  mov     r15, rdx
0x18009a988  mov     qword ptr [rdx], 0
0x18009a98f  mov     rbx, rcx
0x18009a992  call    cs:__imp_EnterCriticalSection
0x18009a999  nop     dword ptr [rax+rax+00h]
0x18009a99e  mov     rcx, rbx
0x18009a9a1  call    ?ContainerAvailPop_@?$TCProducerConsumer@PEAVCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAPEAUOBJ_CONTAINER@12@XZ; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::ContainerAvailPop_(void)
0x18009a9a6  mov     rdx, rax
0x18009a9a9  test    rax, rax
0x18009a9ac  jnz     loc_18009AAC8
0x18009a9b2  cmp     [rbx+68h], eax
0x18009a9b5  jz      short loc_18009AA08
0x18009a9b7  call    ?RequestPoolPop_@?$TCProducerConsumer@PEAVCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAPEAUOBJ_REQUEST@12@XZ; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::RequestPoolPop_(void)
0x18009a9bc  mov     rdi, rax
0x18009a9bf  mov     ebp, 28h ; '('
0x18009a9c4  test    rax, rax
0x18009a9c7  jnz     short loc_18009AA12
0x18009a9c9  mov     ecx, ebp; Size
0x18009a9cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009a9d0  mov     rdi, rax
0x18009a9d3  test    rax, rax
0x18009a9d6  jz      short loc_18009AA03
0x18009a9d8  xor     r9d, r9d; lpName
0x18009a9db  lea     edx, [rbp-27h]; bManualReset
0x18009a9de  xor     r8d, r8d; bInitialState
0x18009a9e1  xor     ecx, ecx; lpEventAttributes
0x18009a9e3  call    cs:__imp_CreateEventW
0x18009a9ea  nop     dword ptr [rax+rax+00h]
0x18009a9ef  mov     [rdi], rax
0x18009a9f2  test    rax, rax
0x18009a9f5  jnz     short loc_18009AA03
0x18009a9f7  mov     edx, ebp
0x18009a9f9  mov     rcx, rdi; Block
0x18009a9fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009aa01  xor     edi, edi
0x18009aa03  test    rdi, rdi
0x18009aa06  jnz     short loc_18009AA21
0x18009aa08  mov     esi, 1Fh
0x18009aa0d  jmp     loc_18009AAD5
0x18009aa12  mov     rcx, [rax]; hEvent
0x18009aa15  call    cs:__imp_ResetEvent
0x18009aa1c  nop     dword ptr [rax+rax+00h]
0x18009aa21  lea     rcx, [rbx+58h]
0x18009aa25  mov     rax, [rcx+8]
0x18009aa29  lea     r14, [rdi+18h]
0x18009aa2d  mov     [r14], rcx
0x18009aa30  mov     [rdi+20h], rax
0x18009aa34  mov     [rax], r14
0x18009aa37  inc     dword ptr [rbx+6Ch]
0x18009aa3a  mov     [rcx+8], r14
0x18009aa3e  mov     rcx, rbx; lpCriticalSection
0x18009aa41  call    cs:__imp_LeaveCriticalSection
0x18009aa48  nop     dword ptr [rax+rax+00h]
0x18009aa4d  mov     rcx, [rdi]; hHandle
0x18009aa50  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009aa53  call    cs:__imp_WaitForSingleObject
0x18009aa5a  nop     dword ptr [rax+rax+00h]
0x18009aa5f  mov     rcx, rbx; lpCriticalSection
0x18009aa62  test    eax, eax
0x18009aa64  jnz     short loc_18009AA82
0x18009aa66  call    cs:__imp_EnterCriticalSection
0x18009aa6d  nop     dword ptr [rax+rax+00h]
0x18009aa72  mov     esi, [rdi+8]
0x18009aa75  test    esi, esi
0x18009aa77  jnz     short loc_18009AA93
0x18009aa79  mov     rax, [rdi+10h]
0x18009aa7d  mov     [r15], rax
0x18009aa80  jmp     short loc_18009AA93
0x18009aa82  mov     esi, 1Fh
0x18009aa87  call    cs:__imp_EnterCriticalSection
0x18009aa8e  nop     dword ptr [rax+rax+00h]
0x18009aa93  mov     eax, [rbx+7Ch]
0x18009aa96  cmp     [rbx+80h], eax
0x18009aa9c  jge     short loc_18009AABB
0x18009aa9e  lea     rcx, [rbx+38h]
0x18009aaa2  mov     rax, [rcx]
0x18009aaa5  mov     [r14], rax
0x18009aaa8  mov     [rdi+20h], rcx
0x18009aaac  mov     [rax+8], r14
0x18009aab0  inc     dword ptr [rbx+80h]
0x18009aab6  mov     [rcx], r14
0x18009aab9  jmp     short loc_18009AAD5
0x18009aabb  mov     rdx, rbp
0x18009aabe  mov     rcx, rdi; Block
0x18009aac1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009aac6  jmp     short loc_18009AAD5
0x18009aac8  mov     rax, [rax]
0x18009aacb  mov     [r15], rax
0x18009aace  call    ?ContainerPoolPush_@?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAXPEAUOBJ_CONTAINER@12@@Z; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::ContainerPoolPush_(Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::OBJ_CONTAINER *)
0x18009aad3  xor     esi, esi
0x18009aad5  mov     rcx, rbx; lpCriticalSection
0x18009aad8  call    cs:__imp_LeaveCriticalSection
0x18009aadf  nop     dword ptr [rax+rax+00h]
0x18009aae4  mov     eax, esi
0x18009aae6  add     rsp, 28h
0x18009aaea  pop     r15
0x18009aaec  pop     r14
0x18009aaee  pop     rdi
0x18009aaef  pop     rsi
0x18009aaf0  pop     rbp
0x18009aaf1  pop     rbx
0x18009aaf2  retn
```

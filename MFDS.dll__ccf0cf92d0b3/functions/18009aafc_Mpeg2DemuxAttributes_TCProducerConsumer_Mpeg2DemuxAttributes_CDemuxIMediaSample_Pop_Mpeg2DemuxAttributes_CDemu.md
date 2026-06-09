# Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::Pop(Mpeg2DemuxAttributes::CDemuxIMediaSample * *)

- ea: `0x18009aafc`
- end: `0x18009ac78`
- name: `?Pop@?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@QEAAKPEAPEAVCDemuxIMediaSample@2@@Z`
- size: `380`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800107b0`
- `0x180010b8c`
- `0x1800141a0`

## callees

- `0x180022018`
- `0x18002d6c0`
- `0x1800363bc`
- `0x180073d0c`
- `0x180073d4c`
- `0x18009aafc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009ab99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009ab99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009abd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009abd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009ab67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009ab67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009abc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ac5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009abc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ac5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ab16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009abea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ac0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ab16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009abea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ac0b`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::Pop(
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
  v6 = (HANDLE *)Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::RequestPoolPop_(
                   v5,
                   0);
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
0x18009aafc  push    rbx
0x18009aafe  push    rbp
0x18009aaff  push    rsi
0x18009ab00  push    rdi
0x18009ab01  push    r14
0x18009ab03  push    r15
0x18009ab05  sub     rsp, 28h
0x18009ab09  mov     r15, rdx
0x18009ab0c  mov     qword ptr [rdx], 0
0x18009ab13  mov     rbx, rcx
0x18009ab16  call    cs:__imp_EnterCriticalSection
0x18009ab1d  nop     dword ptr [rax+rax+00h]
0x18009ab22  mov     rcx, rbx
0x18009ab25  call    ?ContainerAvailPop_@?$TCProducerConsumer@PEAVCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAPEAUOBJ_CONTAINER@12@XZ; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CAttribute *>::ContainerAvailPop_(void)
0x18009ab2a  mov     rdx, rax
0x18009ab2d  test    rax, rax
0x18009ab30  jnz     loc_18009AC4C
0x18009ab36  cmp     [rbx+68h], eax
0x18009ab39  jz      short loc_18009AB8C
0x18009ab3b  call    ?RequestPoolPop_@?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAPEAUOBJ_REQUEST@12@XZ; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::RequestPoolPop_(void)
0x18009ab40  mov     rdi, rax
0x18009ab43  mov     ebp, 28h ; '('
0x18009ab48  test    rax, rax
0x18009ab4b  jnz     short loc_18009AB96
0x18009ab4d  mov     ecx, ebp; Size
0x18009ab4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009ab54  mov     rdi, rax
0x18009ab57  test    rax, rax
0x18009ab5a  jz      short loc_18009AB87
0x18009ab5c  xor     r9d, r9d; lpName
0x18009ab5f  lea     edx, [rbp-27h]; bManualReset
0x18009ab62  xor     r8d, r8d; bInitialState
0x18009ab65  xor     ecx, ecx; lpEventAttributes
0x18009ab67  call    cs:__imp_CreateEventW
0x18009ab6e  nop     dword ptr [rax+rax+00h]
0x18009ab73  mov     [rdi], rax
0x18009ab76  test    rax, rax
0x18009ab79  jnz     short loc_18009AB87
0x18009ab7b  mov     edx, ebp
0x18009ab7d  mov     rcx, rdi; Block
0x18009ab80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009ab85  xor     edi, edi
0x18009ab87  test    rdi, rdi
0x18009ab8a  jnz     short loc_18009ABA5
0x18009ab8c  mov     esi, 1Fh
0x18009ab91  jmp     loc_18009AC59
0x18009ab96  mov     rcx, [rax]; hEvent
0x18009ab99  call    cs:__imp_ResetEvent
0x18009aba0  nop     dword ptr [rax+rax+00h]
0x18009aba5  lea     rcx, [rbx+58h]
0x18009aba9  mov     rax, [rcx+8]
0x18009abad  lea     r14, [rdi+18h]
0x18009abb1  mov     [r14], rcx
0x18009abb4  mov     [rdi+20h], rax
0x18009abb8  mov     [rax], r14
0x18009abbb  inc     dword ptr [rbx+6Ch]
0x18009abbe  mov     [rcx+8], r14
0x18009abc2  mov     rcx, rbx; lpCriticalSection
0x18009abc5  call    cs:__imp_LeaveCriticalSection
0x18009abcc  nop     dword ptr [rax+rax+00h]
0x18009abd1  mov     rcx, [rdi]; hHandle
0x18009abd4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009abd7  call    cs:__imp_WaitForSingleObject
0x18009abde  nop     dword ptr [rax+rax+00h]
0x18009abe3  mov     rcx, rbx; lpCriticalSection
0x18009abe6  test    eax, eax
0x18009abe8  jnz     short loc_18009AC06
0x18009abea  call    cs:__imp_EnterCriticalSection
0x18009abf1  nop     dword ptr [rax+rax+00h]
0x18009abf6  mov     esi, [rdi+8]
0x18009abf9  test    esi, esi
0x18009abfb  jnz     short loc_18009AC17
0x18009abfd  mov     rax, [rdi+10h]
0x18009ac01  mov     [r15], rax
0x18009ac04  jmp     short loc_18009AC17
0x18009ac06  mov     esi, 1Fh
0x18009ac0b  call    cs:__imp_EnterCriticalSection
0x18009ac12  nop     dword ptr [rax+rax+00h]
0x18009ac17  mov     eax, [rbx+7Ch]
0x18009ac1a  cmp     [rbx+80h], eax
0x18009ac20  jge     short loc_18009AC3F
0x18009ac22  lea     rcx, [rbx+38h]
0x18009ac26  mov     rax, [rcx]
0x18009ac29  mov     [r14], rax
0x18009ac2c  mov     [rdi+20h], rcx
0x18009ac30  mov     [rax+8], r14
0x18009ac34  inc     dword ptr [rbx+80h]
0x18009ac3a  mov     [rcx], r14
0x18009ac3d  jmp     short loc_18009AC59
0x18009ac3f  mov     rdx, rbp
0x18009ac42  mov     rcx, rdi; Block
0x18009ac45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009ac4a  jmp     short loc_18009AC59
0x18009ac4c  mov     rax, [rax]
0x18009ac4f  mov     [r15], rax
0x18009ac52  call    ?ContainerPoolPush_@?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@AEAAXPEAUOBJ_CONTAINER@12@@Z; Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::ContainerPoolPush_(Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::OBJ_CONTAINER *)
0x18009ac57  xor     esi, esi
0x18009ac59  mov     rcx, rbx; lpCriticalSection
0x18009ac5c  call    cs:__imp_LeaveCriticalSection
0x18009ac63  nop     dword ptr [rax+rax+00h]
0x18009ac68  mov     eax, esi
0x18009ac6a  add     rsp, 28h
0x18009ac6e  pop     r15
0x18009ac70  pop     r14
0x18009ac72  pop     rdi
0x18009ac73  pop     rsi
0x18009ac74  pop     rbp
0x18009ac75  pop     rbx
0x18009ac76  retn
```

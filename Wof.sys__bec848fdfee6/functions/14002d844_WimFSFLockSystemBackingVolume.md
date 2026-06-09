# WimFSFLockSystemBackingVolume

- ea: `0x14002d844`
- end: `0x14002d989`
- name: `WimFSFLockSystemBackingVolume`
- size: `325`
- prototype: `__int64 __fastcall(__int64, struct _FAST_MUTEX **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140026440`
- `0x14002dd10`

## callees

- `0x14000edcc`
- `0x14002d844`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002d8a7`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002d8a7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d912`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d942`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d912`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002d942`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d900`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d930`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d900`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002d930`
- `FLTMGR!FltObjectDereference` at `0x14002d8d9`
- `FLTMGR!FltObjectDereference` at `0x14002d8d9`
- `FLTMGR!FltReleaseContext` at `0x14002d921`
- `FLTMGR!FltReleaseContext` at `0x14002d95c`
- `FLTMGR!FltReleaseContext` at `0x14002d921`
- `FLTMGR!FltReleaseContext` at `0x14002d95c`

## pseudocode

```c
__int64 __fastcall WimFSFLockSystemBackingVolume(__int64 a1, struct _FAST_MUTEX **a2)
{
  unsigned int v2; // r14d
  struct _FAST_MUTEX *v3; // rdi
  char *v4; // rsi
  int AttachVolumeFromPathName; // ebx
  struct _FAST_MUTEX *v8; // rbx
  char *v9; // rbp
  __int64 result; // rax
  PFAST_MUTEX FastMutex[7]; // [rsp+20h] [rbp-38h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp+18h] BYREF
  PVOID FltObject; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  FltObject = 0;
  v3 = 0;
  FastMutex[0] = 0;
  v4 = 0;
  while ( 1 )
  {
    do
    {
      AttachVolumeFromPathName = WofGetAttachVolumeFromPathName(a1, 0, &FltObject, FastMutex);
      if ( (unsigned int)(AttachVolumeFromPathName + 2147483632) <= 1 )
      {
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
        ++v2;
        if ( AttachVolumeFromPathName == -2147483632 )
          continue;
      }
      if ( AttachVolumeFromPathName != -2147483631 )
        break;
    }
    while ( v2 < 0x28 );
    if ( AttachVolumeFromPathName < 0 )
      break;
    FltObjectDereference(FltObject);
    v8 = FastMutex[0];
    v9 = (char *)FastMutex[0] + (unsigned int)dword_14001A2FC;
    if ( v4 == v9 )
    {
      FltReleaseContext(v3);
      result = 0;
      *a2 = v3;
      return result;
    }
    if ( v4 )
    {
      ExAcquireFastMutexUnsafe(v3);
      --*((_DWORD *)v4 + 1);
      ExReleaseFastMutexUnsafe(v3);
      FltReleaseContext(v3);
    }
    ExAcquireFastMutexUnsafe(v8);
    ++*((_DWORD *)v9 + 1);
    ExReleaseFastMutexUnsafe(v8);
    v4 = v9;
    v3 = v8;
  }
  return (unsigned int)AttachVolumeFromPathName;
}

```

## disassembly

```asm
0x14002d844  mov     rax, rsp
0x14002d847  mov     [rax+8], rbx
0x14002d84b  mov     [rax+10h], rbp
0x14002d84f  push    rsi
0x14002d850  push    rdi
0x14002d851  push    r12
0x14002d853  push    r14
0x14002d855  push    r15
0x14002d857  sub     rsp, 30h
0x14002d85b  xor     r14d, r14d
0x14002d85e  mov     qword ptr [rax+20h], 0
0x14002d866  xor     edi, edi
0x14002d868  mov     [rax-38h], r14
0x14002d86c  xor     esi, esi
0x14002d86e  mov     r15, rdx
0x14002d871  mov     r12, rcx
0x14002d874  lea     r9, [rsp+58h+FastMutex]
0x14002d879  xor     edx, edx
0x14002d87b  lea     r8, [rsp+58h+FltObject]
0x14002d880  mov     rcx, r12
0x14002d883  call    WofGetAttachVolumeFromPathName
0x14002d888  mov     ebx, eax
0x14002d88a  lea     ecx, [rax+7FFFFFF0h]
0x14002d890  cmp     ecx, 1
0x14002d893  ja      short loc_14002D8BE
0x14002d895  lea     r8, [rsp+58h+Interval]; Interval
0x14002d89a  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFF0BDC0h
0x14002d8a3  xor     edx, edx; Alertable
0x14002d8a5  xor     ecx, ecx; WaitMode
0x14002d8a7  call    cs:__imp_KeDelayExecutionThread
0x14002d8ae  nop     dword ptr [rax+rax+00h]
0x14002d8b3  inc     r14d
0x14002d8b6  cmp     ebx, 80000010h
0x14002d8bc  jz      short loc_14002D8C6
0x14002d8be  cmp     ebx, 80000011h
0x14002d8c4  jnz     short loc_14002D8CC
0x14002d8c6  cmp     r14d, 28h ; '('
0x14002d8ca  jb      short loc_14002D874
0x14002d8cc  test    ebx, ebx
0x14002d8ce  js      loc_14002D96F
0x14002d8d4  mov     rcx, [rsp+58h+FltObject]; FltObject
0x14002d8d9  call    cs:__imp_FltObjectDereference
0x14002d8e0  nop     dword ptr [rax+rax+00h]
0x14002d8e5  mov     ebp, cs:dword_14001A2FC
0x14002d8eb  mov     rbx, [rsp+58h+FastMutex]
0x14002d8f0  add     rbp, rbx
0x14002d8f3  cmp     rsi, rbp
0x14002d8f6  jz      short loc_14002D959
0x14002d8f8  test    rsi, rsi
0x14002d8fb  jz      short loc_14002D92D
0x14002d8fd  mov     rcx, rdi; FastMutex
0x14002d900  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002d907  nop     dword ptr [rax+rax+00h]
0x14002d90c  dec     dword ptr [rsi+4]
0x14002d90f  mov     rcx, rdi; FastMutex
0x14002d912  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002d919  nop     dword ptr [rax+rax+00h]
0x14002d91e  mov     rcx, rdi; Context
0x14002d921  call    cs:__imp_FltReleaseContext
0x14002d928  nop     dword ptr [rax+rax+00h]
0x14002d92d  mov     rcx, rbx; FastMutex
0x14002d930  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002d937  nop     dword ptr [rax+rax+00h]
0x14002d93c  inc     dword ptr [rbp+4]
0x14002d93f  mov     rcx, rbx; FastMutex
0x14002d942  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002d949  nop     dword ptr [rax+rax+00h]
0x14002d94e  mov     rsi, rbp
0x14002d951  mov     rdi, rbx
0x14002d954  jmp     loc_14002D874
0x14002d959  mov     rcx, rdi; Context
0x14002d95c  call    cs:__imp_FltReleaseContext
0x14002d963  nop     dword ptr [rax+rax+00h]
0x14002d968  xor     eax, eax
0x14002d96a  mov     [r15], rdi
0x14002d96d  jmp     short loc_14002D971
0x14002d96f  mov     eax, ebx
0x14002d971  mov     rbx, [rsp+58h+arg_0]
0x14002d976  mov     rbp, [rsp+58h+arg_8]
0x14002d97b  add     rsp, 30h
0x14002d97f  pop     r15
0x14002d981  pop     r14
0x14002d983  pop     r12
0x14002d985  pop     rdi
0x14002d986  pop     rsi
0x14002d987  retn
```

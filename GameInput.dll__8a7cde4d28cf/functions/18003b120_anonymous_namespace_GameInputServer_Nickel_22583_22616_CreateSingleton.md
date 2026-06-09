# _anonymous_namespace_::GameInputServer_Nickel_22583_22616::CreateSingleton

- ea: `0x18003b120`
- end: `0x18003b231`
- name: `_anonymous_namespace_::GameInputServer_Nickel_22583_22616::CreateSingleton`
- size: `273`
- prototype: `__int64 __fastcall(struct IGameInputServerInputRouter *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18003ac90`

## callees

- `0x18000c11c`
- `0x18000d68c`
- `0x18003adb0`
- `0x18003b120`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003b164`
- `ntdll!RtlAllocateHeap` at `0x18003b164`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b137`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b137`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b1cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b1cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b207`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GameInputServer_Nickel_22583_22616::CreateSingleton(
        int (__fastcall ***a1)(struct IGameInputServerInputRouter *, GUID *, const char **),
        _QWORD *a2)
{
  struct IGameInputServer **Heap; // rax
  char v5; // dl
  const struct std::nothrow_t *v6; // rdx
  int Singleton; // ebx

  AcquireSRWLockExclusive(&stru_180069830);
  if ( qword_180069828 )
  {
    GameInputFailFast(2147549183LL, 80);
    JUMPOUT(0x18003B230LL);
  }
  Heap = (struct IGameInputServer **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
  if ( Heap )
  {
    Heap[2] = 0;
    *Heap = (struct IGameInputServer *)off_18004F220;
    Heap[1] = 0;
    qword_180069828 = Heap;
    Singleton = GameInputServer::CreateSingleton(a1, v5, Heap + 1);
    if ( Singleton >= 0 )
    {
      *((_DWORD *)qword_180069828 + 4) = 1;
      _mm_mfence();
      *a2 = qword_180069828;
      ReleaseSRWLockExclusive(&stru_180069830);
      return 0;
    }
    operator delete(qword_180069828, v6);
  }
  else
  {
    Singleton = -2147024882;
  }
  qword_180069828 = 0;
  *a2 = 0;
  ReleaseSRWLockExclusive(&stru_180069830);
  return (unsigned int)Singleton;
}

```

## disassembly

```asm
0x18003b120  mov     [rsp+arg_0], rbx
0x18003b125  push    rdi
0x18003b126  sub     rsp, 20h
0x18003b12a  mov     rbx, rcx
0x18003b12d  mov     rdi, rdx
0x18003b130  lea     rcx, stru_180069830; SRWLock
0x18003b137  call    cs:__imp_AcquireSRWLockExclusive
0x18003b13e  nop     dword ptr [rax+rax+00h]
0x18003b143  cmp     cs:qword_180069828, 0
0x18003b14b  jnz     loc_18003B221
0x18003b151  mov     rcx, gs:60h
0x18003b15a  xor     edx, edx; Flags
0x18003b15c  mov     rcx, [rcx+30h]; HeapHandle
0x18003b160  lea     r8d, [rdx+18h]; Size
0x18003b164  call    cs:__imp_RtlAllocateHeap
0x18003b16b  nop     dword ptr [rax+rax+00h]
0x18003b170  test    rax, rax
0x18003b173  jz      short loc_18003B1E9
0x18003b175  lea     rcx, off_18004F220
0x18003b17c  mov     qword ptr [rax+10h], 0
0x18003b184  mov     [rax], rcx
0x18003b187  lea     r8, [rax+8]; struct IGameInputServer **
0x18003b18b  mov     rcx, rbx; struct IGameInputServerInputRouter *
0x18003b18e  mov     qword ptr [rax+8], 0
0x18003b196  mov     cs:qword_180069828, rax
0x18003b19d  call    ?CreateSingleton@GameInputServer@@SAJPEAUIGameInputServerInputRouter@@_NPEAPEAUIGameInputServer@@@Z; GameInputServer::CreateSingleton(IGameInputServerInputRouter *,bool,IGameInputServer * *)
0x18003b1a2  mov     ebx, eax
0x18003b1a4  test    eax, eax
0x18003b1a6  js      short loc_18003B1DB
0x18003b1a8  mov     rax, cs:qword_180069828
0x18003b1af  nop
0x18003b1b0  mov     dword ptr [rax+10h], 1
0x18003b1b7  mfence
0x18003b1ba  mov     rax, cs:qword_180069828
0x18003b1c1  lea     rcx, stru_180069830; SRWLock
0x18003b1c8  mov     [rdi], rax
0x18003b1cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b1d2  nop     dword ptr [rax+rax+00h]
0x18003b1d7  xor     eax, eax
0x18003b1d9  jmp     short loc_18003B215
0x18003b1db  mov     rcx, cs:qword_180069828; P
0x18003b1e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003b1e7  jmp     short loc_18003B1EE
0x18003b1e9  mov     ebx, 8007000Eh
0x18003b1ee  lea     rcx, stru_180069830; SRWLock
0x18003b1f5  mov     cs:qword_180069828, 0
0x18003b200  mov     qword ptr [rdi], 0
0x18003b207  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b20e  nop     dword ptr [rax+rax+00h]
0x18003b213  mov     eax, ebx
0x18003b215  mov     rbx, [rsp+28h+arg_0]
0x18003b21a  add     rsp, 20h
0x18003b21e  pop     rdi
0x18003b21f  retn
0x18003b221  mov     edx, 50h ; 'P'
0x18003b226  mov     ecx, 8000FFFFh
0x18003b22b  call    GameInputFailFast
```

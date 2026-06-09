# VolumeTrackerList::~VolumeTrackerList(void)

- ea: `0x180073ed0`
- end: `0x180073f6b`
- name: `??1VolumeTrackerList@@EEAA@XZ`
- size: `155`
- prototype: `void __fastcall(VolumeTrackerList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180073fd0`

## callees

- `0x18000d400`
- `0x1800725f0`
- `0x180073e98`
- `0x180073ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073ef3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073ef3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073f3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180073f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073f34`

## pseudocode

```c
void __fastcall VolumeTrackerList::~VolumeTrackerList(VolumeTrackerList *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rbx

  *(_QWORD *)this = &VolumeTrackerList::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  while ( 1 )
  {
    v3 = *((_QWORD *)this + 11);
    if ( !v3 )
      break;
    *((_QWORD *)this + 11) = *(_QWORD *)(v3 + 8);
    if ( *(_QWORD *)v3 )
    {
      VolumeTrackerVolume::Release(*(VolumeTrackerVolume **)v3);
      *(_QWORD *)v3 = 0;
    }
    operator delete((void *)v3, (const struct std::nothrow_t *)0x10);
  }
  *((_QWORD *)this + 11) = 0;
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  *(_OWORD *)&v2->DebugInfo = 0;
  *(_OWORD *)&v2->OwningThread = 0;
  v2->SpinCount = 0;
  std::_Tree<std::_Tset_traits<STORE_ID,std::less<STORE_ID>,std::allocator<STORE_ID>,0>>::~_Tree<std::_Tset_traits<STORE_ID,std::less<STORE_ID>,std::allocator<STORE_ID>,0>>((char *)this + 72);
}

```

## disassembly

```asm
0x180073ed0  mov     [rsp+arg_0], rbx
0x180073ed5  mov     [rsp+arg_8], rsi
0x180073eda  push    rdi
0x180073edb  sub     rsp, 20h
0x180073edf  mov     rdi, rcx
0x180073ee2  lea     rax, ??_7VolumeTrackerList@@6B@; const VolumeTrackerList::`vftable'
0x180073ee9  mov     [rcx], rax
0x180073eec  lea     rsi, [rcx+18h]
0x180073ef0  mov     rcx, rsi; lpCriticalSection
0x180073ef3  call    cs:__imp_EnterCriticalSection
0x180073ef9  jmp     short loc_180073F24
0x180073efb  mov     rax, [rbx+8]
0x180073eff  mov     [rdi+58h], rax
0x180073f03  mov     rcx, [rbx]; this
0x180073f06  test    rcx, rcx
0x180073f09  jz      short loc_180073F17
0x180073f0b  call    ?Release@VolumeTrackerVolume@@QEAAKXZ; VolumeTrackerVolume::Release(void)
0x180073f10  mov     qword ptr [rbx], 0
0x180073f17  mov     edx, 10h; struct std::nothrow_t *
0x180073f1c  mov     rcx, rbx; void *
0x180073f1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073f24  mov     rbx, [rdi+58h]
0x180073f28  test    rbx, rbx
0x180073f2b  jnz     short loc_180073EFB
0x180073f2d  mov     [rdi+58h], rbx
0x180073f31  mov     rcx, rsi; lpCriticalSection
0x180073f34  call    cs:__imp_LeaveCriticalSection
0x180073f3a  mov     rcx, rsi; lpCriticalSection
0x180073f3d  call    cs:__imp_DeleteCriticalSection
0x180073f43  xorps   xmm0, xmm0
0x180073f46  xor     eax, eax
0x180073f48  movups  xmmword ptr [rsi], xmm0
0x180073f4b  movups  xmmword ptr [rsi+10h], xmm0
0x180073f4f  mov     [rsi+20h], rax
0x180073f53  lea     rcx, [rdi+48h]
0x180073f57  mov     rbx, [rsp+28h+arg_0]
0x180073f5c  mov     rsi, [rsp+28h+arg_8]
0x180073f61  add     rsp, 20h
0x180073f65  pop     rdi
0x180073f66  jmp     ??1?$_Tree@V?$_Tset_traits@USTORE_ID@@U?$less@USTORE_ID@@@std@@V?$allocator@USTORE_ID@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<STORE_ID,std::less<STORE_ID>,std::allocator<STORE_ID>,0>>::~_Tree<std::_Tset_traits<STORE_ID,std::less<STORE_ID>,std::allocator<STORE_ID>,0>>(void)
```

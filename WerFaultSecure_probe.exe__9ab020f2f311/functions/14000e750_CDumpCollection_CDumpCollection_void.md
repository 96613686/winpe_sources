# CDumpCollection::~CDumpCollection(void)

- ea: `0x14000e750`
- end: `0x14000e819`
- name: `??1CDumpCollection@@QEAA@XZ`
- size: `201`
- prototype: `void __fastcall(CDumpCollection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140006038`

## callees

- `0x1400023f4`
- `0x14000e750`
- `0x14000e820`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000e7e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000e7e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e7ff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e812`

## pseudocode

```c
void __fastcall CDumpCollection::~CDumpCollection(HMODULE *this)
{
  HMODULE v2; // rcx
  HMODULE *v3; // rdi
  HMODULE *v4; // rcx
  HMODULE *v5; // rcx
  HMODULE v6; // rcx
  HMODULE v7; // rcx

  CDumpCollection::Cleanup((CDumpCollection *)this);
  v2 = this[300];
  if ( v2 == (HMODULE)-1LL )
    goto LABEL_4;
  this[301] = v2;
  while ( 1 )
  {
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
LABEL_4:
    v3 = (HMODULE *)this[144];
    if ( v3 == (HMODULE *)-1LL )
      break;
    this[144] = *v3;
    v4 = (HMODULE *)v3[1];
    if ( v4 != v3 + 3 )
      operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
    v2 = (HMODULE)v3;
  }
  while ( 1 )
  {
    v5 = (HMODULE *)this[143];
    if ( v5 == (HMODULE *)-1LL )
      break;
    this[143] = *v5;
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  }
  v6 = this[140];
  if ( v6 )
    FreeLibrary(v6);
  v7 = this[137];
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x14000e750  mov     [rsp+arg_0], rbx
0x14000e755  push    rdi
0x14000e756  sub     rsp, 20h
0x14000e75a  mov     rbx, rcx
0x14000e75d  call    ?Cleanup@CDumpCollection@@QEAAXXZ; CDumpCollection::Cleanup(void)
0x14000e762  mov     rcx, [rbx+960h]; void *
0x14000e769  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e76d  jz      short loc_14000E782
0x14000e76f  mov     [rbx+968h], rcx
0x14000e776  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e77d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e782  mov     rdi, [rbx+480h]
0x14000e789  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000e78d  jz      short loc_14000E7B7
0x14000e78f  mov     rax, [rdi]
0x14000e792  mov     [rbx+480h], rax
0x14000e799  lea     rax, [rdi+18h]
0x14000e79d  mov     rcx, [rdi+8]; void *
0x14000e7a1  cmp     rcx, rax
0x14000e7a4  jz      short loc_14000E7B2
0x14000e7a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e7ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e7b2  mov     rcx, rdi
0x14000e7b5  jmp     short loc_14000E776
0x14000e7b7  mov     rcx, [rbx+478h]; void *
0x14000e7be  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e7c2  jz      short loc_14000E7DC
0x14000e7c4  mov     rax, [rcx]
0x14000e7c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e7ce  mov     [rbx+478h], rax
0x14000e7d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e7da  jmp     short loc_14000E7B7
0x14000e7dc  mov     rcx, [rbx+460h]; hLibModule
0x14000e7e3  test    rcx, rcx
0x14000e7e6  jz      short loc_14000E7EE
0x14000e7e8  call    cs:__imp_FreeLibrary
0x14000e7ee  mov     rcx, [rbx+448h]; hObject
0x14000e7f5  lea     rax, [rcx+1]
0x14000e7f9  cmp     rax, 1
0x14000e7fd  jbe     short loc_14000E805
0x14000e7ff  call    cs:__imp_CloseHandle
0x14000e805  mov     rcx, rbx
0x14000e808  mov     rbx, [rsp+28h+arg_0]
0x14000e80d  add     rsp, 20h
0x14000e811  pop     rdi
0x14000e812  jmp     cs:__imp_DeleteCriticalSection
```

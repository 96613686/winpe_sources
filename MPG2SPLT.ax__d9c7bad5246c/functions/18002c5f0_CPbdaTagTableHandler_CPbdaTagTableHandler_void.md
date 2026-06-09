# CPbdaTagTableHandler::~CPbdaTagTableHandler(void)

- ea: `0x18002c5f0`
- end: `0x18002c681`
- name: `??1CPbdaTagTableHandler@@QEAA@XZ`
- size: `145`
- prototype: `void __fastcall(CPbdaTagTableHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18002c688`

## callees

- `0x180001048`
- `0x18002c5f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c61a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c61a`
- `KERNEL32!DeleteCriticalSection` at `0x18002c67a`
- `KERNEL32!LeaveCriticalSection` at `0x18002c669`
- `KERNEL32!LeaveCriticalSection` at `0x18002c669`
- `KERNEL32!EnterCriticalSection` at `0x18002c606`
- `KERNEL32!EnterCriticalSection` at `0x18002c606`

## pseudocode

```c
void __fastcall CPbdaTagTableHandler::~CPbdaTagTableHandler(CPbdaTagTableHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned __int64 v3; // rdx
  __int64 v4; // rbp
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  v4 = 0;
  v5 = 0;
  do
  {
    v6 = *(void **)((char *)this + v5 + 48);
    if ( v6 )
    {
      free(v6);
      *(_QWORD *)((char *)this + v5 + 48) = 0;
    }
    v7 = *(void **)((char *)this + v5 + 24);
    if ( v7 )
    {
      operator delete(v7, v3);
      *(_QWORD *)((char *)this + v5 + 24) = 0;
    }
    v8 = *(void **)((char *)this + v5 + 40);
    if ( v8 )
    {
      operator delete(v8, v3);
      *(_QWORD *)((char *)this + v5 + 40) = 0;
    }
    ++v4;
    v5 += 64;
  }
  while ( v4 != 5 );
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18002c5f0  push    rbx
0x18002c5f2  push    rbp
0x18002c5f3  push    rsi
0x18002c5f4  push    rdi
0x18002c5f5  sub     rsp, 28h
0x18002c5f9  lea     rbx, [rcx+148h]
0x18002c600  mov     rsi, rcx
0x18002c603  mov     rcx, rbx; lpCriticalSection
0x18002c606  call    cs:__imp_EnterCriticalSection
0x18002c60c  xor     ebp, ebp
0x18002c60e  xor     edi, edi
0x18002c610  mov     rcx, [rdi+rsi+30h]; Block
0x18002c615  test    rcx, rcx
0x18002c618  jz      short loc_18002C629
0x18002c61a  call    cs:__imp_free
0x18002c620  mov     qword ptr [rdi+rsi+30h], 0
0x18002c629  mov     rcx, [rdi+rsi+18h]; void *
0x18002c62e  test    rcx, rcx
0x18002c631  jz      short loc_18002C641
0x18002c633  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c638  mov     qword ptr [rdi+rsi+18h], 0
0x18002c641  mov     rcx, [rdi+rsi+28h]; void *
0x18002c646  test    rcx, rcx
0x18002c649  jz      short loc_18002C659
0x18002c64b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c650  mov     qword ptr [rdi+rsi+28h], 0
0x18002c659  inc     rbp
0x18002c65c  add     rdi, 40h ; '@'
0x18002c660  cmp     rbp, 5
0x18002c664  jnz     short loc_18002C610
0x18002c666  mov     rcx, rbx; lpCriticalSection
0x18002c669  call    cs:__imp_LeaveCriticalSection
0x18002c66f  mov     rcx, rbx
0x18002c672  add     rsp, 28h
0x18002c676  pop     rdi
0x18002c677  pop     rsi
0x18002c678  pop     rbp
0x18002c679  pop     rbx
0x18002c67a  jmp     cs:__imp_DeleteCriticalSection
```

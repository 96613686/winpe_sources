# FreeBufferPool

- ea: `0x180008490`
- end: `0x1800084d8`
- name: `FreeBufferPool`
- size: `72`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003920`
- `0x180005560`

## callees

- `0x1800077bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800084a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800084a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084c5`

## pseudocode

```c
char __fastcall FreeBufferPool(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 64);
  v2 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  FreeUnusedBufferPoolBlocks(v2);
  LOBYTE(v2) = *(_DWORD *)(v2 + 12) == 0;
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  return v2;
}

```

## disassembly

```asm
0x180008490  mov     [rsp+arg_0], rbx
0x180008495  push    rdi
0x180008496  sub     rsp, 20h
0x18000849a  lea     rdi, [rcx+40h]
0x18000849e  mov     rbx, rcx
0x1800084a1  mov     rcx, rdi; lpCriticalSection
0x1800084a4  call    cs:__imp_EnterCriticalSection
0x1800084aa  mov     rcx, rbx
0x1800084ad  call    FreeUnusedBufferPoolBlocks
0x1800084b2  cmp     dword ptr [rbx+0Ch], 0
0x1800084b6  mov     rcx, rdi; lpCriticalSection
0x1800084b9  setz    bl
0x1800084bc  call    cs:__imp_LeaveCriticalSection
0x1800084c2  mov     rcx, rdi; lpCriticalSection
0x1800084c5  call    cs:__imp_DeleteCriticalSection
0x1800084cb  mov     al, bl
0x1800084cd  mov     rbx, [rsp+28h+arg_0]
0x1800084d2  add     rsp, 20h
0x1800084d6  pop     rdi
0x1800084d7  retn
```

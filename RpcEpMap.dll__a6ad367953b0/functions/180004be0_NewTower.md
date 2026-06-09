# NewTower

- ea: `0x180004be0`
- end: `0x180004c39`
- name: `NewTower`
- size: `89`
- prototype: `void *__fastcall(_WORD *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004950`
- `0x180004a50`

## callees

- `0x180004be0`
- `0x18000a8a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bfc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c0a`

## pseudocode

```c
void *__fastcall NewTower(_WORD *Src)
{
  unsigned int v2; // esi
  HANDLE ProcessHeap; // rax
  void *result; // rax
  void *v5; // rbx

  v2 = (unsigned __int16)(*Src + 4);
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 0, v2);
  v5 = result;
  if ( result )
  {
    memcpy_0(result, Src, v2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180004be0  mov     [rsp+arg_0], rbx
0x180004be5  mov     [rsp+arg_8], rsi
0x180004bea  push    rdi
0x180004beb  sub     rsp, 20h
0x180004bef  movzx   eax, word ptr [rcx]
0x180004bf2  mov     rdi, rcx
0x180004bf5  add     ax, 4
0x180004bf9  movzx   esi, ax
0x180004bfc  call    cs:__imp_GetProcessHeap
0x180004c02  mov     r8d, esi; dwBytes
0x180004c05  xor     edx, edx; dwFlags
0x180004c07  mov     rcx, rax; hHeap
0x180004c0a  call    cs:__imp_HeapAlloc
0x180004c10  mov     rbx, rax
0x180004c13  test    rax, rax
0x180004c16  jz      short loc_180004C29
0x180004c18  mov     r8d, esi; Size
0x180004c1b  mov     rdx, rdi; Src
0x180004c1e  mov     rcx, rax; void *
0x180004c21  call    memcpy_0
0x180004c26  mov     rax, rbx
0x180004c29  mov     rbx, [rsp+28h+arg_0]
0x180004c2e  mov     rsi, [rsp+28h+arg_8]
0x180004c33  add     rsp, 20h
0x180004c37  pop     rdi
0x180004c38  retn
```

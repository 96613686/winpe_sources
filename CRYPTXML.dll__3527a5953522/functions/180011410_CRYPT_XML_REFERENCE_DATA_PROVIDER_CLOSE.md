# CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE

- ea: `0x180011410`
- end: `0x18001147c`
- name: `CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE`
- size: `108`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009f80`
- `0x18000fe50`

## callees

- `0x180011410`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001143d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001146e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001143d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001146e`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE(_QWORD *lpMem)
{
  void *v1; // rdi
  HANDLE v3; // rax
  HANDLE ProcessHeap; // rax

  v1 = (void *)lpMem[2];
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, v1);
  }
  v3 = GetProcessHeap();
  HeapFree(v3, 8u, lpMem);
  return 0;
}

```

## disassembly

```asm
0x180011410  mov     [rsp+arg_0], rbx
0x180011415  push    rdi
0x180011416  sub     rsp, 20h
0x18001141a  mov     rdi, [rcx+10h]
0x18001141e  mov     rbx, rcx
0x180011421  test    rdi, rdi
0x180011424  jnz     short loc_180011457
0x180011426  call    cs:__imp_GetProcessHeap
0x18001142d  nop     dword ptr [rax+rax+00h]
0x180011432  mov     r8, rbx; lpMem
0x180011435  mov     edx, 8; dwFlags
0x18001143a  mov     rcx, rax; hHeap
0x18001143d  call    cs:__imp_HeapFree
0x180011444  nop     dword ptr [rax+rax+00h]
0x180011449  mov     rbx, [rsp+28h+arg_0]
0x18001144e  xor     eax, eax
0x180011450  add     rsp, 20h
0x180011454  pop     rdi
0x180011455  retn
0x180011457  call    cs:__imp_GetProcessHeap
0x18001145e  nop     dword ptr [rax+rax+00h]
0x180011463  mov     r8, rdi; lpMem
0x180011466  mov     edx, 8; dwFlags
0x18001146b  mov     rcx, rax; hHeap
0x18001146e  call    cs:__imp_HeapFree
0x180011475  nop     dword ptr [rax+rax+00h]
0x18001147a  jmp     short loc_180011426
```

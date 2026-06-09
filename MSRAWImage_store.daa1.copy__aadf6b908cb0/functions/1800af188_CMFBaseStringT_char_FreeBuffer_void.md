# CMFBaseStringT<char>::_FreeBuffer(void)

- ea: `0x1800af188`
- end: `0x1800af1fe`
- name: `?_FreeBuffer@?$CMFBaseStringT@D@@IEAAXXZ`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a5240`
- `0x1800af0ac`

## callees

- `0x1800af188`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af1d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af1d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af1bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af1bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af1a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af1a9`

## pseudocode

```c
void __fastcall CMFBaseStringT<char>::_FreeBuffer(__int64 a1)
{
  void *v2; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax

  if ( (*(_DWORD *)a1 & 1) == 0 )
  {
    v2 = *(void **)(a1 + 16);
    if ( v2 )
    {
      v3 = *(_DWORD *)a1 & 6;
      if ( v3 )
      {
        if ( v3 == 2 )
          CoTaskMemFree(*(LPVOID *)(a1 + 16));
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
    }
    *(_DWORD *)a1 &= 0xFFFFFFF9;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800af188  mov     [rsp+arg_0], rbx
0x1800af18d  push    rdi
0x1800af18e  sub     rsp, 20h
0x1800af192  mov     eax, [rcx]
0x1800af194  mov     rbx, rcx
0x1800af197  test    al, 1
0x1800af199  jnz     short loc_1800AF1F2
0x1800af19b  mov     rdi, [rcx+10h]
0x1800af19f  test    rdi, rdi
0x1800af1a2  jz      short loc_1800AF1DF
0x1800af1a4  and     eax, 6
0x1800af1a7  jnz     short loc_1800AF1CB
0x1800af1a9  call    cs:__imp_GetProcessHeap
0x1800af1b0  nop     dword ptr [rax+rax+00h]
0x1800af1b5  mov     r8, rdi; lpMem
0x1800af1b8  xor     edx, edx; dwFlags
0x1800af1ba  mov     rcx, rax; hHeap
0x1800af1bd  call    cs:__imp_HeapFree
0x1800af1c4  nop     dword ptr [rax+rax+00h]
0x1800af1c9  jmp     short loc_1800AF1DF
0x1800af1cb  cmp     eax, 2
0x1800af1ce  jnz     short loc_1800AF1DF
0x1800af1d0  mov     rcx, rdi; pv
0x1800af1d3  call    cs:__imp_CoTaskMemFree
0x1800af1da  nop     dword ptr [rax+rax+00h]
0x1800af1df  and     dword ptr [rbx], 0FFFFFFF9h
0x1800af1e2  mov     qword ptr [rbx+10h], 0
0x1800af1ea  mov     qword ptr [rbx+8], 0
0x1800af1f2  mov     rbx, [rsp+28h+arg_0]
0x1800af1f7  add     rsp, 20h
0x1800af1fb  pop     rdi
0x1800af1fc  retn
```

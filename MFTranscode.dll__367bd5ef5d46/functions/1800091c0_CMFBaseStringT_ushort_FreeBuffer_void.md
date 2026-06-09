# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x1800091c0`
- end: `0x18000921e`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `94`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003950`
- `0x180007bd0`
- `0x180008050`
- `0x180008440`
- `0x180008790`
- `0x180008a50`
- `0x18000f0a4`

## callees

- `0x1800091c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009200`

## pseudocode

```c
__int64 __fastcall CMFBaseStringT<unsigned short>::_FreeBuffer(unsigned int *a1)
{
  __int64 result; // rax
  void *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax

  result = *a1;
  if ( (result & 1) == 0 )
  {
    v3 = (void *)*((_QWORD *)a1 + 2);
    if ( v3 )
    {
      v4 = *a1 & 6;
      if ( v4 )
      {
        if ( v4 == 2 )
          CoTaskMemFree(*((LPVOID *)a1 + 2));
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
      }
    }
    *a1 &= 0xFFFFFFF9;
    result = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800091c0  push    rbx
0x1800091c2  sub     rsp, 20h
0x1800091c6  mov     eax, [rcx]
0x1800091c8  mov     rbx, rcx
0x1800091cb  test    al, 1
0x1800091cd  jnz     short loc_180009218
0x1800091cf  mov     [rsp+28h+arg_0], rdi
0x1800091d4  mov     rdi, [rcx+10h]
0x1800091d8  test    rdi, rdi
0x1800091db  jz      short loc_180009206
0x1800091dd  and     eax, 6
0x1800091e0  jnz     short loc_1800091F8
0x1800091e2  call    cs:__imp_GetProcessHeap
0x1800091e8  mov     r8, rdi; lpMem
0x1800091eb  xor     edx, edx; dwFlags
0x1800091ed  mov     rcx, rax; hHeap
0x1800091f0  call    cs:__imp_HeapFree
0x1800091f6  jmp     short loc_180009206
0x1800091f8  cmp     eax, 2
0x1800091fb  jnz     short loc_180009206
0x1800091fd  mov     rcx, rdi; pv
0x180009200  call    cs:__imp_CoTaskMemFree
0x180009206  and     dword ptr [rbx], 0FFFFFFF9h
0x180009209  mov     rdi, [rsp+28h+arg_0]
0x18000920e  xor     eax, eax
0x180009210  mov     [rbx+10h], rax
0x180009214  mov     [rbx+8], rax
0x180009218  add     rsp, 20h
0x18000921c  pop     rbx
0x18000921d  retn
```

# std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>::~unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>(void)

- ea: `0x18000a6d0`
- end: `0x18000a752`
- name: `??1?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ce0`
- `0x18000a1dc`
- `0x18000a280`
- `0x18000a2c0`
- `0x18000a400`
- `0x18000a620`
- `0x18002bd97`

## callees

- `0x18000a6d0`
- `0x180021084`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a726`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a717`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a717`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a734`

## pseudocode

```c
void __fastcall std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[4];
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    v4 = (void *)v1[3];
    if ( v4 )
    {
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
    }
    v6 = (void *)v1[1];
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000a6d0  push    rbx
0x18000a6d2  sub     rsp, 20h
0x18000a6d6  mov     rbx, [rcx]
0x18000a6d9  test    rbx, rbx
0x18000a6dc  jz      short loc_18000A74C
0x18000a6de  mov     [rsp+28h+arg_0], rdi
0x18000a6e3  mov     rdi, [rbx+20h]
0x18000a6e7  test    rdi, rdi
0x18000a6ea  jz      short loc_18000A700
0x18000a6ec  call    cs:__imp_GetProcessHeap
0x18000a6f2  mov     r8, rdi; lpMem
0x18000a6f5  xor     edx, edx; dwFlags
0x18000a6f7  mov     rcx, rax; hHeap
0x18000a6fa  call    cs:__imp_HeapFree
0x18000a700  mov     rdi, [rbx+18h]
0x18000a704  test    rdi, rdi
0x18000a707  jz      short loc_18000A71D
0x18000a709  call    cs:__imp_GetProcessHeap
0x18000a70f  mov     r8, rdi; lpMem
0x18000a712  xor     edx, edx; dwFlags
0x18000a714  mov     rcx, rax; hHeap
0x18000a717  call    cs:__imp_HeapFree
0x18000a71d  mov     rdi, [rbx+8]
0x18000a721  test    rdi, rdi
0x18000a724  jz      short loc_18000A73A
0x18000a726  call    cs:__imp_GetProcessHeap
0x18000a72c  mov     r8, rdi; lpMem
0x18000a72f  xor     edx, edx; dwFlags
0x18000a731  mov     rcx, rax; hHeap
0x18000a734  call    cs:__imp_HeapFree
0x18000a73a  mov     edx, 28h ; '('; unsigned __int64
0x18000a73f  mov     rcx, rbx; void *
0x18000a742  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a747  mov     rdi, [rsp+28h+arg_0]
0x18000a74c  add     rsp, 20h
0x18000a750  pop     rbx
0x18000a751  retn
```

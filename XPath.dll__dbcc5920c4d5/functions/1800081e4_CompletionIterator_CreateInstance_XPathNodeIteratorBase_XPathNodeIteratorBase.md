# CompletionIterator::CreateInstance(XPathNodeIteratorBase *,XPathNodeIteratorBase * *)

- ea: `0x1800081e4`
- end: `0x18000828d`
- name: `?CreateInstance@CompletionIterator@@SAJPEAVXPathNodeIteratorBase@@PEAPEAV2@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct XPathNodeIteratorBase *, struct XPathNodeIteratorBase **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008cb4`

## callees

- `0x180001078`
- `0x1800054e0`
- `0x18000624c`
- `0x1800081e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000824b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000824b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008239`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008239`

## pseudocode

```c
__int64 __fastcall CompletionIterator::CreateInstance(
        struct XPathNodeIteratorBase *a1,
        struct XPathNodeIteratorBase **a2)
{
  CompletionIterator *v4; // rax
  CompletionIterator *v5; // rbx
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  CompletionIterator *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v4 = (CompletionIterator *)operator new(0x88u);
  if ( v4 )
    v5 = CompletionIterator::CompletionIterator(v4, a1);
  else
    v5 = 0;
  InvasivePtr<UnionExpressionIterator>::Reset(&v10);
  v10 = v5;
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x80u);
    *((_QWORD *)v5 + 5) = v8;
    if ( v8 )
    {
      *((_DWORD *)v5 + 12) = 16;
      *a2 = v5;
      v6 = 0;
      v10 = 0;
    }
    else
    {
      v6 = -2147024888;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  InvasivePtr<UnionExpressionIterator>::Reset(&v10);
  return v6;
}

```

## disassembly

```asm
0x1800081e4  mov     [rsp+arg_0], rbx
0x1800081e9  push    rdi
0x1800081ea  sub     rsp, 20h
0x1800081ee  mov     rbx, rcx
0x1800081f1  mov     [rsp+28h+arg_10], 0
0x1800081fa  mov     ecx, 88h; Size
0x1800081ff  mov     rdi, rdx
0x180008202  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008207  test    rax, rax
0x18000820a  jz      short loc_18000821C
0x18000820c  mov     rdx, rbx; struct XPathNodeIteratorBase *
0x18000820f  mov     rcx, rax; this
0x180008212  call    ??0CompletionIterator@@AEAA@PEAVXPathNodeIteratorBase@@@Z; CompletionIterator::CompletionIterator(XPathNodeIteratorBase *)
0x180008217  mov     rbx, rax
0x18000821a  jmp     short loc_18000821E
0x18000821c  xor     ebx, ebx
0x18000821e  lea     rcx, [rsp+28h+arg_10]
0x180008223  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008228  mov     [rsp+28h+arg_10], rbx
0x18000822d  test    rbx, rbx
0x180008230  jnz     short loc_180008239
0x180008232  mov     ebx, 8007000Eh
0x180008237  jmp     short loc_180008276
0x180008239  call    cs:__imp_GetProcessHeap
0x18000823f  mov     edx, 8; dwFlags
0x180008244  mov     rcx, rax; hHeap
0x180008247  lea     r8d, [rdx+78h]; dwBytes
0x18000824b  call    cs:__imp_HeapAlloc
0x180008251  mov     [rbx+28h], rax
0x180008255  test    rax, rax
0x180008258  jz      short loc_180008271
0x18000825a  mov     dword ptr [rbx+30h], 10h
0x180008261  mov     [rdi], rbx
0x180008264  xor     ebx, ebx
0x180008266  mov     [rsp+28h+arg_10], 0
0x18000826f  jmp     short loc_180008276
0x180008271  mov     ebx, 80070008h
0x180008276  lea     rcx, [rsp+28h+arg_10]
0x18000827b  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x180008280  mov     eax, ebx
0x180008282  mov     rbx, [rsp+28h+arg_0]
0x180008287  add     rsp, 20h
0x18000828b  pop     rdi
0x18000828c  retn
```

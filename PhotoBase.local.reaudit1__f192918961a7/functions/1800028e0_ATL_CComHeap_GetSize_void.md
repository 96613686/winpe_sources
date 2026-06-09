# ATL::CComHeap::GetSize(void *)

- ea: `0x1800028e0`
- end: `0x180002958`
- name: `?GetSize@CComHeap@ATL@@UEAA_KPEAX@Z`
- size: `120`
- prototype: `unsigned __int64 __fastcall(ATL::CComHeap *__hidden this, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800028e0`
- `0x180008010`

## import_xrefs

- `ole32!CoGetMalloc` at `0x1800028fc`
- `ole32!CoGetMalloc` at `0x1800028fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComHeap::GetSize(ATL::CComHeap *this, void *a2)
{
  __int64 v4; // rbx
  LPMALLOC ppMalloc; // [rsp+40h] [rbp+18h] BYREF

  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, a2);
    if ( ppMalloc )
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    return v4;
  }
  else
  {
    if ( ppMalloc )
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    return 0;
  }
}

```

## disassembly

```asm
0x1800028e0  push    rbx
0x1800028e2  sub     rsp, 20h
0x1800028e6  mov     rbx, rdx
0x1800028e9  mov     [rsp+28h+ppMalloc], 0
0x1800028f2  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800028f7  mov     ecx, 1; dwMemContext
0x1800028fc  call    cs:__imp_CoGetMalloc
0x180002902  test    eax, eax
0x180002904  jns     short loc_180002921
0x180002906  mov     rcx, [rsp+28h+ppMalloc]
0x18000290b  test    rcx, rcx
0x18000290e  jz      short loc_18000291D
0x180002910  mov     rax, [rcx]
0x180002913  mov     rax, [rax+10h]
0x180002917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291c  nop
0x18000291d  xor     eax, eax
0x18000291f  jmp     short loc_180002952
0x180002921  mov     rcx, [rsp+28h+ppMalloc]
0x180002926  mov     rax, [rcx]
0x180002929  mov     rdx, rbx
0x18000292c  mov     rax, [rax+30h]
0x180002930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002935  mov     rbx, rax
0x180002938  mov     rcx, [rsp+28h+ppMalloc]
0x18000293d  test    rcx, rcx
0x180002940  jz      short loc_18000294F
0x180002942  mov     rdx, [rcx]
0x180002945  mov     rax, [rdx+10h]
0x180002949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294e  nop
0x18000294f  mov     rax, rbx
0x180002952  add     rsp, 20h
0x180002956  pop     rbx
0x180002957  retn
```

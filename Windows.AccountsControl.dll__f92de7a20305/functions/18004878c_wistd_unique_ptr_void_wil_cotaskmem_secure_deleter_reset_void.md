# wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)

- ea: `0x18004878c`
- end: `0x180048809`
- name: `?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045fec`
- `0x180046050`
- `0x180047b8c`

## callees

- `0x18004878c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800487b0`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800487b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800487fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800487fc`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void **a1, void *a2)
{
  _BYTE *v2; // rbx
  __int64 v3; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v2);
      if ( v3 != -1 )
      {
        for ( i = v2; v3; --v3 )
          *i++ = 0;
      }
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    CoTaskMemFree(v2);
  }
}

```

## disassembly

```asm
0x18004878c  push    rbx
0x18004878e  sub     rsp, 20h
0x180048792  mov     rbx, [rcx]
0x180048795  mov     [rcx], rdx
0x180048798  test    rbx, rbx
0x18004879b  jz      short loc_180048803
0x18004879d  mov     [rsp+28h+ppMalloc], 0
0x1800487a6  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800487ab  mov     ecx, 1; dwMemContext
0x1800487b0  call    cs:__imp_CoGetMalloc
0x1800487b6  test    eax, eax
0x1800487b8  js      short loc_1800487F9
0x1800487ba  mov     rcx, [rsp+28h+ppMalloc]
0x1800487bf  mov     rax, [rcx]
0x1800487c2  mov     rdx, rbx
0x1800487c5  mov     rax, [rax+30h]
0x1800487c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800487d2  jz      short loc_1800487E8
0x1800487d4  mov     rcx, rbx
0x1800487d7  test    rax, rax
0x1800487da  jz      short loc_1800487E8
0x1800487dc  mov     byte ptr [rcx], 0
0x1800487df  inc     rcx
0x1800487e2  sub     rax, 1
0x1800487e6  jnz     short loc_1800487DC
0x1800487e8  mov     rcx, [rsp+28h+ppMalloc]
0x1800487ed  mov     rax, [rcx]
0x1800487f0  mov     rax, [rax+10h]
0x1800487f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487f9  mov     rcx, rbx; pv
0x1800487fc  call    cs:__imp_CoTaskMemFree
0x180048802  nop
0x180048803  add     rsp, 20h
0x180048807  pop     rbx
0x180048808  retn
```

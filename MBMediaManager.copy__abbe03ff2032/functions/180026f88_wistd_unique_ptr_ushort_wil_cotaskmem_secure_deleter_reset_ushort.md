# wistd::unique_ptr<ushort,wil::cotaskmem_secure_deleter>::reset(ushort *)

- ea: `0x180026f88`
- end: `0x180027005`
- name: `?reset@?$unique_ptr@GUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAG@Z`
- size: `125`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026c60`
- `0x180026df0`
- `0x180026f64`
- `0x18004fb18`

## callees

- `0x180026f88`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180026fac`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180026fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ff8`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short,wil::cotaskmem_secure_deleter>::reset(void **a1, void *a2)
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
0x180026f88  push    rbx
0x180026f8a  sub     rsp, 20h
0x180026f8e  mov     rbx, [rcx]
0x180026f91  mov     [rcx], rdx
0x180026f94  test    rbx, rbx
0x180026f97  jz      short loc_180026FFF
0x180026f99  mov     [rsp+28h+ppMalloc], 0
0x180026fa2  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180026fa7  mov     ecx, 1; dwMemContext
0x180026fac  call    cs:__imp_CoGetMalloc
0x180026fb2  test    eax, eax
0x180026fb4  js      short loc_180026FF5
0x180026fb6  mov     rcx, [rsp+28h+ppMalloc]
0x180026fbb  mov     rax, [rcx]
0x180026fbe  mov     rdx, rbx
0x180026fc1  mov     rax, [rax+30h]
0x180026fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026fce  jz      short loc_180026FE4
0x180026fd0  mov     rcx, rbx
0x180026fd3  test    rax, rax
0x180026fd6  jz      short loc_180026FE4
0x180026fd8  mov     byte ptr [rcx], 0
0x180026fdb  inc     rcx
0x180026fde  sub     rax, 1
0x180026fe2  jnz     short loc_180026FD8
0x180026fe4  mov     rcx, [rsp+28h+ppMalloc]
0x180026fe9  mov     rax, [rcx]
0x180026fec  mov     rax, [rax+10h]
0x180026ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ff5  mov     rcx, rbx; pv
0x180026ff8  call    cs:__imp_CoTaskMemFree
0x180026ffe  nop
0x180026fff  add     rsp, 20h
0x180027003  pop     rbx
0x180027004  retn
```

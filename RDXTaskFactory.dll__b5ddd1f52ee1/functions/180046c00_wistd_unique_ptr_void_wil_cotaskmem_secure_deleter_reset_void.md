# wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)

- ea: `0x180046c00`
- end: `0x180046c7d`
- name: `?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046470`
- `0x1800464a0`

## callees

- `0x180046c00`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046c70`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180046c24`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180046c24`

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
0x180046c00  push    rbx
0x180046c02  sub     rsp, 20h
0x180046c06  mov     rbx, [rcx]
0x180046c09  mov     [rcx], rdx
0x180046c0c  test    rbx, rbx
0x180046c0f  jz      short loc_180046C77
0x180046c11  mov     [rsp+28h+ppMalloc], 0
0x180046c1a  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180046c1f  mov     ecx, 1; dwMemContext
0x180046c24  call    cs:__imp_CoGetMalloc
0x180046c2a  test    eax, eax
0x180046c2c  js      short loc_180046C6D
0x180046c2e  mov     rcx, [rsp+28h+ppMalloc]
0x180046c33  mov     rax, [rcx]
0x180046c36  mov     rdx, rbx
0x180046c39  mov     rax, [rax+30h]
0x180046c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046c46  jz      short loc_180046C5C
0x180046c48  mov     rcx, rbx
0x180046c4b  test    rax, rax
0x180046c4e  jz      short loc_180046C5C
0x180046c50  mov     byte ptr [rcx], 0
0x180046c53  inc     rcx
0x180046c56  sub     rax, 1
0x180046c5a  jnz     short loc_180046C50
0x180046c5c  mov     rcx, [rsp+28h+ppMalloc]
0x180046c61  mov     rax, [rcx]
0x180046c64  mov     rax, [rax+10h]
0x180046c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c6d  mov     rcx, rbx; pv
0x180046c70  call    cs:__imp_CoTaskMemFree
0x180046c76  nop
0x180046c77  add     rsp, 20h
0x180046c7b  pop     rbx
0x180046c7c  retn
```

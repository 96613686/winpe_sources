# wil::cotaskmem_secure_deleter::operator()<void>(void *)

- ea: `0x14002fe4c`
- end: `0x14002fec9`
- name: `??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z`
- size: `125`
- prototype: `void __fastcall(__int64, _BYTE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14002fedc`
- `0x14003007c`

## callees

- `0x14002fe4c`
- `0x14007d010`

## import_xrefs

- `ole32!CoGetMalloc` at `0x14002fe71`
- `ole32!CoGetMalloc` at `0x14002fe71`
- `ole32!CoTaskMemFree` at `0x14002febd`
- `ole32!CoTaskMemFree` at `0x14002febd`

## pseudocode

```c
void __fastcall wil::cotaskmem_secure_deleter::operator()<void>(__int64 a1, _BYTE *a2)
{
  __int64 v3; // rax
  _BYTE *i; // rcx
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(LPMALLOC, _BYTE *))ppMalloc->lpVtbl->GetSize)(ppMalloc, a2);
      if ( v3 != -1 )
      {
        for ( i = a2; v3; --v3 )
          *i++ = 0;
      }
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x14002fe4c  test    rdx, rdx
0x14002fe4f  jz      short locret_14002FEC8
0x14002fe51  mov     [rsp+ppMalloc], rcx
0x14002fe56  push    rbx
0x14002fe57  sub     rsp, 20h
0x14002fe5b  mov     rbx, rdx
0x14002fe5e  mov     [rsp+28h+ppMalloc], 0
0x14002fe67  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x14002fe6c  mov     ecx, 1; dwMemContext
0x14002fe71  call    cs:__imp_CoGetMalloc
0x14002fe77  test    eax, eax
0x14002fe79  js      short loc_14002FEBA
0x14002fe7b  mov     rcx, [rsp+28h+ppMalloc]
0x14002fe80  mov     rdx, rbx
0x14002fe83  mov     rax, [rcx]
0x14002fe86  mov     rax, [rax+30h]
0x14002fe8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe8f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002fe93  jz      short loc_14002FEA9
0x14002fe95  mov     rcx, rbx
0x14002fe98  test    rax, rax
0x14002fe9b  jz      short loc_14002FEA9
0x14002fe9d  mov     byte ptr [rcx], 0
0x14002fea0  inc     rcx
0x14002fea3  sub     rax, 1
0x14002fea7  jnz     short loc_14002FE9D
0x14002fea9  mov     rcx, [rsp+28h+ppMalloc]
0x14002feae  mov     rax, [rcx]
0x14002feb1  mov     rax, [rax+10h]
0x14002feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002feba  mov     rcx, rbx; pv
0x14002febd  call    cs:__imp_CoTaskMemFree
0x14002fec3  add     rsp, 20h
0x14002fec7  pop     rbx
0x14002fec8  retn
```

# wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)

- ea: `0x1800644b8`
- end: `0x180064535`
- name: `??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z`
- size: `125`
- prototype: `void __fastcall(__int64, _BYTE *)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800650a0`
- `0x180065260`
- `0x180065464`
- `0x180065700`
- `0x180066f30`
- `0x18006d5e8`
- `0x180070900`
- `0x180071060`
- `0x180071360`
- `0x180071840`
- `0x180071af0`

## callees

- `0x1800644b8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064529`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800644dd`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800644dd`

## pseudocode

```c
void __fastcall wil::cotaskmem_secure_deleter::operator()<unsigned short>(__int64 a1, _BYTE *a2)
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
0x1800644b8  test    rdx, rdx
0x1800644bb  jz      short locret_180064534
0x1800644bd  mov     [rsp+ppMalloc], rcx
0x1800644c2  push    rbx
0x1800644c3  sub     rsp, 20h
0x1800644c7  mov     rbx, rdx
0x1800644ca  mov     [rsp+28h+ppMalloc], 0
0x1800644d3  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800644d8  mov     ecx, 1; dwMemContext
0x1800644dd  call    cs:__imp_CoGetMalloc
0x1800644e3  test    eax, eax
0x1800644e5  js      short loc_180064526
0x1800644e7  mov     rcx, [rsp+28h+ppMalloc]
0x1800644ec  mov     rdx, rbx
0x1800644ef  mov     rax, [rcx]
0x1800644f2  mov     rax, [rax+30h]
0x1800644f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800644ff  jz      short loc_180064515
0x180064501  mov     rcx, rbx
0x180064504  test    rax, rax
0x180064507  jz      short loc_180064515
0x180064509  mov     byte ptr [rcx], 0
0x18006450c  inc     rcx
0x18006450f  sub     rax, 1
0x180064513  jnz     short loc_180064509
0x180064515  mov     rcx, [rsp+28h+ppMalloc]
0x18006451a  mov     rax, [rcx]
0x18006451d  mov     rax, [rax+10h]
0x180064521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064526  mov     rcx, rbx; pv
0x180064529  call    cs:__imp_CoTaskMemFree
0x18006452f  add     rsp, 20h
0x180064533  pop     rbx
0x180064534  retn
```

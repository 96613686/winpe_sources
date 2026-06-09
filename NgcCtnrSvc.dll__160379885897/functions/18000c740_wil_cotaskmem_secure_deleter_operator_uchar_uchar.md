# wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)

- ea: `0x18000c740`
- end: `0x18000c7cc`
- name: `??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z`
- size: `140`
- prototype: `void __fastcall(__int64, _BYTE *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000addc`
- `0x18000c6e8`
- `0x18000c718`
- `0x180015810`
- `0x180050b44`
- `0x18005d8fc`

## callees

- `0x18000c740`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000c765`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18000c765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::cotaskmem_secure_deleter::operator()<unsigned char>(__int64 a1, _BYTE *a2)
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
0x18000c740  test    rdx, rdx
0x18000c743  jz      short locret_18000C7BC
0x18000c745  mov     [rsp+ppMalloc], rcx
0x18000c74a  push    rbx
0x18000c74b  sub     rsp, 20h
0x18000c74f  mov     rbx, rdx
0x18000c752  mov     [rsp+28h+ppMalloc], 0
0x18000c75b  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18000c760  mov     ecx, 1; dwMemContext
0x18000c765  call    cs:__imp_CoGetMalloc
0x18000c76c  nop     dword ptr [rax+rax+00h]
0x18000c771  test    eax, eax
0x18000c773  js      short loc_18000C7A8
0x18000c775  mov     rcx, [rsp+28h+ppMalloc]
0x18000c77a  mov     rdx, rbx
0x18000c77d  mov     rax, [rcx]
0x18000c780  mov     rax, [rax+30h]
0x18000c784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c789  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c78d  jz      short loc_18000C797
0x18000c78f  mov     rcx, rbx
0x18000c792  test    rax, rax
0x18000c795  jnz     short loc_18000C7BE
0x18000c797  mov     rcx, [rsp+28h+ppMalloc]
0x18000c79c  mov     rax, [rcx]
0x18000c79f  mov     rax, [rax+10h]
0x18000c7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a8  mov     rcx, rbx; pv
0x18000c7ab  call    cs:__imp_CoTaskMemFree
0x18000c7b2  nop     dword ptr [rax+rax+00h]
0x18000c7b7  add     rsp, 20h
0x18000c7bb  pop     rbx
0x18000c7bc  retn
0x18000c7be  mov     byte ptr [rcx], 0
0x18000c7c1  inc     rcx
0x18000c7c4  sub     rax, 1
0x18000c7c8  jnz     short loc_18000C7BE
0x18000c7ca  jmp     short loc_18000C797
```

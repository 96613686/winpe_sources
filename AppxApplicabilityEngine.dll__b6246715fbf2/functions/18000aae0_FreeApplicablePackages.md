# FreeApplicablePackages

- ea: `0x18000aae0`
- end: `0x18000ab2b`
- name: `FreeApplicablePackages`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aae0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab13`

## pseudocode

```c
__int64 __fastcall FreeApplicablePackages(unsigned int a1, _QWORD **a2)
{
  __int64 i; // rdi

  for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    (*(void (__fastcall **)(_QWORD *))(*a2[i] + 16LL))(a2[i]);
  CoTaskMemFree(a2);
  return 0;
}

```

## disassembly

```asm
0x18000aae0  mov     [rsp+arg_0], rbx
0x18000aae5  mov     [rsp+arg_8], rsi
0x18000aaea  push    rdi
0x18000aaeb  sub     rsp, 20h
0x18000aaef  xor     edi, edi
0x18000aaf1  mov     rbx, rdx
0x18000aaf4  mov     esi, ecx
0x18000aaf6  test    ecx, ecx
0x18000aaf8  jz      short loc_18000AB10
0x18000aafa  mov     rcx, [rbx+rdi*8]
0x18000aafe  mov     rax, [rcx]
0x18000ab01  mov     rax, [rax+10h]
0x18000ab05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab0a  inc     edi
0x18000ab0c  cmp     edi, esi
0x18000ab0e  jb      short loc_18000AAFA
0x18000ab10  mov     rcx, rbx; pv
0x18000ab13  call    cs:__imp_CoTaskMemFree
0x18000ab19  mov     rbx, [rsp+28h+arg_0]
0x18000ab1e  xor     eax, eax
0x18000ab20  mov     rsi, [rsp+28h+arg_8]
0x18000ab25  add     rsp, 20h
0x18000ab29  pop     rdi
0x18000ab2a  retn
```

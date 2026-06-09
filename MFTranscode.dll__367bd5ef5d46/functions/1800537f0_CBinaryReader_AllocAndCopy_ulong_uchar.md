# CBinaryReader::_AllocAndCopy(ulong,uchar * *)

- ea: `0x1800537f0`
- end: `0x180053842`
- name: `?_AllocAndCopy@CBinaryReader@@IEAAJKPEAPEAE@Z`
- size: `82`
- prototype: `int(CBinaryReader *__hidden this, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050e70`

## callees

- `0x1800537f0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053809`

## pseudocode

```c
__int64 __fastcall CBinaryReader::_AllocAndCopy(CBinaryReader *this, unsigned int a2, unsigned __int8 **a3)
{
  unsigned __int8 *v6; // rax

  v6 = (unsigned __int8 *)CoTaskMemAlloc(a2);
  *a3 = v6;
  if ( v6 )
    return (**(__int64 (__fastcall ***)(CBinaryReader *, unsigned __int8 *, _QWORD))this)(this, v6, a2);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x1800537f0  mov     [rsp+arg_0], rbx
0x1800537f5  mov     [rsp+arg_8], rsi
0x1800537fa  push    rdi
0x1800537fb  sub     rsp, 20h
0x1800537ff  mov     rsi, rcx
0x180053802  mov     edi, edx
0x180053804  mov     ecx, edx; cb
0x180053806  mov     rbx, r8
0x180053809  call    cs:__imp_CoTaskMemAlloc
0x18005380f  mov     [rbx], rax
0x180053812  mov     rdx, rax
0x180053815  test    rax, rax
0x180053818  jnz     short loc_180053821
0x18005381a  mov     eax, 8007000Eh
0x18005381f  jmp     short loc_180053832
0x180053821  mov     rax, [rsi]
0x180053824  mov     r8d, edi
0x180053827  mov     rcx, rsi
0x18005382a  mov     rax, [rax]
0x18005382d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053832  mov     rbx, [rsp+28h+arg_0]
0x180053837  mov     rsi, [rsp+28h+arg_8]
0x18005383c  add     rsp, 20h
0x180053840  pop     rdi
0x180053841  retn
```

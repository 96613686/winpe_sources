# ATL::CComSafeArray<uchar,17>::~CComSafeArray<uchar,17>(void)

- ea: `0x14000928c`
- end: `0x1400092ce`
- name: `??1?$CComSafeArray@E$0BB@@ATL@@QEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019a7d`
- `0x140019a8f`

## callees

- `0x14000928c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400092b0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400092b0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000929d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14000929d`

## pseudocode

```c
void __fastcall ATL::CComSafeArray<unsigned char,17>::~CComSafeArray<unsigned char,17>(SAFEARRAY **a1)
{
  SAFEARRAY *v2; // rcx

  v2 = *a1;
  if ( v2 && SafeArrayUnlock(v2) >= 0 && SafeArrayDestroy(*a1) >= 0 )
    *a1 = 0;
}

```

## disassembly

```asm
0x14000928c  push    rbx
0x14000928e  sub     rsp, 20h
0x140009292  mov     rbx, rcx
0x140009295  mov     rcx, [rcx]; psa
0x140009298  test    rcx, rcx
0x14000929b  jz      short loc_1400092C7
0x14000929d  call    cs:__imp_SafeArrayUnlock
0x1400092a4  nop     dword ptr [rax+rax+00h]
0x1400092a9  test    eax, eax
0x1400092ab  js      short loc_1400092C7
0x1400092ad  mov     rcx, [rbx]; psa
0x1400092b0  call    cs:__imp_SafeArrayDestroy
0x1400092b7  nop     dword ptr [rax+rax+00h]
0x1400092bc  test    eax, eax
0x1400092be  js      short loc_1400092C7
0x1400092c0  mov     qword ptr [rbx], 0
0x1400092c7  add     rsp, 20h
0x1400092cb  pop     rbx
0x1400092cc  retn
```

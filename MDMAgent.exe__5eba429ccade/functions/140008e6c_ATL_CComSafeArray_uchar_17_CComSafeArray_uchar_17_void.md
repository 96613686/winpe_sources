# ATL::CComSafeArray<uchar,17>::~CComSafeArray<uchar,17>(void)

- ea: `0x140008e6c`
- end: `0x140008ea1`
- name: `??1?$CComSafeArray@E$0BB@@ATL@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(SAFEARRAY **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018d1c`
- `0x140018d2e`

## callees

- `0x140008e6c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140008e8a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140008e8a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140008e7d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140008e7d`

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
0x140008e6c  push    rbx
0x140008e6e  sub     rsp, 20h
0x140008e72  mov     rbx, rcx
0x140008e75  mov     rcx, [rcx]; psa
0x140008e78  test    rcx, rcx
0x140008e7b  jz      short loc_140008E9B
0x140008e7d  call    cs:__imp_SafeArrayUnlock
0x140008e83  test    eax, eax
0x140008e85  js      short loc_140008E9B
0x140008e87  mov     rcx, [rbx]; psa
0x140008e8a  call    cs:__imp_SafeArrayDestroy
0x140008e90  test    eax, eax
0x140008e92  js      short loc_140008E9B
0x140008e94  mov     qword ptr [rbx], 0
0x140008e9b  add     rsp, 20h
0x140008e9f  pop     rbx
0x140008ea0  retn
```

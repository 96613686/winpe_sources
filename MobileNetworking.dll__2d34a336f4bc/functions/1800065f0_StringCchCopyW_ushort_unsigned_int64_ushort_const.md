# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800065f0`
- end: `0x180006627`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `55`
- prototype: `HRESULT __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005910`
- `0x180006340`
- `0x18000fe38`
- `0x180011300`

## callees

- `0x1800065f0`
- `0x1800066b0`

## pseudocode

```c
HRESULT __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  HRESULT result; // eax
  size_t v4; // [rsp+20h] [rbp-18h]

  if ( !a2 )
    return -2147024809;
  if ( a2 <= 0x7FFFFFFF )
    return StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v4);
  result = -2147024809;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800065f0  sub     rsp, 38h
0x1800065f4  test    rdx, rdx
0x1800065f7  jz      short loc_18000660F
0x1800065f9  cmp     rdx, 7FFFFFFFh
0x180006600  ja      short loc_180006620
0x180006602  mov     r9, r8; pszSrc
0x180006605  call    StringCopyWorkerW
0x18000660a  add     rsp, 38h
0x18000660e  retn
0x18000660f  mov     eax, 80070057h
0x180006614  test    rdx, rdx
0x180006617  jz      short loc_18000660A
0x180006619  xor     edx, edx
0x18000661b  mov     [rcx], dx
0x18000661e  jmp     short loc_18000660A
0x180006620  mov     eax, 80070057h
0x180006625  jmp     short loc_180006619
```

# IISCryptoCreateCleartextBlob

- ea: `0x180004808`
- end: `0x180004869`
- name: `IISCryptoCreateCleartextBlob`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001ce0`
- `0x180001f30`
- `0x180002a3c`
- `0x180005f7c`
- `0x180006104`
- `0x180006704`
- `0x180006ad8`

## callees

- `0x180004808`
- `0x1800083d2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000482c`
- `ole32!CoTaskMemAlloc` at `0x18000482c`

## pseudocode

```c
__int64 __fastcall IISCryptoCreateCleartextBlob(_QWORD *a1, const void *a2, unsigned int a3)
{
  unsigned __int64 v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 result; // rax

  v6 = a3 + 8LL;
  if ( v6 > 0xFFFFFFFF )
    return 2147942414LL;
  v7 = CoTaskMemAlloc((unsigned int)v6);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *v7 = 1648583497;
  v7[1] = a3;
  memcpy_0(v7 + 2, a2, a3);
  result = 0;
  *a1 = v8;
  return result;
}

```

## disassembly

```asm
0x180004808  push    rbx
0x18000480a  push    rbp
0x18000480b  push    rsi
0x18000480c  push    rdi
0x18000480d  push    r14
0x18000480f  sub     rsp, 20h
0x180004813  mov     edi, r8d
0x180004816  mov     r14, rcx
0x180004819  mov     ecx, 0FFFFFFFFh
0x18000481e  mov     rbp, rdx
0x180004821  lea     rax, [rdi+8]
0x180004825  cmp     rax, rcx
0x180004828  ja      short loc_180004859
0x18000482a  mov     ecx, eax; cb
0x18000482c  call    cs:__imp_CoTaskMemAlloc
0x180004832  mov     rbx, rax
0x180004835  test    rax, rax
0x180004838  jz      short loc_180004859
0x18000483a  lea     rcx, [rax+8]; void *
0x18000483e  mov     dword ptr [rax], 62436349h
0x180004844  mov     r8d, edi; Size
0x180004847  mov     [rax+4], edi
0x18000484a  mov     rdx, rbp; Src
0x18000484d  call    memcpy_0
0x180004852  xor     eax, eax
0x180004854  mov     [r14], rbx
0x180004857  jmp     short loc_18000485E
0x180004859  mov     eax, 8007000Eh
0x18000485e  add     rsp, 20h
0x180004862  pop     r14
0x180004864  pop     rdi
0x180004865  pop     rsi
0x180004866  pop     rbp
0x180004867  pop     rbx
0x180004868  retn
```

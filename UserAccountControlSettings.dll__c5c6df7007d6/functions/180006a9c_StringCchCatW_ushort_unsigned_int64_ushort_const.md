# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006a9c`
- end: `0x180006ae8`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `76`
- prototype: `int __fastcall(unsigned __int16 *, size_t, const unsigned __int16 *, size_t)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004fb0`
- `0x180006ce0`
- `0x180009b0c`

## callees

- `0x180006a9c`
- `0x180006bc4`
- `0x180006c8c`

## pseudocode

```c
int __fastcall StringCchCatW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, size_t a4)
{
  int result; // eax
  size_t *v7; // r8
  __int64 v8; // r11
  size_t v9; // [rsp+20h] [rbp-18h]
  size_t pcchDestLength; // [rsp+58h] [rbp+20h] BYREF

  pcchDestLength = 0;
  result = StringValidateDestAndLengthW(a1, a2, &pcchDestLength, a4);
  if ( result >= 0 )
    return StringCopyWorkerW(&a1[pcchDestLength], v8 - pcchDestLength, v7, a3, v9);
  return result;
}

```

## disassembly

```asm
0x180006a9c  mov     [rsp+arg_0], rbx
0x180006aa1  push    rdi
0x180006aa2  sub     rsp, 30h
0x180006aa6  mov     rdi, r8
0x180006aa9  mov     [rsp+38h+pcchDestLength], 0
0x180006ab2  lea     r8, [rsp+38h+pcchDestLength]; pcchDestLength
0x180006ab7  mov     r11, rdx
0x180006aba  mov     rbx, rcx
0x180006abd  call    StringValidateDestAndLengthW
0x180006ac2  test    eax, eax
0x180006ac4  js      short loc_180006ADD
0x180006ac6  mov     rax, [rsp+38h+pcchDestLength]
0x180006acb  mov     r9, rdi; pszSrc
0x180006ace  sub     r11, rax
0x180006ad1  mov     rdx, r11; cchDest
0x180006ad4  lea     rcx, [rbx+rax*2]; pszDest
0x180006ad8  call    StringCopyWorkerW
0x180006add  mov     rbx, [rsp+38h+arg_0]
0x180006ae2  add     rsp, 30h
0x180006ae6  pop     rdi
0x180006ae7  retn
```

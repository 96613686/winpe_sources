# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006630`
- end: `0x18000669b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `HRESULT __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005910`
- `0x180006000`
- `0x180006340`
- `0x18000fe38`
- `0x180011300`

## callees

- `0x180006630`
- `0x1800066b0`

## pseudocode

```c
HRESULT __fastcall StringCchCatW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  size_t v3; // r9
  unsigned __int16 *v4; // rax
  size_t v6; // [rsp+20h] [rbp-18h]

  if ( a2 - 1 > 0x7FFFFFFE )
    return -2147024809;
  v3 = a2;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  if ( v3 )
    return StringCopyWorkerW(&a1[a2 - v3], v3, a3, (STRSAFE_PCNZWCH)a3, v6);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x180006630  sub     rsp, 38h
0x180006634  lea     rax, [rdx-1]
0x180006638  mov     r10, rdx
0x18000663b  mov     r11, rcx
0x18000663e  cmp     rax, 7FFFFFFEh
0x180006644  ja      short loc_180006694
0x180006646  mov     r9, rdx
0x180006649  mov     rax, rcx
0x18000664c  nop     dword ptr [rax+00h]
0x180006650  cmp     word ptr [rax], 0
0x180006654  jz      short loc_180006660
0x180006656  add     rax, 2
0x18000665a  sub     r9, 1
0x18000665e  jnz     short loc_180006650
0x180006660  xor     eax, eax
0x180006662  mov     rcx, r10
0x180006665  sub     rcx, r9
0x180006668  mov     edx, 80070057h
0x18000666d  test    r9, r9
0x180006670  cmovz   rcx, rax
0x180006674  cmovnz  edx, eax
0x180006677  jz      short loc_180006690
0x180006679  sub     r10, rcx
0x18000667c  mov     r9, r8; pszSrc
0x18000667f  mov     rdx, r10; cchDest
0x180006682  lea     rcx, [r11+rcx*2]; pszDest
0x180006686  call    StringCopyWorkerW
0x18000668b  add     rsp, 38h
0x18000668f  retn
0x180006690  mov     eax, edx
0x180006692  jmp     short loc_18000668B
0x180006694  mov     edx, 80070057h
0x180006699  jmp     short loc_180006690
```

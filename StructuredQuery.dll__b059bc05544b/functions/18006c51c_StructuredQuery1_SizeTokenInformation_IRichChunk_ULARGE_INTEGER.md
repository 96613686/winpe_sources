# StructuredQuery1::SizeTokenInformation(IRichChunk *,_ULARGE_INTEGER *)

- ea: `0x18006c51c`
- end: `0x18006c5b5`
- name: `?SizeTokenInformation@StructuredQuery1@@YAJPEAUIRichChunk@@PEAT_ULARGE_INTEGER@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, struct IRichChunk *, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062b30`

## callees

- `0x18006c4f8`
- `0x18006c51c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c58f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006c59a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006c59a`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SizeTokenInformation(
        StructuredQuery1 *this,
        struct IRichChunk *a2,
        union _ULARGE_INTEGER *a3)
{
  int v3; // edi
  __int64 v5; // rbx
  const wchar_t *v6; // rdx
  unsigned int v7; // eax
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v5 = 1;
  if ( this )
  {
    pv = 0;
    *(_OWORD *)pvar = 0;
    v10 = 0;
    v3 = (*(__int64 (__fastcall **)(StructuredQuery1 *, _QWORD, _QWORD, LPVOID *, PROPVARIANT *))(*(_QWORD *)this + 24LL))(
           this,
           0,
           0,
           &pv,
           pvar);
    if ( v3 >= 0 )
    {
      v7 = StructuredQuery1::SizePWSTR((StructuredQuery1 *)pv, v6);
      v5 = v7 + 9LL;
      if ( LOWORD(pvar[0]) == 3 )
        v5 = v7 + 13LL;
      CoTaskMemFree(pv);
      PropVariantClear(pvar);
    }
  }
  a2->lpVtbl = (struct IRichChunkVtbl *)v5;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006c51c  mov     r11, rsp
0x18006c51f  mov     [r11+10h], rbx
0x18006c523  mov     [r11+18h], rsi
0x18006c527  push    rdi
0x18006c528  sub     rsp, 50h
0x18006c52c  xor     edi, edi
0x18006c52e  mov     rsi, rdx
0x18006c531  lea     ebx, [rdi+1]
0x18006c534  test    rcx, rcx
0x18006c537  jz      short loc_18006C5A0
0x18006c539  xor     eax, eax
0x18006c53b  mov     [r11+8], rdi
0x18006c53f  lea     rdx, [r11-28h]
0x18006c543  xorps   xmm0, xmm0
0x18006c546  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x18006c54b  mov     [r11-18h], rax
0x18006c54f  lea     r9, [r11+8]
0x18006c553  mov     rax, [rcx]
0x18006c556  xor     r8d, r8d
0x18006c559  mov     [r11-38h], rdx
0x18006c55d  xor     edx, edx
0x18006c55f  mov     rax, [rax+18h]
0x18006c563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c568  mov     edi, eax
0x18006c56a  test    eax, eax
0x18006c56c  js      short loc_18006C5A0
0x18006c56e  mov     rcx, [rsp+58h+pv]; this
0x18006c573  call    ?SizePWSTR@StructuredQuery1@@YAKPEB_W@Z; StructuredQuery1::SizePWSTR(wchar_t const *)
0x18006c578  mov     ebx, eax
0x18006c57a  add     rbx, 9
0x18006c57e  cmp     word ptr [rsp+58h+pvar], 3
0x18006c584  jnz     short loc_18006C58A
0x18006c586  add     rbx, 4
0x18006c58a  mov     rcx, [rsp+58h+pv]; pv
0x18006c58f  call    cs:__imp_CoTaskMemFree
0x18006c595  lea     rcx, [rsp+58h+pvar]; pvar
0x18006c59a  call    cs:__imp_PropVariantClear
0x18006c5a0  mov     [rsi], rbx
0x18006c5a3  mov     eax, edi
0x18006c5a5  mov     rbx, [rsp+58h+arg_8]
0x18006c5aa  mov     rsi, [rsp+58h+arg_10]
0x18006c5af  add     rsp, 50h
0x18006c5b3  pop     rdi
0x18006c5b4  retn
```

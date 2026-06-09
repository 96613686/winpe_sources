# _ExtensionClassFromIDAssetPair(ushort const *,ushort * *)

- ea: `0x180032438`
- end: `0x1800324d3`
- name: `?_ExtensionClassFromIDAssetPair@@YAJPEBGPEAPEAG@Z`
- size: `155`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800327a4`

## callees

- `0x180032000`
- `0x180032438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180032457`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180032457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032491`

## pseudocode

```c
__int64 __fastcall _ExtensionClassFromIDAssetPair(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  wchar_t *v4; // rax
  const unsigned __int16 *v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rcx
  unsigned __int16 **v10; // [rsp+20h] [rbp-58h]
  unsigned __int64 *v11; // [rsp+28h] [rbp-50h]
  unsigned int v12; // [rsp+30h] [rbp-48h]

  *a2 = 0;
  v3 = -2147023728;
  v4 = wcschr(a1, 0x2Cu);
  if ( v4 )
  {
    v5 = v4 + 1;
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = v6 + 1;
    *a2 = 0;
    if ( v6 + 1 >= v6 && is_mul_ok(v7, 2u) )
    {
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
      *a2 = v8;
      v3 = v8 == 0 ? 0x8007000E : 0;
      if ( v8 )
        StringCchCopyNExW(v8, v6 + 1, v5, v6, v10, v11, v12);
    }
    else
    {
      return (unsigned int)-2147024362;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180032438  push    rbx
0x18003243a  push    rbp
0x18003243b  push    rsi
0x18003243c  push    rdi
0x18003243d  push    r14
0x18003243f  push    r15
0x180032441  sub     rsp, 48h
0x180032445  xor     r15d, r15d
0x180032448  mov     r14, rdx
0x18003244b  mov     [rdx], r15
0x18003244e  mov     ebx, 80070490h
0x180032453  lea     edx, [r15+2Ch]; Ch
0x180032457  call    cs:__imp_wcschr
0x18003245d  test    rax, rax
0x180032460  jz      short loc_1800324C4
0x180032462  lea     rbp, [rax+2]
0x180032466  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003246a  inc     rdi
0x18003246d  cmp     [rbp+rdi*2+0], r15w
0x180032473  jnz     short loc_18003246A
0x180032475  lea     rsi, [rdi+1]
0x180032479  mov     [r14], r15
0x18003247c  cmp     rsi, rdi
0x18003247f  jb      short loc_1800324BF
0x180032481  mov     eax, 2
0x180032486  mul     rsi
0x180032489  test    rdx, rdx
0x18003248c  jnz     short loc_1800324BF
0x18003248e  mov     rcx, rax; cb
0x180032491  call    cs:__imp_CoTaskMemAlloc
0x180032497  mov     rcx, rax; unsigned __int16 *
0x18003249a  mov     [r14], rax
0x18003249d  neg     rax
0x1800324a0  sbb     ebx, ebx
0x1800324a2  not     ebx
0x1800324a4  and     ebx, 8007000Eh
0x1800324aa  test    rcx, rcx
0x1800324ad  jz      short loc_1800324C4
0x1800324af  mov     r9, rdi; unsigned __int64
0x1800324b2  mov     r8, rbp; unsigned __int16 *
0x1800324b5  mov     rdx, rsi; unsigned __int64
0x1800324b8  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800324bd  jmp     short loc_1800324C4
0x1800324bf  mov     ebx, 80070216h
0x1800324c4  mov     eax, ebx
0x1800324c6  add     rsp, 48h
0x1800324ca  pop     r15
0x1800324cc  pop     r14
0x1800324ce  pop     rdi
0x1800324cf  pop     rsi
0x1800324d0  pop     rbp
0x1800324d1  pop     rbx
0x1800324d2  retn
```

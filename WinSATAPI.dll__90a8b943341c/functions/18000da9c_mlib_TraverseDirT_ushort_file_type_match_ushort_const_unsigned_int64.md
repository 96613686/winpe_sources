# mlib::TraverseDirT<ushort>::file_type_match(ushort const *,unsigned __int64)

- ea: `0x18000da9c`
- end: `0x18000dbb3`
- name: `?file_type_match@?$TraverseDirT@G@mlib@@AEBA_NPEBG_K@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd4c`

## callees

- `0x18000da9c`
- `0x18000dc94`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db9c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db9c`

## pseudocode

```c
bool __fastcall mlib::TraverseDirT<unsigned short>::file_type_match(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  const WCHAR *lpString2; // rdi
  unsigned __int64 v5; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rax

  lpString2 = 0;
  v5 = *(_QWORD *)(a1 + 576);
  if ( v5 && a3 < v5 )
  {
    v8 = (_QWORD *)(a1 + 592);
    v9 = 40 * a3;
    if ( *(_BYTE *)(40 * a3 + *v8 + 33) )
      return 1;
  }
  else
  {
    v8 = (_QWORD *)(a1 + 592);
    v9 = 40 * a3;
  }
  if ( !v5 )
    return 1;
  if ( a3 >= v5 )
    return 1;
  if ( *(_QWORD *)(*v8 + v9 + 24) != 3 )
    return 1;
  v11 = a2 - 2;
  v12 = a2 - 2 + 2 * mlib::TRTraitsT<unsigned short>::CStrlen(a2);
  if ( *(_WORD *)v12 == 46 )
    return 1;
  while ( v12 > v11 )
  {
    if ( *(_WORD *)v12 == 46 )
      goto LABEL_15;
    v12 -= 2LL;
  }
  if ( v12 == v11 )
    return 1;
LABEL_15:
  v13 = *(_QWORD *)(a1 + 576);
  if ( v13 )
  {
    if ( a3 < v13 )
      lpString2 = *(const WCHAR **)(*(_QWORD *)(a1 + 592) + 40 * a3 + 8);
  }
  return CompareStringW(0x400u, 0x1001u, (PCNZWCH)(v12 + 2), -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x18000da9c  mov     rax, rsp
0x18000da9f  mov     [rax+8], rbx
0x18000daa3  mov     [rax+10h], rbp
0x18000daa7  mov     [rax+18h], rsi
0x18000daab  mov     [rax+20h], rdi
0x18000daaf  push    r14
0x18000dab1  sub     rsp, 30h
0x18000dab5  mov     rbx, r8
0x18000dab8  xor     edi, edi
0x18000daba  mov     r8, [rcx+240h]
0x18000dac1  mov     r14, rdx
0x18000dac4  mov     rbp, rcx
0x18000dac7  test    r8, r8
0x18000daca  jz      short loc_18000DB0C
0x18000dacc  cmp     rbx, r8
0x18000dacf  jnb     short loc_18000DB0C
0x18000dad1  add     rcx, 250h
0x18000dad8  lea     rax, [rbx+rbx*4]
0x18000dadc  lea     rdx, ds:0[rax*8]
0x18000dae4  mov     rax, [rcx]
0x18000dae7  cmp     [rdx+rax+21h], dil
0x18000daec  jz      short loc_18000DB1B
0x18000daee  mov     al, 1
0x18000daf0  mov     rbx, [rsp+38h+arg_0]
0x18000daf5  mov     rbp, [rsp+38h+arg_8]
0x18000dafa  mov     rsi, [rsp+38h+arg_10]
0x18000daff  mov     rdi, [rsp+38h+arg_18]
0x18000db04  add     rsp, 30h
0x18000db08  pop     r14
0x18000db0a  retn
0x18000db0c  add     rcx, 250h
0x18000db13  lea     rdx, [rbx+rbx*4]
0x18000db17  shl     rdx, 3
0x18000db1b  test    r8, r8
0x18000db1e  jz      short loc_18000DAEE
0x18000db20  cmp     rbx, r8
0x18000db23  jnb     short loc_18000DAEE
0x18000db25  mov     rax, [rcx]
0x18000db28  cmp     qword ptr [rax+rdx+18h], 3
0x18000db2e  jnz     short loc_18000DAEE
0x18000db30  mov     rcx, r14
0x18000db33  lea     rsi, [r14-2]
0x18000db37  call    ?CStrlen@?$TRTraitsT@G@mlib@@SA_KPEBG_K@Z; mlib::TRTraitsT<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18000db3c  lea     r8, [r14-2]
0x18000db40  lea     r8, [r8+rax*2]
0x18000db44  cmp     word ptr [r8], 2Eh ; '.'
0x18000db49  jz      short loc_18000DAEE
0x18000db4b  jmp     short loc_18000DB58
0x18000db4d  cmp     word ptr [r8], 2Eh ; '.'
0x18000db52  jz      short loc_18000DB5F
0x18000db54  sub     r8, 2
0x18000db58  cmp     r8, rsi
0x18000db5b  ja      short loc_18000DB4D
0x18000db5d  jz      short loc_18000DAEE
0x18000db5f  mov     rax, [rbp+240h]
0x18000db66  test    rax, rax
0x18000db69  jz      short loc_18000DB80
0x18000db6b  cmp     rbx, rax
0x18000db6e  jnb     short loc_18000DB80
0x18000db70  mov     rax, [rbp+250h]
0x18000db77  lea     rcx, [rbx+rbx*4]
0x18000db7b  mov     rdi, [rax+rcx*8+8]
0x18000db80  or      r9d, 0FFFFFFFFh; cchCount1
0x18000db84  add     r8, 2; lpString1
0x18000db88  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18000db8d  mov     edx, 1001h; dwCmpFlags
0x18000db92  mov     ecx, 400h; Locale
0x18000db97  mov     [rsp+38h+lpString2], rdi; lpString2
0x18000db9c  call    cs:__imp_CompareStringW
0x18000dba3  nop     dword ptr [rax+rax+00h]
0x18000dba8  cmp     eax, 2
0x18000dbab  setz    al
0x18000dbae  jmp     loc_18000DAF0
```

# CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(tagARPITEM const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x18001b000`
- end: `0x18001b1cc`
- name: `?s_CreateItemID@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAJPEFBUtagARPITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(_OWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800158c0`
- `0x180018d94`
- `0x180019340`

## callees

- `0x180005406`
- `0x18001b000`
- `0x1800582a2`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b17a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b17a`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(
        _OWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v4; // eax
  int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rax
  _OWORD *v12; // rcx
  __int128 v13; // xmm1
  __int16 v14; // si
  void *v15; // rax
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+68h] [rbp+38h] BYREF
  __int64 v19; // [rsp+70h] [rbp+40h] BYREF

  v4 = 0;
  *a3 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
  {
LABEL_5:
    v9 = (unsigned int)(v4 + 1068) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 1068) + 2LL);
    }
    else
    {
      v14 = v4 + 1078;
      if ( (unsigned __int64)(unsigned int)(v4 + 1068) + 10 > 0x10001 )
        goto LABEL_18;
      v15 = CoTaskMemAlloc((unsigned int)(v4 + 1068) + 10LL);
      v10 = (__int64)v15;
      if ( v15 )
      {
        memset_0(v15, 0, v9 + 8);
        *(_WORD *)(v10 + 4) = v9;
        *(_WORD *)v10 = v14 - 2;
        goto LABEL_8;
      }
    }
    if ( v10 )
    {
LABEL_8:
      *(_DWORD *)(v10 + 6) = 1230000705;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 1060;
      if ( a1 )
      {
        v11 = 8;
        v12 = (_OWORD *)(v10 + 14);
        do
        {
          *v12 = *a1;
          v12[1] = a1[1];
          v12[2] = a1[2];
          v12[3] = a1[3];
          v12[4] = a1[4];
          v12[5] = a1[5];
          v12[6] = a1[6];
          v13 = a1[7];
          a1 += 8;
          v12[7] = v13;
          v12 += 8;
          --v11;
        }
        while ( v11 );
        *v12 = *a1;
        v12[1] = a1[1];
        *((_DWORD *)v12 + 8) = *((_DWORD *)a1 + 8);
      }
      if ( Src )
        memcpy_0((void *)(v10 + 1074), Src, (unsigned int)Size);
      *a3 = v10;
      v8 = 0;
      goto LABEL_19;
    }
LABEL_18:
    v8 = -2147024882;
LABEL_19:
    CoTaskMemFree(Src);
    return (unsigned int)v8;
  }
  v19 = 0;
  v8 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v19);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v19 + 40LL))(v19, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v8 >= 0 )
    {
      v4 = Size;
      goto LABEL_5;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b000  mov     [rsp-28h+arg_0], rbx
0x18001b005  push    rbp
0x18001b006  push    rsi
0x18001b007  push    rdi
0x18001b008  push    r14
0x18001b00a  push    r15
0x18001b00c  mov     rbp, rsp
0x18001b00f  sub     rsp, 30h
0x18001b013  xor     eax, eax
0x18001b015  mov     qword ptr [r8], 0
0x18001b01c  mov     [rbp+Src], 0
0x18001b024  mov     rsi, r9
0x18001b027  mov     dword ptr [rbp+Size], eax
0x18001b02a  mov     r15, r8
0x18001b02d  mov     r10, rdx
0x18001b030  mov     rdi, rcx
0x18001b033  test    rdx, rdx
0x18001b036  jz      short loc_18001B094
0x18001b038  mov     [rbp+arg_10], rax
0x18001b03c  lea     r8, [rbp+arg_10]
0x18001b040  mov     rax, [rdx]
0x18001b043  mov     rcx, r10
0x18001b046  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18001b04d  mov     rax, [rax]
0x18001b050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b055  mov     ebx, eax
0x18001b057  test    eax, eax
0x18001b059  js      loc_18001B1B9
0x18001b05f  mov     rcx, [rbp+arg_10]
0x18001b063  lea     r8, [rbp+Size]
0x18001b067  lea     rdx, [rbp+Src]
0x18001b06b  mov     rax, [rcx]
0x18001b06e  mov     rax, [rax+28h]
0x18001b072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b077  mov     rcx, [rbp+arg_10]
0x18001b07b  mov     ebx, eax
0x18001b07d  mov     rax, [rcx]
0x18001b080  mov     rax, [rax+10h]
0x18001b084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b089  test    ebx, ebx
0x18001b08b  js      loc_18001B1B9
0x18001b091  mov     eax, dword ptr [rbp+Size]
0x18001b094  lea     r14d, [rax+42Ch]
0x18001b09b  add     r14, 2
0x18001b09f  test    rsi, rsi
0x18001b0a2  jz      loc_18001B16A
0x18001b0a8  mov     rax, [rsi]
0x18001b0ab  mov     rdx, r14
0x18001b0ae  mov     rcx, rsi
0x18001b0b1  mov     rax, [rax+18h]
0x18001b0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0ba  mov     rbx, rax
0x18001b0bd  test    rbx, rbx
0x18001b0c0  jz      loc_18001B1AA
0x18001b0c6  mov     dword ptr [rbx+6], 49505241h
0x18001b0cd  movzx   eax, word ptr [rbp+Size]
0x18001b0d1  mov     [rbx+0Ah], ax
0x18001b0d5  mov     word ptr [rbx+0Ch], 424h
0x18001b0db  test    rdi, rdi
0x18001b0de  jz      short loc_18001B14A
0x18001b0e0  mov     eax, 8
0x18001b0e5  lea     rcx, [rbx+0Eh]
0x18001b0e9  lea     edx, [rax+78h]
0x18001b0ec  movups  xmm0, xmmword ptr [rdi]
0x18001b0ef  movups  xmmword ptr [rcx], xmm0
0x18001b0f2  movups  xmm1, xmmword ptr [rdi+10h]
0x18001b0f6  movups  xmmword ptr [rcx+10h], xmm1
0x18001b0fa  movups  xmm0, xmmword ptr [rdi+20h]
0x18001b0fe  movups  xmmword ptr [rcx+20h], xmm0
0x18001b102  movups  xmm1, xmmword ptr [rdi+30h]
0x18001b106  movups  xmmword ptr [rcx+30h], xmm1
0x18001b10a  movups  xmm0, xmmword ptr [rdi+40h]
0x18001b10e  movups  xmmword ptr [rcx+40h], xmm0
0x18001b112  movups  xmm1, xmmword ptr [rdi+50h]
0x18001b116  movups  xmmword ptr [rcx+50h], xmm1
0x18001b11a  movups  xmm0, xmmword ptr [rdi+60h]
0x18001b11e  movups  xmmword ptr [rcx+60h], xmm0
0x18001b122  movups  xmm1, xmmword ptr [rdi+70h]
0x18001b126  add     rdi, rdx
0x18001b129  movups  xmmword ptr [rcx+70h], xmm1
0x18001b12d  add     rcx, rdx
0x18001b130  sub     rax, 1
0x18001b134  jnz     short loc_18001B0EC
0x18001b136  movups  xmm0, xmmword ptr [rdi]
0x18001b139  movups  xmmword ptr [rcx], xmm0
0x18001b13c  movups  xmm1, xmmword ptr [rdi+10h]
0x18001b140  movups  xmmword ptr [rcx+10h], xmm1
0x18001b144  mov     eax, [rdi+20h]
0x18001b147  mov     [rcx+20h], eax
0x18001b14a  mov     rdx, [rbp+Src]; Src
0x18001b14e  test    rdx, rdx
0x18001b151  jz      short loc_18001B163
0x18001b153  mov     r8d, dword ptr [rbp+Size]; Size
0x18001b157  lea     rcx, [rbx+432h]; void *
0x18001b15e  call    memcpy_0
0x18001b163  mov     [r15], rbx
0x18001b166  xor     ebx, ebx
0x18001b168  jmp     short loc_18001B1AF
0x18001b16a  lea     rsi, [r14+8]
0x18001b16e  cmp     rsi, 10001h
0x18001b175  ja      short loc_18001B1AA
0x18001b177  mov     rcx, rsi; cb
0x18001b17a  call    cs:__imp_CoTaskMemAlloc
0x18001b180  mov     rbx, rax
0x18001b183  test    rax, rax
0x18001b186  jz      loc_18001B0BD
0x18001b18c  mov     r8, rsi; Size
0x18001b18f  xor     edx, edx; Val
0x18001b191  mov     rcx, rax; void *
0x18001b194  call    memset_0
0x18001b199  sub     si, 2
0x18001b19d  mov     [rbx+4], r14w
0x18001b1a2  mov     [rbx], si
0x18001b1a5  jmp     loc_18001B0C6
0x18001b1aa  mov     ebx, 8007000Eh
0x18001b1af  mov     rcx, [rbp+Src]; pv
0x18001b1b3  call    cs:__imp_CoTaskMemFree
0x18001b1b9  mov     eax, ebx
0x18001b1bb  mov     rbx, [rsp+30h+arg_0]
0x18001b1c0  add     rsp, 30h
0x18001b1c4  pop     r15
0x18001b1c6  pop     r14
0x18001b1c8  pop     rdi
0x18001b1c9  pop     rsi
0x18001b1ca  pop     rbp
0x18001b1cb  retn
```

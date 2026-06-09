# AipkGetAppxFqbnAttributes

- ea: `0x140028a6c`
- end: `0x140028bb6`
- name: `AipkGetAppxFqbnAttributes`
- size: `330`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140036af0`

## callees

- `0x1400272a8`
- `0x14002866c`
- `0x140028964`
- `0x140028a6c`
- `0x140028f80`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!ExQueryFastCacheDevLicense` at `0x140028b36`
- `ntoskrnl!ExQueryFastCacheDevLicense` at `0x140028b36`

## pseudocode

```c
__int64 __fastcall AipkGetAppxFqbnAttributes(const UNICODE_STRING *a1, char a2, _BYTE *a3, _QWORD *a4)
{
  int RegCache; // ebx
  int v8; // eax
  size_t Size; // [rsp+28h] [rbp-48h]
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-28h] BYREF
  int v13[4]; // [rsp+50h] [rbp-20h] BYREF
  int v14[4]; // [rsp+60h] [rbp-10h] BYREF
  size_t v15; // [rsp+98h] [rbp+28h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v16 = 0;
  v12 = 0;
  LODWORD(v15) = 0;
  Src = 0;
  *a4 = 0;
  *(_OWORD *)v13 = 0;
  *(_OWORD *)v14 = 0;
  if ( !a2 )
  {
    RegCache = AipkFindAndReturnEntryFromAppxCache(a1);
    if ( RegCache >= 0 )
    {
      *a3 = 0;
LABEL_12:
      *a4 = v16;
      goto LABEL_13;
    }
    *a3 = 1;
    RegCache = AipkReadRegCache((int)a1, (int)&v16);
    if ( RegCache >= 0 )
      goto LABEL_12;
  }
  *a3 = 1;
  v8 = AipkVerifyPackageMonikerFromService(a1, v13, v14, &v12, &v15, &Src);
  RegCache = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147024894
      || !*(_QWORD *)&v13[2]
      || !*(_QWORD *)&v14[2]
      || !(unsigned __int8)ExQueryFastCacheDevLicense() )
    {
      goto LABEL_13;
    }
    *a3 = 0;
  }
  LODWORD(Size) = v15;
  RegCache = AipkAllocAndFillCacheEntry((int)&v16, (int)a1, (int)v14, (int)v13, v12, Size, Src);
  if ( RegCache >= 0 )
    goto LABEL_12;
LABEL_13:
  AiFree(*(_QWORD *)&v13[2]);
  AiFree(*(_QWORD *)&v14[2]);
  AiFree(Src);
  return (unsigned int)RegCache;
}

```

## disassembly

```asm
0x140028a6c  mov     [rsp-18h+arg_0], rbx
0x140028a71  mov     [rsp-18h+arg_10], rsi
0x140028a76  push    rbp
0x140028a77  push    rdi
0x140028a78  push    r14
0x140028a7a  mov     rbp, rsp
0x140028a7d  sub     rsp, 70h
0x140028a81  mov     [rbp+arg_18], 0
0x140028a89  xorps   xmm0, xmm0
0x140028a8c  mov     [rbp+var_28], 0
0x140028a94  xorps   xmm1, xmm1
0x140028a97  mov     dword ptr [rbp+arg_8], 0
0x140028a9e  mov     r14, r9
0x140028aa1  mov     [rbp+var_30], 0
0x140028aa9  mov     rdi, r8
0x140028aac  mov     qword ptr [r9], 0
0x140028ab3  mov     rsi, rcx
0x140028ab6  movups  xmmword ptr [rbp+var_20], xmm0
0x140028aba  movups  xmmword ptr [rbp+var_10], xmm1
0x140028abe  test    dl, dl
0x140028ac0  jnz     short loc_140028AF2
0x140028ac2  lea     rdx, [rbp+arg_18]
0x140028ac6  call    AipkFindAndReturnEntryFromAppxCache
0x140028acb  mov     ebx, eax
0x140028acd  test    eax, eax
0x140028acf  js      short loc_140028AD9
0x140028ad1  mov     byte ptr [rdi], 0
0x140028ad4  jmp     loc_140028B7C
0x140028ad9  lea     rdx, [rbp+arg_18]; int
0x140028add  mov     byte ptr [rdi], 1
0x140028ae0  mov     rcx, rsi; int
0x140028ae3  call    AipkReadRegCache
0x140028ae8  mov     ebx, eax
0x140028aea  test    eax, eax
0x140028aec  jns     loc_140028B7C
0x140028af2  lea     rax, [rbp+var_30]
0x140028af6  mov     byte ptr [rdi], 1
0x140028af9  mov     [rsp+70h+Size], rax
0x140028afe  lea     r9, [rbp+var_28]
0x140028b02  lea     rax, [rbp+arg_8]
0x140028b06  mov     rcx, rsi
0x140028b09  lea     r8, [rbp+var_10]
0x140028b0d  mov     [rsp+70h+var_50], rax
0x140028b12  lea     rdx, [rbp+var_20]
0x140028b16  call    AipkVerifyPackageMonikerFromService
0x140028b1b  mov     ebx, eax
0x140028b1d  test    eax, eax
0x140028b1f  jns     short loc_140028B49
0x140028b21  cmp     eax, 80070002h
0x140028b26  jnz     short loc_140028B83
0x140028b28  cmp     qword ptr [rbp+var_20+8], 0
0x140028b2d  jz      short loc_140028B83
0x140028b2f  cmp     qword ptr [rbp+var_10+8], 0
0x140028b34  jz      short loc_140028B83
0x140028b36  call    cs:__imp_ExQueryFastCacheDevLicense
0x140028b3d  nop     dword ptr [rax+rax+00h]
0x140028b42  test    al, al
0x140028b44  jz      short loc_140028B83
0x140028b46  mov     byte ptr [rdi], 0
0x140028b49  mov     rax, [rbp+var_30]
0x140028b4d  lea     r9, [rbp+var_20]; int
0x140028b51  mov     [rsp+70h+Src], rax; Src
0x140028b56  lea     r8, [rbp+var_10]; int
0x140028b5a  mov     eax, dword ptr [rbp+arg_8]
0x140028b5d  lea     rcx, [rbp+arg_18]; int
0x140028b61  mov     dword ptr [rsp+70h+Size], eax; Size
0x140028b65  mov     rdx, rsi; int
0x140028b68  mov     rax, [rbp+var_28]
0x140028b6c  mov     [rsp+70h+var_50], rax; __int64
0x140028b71  call    AipkAllocAndFillCacheEntry
0x140028b76  mov     ebx, eax
0x140028b78  test    eax, eax
0x140028b7a  js      short loc_140028B83
0x140028b7c  mov     rax, [rbp+arg_18]
0x140028b80  mov     [r14], rax
0x140028b83  mov     rcx, qword ptr [rbp+var_20+8]
0x140028b87  call    AiFree
0x140028b8c  mov     rcx, qword ptr [rbp+var_10+8]
0x140028b90  call    AiFree
0x140028b95  mov     rcx, [rbp+var_30]
0x140028b99  call    AiFree
0x140028b9e  lea     r11, [rsp+70h+var_s0]
0x140028ba3  mov     eax, ebx
0x140028ba5  mov     rbx, [r11+20h]
0x140028ba9  mov     rsi, [r11+30h]
0x140028bad  mov     rsp, r11
0x140028bb0  pop     r14
0x140028bb2  pop     rdi
0x140028bb3  pop     rbp
0x140028bb4  retn
```

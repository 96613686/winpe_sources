# AipkReadRegCache

- ea: `0x140028f80`
- end: `0x1400290f5`
- name: `AipkReadRegCache`
- size: `373`
- prototype: `__int64 __fastcall(const void **, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140028a6c`

## callees

- `0x140001450`
- `0x140003198`
- `0x14002866c`
- `0x140028c6c`
- `0x140028f80`
- `0x14002948c`
- `0x1400328b0`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400290aa`
- `ntoskrnl!ZwClose` at `0x1400290aa`

## pseudocode

```c
__int64 __fastcall AipkReadRegCache(const void **a1, _QWORD *a2)
{
  void *v4; // rdi
  int StringValue; // ebx
  int v6; // r8d
  int BinaryValue; // eax
  size_t Size; // [rsp+28h] [rbp-48h]
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  int v11[4]; // [rsp+48h] [rbp-28h] BYREF
  int v12[4]; // [rsp+58h] [rbp-18h] BYREF
  size_t v13; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+40h] BYREF
  void *Src; // [rsp+B8h] [rbp+48h] BYREF

  Handle = 0;
  v10 = 0;
  *(_OWORD *)v11 = 0;
  v4 = 0;
  Src = 0;
  *(_OWORD *)v12 = 0;
  LODWORD(v13) = 0;
  if ( AipAppxRegCacheInitialized && !(_BYTE)qword_140019430 )
    AipkLoadRegCache();
  *a2 = 0;
  StringValue = AiRegOpenKey(0, L"NP", 131097, &Handle);
  if ( StringValue >= 0 )
  {
    StringValue = AiRegReadStringValue(Handle, a1, &qword_140009600, v11);
    if ( StringValue >= 0 )
    {
      StringValue = AiRegReadStringValue(Handle, a1, &qword_1400095F0, v12);
      if ( StringValue >= 0 )
      {
        StringValue = AiRegReadQwordValue(Handle, a1, &qword_1400095E0, &v10);
        if ( StringValue >= 0 )
        {
          BinaryValue = AiRegReadBinaryValue((_DWORD)Handle, (_DWORD)a1, v6, (unsigned int)&v13, (__int64)&Src);
          v4 = Src;
          StringValue = BinaryValue;
          if ( BinaryValue >= 0 )
          {
            LODWORD(Size) = v13;
            StringValue = AipkAllocAndFillCacheEntry(a2, a1, (const void **)v11, (const void **)v12, v10, Size, Src);
          }
        }
      }
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( LOWORD(v11[0]) )
    AiFree(*(_QWORD *)&v11[2]);
  if ( LOWORD(v12[0]) )
    AiFree(*(_QWORD *)&v12[2]);
  AiFree(v4);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x140028f80  mov     [rsp-28h+arg_0], rbx
0x140028f85  push    rbp
0x140028f86  push    rsi
0x140028f87  push    rdi
0x140028f88  push    r14
0x140028f8a  push    r15
0x140028f8c  mov     rbp, rsp
0x140028f8f  sub     rsp, 70h
0x140028f93  xor     r15d, r15d
0x140028f96  xorps   xmm0, xmm0
0x140028f99  cmp     cs:AipAppxRegCacheInitialized, r15b
0x140028fa0  xorps   xmm1, xmm1
0x140028fa3  mov     r14, rdx
0x140028fa6  mov     [rbp+Handle], r15
0x140028faa  mov     rsi, rcx
0x140028fad  mov     [rbp+var_30], r15
0x140028fb1  movups  xmmword ptr [rbp+var_28], xmm0
0x140028fb5  mov     edi, r15d
0x140028fb8  mov     [rbp+arg_18], r15
0x140028fbc  movups  xmmword ptr [rbp+var_18], xmm1
0x140028fc0  mov     dword ptr [rbp+arg_8], r15d
0x140028fc4  jz      short loc_140028FD4
0x140028fc6  cmp     byte ptr cs:qword_140019430, r15b
0x140028fcd  jnz     short loc_140028FD4
0x140028fcf  call    AipkLoadRegCache
0x140028fd4  lea     r9, [rbp+Handle]
0x140028fd8  mov     [r14], r15
0x140028fdb  mov     r8d, 20019h
0x140028fe1  lea     rdx, aNp; "NP"
0x140028fe8  xor     ecx, ecx
0x140028fea  call    AiRegOpenKey
0x140028fef  mov     ebx, eax
0x140028ff1  test    eax, eax
0x140028ff3  js      loc_1400290A1
0x140028ff9  mov     rcx, [rbp+Handle]
0x140028ffd  lea     r9, [rbp+var_28]
0x140029001  lea     r8, qword_140009600
0x140029008  mov     rdx, rsi
0x14002900b  call    AiRegReadStringValue
0x140029010  mov     ebx, eax
0x140029012  test    eax, eax
0x140029014  js      loc_1400290A1
0x14002901a  mov     rcx, [rbp+Handle]
0x14002901e  lea     r9, [rbp+var_18]
0x140029022  lea     r8, qword_1400095F0
0x140029029  mov     rdx, rsi
0x14002902c  call    AiRegReadStringValue
0x140029031  mov     ebx, eax
0x140029033  test    eax, eax
0x140029035  js      short loc_1400290A1
0x140029037  mov     rcx, [rbp+Handle]
0x14002903b  lea     r9, [rbp+var_30]
0x14002903f  lea     r8, qword_1400095E0
0x140029046  mov     rdx, rsi
0x140029049  call    AiRegReadQwordValue
0x14002904e  mov     ebx, eax
0x140029050  test    eax, eax
0x140029052  js      short loc_1400290A1
0x140029054  mov     rcx, [rbp+Handle]
0x140029058  lea     rax, [rbp+arg_18]
0x14002905c  lea     r9, [rbp+arg_8]
0x140029060  mov     [rsp+70h+var_50], rax
0x140029065  mov     rdx, rsi
0x140029068  call    AiRegReadBinaryValue
0x14002906d  mov     rdi, [rbp+arg_18]
0x140029071  mov     ebx, eax
0x140029073  test    eax, eax
0x140029075  js      short loc_1400290A1
0x140029077  mov     eax, dword ptr [rbp+arg_8]
0x14002907a  lea     r9, [rbp+var_18]; int
0x14002907e  mov     [rsp+70h+Src], rdi; Src
0x140029083  lea     r8, [rbp+var_28]; int
0x140029087  mov     dword ptr [rsp+70h+Size], eax; Size
0x14002908b  mov     rdx, rsi; int
0x14002908e  mov     rax, [rbp+var_30]
0x140029092  mov     rcx, r14; int
0x140029095  mov     [rsp+70h+var_50], rax; __int64
0x14002909a  call    AipkAllocAndFillCacheEntry
0x14002909f  mov     ebx, eax
0x1400290a1  mov     rcx, [rbp+Handle]; Handle
0x1400290a5  test    rcx, rcx
0x1400290a8  jz      short loc_1400290B6
0x1400290aa  call    cs:__imp_ZwClose
0x1400290b1  nop     dword ptr [rax+rax+00h]
0x1400290b6  cmp     word ptr [rbp+var_28], r15w
0x1400290bb  jz      short loc_1400290C6
0x1400290bd  mov     rcx, qword ptr [rbp+var_28+8]
0x1400290c1  call    AiFree
0x1400290c6  cmp     word ptr [rbp+var_18], r15w
0x1400290cb  jz      short loc_1400290D6
0x1400290cd  mov     rcx, qword ptr [rbp+var_18+8]
0x1400290d1  call    AiFree
0x1400290d6  mov     rcx, rdi
0x1400290d9  call    AiFree
0x1400290de  mov     eax, ebx
0x1400290e0  mov     rbx, [rsp+70h+arg_0]
0x1400290e8  add     rsp, 70h
0x1400290ec  pop     r15
0x1400290ee  pop     r14
0x1400290f0  pop     rdi
0x1400290f1  pop     rsi
0x1400290f2  pop     rbp
0x1400290f3  retn
```

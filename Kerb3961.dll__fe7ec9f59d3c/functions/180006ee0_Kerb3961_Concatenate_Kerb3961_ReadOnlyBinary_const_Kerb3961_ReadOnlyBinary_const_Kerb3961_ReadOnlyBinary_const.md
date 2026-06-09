# Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006ee0`
- end: `0x180007004`
- name: `?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1800050e0`
- `0x180005ed0`
- `0x180006270`
- `0x1800095b0`
- `0x180011530`
- `0x18001190c`
- `0x180011ea0`
- `0x1800166e0`
- `0x180019550`
- `0x180019f70`
- `0x18001bbb0`

## callees

- `0x180002c64`
- `0x1800048b0`
- `0x180006ee0`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate(__int64 a1, _OWORD *a2, __int128 *a3, __int128 *a4)
{
  _BYTE *v4; // rax
  __int128 v6; // xmm1
  unsigned __int64 v7; // rbp
  __int128 v8; // xmm2
  char *v9; // rcx
  const char *v10; // rdx
  void *v11; // rdi
  char *v12; // r14
  const void **i; // rbx
  _OWORD v15[3]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-18h] BYREF
  void *v17; // [rsp+70h] [rbp+8h] BYREF

  v4 = v15;
  v6 = *a3;
  v7 = 0;
  v8 = *a4;
  v15[0] = *a2;
  v15[1] = v6;
  v15[2] = v8;
  while ( v4 != v16 )
  {
    if ( *(_QWORD *)v4 > 0xFFFFFFFF )
    {
      v9 = "entry.length <= utl::numeric_limits<uint32_t>::max()";
      goto LABEL_17;
    }
    v7 += *(_QWORD *)v4;
    v4 += 16;
  }
  if ( v7 > 0xFFFFFFFF )
  {
    v9 = "length <= utl::numeric_limits<uint32_t>::max()";
LABEL_17:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v9, (const char *)0xFFFFFFFFLL);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741675;
  }
  else
  {
    if ( !v7 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
LABEL_9:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
    }
    utl::make_unique<unsigned char [0],0>(&v17);
    v11 = v17;
    if ( v17 )
    {
      v12 = (char *)v17;
      for ( i = (const void **)v15; i != (const void **)v16; i += 2 )
      {
        memcpy_0(v12, i[1], (size_t)*i);
        v12 = &v12[(_QWORD)*i];
      }
      *(_QWORD *)a1 = v7;
      *(_QWORD *)(a1 + 8) = v11;
      goto LABEL_9;
    }
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v10);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741801;
  }
  return a1;
}

```

## disassembly

```asm
0x180006ee0  mov     rax, rsp
0x180006ee3  mov     [rax+10h], rbx
0x180006ee7  mov     [rax+18h], rbp
0x180006eeb  push    rsi
0x180006eec  push    rdi
0x180006eed  push    r14
0x180006eef  sub     rsp, 50h
0x180006ef3  movups  xmm0, xmmword ptr [rdx]
0x180006ef6  lea     rax, [rax-48h]
0x180006efa  mov     rsi, rcx
0x180006efd  movups  xmm1, xmmword ptr [r8]
0x180006f01  xor     ebp, ebp
0x180006f03  mov     edx, 0FFFFFFFFh; char *
0x180006f08  movups  xmm2, xmmword ptr [r9]
0x180006f0c  movaps  xmmword ptr [rax], xmm0
0x180006f0f  movaps  xmmword ptr [rax+10h], xmm1
0x180006f13  movaps  xmmword ptr [rax+20h], xmm2
0x180006f17  lea     rcx, [rsp+68h+var_18]
0x180006f1c  cmp     rax, rcx
0x180006f1f  jz      short loc_180006F3B
0x180006f21  cmp     [rax], rdx
0x180006f24  ja      short loc_180006F2F
0x180006f26  add     rbp, [rax]
0x180006f29  add     rax, 10h
0x180006f2d  jmp     short loc_180006F17
0x180006f2f  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x180006f36  jmp     loc_180006FD1
0x180006f3b  cmp     rbp, rdx
0x180006f3e  ja      loc_180006FCA
0x180006f44  test    rbp, rbp
0x180006f47  jnz     short loc_180006F5C
0x180006f49  mov     [rsi], rbp
0x180006f4c  mov     [rsi+8], rbp
0x180006f50  mov     dword ptr [rsi+10h], 0
0x180006f57  jmp     loc_180006FEC
0x180006f5c  mov     rdx, rbp
0x180006f5f  lea     rcx, [rsp+68h+arg_0]
0x180006f64  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180006f69  mov     rdi, [rsp+68h+arg_0]
0x180006f6e  test    rdi, rdi
0x180006f71  jz      short loc_180006FA6
0x180006f73  mov     r14, rdi
0x180006f76  lea     rbx, [rsp+68h+var_48]
0x180006f7b  lea     rax, [rsp+68h+var_18]
0x180006f80  cmp     rbx, rax
0x180006f83  jz      short loc_180006F9D
0x180006f85  mov     r8, [rbx]; Size
0x180006f88  mov     rcx, r14; void *
0x180006f8b  mov     rdx, [rbx+8]; Src
0x180006f8f  call    memcpy_0
0x180006f94  add     r14, [rbx]
0x180006f97  add     rbx, 10h
0x180006f9b  jmp     short loc_180006F7B
0x180006f9d  mov     [rsi], rbp
0x180006fa0  mov     [rsi+8], rdi
0x180006fa4  jmp     short loc_180006F50
0x180006fa6  lea     rcx, aResult; "result"
0x180006fad  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006fb2  mov     qword ptr [rsi], 0
0x180006fb9  mov     qword ptr [rsi+8], 0
0x180006fc1  mov     dword ptr [rsi+10h], 0C0000017h
0x180006fc8  jmp     short loc_180006FEC
0x180006fca  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x180006fd1  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006fd6  mov     qword ptr [rsi], 0
0x180006fdd  mov     qword ptr [rsi+8], 0
0x180006fe5  mov     dword ptr [rsi+10h], 0C0000095h
0x180006fec  lea     r11, [rsp+68h+var_18]
0x180006ff1  mov     rax, rsi
0x180006ff4  mov     rbx, [r11+28h]
0x180006ff8  mov     rbp, [r11+30h]
0x180006ffc  mov     rsp, r11
0x180006fff  pop     r14
0x180007001  pop     rdi
0x180007002  pop     rsi
0x180007003  retn
```

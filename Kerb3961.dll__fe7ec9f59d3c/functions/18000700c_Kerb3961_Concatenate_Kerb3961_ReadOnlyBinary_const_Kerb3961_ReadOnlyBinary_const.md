# Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000700c`
- end: `0x180007126`
- name: `?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180005480`
- `0x180007d00`
- `0x1800082f0`
- `0x1800110c0`
- `0x18001190c`
- `0x180011c70`
- `0x180012260`
- `0x180019f70`

## callees

- `0x180002c64`
- `0x1800048b0`
- `0x18000700c`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate(__int64 a1, _OWORD *a2, __int128 *a3)
{
  _BYTE *v3; // rax
  __int128 v5; // xmm1
  unsigned __int64 v6; // rbp
  char *v7; // rcx
  const char *v8; // rdx
  void *v9; // rdi
  char *v10; // r14
  const void **i; // rbx
  _OWORD v13[2]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-18h] BYREF
  void *v15; // [rsp+60h] [rbp+8h] BYREF

  v3 = v13;
  v5 = *a3;
  v6 = 0;
  v13[0] = *a2;
  v13[1] = v5;
  while ( v3 != v14 )
  {
    if ( *(_QWORD *)v3 > 0xFFFFFFFF )
    {
      v7 = "entry.length <= utl::numeric_limits<uint32_t>::max()";
      goto LABEL_17;
    }
    v6 += *(_QWORD *)v3;
    v3 += 16;
  }
  if ( v6 > 0xFFFFFFFF )
  {
    v7 = "length <= utl::numeric_limits<uint32_t>::max()";
LABEL_17:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, (const char *)0xFFFFFFFFLL);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741675;
  }
  else
  {
    if ( !v6 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
LABEL_9:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
    }
    utl::make_unique<unsigned char [0],0>(&v15);
    v9 = v15;
    if ( v15 )
    {
      v10 = (char *)v15;
      for ( i = (const void **)v13; i != (const void **)v14; i += 2 )
      {
        memcpy_0(v10, i[1], (size_t)*i);
        v10 = &v10[(_QWORD)*i];
      }
      *(_QWORD *)a1 = v6;
      *(_QWORD *)(a1 + 8) = v9;
      goto LABEL_9;
    }
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v8);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741801;
  }
  return a1;
}

```

## disassembly

```asm
0x18000700c  mov     rax, rsp
0x18000700f  mov     [rax+10h], rbx
0x180007013  mov     [rax+18h], rbp
0x180007017  push    rsi
0x180007018  push    rdi
0x180007019  push    r14
0x18000701b  sub     rsp, 40h
0x18000701f  movups  xmm0, xmmword ptr [rdx]
0x180007022  lea     rax, [rax-38h]
0x180007026  mov     rsi, rcx
0x180007029  movups  xmm1, xmmword ptr [r8]
0x18000702d  xor     ebp, ebp
0x18000702f  mov     edx, 0FFFFFFFFh; char *
0x180007034  movaps  xmmword ptr [rax], xmm0
0x180007037  movaps  xmmword ptr [rax+10h], xmm1
0x18000703b  lea     rcx, [rsp+58h+var_18]
0x180007040  cmp     rax, rcx
0x180007043  jz      short loc_18000705F
0x180007045  cmp     [rax], rdx
0x180007048  ja      short loc_180007053
0x18000704a  add     rbp, [rax]
0x18000704d  add     rax, 10h
0x180007051  jmp     short loc_18000703B
0x180007053  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x18000705a  jmp     loc_1800070F5
0x18000705f  cmp     rbp, rdx
0x180007062  ja      loc_1800070EE
0x180007068  test    rbp, rbp
0x18000706b  jnz     short loc_180007080
0x18000706d  mov     [rsi], rbp
0x180007070  mov     [rsi+8], rbp
0x180007074  mov     dword ptr [rsi+10h], 0
0x18000707b  jmp     loc_180007110
0x180007080  mov     rdx, rbp
0x180007083  lea     rcx, [rsp+58h+arg_0]
0x180007088  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000708d  mov     rdi, [rsp+58h+arg_0]
0x180007092  test    rdi, rdi
0x180007095  jz      short loc_1800070CA
0x180007097  mov     r14, rdi
0x18000709a  lea     rbx, [rsp+58h+var_38]
0x18000709f  lea     rax, [rsp+58h+var_18]
0x1800070a4  cmp     rbx, rax
0x1800070a7  jz      short loc_1800070C1
0x1800070a9  mov     r8, [rbx]; Size
0x1800070ac  mov     rcx, r14; void *
0x1800070af  mov     rdx, [rbx+8]; Src
0x1800070b3  call    memcpy_0
0x1800070b8  add     r14, [rbx]
0x1800070bb  add     rbx, 10h
0x1800070bf  jmp     short loc_18000709F
0x1800070c1  mov     [rsi], rbp
0x1800070c4  mov     [rsi+8], rdi
0x1800070c8  jmp     short loc_180007074
0x1800070ca  lea     rcx, aResult; "result"
0x1800070d1  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800070d6  mov     qword ptr [rsi], 0
0x1800070dd  mov     qword ptr [rsi+8], 0
0x1800070e5  mov     dword ptr [rsi+10h], 0C0000017h
0x1800070ec  jmp     short loc_180007110
0x1800070ee  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x1800070f5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800070fa  mov     qword ptr [rsi], 0
0x180007101  mov     qword ptr [rsi+8], 0
0x180007109  mov     dword ptr [rsi+10h], 0C0000095h
0x180007110  mov     rbx, [rsp+58h+arg_8]
0x180007115  mov     rax, rsi
0x180007118  mov     rbp, [rsp+58h+arg_10]
0x18000711d  add     rsp, 40h
0x180007121  pop     r14
0x180007123  pop     rdi
0x180007124  pop     rsi
0x180007125  retn
```

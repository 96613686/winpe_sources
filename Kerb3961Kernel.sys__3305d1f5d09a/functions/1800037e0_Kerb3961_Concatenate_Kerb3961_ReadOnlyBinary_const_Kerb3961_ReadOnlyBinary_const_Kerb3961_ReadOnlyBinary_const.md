# Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800037e0`
- end: `0x180003908`
- name: `?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z`
- size: `296`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028d4`
- `0x180002cc4`
- `0x180003dc0`
- `0x1800060f0`
- `0x180007338`
- `0x180007710`
- `0x180009040`
- `0x18000d580`
- `0x18000e310`
- `0x18000e6b0`
- `0x180010460`

## callees

- `0x180001818`
- `0x1800037e0`
- `0x180011760`
- `0x180012300`

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
  char *v12; // r15
  const void **i; // rbx
  size_t v14; // rsi
  _OWORD v16[3]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v17[56]; // [rsp+50h] [rbp-38h] BYREF
  void *v18; // [rsp+90h] [rbp+8h] BYREF

  v4 = v16;
  v6 = *a3;
  v7 = 0;
  v8 = *a4;
  v16[0] = *a2;
  v16[1] = v6;
  v16[2] = v8;
  while ( v4 != v17 )
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
    utl::make_unique<unsigned char [0],0>(&v18);
    v11 = v18;
    if ( v18 )
    {
      v12 = (char *)v18;
      for ( i = (const void **)v16; i != (const void **)v17; i += 2 )
      {
        v14 = (size_t)*i;
        memmove(v12, i[1], (size_t)*i);
        v12 += v14;
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
0x1800037e0  mov     rax, rsp
0x1800037e3  push    rbx
0x1800037e4  push    rbp
0x1800037e5  push    rsi
0x1800037e6  push    rdi
0x1800037e7  push    r14
0x1800037e9  push    r15
0x1800037eb  sub     rsp, 58h
0x1800037ef  movups  xmm0, xmmword ptr [rdx]
0x1800037f2  lea     rax, [rax-68h]
0x1800037f6  mov     r14, rcx
0x1800037f9  movups  xmm1, xmmword ptr [r8]
0x1800037fd  xor     ebp, ebp
0x1800037ff  mov     edx, 0FFFFFFFFh; char *
0x180003804  movups  xmm2, xmmword ptr [r9]
0x180003808  movaps  xmmword ptr [rax], xmm0
0x18000380b  movaps  xmmword ptr [rax+10h], xmm1
0x18000380f  movaps  xmmword ptr [rax+20h], xmm2
0x180003813  lea     rcx, [rsp+88h+var_38]
0x180003818  cmp     rax, rcx
0x18000381b  jz      short loc_18000383A
0x18000381d  mov     rcx, [rax]
0x180003820  cmp     rcx, rdx
0x180003823  ja      short loc_18000382E
0x180003825  add     rbp, rcx
0x180003828  add     rax, 10h
0x18000382c  jmp     short loc_180003813
0x18000382e  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x180003835  jmp     loc_1800038DB
0x18000383a  cmp     rbp, rdx
0x18000383d  ja      loc_1800038D4
0x180003843  test    rbp, rbp
0x180003846  jnz     short loc_18000385C
0x180003848  mov     [r14], rbp
0x18000384b  mov     [r14+8], rbp
0x18000384f  mov     dword ptr [r14+10h], 0
0x180003857  jmp     loc_1800038F7
0x18000385c  mov     rdx, rbp
0x18000385f  lea     rcx, [rsp+88h+arg_0]
0x180003867  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000386c  mov     rdi, [rsp+88h+arg_0]
0x180003874  test    rdi, rdi
0x180003877  jz      short loc_1800038AF
0x180003879  mov     r15, rdi
0x18000387c  lea     rbx, [rsp+88h+var_68]
0x180003881  lea     rax, [rsp+88h+var_38]
0x180003886  cmp     rbx, rax
0x180003889  jz      short loc_1800038A6
0x18000388b  mov     rsi, [rbx]
0x18000388e  mov     rcx, r15; void *
0x180003891  mov     rdx, [rbx+8]; Src
0x180003895  mov     r8, rsi; Size
0x180003898  call    memmove
0x18000389d  add     r15, rsi
0x1800038a0  add     rbx, 10h
0x1800038a4  jmp     short loc_180003881
0x1800038a6  mov     [r14], rbp
0x1800038a9  mov     [r14+8], rdi
0x1800038ad  jmp     short loc_18000384F
0x1800038af  lea     rcx, aResult; "result"
0x1800038b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800038bb  mov     qword ptr [r14], 0
0x1800038c2  mov     qword ptr [r14+8], 0
0x1800038ca  mov     dword ptr [r14+10h], 0C0000017h
0x1800038d2  jmp     short loc_1800038F7
0x1800038d4  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x1800038db  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800038e0  mov     qword ptr [r14], 0
0x1800038e7  mov     qword ptr [r14+8], 0
0x1800038ef  mov     dword ptr [r14+10h], 0C0000095h
0x1800038f7  mov     rax, r14
0x1800038fa  add     rsp, 58h
0x1800038fe  pop     r15
0x180003900  pop     r14
0x180003902  pop     rdi
0x180003903  pop     rsi
0x180003904  pop     rbp
0x180003905  pop     rbx
0x180003906  retn
```

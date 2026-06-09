# Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)

- ea: `0x180004118`
- end: `0x18000420e`
- name: `??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005480`
- `0x180006ac0`
- `0x180011ea0`
- `0x180019950`
- `0x18001ade0`

## callees

- `0x180002c64`
- `0x180004118`
- `0x1800048b0`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate<4>(__int64 a1, const char *a2)
{
  const char *v3; // rsi
  const char *v4; // rdi
  unsigned __int64 v5; // rbp
  const char *i; // rax
  char *v7; // rcx
  const char *v8; // rdx
  void *v9; // rbx
  char *v10; // r15
  void *v12; // [rsp+20h] [rbp-48h] BYREF

  v3 = a2 + 64;
  v4 = a2;
  v5 = 0;
  for ( i = a2; i != v3; i += 16 )
  {
    if ( *(_QWORD *)i > 0xFFFFFFFF )
    {
      v7 = "entry.length <= utl::numeric_limits<uint32_t>::max()";
      goto LABEL_17;
    }
    v5 += *(_QWORD *)i;
  }
  if ( v5 > 0xFFFFFFFF )
  {
    v7 = "length <= utl::numeric_limits<uint32_t>::max()";
LABEL_17:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741675;
  }
  else
  {
    if ( !v5 )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
LABEL_9:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
    }
    utl::make_unique<unsigned char [0],0>(&v12, v5);
    v9 = v12;
    if ( v12 )
    {
      v10 = (char *)v12;
      while ( v4 != v3 )
      {
        memcpy_0(v10, *((const void **)v4 + 1), *(_QWORD *)v4);
        v10 += *(_QWORD *)v4;
        v4 += 16;
      }
      *(_QWORD *)a1 = v5;
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
0x180004118  push    rbx
0x18000411a  push    rbp
0x18000411b  push    rsi
0x18000411c  push    rdi
0x18000411d  push    r14
0x18000411f  push    r15
0x180004121  sub     rsp, 38h
0x180004125  mov     r14, rcx
0x180004128  lea     rsi, [rdx+40h]
0x18000412c  mov     ecx, 0FFFFFFFFh
0x180004131  mov     rdi, rdx
0x180004134  xor     ebp, ebp
0x180004136  mov     rax, rdx
0x180004139  cmp     rax, rsi
0x18000413c  jz      short loc_180004158
0x18000413e  cmp     [rax], rcx
0x180004141  ja      short loc_18000414C
0x180004143  add     rbp, [rax]
0x180004146  add     rax, 10h
0x18000414a  jmp     short loc_180004139
0x18000414c  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x180004153  jmp     loc_1800041E2
0x180004158  cmp     rbp, rcx
0x18000415b  ja      short loc_1800041DB
0x18000415d  test    rbp, rbp
0x180004160  jnz     short loc_180004176
0x180004162  mov     [r14], rbp
0x180004165  mov     [r14+8], rbp
0x180004169  mov     dword ptr [r14+10h], 0
0x180004171  jmp     loc_1800041FE
0x180004176  mov     rdx, rbp
0x180004179  lea     rcx, [rsp+68h+var_48]
0x18000417e  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180004183  mov     rbx, [rsp+68h+var_48]
0x180004188  test    rbx, rbx
0x18000418b  jz      short loc_1800041B6
0x18000418d  mov     r15, rbx
0x180004190  cmp     rdi, rsi
0x180004193  jz      short loc_1800041AD
0x180004195  mov     r8, [rdi]; Size
0x180004198  mov     rcx, r15; void *
0x18000419b  mov     rdx, [rdi+8]; Src
0x18000419f  call    memcpy_0
0x1800041a4  add     r15, [rdi]
0x1800041a7  add     rdi, 10h
0x1800041ab  jmp     short loc_180004190
0x1800041ad  mov     [r14], rbp
0x1800041b0  mov     [r14+8], rbx
0x1800041b4  jmp     short loc_180004169
0x1800041b6  lea     rcx, aResult; "result"
0x1800041bd  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800041c2  mov     qword ptr [r14], 0
0x1800041c9  mov     qword ptr [r14+8], 0
0x1800041d1  mov     dword ptr [r14+10h], 0C0000017h
0x1800041d9  jmp     short loc_1800041FE
0x1800041db  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x1800041e2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800041e7  mov     qword ptr [r14], 0
0x1800041ee  mov     qword ptr [r14+8], 0
0x1800041f6  mov     dword ptr [r14+10h], 0C0000095h
0x1800041fe  mov     rax, r14
0x180004201  add     rsp, 38h
0x180004205  pop     r15
0x180004207  pop     r14
0x180004209  pop     rdi
0x18000420a  pop     rsi
0x18000420b  pop     rbp
0x18000420c  pop     rbx
0x18000420d  retn
```

# Kerb3961::Concatenate<5>(utl::array<Kerb3961::ReadOnlyBinary const,5>)

- ea: `0x18000fc10`
- end: `0x18000fd06`
- name: `??$Concatenate@$04@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$04@utl@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012ab8`

## callees

- `0x180002c64`
- `0x1800048b0`
- `0x18000fc10`
- `0x18001d360`

## pseudocode

```c
__int64 __fastcall Kerb3961::Concatenate<5>(__int64 a1, const char *a2)
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

  v3 = a2 + 80;
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
0x18000fc10  push    rbx
0x18000fc12  push    rbp
0x18000fc13  push    rsi
0x18000fc14  push    rdi
0x18000fc15  push    r14
0x18000fc17  push    r15
0x18000fc19  sub     rsp, 38h
0x18000fc1d  mov     r14, rcx
0x18000fc20  lea     rsi, [rdx+50h]
0x18000fc24  mov     ecx, 0FFFFFFFFh
0x18000fc29  mov     rdi, rdx
0x18000fc2c  xor     ebp, ebp
0x18000fc2e  mov     rax, rdx
0x18000fc31  cmp     rax, rsi
0x18000fc34  jz      short loc_18000FC50
0x18000fc36  cmp     [rax], rcx
0x18000fc39  ja      short loc_18000FC44
0x18000fc3b  add     rbp, [rax]
0x18000fc3e  add     rax, 10h
0x18000fc42  jmp     short loc_18000FC31
0x18000fc44  lea     rcx, aEntryLengthUtl; "entry.length <= utl::numeric_limits<uin"...
0x18000fc4b  jmp     loc_18000FCDA
0x18000fc50  cmp     rbp, rcx
0x18000fc53  ja      short loc_18000FCD3
0x18000fc55  test    rbp, rbp
0x18000fc58  jnz     short loc_18000FC6E
0x18000fc5a  mov     [r14], rbp
0x18000fc5d  mov     [r14+8], rbp
0x18000fc61  mov     dword ptr [r14+10h], 0
0x18000fc69  jmp     loc_18000FCF6
0x18000fc6e  mov     rdx, rbp
0x18000fc71  lea     rcx, [rsp+68h+var_48]
0x18000fc76  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000fc7b  mov     rbx, [rsp+68h+var_48]
0x18000fc80  test    rbx, rbx
0x18000fc83  jz      short loc_18000FCAE
0x18000fc85  mov     r15, rbx
0x18000fc88  cmp     rdi, rsi
0x18000fc8b  jz      short loc_18000FCA5
0x18000fc8d  mov     r8, [rdi]; Size
0x18000fc90  mov     rcx, r15; void *
0x18000fc93  mov     rdx, [rdi+8]; Src
0x18000fc97  call    memcpy_0
0x18000fc9c  add     r15, [rdi]
0x18000fc9f  add     rdi, 10h
0x18000fca3  jmp     short loc_18000FC88
0x18000fca5  mov     [r14], rbp
0x18000fca8  mov     [r14+8], rbx
0x18000fcac  jmp     short loc_18000FC61
0x18000fcae  lea     rcx, aResult; "result"
0x18000fcb5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fcba  mov     qword ptr [r14], 0
0x18000fcc1  mov     qword ptr [r14+8], 0
0x18000fcc9  mov     dword ptr [r14+10h], 0C0000017h
0x18000fcd1  jmp     short loc_18000FCF6
0x18000fcd3  lea     rcx, aLengthUtlNumer; "length <= utl::numeric_limits<uint32_t>"...
0x18000fcda  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fcdf  mov     qword ptr [r14], 0
0x18000fce6  mov     qword ptr [r14+8], 0
0x18000fcee  mov     dword ptr [r14+10h], 0C0000095h
0x18000fcf6  mov     rax, r14
0x18000fcf9  add     rsp, 38h
0x18000fcfd  pop     r15
0x18000fcff  pop     r14
0x18000fd01  pop     rdi
0x18000fd02  pop     rsi
0x18000fd03  pop     rbp
0x18000fd04  pop     rbx
0x18000fd05  retn
```

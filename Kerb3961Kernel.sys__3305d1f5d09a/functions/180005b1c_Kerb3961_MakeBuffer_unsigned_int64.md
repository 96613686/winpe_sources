# Kerb3961::MakeBuffer(unsigned __int64)

- ea: `0x180005b1c`
- end: `0x180005b9d`
- name: `?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `29`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e7c`
- `0x180001ff4`
- `0x180002174`
- `0x1800022a8`
- `0x1800023e0`
- `0x1800041a0`
- `0x180004700`
- `0x180004a00`
- `0x1800059e4`
- `0x180005c30`
- `0x180006f6c`
- `0x180007ad0`
- `0x1800083f0`
- `0x180008e10`
- `0x180008ea0`
- `0x180009da0`
- `0x18000a320`
- `0x18000a500`
- `0x18000acb4`
- `0x18000b0c8`
- `0x18000c230`
- `0x18000d3c0`
- `0x18000d580`
- `0x18000e6b0`
- `0x18000eec0`
- `0x18000f730`
- `0x18000fe44`
- `0x180010060`
- `0x1800101c0`

## callees

- `0x180001818`
- `0x180005b1c`
- `0x180011760`
- `0x180011b40`

## pseudocode

```c
__int64 __fastcall Kerb3961::MakeBuffer(__int64 a1, const struct std::nothrow_t *a2)
{
  const char *v4; // rdx
  __int64 v5; // rdi
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  utl::make_unique<unsigned char [0],0>(&v7, a2);
  v5 = v7;
  if ( v7 )
  {
    *(_QWORD *)a1 = a2;
    *(_QWORD *)(a1 + 8) = v5;
    *(_DWORD *)(a1 + 16) = 0;
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"buffer", v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741801;
  }
  return a1;
}

```

## disassembly

```asm
0x180005b1c  mov     [rsp+arg_0], rbx
0x180005b21  mov     [rsp+arg_8], rsi
0x180005b26  push    rdi
0x180005b27  sub     rsp, 20h
0x180005b2b  mov     rbx, rcx
0x180005b2e  mov     rsi, rdx
0x180005b31  lea     rcx, [rsp+28h+arg_10]
0x180005b36  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180005b3b  mov     rdi, [rsp+28h+arg_10]
0x180005b40  test    rdi, rdi
0x180005b43  setnz   al
0x180005b46  test    al, al
0x180005b48  jnz     short loc_180005B7B
0x180005b4a  lea     rcx, aBuffer; "buffer"
0x180005b51  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005b56  mov     qword ptr [rbx], 0
0x180005b5d  mov     qword ptr [rbx+8], 0
0x180005b65  mov     dword ptr [rbx+10h], 0C0000017h
0x180005b6c  test    rdi, rdi
0x180005b6f  jz      short loc_180005B89
0x180005b71  mov     rcx, rdi
0x180005b74  call    Kerb3961Free
0x180005b79  jmp     short loc_180005B89
0x180005b7b  mov     [rbx], rsi
0x180005b7e  mov     [rbx+8], rdi
0x180005b82  mov     dword ptr [rbx+10h], 0
0x180005b89  mov     rsi, [rsp+28h+arg_8]
0x180005b8e  mov     rax, rbx
0x180005b91  mov     rbx, [rsp+28h+arg_0]
0x180005b96  add     rsp, 20h
0x180005b9a  pop     rdi
0x180005b9b  retn
```

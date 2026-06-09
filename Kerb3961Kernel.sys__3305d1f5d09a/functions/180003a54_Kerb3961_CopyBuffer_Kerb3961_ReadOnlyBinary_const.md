# Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180003a54`
- end: `0x180003afb`
- name: `?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002cc4`
- `0x180003b10`
- `0x180003dc0`
- `0x1800051e0`
- `0x180005f40`
- `0x180008fd0`
- `0x180009da0`
- `0x18000b0c8`
- `0x18000d900`
- `0x18000e6b0`
- `0x18000f2c0`
- `0x18000f5e0`
- `0x1800103f0`

## callees

- `0x180001818`
- `0x180003a54`
- `0x180011760`
- `0x180011b40`
- `0x180012300`

## pseudocode

```c
__int64 __fastcall Kerb3961::CopyBuffer(__int64 a1, __int64 a2)
{
  const char *v4; // rdx
  void *v5; // rdi
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  if ( *(_QWORD *)a2 )
  {
    utl::make_unique<unsigned char [0],0>(&v7);
    v5 = v7;
    if ( v7 )
    {
      memmove(v7, *(const void **)(a2 + 8), *(_QWORD *)a2);
      *(_QWORD *)a1 = *(_QWORD *)a2;
      *(_QWORD *)(a1 + 8) = v5;
      *(_DWORD *)(a1 + 16) = 0;
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"copy", v4);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741801;
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180003a54  mov     [rsp+arg_0], rbx
0x180003a59  mov     [rsp+arg_10], rsi
0x180003a5e  push    rdi
0x180003a5f  sub     rsp, 20h
0x180003a63  mov     rsi, rdx
0x180003a66  mov     rbx, rcx
0x180003a69  mov     rdx, [rdx]
0x180003a6c  test    rdx, rdx
0x180003a6f  jnz     short loc_180003A7D
0x180003a71  mov     [rcx], rdx
0x180003a74  mov     [rcx+8], rdx
0x180003a78  mov     [rcx+10h], edx
0x180003a7b  jmp     short loc_180003AE7
0x180003a7d  lea     rcx, [rsp+28h+arg_8]
0x180003a82  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180003a87  mov     rdi, [rsp+28h+arg_8]
0x180003a8c  test    rdi, rdi
0x180003a8f  setnz   al
0x180003a92  test    al, al
0x180003a94  jnz     short loc_180003AC7
0x180003a96  lea     rcx, aCopy; "copy"
0x180003a9d  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180003aa2  mov     qword ptr [rbx], 0
0x180003aa9  mov     qword ptr [rbx+8], 0
0x180003ab1  mov     dword ptr [rbx+10h], 0C0000017h
0x180003ab8  test    rdi, rdi
0x180003abb  jz      short loc_180003AE7
0x180003abd  mov     rcx, rdi
0x180003ac0  call    Kerb3961Free
0x180003ac5  jmp     short loc_180003AE7
0x180003ac7  mov     r8, [rsi]; Size
0x180003aca  mov     rcx, rdi; void *
0x180003acd  mov     rdx, [rsi+8]; Src
0x180003ad1  call    memmove
0x180003ad6  mov     rax, [rsi]
0x180003ad9  mov     [rbx], rax
0x180003adc  mov     [rbx+8], rdi
0x180003ae0  mov     dword ptr [rbx+10h], 0
0x180003ae7  mov     rsi, [rsp+28h+arg_10]
0x180003aec  mov     rax, rbx
0x180003aef  mov     rbx, [rsp+28h+arg_0]
0x180003af4  add     rsp, 20h
0x180003af8  pop     rdi
0x180003af9  retn
```

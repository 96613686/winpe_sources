# Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000712c`
- end: `0x1800071d2`
- name: `?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005480`
- `0x180006270`
- `0x1800071e0`
- `0x180007500`
- `0x180007d00`
- `0x1800093a0`
- `0x18000e320`
- `0x18000f030`
- `0x18001190c`
- `0x180015170`
- `0x180019cc0`
- `0x180019f70`
- `0x18001bb50`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x1800048b0`
- `0x18000712c`
- `0x18001d360`

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
      memcpy_0(v7, *(const void **)(a2 + 8), *(_QWORD *)a2);
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
0x18000712c  mov     [rsp+arg_0], rbx
0x180007131  mov     [rsp+arg_10], rsi
0x180007136  push    rdi
0x180007137  sub     rsp, 20h
0x18000713b  mov     rsi, rdx
0x18000713e  mov     rbx, rcx
0x180007141  mov     rdx, [rdx]
0x180007144  test    rdx, rdx
0x180007147  jnz     short loc_180007155
0x180007149  mov     [rcx], rdx
0x18000714c  mov     [rcx+8], rdx
0x180007150  mov     [rcx+10h], edx
0x180007153  jmp     short loc_1800071BF
0x180007155  lea     rcx, [rsp+28h+arg_8]
0x18000715a  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000715f  mov     rdi, [rsp+28h+arg_8]
0x180007164  test    rdi, rdi
0x180007167  setnz   al
0x18000716a  test    al, al
0x18000716c  jnz     short loc_18000719F
0x18000716e  lea     rcx, aCopy; "copy"
0x180007175  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000717a  mov     qword ptr [rbx], 0
0x180007181  mov     qword ptr [rbx+8], 0
0x180007189  mov     dword ptr [rbx+10h], 0C0000017h
0x180007190  test    rdi, rdi
0x180007193  jz      short loc_1800071BF
0x180007195  mov     rcx, rdi; void *
0x180007198  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000719d  jmp     short loc_1800071BF
0x18000719f  mov     r8, [rsi]; Size
0x1800071a2  mov     rcx, rdi; void *
0x1800071a5  mov     rdx, [rsi+8]; Src
0x1800071a9  call    memcpy_0
0x1800071ae  mov     rax, [rsi]
0x1800071b1  mov     [rbx], rax
0x1800071b4  mov     [rbx+8], rdi
0x1800071b8  mov     dword ptr [rbx+10h], 0
0x1800071bf  mov     rsi, [rsp+28h+arg_10]
0x1800071c4  mov     rax, rbx
0x1800071c7  mov     rbx, [rsp+28h+arg_0]
0x1800071cc  add     rsp, 20h
0x1800071d0  pop     rdi
0x1800071d1  retn
```

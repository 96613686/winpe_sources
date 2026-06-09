# Concurrency::invalid_operation::invalid_operation(char const *)

- ea: `0x180016030`
- end: `0x18001608a`
- name: `??0invalid_operation@Concurrency@@QEAA@PEBD@Z`
- size: `90`
- prototype: `Concurrency::invalid_operation *__fastcall(Concurrency::invalid_operation *this, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180019850`

## callees

- `0x180002b16`

## string_xrefs

- `0x18001604f`: `This function cannot be called on a default constructed task`

## pseudocode

```c
Concurrency::invalid_operation *__fastcall Concurrency::invalid_operation::invalid_operation(
        Concurrency::invalid_operation *this,
        const char *a2)
{
  const char *v4; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+28h] [rbp-10h]
  int v6; // [rsp+29h] [rbp-Fh]
  __int16 v7; // [rsp+2Dh] [rbp-Bh]
  char v8; // [rsp+2Fh] [rbp-9h]

  v5 = 1;
  *(_QWORD *)this = &std::exception::`vftable';
  v4 = "This function cannot be called on a default constructed task";
  v6 = 0;
  v7 = 0;
  v8 = 0;
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0(&v4);
  *(_QWORD *)this = &std::logic_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x180016030  push    rbx
0x180016032  sub     rsp, 30h
0x180016036  lea     rdx, [rcx+8]
0x18001603a  mov     [rsp+38h+var_10], 1
0x18001603f  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180016046  mov     rbx, rcx
0x180016049  mov     [rcx], rax
0x18001604c  xorps   xmm0, xmm0
0x18001604f  lea     rax, aThisFunctionCa; "This function cannot be called on a def"...
0x180016056  mov     [rsp+38h+var_18], rax
0x18001605b  lea     rcx, [rsp+38h+var_18]
0x180016060  xor     eax, eax
0x180016062  mov     [rsp+38h+var_F], eax
0x180016066  mov     [rsp+38h+var_B], ax
0x18001606b  mov     [rsp+38h+var_9], al
0x18001606f  movups  xmmword ptr [rdx], xmm0
0x180016072  call    _o___std_exception_copy_0
0x180016077  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18001607e  mov     [rbx], rax
0x180016081  mov     rax, rbx
0x180016084  add     rsp, 30h
0x180016088  pop     rbx
0x180016089  retn
```

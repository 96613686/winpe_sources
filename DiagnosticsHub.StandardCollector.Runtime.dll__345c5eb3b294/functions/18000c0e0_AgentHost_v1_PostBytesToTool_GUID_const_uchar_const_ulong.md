# AgentHost_v1::PostBytesToTool(_GUID const &,uchar const *,ulong)

- ea: `0x18000c0e0`
- end: `0x18000c1cb`
- name: `?PostBytesToTool@AgentHost_v1@@UEAAJAEBU_GUID@@PEBEK@Z`
- size: `235`
- prototype: `__int64 __fastcall(AgentHost_v1 *this, const struct _GUID *, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000c0e0`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18000c196`
- `VCRUNTIME140!memcpy` at `0x18000c196`
- `ole32!CoTaskMemAlloc` at `0x18000c118`
- `ole32!CoTaskMemAlloc` at `0x18000c17a`
- `ole32!CoTaskMemAlloc` at `0x18000c118`
- `ole32!CoTaskMemAlloc` at `0x18000c17a`
- `ole32!CoTaskMemFree` at `0x18000c153`
- `ole32!CoTaskMemFree` at `0x18000c15d`
- `ole32!CoTaskMemFree` at `0x18000c153`
- `ole32!CoTaskMemFree` at `0x18000c15d`

## pseudocode

```c
__int64 __fastcall AgentHost_v1::PostBytesToTool(
        AgentHost_v1 *this,
        const struct _GUID *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v4; // rdi
  _QWORD *v9; // rsi
  unsigned int v10; // edi
  void *v11; // rbx
  void *v12; // rax
  __int64 v13; // rcx
  _OWORD v14[4]; // [rsp+30h] [rbp-48h] BYREF

  v4 = a4;
  if ( !a3 )
    return 2147500035LL;
  if ( !a4 )
    return 2147942487LL;
  v9 = CoTaskMemAlloc(0x10u);
  if ( v9 )
  {
    v11 = 0;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v4
      && (unsigned int)v4 <= 0x7FFFFFFF
      && (_mm_lfence(), v12 = CoTaskMemAlloc(v4), (v11 = v12) != 0) )
    {
      memcpy(v12, a3, v4);
      *(_DWORD *)v9 = v4;
      v9[1] = v11;
      v13 = *((_QWORD *)this + 3);
      v14[0] = *a2;
      v10 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD *))(*(_QWORD *)v13 + 32LL))(v13, v14, v9);
    }
    else
    {
      v10 = -2147024882;
    }
    CoTaskMemFree(v11);
  }
  else
  {
    v10 = -2147024882;
  }
  CoTaskMemFree(v9);
  return v10;
}

```

## disassembly

```asm
0x18000c0e0  push    rbx
0x18000c0e2  push    rbp
0x18000c0e3  push    rsi
0x18000c0e4  push    rdi
0x18000c0e5  push    r12
0x18000c0e7  push    r14
0x18000c0e9  push    r15
0x18000c0eb  sub     rsp, 40h
0x18000c0ef  mov     edi, r9d
0x18000c0f2  mov     r14, r8
0x18000c0f5  mov     r12, rdx
0x18000c0f8  mov     r15, rcx
0x18000c0fb  test    r8, r8
0x18000c0fe  jnz     short loc_18000C107
0x18000c100  mov     eax, 80004003h
0x18000c105  jmp     short loc_18000C165
0x18000c107  test    r9d, r9d
0x18000c10a  jnz     short loc_18000C113
0x18000c10c  mov     eax, 80070057h
0x18000c111  jmp     short loc_18000C165
0x18000c113  mov     ecx, 10h; cb
0x18000c118  call    cs:__imp_CoTaskMemAlloc
0x18000c11e  mov     rsi, rax
0x18000c121  mov     [rsp+78h+var_58], rax
0x18000c126  test    rax, rax
0x18000c129  jnz     short loc_18000C132
0x18000c12b  mov     edi, 8007000Eh
0x18000c130  jmp     short loc_18000C15A
0x18000c132  xor     ebx, ebx
0x18000c134  xor     edx, edx
0x18000c136  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c13a  div     rdi
0x18000c13d  cmp     rax, 1
0x18000c141  jb      short loc_18000C14B
0x18000c143  cmp     edi, 7FFFFFFFh
0x18000c149  jbe     short loc_18000C174
0x18000c14b  mov     edi, 8007000Eh
0x18000c150  mov     rcx, rbx; pv
0x18000c153  call    cs:__imp_CoTaskMemFree
0x18000c159  nop
0x18000c15a  mov     rcx, rsi; pv
0x18000c15d  call    cs:__imp_CoTaskMemFree
0x18000c163  mov     eax, edi
0x18000c165  add     rsp, 40h
0x18000c169  pop     r15
0x18000c16b  pop     r14
0x18000c16d  pop     r12
0x18000c16f  pop     rdi
0x18000c170  pop     rsi
0x18000c171  pop     rbp
0x18000c172  pop     rbx
0x18000c173  retn
0x18000c174  lfence
0x18000c177  mov     rcx, rdi; cb
0x18000c17a  call    cs:__imp_CoTaskMemAlloc
0x18000c180  mov     rbx, rax
0x18000c183  mov     [rsp+78h+var_50], rax
0x18000c188  test    rax, rax
0x18000c18b  jz      short loc_18000C14B
0x18000c18d  mov     r8, rdi; Size
0x18000c190  mov     rdx, r14; Src
0x18000c193  mov     rcx, rax; void *
0x18000c196  call    cs:__imp_memcpy
0x18000c19c  mov     [rsi], edi
0x18000c19e  mov     [rsi+8], rbx
0x18000c1a2  mov     rcx, [r15+18h]
0x18000c1a6  movups  xmm0, xmmword ptr [r12]
0x18000c1ab  movdqu  [rsp+78h+var_48], xmm0
0x18000c1b1  mov     rax, [rcx]
0x18000c1b4  mov     r8, rsi
0x18000c1b7  lea     rdx, [rsp+78h+var_48]
0x18000c1bc  mov     rax, [rax+20h]
0x18000c1c0  call    cs:__guard_dispatch_icall_fptr
0x18000c1c6  mov     edi, eax
0x18000c1c8  jmp     short loc_18000C150
```

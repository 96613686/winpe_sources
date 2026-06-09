# WriteAuditAttribute

- ea: `0x18000fef0`
- end: `0x18000ffe0`
- name: `WriteAuditAttribute`
- size: `240`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007918`

## callees

- `0x180005db4`
- `0x18000fef0`
- `0x180015010`

## string_xrefs

- `0x18000ff58`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000ffb9`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall WriteAuditAttribute(__int64 *a1, __int64 a2, __int64 a3, char a4, char a5)
{
  char v7; // bl
  __int64 v8; // rax
  const char *v9; // r14
  const char *v10; // rcx
  __int64 (__fastcall *v11)(__int64 *, _QWORD, __int64, _QWORD, const char *); // rax
  int v12; // eax
  unsigned int v13; // edi
  int v16; // eax
  unsigned int v17; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = a4 & 0x20;
  if ( (a4 & 0x20) == 0 && (a4 & 0x40) == 0 )
    return 0;
  v8 = *a1;
  v9 = L"true";
  v10 = L"true";
  v11 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, const char *))(v8 + 56);
  if ( !v7 )
    v10 = L"false";
  v12 = v11(a1, 0, a2, 0, v10);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v12);
    return v13;
  }
  if ( !a3 )
    return 0;
  if ( !a5 || !v7 )
    v9 = L"false";
  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, const char *))(*a1 + 56))(a1, 0, a3, 0, v9);
  v17 = v16;
  if ( v16 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFE,
    (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
    (const char *)(unsigned int)v16);
  return v17;
}

```

## disassembly

```asm
0x18000fef0  push    rbx
0x18000fef2  push    rbp
0x18000fef3  push    rsi
0x18000fef4  push    rdi
0x18000fef5  push    r14
0x18000fef7  push    r15
0x18000fef9  sub     rsp, 38h
0x18000fefd  mov     bl, r9b
0x18000ff00  mov     rbp, r8
0x18000ff03  mov     r8, rdx
0x18000ff06  mov     rsi, rcx
0x18000ff09  and     bl, 20h
0x18000ff0c  jnz     short loc_18000FF18
0x18000ff0e  test    r9b, 40h
0x18000ff12  jz      loc_18000FFD1
0x18000ff18  mov     rax, [rcx]
0x18000ff1b  lea     r14, aTrue; "true"
0x18000ff22  test    bl, bl
0x18000ff24  lea     r15, aFalse; "false"
0x18000ff2b  mov     rcx, r14
0x18000ff2e  setnz   dl
0x18000ff31  mov     rax, [rax+38h]
0x18000ff35  test    dl, dl
0x18000ff37  cmovz   rcx, r15
0x18000ff3b  xor     r9d, r9d
0x18000ff3e  mov     qword ptr [rsp+68h+var_48], rcx; int
0x18000ff43  xor     edx, edx
0x18000ff45  mov     rcx, rsi
0x18000ff48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff4d  mov     edi, eax
0x18000ff4f  test    eax, eax
0x18000ff51  jns     short loc_18000FF70
0x18000ff53  mov     rcx, [rsp+68h]; this
0x18000ff58  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000ff5f  mov     r9d, eax; char *
0x18000ff62  mov     edx, 0FBh; void *
0x18000ff67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff6c  mov     eax, edi
0x18000ff6e  jmp     short loc_18000FFD3
0x18000ff70  test    rbp, rbp
0x18000ff73  jz      short loc_18000FFD1
0x18000ff75  cmp     [rsp+68h+arg_20], 0
0x18000ff7d  mov     rax, [rsi]
0x18000ff80  mov     r10, [rax+38h]
0x18000ff84  jz      short loc_18000FF8E
0x18000ff86  test    bl, bl
0x18000ff88  jz      short loc_18000FF8E
0x18000ff8a  mov     al, 1
0x18000ff8c  jmp     short loc_18000FF90
0x18000ff8e  xor     al, al
0x18000ff90  test    al, al
0x18000ff92  mov     r8, rbp
0x18000ff95  mov     rcx, rsi
0x18000ff98  mov     rax, r10
0x18000ff9b  cmovz   r14, r15
0x18000ff9f  xor     r9d, r9d
0x18000ffa2  xor     edx, edx
0x18000ffa4  mov     qword ptr [rsp+68h+var_48], r14; int
0x18000ffa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffae  mov     ebx, eax
0x18000ffb0  test    eax, eax
0x18000ffb2  jns     short loc_18000FFD1
0x18000ffb4  mov     rcx, [rsp+68h]; this
0x18000ffb9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000ffc0  mov     r9d, eax; char *
0x18000ffc3  mov     edx, 0FEh; void *
0x18000ffc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffcd  mov     eax, ebx
0x18000ffcf  jmp     short loc_18000FFD3
0x18000ffd1  xor     eax, eax
0x18000ffd3  add     rsp, 38h
0x18000ffd7  pop     r15
0x18000ffd9  pop     r14
0x18000ffdb  pop     rdi
0x18000ffdc  pop     rsi
0x18000ffdd  pop     rbp
0x18000ffde  pop     rbx
0x18000ffdf  retn
```

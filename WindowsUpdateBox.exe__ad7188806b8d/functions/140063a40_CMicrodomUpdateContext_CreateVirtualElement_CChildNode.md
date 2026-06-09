# CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)

- ea: `0x140063a40`
- end: `0x140063c6e`
- name: `?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct CChildNode **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006439c`
- `0x140065c88`

## callees

- `0x140062828`
- `0x140063a40`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140063c16`
- `KERNEL32!HeapFree` at `0x140063c16`
- `KERNEL32!HeapAlloc` at `0x140063a76`
- `KERNEL32!HeapAlloc` at `0x140063b08`
- `KERNEL32!HeapAlloc` at `0x140063a76`
- `KERNEL32!HeapAlloc` at `0x140063b08`
- `KERNEL32!GetProcessHeap` at `0x140063a61`
- `KERNEL32!GetProcessHeap` at `0x140063af1`
- `KERNEL32!GetProcessHeap` at `0x140063c02`
- `KERNEL32!GetProcessHeap` at `0x140063a61`
- `KERNEL32!GetProcessHeap` at `0x140063af1`
- `KERNEL32!GetProcessHeap` at `0x140063c02`

## string_xrefs

- `0x140063aaf`: `onecore\base\xml\udom_modify.cpp`
- `0x140063bc2`: `onecore\base\xml\udom_modify.cpp`
- `0x140063ac6`: `CMicrodomUpdateContext::CreateVirtualElement`
- `0x140063bd9`: `CMicrodomUpdateContext::CreateVirtualElement`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::CreateVirtualElement(CMicrodomUpdateContext *this, struct CChildNode **a2)
{
  HANDLE ProcessHeap; // rax
  CChildNode *v5; // rax
  __int64 v6; // rdx
  CChildNode *v7; // rbx
  HANDLE v9; // rax
  char *v10; // rax
  __int64 v11; // rdx
  HANDLE v12; // rax
  __int128 v13; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+30h] [rbp-10h]
  const char *v15; // [rsp+38h] [rbp-8h]

  *a2 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (CChildNode *)HeapAlloc(ProcessHeap, 0, 0x40u);
  v7 = v5;
  if ( v5 )
  {
    *((_QWORD *)v5 + 2) = 0;
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 6) = 0;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
  {
    v14 = 1251;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualElement";
    v15 = "NewChild.Allocate()";
    RtlReportErrorOrigination(&v13, v6, 3221225495LL);
    return 3221225495LL;
  }
  v9 = GetProcessHeap();
  v10 = (char *)HeapAlloc(v9, 0, 0xD0u);
  if ( v10 )
  {
    *(_OWORD *)(v10 + 8) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_OWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 6) = 0;
    *(_OWORD *)(v10 + 56) = 0;
    *((_QWORD *)v10 + 9) = 0;
    *((_OWORD *)v10 + 5) = 0;
    *((_QWORD *)v10 + 12) = 0;
    *(_QWORD *)v10 = &CElementModification::`vftable';
    *((_QWORD *)v10 + 13) = 0;
    *((_QWORD *)v10 + 14) = 0;
    *((_WORD *)v10 + 60) = 0;
    *((_OWORD *)v10 + 8) = 0;
    *((_DWORD *)v10 + 34) = -1;
    v10[144] = 0;
    *((_DWORD *)v10 + 37) = 0;
    *((_QWORD *)v10 + 19) = 0;
    *((_QWORD *)v10 + 20) = 0;
    *((_QWORD *)v10 + 21) = 0;
    *((_DWORD *)v10 + 44) = 0;
    *((_QWORD *)v10 + 23) = 0;
    *((_QWORD *)v10 + 24) = 0;
    *((_QWORD *)v10 + 25) = 0;
    v13 = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( *((_QWORD *)v7 + 5) )
    __debugbreak();
  *((_QWORD *)v7 + 5) = v10;
  if ( !v10 )
  {
    v14 = 1252;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualElement";
    v15 = "NewChild->Element.Allocate()";
    RtlReportErrorOrigination(&v13, v11, 3221225495LL);
    CChildNode::~CChildNode(v7);
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v7);
    return 3221225495LL;
  }
  *((_QWORD *)v10 + 13) = this;
  *((_QWORD *)v10 + 14) = 0;
  *((_QWORD *)v7 + 7) = v10;
  *a2 = v7;
  *((_QWORD *)v7 + 1) = *((_QWORD *)this + 2);
  *(_QWORD *)v7 = (char *)this + 8;
  **((_QWORD **)this + 2) = v7;
  *((_QWORD *)this + 2) = v7;
  *((_QWORD *)v7 + 2) = (char *)this + 8;
  ++*((_QWORD *)this + 4);
  return 0;
}

```

## disassembly

```asm
0x140063a40  mov     [rsp-18h+arg_10], rbx
0x140063a45  mov     [rsp-18h+arg_18], rsi
0x140063a4a  push    rbp
0x140063a4b  push    rdi
0x140063a4c  push    r14
0x140063a4e  mov     rbp, rsp
0x140063a51  sub     rsp, 40h
0x140063a55  xor     r14d, r14d
0x140063a58  mov     rsi, rdx
0x140063a5b  mov     [rdx], r14
0x140063a5e  mov     rdi, rcx
0x140063a61  call    cs:__imp_GetProcessHeap
0x140063a68  nop     dword ptr [rax+rax+00h]
0x140063a6d  xor     edx, edx; dwFlags
0x140063a6f  lea     r8d, [r14+40h]; dwBytes
0x140063a73  mov     rcx, rax; hHeap
0x140063a76  call    cs:__imp_HeapAlloc
0x140063a7d  nop     dword ptr [rax+rax+00h]
0x140063a82  mov     rbx, rax
0x140063a85  test    rax, rax
0x140063a88  jz      short loc_140063AA7
0x140063a8a  mov     [rax+10h], r14
0x140063a8e  mov     [rax], r14
0x140063a91  mov     [rax+8], r14
0x140063a95  mov     [rax+18h], r14
0x140063a99  mov     [rax+20h], r14
0x140063a9d  mov     [rax+28h], r14
0x140063aa1  mov     [rax+30h], r14
0x140063aa5  jmp     short loc_140063AAA
0x140063aa7  mov     rbx, r14
0x140063aaa  test    rbx, rbx
0x140063aad  jnz     short loc_140063AF1
0x140063aaf  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140063ab6  mov     [rbp+var_10], 4E3h
0x140063abe  mov     qword ptr [rbp+var_20], rax
0x140063ac2  lea     rcx, [rbp+var_20]
0x140063ac6  lea     rax, aCmicrodomupdat_2; "CMicrodomUpdateContext::CreateVirtualEl"...
0x140063acd  mov     r8d, 0C0000017h
0x140063ad3  mov     qword ptr [rbp+var_20+8], rax
0x140063ad7  lea     rax, aNewchildAlloca; "NewChild.Allocate()"
0x140063ade  mov     [rbp+var_8], rax
0x140063ae2  call    RtlReportErrorOrigination
0x140063ae7  mov     eax, 0C0000017h
0x140063aec  jmp     loc_140063C5A
0x140063af1  call    cs:__imp_GetProcessHeap
0x140063af8  nop     dword ptr [rax+rax+00h]
0x140063afd  xor     edx, edx; dwFlags
0x140063aff  mov     r8d, 0D0h; dwBytes
0x140063b05  mov     rcx, rax; hHeap
0x140063b08  call    cs:__imp_HeapAlloc
0x140063b0f  nop     dword ptr [rax+rax+00h]
0x140063b14  test    rax, rax
0x140063b17  jz      loc_140063BAF
0x140063b1d  xorps   xmm0, xmm0
0x140063b20  xor     ecx, ecx
0x140063b22  movups  xmmword ptr [rax+8], xmm0
0x140063b26  mov     [rax+18h], rcx
0x140063b2a  movups  xmmword ptr [rax+20h], xmm0
0x140063b2e  mov     [rax+30h], rcx
0x140063b32  movups  xmmword ptr [rax+38h], xmm0
0x140063b36  mov     [rax+48h], rcx
0x140063b3a  movups  xmmword ptr [rax+50h], xmm0
0x140063b3e  mov     [rax+60h], rcx
0x140063b42  lea     rcx, ??_7CElementModification@@6B@; const CElementModification::`vftable'
0x140063b49  mov     [rax], rcx
0x140063b4c  mov     [rax+68h], r14
0x140063b50  mov     [rax+70h], r14
0x140063b54  mov     [rax+78h], r14w
0x140063b59  movups  xmmword ptr [rax+80h], xmm0
0x140063b60  mov     dword ptr [rax+88h], 0FFFFFFFFh
0x140063b6a  mov     [rax+90h], r14b
0x140063b71  mov     [rax+94h], r14d
0x140063b78  mov     [rax+98h], r14
0x140063b7f  mov     [rax+0A0h], r14
0x140063b86  mov     [rax+0A8h], r14
0x140063b8d  mov     [rax+0B0h], r14d
0x140063b94  mov     [rax+0B8h], r14
0x140063b9b  mov     [rax+0C0h], r14
0x140063ba2  mov     [rax+0C8h], r14
0x140063ba9  movups  [rbp+var_20], xmm0
0x140063bad  jmp     short loc_140063BB2
0x140063baf  mov     rax, r14
0x140063bb2  cmp     [rbx+28h], r14
0x140063bb6  jz      short loc_140063BB9
0x140063bb8  int     3; Trap to Debugger
0x140063bb9  mov     [rbx+28h], rax
0x140063bbd  test    rax, rax
0x140063bc0  jnz     short loc_140063C27
0x140063bc2  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140063bc9  mov     [rbp+var_10], 4E4h
0x140063bd1  mov     qword ptr [rbp+var_20], rax
0x140063bd5  lea     rcx, [rbp+var_20]
0x140063bd9  lea     rax, aCmicrodomupdat_2; "CMicrodomUpdateContext::CreateVirtualEl"...
0x140063be0  mov     r8d, 0C0000017h
0x140063be6  mov     qword ptr [rbp+var_20+8], rax
0x140063bea  lea     rax, aNewchildElemen; "NewChild->Element.Allocate()"
0x140063bf1  mov     [rbp+var_8], rax
0x140063bf5  call    RtlReportErrorOrigination
0x140063bfa  mov     rcx, rbx; this
0x140063bfd  call    ??1CChildNode@@QEAA@XZ; CChildNode::~CChildNode(void)
0x140063c02  call    cs:__imp_GetProcessHeap
0x140063c09  nop     dword ptr [rax+rax+00h]
0x140063c0e  mov     r8, rbx; lpMem
0x140063c11  xor     edx, edx; dwFlags
0x140063c13  mov     rcx, rax; hHeap
0x140063c16  call    cs:__imp_HeapFree
0x140063c1d  nop     dword ptr [rax+rax+00h]
0x140063c22  jmp     loc_140063AE7
0x140063c27  mov     [rax+68h], rdi
0x140063c2b  lea     rcx, [rdi+8]
0x140063c2f  mov     [rax+70h], r14
0x140063c33  mov     [rbx+38h], rax
0x140063c37  mov     [rsi], rbx
0x140063c3a  mov     rax, [rcx+8]
0x140063c3e  mov     [rbx+8], rax
0x140063c42  mov     [rbx], rcx
0x140063c45  mov     rax, [rcx+8]
0x140063c49  mov     [rax], rbx
0x140063c4c  mov     [rcx+8], rbx
0x140063c50  mov     [rbx+10h], rcx
0x140063c54  inc     qword ptr [rcx+18h]
0x140063c58  xor     eax, eax
0x140063c5a  mov     rbx, [rsp+40h+arg_10]
0x140063c5f  mov     rsi, [rsp+40h+arg_18]
0x140063c64  add     rsp, 40h
0x140063c68  pop     r14
0x140063c6a  pop     rdi
0x140063c6b  pop     rbp
0x140063c6c  retn
```

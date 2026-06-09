# CMicrodomUpdateContext::CreateVirtualTextual(CChildNode * &)

- ea: `0x140063c74`
- end: `0x140063e5f`
- name: `?CreateVirtualTextual@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct CChildNode **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140062ce0`
- `0x14006439c`
- `0x140065dc8`

## callees

- `0x140062828`
- `0x140063c74`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140063e07`
- `KERNEL32!HeapFree` at `0x140063e07`
- `KERNEL32!HeapAlloc` at `0x140063caa`
- `KERNEL32!HeapAlloc` at `0x140063d3c`
- `KERNEL32!HeapAlloc` at `0x140063caa`
- `KERNEL32!HeapAlloc` at `0x140063d3c`
- `KERNEL32!GetProcessHeap` at `0x140063c95`
- `KERNEL32!GetProcessHeap` at `0x140063d25`
- `KERNEL32!GetProcessHeap` at `0x140063df3`
- `KERNEL32!GetProcessHeap` at `0x140063c95`
- `KERNEL32!GetProcessHeap` at `0x140063d25`
- `KERNEL32!GetProcessHeap` at `0x140063df3`

## string_xrefs

- `0x140063ce3`: `onecore\base\xml\udom_modify.cpp`
- `0x140063db3`: `onecore\base\xml\udom_modify.cpp`
- `0x140063cfa`: `CMicrodomUpdateContext::CreateVirtualTextual`
- `0x140063dca`: `CMicrodomUpdateContext::CreateVirtualTextual`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::CreateVirtualTextual(CMicrodomUpdateContext *this, struct CChildNode **a2)
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
    v14 = 1224;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualTextual";
    v15 = "NewChild.Allocate()";
    RtlReportErrorOrigination(&v13, v6, 3221225495LL);
    return 3221225495LL;
  }
  v9 = GetProcessHeap();
  v10 = (char *)HeapAlloc(v9, 0, 0x90u);
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
    *(_QWORD *)v10 = &CTextModification::`vftable';
    *((_QWORD *)v10 + 13) = 0;
    *((_QWORD *)v10 + 14) = 0;
    *((_WORD *)v10 + 60) = 0;
    *((_OWORD *)v10 + 8) = 0;
    *((_DWORD *)v10 + 34) = -1;
    v13 = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( *((_QWORD *)v7 + 3) )
    __debugbreak();
  *((_QWORD *)v7 + 3) = v10;
  if ( !v10 )
  {
    v14 = 1225;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualTextual";
    v15 = "NewChild->Text.Allocate()";
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
0x140063c74  mov     [rsp-18h+arg_10], rbx
0x140063c79  mov     [rsp-18h+arg_18], rsi
0x140063c7e  push    rbp
0x140063c7f  push    rdi
0x140063c80  push    r14
0x140063c82  mov     rbp, rsp
0x140063c85  sub     rsp, 40h
0x140063c89  xor     r14d, r14d
0x140063c8c  mov     rsi, rdx
0x140063c8f  mov     [rdx], r14
0x140063c92  mov     rdi, rcx
0x140063c95  call    cs:__imp_GetProcessHeap
0x140063c9c  nop     dword ptr [rax+rax+00h]
0x140063ca1  xor     edx, edx; dwFlags
0x140063ca3  lea     r8d, [r14+40h]; dwBytes
0x140063ca7  mov     rcx, rax; hHeap
0x140063caa  call    cs:__imp_HeapAlloc
0x140063cb1  nop     dword ptr [rax+rax+00h]
0x140063cb6  mov     rbx, rax
0x140063cb9  test    rax, rax
0x140063cbc  jz      short loc_140063CDB
0x140063cbe  mov     [rax+10h], r14
0x140063cc2  mov     [rax], r14
0x140063cc5  mov     [rax+8], r14
0x140063cc9  mov     [rax+18h], r14
0x140063ccd  mov     [rax+20h], r14
0x140063cd1  mov     [rax+28h], r14
0x140063cd5  mov     [rax+30h], r14
0x140063cd9  jmp     short loc_140063CDE
0x140063cdb  mov     rbx, r14
0x140063cde  test    rbx, rbx
0x140063ce1  jnz     short loc_140063D25
0x140063ce3  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140063cea  mov     [rbp+var_10], 4C8h
0x140063cf2  mov     qword ptr [rbp+var_20], rax
0x140063cf6  lea     rcx, [rbp+var_20]
0x140063cfa  lea     rax, aCmicrodomupdat_1; "CMicrodomUpdateContext::CreateVirtualTe"...
0x140063d01  mov     r8d, 0C0000017h
0x140063d07  mov     qword ptr [rbp+var_20+8], rax
0x140063d0b  lea     rax, aNewchildAlloca; "NewChild.Allocate()"
0x140063d12  mov     [rbp+var_8], rax
0x140063d16  call    RtlReportErrorOrigination
0x140063d1b  mov     eax, 0C0000017h
0x140063d20  jmp     loc_140063E4B
0x140063d25  call    cs:__imp_GetProcessHeap
0x140063d2c  nop     dword ptr [rax+rax+00h]
0x140063d31  xor     edx, edx; dwFlags
0x140063d33  mov     r8d, 90h; dwBytes
0x140063d39  mov     rcx, rax; hHeap
0x140063d3c  call    cs:__imp_HeapAlloc
0x140063d43  nop     dword ptr [rax+rax+00h]
0x140063d48  test    rax, rax
0x140063d4b  jz      short loc_140063DA0
0x140063d4d  xorps   xmm0, xmm0
0x140063d50  xor     ecx, ecx
0x140063d52  movups  xmmword ptr [rax+8], xmm0
0x140063d56  mov     [rax+18h], rcx
0x140063d5a  movups  xmmword ptr [rax+20h], xmm0
0x140063d5e  mov     [rax+30h], rcx
0x140063d62  movups  xmmword ptr [rax+38h], xmm0
0x140063d66  mov     [rax+48h], rcx
0x140063d6a  movups  xmmword ptr [rax+50h], xmm0
0x140063d6e  mov     [rax+60h], rcx
0x140063d72  lea     rcx, ??_7CTextModification@@6B@; const CTextModification::`vftable'
0x140063d79  mov     [rax], rcx
0x140063d7c  mov     [rax+68h], r14
0x140063d80  mov     [rax+70h], r14
0x140063d84  mov     [rax+78h], r14w
0x140063d89  movups  xmmword ptr [rax+80h], xmm0
0x140063d90  mov     dword ptr [rax+88h], 0FFFFFFFFh
0x140063d9a  movups  [rbp+var_20], xmm0
0x140063d9e  jmp     short loc_140063DA3
0x140063da0  mov     rax, r14
0x140063da3  cmp     [rbx+18h], r14
0x140063da7  jz      short loc_140063DAA
0x140063da9  int     3; Trap to Debugger
0x140063daa  mov     [rbx+18h], rax
0x140063dae  test    rax, rax
0x140063db1  jnz     short loc_140063E18
0x140063db3  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140063dba  mov     [rbp+var_10], 4C9h
0x140063dc2  mov     qword ptr [rbp+var_20], rax
0x140063dc6  lea     rcx, [rbp+var_20]
0x140063dca  lea     rax, aCmicrodomupdat_1; "CMicrodomUpdateContext::CreateVirtualTe"...
0x140063dd1  mov     r8d, 0C0000017h
0x140063dd7  mov     qword ptr [rbp+var_20+8], rax
0x140063ddb  lea     rax, aNewchildTextAl; "NewChild->Text.Allocate()"
0x140063de2  mov     [rbp+var_8], rax
0x140063de6  call    RtlReportErrorOrigination
0x140063deb  mov     rcx, rbx; this
0x140063dee  call    ??1CChildNode@@QEAA@XZ; CChildNode::~CChildNode(void)
0x140063df3  call    cs:__imp_GetProcessHeap
0x140063dfa  nop     dword ptr [rax+rax+00h]
0x140063dff  mov     r8, rbx; lpMem
0x140063e02  xor     edx, edx; dwFlags
0x140063e04  mov     rcx, rax; hHeap
0x140063e07  call    cs:__imp_HeapFree
0x140063e0e  nop     dword ptr [rax+rax+00h]
0x140063e13  jmp     loc_140063D1B
0x140063e18  mov     [rax+68h], rdi
0x140063e1c  lea     rcx, [rdi+8]
0x140063e20  mov     [rax+70h], r14
0x140063e24  mov     [rbx+38h], rax
0x140063e28  mov     [rsi], rbx
0x140063e2b  mov     rax, [rcx+8]
0x140063e2f  mov     [rbx+8], rax
0x140063e33  mov     [rbx], rcx
0x140063e36  mov     rax, [rcx+8]
0x140063e3a  mov     [rax], rbx
0x140063e3d  mov     [rcx+8], rbx
0x140063e41  mov     [rbx+10h], rcx
0x140063e45  inc     qword ptr [rcx+18h]
0x140063e49  xor     eax, eax
0x140063e4b  mov     rbx, [rsp+40h+arg_10]
0x140063e50  mov     rsi, [rsp+40h+arg_18]
0x140063e55  add     rsp, 40h
0x140063e59  pop     r14
0x140063e5b  pop     rdi
0x140063e5c  pop     rbp
0x140063e5d  retn
```

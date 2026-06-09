# CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)

- ea: `0x140063644`
- end: `0x140063844`
- name: `?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct CChildNode **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006439c`
- `0x140065b5c`

## callees

- `0x140062828`
- `0x140063644`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400637ec`
- `KERNEL32!HeapFree` at `0x1400637ec`
- `KERNEL32!HeapAlloc` at `0x14006367a`
- `KERNEL32!HeapAlloc` at `0x14006370c`
- `KERNEL32!HeapAlloc` at `0x14006367a`
- `KERNEL32!HeapAlloc` at `0x14006370c`
- `KERNEL32!GetProcessHeap` at `0x140063665`
- `KERNEL32!GetProcessHeap` at `0x1400636f5`
- `KERNEL32!GetProcessHeap` at `0x1400637d8`
- `KERNEL32!GetProcessHeap` at `0x140063665`
- `KERNEL32!GetProcessHeap` at `0x1400636f5`
- `KERNEL32!GetProcessHeap` at `0x1400637d8`

## string_xrefs

- `0x1400636b3`: `onecore\base\xml\udom_modify.cpp`
- `0x140063798`: `onecore\base\xml\udom_modify.cpp`
- `0x1400636ca`: `CMicrodomUpdateContext::CreateVirtualAttribute`
- `0x1400637af`: `CMicrodomUpdateContext::CreateVirtualAttribute`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::CreateVirtualAttribute(CMicrodomUpdateContext *this, struct CChildNode **a2)
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
    v14 = 1281;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualAttribute";
    v15 = "NewChild.Allocate()";
    RtlReportErrorOrigination(&v13, v6, 3221225495LL);
    return 3221225495LL;
  }
  v9 = GetProcessHeap();
  v10 = (char *)HeapAlloc(v9, 0, 0xA8u);
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
    *(_QWORD *)v10 = &CAttributeModification::`vftable';
    *((_QWORD *)v10 + 13) = 0;
    *((_QWORD *)v10 + 14) = 0;
    *((_WORD *)v10 + 60) = 0;
    *((_QWORD *)v10 + 18) = 0;
    *((_QWORD *)v10 + 16) = 0;
    *((_QWORD *)v10 + 17) = 0;
    *(_OWORD *)(v10 + 152) = 0;
    *((_DWORD *)v10 + 40) = -1;
    v13 = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( *((_QWORD *)v7 + 4) )
    __debugbreak();
  *((_QWORD *)v7 + 4) = v10;
  if ( !v10 )
  {
    v14 = 1282;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualAttribute";
    v15 = "NewChild->Attribute.Allocate()";
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
0x140063644  mov     [rsp-18h+arg_10], rbx
0x140063649  mov     [rsp-18h+arg_18], rsi
0x14006364e  push    rbp
0x14006364f  push    rdi
0x140063650  push    r14
0x140063652  mov     rbp, rsp
0x140063655  sub     rsp, 40h
0x140063659  xor     r14d, r14d
0x14006365c  mov     rsi, rdx
0x14006365f  mov     [rdx], r14
0x140063662  mov     rdi, rcx
0x140063665  call    cs:__imp_GetProcessHeap
0x14006366c  nop     dword ptr [rax+rax+00h]
0x140063671  xor     edx, edx; dwFlags
0x140063673  lea     r8d, [r14+40h]; dwBytes
0x140063677  mov     rcx, rax; hHeap
0x14006367a  call    cs:__imp_HeapAlloc
0x140063681  nop     dword ptr [rax+rax+00h]
0x140063686  mov     rbx, rax
0x140063689  test    rax, rax
0x14006368c  jz      short loc_1400636AB
0x14006368e  mov     [rax+10h], r14
0x140063692  mov     [rax], r14
0x140063695  mov     [rax+8], r14
0x140063699  mov     [rax+18h], r14
0x14006369d  mov     [rax+20h], r14
0x1400636a1  mov     [rax+28h], r14
0x1400636a5  mov     [rax+30h], r14
0x1400636a9  jmp     short loc_1400636AE
0x1400636ab  mov     rbx, r14
0x1400636ae  test    rbx, rbx
0x1400636b1  jnz     short loc_1400636F5
0x1400636b3  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1400636ba  mov     [rbp+var_10], 501h
0x1400636c2  mov     qword ptr [rbp+var_20], rax
0x1400636c6  lea     rcx, [rbp+var_20]
0x1400636ca  lea     rax, aCmicrodomupdat_0; "CMicrodomUpdateContext::CreateVirtualAt"...
0x1400636d1  mov     r8d, 0C0000017h
0x1400636d7  mov     qword ptr [rbp+var_20+8], rax
0x1400636db  lea     rax, aNewchildAlloca; "NewChild.Allocate()"
0x1400636e2  mov     [rbp+var_8], rax
0x1400636e6  call    RtlReportErrorOrigination
0x1400636eb  mov     eax, 0C0000017h
0x1400636f0  jmp     loc_140063830
0x1400636f5  call    cs:__imp_GetProcessHeap
0x1400636fc  nop     dword ptr [rax+rax+00h]
0x140063701  xor     edx, edx; dwFlags
0x140063703  mov     r8d, 0A8h; dwBytes
0x140063709  mov     rcx, rax; hHeap
0x14006370c  call    cs:__imp_HeapAlloc
0x140063713  nop     dword ptr [rax+rax+00h]
0x140063718  test    rax, rax
0x14006371b  jz      short loc_140063785
0x14006371d  xorps   xmm0, xmm0
0x140063720  xor     ecx, ecx
0x140063722  movups  xmmword ptr [rax+8], xmm0
0x140063726  mov     [rax+18h], rcx
0x14006372a  movups  xmmword ptr [rax+20h], xmm0
0x14006372e  mov     [rax+30h], rcx
0x140063732  movups  xmmword ptr [rax+38h], xmm0
0x140063736  mov     [rax+48h], rcx
0x14006373a  movups  xmmword ptr [rax+50h], xmm0
0x14006373e  mov     [rax+60h], rcx
0x140063742  lea     rcx, ??_7CAttributeModification@@6B@; const CAttributeModification::`vftable'
0x140063749  mov     [rax], rcx
0x14006374c  mov     [rax+68h], r14
0x140063750  mov     [rax+70h], r14
0x140063754  mov     [rax+78h], r14w
0x140063759  mov     [rax+90h], r14
0x140063760  mov     [rax+80h], r14
0x140063767  mov     [rax+88h], r14
0x14006376e  movups  xmmword ptr [rax+98h], xmm0
0x140063775  mov     dword ptr [rax+0A0h], 0FFFFFFFFh
0x14006377f  movups  [rbp+var_20], xmm0
0x140063783  jmp     short loc_140063788
0x140063785  mov     rax, r14
0x140063788  cmp     [rbx+20h], r14
0x14006378c  jz      short loc_14006378F
0x14006378e  int     3; Trap to Debugger
0x14006378f  mov     [rbx+20h], rax
0x140063793  test    rax, rax
0x140063796  jnz     short loc_1400637FD
0x140063798  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x14006379f  mov     [rbp+var_10], 502h
0x1400637a7  mov     qword ptr [rbp+var_20], rax
0x1400637ab  lea     rcx, [rbp+var_20]
0x1400637af  lea     rax, aCmicrodomupdat_0; "CMicrodomUpdateContext::CreateVirtualAt"...
0x1400637b6  mov     r8d, 0C0000017h
0x1400637bc  mov     qword ptr [rbp+var_20+8], rax
0x1400637c0  lea     rax, aNewchildAttrib; "NewChild->Attribute.Allocate()"
0x1400637c7  mov     [rbp+var_8], rax
0x1400637cb  call    RtlReportErrorOrigination
0x1400637d0  mov     rcx, rbx; this
0x1400637d3  call    ??1CChildNode@@QEAA@XZ; CChildNode::~CChildNode(void)
0x1400637d8  call    cs:__imp_GetProcessHeap
0x1400637df  nop     dword ptr [rax+rax+00h]
0x1400637e4  mov     r8, rbx; lpMem
0x1400637e7  xor     edx, edx; dwFlags
0x1400637e9  mov     rcx, rax; hHeap
0x1400637ec  call    cs:__imp_HeapFree
0x1400637f3  nop     dword ptr [rax+rax+00h]
0x1400637f8  jmp     loc_1400636EB
0x1400637fd  mov     [rax+68h], rdi
0x140063801  lea     rcx, [rdi+8]
0x140063805  mov     [rax+70h], r14
0x140063809  mov     [rbx+38h], rax
0x14006380d  mov     [rsi], rbx
0x140063810  mov     rax, [rcx+8]
0x140063814  mov     [rbx+8], rax
0x140063818  mov     [rbx], rcx
0x14006381b  mov     rax, [rcx+8]
0x14006381f  mov     [rax], rbx
0x140063822  mov     [rcx+8], rbx
0x140063826  mov     [rbx+10h], rcx
0x14006382a  inc     qword ptr [rcx+18h]
0x14006382e  xor     eax, eax
0x140063830  mov     rbx, [rsp+40h+arg_10]
0x140063835  mov     rsi, [rsp+40h+arg_18]
0x14006383a  add     rsp, 40h
0x14006383e  pop     r14
0x140063840  pop     rdi
0x140063841  pop     rbp
0x140063842  retn
```

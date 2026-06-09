# CMicrodomUpdateContext::CreateVirtualComment(CChildNode * &)

- ea: `0x14006384c`
- end: `0x140063a37`
- name: `?CreateVirtualComment@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct CChildNode **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006439c`

## callees

- `0x140062828`
- `0x14006384c`
- `0x140072764`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400639df`
- `KERNEL32!HeapFree` at `0x1400639df`
- `KERNEL32!HeapAlloc` at `0x140063882`
- `KERNEL32!HeapAlloc` at `0x140063914`
- `KERNEL32!HeapAlloc` at `0x140063882`
- `KERNEL32!HeapAlloc` at `0x140063914`
- `KERNEL32!GetProcessHeap` at `0x14006386d`
- `KERNEL32!GetProcessHeap` at `0x1400638fd`
- `KERNEL32!GetProcessHeap` at `0x1400639cb`
- `KERNEL32!GetProcessHeap` at `0x14006386d`
- `KERNEL32!GetProcessHeap` at `0x1400638fd`
- `KERNEL32!GetProcessHeap` at `0x1400639cb`

## string_xrefs

- `0x1400638bb`: `onecore\base\xml\udom_modify.cpp`
- `0x14006398b`: `onecore\base\xml\udom_modify.cpp`
- `0x1400638d2`: `CMicrodomUpdateContext::CreateVirtualComment`
- `0x1400639a2`: `CMicrodomUpdateContext::CreateVirtualComment`
- `0x1400639b3`: `NewChild->Comment.Allocate()`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::CreateVirtualComment(CMicrodomUpdateContext *this, struct CChildNode **a2)
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
    v14 = 1197;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualComment";
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
    *(_QWORD *)v10 = &CCommentModification::`vftable';
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
  if ( *((_QWORD *)v7 + 6) )
    __debugbreak();
  *((_QWORD *)v7 + 6) = v10;
  if ( !v10 )
  {
    v14 = 1198;
    *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
    *((_QWORD *)&v13 + 1) = "CMicrodomUpdateContext::CreateVirtualComment";
    v15 = "NewChild->Comment.Allocate()";
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
0x14006384c  mov     [rsp-18h+arg_10], rbx
0x140063851  mov     [rsp-18h+arg_18], rsi
0x140063856  push    rbp
0x140063857  push    rdi
0x140063858  push    r14
0x14006385a  mov     rbp, rsp
0x14006385d  sub     rsp, 40h
0x140063861  xor     r14d, r14d
0x140063864  mov     rsi, rdx
0x140063867  mov     [rdx], r14
0x14006386a  mov     rdi, rcx
0x14006386d  call    cs:__imp_GetProcessHeap
0x140063874  nop     dword ptr [rax+rax+00h]
0x140063879  xor     edx, edx; dwFlags
0x14006387b  lea     r8d, [r14+40h]; dwBytes
0x14006387f  mov     rcx, rax; hHeap
0x140063882  call    cs:__imp_HeapAlloc
0x140063889  nop     dword ptr [rax+rax+00h]
0x14006388e  mov     rbx, rax
0x140063891  test    rax, rax
0x140063894  jz      short loc_1400638B3
0x140063896  mov     [rax+10h], r14
0x14006389a  mov     [rax], r14
0x14006389d  mov     [rax+8], r14
0x1400638a1  mov     [rax+18h], r14
0x1400638a5  mov     [rax+20h], r14
0x1400638a9  mov     [rax+28h], r14
0x1400638ad  mov     [rax+30h], r14
0x1400638b1  jmp     short loc_1400638B6
0x1400638b3  mov     rbx, r14
0x1400638b6  test    rbx, rbx
0x1400638b9  jnz     short loc_1400638FD
0x1400638bb  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x1400638c2  mov     [rbp+var_10], 4ADh
0x1400638ca  mov     qword ptr [rbp+var_20], rax
0x1400638ce  lea     rcx, [rbp+var_20]
0x1400638d2  lea     rax, aCmicrodomupdat; "CMicrodomUpdateContext::CreateVirtualCo"...
0x1400638d9  mov     r8d, 0C0000017h
0x1400638df  mov     qword ptr [rbp+var_20+8], rax
0x1400638e3  lea     rax, aNewchildAlloca; "NewChild.Allocate()"
0x1400638ea  mov     [rbp+var_8], rax
0x1400638ee  call    RtlReportErrorOrigination
0x1400638f3  mov     eax, 0C0000017h
0x1400638f8  jmp     loc_140063A23
0x1400638fd  call    cs:__imp_GetProcessHeap
0x140063904  nop     dword ptr [rax+rax+00h]
0x140063909  xor     edx, edx; dwFlags
0x14006390b  mov     r8d, 90h; dwBytes
0x140063911  mov     rcx, rax; hHeap
0x140063914  call    cs:__imp_HeapAlloc
0x14006391b  nop     dword ptr [rax+rax+00h]
0x140063920  test    rax, rax
0x140063923  jz      short loc_140063978
0x140063925  xorps   xmm0, xmm0
0x140063928  xor     ecx, ecx
0x14006392a  movups  xmmword ptr [rax+8], xmm0
0x14006392e  mov     [rax+18h], rcx
0x140063932  movups  xmmword ptr [rax+20h], xmm0
0x140063936  mov     [rax+30h], rcx
0x14006393a  movups  xmmword ptr [rax+38h], xmm0
0x14006393e  mov     [rax+48h], rcx
0x140063942  movups  xmmword ptr [rax+50h], xmm0
0x140063946  mov     [rax+60h], rcx
0x14006394a  lea     rcx, ??_7CCommentModification@@6B@; const CCommentModification::`vftable'
0x140063951  mov     [rax], rcx
0x140063954  mov     [rax+68h], r14
0x140063958  mov     [rax+70h], r14
0x14006395c  mov     [rax+78h], r14w
0x140063961  movups  xmmword ptr [rax+80h], xmm0
0x140063968  mov     dword ptr [rax+88h], 0FFFFFFFFh
0x140063972  movups  [rbp+var_20], xmm0
0x140063976  jmp     short loc_14006397B
0x140063978  mov     rax, r14
0x14006397b  cmp     [rbx+30h], r14
0x14006397f  jz      short loc_140063982
0x140063981  int     3; Trap to Debugger
0x140063982  mov     [rbx+30h], rax
0x140063986  test    rax, rax
0x140063989  jnz     short loc_1400639F0
0x14006398b  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x140063992  mov     [rbp+var_10], 4AEh
0x14006399a  mov     qword ptr [rbp+var_20], rax
0x14006399e  lea     rcx, [rbp+var_20]
0x1400639a2  lea     rax, aCmicrodomupdat; "CMicrodomUpdateContext::CreateVirtualCo"...
0x1400639a9  mov     r8d, 0C0000017h
0x1400639af  mov     qword ptr [rbp+var_20+8], rax
0x1400639b3  lea     rax, aNewchildCommen; "NewChild->Comment.Allocate()"
0x1400639ba  mov     [rbp+var_8], rax
0x1400639be  call    RtlReportErrorOrigination
0x1400639c3  mov     rcx, rbx; this
0x1400639c6  call    ??1CChildNode@@QEAA@XZ; CChildNode::~CChildNode(void)
0x1400639cb  call    cs:__imp_GetProcessHeap
0x1400639d2  nop     dword ptr [rax+rax+00h]
0x1400639d7  mov     r8, rbx; lpMem
0x1400639da  xor     edx, edx; dwFlags
0x1400639dc  mov     rcx, rax; hHeap
0x1400639df  call    cs:__imp_HeapFree
0x1400639e6  nop     dword ptr [rax+rax+00h]
0x1400639eb  jmp     loc_1400638F3
0x1400639f0  mov     [rax+68h], rdi
0x1400639f4  lea     rcx, [rdi+8]
0x1400639f8  mov     [rax+70h], r14
0x1400639fc  mov     [rbx+38h], rax
0x140063a00  mov     [rsi], rbx
0x140063a03  mov     rax, [rcx+8]
0x140063a07  mov     [rbx+8], rax
0x140063a0b  mov     [rbx], rcx
0x140063a0e  mov     rax, [rcx+8]
0x140063a12  mov     [rax], rbx
0x140063a15  mov     [rcx+8], rbx
0x140063a19  mov     [rbx+10h], rcx
0x140063a1d  inc     qword ptr [rcx+18h]
0x140063a21  xor     eax, eax
0x140063a23  mov     rbx, [rsp+40h+arg_10]
0x140063a28  mov     rsi, [rsp+40h+arg_18]
0x140063a2d  add     rsp, 40h
0x140063a31  pop     r14
0x140063a33  pop     rdi
0x140063a34  pop     rbp
0x140063a35  retn
```

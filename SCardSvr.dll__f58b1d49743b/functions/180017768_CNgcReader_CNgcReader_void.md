# CNgcReader::~CNgcReader(void)

- ea: `0x180017768`
- end: `0x1800178cc`
- name: `??1CNgcReader@@UEAA@XZ`
- size: `356`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002bc10`

## callees

- `0x180010670`
- `0x1800151f8`
- `0x180017768`
- `0x1800179b0`
- `0x180017b28`
- `0x180023168`
- `0x18002ba38`
- `0x18002bea0`
- `0x18002e770`
- `0x1800326d0`

## string_xrefs

- `0x180017794`: `CNgcReader::~CNgcReader`

## pseudocode

```c
void __fastcall CNgcReader::~CNgcReader(CNgcReader *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  int v6; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-38h] BYREF
  char v9[24]; // [rsp+40h] [rbp-28h] BYREF

  *(_QWORD *)this = &CNgcReader::`vftable';
  v6 = 0;
  strcpy(v9, "CNgcReader::~CNgcReader");
  v8[0] = v9;
  v8[1] = &v6;
  lambda_7bd2e6b7bf0a047155b12de37d32be45_::operator()(v8);
  v6 = 1;
  v7 = v8;
  if ( !(unsigned int)CReader::InitFailed(this) )
  {
    CReader::TakeoverReader(this);
    CNgcReader::Close(this);
  }
  WppTraceUnwinder__lambda_7bd2e6b7bf0a047155b12de37d32be45____::_WppTraceUnwinder__lambda_7bd2e6b7bf0a047155b12de37d32be45____(&v7);
  *((_QWORD *)this + 109) = &Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
  *((_QWORD *)this + 106) = &CBuffer::`vftable';
  v2 = (void *)*((_QWORD *)this + 107);
  if ( v2 )
    operator delete[](v2);
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 103) = &CBuffer::`vftable';
  v3 = (void *)*((_QWORD *)this + 104);
  if ( v3 )
    operator delete[](v3);
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 100) = &CBuffer::`vftable';
  v4 = (void *)*((_QWORD *)this + 101);
  if ( v4 )
    operator delete[](v4);
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 97) = &CBuffer::`vftable';
  v5 = (void *)*((_QWORD *)this + 98);
  if ( v5 )
    operator delete[](v5);
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  CReader::~CReader(this);
}

```

## disassembly

```asm
0x180017768  push    rbp
0x18001776a  push    rbx
0x18001776b  push    rsi
0x18001776c  push    rdi
0x18001776d  mov     rbp, rsp
0x180017770  sub     rsp, 68h
0x180017774  mov     rax, cs:__security_cookie
0x18001777b  xor     rax, rsp
0x18001777e  mov     [rbp+var_10], rax
0x180017782  mov     rbx, rcx
0x180017785  lea     rax, ??_7CNgcReader@@6B@; const CNgcReader::`vftable'
0x18001778c  mov     [rcx], rax
0x18001778f  xor     edi, edi
0x180017791  mov     [rbp+var_48], edi
0x180017794  movups  xmm0, xmmword ptr cs:aCngcreaderCngc_0; "CNgcReader::~CNgcReader"
0x18001779b  movups  xmmword ptr [rbp+var_28], xmm0
0x18001779f  movsd   xmm1, qword ptr cs:aCngcreaderCngc_0+10h; "cReader"
0x1800177a7  movsd   qword ptr [rbp+var_28+10h], xmm1
0x1800177ac  lea     rax, [rbp+var_28]
0x1800177b0  mov     [rbp+var_38], rax
0x1800177b4  lea     rax, [rbp+var_48]
0x1800177b8  mov     [rbp+var_30], rax
0x1800177bc  lea     rcx, [rbp+var_38]
0x1800177c0  call    _lambda_7bd2e6b7bf0a047155b12de37d32be45___operator__
0x1800177c5  mov     [rbp+var_48], 1
0x1800177cc  lea     rax, [rbp+var_38]
0x1800177d0  mov     [rbp+var_40], rax
0x1800177d4  mov     rcx, rbx; this
0x1800177d7  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x1800177dc  test    eax, eax
0x1800177de  jnz     short loc_1800177F0
0x1800177e0  mov     rcx, rbx; this
0x1800177e3  call    ?TakeoverReader@CReader@@IEAAXXZ; CReader::TakeoverReader(void)
0x1800177e8  mov     rcx, rbx; this
0x1800177eb  call    ?Close@CNgcReader@@UEAAXXZ; CNgcReader::Close(void)
0x1800177f0  lea     rcx, [rbp+var_40]
0x1800177f4  call    WppTraceUnwinder__lambda_7bd2e6b7bf0a047155b12de37d32be45_______WppTraceUnwinder__lambda_7bd2e6b7bf0a047155b12de37d32be45____
0x1800177f9  lea     rcx, [rbx+368h]
0x180017800  lea     rax, ??_7?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable'
0x180017807  mov     [rcx], rax
0x18001780a  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x18001780f  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180017816  mov     [rbx+350h], rsi
0x18001781d  mov     rcx, [rbx+358h]; Block
0x180017824  test    rcx, rcx
0x180017827  jz      short loc_18001782E
0x180017829  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001782e  mov     [rbx+358h], rdi
0x180017835  mov     [rbx+360h], rdi
0x18001783c  mov     [rbx+338h], rsi
0x180017843  mov     rcx, [rbx+340h]; Block
0x18001784a  test    rcx, rcx
0x18001784d  jz      short loc_180017854
0x18001784f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180017854  mov     [rbx+340h], rdi
0x18001785b  mov     [rbx+348h], rdi
0x180017862  mov     [rbx+320h], rsi
0x180017869  mov     rcx, [rbx+328h]; Block
0x180017870  test    rcx, rcx
0x180017873  jz      short loc_18001787A
0x180017875  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001787a  mov     [rbx+328h], rdi
0x180017881  mov     [rbx+330h], rdi
0x180017888  mov     [rbx+308h], rsi
0x18001788f  mov     rcx, [rbx+310h]; Block
0x180017896  test    rcx, rcx
0x180017899  jz      short loc_1800178A0
0x18001789b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800178a0  mov     [rbx+310h], rdi
0x1800178a7  mov     [rbx+318h], rdi
0x1800178ae  mov     rcx, rbx; this
0x1800178b1  call    ??1CReader@@UEAA@XZ; CReader::~CReader(void)
0x1800178b6  nop
0x1800178b7  mov     rcx, [rbp+var_10]
0x1800178bb  xor     rcx, rsp; StackCookie
0x1800178be  call    __security_check_cookie
0x1800178c3  add     rsp, 68h
0x1800178c7  pop     rdi
0x1800178c8  pop     rsi
0x1800178c9  pop     rbx
0x1800178ca  pop     rbp
0x1800178cb  retn
```

# CNgcReader::CNgcReader(ushort const *)

- ea: `0x18002b43c`
- end: `0x18002b591`
- name: `??0CNgcReader@@QEAA@PEBG@Z`
- size: `341`
- prototype: `CNgcReader *__fastcall(CNgcReader *this, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002bc50`

## callees

- `0x180010670`
- `0x1800136a0`
- `0x18002b43c`
- `0x18002b638`
- `0x18002b924`
- `0x18002bde0`
- `0x18002d394`
- `0x1800326d0`

## string_xrefs

- `0x18002b4ed`: `CNgcReader::CNgcReader`

## pseudocode

```c
CNgcReader *__fastcall CNgcReader::CNgcReader(CNgcReader *this, const unsigned __int8 *a2)
{
  __int64 v4; // r8
  int v6; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v8[3]; // [rsp+30h] [rbp-40h] BYREF
  char v9[24]; // [rsp+48h] [rbp-28h] BYREF

  v8[2] = this;
  CReader::CReader(this);
  *(_QWORD *)this = &CNgcReader::`vftable';
  *((_QWORD *)this + 97) = &CBuffer::`vftable';
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = &CBuffer::`vftable';
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = &CBuffer::`vftable';
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 106) = &CBuffer::`vftable';
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 109) = &Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable';
  *((_QWORD *)this + 110) = 0;
  v6 = 0;
  strcpy(v9, "CNgcReader::CNgcReader");
  v8[0] = v9;
  v8[1] = &v6;
  lambda_44d43df88f935ab601723007ed933ef8_::operator()(v8);
  v6 = 1;
  v7 = v8;
  if ( !(unsigned int)CReader::InitFailed(this) )
  {
    CNgcReader::Clean(this);
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a2[2 * v4] );
    CBuffer::Set((CNgcReader *)((char *)this + 776), a2, 2 * v4 + 2);
  }
  WppTraceUnwinder__lambda_44d43df88f935ab601723007ed933ef8____::_WppTraceUnwinder__lambda_44d43df88f935ab601723007ed933ef8____(&v7);
  return this;
}

```

## disassembly

```asm
0x18002b43c  mov     [rsp-18h+arg_10], rbx
0x18002b441  mov     [rsp-18h+arg_18], rsi
0x18002b446  push    rbp
0x18002b447  push    rdi
0x18002b448  push    r14
0x18002b44a  mov     rbp, rsp
0x18002b44d  sub     rsp, 70h
0x18002b451  mov     rax, cs:__security_cookie
0x18002b458  xor     rax, rsp
0x18002b45b  mov     [rbp+var_10], rax
0x18002b45f  mov     rdi, rdx
0x18002b462  mov     rbx, rcx
0x18002b465  mov     [rbp+var_30], rcx
0x18002b469  call    ??0CReader@@QEAA@XZ; CReader::CReader(void)
0x18002b46e  nop
0x18002b46f  lea     rax, ??_7CNgcReader@@6B@; const CNgcReader::`vftable'
0x18002b476  mov     [rbx], rax
0x18002b479  lea     rsi, [rbx+308h]
0x18002b480  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002b487  mov     [rsi], rax
0x18002b48a  xor     r14d, r14d
0x18002b48d  mov     [rsi+8], r14
0x18002b491  mov     [rsi+10h], r14
0x18002b495  mov     [rbx+320h], rax
0x18002b49c  mov     [rbx+328h], r14
0x18002b4a3  mov     [rbx+330h], r14
0x18002b4aa  mov     [rbx+338h], rax
0x18002b4b1  mov     [rbx+340h], r14
0x18002b4b8  mov     [rbx+348h], r14
0x18002b4bf  mov     [rbx+350h], rax
0x18002b4c6  mov     [rbx+358h], r14
0x18002b4cd  mov     [rbx+360h], r14
0x18002b4d4  lea     rax, ??_7?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::`vftable'
0x18002b4db  mov     [rbx+368h], rax
0x18002b4e2  mov     [rbx+370h], r14
0x18002b4e9  mov     [rbp+var_50], r14d
0x18002b4ed  movups  xmm0, xmmword ptr cs:aCngcreaderCngc; "CNgcReader::CNgcReader"
0x18002b4f4  movups  xmmword ptr [rbp+var_28], xmm0
0x18002b4f8  movsd   xmm1, qword ptr cs:aCngcreaderCngc+0Fh; "cReader"
0x18002b500  movsd   qword ptr [rbp+var_28+0Fh], xmm1
0x18002b505  lea     rax, [rbp+var_28]
0x18002b509  mov     [rbp+var_40], rax
0x18002b50d  lea     rax, [rbp+var_50]
0x18002b511  mov     [rbp+var_38], rax
0x18002b515  lea     rcx, [rbp+var_40]
0x18002b519  call    _lambda_44d43df88f935ab601723007ed933ef8___operator__
0x18002b51e  mov     [rbp+var_50], 1
0x18002b525  lea     rax, [rbp+var_40]
0x18002b529  mov     [rbp+var_48], rax
0x18002b52d  mov     rcx, rbx; this
0x18002b530  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18002b535  test    eax, eax
0x18002b537  jnz     short loc_18002B563
0x18002b539  mov     rcx, rbx; this
0x18002b53c  call    ?Clean@CNgcReader@@IEAAXXZ; CNgcReader::Clean(void)
0x18002b541  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b545  inc     r8
0x18002b548  cmp     [rdi+r8*2], r14w
0x18002b54d  jnz     short loc_18002B545
0x18002b54f  lea     r8d, ds:2[r8*2]; unsigned int
0x18002b557  mov     rdx, rdi; unsigned __int8 *
0x18002b55a  mov     rcx, rsi; this
0x18002b55d  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18002b562  nop
0x18002b563  lea     rcx, [rbp+var_48]
0x18002b567  call    WppTraceUnwinder__lambda_44d43df88f935ab601723007ed933ef8_______WppTraceUnwinder__lambda_44d43df88f935ab601723007ed933ef8____
0x18002b56c  nop
0x18002b56d  mov     rax, rbx
0x18002b570  mov     rcx, [rbp+var_10]
0x18002b574  xor     rcx, rsp; StackCookie
0x18002b577  call    __security_check_cookie
0x18002b57c  lea     r11, [rsp+70h+var_s0]
0x18002b581  mov     rbx, [r11+30h]
0x18002b585  mov     rsi, [r11+38h]
0x18002b589  mov     rsp, r11
0x18002b58c  pop     r14
0x18002b58e  pop     rdi
0x18002b58f  pop     rbp
0x18002b590  retn
```

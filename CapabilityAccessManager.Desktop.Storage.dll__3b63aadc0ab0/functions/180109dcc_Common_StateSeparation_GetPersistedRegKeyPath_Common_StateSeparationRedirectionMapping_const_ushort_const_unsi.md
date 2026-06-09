# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)

- ea: `0x180109dcc`
- end: `0x180109fa5`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z`
- size: `473`
- prototype: `__int64 __fastcall(Common **, const unsigned __int16 **, __int64, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180103964`
- `0x180106144`
- `0x180109fac`

## callees

- `0x180003430`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1801099b0`
- `0x180109dcc`
- `0x18010a834`

## string_xrefs

- `0x180109e11`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109ea9`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109f4b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109e91`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        Common **a1,
        const unsigned __int16 **a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  int PersistedRegKeyPath; // eax
  unsigned int v7; // edi
  unsigned __int16 *v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r8
  unsigned __int16 *v11; // rax
  void *v13; // rcx
  __int64 v14; // rdi
  const unsigned __int16 *v15; // rdx
  int appended; // eax
  unsigned int v17; // ebx
  void *v18[2]; // [rsp+20h] [rbp-30h] BYREF
  int v19; // [rsp+30h] [rbp-20h]
  _QWORD v20[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned __int16 *v22; // [rsp+90h] [rbp+40h] BYREF

  v22 = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, &v22);
  v7 = PersistedRegKeyPath;
  v8 = v22;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      (int)v18[0]);
LABEL_10:
    operator delete(v8);
    return v7;
  }
  *(_OWORD *)v18 = 0;
  v19 = 0;
  LODWORD(v9) = 0;
  if ( v22 )
  {
    v10 = 1073741822;
    v11 = v22;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    v7 = v10 == 0 ? 0x80070057 : 0;
    v9 = (1073741822 - v10) & -(__int64)(v10 != 0);
    if ( !v10 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16C,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v7);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)v7,
        (int)v18[0]);
      if ( v18[1] )
        operator delete(v18[1]);
      goto LABEL_10;
    }
  }
  v13 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v13 )
    operator delete(v13);
  v18[1] = v8;
  LODWORD(v18[0]) = v9;
  v19 = v9 + 1;
  v22 = 0;
  v14 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      if ( v14 || (v15 = *a2) == 0 )
      {
        v8 = (unsigned __int16 *)v18[1];
        goto LABEL_21;
      }
      v20[1] = v18;
      v20[0] = &Common::StringBufferBuilder::`vftable';
      v20[2] = v18;
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBufferBuilder *)v20, v15);
      v17 = appended;
      if ( appended < 0 )
        break;
      v14 = 1;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)appended,
      (int)v18[0]);
    if ( v18[1] )
      operator delete(v18[1]);
  }
  else
  {
LABEL_21:
    v18[1] = 0;
    LODWORD(v18[0]) = 0;
    v19 = 0;
    *a4 = v8;
    v17 = 0;
  }
  operator delete(0);
  return v17;
}

```

## disassembly

```asm
0x180109dcc  mov     [rsp-28h+arg_0], rbx
0x180109dd1  mov     [rsp-28h+arg_8], rsi
0x180109dd6  mov     [rsp-28h+arg_10], r8
0x180109ddb  push    rbp
0x180109ddc  push    rdi
0x180109ddd  push    r12
0x180109ddf  push    r14
0x180109de1  push    r15
0x180109de3  mov     rbp, rsp
0x180109de6  sub     rsp, 50h
0x180109dea  mov     r15, r9
0x180109ded  mov     r14, rdx
0x180109df0  xor     r12d, r12d
0x180109df3  mov     [rbp+arg_10], r12
0x180109df7  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x180109dfb  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x180109e00  mov     edi, eax
0x180109e02  mov     rbx, [rbp+arg_10]
0x180109e06  test    eax, eax
0x180109e08  jns     short loc_180109E27
0x180109e0a  mov     rcx, [rbp+28h]; this
0x180109e0e  mov     r9d, eax; char *
0x180109e11  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109e18  mov     edx, 18Ch; void *
0x180109e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e22  jmp     loc_180109ECA
0x180109e27  xorps   xmm0, xmm0
0x180109e2a  movups  xmmword ptr [rbp+var_30], xmm0
0x180109e2e  mov     [rbp+var_20], r12d
0x180109e32  mov     esi, r12d
0x180109e35  test    rbx, rbx
0x180109e38  jz      loc_180109ED9
0x180109e3e  mov     r9d, 3FFFFFFEh
0x180109e44  mov     r8d, r9d
0x180109e47  mov     rax, rbx
0x180109e4a  cmp     [rax], r12w
0x180109e4e  jz      short loc_180109E5A
0x180109e50  add     rax, 2
0x180109e54  sub     r8, 1
0x180109e58  jnz     short loc_180109E4A
0x180109e5a  mov     rax, r8
0x180109e5d  neg     rax
0x180109e60  sbb     edi, edi
0x180109e62  not     edi
0x180109e64  and     edi, 80070057h
0x180109e6a  mov     rdx, r8
0x180109e6d  mov     rax, r8
0x180109e70  sub     r9, r8
0x180109e73  neg     rax
0x180109e76  sbb     rcx, rcx
0x180109e79  and     rcx, r9
0x180109e7c  neg     rdx
0x180109e7f  sbb     rsi, rsi
0x180109e82  and     rsi, rcx
0x180109e85  mov     rcx, [rbp+28h]; this
0x180109e89  test    r8, r8
0x180109e8c  jnz     short loc_180109ED9
0x180109e8e  mov     r9d, edi; char *
0x180109e91  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\common\\widest"...
0x180109e98  mov     edx, 16Ch; void *
0x180109e9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180109ea2  mov     rcx, [rbp+28h]; this
0x180109ea6  mov     r9d, edi; char *
0x180109ea9  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109eb0  mov     edx, 18Eh; void *
0x180109eb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109eba  nop
0x180109ebb  mov     rcx, [rbp+var_30+8]; void *
0x180109ebf  test    rcx, rcx
0x180109ec2  jz      short loc_180109ECA
0x180109ec4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109ec9  nop
0x180109eca  mov     rcx, rbx; void *
0x180109ecd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109ed2  mov     eax, edi
0x180109ed4  jmp     loc_180109F8C
0x180109ed9  psrldq  xmm0, 8
0x180109ede  movq    rcx, xmm0; void *
0x180109ee3  test    rcx, rcx
0x180109ee6  jz      short loc_180109EED
0x180109ee8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109eed  mov     [rbp+var_30+8], rbx
0x180109ef1  mov     dword ptr [rbp+var_30], esi
0x180109ef4  lea     eax, [rsi+1]
0x180109ef7  mov     [rbp+var_20], eax
0x180109efa  mov     [rbp+arg_10], r12
0x180109efe  mov     rdi, r12
0x180109f01  test    r14, r14
0x180109f04  jz      short loc_180109F71
0x180109f06  cmp     rdi, 1
0x180109f0a  jnb     short loc_180109F6D
0x180109f0c  mov     rdx, [r14+rdi*8]; unsigned __int16 *
0x180109f10  test    rdx, rdx
0x180109f13  jz      short loc_180109F6D
0x180109f15  lea     rax, [rbp+var_30]
0x180109f19  mov     [rbp+var_10], rax
0x180109f1d  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180109f24  mov     [rbp+var_18], rax
0x180109f28  lea     rax, [rbp+var_30]
0x180109f2c  mov     [rbp+var_8], rax
0x180109f30  lea     rcx, [rbp+var_18]; struct Common::StringBufferBuilder *
0x180109f34  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBufferBuilder *,ushort const *)
0x180109f39  mov     ebx, eax
0x180109f3b  test    eax, eax
0x180109f3d  js      short loc_180109F44
0x180109f3f  inc     rdi
0x180109f42  jmp     short loc_180109F06
0x180109f44  mov     rcx, [rbp+28h]; this
0x180109f48  mov     r9d, eax; char *
0x180109f4b  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109f52  mov     edx, 193h; void *
0x180109f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109f5c  nop
0x180109f5d  mov     rcx, [rbp+var_30+8]; void *
0x180109f61  test    rcx, rcx
0x180109f64  jz      short loc_180109F83
0x180109f66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109f6b  jmp     short loc_180109F83
0x180109f6d  mov     rbx, [rbp+var_30+8]
0x180109f71  mov     [rbp+var_30+8], r12
0x180109f75  mov     dword ptr [rbp+var_30], r12d
0x180109f79  mov     [rbp+var_20], r12d
0x180109f7d  mov     [r15], rbx
0x180109f80  mov     ebx, r12d
0x180109f83  xor     ecx, ecx; void *
0x180109f85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109f8a  mov     eax, ebx
0x180109f8c  lea     r11, [rsp+50h+var_s0]
0x180109f91  mov     rbx, [r11+30h]
0x180109f95  mov     rsi, [r11+38h]
0x180109f99  mov     rsp, r11
0x180109f9c  pop     r15
0x180109f9e  pop     r14
0x180109fa0  pop     r12
0x180109fa2  pop     rdi
0x180109fa3  pop     rbp
0x180109fa4  retn
```

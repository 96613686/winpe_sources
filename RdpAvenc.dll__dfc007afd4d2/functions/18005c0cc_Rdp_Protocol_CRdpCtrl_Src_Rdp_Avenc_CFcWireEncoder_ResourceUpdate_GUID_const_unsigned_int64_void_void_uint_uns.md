# Rdp::Protocol::CRdpCtrl_Src<Rdp::Avenc::CFcWireEncoder>::ResourceUpdate(_GUID const &,unsigned __int64,void *,void *,uint,unsigned __int64,uint,tagRECT const *,unsigned __int64,uint,uchar const *)

- ea: `0x18005c0cc`
- end: `0x18005c348`
- name: `?ResourceUpdate@?$CRdpCtrl_Src@VCFcWireEncoder@Avenc@Rdp@@@Protocol@Rdp@@QEAAXAEBU_GUID@@_KPEAX2I1IPEBUtagRECT@@1IPEBE@Z`
- size: `636`
- prototype: `bool __fastcall(__int64, __int128 *, __int64, __int64, __int64, int, const char *, __int64, __int64, __int64, int, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18005b5c4`

## callees

- `0x180006f8a`
- `0x180007018`
- `0x18001143c`
- `0x1800146bc`
- `0x18005c0cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005c2e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005c2ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005c2e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005c2ef`

## string_xrefs

- `0x18005c105`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x18005c13c`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x18005c1c3`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x18005c26a`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x18005c315`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`
- `0x18005c1b7`: `Unable to ensure RDPCTRL_SRC_RESOURCE_UPDATE`
- `0x18005c306`: `Failed to copy blob data into RDPCTRL_SRC_RESOURCE_UPDATE`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall Rdp::Protocol::CRdpCtrl_Src<Rdp::Avenc::CFcWireEncoder>::ResourceUpdate(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        const char *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int a11,
        _OWORD *a12)
{
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ecx
  __int128 v21; // xmm0
  __int64 v22; // rax
  _OWORD *v23; // rcx
  size_t v24; // rbx
  int v25; // ebx
  int *v26; // rax
  int v28; // [rsp+20h] [rbp-58h]
  int v29; // [rsp+20h] [rbp-58h]
  int v30; // [rsp+20h] [rbp-58h]
  const char *v31; // [rsp+30h] [rbp-48h]
  const char *v32; // [rsp+30h] [rbp-48h]
  const char *v33; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  LOBYTE(v28) = (_DWORD)a8 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1F2,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    (const char *)0x80070057LL,
    v28,
    (bool)"Invalid number of dirty rectangles",
    v31);
  v15 = (unsigned int)(16 * a8 + 100);
  LOBYTE(v29) = (unsigned int)v15 > 0x1000;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1F5,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    (const char *)0x800705B6LL,
    v29,
    (bool)"PDU size must at most be one page.",
    v32);
  v16 = 0;
  while ( 1 )
  {
    v19 = *(unsigned int *)(a1 + 60);
    if ( (unsigned int)v19 >= *(_DWORD *)(a1 + 56) )
      break;
    v17 = *(_QWORD *)(a1 + 32);
    v18 = *(_QWORD *)(a1 + 64);
    if ( *(_QWORD *)(v17 + 24 * v19 + 8) - v18 >= (unsigned __int64)(unsigned int)v15 )
    {
      v16 = v18 + *(_QWORD *)(v17 + 24 * v19 + 16);
      *(_QWORD *)(a1 + 64) = v18 + v15;
      break;
    }
    *(_QWORD *)(v17 + 24 * v19 + 8) = v18;
    ++*(_DWORD *)(a1 + 60);
    *(_QWORD *)(a1 + 64) = 0;
  }
  v30 = v16;
  wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
    retaddr,
    503,
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    2147942414LL);
  v20 = 0;
  *(_DWORD *)(v16 + 8) = 4;
  *(_DWORD *)v16 = v15;
  v21 = *a2;
  *(_QWORD *)(v16 + 44) = a5;
  *(_DWORD *)(v16 + 52) = a6;
  *(_QWORD *)(v16 + 56) = a7;
  *(_QWORD *)(v16 + 64) = a10;
  *(_QWORD *)(v16 + 36) = a4;
  *(_QWORD *)(v16 + 28) = a3;
  *(_DWORD *)(v16 + 72) = a8;
  *(_QWORD *)(v16 + 76) = 16;
  for ( *(_OWORD *)(v16 + 12) = v21; v20 < (unsigned int)a8; *(_OWORD *)(v16 + 16 * v22 + 84) = *(_OWORD *)(a9 + 16 * v22) )
    v22 = v20++;
  LOBYTE(v30) = a12 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x20D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
    (const char *)0x80004003LL,
    v30,
    (bool)"Expected valid BlobData pointer when BlobByteCount > 0",
    v33);
  v23 = (_OWORD *)(v16 + 16LL * (unsigned int)a8 + 84);
  *(_DWORD *)(v16 + 80) = 16 * a8 + 84;
  if ( !v23 )
    goto LABEL_17;
  v24 = (unsigned int)v15 - (16LL * (unsigned int)a8 + 84);
  if ( !a12 || v24 < 0x10 )
  {
    memset_0(v23, 0, v24);
    if ( a12 )
    {
      if ( v24 >= 0x10 )
      {
        v25 = 22;
        goto LABEL_19;
      }
      v26 = (int *)_o__errno();
      v25 = 34;
LABEL_18:
      *v26 = v25;
      invalid_parameter_noinfo();
      goto LABEL_19;
    }
LABEL_17:
    v26 = (int *)_o__errno();
    v25 = 22;
    goto LABEL_18;
  }
  v25 = 0;
  *v23 = *a12;
LABEL_19:
  LOBYTE(a5) = v25 != 0;
  return wil::details::in1diag3::Throw_HrIfMsg(
           retaddr,
           (void *)0x215,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
           (const char *)0x80004005LL,
           a5,
           (bool)"Failed to copy blob data into RDPCTRL_SRC_RESOURCE_UPDATE",
           a7,
           a8,
           a9,
           a10);
}

```

## disassembly

```asm
0x18005c0cc  mov     [rsp+arg_8], rdx
0x18005c0d1  push    rbx
0x18005c0d2  push    rbp
0x18005c0d3  push    rsi
0x18005c0d4  push    rdi
0x18005c0d5  push    r12
0x18005c0d7  push    r13
0x18005c0d9  push    r14
0x18005c0db  push    r15
0x18005c0dd  sub     rsp, 38h
0x18005c0e1  mov     ebp, dword ptr [rsp+78h+arg_38]
0x18005c0e8  lea     rdx, aInvalidNumberO; "Invalid number of dirty rectangles"
0x18005c0ef  mov     r15, [rsp+78h+arg_40]
0x18005c0f7  mov     r12, r9
0x18005c0fa  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x18005c0ff  mov     r13, r8
0x18005c102  mov     rdi, rcx
0x18005c105  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005c10c  mov     rcx, [rsp+78h]; this
0x18005c111  cmp     ebp, 1
0x18005c114  mov     r9d, 80070057h; char *
0x18005c11a  mov     edx, 1F2h; void *
0x18005c11f  setb    al
0x18005c122  mov     byte ptr [rsp+78h+var_58], al; int
0x18005c126  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005c12b  mov     rcx, [rsp+78h]; this
0x18005c130  lea     rdx, aPduSizeMustAtM; "PDU size must at most be one page."
0x18005c137  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x18005c13c  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005c143  mov     r14d, ebp
0x18005c146  mov     r9d, 800705B6h; char *
0x18005c14c  shl     r14d, 4
0x18005c150  mov     edx, 1F5h; void *
0x18005c155  add     r14d, 64h ; 'd'
0x18005c159  cmp     r14d, 1000h
0x18005c160  setnbe  al
0x18005c163  mov     byte ptr [rsp+78h+var_58], al; int
0x18005c167  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005c16c  xor     ebx, ebx
0x18005c16e  mov     esi, r14d
0x18005c171  jmp     short loc_18005C198
0x18005c173  mov     r8, [rdi+20h]
0x18005c177  lea     rdx, [rax+rax*2]
0x18005c17b  mov     rcx, [rdi+40h]
0x18005c17f  mov     rax, [r8+rdx*8+8]
0x18005c184  sub     rax, rcx
0x18005c187  cmp     rax, rsi
0x18005c18a  jnb     short loc_18005C1A2
0x18005c18c  mov     [r8+rdx*8+8], rcx
0x18005c191  inc     dword ptr [rdi+3Ch]
0x18005c194  mov     [rdi+40h], rbx
0x18005c198  mov     eax, [rdi+3Ch]
0x18005c19b  cmp     eax, [rdi+38h]
0x18005c19e  jb      short loc_18005C173
0x18005c1a0  jmp     short loc_18005C1B2
0x18005c1a2  mov     rbx, [r8+rdx*8+10h]
0x18005c1a7  lea     rax, [rcx+r14]
0x18005c1ab  add     rbx, rcx
0x18005c1ae  mov     [rdi+40h], rax
0x18005c1b2  mov     rcx, [rsp+78h]
0x18005c1b7  lea     rax, aUnableToEnsure_22; "Unable to ensure RDPCTRL_SRC_RESOURCE_U"...
0x18005c1be  mov     qword ptr [rsp+78h+var_50], rax
0x18005c1c3  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005c1ca  mov     r9d, 8007000Eh
0x18005c1d0  mov     qword ptr [rsp+78h+var_58], rbx
0x18005c1d5  mov     edx, 1F7h
0x18005c1da  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18005c1df  mov     rax, [rsp+78h+arg_8]
0x18005c1e7  xor     ecx, ecx
0x18005c1e9  mov     dword ptr [rbx+8], 4
0x18005c1f0  mov     [rbx], r14d
0x18005c1f3  movups  xmm0, xmmword ptr [rax]
0x18005c1f6  mov     rax, [rsp+78h+arg_20]
0x18005c1fe  mov     [rbx+2Ch], rax
0x18005c202  mov     eax, dword ptr [rsp+78h+arg_28]
0x18005c209  mov     [rbx+34h], eax
0x18005c20c  mov     rax, [rsp+78h+arg_30]
0x18005c214  mov     [rbx+38h], rax
0x18005c218  mov     rax, [rsp+78h+arg_48]
0x18005c220  mov     [rbx+40h], rax
0x18005c224  mov     [rbx+24h], r12
0x18005c228  mov     [rbx+1Ch], r13
0x18005c22c  mov     [rbx+48h], ebp
0x18005c22f  mov     qword ptr [rbx+4Ch], 10h
0x18005c237  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x18005c23c  test    ebp, ebp
0x18005c23e  jz      short loc_18005C256
0x18005c240  mov     eax, ecx
0x18005c242  inc     ecx
0x18005c244  add     rax, rax
0x18005c247  movups  xmm0, xmmword ptr [r15+rax*8]
0x18005c24c  movdqu  xmmword ptr [rbx+rax*8+54h], xmm0
0x18005c252  cmp     ecx, ebp
0x18005c254  jb      short loc_18005C240
0x18005c256  mov     rdi, [rsp+78h+arg_58]
0x18005c25e  lea     rdx, aExpectedValidB; "Expected valid BlobData pointer when Bl"...
0x18005c265  mov     rcx, [rsp+78h]; this
0x18005c26a  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005c271  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x18005c276  test    rdi, rdi
0x18005c279  mov     r9d, 80004003h; char *
0x18005c27f  mov     edx, 20Dh; void *
0x18005c284  setz    al
0x18005c287  mov     byte ptr [rsp+78h+var_58], al; int
0x18005c28b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005c290  mov     rcx, rbp
0x18005c293  shl     rcx, 4
0x18005c297  add     rcx, 54h ; 'T'
0x18005c29b  add     rcx, rbx; void *
0x18005c29e  mov     eax, ecx
0x18005c2a0  sub     eax, ebx
0x18005c2a2  mov     [rbx+50h], eax
0x18005c2a5  test    rcx, rcx
0x18005c2a8  jz      short loc_18005C2EF
0x18005c2aa  sub     rsi, rcx
0x18005c2ad  add     rbx, rsi
0x18005c2b0  test    rdi, rdi
0x18005c2b3  jz      short loc_18005C2C6
0x18005c2b5  cmp     rbx, 10h
0x18005c2b9  jb      short loc_18005C2C6
0x18005c2bb  movups  xmm0, xmmword ptr [rdi]
0x18005c2be  xor     ebx, ebx
0x18005c2c0  movdqu  xmmword ptr [rcx], xmm0
0x18005c2c4  jmp     short loc_18005C301
0x18005c2c6  mov     r8, rbx; Size
0x18005c2c9  xor     edx, edx; Val
0x18005c2cb  call    memset_0
0x18005c2d0  test    rdi, rdi
0x18005c2d3  jz      short loc_18005C2EF
0x18005c2d5  cmp     rbx, 10h
0x18005c2d9  jb      short loc_18005C2E2
0x18005c2db  mov     ebx, 16h
0x18005c2e0  jmp     short loc_18005C301
0x18005c2e2  call    cs:__imp__o__errno
0x18005c2e8  mov     ebx, 22h ; '"'
0x18005c2ed  jmp     short loc_18005C2FA
0x18005c2ef  call    cs:__imp__o__errno
0x18005c2f5  mov     ebx, 16h
0x18005c2fa  mov     [rax], ebx
0x18005c2fc  call    _invalid_parameter_noinfo
0x18005c301  mov     rcx, [rsp+78h]; this
0x18005c306  lea     rdx, aFailedToCopyBl_0; "Failed to copy blob data into RDPCTRL_S"...
0x18005c30d  mov     qword ptr [rsp+78h+arg_28], rdx; bool
0x18005c315  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005c31c  test    ebx, ebx
0x18005c31e  mov     r9d, 80004005h; char *
0x18005c324  mov     edx, 215h; void *
0x18005c329  setnz   al
0x18005c32c  mov     byte ptr [rsp+78h+arg_20], al; int
0x18005c333  add     rsp, 38h
0x18005c337  pop     r15
0x18005c339  pop     r14
0x18005c33b  pop     r13
0x18005c33d  pop     r12
0x18005c33f  pop     rdi
0x18005c340  pop     rsi
0x18005c341  pop     rbp
0x18005c342  pop     rbx
0x18005c343  jmp     ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
```

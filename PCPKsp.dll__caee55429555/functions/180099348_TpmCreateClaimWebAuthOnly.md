# TpmCreateClaimWebAuthOnly

- ea: `0x180099348`
- end: `0x180099485`
- name: `TpmCreateClaimWebAuthOnly`
- size: `317`
- prototype: `__int64 __fastcall(void *, void *, void *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180050bb0`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800764d0`
- `0x1800973d0`
- `0x180099348`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x1800993ab`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800993ab`

## string_xrefs

- `0x180099382`: `TpmCreateClaimWebAuthOnly`

## pseudocode

```c
__int64 __fastcall TpmCreateClaimWebAuthOnly(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int a9)
{
  int DeviceInfo; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  unsigned int v18; // [rsp+20h] [rbp-98h]
  int *v19[3]; // [rsp+50h] [rbp-68h] BYREF
  __int128 v20; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v19, L"TpmCreateClaimWebAuthOnly", 1);
  v20 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v20);
  v14 = DeviceInfo;
  if ( DeviceInfo >= 0 )
  {
    if ( DWORD1(v20) == 1 )
    {
      v14 = -2144795643;
      v15 = 1857;
    }
    else
    {
      if ( DWORD1(v20) == 2 )
      {
        DeviceInfo = TpmCreateClaimWebAuthOnly20(a1, a2, a3, a4, a5, a6, a7, a8, a9);
        v14 = DeviceInfo;
        if ( DeviceInfo >= 0 )
        {
          KspFunctionLogger::~KspFunctionLogger(v19);
          return 0;
        }
        v15 = 1868;
        goto LABEL_8;
      }
      v14 = -2144795619;
      v15 = 1871;
    }
    v16 = v14;
    goto LABEL_12;
  }
  v15 = 1852;
LABEL_8:
  v16 = (unsigned int)DeviceInfo;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation.cpp",
    (const char *)v16,
    v18);
  KspFunctionLogger::~KspFunctionLogger(v19);
  return v14;
}

```

## disassembly

```asm
0x180099348  push    rbx
0x18009934a  push    rbp
0x18009934b  push    rsi
0x18009934c  push    rdi
0x18009934d  push    r12
0x18009934f  push    r14
0x180099351  push    r15
0x180099353  sub     rsp, 80h
0x18009935a  mov     rax, cs:__security_cookie
0x180099361  xor     rax, rsp
0x180099364  mov     [rsp+0B8h+var_40], rax
0x180099369  mov     r15, [rsp+0B8h+arg_28]
0x180099371  mov     rbp, r8
0x180099374  mov     r12, [rsp+0B8h+arg_38]
0x18009937c  mov     rsi, rdx
0x18009937f  mov     rdi, rcx
0x180099382  lea     rdx, aTpmcreateclaim_2; "TpmCreateClaimWebAuthOnly"
0x180099389  mov     r8b, 1; bool
0x18009938c  lea     rcx, [rsp+0B8h+var_68]; this
0x180099391  mov     r14, r9
0x180099394  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180099399  xorps   xmm0, xmm0
0x18009939c  lea     rdx, [rsp+0B8h+var_50]
0x1800993a1  mov     ecx, 10h
0x1800993a6  movups  [rsp+0B8h+var_50], xmm0
0x1800993ab  call    cs:__imp_Tbsi_GetDeviceInfo
0x1800993b2  nop     dword ptr [rax+rax+00h]
0x1800993b7  mov     ebx, eax
0x1800993b9  test    eax, eax
0x1800993bb  jns     short loc_1800993C4
0x1800993bd  mov     edx, 73Ch
0x1800993c2  jmp     short loc_180099425
0x1800993c4  mov     eax, dword ptr [rsp+0B8h+var_50+4]
0x1800993c8  sub     eax, 1
0x1800993cb  jz      short loc_180099438
0x1800993cd  cmp     eax, 1
0x1800993d0  jz      short loc_1800993DE
0x1800993d2  mov     ebx, 8029041Dh
0x1800993d7  mov     edx, 74Fh
0x1800993dc  jmp     short loc_180099442
0x1800993de  mov     eax, [rsp+0B8h+arg_40]
0x1800993e5  mov     r9, r14; unsigned __int8 *
0x1800993e8  mov     [rsp+0B8h+var_78], eax; unsigned int
0x1800993ec  mov     r8, rbp; void *
0x1800993ef  mov     eax, [rsp+0B8h+arg_30]
0x1800993f6  mov     rdx, rsi; void *
0x1800993f9  mov     [rsp+0B8h+var_80], r12; unsigned int *
0x1800993fe  mov     rcx, rdi; void *
0x180099401  mov     [rsp+0B8h+var_88], eax; unsigned int
0x180099405  mov     eax, [rsp+0B8h+arg_20]
0x18009940c  mov     [rsp+0B8h+var_90], r15; unsigned __int8 *
0x180099411  mov     [rsp+0B8h+var_98], eax; unsigned int
0x180099415  call    ?TpmCreateClaimWebAuthOnly20@@YAJPEAX00PEAEK1IPEAIK@Z; TpmCreateClaimWebAuthOnly20(void *,void *,void *,uchar *,ulong,uchar *,uint,uint *,ulong)
0x18009941a  mov     ebx, eax
0x18009941c  test    eax, eax
0x18009941e  jns     short loc_18009942A
0x180099420  mov     edx, 74Ch
0x180099425  mov     r9d, eax
0x180099428  jmp     short loc_180099445
0x18009942a  lea     rcx, [rsp+0B8h+var_68]; this
0x18009942f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180099434  xor     eax, eax
0x180099436  jmp     short loc_180099465
0x180099438  mov     ebx, 80290405h
0x18009943d  mov     edx, 741h; void *
0x180099442  mov     r9d, ebx; char *
0x180099445  mov     rcx, [rsp+0B8h]; this
0x18009944d  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180099454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099459  lea     rcx, [rsp+0B8h+var_68]; this
0x18009945e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180099463  mov     eax, ebx
0x180099465  mov     rcx, [rsp+0B8h+var_40]
0x18009946a  xor     rcx, rsp; StackCookie
0x18009946d  call    __security_check_cookie
0x180099472  add     rsp, 80h
0x180099479  pop     r15
0x18009947b  pop     r14
0x18009947d  pop     r12
0x18009947f  pop     rdi
0x180099480  pop     rsi
0x180099481  pop     rbp
0x180099482  pop     rbx
0x180099483  retn
```

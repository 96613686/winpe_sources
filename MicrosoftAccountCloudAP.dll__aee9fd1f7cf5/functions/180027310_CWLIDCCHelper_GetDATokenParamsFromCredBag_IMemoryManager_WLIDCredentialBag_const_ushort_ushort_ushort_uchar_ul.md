# CWLIDCCHelper::GetDATokenParamsFromCredBag(IMemoryManager *,_WLIDCredentialBag const *,ushort * *,ushort * *,ushort * *,uchar * *,ulong *,ushort * *)

- ea: `0x180027310`
- end: `0x18002771c`
- name: `?GetDATokenParamsFromCredBag@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBU_WLIDCredentialBag@@PEAPEAG22PEAPEAEPEAK2@Z`
- size: `1036`
- prototype: `__int64 __fastcall(struct IMemoryManager *, const struct _WLIDCredentialBag *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ed44`

## callees

- `0x180008440`
- `0x18000baac`
- `0x180024360`
- `0x180026c8c`
- `0x180026f50`
- `0x180026f68`
- `0x180026fc0`
- `0x1800271ec`
- `0x180027310`

## string_xrefs

- `0x180027441`: `hr = CredSerializationHelper::GetDATokenParamIndices( pCredBag->credType, daTokenIndex, daExpiryTimeIndex, daCreationTimeIndex, sessionKeyIndex, flowTokenIndex, nullptr)`
- `0x1800273b0`: `CWLIDCCHelper::GetDATokenParamsFromCredBag`
- `0x180027456`: `CWLIDCCHelper::GetDATokenParamsFromCredBag`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWLIDCCHelper::GetDATokenParamsFromCredBag(
        struct IMemoryManager *a1,
        const struct _WLIDCredentialBag *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned __int16 **a8)
{
  unsigned __int8 *v12; // r12
  unsigned int v13; // r15d
  int DATokenParamIndices; // eax
  __int64 v15; // rdx
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // r14
  __int64 v25; // rdx
  int v26; // ebx
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rbx
  int v32; // eax
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rax
  unsigned int v37; // ebx
  char *v39; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v41; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v42; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  struct IMemoryManager *v46; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  struct IMemoryManager *v49; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 v51; // [rsp+88h] [rbp-78h]
  struct IMemoryManager *v52; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  struct IMemoryManager *v55; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v56; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-48h]
  struct IMemoryManager *v58; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v59; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h]
  struct IMemoryManager *v61; // [rsp+D8h] [rbp-28h]
  _QWORD v62[12]; // [rsp+E0h] [rbp-20h] BYREF
  int v63; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v64; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int16 **v65; // [rsp+160h] [rbp+60h]
  unsigned int v66; // [rsp+168h] [rbp+68h] BYREF

  v65 = a3;
  v63 = 0;
  v56 = 0;
  v58 = a1;
  v57 = 0;
  v53 = 0;
  v55 = a1;
  v54 = 0;
  v50 = 0;
  v52 = a1;
  v51 = 0;
  v59 = 0;
  v61 = a1;
  v60 = 0;
  v12 = 0;
  v47 = 0;
  v49 = a1;
  v48 = 0;
  v13 = 0;
  v42 = 0;
  v44 = 0;
  v46 = a1;
  v45 = 0;
  v64 = 0;
  v66 = 0;
  v40 = 0;
  v41 = 0;
  v43 = 0;
  v62[0] = "CWLIDCCHelper::GetDATokenParamsFromCredBag";
  v62[1] = &v63;
  v62[2] = 0;
  v62[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
    "CWLIDCCHelper::GetDATokenParamsFromCredBag",
    (const char *)0x164,
    0,
    (const unsigned __int16 *)v39);
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  DATokenParamIndices = CredSerializationHelper::GetDATokenParamIndices(
                          *(unsigned int *)a2,
                          &v64,
                          &v66,
                          &v40,
                          &v41,
                          &v43,
                          0);
  v63 = DATokenParamIndices;
  if ( DATokenParamIndices < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      "CWLIDCCHelper::GetDATokenParamsFromCredBag",
      0x17Bu,
      DATokenParamIndices,
      "hr = CredSerializationHelper::GetDATokenParamIndices( pCredBag->credType, daTokenIndex, daExpiryTimeIndex, daCreat"
      "ionTimeIndex, sessionKeyIndex, flowTokenIndex, nullptr)");
    goto LABEL_19;
  }
  v15 = *((_QWORD *)a2 + 1);
  v16 = (unsigned int)(2 * *(_DWORD *)(v15 + 24LL * v64 + 8));
  v17 = CWLIDCCHelper::DuplicateString(
          a1,
          *(const unsigned __int16 **)(v15 + 24LL * v64 + 16),
          2 * *(_WORD *)(v15 + 24LL * v64 + 8),
          &v56);
  v63 = v17;
  v57 = v16 + 2;
  if ( v17 >= 0 )
  {
    v18 = *((_QWORD *)a2 + 1);
    v19 = (unsigned int)(2 * *(_DWORD *)(v18 + 24LL * v66 + 8));
    v20 = CWLIDCCHelper::DuplicateString(
            a1,
            *(const unsigned __int16 **)(v18 + 24LL * v66 + 16),
            2 * *(_WORD *)(v18 + 24LL * v66 + 8),
            &v53);
    v63 = v20;
    v54 = v19 + 2;
    if ( v20 >= 0 )
    {
      v21 = *((_QWORD *)a2 + 1);
      v22 = (unsigned int)(2 * *(_DWORD *)(v21 + 24LL * v40 + 8));
      v23 = CWLIDCCHelper::DuplicateString(
              a1,
              *(const unsigned __int16 **)(v21 + 24LL * v40 + 16),
              2 * *(_WORD *)(v21 + 24LL * v40 + 8),
              &v50);
      v63 = v23;
      v51 = v22 + 2;
      if ( v23 >= 0 )
      {
        v24 = 3LL * v41;
        v25 = *((_QWORD *)a2 + 1);
        v26 = *(_DWORD *)(v25 + 24LL * v41 + 8);
        if ( v26 )
        {
          v27 = 2 * v26;
          v28 = CWLIDCCHelper::DuplicateString(a1, *(const unsigned __int16 **)(v25 + 24LL * v41 + 16), v27, &v59);
          v63 = v28;
          v60 = v27 + 2LL;
          if ( v28 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
              "CWLIDCCHelper::GetDATokenParamsFromCredBag",
              0x197u,
              v28,
              "hr");
            goto LABEL_19;
          }
          v29 = CWLIDCCHelper::Base64Decode(a1, v59, *(_DWORD *)(*((_QWORD *)a2 + 1) + 8 * v24 + 8), &v47, &v42);
          v63 = v29;
          v13 = v42;
          v48 = v42;
          if ( v29 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
              "CWLIDCCHelper::GetDATokenParamsFromCredBag",
              0x19Bu,
              v29,
              "hr");
            goto LABEL_19;
          }
          v12 = v47;
        }
        v30 = *((_QWORD *)a2 + 1);
        v31 = (unsigned int)(2 * *(_DWORD *)(v30 + 24LL * v43 + 8));
        v32 = CWLIDCCHelper::DuplicateString(
                a1,
                *(const unsigned __int16 **)(v30 + 24LL * v43 + 16),
                2 * *(_WORD *)(v30 + 24LL * v43 + 8),
                &v44);
        v63 = v32;
        v45 = v31 + 2;
        if ( v32 >= 0 )
        {
          v33 = v56;
          v56 = 0;
          v57 = 0;
          *v65 = v33;
          v34 = v53;
          v53 = 0;
          v54 = 0;
          *a4 = v34;
          v35 = v50;
          v50 = 0;
          v51 = 0;
          *a5 = v35;
          v47 = 0;
          v48 = 0;
          *a6 = v12;
          *a7 = v13;
          v36 = v44;
          v44 = 0;
          v45 = 0;
          *a8 = v36;
        }
        else
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
            "CWLIDCCHelper::GetDATokenParamsFromCredBag",
            0x1A2u,
            v32,
            "hr");
        }
      }
      else
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
          "CWLIDCCHelper::GetDATokenParamsFromCredBag",
          0x18Eu,
          v23,
          "hr");
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
        "CWLIDCCHelper::GetDATokenParamsFromCredBag",
        0x188u,
        v20,
        "hr");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      "CWLIDCCHelper::GetDATokenParamsFromCredBag",
      0x182u,
      v17,
      "hr");
  }
LABEL_19:
  v37 = v63;
  CTraceFuncW<long>::~CTraceFuncW<long>(v62);
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>::~Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(&v44);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v47);
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>::~Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(&v59);
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>::~Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(&v50);
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>::~Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(&v53);
  Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>::~Auto<unsigned short *,ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(&v56);
  return v37;
}

```

## disassembly

```asm
0x180027310  mov     [rsp-8+arg_10], r8
0x180027315  push    rbp
0x180027316  push    rbx
0x180027317  push    rsi
0x180027318  push    rdi
0x180027319  push    r12
0x18002731b  push    r13
0x18002731d  push    r14
0x18002731f  push    r15
0x180027321  lea     rbp, [rsp-8]
0x180027326  sub     rsp, 108h
0x18002732d  mov     r13, r9
0x180027330  mov     rbx, r8
0x180027333  mov     rsi, rdx
0x180027336  mov     rdi, rcx
0x180027339  xor     r14d, r14d
0x18002733c  mov     [rbp+40h+arg_0], r14d
0x180027340  mov     [rbp+40h+var_90], r14
0x180027344  mov     [rbp+40h+var_80], rcx
0x180027348  mov     [rbp+40h+var_88], r14
0x18002734c  mov     [rbp+40h+var_A8], r14
0x180027350  mov     [rbp+40h+var_98], rcx
0x180027354  mov     [rbp+40h+var_A0], r14
0x180027358  mov     [rbp+40h+var_C0], r14
0x18002735c  mov     [rbp+40h+var_B0], rcx
0x180027360  mov     [rbp+40h+var_B8], r14
0x180027364  mov     [rbp+40h+var_78], r14
0x180027368  mov     [rbp+40h+var_68], rcx
0x18002736c  mov     [rbp+40h+var_70], r14
0x180027370  mov     r12d, r14d
0x180027373  mov     [rsp+140h+var_D8], r14
0x180027378  mov     [rsp+140h+var_C8], rcx
0x18002737d  mov     [rsp+140h+var_D0], r14
0x180027382  mov     r15d, r14d
0x180027385  mov     [rsp+140h+var_F8], r14d
0x18002738a  mov     [rsp+140h+var_F0], r14
0x18002738f  mov     [rsp+140h+var_E0], rcx
0x180027394  mov     [rsp+140h+var_E8], r14
0x180027399  mov     [rbp+40h+arg_8], r14d
0x18002739d  mov     [rbp+40h+arg_18], r14d
0x1800273a1  mov     [rsp+140h+var_100], r14d
0x1800273a6  mov     [rsp+140h+var_FC], r14d
0x1800273ab  mov     [rsp+140h+var_F4], r14d
0x1800273b0  lea     rcx, aCwlidcchelperG; "CWLIDCCHelper::GetDATokenParamsFromCred"...
0x1800273b7  mov     [rbp+40h+var_60], rcx
0x1800273bb  lea     rax, [rbp+40h+arg_0]
0x1800273bf  mov     [rbp+40h+var_58], rax
0x1800273c3  mov     [rbp+40h+var_50], r14
0x1800273c7  mov     [rbp+40h+var_48], r14
0x1800273cb  xor     r9d, r9d; unsigned int
0x1800273ce  mov     r8d, 164h; char *
0x1800273d4  mov     rdx, rcx; char *
0x1800273d7  lea     rcx, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800273de  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800273e3  nop
0x1800273e4  mov     [rbx], r14
0x1800273e7  mov     [r13+0], r14
0x1800273eb  mov     rax, [rbp+40h+arg_20]
0x1800273ef  mov     [rax], r14
0x1800273f2  mov     rax, [rbp+40h+arg_28]
0x1800273f6  mov     [rax], r14
0x1800273f9  mov     rax, [rbp+40h+arg_30]
0x180027400  mov     [rax], r14d
0x180027403  mov     rax, [rbp+40h+arg_38]
0x18002740a  mov     [rax], r14
0x18002740d  mov     [rsp+140h+var_110], r14
0x180027412  lea     rax, [rsp+140h+var_F4]
0x180027417  mov     [rsp+140h+var_118], rax
0x18002741c  lea     rax, [rsp+140h+var_FC]
0x180027421  mov     [rsp+140h+var_120], rax
0x180027426  lea     r9, [rsp+140h+var_100]
0x18002742b  lea     r8, [rbp+40h+arg_18]
0x18002742f  lea     rdx, [rbp+40h+arg_8]
0x180027433  mov     ecx, [rsi]
0x180027435  call    ?GetDATokenParamIndices@CredSerializationHelper@@SAJW4_WLIDCredentialsType@@AEAK1111PEAK@Z; CredSerializationHelper::GetDATokenParamIndices(_WLIDCredentialsType,ulong &,ulong &,ulong &,ulong &,ulong &,ulong *)
0x18002743a  mov     [rbp+40h+arg_0], eax
0x18002743d  test    eax, eax
0x18002743f  jns     short loc_18002746E
0x180027441  lea     r8, aHrCredserializ_0; "hr = CredSerializationHelper::GetDAToke"...
0x180027448  mov     [rsp+140h+var_120], r8; char *
0x18002744d  mov     r8d, 17Bh; unsigned int
0x180027453  mov     r9d, eax; int
0x180027456  lea     rdx, aCwlidcchelperG; "CWLIDCCHelper::GetDATokenParamsFromCred"...
0x18002745d  lea     rcx, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180027464  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180027469  jmp     loc_1800276BC
0x18002746e  mov     eax, [rbp+40h+arg_8]
0x180027471  lea     rcx, [rax+rax*2]
0x180027475  mov     rdx, [rsi+8]
0x180027479  mov     eax, [rdx+rcx*8+8]
0x18002747d  add     eax, eax
0x18002747f  mov     ebx, eax
0x180027481  movzx   r8d, ax; unsigned __int16
0x180027485  lea     r9, [rbp+40h+var_90]; unsigned __int16 **
0x180027489  mov     rdx, [rdx+rcx*8+10h]; unsigned __int16 *
0x18002748e  mov     rcx, rdi; struct IMemoryManager *
0x180027491  call    ?DuplicateString@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGGPEAPEAG@Z; CWLIDCCHelper::DuplicateString(IMemoryManager *,ushort const *,ushort,ushort * *)
0x180027496  mov     [rbp+40h+arg_0], eax
0x180027499  add     rbx, 2
0x18002749d  mov     [rbp+40h+var_88], rbx
0x1800274a1  test    eax, eax
0x1800274a3  jns     short loc_1800274B9
0x1800274a5  lea     rcx, aHr; "hr"
0x1800274ac  mov     [rsp+140h+var_120], rcx
0x1800274b1  mov     r8d, 182h
0x1800274b7  jmp     short loc_180027453
0x1800274b9  mov     eax, [rbp+40h+arg_18]
0x1800274bc  lea     rcx, [rax+rax*2]
0x1800274c0  mov     rdx, [rsi+8]
0x1800274c4  mov     eax, [rdx+rcx*8+8]
0x1800274c8  add     eax, eax
0x1800274ca  mov     ebx, eax
0x1800274cc  movzx   r8d, ax; unsigned __int16
0x1800274d0  lea     r9, [rbp+40h+var_A8]; unsigned __int16 **
0x1800274d4  mov     rdx, [rdx+rcx*8+10h]; unsigned __int16 *
0x1800274d9  mov     rcx, rdi; struct IMemoryManager *
0x1800274dc  call    ?DuplicateString@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGGPEAPEAG@Z; CWLIDCCHelper::DuplicateString(IMemoryManager *,ushort const *,ushort,ushort * *)
0x1800274e1  mov     [rbp+40h+arg_0], eax
0x1800274e4  add     rbx, 2
0x1800274e8  mov     [rbp+40h+var_A0], rbx
0x1800274ec  test    eax, eax
0x1800274ee  jns     short loc_180027507
0x1800274f0  lea     rcx, aHr; "hr"
0x1800274f7  mov     [rsp+140h+var_120], rcx
0x1800274fc  mov     r8d, 188h
0x180027502  jmp     loc_180027453
0x180027507  mov     eax, [rsp+140h+var_100]
0x18002750b  lea     rcx, [rax+rax*2]
0x18002750f  mov     rdx, [rsi+8]
0x180027513  mov     eax, [rdx+rcx*8+8]
0x180027517  add     eax, eax
0x180027519  mov     ebx, eax
0x18002751b  movzx   r8d, ax; unsigned __int16
0x18002751f  lea     r9, [rbp+40h+var_C0]; unsigned __int16 **
0x180027523  mov     rdx, [rdx+rcx*8+10h]; unsigned __int16 *
0x180027528  mov     rcx, rdi; struct IMemoryManager *
0x18002752b  call    ?DuplicateString@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGGPEAPEAG@Z; CWLIDCCHelper::DuplicateString(IMemoryManager *,ushort const *,ushort,ushort * *)
0x180027530  mov     [rbp+40h+arg_0], eax
0x180027533  add     rbx, 2
0x180027537  mov     [rbp+40h+var_B8], rbx
0x18002753b  test    eax, eax
0x18002753d  jns     short loc_180027556
0x18002753f  lea     rcx, aHr; "hr"
0x180027546  mov     [rsp+140h+var_120], rcx
0x18002754b  mov     r8d, 18Eh
0x180027551  jmp     loc_180027453
0x180027556  mov     eax, [rsp+140h+var_FC]
0x18002755a  lea     r14, [rax+rax*2]
0x18002755e  mov     rdx, [rsi+8]
0x180027562  mov     ebx, [rdx+r14*8+8]
0x180027567  test    ebx, ebx
0x180027569  jz      loc_1800275FF
0x18002756f  add     ebx, ebx
0x180027571  movzx   r8d, bx; unsigned __int16
0x180027575  lea     r9, [rbp+40h+var_78]; unsigned __int16 **
0x180027579  mov     rdx, [rdx+r14*8+10h]; unsigned __int16 *
0x18002757e  mov     rcx, rdi; struct IMemoryManager *
0x180027581  call    ?DuplicateString@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGGPEAPEAG@Z; CWLIDCCHelper::DuplicateString(IMemoryManager *,ushort const *,ushort,ushort * *)
0x180027586  mov     [rbp+40h+arg_0], eax
0x180027589  mov     ecx, ebx
0x18002758b  add     rcx, 2
0x18002758f  mov     [rbp+40h+var_70], rcx
0x180027593  test    eax, eax
0x180027595  jns     short loc_1800275AE
0x180027597  lea     rcx, aHr; "hr"
0x18002759e  mov     [rsp+140h+var_120], rcx
0x1800275a3  mov     r8d, 197h
0x1800275a9  jmp     loc_180027453
0x1800275ae  mov     r8, [rsi+8]
0x1800275b2  lea     rax, [rsp+140h+var_F8]
0x1800275b7  mov     [rsp+140h+var_120], rax; unsigned int *
0x1800275bc  lea     r9, [rsp+140h+var_D8]; unsigned __int8 **
0x1800275c1  mov     r8d, [r8+r14*8+8]; unsigned int
0x1800275c6  mov     rdx, [rbp+40h+var_78]; unsigned __int16 *
0x1800275ca  mov     rcx, rdi; struct IMemoryManager *
0x1800275cd  call    ?Base64Decode@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGKPEAPEAEPEAK@Z; CWLIDCCHelper::Base64Decode(IMemoryManager *,ushort const *,ulong,uchar * *,ulong *)
0x1800275d2  mov     [rbp+40h+arg_0], eax
0x1800275d5  mov     r15d, [rsp+140h+var_F8]
0x1800275da  mov     [rsp+140h+var_D0], r15
0x1800275df  test    eax, eax
0x1800275e1  jns     short loc_1800275FA
0x1800275e3  lea     rcx, aHr; "hr"
0x1800275ea  mov     [rsp+140h+var_120], rcx
0x1800275ef  mov     r8d, 19Bh
0x1800275f5  jmp     loc_180027453
0x1800275fa  mov     r12, [rsp+140h+var_D8]
0x1800275ff  mov     eax, [rsp+140h+var_F4]
0x180027603  lea     rcx, [rax+rax*2]
0x180027607  mov     rdx, [rsi+8]
0x18002760b  mov     eax, [rdx+rcx*8+8]
0x18002760f  add     eax, eax
0x180027611  mov     ebx, eax
0x180027613  movzx   r8d, ax; unsigned __int16
0x180027617  lea     r9, [rsp+140h+var_F0]; unsigned __int16 **
0x18002761c  mov     rdx, [rdx+rcx*8+10h]; unsigned __int16 *
0x180027621  mov     rcx, rdi; struct IMemoryManager *
0x180027624  call    ?DuplicateString@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBGGPEAPEAG@Z; CWLIDCCHelper::DuplicateString(IMemoryManager *,ushort const *,ushort,ushort * *)
0x180027629  mov     [rbp+40h+arg_0], eax
0x18002762c  add     rbx, 2
0x180027630  mov     [rsp+140h+var_E8], rbx
0x180027635  xor     edx, edx
0x180027637  test    eax, eax
0x180027639  jns     short loc_180027652
0x18002763b  lea     rcx, aHr; "hr"
0x180027642  mov     [rsp+140h+var_120], rcx
0x180027647  mov     r8d, 1A2h
0x18002764d  jmp     loc_180027453
0x180027652  mov     rax, [rbp+40h+var_90]
0x180027656  mov     [rbp+40h+var_90], rdx
0x18002765a  mov     [rbp+40h+var_88], rdx
0x18002765e  mov     rcx, [rbp+40h+arg_10]
0x180027662  mov     [rcx], rax
0x180027665  mov     rax, [rbp+40h+var_A8]
0x180027669  mov     [rbp+40h+var_A8], rdx
0x18002766d  mov     [rbp+40h+var_A0], rdx
0x180027671  mov     [r13+0], rax
0x180027675  mov     rax, [rbp+40h+var_C0]
0x180027679  mov     [rbp+40h+var_C0], rdx
0x18002767d  mov     [rbp+40h+var_B8], rdx
0x180027681  mov     rcx, [rbp+40h+arg_20]
0x180027685  mov     [rcx], rax
0x180027688  mov     [rsp+140h+var_D8], rdx
0x18002768d  mov     [rsp+140h+var_D0], rdx
0x180027692  mov     rax, [rbp+40h+arg_28]
0x180027696  mov     [rax], r12
0x180027699  mov     rax, [rbp+40h+arg_30]
0x1800276a0  mov     [rax], r15d
0x1800276a3  mov     rax, [rsp+140h+var_F0]
0x1800276a8  mov     [rsp+140h+var_F0], rdx
0x1800276ad  mov     [rsp+140h+var_E8], rdx
0x1800276b2  mov     rcx, [rbp+40h+arg_38]
0x1800276b9  mov     [rcx], rax
0x1800276bc  mov     ebx, [rbp+40h+arg_0]
0x1800276bf  lea     rcx, [rbp+40h+var_60]
0x1800276c3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800276c8  nop
0x1800276c9  lea     rcx, [rsp+140h+var_F0]
0x1800276ce  call    ??1?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@QEAA@XZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>::~Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>(void)
0x1800276d3  nop
0x1800276d4  lea     rcx, [rsp+140h+var_D8]
0x1800276d9  call    ??1?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAA@XZ; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::~Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>(void)
0x1800276de  nop
0x1800276df  lea     rcx, [rbp+40h+var_78]
0x1800276e3  call    ??1?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@QEAA@XZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>::~Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>(void)
0x1800276e8  nop
0x1800276e9  lea     rcx, [rbp+40h+var_C0]
0x1800276ed  call    ??1?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@QEAA@XZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>::~Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>(void)
0x1800276f2  nop
0x1800276f3  lea     rcx, [rbp+40h+var_A8]
0x1800276f7  call    ??1?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@QEAA@XZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>::~Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>(void)
0x1800276fc  nop
0x1800276fd  lea     rcx, [rbp+40h+var_90]
0x180027701  call    ??1?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@QEAA@XZ; Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>::~Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager>(void)
0x180027706  mov     eax, ebx
0x180027708  add     rsp, 108h
0x18002770f  pop     r15
0x180027711  pop     r14
0x180027713  pop     r13
0x180027715  pop     r12
0x180027717  pop     rdi
0x180027718  pop     rsi
0x180027719  pop     rbx
0x18002771a  pop     rbp
0x18002771b  retn
```

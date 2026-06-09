# NativePreProcessor::NNResizeNV12ToBGRA

- ea: `0x180025514`
- end: `0x180025a32`
- name: `NativePreProcessor::NNResizeNV12ToBGRA`
- size: `1310`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int, int, signed int, DWORD dwHeight, IMFMediaBuffer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800261a4`

## callees

- `0x180006014`
- `0x1800220bc`
- `0x180022680`
- `0x180025514`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreate2DMediaBuffer` at `0x180025779`
- `MFPlat!MFCreate2DMediaBuffer` at `0x180025779`

## string_xrefs

- `0x180025573`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x1800255fa`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x180025653`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x18002568e`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x1800256eb`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x18002578c`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x180025811`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`
- `0x18002587a`: `avcore\mf\photography\components\facedetection\core\facedetectionmodelrunner.cpp`

## pseudocode

```c
__int64 __fastcall NativePreProcessor::NNResizeNV12ToBGRA(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        int a3,
        signed int a4,
        DWORD dwHeight,
        IMFMediaBuffer **a6)
{
  __int64 v7; // rdi
  __int64 (__fastcall **v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  IMFMediaBuffer **v13; // rsi
  IMFMediaBuffer *v14; // rcx
  signed int v15; // r12d
  HRESULT v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  unsigned __int64 v20; // rdx
  int v21; // r13d
  __int64 v22; // rbx
  signed int v23; // edi
  __int64 v24; // r14
  signed int v25; // esi
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // r11d
  IMFMediaBuffer *v29; // rcx
  int ppBuffer; // [rsp+20h] [rbp-59h]
  int ppBuffera; // [rsp+20h] [rbp-59h]
  int v33; // [rsp+40h] [rbp-39h]
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  __int64 v36; // [rsp+58h] [rbp-21h] BYREF
  __int64 v37; // [rsp+60h] [rbp-19h] BYREF
  IMFMediaBuffer *v38; // [rsp+68h] [rbp-11h] BYREF
  int v39[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v40; // [rsp+78h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  char v42; // [rsp+D8h] [rbp+5Fh] BYREF
  char v43; // [rsp+D9h] [rbp+60h]
  char v44; // [rsp+DAh] [rbp+61h]
  int v45; // [rsp+E0h] [rbp+67h] BYREF
  signed int v46; // [rsp+E8h] [rbp+6Fh] BYREF

  v7 = a3;
  v36 = 0;
  v35 = 0;
  v45 = a2;
  v38 = 0;
  v34 = 0;
  v9 = *a1;
  v37 = 0;
  v10 = (*v9)(a1, &GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec, &v37);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
      (const char *)(unsigned int)v10,
      ppBuffer);
    goto LABEL_56;
  }
  *(_QWORD *)v39 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v37 + 80LL))(v37, 1, &v36, &v45);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
      (const char *)(unsigned int)v12,
      (int)v39);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
    goto LABEL_56;
  }
  if ( !v36 )
  {
    v11 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
      (const char *)0x80004003LL,
      (int)v39);
    goto LABEL_15;
  }
  if ( (unsigned __int64)(v36 + (int)v7 * v45) <= *(_QWORD *)v39 )
  {
    v46 = a4;
    v13 = a6;
    if ( !a6 )
    {
      v11 = -2147467261;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
        (const char *)0x80004003LL,
        (int)v39);
LABEL_15:
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
      goto LABEL_56;
    }
    v40 = v36 + v45 * v7;
    *a6 = 0;
    v14 = v38;
    v38 = 0;
    if ( v14 )
      ((void (__fastcall *)(IMFMediaBuffer *))v14->lpVtbl->Release)(v14);
    v15 = dwHeight;
    v16 = MFCreate2DMediaBuffer(a4, dwHeight, MFVideoFormat_ARGB32.Data1, 0, &v38);
    v11 = v16;
    if ( v16 >= 0 )
    {
      v17 = v34;
      v34 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *, __int64 *))v38->lpVtbl->QueryInterface)(
              v38,
              &GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec,
              &v34);
      v11 = v18;
      if ( v18 >= 0 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, signed int *))(*(_QWORD *)v34 + 24LL))(v34, &v35, &v46);
        v11 = v19;
        if ( v19 >= 0 )
        {
          v33 = (a2 << 16) / a4 + 1;
          v20 = (unsigned int)((__int16)v7 >> 15);
          LODWORD(v20) = ((_DWORD)v7 << 16) % v15;
          v21 = ((_DWORD)v7 << 16) / v15;
          v22 = 0;
          v23 = 0;
          if ( v15 > 0 )
          {
            do
            {
              v20 = (unsigned __int64)(unsigned int)(v23 * (v21 + 1)) >> 16;
              v24 = v36 + v20 * v45;
              if ( (v23 & 1) == 0 )
                v22 = v40 + v45 * ((unsigned __int64)(unsigned int)(v23 * (v21 + 1)) >> 17);
              v25 = 0;
              if ( a4 > 0 )
              {
                do
                {
                  v26 = (unsigned __int64)(unsigned int)(v25 * v33) >> 16;
                  v42 = *(_BYTE *)(v24 + v26);
                  v27 = (unsigned int)v26 & 0xFFFFFFFE;
                  v43 = *(_BYTE *)(v27 + v22);
                  v44 = *(_BYTE *)(v22 + v27 + 1);
                  NativePreProcessor::ConvertYUVtoRGB(
                    &v42,
                    v35 + 4 * v25 + v23 * v46 + 2,
                    v35 + 4 * v25 + v23 * v46 + 1,
                    v35 + 4 * v25 + v23 * v46);
                  *(_BYTE *)(v28 + v23 * v46 + v35 + 3) = -1;
                  ++v25;
                }
                while ( v25 < a4 );
                v15 = dwHeight;
              }
              ++v23;
            }
            while ( v23 < v15 );
            v13 = a6;
          }
          v29 = v38;
          if ( v38 )
          {
            *v13 = v38;
            ((void (__fastcall *)(IMFMediaBuffer *, unsigned __int64))v29->lpVtbl->AddRef)(v29, v20);
          }
          else
          {
            *v13 = 0;
          }
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
          v11 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x70,
            (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
            (const char *)(unsigned int)v19,
            ppBuffera);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
          (const char *)(unsigned int)v18,
          ppBuffera);
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
        (const char *)(unsigned int)v16,
        ppBuffera);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
    }
  }
  else
  {
    v11 = -1072875855;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"avcore\\mf\\photography\\components\\facedetection\\core\\facedetectionmodelrunner.cpp",
      (const char *)0xC00D36B1LL,
      (int)v39);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 32LL))(v37);
  }
LABEL_56:
  wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v38);
  wil::com_ptr_t<IMFSample,wil::err_returncode_policy>::~com_ptr_t<IMFSample,wil::err_returncode_policy>(&v37);
  return v11;
}

```

## disassembly

```asm
0x180025514  push    rbp
0x180025516  push    rbx
0x180025517  push    rsi
0x180025518  push    rdi
0x180025519  push    r12
0x18002551b  push    r13
0x18002551d  push    r14
0x18002551f  push    r15
0x180025521  lea     rbp, [rsp-0Fh]
0x180025526  sub     rsp, 88h
0x18002552d  mov     r15d, r9d
0x180025530  movsxd  rdi, r8d
0x180025533  mov     r14d, edx
0x180025536  xor     r13d, r13d
0x180025539  mov     [rbp+47h+var_68], r13
0x18002553d  mov     [rbp+47h+var_70], r13
0x180025541  mov     [rbp+47h+arg_10], edx
0x180025544  mov     [rbp+47h+var_58], r13
0x180025548  mov     [rbp+47h+var_78], r13
0x18002554c  mov     rax, [rcx]
0x18002554f  mov     [rbp+47h+var_60], r13
0x180025553  lea     r8, [rbp+47h+var_60]
0x180025557  lea     rdx, _GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec
0x18002555e  mov     rax, [rax]
0x180025561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025566  mov     ebx, eax
0x180025568  test    eax, eax
0x18002556a  jns     short loc_1800255B6
0x18002556c  mov     rcx, [rbp+4Fh]; this
0x180025570  mov     r9d, eax; char *
0x180025573  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x18002557a  lea     edx, [r13+52h]; void *
0x18002557e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025583  nop
0x180025584  cmp     [rbp+47h+var_70], r13
0x180025588  jz      short loc_18002559A
0x18002558a  mov     rcx, [rbp+47h+var_78]
0x18002558e  mov     rax, [rcx]
0x180025591  mov     rax, [rax+20h]
0x180025595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002559a  cmp     [rbp+47h+var_68], r13
0x18002559e  jz      short loc_1800255B1
0x1800255a0  mov     rcx, [rbp+47h+var_60]
0x1800255a4  mov     rax, [rcx]
0x1800255a7  mov     rax, [rax+20h]
0x1800255ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255b0  nop
0x1800255b1  jmp     loc_180025A01
0x1800255b6  mov     qword ptr [rbp+47h+var_50], r13
0x1800255ba  mov     [rbp+47h+arg_0], r13d
0x1800255be  mov     rcx, [rbp+47h+var_60]
0x1800255c2  mov     rax, [rcx]
0x1800255c5  lea     rdx, [rbp+47h+arg_0]
0x1800255c9  mov     [rsp+0C0h+var_98], rdx
0x1800255ce  lea     rdx, [rbp+47h+var_50]
0x1800255d2  mov     [rsp+0C0h+ppBuffer], rdx; int
0x1800255d7  lea     r9, [rbp+47h+arg_10]
0x1800255db  lea     r8, [rbp+47h+var_68]
0x1800255df  mov     edx, 1
0x1800255e4  mov     rax, [rax+50h]
0x1800255e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255ed  mov     ebx, eax
0x1800255ef  test    eax, eax
0x1800255f1  jns     short loc_18002563E
0x1800255f3  mov     rcx, [rbp+4Fh]; this
0x1800255f7  mov     r9d, eax; char *
0x1800255fa  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180025601  mov     edx, 5Ch ; '\'; void *
0x180025606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002560b  nop
0x18002560c  cmp     [rbp+47h+var_70], r13
0x180025610  jz      short loc_180025622
0x180025612  mov     rcx, [rbp+47h+var_78]
0x180025616  mov     rax, [rcx]
0x180025619  mov     rax, [rax+20h]
0x18002561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025622  cmp     [rbp+47h+var_68], r13
0x180025626  jz      short loc_180025639
0x180025628  mov     rcx, [rbp+47h+var_60]
0x18002562c  mov     rax, [rcx]
0x18002562f  mov     rax, [rax+20h]
0x180025633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025638  nop
0x180025639  jmp     loc_180025A01
0x18002563e  mov     rdx, [rbp+47h+var_68]
0x180025642  test    rdx, rdx
0x180025645  jnz     short loc_18002566A
0x180025647  mov     rcx, [rbp+4Fh]; this
0x18002564b  mov     ebx, 80004003h
0x180025650  mov     r9d, ebx; char *
0x180025653  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x18002565a  mov     edx, 5Eh ; '^'; void *
0x18002565f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025664  nop
0x180025665  jmp     loc_1800256FB
0x18002566a  mov     eax, [rbp+47h+arg_10]
0x18002566d  imul    eax, edi
0x180025670  movsxd  rcx, eax
0x180025673  add     rcx, rdx
0x180025676  mov     eax, [rbp+47h+arg_0]
0x180025679  add     rax, qword ptr [rbp+47h+var_50]
0x18002567d  cmp     rcx, rax
0x180025680  jbe     short loc_1800256D2
0x180025682  mov     rcx, [rbp+4Fh]; this
0x180025686  mov     ebx, 0C00D36B1h
0x18002568b  mov     r9d, ebx; char *
0x18002568e  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180025695  mov     edx, 5Fh ; '_'; void *
0x18002569a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002569f  nop
0x1800256a0  cmp     [rbp+47h+var_70], r13
0x1800256a4  jz      short loc_1800256B6
0x1800256a6  mov     rcx, [rbp+47h+var_78]
0x1800256aa  mov     rax, [rcx]
0x1800256ad  mov     rax, [rax+20h]
0x1800256b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256b6  cmp     [rbp+47h+var_68], r13
0x1800256ba  jz      short loc_1800256CD
0x1800256bc  mov     rcx, [rbp+47h+var_60]
0x1800256c0  mov     rax, [rcx]
0x1800256c3  mov     rax, [rax+20h]
0x1800256c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256cc  nop
0x1800256cd  jmp     loc_180025A01
0x1800256d2  mov     [rbp+47h+arg_18], r15d
0x1800256d6  mov     rsi, [rbp+47h+arg_28]
0x1800256da  test    rsi, rsi
0x1800256dd  jnz     short loc_18002572D
0x1800256df  mov     rcx, [rbp+4Fh]; this
0x1800256e3  mov     ebx, 80004003h
0x1800256e8  mov     r9d, ebx; char *
0x1800256eb  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x1800256f2  lea     edx, [rsi+6Bh]; void *
0x1800256f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256fa  nop
0x1800256fb  cmp     [rbp+47h+var_70], r13
0x1800256ff  jz      short loc_180025711
0x180025701  mov     rcx, [rbp+47h+var_78]
0x180025705  mov     rax, [rcx]
0x180025708  mov     rax, [rax+20h]
0x18002570c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025711  cmp     [rbp+47h+var_68], r13
0x180025715  jz      short loc_180025728
0x180025717  mov     rcx, [rbp+47h+var_60]
0x18002571b  mov     rax, [rcx]
0x18002571e  mov     rax, [rax+20h]
0x180025722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025727  nop
0x180025728  jmp     loc_180025A01
0x18002572d  movsxd  rcx, [rbp+47h+arg_10]
0x180025731  mov     rax, rdi
0x180025734  imul    rax, rcx
0x180025738  add     rax, rdx
0x18002573b  mov     [rbp+47h+var_48], rax
0x18002573f  mov     [rsi], r13
0x180025742  mov     rcx, [rbp+47h+var_58]
0x180025746  mov     [rbp+47h+var_58], r13
0x18002574a  test    rcx, rcx
0x18002574d  jz      short loc_18002575C
0x18002574f  mov     rax, [rcx]
0x180025752  mov     rax, [rax+10h]
0x180025756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002575b  nop
0x18002575c  lea     rax, [rbp+47h+var_58]
0x180025760  mov     [rsp+0C0h+ppBuffer], rax; int
0x180025765  xor     r9d, r9d; fBottomUp
0x180025768  mov     r8d, cs:MFVideoFormat_ARGB32.Data1; dwFourCC
0x18002576f  mov     r12d, [rbp+47h+dwHeight]
0x180025773  mov     edx, r12d; dwHeight
0x180025776  mov     ecx, r15d; dwWidth
0x180025779  call    cs:__imp_MFCreate2DMediaBuffer
0x18002577f  mov     ebx, eax
0x180025781  test    eax, eax
0x180025783  jns     short loc_1800257D0
0x180025785  mov     rcx, [rbp+4Fh]; this
0x180025789  mov     r9d, eax; char *
0x18002578c  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180025793  mov     edx, 6Eh ; 'n'; void *
0x180025798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002579d  nop
0x18002579e  cmp     [rbp+47h+var_70], r13
0x1800257a2  jz      short loc_1800257B4
0x1800257a4  mov     rcx, [rbp+47h+var_78]
0x1800257a8  mov     rax, [rcx]
0x1800257ab  mov     rax, [rax+20h]
0x1800257af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257b4  cmp     [rbp+47h+var_68], r13
0x1800257b8  jz      short loc_1800257CB
0x1800257ba  mov     rcx, [rbp+47h+var_60]
0x1800257be  mov     rax, [rcx]
0x1800257c1  mov     rax, [rax+20h]
0x1800257c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257ca  nop
0x1800257cb  jmp     loc_180025A01
0x1800257d0  mov     rcx, [rbp+47h+var_78]
0x1800257d4  mov     [rbp+47h+var_78], r13
0x1800257d8  test    rcx, rcx
0x1800257db  jz      short loc_1800257EA
0x1800257dd  mov     rax, [rcx]
0x1800257e0  mov     rax, [rax+10h]
0x1800257e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257e9  nop
0x1800257ea  mov     rcx, [rbp+47h+var_58]
0x1800257ee  mov     rax, [rcx]
0x1800257f1  lea     r8, [rbp+47h+var_78]
0x1800257f5  lea     rdx, _GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec
0x1800257fc  mov     rax, [rax]
0x1800257ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025804  mov     ebx, eax
0x180025806  test    eax, eax
0x180025808  jns     short loc_180025855
0x18002580a  mov     rcx, [rbp+4Fh]; this
0x18002580e  mov     r9d, eax; char *
0x180025811  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180025818  mov     edx, 6Fh ; 'o'; void *
0x18002581d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025822  nop
0x180025823  cmp     [rbp+47h+var_70], r13
0x180025827  jz      short loc_180025839
0x180025829  mov     rcx, [rbp+47h+var_78]
0x18002582d  mov     rax, [rcx]
0x180025830  mov     rax, [rax+20h]
0x180025834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025839  cmp     [rbp+47h+var_68], r13
0x18002583d  jz      short loc_180025850
0x18002583f  mov     rcx, [rbp+47h+var_60]
0x180025843  mov     rax, [rcx]
0x180025846  mov     rax, [rax+20h]
0x18002584a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002584f  nop
0x180025850  jmp     loc_180025A01
0x180025855  mov     rcx, [rbp+47h+var_78]
0x180025859  mov     rax, [rcx]
0x18002585c  lea     r8, [rbp+47h+arg_18]
0x180025860  lea     rdx, [rbp+47h+var_70]
0x180025864  mov     rax, [rax+18h]
0x180025868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002586d  mov     ebx, eax
0x18002586f  test    eax, eax
0x180025871  jns     short loc_1800258BE
0x180025873  mov     rcx, [rbp+4Fh]; this
0x180025877  mov     r9d, eax; char *
0x18002587a  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\fa"...
0x180025881  mov     edx, 70h ; 'p'; void *
0x180025886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002588b  nop
0x18002588c  cmp     [rbp+47h+var_70], r13
0x180025890  jz      short loc_1800258A2
0x180025892  mov     rcx, [rbp+47h+var_78]
0x180025896  mov     rax, [rcx]
0x180025899  mov     rax, [rax+20h]
0x18002589d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a2  cmp     [rbp+47h+var_68], r13
0x1800258a6  jz      short loc_1800258B9
0x1800258a8  mov     rcx, [rbp+47h+var_60]
0x1800258ac  mov     rax, [rcx]
0x1800258af  mov     rax, [rax+20h]
0x1800258b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258b8  nop
0x1800258b9  jmp     loc_180025A01
0x1800258be  shl     r14d, 10h
0x1800258c2  mov     eax, r14d
0x1800258c5  cdq
0x1800258c6  idiv    r15d
0x1800258c9  inc     eax
0x1800258cb  mov     [rbp+47h+var_80], eax
0x1800258ce  shl     edi, 10h
0x1800258d1  mov     eax, edi
0x1800258d3  cdq
0x1800258d4  idiv    r12d
0x1800258d7  mov     r13d, eax
0x1800258da  xor     ebx, ebx
0x1800258dc  xor     edi, edi
0x1800258de  test    r12d, r12d
0x1800258e1  jle     loc_1800259AF
0x1800258e7  lea     edx, [r13+1]
0x1800258eb  imul    edx, edi
0x1800258ee  shr     rdx, 10h
0x1800258f2  movsxd  rax, [rbp+47h+arg_10]
0x1800258f6  mov     r14, rax
0x1800258f9  imul    r14, rdx
0x1800258fd  add     r14, [rbp+47h+var_68]
0x180025901  test    dil, 1
0x180025905  jnz     short loc_180025915
0x180025907  mov     rbx, rdx
0x18002590a  shr     rbx, 1
0x18002590d  imul    rbx, rax
0x180025911  add     rbx, [rbp+47h+var_48]
0x180025915  xor     esi, esi
0x180025917  test    r15d, r15d
0x18002591a  jle     loc_1800259A0
0x180025920  mov     r12d, [rbp+47h+var_80]
0x180025924  mov     ecx, r12d
0x180025927  imul    ecx, esi
0x18002592a  shr     rcx, 10h
0x18002592e  mov     al, [r14+rcx]
0x180025932  mov     [rbp+47h+arg_8], al
0x180025935  mov     eax, 0FFFFFFFEh
0x18002593a  and     rcx, rax
0x18002593d  mov     al, [rcx+rbx]
  ... truncated ...
```

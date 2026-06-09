# VsmUtils::Unseal(uchar *,uint,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uint *)

- ea: `0x140059204`
- end: `0x140059682`
- name: `?Unseal@VsmUtils@@YAJPEAEIW4TpmAuthType@1@0I0IPEAI@Z`
- size: `1150`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x14004907c`

## callees

- `0x140007410`
- `0x14000e034`
- `0x1400104fc`
- `0x14002bdcc`
- `0x140055470`
- `0x1400560d4`
- `0x140057f5c`
- `0x140059204`
- `0x14005ac70`
- `0x14005be04`
- `0x14005c5c4`
- `0x1400604d8`
- `0x140060e24`
- `0x140061684`
- `0x140061fb0`
- `0x140062520`
- `0x140065c28`
- `0x140067d88`
- `0x140068248`
- `0x14006833c`
- `0x14006a3f8`
- `0x14006a4ac`

## string_xrefs

- `0x1400592f6`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400593a8`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140059489`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400594fa`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140059572`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005965b`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall VsmUtils::Unseal(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        _DWORD *a8)
{
  unsigned __int64 v8; // rdi
  unsigned int v10; // r13d
  _DWORD *v11; // r14
  unsigned int v13; // edx
  __int64 v14; // rdx
  unsigned int v15; // edx
  unsigned int v16; // ebx
  const unsigned __int8 **v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // ebx
  __int64 v20; // r9
  unsigned int v21; // r8d
  unsigned int v22; // ebx
  unsigned int v23; // r15d
  int v24; // eax
  struct VsmUtils::TpmSessionKey *v25; // rax
  struct tpm12class::TPMW82B_BUFFER *v26; // rdx
  int RsaSRKName; // eax
  const unsigned __int8 **v28; // r9
  __int64 v29; // rdx
  const unsigned __int8 **v30; // r9
  unsigned int v31; // eax
  int v32; // edx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rdx
  int v38; // eax
  struct tpm12class::TPMW82B_BUFFER *v39; // r8
  unsigned __int8 v40; // r9
  unsigned int v41; // eax
  int v42; // edx
  unsigned int *v43; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v45; // [rsp+58h] [rbp-A8h]
  _QWORD v46[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  char v50; // [rsp+90h] [rbp-70h]
  unsigned __int16 v51; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v52; // [rsp+A0h] [rbp-60h]
  unsigned int v53; // [rsp+B0h] [rbp-50h]
  _BYTE v54[80]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v55[196]; // [rsp+110h] [rbp+10h] BYREF
  int v56; // [rsp+1D4h] [rbp+D4h]
  char v57[72]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v58[72]; // [rsp+220h] [rbp+120h] BYREF
  tpm12class::TpmDataObject *v59; // [rsp+268h] [rbp+168h]
  int v60; // [rsp+270h] [rbp+170h]
  char v61[72]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v62[168]; // [rsp+2C0h] [rbp+1C0h] BYREF
  VsmUtils *v63; // [rsp+368h] [rbp+268h]
  int v64; // [rsp+380h] [rbp+280h]
  char v65[128]; // [rsp+388h] [rbp+288h] BYREF
  unsigned __int16 v66; // [rsp+408h] [rbp+308h]
  void *Src; // [rsp+410h] [rbp+310h]
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+358h]
  unsigned int v69; // [rsp+460h] [rbp+360h] BYREF
  int v70; // [rsp+470h] [rbp+370h]
  unsigned __int8 *v71; // [rsp+478h] [rbp+378h]

  v71 = a4;
  v70 = a3;
  v8 = a2;
  if ( !a1 || a2 < 2 || (v10 = a5, a5 - 1 > 0x3FF) || (v11 = a8) == 0 )
  {
    v14 = 1407;
    goto LABEL_55;
  }
  if ( !a6 && !a7 )
  {
    *a8 = 128;
    return 0;
  }
  v13 = *(unsigned __int8 *)(a1 + 1) + 2;
  v53 = v13;
  if ( (unsigned __int64)v13 + 2 >= v8 )
  {
    v14 = 1425;
LABEL_55:
    v19 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80070057LL,
      (int)v43);
    return v19;
  }
  v69 = *(unsigned __int8 *)(v13 + 1 + a1);
  v15 = v13 + 2;
  v16 = v15 + v69;
  if ( v15 + v69 > (unsigned int)v8 )
  {
    v14 = 1434;
    goto LABEL_55;
  }
  v44 = v15;
  tpm12class::TPMW8L_DIGEST::TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v54);
  if ( v16 == (_DWORD)v8 )
    goto LABEL_26;
  if ( (unsigned __int64)v16 + 4 <= v8 )
  {
    v21 = *(unsigned __int8 *)(v16 + 3 + a1);
    v22 = v16 + 4;
    v23 = v22 + v21;
    if ( v22 + v21 > (unsigned int)v8 )
    {
      v18 = 1450;
      goto LABEL_15;
    }
    if ( v21 )
    {
      v24 = tpm12class::TpmDataObject::Set(
              (tpm12class::TpmDataObject *)v54,
              (const unsigned __int8 *)(a1 + v22),
              v21,
              v17,
              v43);
      v19 = v24;
      if ( v24 < 0 )
      {
        v20 = (unsigned int)v24;
        v18 = 1454;
        goto LABEL_16;
      }
      v22 = v23;
    }
    if ( v22 != (_DWORD)v8 )
    {
      v18 = 1459;
      goto LABEL_15;
    }
LABEL_26:
    LOWORD(v70) = 256;
    v25 = VsmUtils::TpmSessionKey::Instance();
    SetTbsHandle(*((_QWORD *)v25 + 1));
    tpm12class::TPMW8_Load::TPMW8_Load((tpm12class::TPMW8_Load *)v55);
    v56 = -2130706431;
    RsaSRKName = VsmUtils::GetRsaSRKName((VsmUtils *)v57, v26);
    v19 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v29 = 1490;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)RsaSRKName,
        (int)v43);
LABEL_29:
      tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v55);
      goto LABEL_17;
    }
    RsaSRKName = tpm12class::TpmDataObject::Set(
                   (tpm12class::TpmDataObject *)v58,
                   (const unsigned __int8 *)a1,
                   v53,
                   v28,
                   v43);
    v19 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v29 = 1492;
      goto LABEL_28;
    }
    RsaSRKName = tpm12class::TpmDataObject::Set(v59, (const unsigned __int8 *)(a1 + v44), v69, v30, v43);
    v19 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v29 = 1493;
      goto LABEL_28;
    }
    v31 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v55, 0);
    RsaSRKName = VsmUtils::MapTpmError((VsmUtils *)v31, v32);
    v19 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v29 = 1495;
      goto LABEL_28;
    }
    v44 = (unsigned __int64)v55;
    v45 = 256;
    tpm12class::TPMW8_Unseal::TPMW8_Unseal((tpm12class::TPMW8_Unseal *)v62);
    v64 = v60;
    v33 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v65,
            (const struct tpm12class::TPMW82B_BUFFER *)v61);
    v19 = v33;
    if ( v33 < 0 )
    {
      v34 = 1508;
      goto LABEL_38;
    }
    v46[1] = 0;
    v46[2] = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v46[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v51 = 0;
    v52 = 0;
    v36 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v46, 0x20u);
    v19 = v36;
    if ( v36 >= 0 )
    {
      v69 = 0;
      v38 = PlatformHash(L"SHA256", v71, v10, 0, 0, v52, v51, &v69, 0);
      if ( v38 < 0 )
      {
        v19 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x5ED,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v38,
                (int)v43);
        goto LABEL_44;
      }
      v51 = v69;
      LOBYTE(v39) = 64;
      v36 = VsmUtils::AddSecureSession(v63, (struct tpm12class::TPMW8_SESSION *)v46, v39, v40);
      v19 = v36;
      if ( v36 >= 0 )
      {
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v46);
        v41 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v62, 0);
        v33 = VsmUtils::MapTpmError((VsmUtils *)v41, v42);
        v19 = v33;
        if ( v33 >= 0 )
        {
          if ( a7 >= v66 )
          {
            *v11 = v66;
            memcpy_0(a6, Src, v66);
            tpm12class::TPMW8_Unseal::~TPMW8_Unseal((tpm12class::TPMW8_Unseal *)v62);
            wil::details::ScopeExitFnGuard__lambda_3efb7b143ea4e1281c91886708fcc64d___::operator()(&v44);
            tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v55);
            v19 = 0;
            goto LABEL_17;
          }
          v19 = -1073741789;
          v35 = 3221225507LL;
          v34 = 1575;
          goto LABEL_39;
        }
        v34 = 1573;
LABEL_38:
        v35 = (unsigned int)v33;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
          (const char *)v35,
          (int)v43);
LABEL_40:
        tpm12class::TPMW8_Unseal::~TPMW8_Unseal((tpm12class::TPMW8_Unseal *)v62);
        wil::details::ScopeExitFnGuard__lambda_3efb7b143ea4e1281c91886708fcc64d___::operator()(&v44);
        goto LABEL_29;
      }
      v37 = 1524;
    }
    else
    {
      v37 = 1513;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v36,
      (int)v43);
LABEL_44:
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v46);
    goto LABEL_40;
  }
  v18 = 1445;
LABEL_15:
  v19 = -2147024809;
  v20 = 2147942487LL;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
    (const char *)v20,
    (int)v43);
LABEL_17:
  tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v54);
  return v19;
}

```

## disassembly

```asm
0x140059204  mov     [rsp-8+arg_18], r9
0x140059209  mov     [rsp-8+arg_10], r8d
0x14005920e  push    rbp
0x14005920f  push    rbx
0x140059210  push    rsi
0x140059211  push    rdi
0x140059212  push    r13
0x140059214  push    r14
0x140059216  push    r15
0x140059218  lea     rbp, [rsp-320h]
0x140059220  sub     rsp, 420h
0x140059227  mov     edi, edx
0x140059229  mov     rsi, rcx
0x14005922c  test    rcx, rcx
0x14005922f  jz      loc_14005964E
0x140059235  cmp     edi, 2
0x140059238  jb      loc_14005964E
0x14005923e  mov     r13d, [rbp+350h+arg_20]
0x140059245  lea     eax, [r13-1]
0x140059249  cmp     eax, 3FFh
0x14005924e  ja      loc_14005964E
0x140059254  mov     r14, [rbp+350h+arg_38]
0x14005925b  test    r14, r14
0x14005925e  jz      loc_14005964E
0x140059264  cmp     [rbp+350h+arg_28], 0
0x14005926c  jnz     short loc_140059285
0x14005926e  cmp     [rbp+350h+arg_30], 0
0x140059275  jnz     short loc_140059285
0x140059277  mov     dword ptr [r14], 80h
0x14005927e  xor     eax, eax
0x140059280  jmp     loc_140059670
0x140059285  movzx   edx, byte ptr [rcx+1]
0x140059289  add     edx, 2
0x14005928c  mov     [rbp+350h+var_3A0], edx
0x14005928f  mov     eax, edx
0x140059291  add     rax, 2
0x140059295  cmp     rax, rdi
0x140059298  jb      short loc_1400592A4
0x14005929a  mov     edx, 591h
0x14005929f  jmp     loc_140059653
0x1400592a4  lea     eax, [rdx+1]
0x1400592a7  movzx   eax, byte ptr [rax+rcx]
0x1400592ab  mov     [rbp+350h+arg_0], eax
0x1400592b1  add     edx, 2
0x1400592b4  lea     ebx, [rdx+rax]
0x1400592b7  cmp     ebx, edi
0x1400592b9  jbe     short loc_1400592C5
0x1400592bb  mov     edx, 59Ah
0x1400592c0  jmp     loc_140059653
0x1400592c5  mov     eax, edx
0x1400592c7  mov     [rsp+450h+var_400], rax
0x1400592cc  lea     rcx, [rbp+350h+var_390]; this
0x1400592d0  call    ??0TPMW8L_DIGEST@tpm12class@@QEAA@XZ; tpm12class::TPMW8L_DIGEST::TPMW8L_DIGEST(void)
0x1400592d5  nop
0x1400592d6  cmp     ebx, edi
0x1400592d8  jz      loc_140059364
0x1400592de  mov     eax, ebx
0x1400592e0  add     rax, 4
0x1400592e4  cmp     rax, rdi
0x1400592e7  jbe     short loc_140059318
0x1400592e9  mov     edx, 5A5h; void *
0x1400592ee  mov     ebx, 80070057h
0x1400592f3  mov     r9d, ebx; char *
0x1400592f6  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400592fd  mov     rcx, [rbp+358h]; this
0x140059304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059309  nop
0x14005930a  lea     rcx, [rbp+350h+var_390]; this
0x14005930e  call    ??1TPMW8L_DIGEST@tpm12class@@UEAA@XZ; tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST(void)
0x140059313  jmp     loc_14005966E
0x140059318  lea     eax, [rbx+3]
0x14005931b  movzx   r8d, byte ptr [rax+rsi]; unsigned int
0x140059320  add     ebx, 4
0x140059323  lea     r15d, [rbx+r8]
0x140059327  cmp     r15d, edi
0x14005932a  jbe     short loc_140059333
0x14005932c  mov     edx, 5AAh
0x140059331  jmp     short loc_1400592EE
0x140059333  test    r8d, r8d
0x140059336  jz      short loc_140059359
0x140059338  mov     edx, ebx
0x14005933a  add     rdx, rsi; unsigned __int8 *
0x14005933d  lea     rcx, [rbp+350h+var_390]; this
0x140059341  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x140059346  mov     ebx, eax
0x140059348  test    eax, eax
0x14005934a  jns     short loc_140059356
0x14005934c  mov     r9d, eax
0x14005934f  mov     edx, 5AEh
0x140059354  jmp     short loc_1400592F6
0x140059356  mov     ebx, r15d
0x140059359  cmp     ebx, edi
0x14005935b  jz      short loc_140059364
0x14005935d  mov     edx, 5B3h
0x140059362  jmp     short loc_1400592EE
0x140059364  xor     edi, edi
0x140059366  mov     word ptr [rbp+350h+arg_10], 100h
0x14005936f  call    ?Instance@TpmSessionKey@VsmUtils@@SAAEAV12@XZ; VsmUtils::TpmSessionKey::Instance(void)
0x140059374  mov     rcx, [rax+8]; unsigned __int64
0x140059378  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x14005937d  lea     rcx, [rbp+350h+var_340]; this
0x140059381  call    ??0TPMW8_Load@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Load::TPMW8_Load(void)
0x140059386  nop
0x140059387  mov     [rbp+350h+var_27C], 81000001h
0x140059391  lea     rcx, [rbp+350h+var_278]; this
0x140059398  call    ?GetRsaSRKName@VsmUtils@@YAJPEAVTPMW82B_BUFFER@tpm12class@@@Z; VsmUtils::GetRsaSRKName(tpm12class::TPMW82B_BUFFER *)
0x14005939d  mov     ebx, eax
0x14005939f  test    eax, eax
0x1400593a1  jns     short loc_1400593CE
0x1400593a3  mov     edx, 5D2h; void *
0x1400593a8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400593af  mov     r9d, eax; char *
0x1400593b2  mov     rcx, [rbp+358h]; this
0x1400593b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400593be  nop
0x1400593bf  lea     rcx, [rbp+350h+var_340]; this
0x1400593c3  call    ??1TPMW8_Load@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Load::~TPMW8_Load(void)
0x1400593c8  nop
0x1400593c9  jmp     loc_14005930A
0x1400593ce  mov     r8d, [rbp+350h+var_3A0]; unsigned int
0x1400593d2  mov     rdx, rsi; unsigned __int8 *
0x1400593d5  lea     rcx, [rbp+350h+var_230]; this
0x1400593dc  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x1400593e1  mov     ebx, eax
0x1400593e3  test    eax, eax
0x1400593e5  jns     short loc_1400593EE
0x1400593e7  mov     edx, 5D4h
0x1400593ec  jmp     short loc_1400593A8
0x1400593ee  mov     rdx, [rsp+450h+var_400]
0x1400593f3  add     rdx, rsi; unsigned __int8 *
0x1400593f6  mov     r8d, [rbp+350h+arg_0]; unsigned int
0x1400593fd  mov     rcx, [rbp+350h+var_1E8]; this
0x140059404  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x140059409  mov     ebx, eax
0x14005940b  test    eax, eax
0x14005940d  jns     short loc_140059416
0x14005940f  mov     edx, 5D5h
0x140059414  jmp     short loc_1400593A8
0x140059416  xor     edx, edx; void *
0x140059418  lea     rcx, [rbp+350h+var_340]; this
0x14005941c  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140059421  mov     ecx, eax; this
0x140059423  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140059428  mov     ebx, eax
0x14005942a  test    eax, eax
0x14005942c  jns     short loc_140059438
0x14005942e  mov     edx, 5D7h
0x140059433  jmp     loc_1400593A8
0x140059438  lea     rax, [rbp+350h+var_340]
0x14005943c  mov     [rsp+450h+var_400], rax
0x140059441  mov     [rsp+450h+var_3F8], 100h
0x140059448  lea     rcx, [rbp+350h+var_190]; this
0x14005944f  call    ??0TPMW8_Unseal@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Unseal::TPMW8_Unseal(void)
0x140059454  nop
0x140059455  mov     eax, [rbp+350h+var_1E0]
0x14005945b  mov     [rbp+350h+var_D0], eax
0x140059461  lea     rdx, [rbp+350h+var_1D8]; struct tpm12class::TPMW82B_BUFFER *
0x140059468  lea     rcx, [rbp+350h+var_C8]; this
0x14005946f  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x140059474  mov     ebx, eax
0x140059476  test    eax, eax
0x140059478  jns     short loc_1400594B2
0x14005947a  mov     edx, 5E4h; void *
0x14005947f  mov     r9d, eax; char *
0x140059482  mov     rcx, [rbp+358h]; this
0x140059489  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140059490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059495  nop
0x140059496  lea     rcx, [rbp+350h+var_190]; this
0x14005949d  call    ??1TPMW8_Unseal@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Unseal::~TPMW8_Unseal(void)
0x1400594a2  nop
0x1400594a3  lea     rcx, [rsp+450h+var_400]
0x1400594a8  call    wil__details__ScopeExitFnGuard__lambda_3efb7b143ea4e1281c91886708fcc64d_____operator__
0x1400594ad  jmp     loc_1400593BF
0x1400594b2  mov     [rsp+450h+var_3E8], rdi
0x1400594b7  mov     [rsp+450h+var_3E0], rdi
0x1400594bc  mov     [rsp+450h+var_3D8], edi
0x1400594c0  mov     [rbp+350h+var_3D0], rdi
0x1400594c4  mov     [rbp+350h+var_3C8], rdi
0x1400594c8  mov     [rbp+350h+var_3C0], dil
0x1400594cc  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x1400594d3  mov     [rsp+450h+var_3F0], rax
0x1400594d8  mov     [rbp+350h+var_3B8], di
0x1400594dc  mov     [rbp+350h+var_3B0], rdi
0x1400594e0  mov     edx, 20h ; ' '; unsigned __int64
0x1400594e5  lea     rcx, [rsp+450h+var_3F0]; this
0x1400594ea  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x1400594ef  mov     ebx, eax
0x1400594f1  test    eax, eax
0x1400594f3  jns     short loc_140059520
0x1400594f5  mov     edx, 5E9h; void *
0x1400594fa  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140059501  mov     r9d, eax; char *
0x140059504  mov     rcx, [rbp+358h]; this
0x14005950b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059510  nop
0x140059511  lea     rcx, [rsp+450h+var_3F0]; this
0x140059516  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005951b  jmp     loc_140059496
0x140059520  mov     [rbp+350h+arg_0], edi
0x140059526  movzx   eax, [rbp+350h+var_3B8]
0x14005952a  mov     [rsp+450h+var_410], edi; unsigned int
0x14005952e  lea     rcx, [rbp+350h+arg_0]
0x140059535  mov     [rsp+450h+var_418], rcx; unsigned int *
0x14005953a  mov     [rsp+450h+var_420], eax; unsigned int
0x14005953e  mov     rax, [rbp+350h+var_3B0]
0x140059542  mov     [rsp+450h+var_428], rax; unsigned __int8 *
0x140059547  mov     dword ptr [rsp+450h+var_430], edi; int
0x14005954b  xor     r9d, r9d; unsigned __int8 *
0x14005954e  mov     r8d, r13d; unsigned int
0x140059551  mov     rdx, [rbp+350h+arg_18]; unsigned __int8 *
0x140059558  lea     rcx, aSha256; "SHA256"
0x14005955f  call    ?PlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; PlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x140059564  test    eax, eax
0x140059566  jns     short loc_140059587
0x140059568  mov     rcx, [rbp+358h]; this
0x14005956f  mov     r9d, eax; char *
0x140059572  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140059579  mov     edx, 5EDh; void *
0x14005957e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140059583  mov     ebx, eax
0x140059585  jmp     short loc_140059511
0x140059587  movzx   eax, word ptr [rbp+350h+arg_0]
0x14005958e  mov     [rbp+350h+var_3B8], ax
0x140059592  mov     r8b, 40h ; '@'; struct tpm12class::TPMW82B_BUFFER *
0x140059595  lea     rdx, [rsp+450h+var_3F0]; struct tpm12class::TPMW8_SESSION *
0x14005959a  mov     rcx, [rbp+350h+var_E8]; this
0x1400595a1  call    ?AddSecureSession@VsmUtils@@YAJPEAVTPMW8_SESSION@tpm12class@@PEAVTPMW82B_BUFFER@3@E@Z; VsmUtils::AddSecureSession(tpm12class::TPMW8_SESSION *,tpm12class::TPMW82B_BUFFER *,uchar)
0x1400595a6  mov     ebx, eax
0x1400595a8  test    eax, eax
0x1400595aa  jns     short loc_1400595B6
0x1400595ac  mov     edx, 5F4h
0x1400595b1  jmp     loc_1400594FA
0x1400595b6  lea     rcx, [rsp+450h+var_3F0]; this
0x1400595bb  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400595c0  xor     edx, edx; void *
0x1400595c2  lea     rcx, [rbp+350h+var_190]; this
0x1400595c9  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400595ce  mov     ecx, eax; this
0x1400595d0  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x1400595d5  mov     ebx, eax
0x1400595d7  test    eax, eax
0x1400595d9  jns     short loc_1400595E5
0x1400595db  mov     edx, 625h
0x1400595e0  jmp     loc_14005947F
0x1400595e5  movzx   eax, [rbp+350h+var_48]
0x1400595ec  cmp     [rbp+350h+arg_30], eax
0x1400595f2  jnb     short loc_140059606
0x1400595f4  mov     ebx, 0C0000023h
0x1400595f9  mov     r9d, ebx
0x1400595fc  mov     edx, 627h
0x140059601  jmp     loc_140059482
0x140059606  mov     [r14], eax
0x140059609  movzx   r8d, [rbp+350h+var_48]; Size
0x140059611  mov     rdx, [rbp+350h+Src]; Src
0x140059618  mov     rcx, [rbp+350h+arg_28]; void *
0x14005961f  call    memcpy_0
0x140059624  nop
0x140059625  lea     rcx, [rbp+350h+var_190]; this
0x14005962c  call    ??1TPMW8_Unseal@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Unseal::~TPMW8_Unseal(void)
0x140059631  nop
0x140059632  lea     rcx, [rsp+450h+var_400]
0x140059637  call    wil__details__ScopeExitFnGuard__lambda_3efb7b143ea4e1281c91886708fcc64d_____operator__
0x14005963c  nop
0x14005963d  lea     rcx, [rbp+350h+var_340]; this
0x140059641  call    ??1TPMW8_Load@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Load::~TPMW8_Load(void)
0x140059646  nop
0x140059647  mov     ebx, edi
0x140059649  jmp     loc_14005930A
0x14005964e  mov     edx, 57Fh; void *
0x140059653  mov     ebx, 80070057h
0x140059658  mov     r9d, ebx; char *
0x14005965b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140059662  mov     rcx, [rbp+358h]; this
0x140059669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005966e  mov     eax, ebx
0x140059670  add     rsp, 420h
0x140059677  pop     r15
0x140059679  pop     r14
0x14005967b  pop     r13
0x14005967d  pop     rdi
0x14005967e  pop     rsi
0x14005967f  pop     rbx
0x140059680  pop     rbp
0x140059681  retn
```

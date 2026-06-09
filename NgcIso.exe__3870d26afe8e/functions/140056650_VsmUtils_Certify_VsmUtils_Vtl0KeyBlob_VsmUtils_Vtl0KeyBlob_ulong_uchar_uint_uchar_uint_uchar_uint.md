# VsmUtils::Certify(VsmUtils::Vtl0KeyBlob *,VsmUtils::Vtl0KeyBlob *,ulong,uchar *,uint,uchar *,uint,uchar * *,uint *)

- ea: `0x140056650`
- end: `0x140056a3f`
- name: `?Certify@VsmUtils@@YAJPEAUVtl0KeyBlob@1@0KPEAEI1IPEAPEAEPEAI@Z`
- size: `1007`
- prototype: `__int64 __fastcall(VsmUtils *__hidden this, struct VsmUtils::Vtl0KeyBlob *, struct VsmUtils::Vtl0KeyBlob *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140047f34`

## callees

- `0x14000e034`
- `0x14000f6a0`
- `0x14005522c`
- `0x140055470`
- `0x140056650`
- `0x14005b484`
- `0x14005b650`
- `0x14005b944`
- `0x14005c5c4`
- `0x1400624d4`
- `0x140063f94`
- `0x140064304`
- `0x1400652d4`
- `0x140065c28`
- `0x1400676b4`
- `0x14006927c`
- `0x1400693dc`
- `0x140069780`
- `0x1400698a4`
- `0x140069958`

## string_xrefs

- `0x1400566bc`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140056740`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140056823`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140056873`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400568f2`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VsmUtils::Certify(
        VsmUtils *this,
        struct VsmUtils::Vtl0KeyBlob *a2,
        struct VsmUtils::Vtl0KeyBlob *a3,
        VsmUtils *a4,
        unsigned __int8 *Size,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        struct tpm12class::TPMW8_Certify *a8,
        unsigned __int8 **a9)
{
  int v9; // r14d
  __int64 v12; // rcx
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  int v17; // edx
  int v18; // eax
  unsigned int v19; // r9d
  VsmUtils *v20; // rdi
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  int v24; // edx
  int ClaimSubject; // eax
  __int64 v26; // rdx
  __int64 v27; // r9
  unsigned int v28; // eax
  int v29; // edx
  unsigned int *v31; // [rsp+20h] [rbp-E0h]
  unsigned int *v32; // [rsp+30h] [rbp-D0h] BYREF
  VsmUtils *Src; // [rsp+38h] [rbp-C8h]
  _QWORD v34[24]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v35[4]; // [rsp+100h] [rbp+0h]
  _BYTE v36[196]; // [rsp+110h] [rbp+10h] BYREF
  int v37; // [rsp+1D4h] [rbp+D4h]
  tpm12class::TpmDataObject *v38; // [rsp+1D8h] [rbp+D8h]
  _BYTE v39[144]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v40[42]; // [rsp+270h] [rbp+170h] BYREF
  tpm12class::TPMW8_SESSION *v41; // [rsp+318h] [rbp+218h]
  int v42; // [rsp+330h] [rbp+230h]
  _BYTE v43[72]; // [rsp+338h] [rbp+238h] BYREF
  int v44; // [rsp+380h] [rbp+280h]
  _BYTE v45[72]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v46[624]; // [rsp+3D0h] [rbp+2D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+688h] [rbp+588h]

  Src = a4;
  v9 = (int)a3;
  v12 = *((_QWORD *)this + 5);
  if ( v12 == *((_QWORD *)a2 + 5) )
  {
    SetTbsHandle(v12);
    BYTE1(v32) = 1;
    tpm12class::TPMW8_Certify::TPMW8_Certify((tpm12class::TPMW8_Certify *)v40);
    v42 = *((_DWORD *)this + 12);
    v14 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v43,
            (const unsigned __int8 *)this + 4,
            0x22u);
    v13 = v14;
    if ( v14 < 0 )
    {
      v15 = 646;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v14,
        (int)v31);
LABEL_39:
      tpm12class::TPMW8_Certify::~TPMW8_Certify((tpm12class::TPMW8_Certify *)v40);
      ClearTbsHandle();
      return v13;
    }
    v44 = *((_DWORD *)a2 + 12);
    v14 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v45,
            (const unsigned __int8 *)a2 + 4,
            0x22u);
    v13 = v14;
    if ( v14 < 0 )
    {
      v15 = 649;
      goto LABEL_7;
    }
    *((_WORD *)v41 + 381) = 11;
    *((_BYTE *)v41 + 761) = 1;
    v14 = tpm12class::TPMW8_SESSION::Create(v41, 0);
    v13 = v14;
    if ( v14 < 0 )
    {
      v15 = 653;
      goto LABEL_7;
    }
    if ( a6 )
    {
      if ( (_DWORD)a7 )
      {
        v14 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v46, a6, (unsigned int)a7);
        v13 = v14;
        if ( v14 < 0 )
        {
          v15 = 657;
          goto LABEL_7;
        }
      }
    }
    tpm12class::TPMW8_COMMAND::TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v34);
    v34[0] = &tpm12class::TPMW8_PolicyCommandCode::`vftable';
    tpm12class::TPMW8_PolicyCommandCode::Clear((tpm12class::TPMW8_PolicyCommandCode *)v34, 1u);
    v35[0] = *((_DWORD *)v41 + 4);
    v35[1] = 328;
    v16 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v34, 0);
    v18 = VsmUtils::MapTpmError((VsmUtils *)v16, v17);
    v13 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v18,
        (int)v31);
      v34[0] = &tpm12class::TPMW8_PolicyCommandCode::`vftable';
LABEL_16:
      *(_QWORD *)v35 = 1073741831;
      tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v34);
      goto LABEL_39;
    }
    v20 = Src;
    v21 = VsmUtils::ExecutePolicyOr(Src, (unsigned __int8 *)(unsigned int)Size, v35[0], v19);
    v13 = v21;
    if ( v21 < 0 )
    {
      v22 = 666;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v21,
        (int)v31);
LABEL_20:
      v34[0] = &tpm12class::TPMW8_PolicyCommandCode::`vftable';
      goto LABEL_16;
    }
    v23 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v40, 0);
    v21 = VsmUtils::MapTpmError((VsmUtils *)v23, v24);
    v13 = v21;
    if ( v21 < 0 )
    {
      v22 = 668;
      goto LABEL_19;
    }
    tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
    v37 = *((_DWORD *)this + 12);
    ClaimSubject = tpm12class::TPMW82B_BUFFER::CopyFrom(
                     (tpm12class::TPMW82B_BUFFER *)v39,
                     (const unsigned __int8 *)this + 4,
                     0x22u);
    v13 = ClaimSubject;
    if ( ClaimSubject >= 0 )
    {
      v28 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v36, 0);
      ClaimSubject = VsmUtils::MapTpmError((VsmUtils *)v28, v29);
      v13 = ClaimSubject;
      if ( ClaimSubject >= 0 )
      {
        ClaimSubject = tpm12class::TpmDataObject::Get(v38, 0, 0, (unsigned __int16 *)&v32 + 2);
        v13 = ClaimSubject;
        if ( ClaimSubject >= 0 )
        {
          if ( v9 == 2 )
          {
            ClaimSubject = VsmUtils::GetClaimSubject(v38, v20, (unsigned int)Size, (unsigned int)v40, a8, a9, v32);
            v13 = ClaimSubject;
            if ( ClaimSubject < 0 )
            {
              v26 = 687;
              goto LABEL_25;
            }
          }
          else
          {
            if ( v9 != 258 )
            {
              v13 = -2146893785;
              v27 = 2148073511LL;
              v26 = 699;
              goto LABEL_26;
            }
            ClaimSubject = VsmUtils::GetClaimWebAuthSubject(v38, (struct tpm12class::TPMW8T_PUBLIC *)v40, a8, a9, v31);
            v13 = ClaimSubject;
            if ( ClaimSubject < 0 )
            {
              v26 = 695;
              goto LABEL_25;
            }
          }
          tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
          v34[0] = &tpm12class::TPMW8_PolicyCommandCode::`vftable';
          *(_QWORD *)v35 = 1073741831;
          tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v34);
          v13 = 0;
          goto LABEL_39;
        }
        v26 = 676;
      }
      else
      {
        v26 = 673;
      }
    }
    else
    {
      v26 = 672;
    }
LABEL_25:
    v27 = (unsigned int)ClaimSubject;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)v27,
      (int)v31);
    tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
    goto LABEL_20;
  }
  v13 = -2146893786;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27D,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
    (const char *)0x80090026LL,
    (int)v31);
  return v13;
}

```

## disassembly

```asm
0x140056650  mov     [rsp-8+arg_10], rbx
0x140056655  push    rbp
0x140056656  push    rsi
0x140056657  push    rdi
0x140056658  push    r12
0x14005665a  push    r13
0x14005665c  push    r14
0x14005665e  push    r15
0x140056660  lea     rbp, [rsp-550h]
0x140056668  sub     rsp, 650h
0x14005666f  mov     rax, cs:__security_cookie
0x140056676  xor     rax, rsp
0x140056679  mov     [rbp+580h+var_40], rax
0x140056680  mov     [rsp+680h+Src], r9
0x140056685  mov     r14d, r8d
0x140056688  mov     rdi, rdx
0x14005668b  mov     r15, rcx
0x14005668e  mov     rsi, [rbp+580h+arg_28]
0x140056695  mov     r12, [rbp+580h+arg_38]
0x14005669c  mov     r13, [rbp+580h+arg_40]
0x1400566a3  mov     rcx, [rcx+28h]; unsigned __int64
0x1400566a7  cmp     rcx, [rdx+28h]
0x1400566ab  jz      short loc_1400566D2
0x1400566ad  mov     rcx, [rbp+588h]; this
0x1400566b4  mov     ebx, 80090026h
0x1400566b9  mov     r9d, ebx; char *
0x1400566bc  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400566c3  mov     edx, 27Dh; void *
0x1400566c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400566cd  jmp     loc_140056A13
0x1400566d2  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x1400566d7  mov     [rsp+680h+var_64F], 1
0x1400566dc  lea     rcx, [rbp+580h+var_410]; this
0x1400566e3  call    ??0TPMW8_Certify@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Certify::TPMW8_Certify(void)
0x1400566e8  nop
0x1400566e9  mov     eax, [r15+30h]
0x1400566ed  mov     [rbp+580h+var_350], eax
0x1400566f3  lea     rdx, [r15+4]; unsigned __int8 *
0x1400566f7  mov     r8d, 22h ; '"'; unsigned __int64
0x1400566fd  lea     rcx, [rbp+580h+var_348]; this
0x140056704  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140056709  mov     ebx, eax
0x14005670b  test    eax, eax
0x14005670d  jns     short loc_140056716
0x14005670f  mov     edx, 286h
0x140056714  jmp     short loc_140056740
0x140056716  mov     eax, [rdi+30h]
0x140056719  mov     [rbp+580h+var_300], eax
0x14005671f  lea     rdx, [rdi+4]; unsigned __int8 *
0x140056723  mov     r8d, 22h ; '"'; unsigned __int64
0x140056729  lea     rcx, [rbp+580h+var_2F8]; this
0x140056730  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140056735  mov     ebx, eax
0x140056737  test    eax, eax
0x140056739  jns     short loc_14005675B
0x14005673b  mov     edx, 289h; void *
0x140056740  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140056747  mov     r9d, eax; char *
0x14005674a  mov     rcx, [rbp+588h]; this
0x140056751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056756  jmp     loc_140056A01
0x14005675b  mov     rax, [rbp+580h+var_368]
0x140056762  mov     word ptr [rax+2FAh], 0Bh
0x14005676b  mov     rax, [rbp+580h+var_368]
0x140056772  mov     byte ptr [rax+2F9h], 1
0x140056779  xor     edx, edx; void *
0x14005677b  mov     rcx, [rbp+580h+var_368]; this
0x140056782  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140056787  mov     ebx, eax
0x140056789  test    eax, eax
0x14005678b  jns     short loc_140056794
0x14005678d  mov     edx, 28Dh
0x140056792  jmp     short loc_140056740
0x140056794  test    rsi, rsi
0x140056797  jz      short loc_1400567C7
0x140056799  mov     eax, dword ptr [rbp+580h+arg_30]
0x14005679f  test    eax, eax
0x1400567a1  jz      short loc_1400567C7
0x1400567a3  mov     r8d, eax; unsigned __int64
0x1400567a6  mov     rdx, rsi; unsigned __int8 *
0x1400567a9  lea     rcx, [rbp+580h+var_2B0]; this
0x1400567b0  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x1400567b5  mov     ebx, eax
0x1400567b7  xor     esi, esi
0x1400567b9  test    eax, eax
0x1400567bb  jns     short loc_1400567C9
0x1400567bd  mov     edx, 291h
0x1400567c2  jmp     loc_140056740
0x1400567c7  xor     esi, esi
0x1400567c9  lea     rcx, [rsp+680h+var_640]; this
0x1400567ce  call    ??0TPMW8_COMMAND@tpm12class@@QEAA@XZ; tpm12class::TPMW8_COMMAND::TPMW8_COMMAND(void)
0x1400567d3  lea     rdi, ??_7TPMW8_PolicyCommandCode@tpm12class@@6B@; const tpm12class::TPMW8_PolicyCommandCode::`vftable'
0x1400567da  mov     [rsp+680h+var_640], rdi
0x1400567df  mov     dl, 1; unsigned __int8
0x1400567e1  lea     rcx, [rsp+680h+var_640]; this
0x1400567e6  call    ?Clear@TPMW8_PolicyCommandCode@tpm12class@@MEAAJE@Z; tpm12class::TPMW8_PolicyCommandCode::Clear(uchar)
0x1400567eb  nop
0x1400567ec  mov     rax, [rbp+580h+var_368]
0x1400567f3  mov     ecx, [rax+10h]
0x1400567f6  mov     [rbp+580h+var_580], ecx
0x1400567f9  mov     [rbp+580h+var_580+4], 148h
0x140056800  xor     edx, edx; void *
0x140056802  lea     rcx, [rsp+680h+var_640]; this
0x140056807  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14005680c  mov     ecx, eax; this
0x14005680e  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140056813  mov     ebx, eax
0x140056815  test    eax, eax
0x140056817  jns     short loc_140056851
0x140056819  mov     rcx, [rbp+588h]; this
0x140056820  mov     r9d, eax; char *
0x140056823  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005682a  mov     edx, 297h; void *
0x14005682f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056834  nop
0x140056835  mov     [rsp+680h+var_640], rdi
0x14005683a  mov     qword ptr [rbp+580h+var_580], 40000007h
0x140056842  lea     rcx, [rsp+680h+var_640]; this
0x140056847  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x14005684c  jmp     loc_140056A01
0x140056851  mov     r8d, [rbp+580h+var_580]; unsigned int
0x140056855  mov     edx, dword ptr [rbp+580h+Size]; unsigned __int8 *
0x14005685b  mov     rdi, [rsp+680h+Src]
0x140056860  mov     rcx, rdi; this
0x140056863  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x140056868  mov     ebx, eax
0x14005686a  test    eax, eax
0x14005686c  jns     short loc_140056898
0x14005686e  mov     edx, 29Ah; void *
0x140056873  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005687a  mov     r9d, eax; char *
0x14005687d  mov     rcx, [rbp+588h]; this
0x140056884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056889  nop
0x14005688a  lea     rax, ??_7TPMW8_PolicyCommandCode@tpm12class@@6B@; const tpm12class::TPMW8_PolicyCommandCode::`vftable'
0x140056891  mov     [rsp+680h+var_640], rax
0x140056896  jmp     short loc_14005683A
0x140056898  xor     edx, edx; void *
0x14005689a  lea     rcx, [rbp+580h+var_410]; this
0x1400568a1  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400568a6  mov     ecx, eax; this
0x1400568a8  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x1400568ad  mov     ebx, eax
0x1400568af  test    eax, eax
0x1400568b1  jns     short loc_1400568BA
0x1400568b3  mov     edx, 29Ch
0x1400568b8  jmp     short loc_140056873
0x1400568ba  lea     rcx, [rbp+580h+var_570]; this
0x1400568be  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x1400568c3  nop
0x1400568c4  mov     eax, [r15+30h]
0x1400568c8  mov     [rbp+580h+var_4AC], eax
0x1400568ce  mov     r8d, 22h ; '"'; unsigned __int64
0x1400568d4  lea     rdx, [r15+4]; unsigned __int8 *
0x1400568d8  lea     rcx, [rbp+580h+var_4A0]; this
0x1400568df  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x1400568e4  mov     ebx, eax
0x1400568e6  test    eax, eax
0x1400568e8  jns     short loc_140056914
0x1400568ea  mov     edx, 2A0h; void *
0x1400568ef  mov     r9d, eax; char *
0x1400568f2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400568f9  mov     rcx, [rbp+588h]; this
0x140056900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056905  nop
0x140056906  lea     rcx, [rbp+580h+var_570]; this
0x14005690a  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x14005690f  jmp     loc_14005688A
0x140056914  xor     edx, edx; void *
0x140056916  lea     rcx, [rbp+580h+var_570]; this
0x14005691a  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14005691f  mov     ecx, eax; this
0x140056921  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140056926  mov     ebx, eax
0x140056928  test    eax, eax
0x14005692a  jns     short loc_140056933
0x14005692c  mov     edx, 2A1h
0x140056931  jmp     short loc_1400568EF
0x140056933  xor     r8d, r8d; unsigned __int16
0x140056936  lea     r9, [rsp+680h+var_64C]; unsigned __int16 *
0x14005693b  xor     edx, edx; unsigned __int8 *
0x14005693d  mov     rcx, [rbp+580h+var_4A8]; this
0x140056944  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEGPEAG@Z; tpm12class::TpmDataObject::Get(uchar *,ushort,ushort *)
0x140056949  mov     ebx, eax
0x14005694b  test    eax, eax
0x14005694d  jns     short loc_140056956
0x14005694f  mov     edx, 2A4h
0x140056954  jmp     short loc_1400568EF
0x140056956  cmp     r14d, 2
0x14005695a  jz      short loc_1400569A0
0x14005695c  cmp     r14d, 102h
0x140056963  jz      short loc_140056977
0x140056965  mov     ebx, 80090027h
0x14005696a  mov     r9d, ebx
0x14005696d  mov     edx, 2BBh
0x140056972  jmp     loc_1400568F2
0x140056977  mov     r9, r13; unsigned __int8 **
0x14005697a  mov     r8, r12; struct tpm12class::TPMW8_Certify *
0x14005697d  lea     rdx, [rbp+580h+var_410]; struct tpm12class::TPMW8T_PUBLIC *
0x140056984  mov     rcx, [rbp+580h+var_4A8]; this
0x14005698b  call    ?GetClaimWebAuthSubject@VsmUtils@@YAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8_Certify@3@PEAPEAEPEAI@Z; VsmUtils::GetClaimWebAuthSubject(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8_Certify *,uchar * *,uint *)
0x140056990  mov     ebx, eax
0x140056992  test    eax, eax
0x140056994  jns     short loc_1400569D7
0x140056996  mov     edx, 2B7h
0x14005699b  jmp     loc_1400568EF
0x1400569a0  mov     [rsp+680h+var_658], r13; unsigned __int8 **
0x1400569a5  mov     [rsp+680h+var_660], r12; struct tpm12class::TPMW8_Certify *
0x1400569aa  lea     r9, [rbp+580h+var_410]; unsigned int
0x1400569b1  mov     r8d, dword ptr [rbp+580h+Size]; Size
0x1400569b8  mov     rdx, rdi; Src
0x1400569bb  mov     rcx, [rbp+580h+var_4A8]; this
0x1400569c2  call    ?GetClaimSubject@VsmUtils@@YAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAEIPEAVTPMW8_Certify@3@PEAPEAEPEAI@Z; VsmUtils::GetClaimSubject(tpm12class::TPMW8T_PUBLIC *,uchar *,uint,tpm12class::TPMW8_Certify *,uchar * *,uint *)
0x1400569c7  mov     ebx, eax
0x1400569c9  test    eax, eax
0x1400569cb  jns     short loc_1400569D7
0x1400569cd  mov     edx, 2AFh
0x1400569d2  jmp     loc_1400568EF
0x1400569d7  lea     rcx, [rbp+580h+var_570]; this
0x1400569db  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x1400569e0  nop
0x1400569e1  lea     rax, ??_7TPMW8_PolicyCommandCode@tpm12class@@6B@; const tpm12class::TPMW8_PolicyCommandCode::`vftable'
0x1400569e8  mov     [rsp+680h+var_640], rax
0x1400569ed  mov     qword ptr [rbp+580h+var_580], 40000007h
0x1400569f5  lea     rcx, [rsp+680h+var_640]; this
0x1400569fa  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x1400569ff  mov     ebx, esi
0x140056a01  lea     rcx, [rbp+580h+var_410]; this
0x140056a08  call    ??1TPMW8_Certify@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Certify::~TPMW8_Certify(void)
0x140056a0d  nop
0x140056a0e  call    ?ClearTbsHandle@@YAXXZ; ClearTbsHandle(void)
0x140056a13  mov     eax, ebx
0x140056a15  mov     rcx, [rbp+580h+var_40]
0x140056a1c  xor     rcx, rsp; StackCookie
0x140056a1f  call    __security_check_cookie
0x140056a24  mov     rbx, [rsp+680h+arg_10]
0x140056a2c  add     rsp, 650h
0x140056a33  pop     r15
0x140056a35  pop     r14
0x140056a37  pop     r13
0x140056a39  pop     r12
0x140056a3b  pop     rdi
0x140056a3c  pop     rsi
0x140056a3d  pop     rbp
0x140056a3e  retn
```

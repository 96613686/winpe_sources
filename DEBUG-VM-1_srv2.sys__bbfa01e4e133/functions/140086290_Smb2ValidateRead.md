# Smb2ValidateRead

- ea: `0x140086290`
- end: `0x140086dd1`
- name: `Smb2ValidateRead`
- size: `2881`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140073a60`

## callees

- `0x140003bec`
- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d684`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x140032e3c`
- `0x140032ea4`
- `0x14005c600`
- `0x140086290`

## import_xrefs

- `srvnet!SrvNetIsRdmaConnection` at `0x1400865f6`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008661f`
- `srvnet!SrvNetIsRdmaConnection` at `0x1400865f6`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008661f`
- `srvnet!SrvNetValidateMrToken` at `0x1400866b3`
- `srvnet!SrvNetValidateMrToken` at `0x1400866b3`

## string_xrefs

- `0x140086424`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x1400868b3`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009abe8`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac13`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac41`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac5f`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac7d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac9d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009acc1`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ad42`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ad66`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ad8a`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009adae`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009add2`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009adf6`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ae50`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
__int64 __fastcall Smb2ValidateRead(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  unsigned int v4; // r8d
  __int64 v5; // rbx
  __int64 v6; // r15
  int v7; // ebp
  int v8; // ebp
  __int64 v9; // r8
  __int64 v10; // r8
  int v11; // r14d
  char v12; // dl
  char v13; // dl
  __int64 v14; // rax
  int v15; // ecx
  char v16; // cl
  __int64 v17; // r8
  unsigned int v18; // r13d
  unsigned int v19; // r14d
  bool v20; // bp
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 v29; // r8
  int v30; // r9d
  char v31; // dl
  unsigned int v32; // r11d
  unsigned __int64 v33; // rcx
  __int64 v34; // r10
  __int64 v35; // r8
  int v36; // eax
  int v37; // eax
  unsigned int v38; // r8d
  _QWORD *v39; // rax
  __int64 *v40; // r9
  __int64 v41; // rcx
  __int64 *v42; // r11
  __int64 v43; // rcx
  __int64 *v44; // r10
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  int v48; // ecx
  int v49; // eax
  __int64 v50; // [rsp+98h] [rbp-60h]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x71 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
        BugCheckParameter4,
        v4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", 319);
    Smb2LkmdTelCollectParsingFailureReadHelper(v3, 0);
    return 0;
  }
  else
  {
    v5 = *(_QWORD *)(v1 + 24);
    if ( *(_WORD *)(v5 + 64) == 49 )
    {
      v6 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
      v7 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v5 + 40), v5, 0, 1, 0);
      if ( v7 >= 0 )
      {
        v8 = Smb2VerifyFileEx(BugCheckParameter4);
        if ( v8 >= 0 )
          goto LABEL_5;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v9, *(unsigned __int16 *)(v5 + 12), BugCheckParameter4);
        }
        if ( v8 == -1073741528 )
        {
LABEL_5:
          v11 = Smb2VerifyTreeConnect_Old(BugCheckParameter4, *(unsigned int *)(v5 + 36), v5);
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 92, v10, *(unsigned __int16 *)(v5 + 12), BugCheckParameter4);
            }
            goto LABEL_155;
          }
          if ( v8 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 560) + 56LL) + 154LL) )
            *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        }
        if ( v8 >= 0 )
        {
          v12 = 0;
          if ( *(_DWORD *)(*(_QWORD *)(v3 + 56) + 76LL) == 1 )
            v12 = 4;
          v13 = *(_BYTE *)(v3 + 264) & 0xFB | v12;
          v14 = *(_QWORD *)(v3 + 72);
          *(_BYTE *)(v3 + 264) = v13;
          v15 = *(_DWORD *)(v14 + 224);
          if ( (v15 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                13,
                &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                BugCheckParameter4);
            }
            Smb2SetError(
              BugCheckParameter4,
              3221225506LL,
              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
              382);
            return 0;
          }
          *(_BYTE *)(v3 + 264) = v13 ^ (v13 ^ (8 * BYTE1(v15))) & 8;
          *(_BYTE *)(v5 + 67) &= *(_BYTE *)(v6 + 48);
          v16 = *(_BYTE *)(v5 + 67) & 1;
          if ( (*(_BYTE *)(v3 + 264) & 4) != 0 )
          {
            if ( v16 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  14,
                  &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                  BugCheckParameter4);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                414);
              v22 = 2;
              goto LABEL_17;
            }
          }
          else if ( v16 )
          {
            v17 = *(unsigned int *)(v5 + 68);
            v20 = 1;
            v19 = *(_DWORD *)(v5 + 68);
            v18 = 1;
LABEL_27:
            v26 = *(unsigned __int16 *)(*(_QWORD *)(v3 + 72) + 196LL);
            if ( (_WORD)v26 )
            {
              v27 = *(_QWORD *)(v5 + 72);
              if ( ((v26 - 1) & v27) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qid(WPP_GLOBAL_Control->AttachedDevice, v27, v17, BugCheckParameter4, v27, v26);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  451);
                return 0;
              }
              if ( (((_DWORD)v26 - 1) & (unsigned int)v17) != 0 )
              {
                v19 = v17 + v26 - 1 - ((int)v17 + (int)v26 - 1) % (unsigned int)v26;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    16,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v17,
                    v19);
                }
              }
            }
LABEL_14:
            v21 = *(unsigned int *)(v6 + 36);
            if ( v19 > (unsigned int)v21 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) )
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v19,
                    v21);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                487);
              v22 = 4;
LABEL_17:
              Smb2LkmdTelCollectParsingFailureReadHelper(v3, v22);
              return 0;
            }
            v24 = *(_QWORD *)(v5 + 72);
            if ( v24 < 0 || (v25 = v24 + v19, v25 < v24) || v25 > 0x7FFFFFFFFFFFFFFFLL )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qID(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v21, BugCheckParameter4, v24, v19);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                512);
              v22 = 5;
              goto LABEL_17;
            }
            if ( (*(_BYTE *)(v6 + 49) & 2) != 0 )
            {
              v37 = *(_DWORD *)(v5 + 68);
              if ( v37 )
                v18 = ((unsigned int)(v37 - 1) >> 16) + 1;
              v38 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
              if ( v38 < v18 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    19,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v38,
                    v18);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  536);
                v22 = 6;
                goto LABEL_17;
              }
            }
            if ( *(_WORD *)(v6 + 44) < 0x300u )
            {
              *(_DWORD *)(v5 + 100) = 0;
            }
            else
            {
              v28 = *(_DWORD *)(v5 + 100);
              if ( v28 > *(_DWORD *)(v6 + 32) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    20,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v28);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  556);
                v22 = 7;
                goto LABEL_17;
              }
              if ( v28 - 1 <= 1 )
              {
                if ( !(unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 480LL)) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      21,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    586);
                  v22 = 8;
                  goto LABEL_17;
                }
                v32 = *(_DWORD *)(v5 + 68);
                if ( !v32 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      22,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    601);
                  v22 = 9;
                  goto LABEL_17;
                }
                v33 = *(unsigned __int16 *)(v5 + 108);
                if ( !(_WORD)v33 || (v34 = *(unsigned __int16 *)(v5 + 110), !(_WORD)v34) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      23,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    617);
                  v22 = 10;
                  goto LABEL_17;
                }
                v35 = *(unsigned __int16 *)(v5 + 108);
                if ( v33 - 112 > 0x100
                  || (v33 + v34 >= v33
                   && v33 + v34 <= *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL)
                   && (((_BYTE)v5 + (_BYTE)v35) & 7) == 0
                    ? (v36 = 0)
                    : (v36 = -1073741811),
                      v36 < 0) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      24,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    641);
                  v22 = 11;
                  goto LABEL_17;
                }
                if ( (int)SrvNetValidateMrToken(
                            v35 + v5,
                            *(unsigned __int16 *)(v5 + 110),
                            v32,
                            BugCheckParameter4 + 552) < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      25,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    660);
                  v22 = 12;
                  goto LABEL_17;
                }
                v30 = *(unsigned __int16 *)(v5 + 110);
                v29 = v5 + *(unsigned __int16 *)(v5 + 108);
                *(_BYTE *)(BugCheckParameter4 + 556) = *(_DWORD *)(v5 + 100) == 2;
LABEL_36:
                if ( v20 )
                {
                  v31 = *(_BYTE *)(v3 + 264);
                  if ( (v31 & 4) != 0 )
                    goto LABEL_38;
                  v31 |= 2u;
                }
                else
                {
                  v48 = *(_DWORD *)(*(_QWORD *)(v3 + 56) + 84LL);
                  if ( (v48 & 0x4000000) != 0
                    || (v48 & 0x1000000) != 0
                    || (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x200) != 0 )
                  {
                    *(_BYTE *)(v3 + 264) |= 0x22u;
                  }
                  v31 = *(_BYTE *)(v3 + 264);
                  v49 = *(_DWORD *)(v3 + 8);
                  if ( v49 != 1 )
                  {
                    if ( !v29 || v49 < 2 || (*(_DWORD *)(*(_QWORD *)(v3 + 32) + 304LL) & 1) == 0 )
                      goto LABEL_38;
                    v31 = *(_BYTE *)(v3 + 264);
                  }
                  v31 |= 0x20u;
                }
                *(_BYTE *)(v3 + 264) = v31;
LABEL_38:
                *(_DWORD *)(v3 + 236) = v19;
                *(_DWORD *)(v3 + 244) = *(_DWORD *)(v5 + 68);
                *(_DWORD *)(v3 + 240) = *(_DWORD *)(v5 + 96);
                *(_QWORD *)(v3 + 192) = *(_QWORD *)(v5 + 72);
                *(_BYTE *)(v3 + 265) = *(_BYTE *)(v5 + 66);
                *(_QWORD *)(v3 + 200) = 0;
                *(_QWORD *)(v3 + 216) = v29;
                *(_DWORD *)(v3 + 232) = v30;
                *(_BYTE *)(v3 + 264) = (16 * v20) | v31 & 0xEF;
                if ( (*(_BYTE *)(v5 + 67) & 2) != 0 && !Smb2CompressionDisabled )
                  *(_DWORD *)(BugCheckParameter4 + 484) |= 0x2000u;
                if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
                {
                  v39 = *(_QWORD **)(BugCheckParameter4 + 560);
                  v40 = &Srv2ZeroGuid;
                  v41 = v39[9];
                  v42 = (__int64 *)(v41 + 96);
                  if ( !v41 )
                    v42 = &Srv2ZeroGuid;
                  v43 = v39[7];
                  v44 = (__int64 *)(v43 + 24);
                  if ( !v43 )
                    v44 = &Srv2ZeroGuid;
                  v45 = v39[4];
                  if ( v45 )
                    v40 = (__int64 *)(v45 + 72);
                  v46 = *(_QWORD *)(BugCheckParameter4 + 416);
                  if ( v46 )
                    v47 = *(_QWORD *)(*(_QWORD *)(v46 + 560) + 176LL);
                  else
                    LODWORD(v47) = -1;
                  v50 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
                  McTemplateK0xqqxxhhqqxxqqqhhjjjj_EtwWriteTransfer(
                    v50,
                    v47,
                    BugCheckParameter4 + 584,
                    *(_QWORD *)(v5 + 40),
                    *(_DWORD *)(v5 + 32),
                    *(_DWORD *)(v5 + 36),
                    *(_QWORD *)(v5 + 24),
                    v47,
                    *(_WORD *)(v5 + 12),
                    *(_WORD *)(v5 + 14),
                    *(_DWORD *)(v5 + 16),
                    *(_DWORD *)(v5 + 68),
                    *(_QWORD *)(v5 + 72),
                    *(_QWORD *)(v5 + 80),
                    *(_DWORD *)(v5 + 96),
                    *(_DWORD *)(v5 + 100),
                    *(_DWORD *)(v5 + 104),
                    *(_WORD *)(v5 + 108),
                    *(_WORD *)(v5 + 110),
                    v50,
                    (__int64)v40,
                    (__int64)v44,
                    (__int64)v42);
                }
                if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 480LL))
                  && (*(_BYTE *)(v3 + 264) & 4) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x40) == 0 )
                {
                  *(_BYTE *)(v3 + 7) = 1;
                  _InterlockedIncrement((volatile signed __int32 *)(v6 + 196));
                }
                return 3221225494LL;
              }
            }
            v29 = 0;
            v30 = 0;
            goto LABEL_36;
          }
          v17 = *(unsigned int *)(v5 + 68);
          v18 = 1;
          v19 = *(_DWORD *)(v5 + 68);
          v20 = (*(_DWORD *)(*(_QWORD *)(v3 + 88) + 80LL) & 8) != 0;
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 88) + 80LL) & 8) == 0 )
            goto LABEL_14;
          goto LABEL_27;
        }
        v11 = v8;
LABEL_155:
        Smb2SetError(
          BugCheckParameter4,
          (unsigned int)v11,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
          363);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(
        BugCheckParameter4,
        (unsigned int)v7,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
        350);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", 335);
      Smb2LkmdTelCollectParsingFailureReadHelper(v3, 1);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x140086290  mov     rax, rsp
0x140086293  push    rbx
0x140086294  push    rsi
0x140086295  push    rdi
0x140086296  push    r12
0x140086298  sub     rsp, 0D8h
0x14008629f  mov     rbx, [rcx+130h]
0x1400862a6  mov     rdi, rcx
0x1400862a9  mov     rsi, [rcx+230h]
0x1400862b0  mov     r8d, [rbx+24h]
0x1400862b4  cmp     r8d, 71h ; 'q'
0x1400862b8  jb      loc_140086921
0x1400862be  mov     rbx, [rbx+18h]
0x1400862c2  mov     [rax+10h], r13
0x1400862c6  cmp     word ptr [rbx+40h], 31h ; '1'
0x1400862cb  jnz     loc_140086972
0x1400862d1  mov     rdx, [rbx+28h]
0x1400862d5  xor     r9d, r9d
0x1400862d8  mov     [rax+8], rbp
0x1400862dc  mov     r8, rbx
0x1400862df  mov     [rax-28h], r15
0x1400862e3  mov     rax, [rcx+60h]
0x1400862e7  mov     byte ptr [rsp+0F8h+var_D0], 0
0x1400862ec  mov     byte ptr [rsp+0F8h+var_D8], 1
0x1400862f1  mov     r15, [rax+1F0h]
0x1400862f8  call    Smb2VerifySessionExEx
0x1400862fd  mov     ebp, eax
0x1400862ff  test    eax, eax
0x140086301  js      loc_1400869BE
0x140086307  movups  xmm0, xmmword ptr [rbx+50h]
0x14008630b  mov     r9b, 3
0x14008630e  mov     [rsp+0F8h+arg_10], r14
0x140086316  mov     r8, rbx
0x140086319  lea     rdx, [rsp+0F8h+var_38]
0x140086321  mov     rcx, rdi; BugCheckParameter4
0x140086324  movaps  [rsp+0F8h+var_38], xmm0
0x14008632c  call    Smb2VerifyFileEx
0x140086331  lea     r12, WPP_GLOBAL_Control
0x140086338  mov     ebp, eax
0x14008633a  test    eax, eax
0x14008633c  js      loc_140086A0A
0x140086342  mov     edx, [rbx+24h]
0x140086345  mov     r8, rbx
0x140086348  mov     rcx, rdi
0x14008634b  call    Smb2VerifyTreeConnect_Old
0x140086350  mov     r14d, eax
0x140086353  test    eax, eax
0x140086355  js      loc_140086A4E
0x14008635b  cmp     ebp, 0C0000128h
0x140086361  jz      loc_140086A93
0x140086367  test    ebp, ebp
0x140086369  js      loc_140086AB7
0x14008636f  mov     rax, [rsi+38h]
0x140086373  xor     edx, edx
0x140086375  mov     ecx, 4
0x14008637a  cmp     dword ptr [rax+4Ch], 1
0x14008637e  movzx   eax, byte ptr [rsi+108h]
0x140086385  cmovz   edx, ecx
0x140086388  and     al, 0FBh
0x14008638a  or      dl, al
0x14008638c  mov     rax, [rsi+48h]
0x140086390  mov     [rsi+108h], dl
0x140086396  mov     ecx, [rax+0E0h]
0x14008639c  test    cl, 1
0x14008639f  jz      loc_140086ABF
0x1400863a5  shr     ecx, 8
0x1400863a8  shl     cl, 3
0x1400863ab  xor     cl, dl
0x1400863ad  and     cl, 8
0x1400863b0  xor     cl, dl
0x1400863b2  mov     [rsi+108h], cl
0x1400863b8  movzx   eax, byte ptr [r15+30h]
0x1400863bd  and     [rbx+43h], al
0x1400863c0  movzx   ecx, byte ptr [rbx+43h]
0x1400863c4  and     cl, 1
0x1400863c7  test    byte ptr [rsi+108h], 4
0x1400863ce  jnz     loc_140086B04
0x1400863d4  test    cl, cl
0x1400863d6  jnz     loc_1400864DF
0x1400863dc  mov     rax, [rsi+58h]
0x1400863e0  xor     dl, dl
0x1400863e2  mov     r8d, [rbx+44h]
0x1400863e6  mov     r13d, 1
0x1400863ec  movzx   ebp, dl
0x1400863ef  mov     r14d, r8d
0x1400863f2  mov     ecx, [rax+50h]
0x1400863f5  test    cl, 8
0x1400863f8  cmovnz  ebp, r13d
0x1400863fc  test    bpl, bpl
0x1400863ff  jnz     loc_1400864EF
0x140086405  mov     r8d, [r15+24h]
0x140086409  cmp     r14d, r8d
0x14008640c  jbe     short loc_140086475
0x14008640e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086415  cmp     rcx, r12
0x140086418  jnz     loc_140086B94
0x14008641e  mov     r9d, 1E7h
0x140086424  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14008642b  mov     edx, 0C000000Dh
0x140086430  mov     rcx, rdi
0x140086433  call    _Smb2SetError
0x140086438  mov     edx, 4
0x14008643d  mov     rcx, rsi
0x140086440  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x140086445  xor     eax, eax
0x140086447  mov     r14, [rsp+0F8h+arg_10]
0x14008644f  mov     rbp, [rsp+0F8h+arg_0]
0x140086457  mov     r15, [rsp+0F8h+var_28]
0x14008645f  mov     r13, [rsp+0F8h+arg_8]
0x140086467  add     rsp, 0D8h
0x14008646e  pop     r12
0x140086470  pop     rdi
0x140086471  pop     rsi
0x140086472  pop     rbx
0x140086473  retn
0x140086475  mov     rcx, [rbx+48h]
0x140086479  test    rcx, rcx
0x14008647c  js      short loc_14008649C
0x14008647e  mov     edx, r14d
0x140086481  add     rdx, rcx
0x140086484  cmp     rdx, rcx
0x140086487  jb      short loc_14008649C
0x140086489  mov     rax, 7FFFFFFFFFFFFFFFh
0x140086493  cmp     rdx, rax
0x140086496  jbe     loc_140086528
0x14008649c  mov     rdx, cs:WPP_GLOBAL_Control
0x1400864a3  cmp     rdx, r12
0x1400864a6  jz      loc_14009AE4A
0x1400864ac  test    dword ptr [rdx+2Ch], 800000h
0x1400864b3  jz      loc_14009AE4A
0x1400864b9  cmp     byte ptr [rdx+29h], 1
0x1400864bd  jb      loc_14009AE4A
0x1400864c3  mov     [rsp+0F8h+var_D0], r14d
0x1400864c8  mov     r9, rdi
0x1400864cb  mov     [rsp+0F8h+var_D8], rcx
0x1400864d0  mov     rcx, [rdx+18h]
0x1400864d4  call    WPP_SF_qID
0x1400864d9  nop
0x1400864da  jmp     loc_14009AE4A
0x1400864df  mov     r8d, [rbx+44h]
0x1400864e3  mov     bpl, 1
0x1400864e6  mov     r14d, r8d
0x1400864e9  mov     r13d, 1
0x1400864ef  mov     rax, [rsi+48h]
0x1400864f3  movzx   ecx, word ptr [rax+0C4h]
0x1400864fa  test    cx, cx
0x1400864fd  jz      loc_140086405
0x140086503  mov     rdx, [rbx+48h]
0x140086507  lea     rax, [rcx-1]
0x14008650b  mov     r9d, ecx
0x14008650e  test    rdx, rax
0x140086511  jnz     loc_140086B51
0x140086517  lea     eax, [rcx-1]
0x14008651a  test    r8d, eax
0x14008651d  jz      loc_140086405
0x140086523  jmp     loc_14009ACDB
0x140086528  test    byte ptr [r15+31h], 2
0x14008652d  jnz     loc_1400866E6
0x140086533  mov     eax, 300h
0x140086538  cmp     [r15+2Ch], ax
0x14008653d  jb      loc_140086D64
0x140086543  mov     r8d, [rbx+64h]
0x140086547  cmp     r8d, [r15+20h]
0x14008654b  ja      loc_140086BD2
0x140086551  lea     eax, [r8-1]
0x140086555  cmp     eax, 1
0x140086558  jbe     loc_140086614
0x14008655e  xor     r8d, r8d
0x140086561  xor     r9d, r9d
0x140086564  test    bpl, bpl
0x140086567  jz      loc_140086D78
0x14008656d  movzx   edx, byte ptr [rsi+108h]
0x140086574  test    dl, 4
0x140086577  jz      loc_140086D70
0x14008657d  mov     [rsi+0ECh], r14d
0x140086584  and     dl, 0EFh
0x140086587  mov     eax, [rbx+44h]
0x14008658a  mov     [rsi+0F4h], eax
0x140086590  mov     eax, [rbx+60h]
0x140086593  mov     [rsi+0F0h], eax
0x140086599  mov     rax, [rbx+48h]
0x14008659d  shl     bpl, 4
0x1400865a1  mov     [rsi+0C0h], rax
0x1400865a8  or      dl, bpl
0x1400865ab  movzx   eax, byte ptr [rbx+42h]
0x1400865af  mov     [rsi+109h], al
0x1400865b5  mov     qword ptr [rsi+0C8h], 0
0x1400865c0  mov     [rsi+0D8h], r8
0x1400865c7  mov     [rsi+0E8h], r9d
0x1400865ce  mov     [rsi+108h], dl
0x1400865d4  test    byte ptr [rbx+43h], 2
0x1400865d8  jnz     loc_140086DAC
0x1400865de  test    cs:Microsoft_Windows_SMBServerEnableBits, 1
0x1400865e5  jnz     loc_140086789
0x1400865eb  mov     rcx, [rdi+60h]
0x1400865ef  mov     rcx, [rcx+1E0h]
0x1400865f6  call    cs:__imp_SrvNetIsRdmaConnection
0x1400865fd  nop     dword ptr [rax+rax+00h]
0x140086602  test    al, al
0x140086604  jnz     loc_140086758
0x14008660a  mov     eax, 0C0000016h
0x14008660f  jmp     loc_140086447
0x140086614  mov     rcx, [rdi+60h]
0x140086618  mov     rcx, [rcx+1E0h]
0x14008661f  call    cs:__imp_SrvNetIsRdmaConnection
0x140086626  nop     dword ptr [rax+rax+00h]
0x14008662b  test    al, al
0x14008662d  jz      loc_140086C1C
0x140086633  mov     r11d, [rbx+44h]
0x140086637  test    r11d, r11d
0x14008663a  jz      loc_14008689D
0x140086640  movzx   ecx, word ptr [rbx+6Ch]
0x140086644  xor     eax, eax
0x140086646  cmp     ax, cx
0x140086649  jz      loc_140086D1F
0x14008664f  movzx   r10d, word ptr [rbx+6Eh]
0x140086654  cmp     ax, r10w
0x140086658  jz      loc_140086D1F
0x14008665e  lea     rax, [rcx-70h]
0x140086662  mov     r8d, ecx
0x140086665  cmp     rax, 100h
0x14008666b  ja      loc_140086CDA
0x140086671  lea     rdx, [rcx+r10]
0x140086675  cmp     rdx, rcx
0x140086678  jb      short loc_140086695
0x14008667a  mov     rax, [rdi+130h]
0x140086681  mov     ecx, [rax+24h]
0x140086684  cmp     rdx, rcx
0x140086687  ja      short loc_140086695
0x140086689  lea     eax, [rbx+r8]
0x14008668d  test    al, 7
0x14008668f  jz      loc_1400868D1
0x140086695  mov     eax, 0C000000Dh
0x14008669a  test    eax, eax
0x14008669c  js      loc_140086CDA
0x1400866a2  lea     rcx, [r8+rbx]
0x1400866a6  mov     edx, r10d
0x1400866a9  mov     r8d, r11d
0x1400866ac  lea     r9, [rdi+228h]
0x1400866b3  call    cs:__imp_SrvNetValidateMrToken
0x1400866ba  nop     dword ptr [rax+rax+00h]
0x1400866bf  test    eax, eax
0x1400866c1  js      loc_140086C95
0x1400866c7  movzx   r8d, word ptr [rbx+6Ch]
0x1400866cc  movzx   r9d, word ptr [rbx+6Eh]
0x1400866d1  add     r8, rbx
0x1400866d4  cmp     dword ptr [rbx+64h], 2
0x1400866d8  setz    al
0x1400866db  mov     [rdi+22Ch], al
0x1400866e1  jmp     loc_140086564
0x1400866e6  mov     eax, [rbx+44h]
0x1400866e9  test    eax, eax
0x1400866eb  jz      short loc_1400866F8
0x1400866ed  lea     r13d, [rax-1]
0x1400866f1  shr     r13d, 10h
0x1400866f5  inc     r13d
0x1400866f8  movzx   r8d, word ptr [rdi+1E8h]
0x140086700  cmp     r8d, r13d
0x140086703  jnb     loc_140086533
0x140086709  mov     rcx, cs:WPP_GLOBAL_Control
0x140086710  cmp     rcx, r12
0x140086713  jz      loc_14009AD3C
0x140086719  test    dword ptr [rcx+2Ch], 800000h
0x140086720  jz      loc_14009AD3C
0x140086726  cmp     byte ptr [rcx+29h], 1
0x14008672a  jb      loc_14009AD3C
0x140086730  mov     rcx, [rcx+18h]
0x140086734  mov     edx, 13h
0x140086739  mov     [rsp+0F8h+var_D0], r13d
0x14008673e  mov     r9, rdi
0x140086741  mov     dword ptr [rsp+0F8h+var_D8], r8d
0x140086746  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14008674d  call    WPP_SF_qDD
0x140086752  nop
0x140086753  jmp     loc_14009AD3C
0x140086758  test    byte ptr [rsi+108h], 4
0x14008675f  jnz     loc_14008660A
0x140086765  mov     rax, [rsi+48h]
0x140086769  mov     ecx, [rax+0E0h]
0x14008676f  test    cl, 40h
0x140086772  jnz     loc_14008660A
0x140086778  mov     byte ptr [rsi+7], 1
0x14008677c  lock inc dword ptr [r15+0C4h]
0x140086784  jmp     loc_14008660A
0x140086789  mov     rax, [rdi+230h]
0x140086790  lea     r9, Srv2ZeroGuid
0x140086797  mov     rcx, [rax+48h]
0x14008679b  lea     r11, [rcx+60h]
0x14008679f  test    rcx, rcx
0x1400867a2  jnz     short loc_1400867A7
0x1400867a4  mov     r11, r9
0x1400867a7  mov     rcx, [rax+38h]
0x1400867ab  lea     r10, [rcx+18h]
0x1400867af  test    rcx, rcx
0x1400867b2  jnz     short loc_1400867B7
0x1400867b4  mov     r10, r9
0x1400867b7  mov     rcx, [rax+20h]
0x1400867bb  test    rcx, rcx
0x1400867be  jnz     loc_140086DC8
0x1400867c4  mov     rax, [rdi+1A0h]
  ... truncated ...
```

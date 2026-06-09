# VsmUtils::Seal(uchar *,uint,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uint *)

- ea: `0x14005833c`
- end: `0x1400589b4`
- name: `?Seal@VsmUtils@@YAJPEAEIW4TpmAuthType@1@0I0IPEAI@Z`
- size: `1656`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140048a24`

## callees

- `0x140007410`
- `0x14000e034`
- `0x1400154b8`
- `0x14002bdcc`
- `0x140055164`
- `0x140055470`
- `0x140057f5c`
- `0x14005833c`
- `0x14005ac70`
- `0x14005be04`
- `0x14005c5c4`
- `0x1400604d8`
- `0x140060550`
- `0x1400606a4`
- `0x140060e24`
- `0x140061684`
- `0x140061fb0`
- `0x1400624d4`
- `0x140062520`
- `0x140065c28`
- `0x140067784`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005875d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400588ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005892b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005875d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400588ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x14005892b`

## string_xrefs

- `0x140058477`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400584fc`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005856f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058738`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005878b`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400587fc`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400588c7`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005894d`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058986`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall VsmUtils::Seal(
        const unsigned __int8 *a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        void *a6,
        unsigned int DestinationSize,
        unsigned int *a8)
{
  struct VsmUtils::TpmSessionKey *v11; // rax
  int RsaSRKName; // eax
  struct tpm12class::TPMW82B_BUFFER *v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  struct tpm12class::TPMW82B_BUFFER *v19; // r8
  unsigned __int8 v20; // r9
  unsigned int v21; // eax
  int v22; // edx
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  unsigned int v26; // r15d
  __int16 v27; // r14
  unsigned int v28; // esi
  unsigned int v29; // ebx
  int v30; // eax
  int v31; // edi
  HLOCAL v32; // rcx
  unsigned int v33; // r8d
  HLOCAL v34; // rcx
  unsigned int v35; // esi
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // esi
  HLOCAL v40; // rcx
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v45; // [rsp+5Ch] [rbp-A4h]
  unsigned int v46; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v47; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v48; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v49[3]; // [rsp+70h] [rbp-90h] BYREF
  int v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  char v53; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v54; // [rsp+A8h] [rbp-58h]
  unsigned __int8 *v55; // [rsp+B0h] [rbp-50h]
  void *Destination; // [rsp+C0h] [rbp-40h]
  _BYTE v57[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v58[168]; // [rsp+120h] [rbp+20h] BYREF
  VsmUtils *v59; // [rsp+1C8h] [rbp+C8h]
  int v60; // [rsp+1E8h] [rbp+E8h]
  _BYTE v61[72]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v62; // [rsp+238h] [rbp+138h]
  __int64 v63; // [rsp+240h] [rbp+140h]
  _BYTE v64[72]; // [rsp+2D8h] [rbp+1D8h] BYREF
  tpm12class::TpmDataObject *v65; // [rsp+320h] [rbp+220h]
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  Destination = a6;
  g_fpW8TpmSubmit = WinPlatformW8TbsSubmit;
  g_fpGetRandom = (int (*)(unsigned __int8 *, unsigned int))WinPlatformGetRandom;
  g_fpHash = (int (*)(unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))WinPlatformHash;
  g_fpRsaEncrypt = (int (*)(struct _BCRYPT_RSAKEY_BLOB *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int16, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *))WinPlatformRsaEncryptWorker;
  g_fpAesCfbEncrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbEncrypt;
  g_fpAesCfbDecrypt = (int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))WinPlatformAesCfbDecrypt;
  if ( !a1 || a2 - 1 > 0x7F || !a4 || a5 - 1 > 0x3FF || !a8 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x476,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80070057LL,
      v42);
    return v14;
  }
  v45 = 256;
  v11 = VsmUtils::TpmSessionKey::Instance();
  SetTbsHandle(*((_QWORD *)v11 + 1));
  tpm12class::TPMW8_Create::TPMW8_Create((tpm12class::TPMW8_Create *)v58);
  RsaSRKName = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)(v62 + 136), a1, a2);
  v14 = RsaSRKName;
  if ( RsaSRKName >= 0 )
  {
    v60 = -2130706431;
    RsaSRKName = VsmUtils::GetRsaSRKName((VsmUtils *)v61, v13);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1175;
      goto LABEL_10;
    }
    *(_WORD *)(v63 + 56) = 8;
    *(_WORD *)(v63 + 58) = 11;
    *(_DWORD *)(v63 + 60) = 18;
    v49[1] = 0;
    v49[2] = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v49[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v54 = 0;
    v55 = 0;
    v16 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v49, 0x20u);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 1185;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v16,
        v42);
LABEL_14:
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v49);
      goto LABEL_60;
    }
    v46 = 0;
    v18 = PlatformHash(L"SHA256", a4, a5, 0, 0, v55, v54, &v46, 0);
    if ( v18 < 0 )
    {
      v14 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x4A5,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v18,
              v42);
      goto LABEL_14;
    }
    v54 = v46;
    *(_DWORD *)(v63 + 60) |= 0x40u;
    v16 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)(v62 + 64),
            (const struct tpm12class::TPMW82B_BUFFER *)v49);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 1194;
      goto LABEL_13;
    }
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v49);
    LOBYTE(v19) = 32;
    RsaSRKName = VsmUtils::AddSecureSession(v59, 0, v19, v20);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1307;
      goto LABEL_10;
    }
    *(_WORD *)(v63 + 688) = 16;
    RsaSRKName = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)(v63 + 760), 0x20u);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1310;
      goto LABEL_10;
    }
    v21 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v58, 0);
    RsaSRKName = VsmUtils::MapTpmError((VsmUtils *)v21, v22);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1312;
      goto LABEL_10;
    }
    v48 = 0;
    RsaSRKName = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v64, 0, 0, &v48);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1316;
      goto LABEL_10;
    }
    v47 = 0;
    RsaSRKName = tpm12class::TpmDataObject::Get(v65, 0, 0, &v47);
    v14 = RsaSRKName;
    if ( RsaSRKName < 0 )
    {
      v15 = 1319;
      goto LABEL_10;
    }
    tpm12class::TPMW8L_DIGEST::TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v57);
    v44 = 0;
    v23 = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v57, 0, 0, &v44);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = (unsigned int)v23;
      v25 = 1323;
LABEL_59:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)v24,
        v42);
      tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v57);
      goto LABEL_60;
    }
    v26 = v44;
    v27 = v47;
    v28 = v48;
    v29 = v44 + v47 + v48 + 6;
    if ( !a6 || DestinationSize < v29 )
    {
      v14 = -2146893784;
      v24 = 2148073512LL;
      v25 = 1328;
      goto LABEL_59;
    }
    wil::make_unique_hlocal<unsigned char [0]>(&hMem, v29);
    v44 = 0;
    v30 = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v64, (unsigned __int8 *)hMem, v29, &v44);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53A,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v30,
        v42);
      v32 = hMem;
      hMem = 0;
LABEL_35:
      if ( v32 )
        LocalFree(v32);
      tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v57);
      v14 = v31;
      goto LABEL_60;
    }
    v33 = v44;
    if ( v44 > v28 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53C,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)0x80090020LL,
        v42);
      v34 = hMem;
      hMem = 0;
LABEL_52:
      if ( v34 )
        LocalFree(v34);
      tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v57);
      v14 = -2146893792;
      goto LABEL_60;
    }
    *((_BYTE *)hMem + v44) = HIBYTE(v27);
    *((_BYTE *)hMem + v33 + 1) = v27;
    v35 = v33 + 2;
    v31 = tpm12class::TpmDataObject::Get(v65, (unsigned __int8 *)hMem + v35, v29 - v35, &v44);
    if ( v31 < 0 )
    {
      v36 = 1353;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v31,
        v42);
      v32 = hMem;
      hMem = 0;
      goto LABEL_35;
    }
    if ( v44 <= v29 )
    {
      v38 = v35 + v44;
      *((_BYTE *)hMem + v38) = HIBYTE(v26);
      *((_BYTE *)hMem + (unsigned int)(v38 + 1)) = BYTE2(v26);
      *((_BYTE *)hMem + (unsigned int)(v38 + 2)) = BYTE1(v26);
      *((_BYTE *)hMem + (unsigned int)(v38 + 3)) = v26;
      v39 = v38 + 4;
      v31 = tpm12class::TpmDataObject::Get(
              (tpm12class::TpmDataObject *)v57,
              (unsigned __int8 *)hMem + v39,
              v29 - v39,
              &v44);
      if ( v31 < 0 )
      {
        v36 = 1368;
        goto LABEL_42;
      }
      if ( v44 <= v29 )
      {
        if ( v39 + v44 == v29 )
        {
          memcpy_s_0(Destination, DestinationSize, hMem, v29);
          *a8 = v29;
          v40 = hMem;
          hMem = 0;
          if ( v40 )
            LocalFree(v40);
          tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((tpm12class::TPMW8L_DIGEST *)v57);
          v14 = 0;
          goto LABEL_60;
        }
        v37 = 1374;
      }
      else
      {
        v37 = 1370;
      }
    }
    else
    {
      v37 = 1355;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80090020LL,
      v42);
    v34 = hMem;
    hMem = 0;
    goto LABEL_52;
  }
  v15 = 1172;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
    (const char *)(unsigned int)RsaSRKName,
    v42);
LABEL_60:
  tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v58);
  return v14;
}

```

## disassembly

```asm
0x14005833c  mov     [rsp-8+arg_10], rbx
0x140058341  push    rbp
0x140058342  push    rsi
0x140058343  push    rdi
0x140058344  push    r12
0x140058346  push    r13
0x140058348  push    r14
0x14005834a  push    r15
0x14005834c  lea     rbp, [rsp-280h]
0x140058354  sub     rsp, 380h
0x14005835b  mov     rsi, r9
0x14005835e  mov     ebx, edx
0x140058360  mov     r14, rcx
0x140058363  mov     r12, [rbp+2B0h+arg_28]
0x14005836a  mov     [rbp+2B0h+Destination], r12
0x14005836e  mov     r13, [rbp+2B0h+arg_38]
0x140058375  lea     rax, ?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z; WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)
0x14005837c  mov     cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA, rax; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x140058383  lea     rax, ?WinPlatformGetRandom@@YAJPEAEI@Z; WinPlatformGetRandom(uchar *,uint)
0x14005838a  mov     cs:?g_fpGetRandom@@3P6AJPEAEI@ZEA, rax; long (*g_fpGetRandom)(uchar *,uint)
0x140058391  lea     rax, ?WinPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; WinPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x140058398  mov     cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA, rax; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14005839f  lea     rax, ?WinPlatformRsaEncryptWorker@@YAJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@Z; WinPlatformRsaEncryptWorker(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x1400583a6  mov     cs:?g_fpRsaEncrypt@@3P6AJPEAU_BCRYPT_RSAKEY_BLOB@@KPEAEIG1I1IPEAI@ZEA, rax; long (*g_fpRsaEncrypt)(_BCRYPT_RSAKEY_BLOB *,ulong,uchar *,uint,ushort,uchar *,uint,uchar *,uint,uint *)
0x1400583ad  lea     rax, ?WinPlatformAesCfbEncrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbEncrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400583b4  mov     cs:?g_fpAesCfbEncrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbEncrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400583bb  lea     rax, ?WinPlatformAesCfbDecrypt@@YAJPEAEI0I0I0@Z; WinPlatformAesCfbDecrypt(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400583c2  mov     cs:?g_fpAesCfbDecrypt@@3P6AJPEAEI0I0I0@ZEA, rax; long (*g_fpAesCfbDecrypt)(uchar *,uint,uchar *,uint,uchar *,uint,uchar *)
0x1400583c9  xor     r15d, r15d
0x1400583cc  test    rcx, rcx
0x1400583cf  jz      loc_140058977
0x1400583d5  lea     eax, [rbx-1]
0x1400583d8  cmp     eax, 7Fh
0x1400583db  ja      loc_140058977
0x1400583e1  test    r9, r9
0x1400583e4  jz      loc_140058977
0x1400583ea  mov     edi, [rbp+2B0h+arg_20]
0x1400583f0  lea     eax, [rdi-1]
0x1400583f3  cmp     eax, 3FFh
0x1400583f8  ja      loc_140058977
0x1400583fe  test    r13, r13
0x140058401  jz      loc_140058977
0x140058407  mov     [rsp+3B0h+var_354], 100h
0x14005840e  call    ?Instance@TpmSessionKey@VsmUtils@@SAAEAV12@XZ; VsmUtils::TpmSessionKey::Instance(void)
0x140058413  mov     rcx, [rax+8]; unsigned __int64
0x140058417  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x14005841c  lea     rcx, [rbp+2B0h+var_290]; this
0x140058420  call    ??0TPMW8_Create@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Create::TPMW8_Create(void)
0x140058425  nop
0x140058426  mov     r8d, ebx; unsigned __int64
0x140058429  mov     rcx, [rbp+2B0h+var_178]
0x140058430  add     rcx, 88h; this
0x140058437  mov     rdx, r14; unsigned __int8 *
0x14005843a  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005843f  mov     ebx, eax
0x140058441  test    eax, eax
0x140058443  jns     short loc_14005844C
0x140058445  mov     edx, 494h
0x14005844a  jmp     short loc_14005846D
0x14005844c  mov     [rbp+2B0h+var_1C8], 81000001h
0x140058456  lea     rcx, [rbp+2B0h+var_1C0]; this
0x14005845d  call    ?GetRsaSRKName@VsmUtils@@YAJPEAVTPMW82B_BUFFER@tpm12class@@@Z; VsmUtils::GetRsaSRKName(tpm12class::TPMW82B_BUFFER *)
0x140058462  mov     ebx, eax
0x140058464  test    eax, eax
0x140058466  jns     short loc_140058488
0x140058468  mov     edx, 497h; void *
0x14005846d  mov     rcx, [rbp+2B8h]; this
0x140058474  mov     r9d, eax; char *
0x140058477  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005847e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058483  jmp     loc_14005896B
0x140058488  mov     rax, [rbp+2B0h+var_170]
0x14005848f  mov     word ptr [rax+38h], 8
0x140058495  mov     rax, [rbp+2B0h+var_170]
0x14005849c  mov     word ptr [rax+3Ah], 0Bh
0x1400584a2  mov     rax, [rbp+2B0h+var_170]
0x1400584a9  mov     dword ptr [rax+3Ch], 12h
0x1400584b0  mov     [rsp+3B0h+var_338], r15
0x1400584b5  mov     [rbp+2B0h+var_330], r15
0x1400584b9  mov     [rbp+2B0h+var_328], r15d
0x1400584bd  mov     [rbp+2B0h+var_320], r15
0x1400584c1  mov     [rbp+2B0h+var_318], r15
0x1400584c5  mov     [rbp+2B0h+var_310], r15b
0x1400584c9  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x1400584d0  mov     [rsp+3B0h+var_340], rax
0x1400584d5  mov     [rbp+2B0h+var_308], r15w
0x1400584da  mov     [rbp+2B0h+var_300], r15
0x1400584de  mov     r14d, 20h ; ' '
0x1400584e4  mov     edx, r14d; unsigned __int64
0x1400584e7  lea     rcx, [rsp+3B0h+var_340]; this
0x1400584ec  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x1400584f1  mov     ebx, eax
0x1400584f3  test    eax, eax
0x1400584f5  jns     short loc_140058522
0x1400584f7  mov     edx, 4A1h; void *
0x1400584fc  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058503  mov     r9d, eax; char *
0x140058506  mov     rcx, [rbp+2B8h]; this
0x14005850d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058512  nop
0x140058513  lea     rcx, [rsp+3B0h+var_340]; this
0x140058518  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005851d  jmp     loc_14005896B
0x140058522  mov     [rsp+3B0h+var_350], r15d
0x140058527  movzx   eax, [rbp+2B0h+var_308]
0x14005852b  mov     [rsp+3B0h+var_370], r15d; unsigned int
0x140058530  lea     rcx, [rsp+3B0h+var_350]
0x140058535  mov     [rsp+3B0h+var_378], rcx; unsigned int *
0x14005853a  mov     [rsp+3B0h+var_380], eax; unsigned int
0x14005853e  mov     rax, [rbp+2B0h+var_300]
0x140058542  mov     [rsp+3B0h+var_388], rax; unsigned __int8 *
0x140058547  mov     [rsp+3B0h+var_390], r15d; int
0x14005854c  xor     r9d, r9d; unsigned __int8 *
0x14005854f  mov     r8d, edi; unsigned int
0x140058552  mov     rdx, rsi; unsigned __int8 *
0x140058555  lea     rcx, aSha256; "SHA256"
0x14005855c  call    ?PlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z; PlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x140058561  test    eax, eax
0x140058563  jns     short loc_140058584
0x140058565  mov     rcx, [rbp+2B8h]; this
0x14005856c  mov     r9d, eax; char *
0x14005856f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058576  mov     edx, 4A5h; void *
0x14005857b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058580  mov     ebx, eax
0x140058582  jmp     short loc_140058513
0x140058584  movzx   eax, word ptr [rsp+3B0h+var_350]
0x140058589  mov     [rbp+2B0h+var_308], ax
0x14005858d  mov     rax, [rbp+2B0h+var_170]
0x140058594  or      dword ptr [rax+3Ch], 40h
0x140058598  mov     rcx, [rbp+2B0h+var_178]
0x14005859f  add     rcx, 40h ; '@'; this
0x1400585a3  lea     rdx, [rsp+3B0h+var_340]; struct tpm12class::TPMW82B_BUFFER *
0x1400585a8  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1400585ad  mov     ebx, eax
0x1400585af  test    eax, eax
0x1400585b1  jns     short loc_1400585BD
0x1400585b3  mov     edx, 4AAh
0x1400585b8  jmp     loc_1400584FC
0x1400585bd  lea     rcx, [rsp+3B0h+var_340]; this
0x1400585c2  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400585c7  mov     r8b, r14b; struct tpm12class::TPMW82B_BUFFER *
0x1400585ca  xor     edx, edx; struct tpm12class::TPMW8_SESSION *
0x1400585cc  mov     rcx, [rbp+2B0h+var_1E8]; this
0x1400585d3  call    ?AddSecureSession@VsmUtils@@YAJPEAVTPMW8_SESSION@tpm12class@@PEAVTPMW82B_BUFFER@3@E@Z; VsmUtils::AddSecureSession(tpm12class::TPMW8_SESSION *,tpm12class::TPMW82B_BUFFER *,uchar)
0x1400585d8  mov     ebx, eax
0x1400585da  test    eax, eax
0x1400585dc  jns     short loc_1400585E8
0x1400585de  mov     edx, 51Bh
0x1400585e3  jmp     loc_14005846D
0x1400585e8  mov     rax, [rbp+2B0h+var_170]
0x1400585ef  mov     word ptr [rax+2B0h], 10h
0x1400585f8  mov     rcx, [rbp+2B0h+var_170]
0x1400585ff  add     rcx, 2F8h; this
0x140058606  mov     rdx, r14; unsigned __int64
0x140058609  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x14005860e  mov     ebx, eax
0x140058610  test    eax, eax
0x140058612  jns     short loc_14005861E
0x140058614  mov     edx, 51Eh
0x140058619  jmp     loc_14005846D
0x14005861e  xor     edx, edx; void *
0x140058620  lea     rcx, [rbp+2B0h+var_290]; this
0x140058624  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140058629  mov     ecx, eax; this
0x14005862b  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140058630  mov     ebx, eax
0x140058632  test    eax, eax
0x140058634  jns     short loc_140058640
0x140058636  mov     edx, 520h
0x14005863b  jmp     loc_14005846D
0x140058640  mov     [rsp+3B0h+var_348], r15d
0x140058645  lea     r9, [rsp+3B0h+var_348]; unsigned int *
0x14005864a  xor     r8d, r8d; unsigned int
0x14005864d  xor     edx, edx; unsigned __int8 *
0x14005864f  lea     rcx, [rbp+2B0h+var_D8]; this
0x140058656  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x14005865b  mov     ebx, eax
0x14005865d  test    eax, eax
0x14005865f  jns     short loc_14005866B
0x140058661  mov     edx, 524h
0x140058666  jmp     loc_14005846D
0x14005866b  mov     [rsp+3B0h+var_34C], r15d
0x140058670  lea     r9, [rsp+3B0h+var_34C]; unsigned int *
0x140058675  xor     r8d, r8d; unsigned int
0x140058678  xor     edx, edx; unsigned __int8 *
0x14005867a  mov     rcx, [rbp+2B0h+var_90]; this
0x140058681  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x140058686  mov     ebx, eax
0x140058688  test    eax, eax
0x14005868a  jns     short loc_140058696
0x14005868c  mov     edx, 527h
0x140058691  jmp     loc_14005846D
0x140058696  lea     rcx, [rbp+2B0h+var_2E0]; this
0x14005869a  call    ??0TPMW8L_DIGEST@tpm12class@@QEAA@XZ; tpm12class::TPMW8L_DIGEST::TPMW8L_DIGEST(void)
0x14005869f  nop
0x1400586a0  mov     [rsp+3B0h+var_358], r15d
0x1400586a5  lea     r9, [rsp+3B0h+var_358]; unsigned int *
0x1400586aa  xor     r8d, r8d; unsigned int
0x1400586ad  xor     edx, edx; unsigned __int8 *
0x1400586af  lea     rcx, [rbp+2B0h+var_2E0]; this
0x1400586b3  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x1400586b8  mov     ebx, eax
0x1400586ba  test    eax, eax
0x1400586bc  jns     short loc_1400586CB
0x1400586be  mov     r9d, eax
0x1400586c1  mov     edx, 52Bh
0x1400586c6  jmp     loc_14005894D
0x1400586cb  mov     r15d, [rsp+3B0h+var_358]
0x1400586d0  mov     r14d, [rsp+3B0h+var_34C]
0x1400586d5  lea     eax, [r15+r14]
0x1400586d9  mov     esi, [rsp+3B0h+var_348]
0x1400586dd  lea     ebx, [rsi+6]
0x1400586e0  add     ebx, eax
0x1400586e2  test    r12, r12
0x1400586e5  jz      loc_140058940
0x1400586eb  cmp     dword ptr [rbp+2B0h+DestinationSize], ebx
0x1400586f1  jb      loc_140058940
0x1400586f7  mov     r12d, ebx
0x1400586fa  mov     edx, ebx
0x1400586fc  lea     rcx, [rsp+3B0h+hMem]
0x140058701  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x140058706  nop
0x140058707  mov     [rsp+3B0h+var_358], 0
0x14005870f  lea     r9, [rsp+3B0h+var_358]; unsigned int *
0x140058714  mov     r8d, ebx; unsigned int
0x140058717  mov     rdx, [rsp+3B0h+hMem]; unsigned __int8 *
0x14005871c  lea     rcx, [rbp+2B0h+var_D8]; this
0x140058723  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x140058728  mov     edi, eax
0x14005872a  test    eax, eax
0x14005872c  jns     short loc_140058774
0x14005872e  mov     rcx, [rbp+2B8h]; this
0x140058735  mov     r9d, eax; char *
0x140058738  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005873f  mov     edx, 53Ah; void *
0x140058744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058749  nop
0x14005874a  mov     rcx, [rsp+3B0h+hMem]; hMem
0x14005874f  mov     [rsp+3B0h+hMem], 0
0x140058758  test    rcx, rcx
0x14005875b  jz      short loc_140058764
0x14005875d  call    cs:__imp_LocalFree
0x140058763  nop
0x140058764  lea     rcx, [rbp+2B0h+var_2E0]; this
0x140058768  call    ??1TPMW8L_DIGEST@tpm12class@@UEAA@XZ; tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST(void)
0x14005876d  mov     ebx, edi
0x14005876f  jmp     loc_14005896B
0x140058774  mov     r8d, [rsp+3B0h+var_358]
0x140058779  cmp     r8d, esi
0x14005877c  jbe     short loc_1400587B0
0x14005877e  mov     rcx, [rbp+2B8h]; this
0x140058785  mov     r9d, 80090020h; char *
0x14005878b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058792  mov     edx, 53Ch; void *
0x140058797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005879c  nop
0x14005879d  mov     rcx, [rsp+3B0h+hMem]
0x1400587a2  mov     [rsp+3B0h+hMem], 0
0x1400587ab  jmp     loc_1400588E5
0x1400587b0  mov     edx, r14d
0x1400587b3  shr     edx, 8
0x1400587b6  mov     rax, [rsp+3B0h+hMem]
0x1400587bb  mov     [r8+rax], dl
0x1400587bf  lea     ecx, [r8+1]
0x1400587c3  mov     rax, [rsp+3B0h+hMem]
0x1400587c8  mov     [rcx+rax], r14b
0x1400587cc  lea     esi, [r8+2]
0x1400587d0  mov     r8d, ebx
0x1400587d3  sub     r8d, esi; unsigned int
0x1400587d6  mov     edx, esi
0x1400587d8  add     rdx, [rsp+3B0h+hMem]; unsigned __int8 *
0x1400587dd  lea     r9, [rsp+3B0h+var_358]; unsigned int *
0x1400587e2  mov     rcx, [rbp+2B0h+var_90]; this
0x1400587e9  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x1400587ee  mov     edi, eax
0x1400587f0  xor     r14d, r14d
0x1400587f3  test    eax, eax
0x1400587f5  jns     short loc_140058822
0x1400587f7  mov     edx, 549h; void *
0x1400587fc  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058803  mov     r9d, edi; char *
0x140058806  mov     rcx, [rbp+2B8h]; this
0x14005880d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058812  nop
0x140058813  mov     rcx, [rsp+3B0h+hMem]
0x140058818  mov     [rsp+3B0h+hMem], r14
0x14005881d  jmp     loc_140058758
0x140058822  mov     eax, [rsp+3B0h+var_358]
0x140058826  cmp     eax, ebx
0x140058828  jbe     short loc_140058834
0x14005882a  mov     edx, 54Bh
0x14005882f  jmp     loc_1400588C1
0x140058834  lea     r8d, [rsi+rax]
0x140058838  mov     edx, r15d
0x14005883b  shr     edx, 18h
0x14005883e  mov     rax, [rsp+3B0h+hMem]
0x140058843  mov     [r8+rax], dl
0x140058847  mov     edx, r15d
0x14005884a  shr     edx, 10h
  ... truncated ...
```

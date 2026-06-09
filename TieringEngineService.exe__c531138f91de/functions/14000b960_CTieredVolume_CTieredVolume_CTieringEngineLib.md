# CTieredVolume::CTieredVolume(CTieringEngineLib *)

- ea: `0x14000b960`
- end: `0x14000be5a`
- name: `??0CTieredVolume@@QEAA@PEAVCTieringEngineLib@@@Z`
- size: `1274`
- prototype: `CTieredVolume *__fastcall(CTieredVolume *__hidden this, struct CTieringEngineLib *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000761c`

## callees

- `0x14000271c`
- `0x140004e44`
- `0x140004ef0`
- `0x140005420`
- `0x140005680`
- `0x14000568c`
- `0x140009f1c`
- `0x14000b960`
- `0x140017b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be2a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000bca6`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x14000bca6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000bd42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000bd60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000bd42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000bd60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000bd12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000bd12`

## pseudocode

```c
CTieredVolume *__fastcall CTieredVolume::CTieredVolume(CTieredVolume *this, struct CTieringEngineLib *a2)
{
  struct _UNICODE_STRING v4; // xmm0
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  HANDLE EventW; // rbx
  HANDLE v7; // rax
  signed int v9; // eax
  int v10; // eax
  signed int LastError; // eax
  int v12; // eax
  signed int v13; // eax
  int v14; // eax
  _BYTE v15[56]; // [rsp+30h] [rbp-38h] BYREF

  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 10;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 10;
  v4 = NullUnicodeString;
  *((struct _UNICODE_STRING *)this + 9) = NullUnicodeString;
  *(_DWORD *)((char *)this + 162) = 0;
  *((_WORD *)this + 83) = 0;
  *((_DWORD *)this + 46) = 1;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((struct _UNICODE_STRING *)this + 37) = v4;
  *((_QWORD *)this + 76) = 0;
  *(struct _UNICODE_STRING *)((char *)this + 616) = v4;
  *((_QWORD *)this + 79) = 0;
  *((struct _UNICODE_STRING *)this + 40) = v4;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((struct _UNICODE_STRING *)this + 42) = v4;
  *((_QWORD *)this + 86) = 0;
  *(struct _UNICODE_STRING *)((char *)this + 696) = v4;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_WORD *)this + 364) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_DWORD *)this + 200) = -1;
  *((_DWORD *)this + 201) = -1;
  *((_QWORD *)this + 101) = 0;
  *((struct _UNICODE_STRING *)this + 51) = v4;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((struct _UNICODE_STRING *)this + 53) = v4;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 109) = 0;
  *((struct _UNICODE_STRING *)this + 55) = v4;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_DWORD *)this + 250) = 0;
  `eh vector constructor iterator'(
    (char *)this + 1008,
    0x30u,
    2u,
    ATL::CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::`default constructor closure',
    ATL::CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::~CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>);
  *((_QWORD *)this + 140) = (char *)this + 48 * *((unsigned int *)this + 250) + 1008;
  *((_BYTE *)this + 1136) = 0;
  *((_BYTE *)this + 1152) = 0;
  *((_BYTE *)this + 1168) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_BYTE *)this + 1192) = 0;
  *((_BYTE *)this + 1224) = 0;
  *((_DWORD *)this + 314) = 0;
  *((_WORD *)this + 630) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_QWORD *)this + 161) = 0;
  *((_QWORD *)this + 162) = 0;
  *((_BYTE *)this + 1332) = 0;
  *((_DWORD *)this + 334) = 0;
  *((_BYTE *)this + 1340) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_BYTE *)this + 1352) = 0;
  *((_BYTE *)this + 1384) = 0;
  *((_DWORD *)this + 354) = 0;
  *((_WORD *)this + 710) = 0;
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_BYTE *)this + 1492) = 0;
  *((_DWORD *)this + 374) = 0;
  *((_BYTE *)this + 1500) = 0;
  *((_QWORD *)this + 188) = 0;
  *((_BYTE *)this + 1512) = 0;
  *((_BYTE *)this + 1544) = 0;
  *((_DWORD *)this + 394) = 0;
  *((_WORD *)this + 790) = 0;
  *((_QWORD *)this + 198) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_BYTE *)this + 1652) = 0;
  *((_DWORD *)this + 414) = 0;
  *((_BYTE *)this + 1660) = 0;
  *((_BYTE *)this + 1672) = 0;
  *(_QWORD *)((char *)this + 1676) = 0;
  *((_QWORD *)this + 211) = this;
  *((_QWORD *)this + 212) = -1;
  *((_QWORD *)this + 213) = -1;
  *((_QWORD *)this + 214) = -1;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::CTieredVolume";
  CHResultImp::CHResultImp((CHResultImp *)v15);
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 208) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, this);
  }
  InitializeSRWLock((PSRWLOCK)this + 3);
  *((_OWORD *)this + 69) = 0;
  *((_QWORD *)this + 141) = (char *)this + 1104;
  *((_DWORD *)this + 230) = 3;
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_DWORD *)this + 244) = 0;
  *((_DWORD *)this + 245) = 1;
  *((_DWORD *)this + 246) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 124) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CHResultImp::operator=(v15, (unsigned int)LastError);
    v12 = CHResultImp::operator long(v15);
    ATL::AtlThrowImpl(v12);
  }
  *((_QWORD *)this + 117) = ThreadpoolCleanupGroup;
  *((_QWORD *)this + 118) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    CHResultImp::operator=(v15, (unsigned int)v13);
    v14 = CHResultImp::operator long(v15);
    ATL::AtlThrowImpl(v14);
  }
  v7 = CreateEventW(0, 1, 0, 0);
  if ( !v7 )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    CHResultImp::operator=(v15, (unsigned int)v9);
    v10 = CHResultImp::operator long(v15);
    ATL::AtlThrowImpl(v10);
  }
  *((_QWORD *)this + 96) = EventW;
  *((_QWORD *)this + 97) = v7;
  *((_DWORD *)this + 79) = 4096;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v15);
  return this;
}

```

## disassembly

```asm
0x14000b960  mov     [rsp+arg_0], rcx
0x14000b965  push    rbx
0x14000b966  push    rsi
0x14000b967  push    rdi
0x14000b968  push    r15
0x14000b96a  sub     rsp, 48h
0x14000b96e  mov     rbx, rdx
0x14000b971  mov     rdi, rcx
0x14000b974  xor     esi, esi
0x14000b976  mov     [rcx+20h], rsi
0x14000b97a  mov     [rcx+28h], rsi
0x14000b97e  mov     [rcx+30h], rsi
0x14000b982  mov     [rcx+38h], rsi
0x14000b986  mov     [rcx+40h], rsi
0x14000b98a  mov     dword ptr [rcx+48h], 0Ah
0x14000b991  mov     [rcx+50h], rsi
0x14000b995  mov     [rcx+58h], rsi
0x14000b999  mov     [rcx+60h], rsi
0x14000b99d  mov     [rcx+68h], rsi
0x14000b9a1  mov     [rcx+70h], rsi
0x14000b9a5  mov     dword ptr [rcx+78h], 0Ah
0x14000b9ac  movups  xmm0, cs:?NullUnicodeString@@3U_UNICODE_STRING@@A; _UNICODE_STRING NullUnicodeString
0x14000b9b3  movdqu  xmmword ptr [rcx+90h], xmm0
0x14000b9bb  mov     [rcx+0A2h], esi
0x14000b9c1  mov     [rcx+0A6h], si
0x14000b9c8  mov     dword ptr [rcx+0B8h], 1
0x14000b9d2  mov     [rcx+0C0h], rsi
0x14000b9d9  mov     [rcx+0C8h], rsi
0x14000b9e0  movdqu  xmmword ptr [rcx+250h], xmm0
0x14000b9e8  mov     [rcx+260h], rsi
0x14000b9ef  movdqu  xmmword ptr [rcx+268h], xmm0
0x14000b9f7  mov     [rcx+278h], rsi
0x14000b9fe  movdqu  xmmword ptr [rcx+280h], xmm0
0x14000ba06  mov     [rcx+290h], rsi
0x14000ba0d  mov     [rcx+298h], rsi
0x14000ba14  movdqu  xmmword ptr [rcx+2A0h], xmm0
0x14000ba1c  mov     [rcx+2B0h], rsi
0x14000ba23  movdqu  xmmword ptr [rcx+2B8h], xmm0
0x14000ba2b  mov     [rcx+2C8h], rsi
0x14000ba32  mov     [rcx+2D0h], rsi
0x14000ba39  mov     [rcx+2D8h], si
0x14000ba40  mov     [rcx+2F0h], rsi
0x14000ba47  mov     [rcx+2F8h], rsi
0x14000ba4e  mov     [rcx+300h], rsi
0x14000ba55  mov     [rcx+308h], rsi
0x14000ba5c  or      eax, 0FFFFFFFFh
0x14000ba5f  mov     [rcx+320h], eax
0x14000ba65  mov     [rcx+324h], eax
0x14000ba6b  mov     [rcx+328h], rsi
0x14000ba72  movdqu  xmmword ptr [rcx+330h], xmm0
0x14000ba7a  mov     [rcx+340h], rsi
0x14000ba81  mov     [rcx+348h], rsi
0x14000ba88  movdqu  xmmword ptr [rcx+350h], xmm0
0x14000ba90  mov     [rcx+360h], rsi
0x14000ba97  mov     [rcx+368h], rsi
0x14000ba9e  movdqu  xmmword ptr [rcx+370h], xmm0
0x14000baa6  mov     [rcx+380h], rsi
0x14000baad  mov     [rcx+388h], rsi
0x14000bab4  mov     [rcx+390h], rsi
0x14000babb  mov     [rcx+3E8h], esi
0x14000bac1  add     rcx, 3F0h; void *
0x14000bac8  lea     rax, ??1?$CRBMap@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@QEAA@XZ; ATL::CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::~CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>(void)
0x14000bacf  mov     [rsp+68h+var_48], rax; void (*)(void *)
0x14000bad4  lea     r9, ??_F?$CRBMap@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@QEAAXXZ; void (*)(void *)
0x14000badb  lea     edx, [rsi+30h]; unsigned __int64
0x14000bade  lea     r8d, [rsi+2]; unsigned __int64
0x14000bae2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x14000bae7  mov     eax, [rdi+3E8h]
0x14000baed  add     rax, 15h
0x14000baf1  lea     rcx, [rax+rax*2]
0x14000baf5  shl     rcx, 4
0x14000baf9  add     rcx, rdi
0x14000bafc  mov     [rdi+460h], rcx
0x14000bb03  mov     [rdi+470h], sil
0x14000bb0a  mov     [rdi+480h], sil
0x14000bb11  mov     [rdi+490h], sil
0x14000bb18  mov     [rdi+4A0h], rsi
0x14000bb1f  mov     [rdi+4A8h], sil
0x14000bb26  mov     [rdi+4C8h], sil
0x14000bb2d  mov     [rdi+4E8h], esi
0x14000bb33  mov     [rdi+4ECh], si
0x14000bb3a  mov     [rdi+4F0h], rsi
0x14000bb41  mov     [rdi+4F8h], rsi
0x14000bb48  mov     [rdi+508h], rsi
0x14000bb4f  mov     [rdi+510h], rsi
0x14000bb56  mov     [rdi+534h], sil
0x14000bb5d  mov     [rdi+538h], esi
0x14000bb63  mov     [rdi+53Ch], sil
0x14000bb6a  mov     [rdi+540h], rsi
0x14000bb71  mov     [rdi+548h], sil
0x14000bb78  mov     [rdi+568h], sil
0x14000bb7f  mov     [rdi+588h], esi
0x14000bb85  mov     [rdi+58Ch], si
0x14000bb8c  mov     [rdi+590h], rsi
0x14000bb93  mov     [rdi+598h], rsi
0x14000bb9a  mov     [rdi+5A8h], rsi
0x14000bba1  mov     [rdi+5B0h], rsi
0x14000bba8  mov     [rdi+5D4h], sil
0x14000bbaf  mov     [rdi+5D8h], esi
0x14000bbb5  mov     [rdi+5DCh], sil
0x14000bbbc  mov     [rdi+5E0h], rsi
0x14000bbc3  mov     [rdi+5E8h], sil
0x14000bbca  mov     [rdi+608h], sil
0x14000bbd1  mov     [rdi+628h], esi
0x14000bbd7  mov     [rdi+62Ch], si
0x14000bbde  mov     [rdi+630h], rsi
0x14000bbe5  mov     [rdi+638h], rsi
0x14000bbec  mov     [rdi+648h], rsi
0x14000bbf3  mov     [rdi+650h], rsi
0x14000bbfa  mov     [rdi+674h], sil
0x14000bc01  mov     [rdi+678h], esi
0x14000bc07  mov     [rdi+67Ch], sil
0x14000bc0e  mov     [rdi+688h], sil
0x14000bc15  mov     [rdi+68Ch], rsi
0x14000bc1c  mov     [rdi+698h], rdi
0x14000bc23  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bc27  mov     [rdi+6A0h], rax
0x14000bc2e  mov     [rdi+6A8h], rax
0x14000bc35  mov     [rdi+6B0h], rax
0x14000bc3c  mov     edx, 8
0x14000bc41  mov     rax, gs:58h
0x14000bc4a  mov     rcx, [rax]
0x14000bc4d  lea     rax, aCtieredvolumeC; "CTieredVolume::CTieredVolume"
0x14000bc54  mov     [rdx+rcx], rax
0x14000bc58  lea     rcx, [rsp+68h+var_38]; this
0x14000bc5d  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000bc62  mov     [rdi+10h], rbx
0x14000bc66  mov     [rdi+680h], rsi
0x14000bc6d  lea     r15, WPP_GLOBAL_Control
0x14000bc74  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc7b  cmp     rcx, r15
0x14000bc7e  jz      short loc_14000BCA2
0x14000bc80  test    byte ptr [rcx+1Ch], 1
0x14000bc84  jz      short loc_14000BCA2
0x14000bc86  cmp     byte ptr [rcx+19h], 4
0x14000bc8a  jb      short loc_14000BCA2
0x14000bc8c  lea     edx, [rsi+0Ah]
0x14000bc8f  mov     r9, rdi
0x14000bc92  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000bc99  mov     rcx, [rcx+10h]
0x14000bc9d  call    WPP_SF_q
0x14000bca2  lea     rcx, [rdi+18h]; SRWLock
0x14000bca6  call    cs:__imp_InitializeSRWLock
0x14000bcac  xorps   xmm0, xmm0
0x14000bcaf  movups  xmmword ptr [rdi+450h], xmm0
0x14000bcb6  lea     rax, [rdi+450h]
0x14000bcbd  mov     [rdi+468h], rax
0x14000bcc4  mov     dword ptr [rdi+398h], 3
0x14000bcce  mov     [rdi+3A0h], rsi
0x14000bcd5  mov     [rdi+3A8h], rsi
0x14000bcdc  mov     [rdi+3B0h], rsi
0x14000bce3  mov     [rdi+3B8h], rsi
0x14000bcea  mov     [rdi+3C0h], rsi
0x14000bcf1  mov     [rdi+3C8h], rsi
0x14000bcf8  mov     [rdi+3D0h], esi
0x14000bcfe  mov     dword ptr [rdi+3D4h], 1
0x14000bd08  mov     dword ptr [rdi+3D8h], 48h ; 'H'
0x14000bd12  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14000bd18  mov     [rdi+3E0h], rax
0x14000bd1f  test    rax, rax
0x14000bd22  jz      loc_14000BDFA
0x14000bd28  mov     [rdi+3A8h], rax
0x14000bd2f  mov     [rdi+3B0h], rsi
0x14000bd36  xor     r9d, r9d; lpName
0x14000bd39  xor     r8d, r8d; bInitialState
0x14000bd3c  lea     edx, [r9+1]; bManualReset
0x14000bd40  xor     ecx, ecx; lpEventAttributes
0x14000bd42  call    cs:__imp_CreateEventW
0x14000bd48  mov     rbx, rax
0x14000bd4b  test    rax, rax
0x14000bd4e  jz      loc_14000BE2A
0x14000bd54  xor     r9d, r9d; lpName
0x14000bd57  xor     r8d, r8d; bInitialState
0x14000bd5a  lea     edx, [r9+1]; bManualReset
0x14000bd5e  xor     ecx, ecx; lpEventAttributes
0x14000bd60  call    cs:__imp_CreateEventW
0x14000bd66  test    rax, rax
0x14000bd69  jz      short loc_14000BDC9
0x14000bd6b  mov     [rdi+300h], rbx
0x14000bd72  mov     [rdi+308h], rax
0x14000bd79  mov     r9d, 1000h
0x14000bd7f  mov     [rdi+13Ch], r9d
0x14000bd86  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd8d  cmp     rcx, r15
0x14000bd90  jz      short loc_14000BDB1
0x14000bd92  test    byte ptr [rcx+1Ch], 1
0x14000bd96  jz      short loc_14000BDB1
0x14000bd98  cmp     byte ptr [rcx+19h], 4
0x14000bd9c  jb      short loc_14000BDB1
0x14000bd9e  mov     edx, 0Bh
0x14000bda3  mov     [rsp+68h+var_48], rdi
0x14000bda8  mov     rcx, [rcx+10h]
0x14000bdac  call    WPP_SF_Dq
0x14000bdb1  lea     rcx, [rsp+68h+var_38]; this
0x14000bdb6  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000bdbb  nop
0x14000bdbc  mov     rax, rdi
0x14000bdbf  add     rsp, 48h
0x14000bdc3  pop     r15
0x14000bdc5  pop     rdi
0x14000bdc6  pop     rsi
0x14000bdc7  pop     rbx
0x14000bdc8  retn
0x14000bdc9  call    cs:__imp_GetLastError
0x14000bdcf  nop
0x14000bdd0  test    eax, eax
0x14000bdd2  jle     short loc_14000BDDC
0x14000bdd4  movzx   eax, ax
0x14000bdd7  or      eax, 80070000h
0x14000bddc  mov     edx, eax
0x14000bdde  lea     rcx, [rsp+68h+var_38]
0x14000bde3  call    ??4CHResultImp@@QEAAJJ@Z; CHResultImp::operator=(long)
0x14000bde8  lea     rcx, [rsp+68h+var_38]
0x14000bded  call    ??BCHResultImp@@QEBAJXZ; CHResultImp::operator long(void)
0x14000bdf2  mov     ecx, eax; int
0x14000bdf4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000bdfa  call    cs:__imp_GetLastError
0x14000be00  test    eax, eax
0x14000be02  jle     short loc_14000BE0C
0x14000be04  movzx   eax, ax
0x14000be07  or      eax, 80070000h
0x14000be0c  mov     edx, eax
0x14000be0e  lea     rcx, [rsp+68h+var_38]
0x14000be13  call    ??4CHResultImp@@QEAAJJ@Z; CHResultImp::operator=(long)
0x14000be18  lea     rcx, [rsp+68h+var_38]
0x14000be1d  call    ??BCHResultImp@@QEBAJXZ; CHResultImp::operator long(void)
0x14000be22  mov     ecx, eax; int
0x14000be24  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000be2a  call    cs:__imp_GetLastError
0x14000be30  test    eax, eax
0x14000be32  jle     short loc_14000BE3C
0x14000be34  movzx   eax, ax
0x14000be37  or      eax, 80070000h
0x14000be3c  mov     edx, eax
0x14000be3e  lea     rcx, [rsp+68h+var_38]
0x14000be43  call    ??4CHResultImp@@QEAAJJ@Z; CHResultImp::operator=(long)
0x14000be48  lea     rcx, [rsp+68h+var_38]
0x14000be4d  call    ??BCHResultImp@@QEBAJXZ; CHResultImp::operator long(void)
0x14000be52  mov     ecx, eax; int
0x14000be54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

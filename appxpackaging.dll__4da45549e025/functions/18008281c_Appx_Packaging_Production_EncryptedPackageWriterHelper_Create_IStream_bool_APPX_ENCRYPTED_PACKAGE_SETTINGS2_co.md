# Appx::Packaging::Production::EncryptedPackageWriterHelper::Create(IStream *,bool,APPX_ENCRYPTED_PACKAGE_SETTINGS2 const *,APPX_KEY_INFO const *,IAppxManifestPackageId *,Appx::Packaging::Production::EncryptedPackageWriterHelper * *)

- ea: `0x18008281c`
- end: `0x180082c8a`
- name: `?Create@EncryptedPackageWriterHelper@Production@Packaging@Appx@@SAJPEAUIStream@@_NPEBUAPPX_ENCRYPTED_PACKAGE_SETTINGS2@@PEBUAPPX_KEY_INFO@@PEAUIAppxManifestPackageId@@PEAPEAV1234@@Z`
- size: `1134`
- prototype: `__int64 __usercall@<rax>(struct IStream *this@<rcx>, bool@<dl>, const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *@<r8>, const struct APPX_KEY_INFO *@<r9>, struct IAppxManifestPackageId *, struct Appx::Packaging::Production::EncryptedPackageWriterHelper **)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180081724`
- `0x180082078`

## callees

- `0x1800133fc`
- `0x180017b48`
- `0x180024974`
- `0x18004f810`
- `0x180050ae8`
- `0x18005b194`
- `0x180071f50`
- `0x180082468`
- `0x18008281c`
- `0x18008378c`
- `0x180086f40`
- `0x180087158`
- `0x180087278`
- `0x180088768`
- `0x180088a08`
- `0x1800992c4`
- `0x1800992d0`
- `0x18009d3d0`
- `0x18009d729`
- `0x1800cf858`
- `0x1800edd8c`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180082b89`
- `OLEAUT32!__imp_SysFreeString` at `0x180082bd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180082bef`
- `OLEAUT32!__imp_SysFreeString` at `0x180082b89`
- `OLEAUT32!__imp_SysFreeString` at `0x180082bd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180082bef`

## string_xrefs

- `0x1800828cf`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082943`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800829ac`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082a69`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082ab2`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082b13`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082b74`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082bbc`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082c19`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180082c5e`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Appx::Packaging::Production::EncryptedPackageWriterHelper::Create(
        struct IStream *this,
        char a2,
        const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *a3,
        struct APPX_KEY_INFO *a4,
        struct IAppxManifestPackageId *a5,
        struct Appx::Packaging::Production::EncryptedPackageWriterHelper **a6)
{
  struct APPX_KEY_INFO *v6; // r14
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  unsigned __int64 *v12; // r8
  int StreamCurrentPosition; // ebx
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  int KeyInfo; // eax
  wil::details::in1diag3 *v18; // rcx
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  _QWORD *v21; // r12
  int CipherBlockAlignedSize; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  Appx::Packaging::EncryptedAppxHeader *v25; // rax
  _QWORD *v26; // rsi
  void *v27; // rax
  void *v28; // rbx
  unsigned __int64 v29; // rdx
  int v30; // eax
  unsigned __int64 v31; // rdx
  int v32; // eax
  unsigned __int64 v33; // rdx
  IUri *blockMapHashAlgorithm; // rcx
  int v35; // eax
  unsigned __int64 v36; // rdx
  int v37; // eax
  unsigned __int64 v38; // rdx
  struct IAppxManifestPackageId *v39; // rdx
  int v40; // eax
  unsigned __int64 v41; // rdx
  int v43; // [rsp+20h] [rbp-48h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v45; // [rsp+40h] [rbp-28h] BYREF
  __int64 v46; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  struct APPX_KEY_INFO *v48; // [rsp+C8h] [rbp+60h] BYREF

  v48 = a4;
  bstrString[1] = (BSTR)-2LL;
  v6 = a4;
  v10 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    StreamCurrentPosition = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
      (const char *)0x8007000ELL,
      v43);
    goto LABEL_50;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  v10[4] = 0;
  v10[5] = 0;
  v10[6] = 0;
  v10[7] = 0;
  v10[8] = 0;
  v10[9] = 0;
  v10[10] = 0;
  v10[11] = 0;
  v10[12] = 0;
  v10[13] = 0;
  v10[14] = 0;
  *((_WORD *)v10 + 60) = 0;
  Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=(v10 + 10, this);
  StreamCurrentPosition = Appx::Packaging::GetStreamCurrentPosition(this, (struct IStream *)(v11 + 13), v12);
  v14 = retaddr;
  if ( StreamCurrentPosition >= 0 )
  {
    v11[14] = v11[13];
    if ( (a3->options & 2) != 0 )
      *((_BYTE *)v11 + 121) = 1;
    StreamCurrentPosition = Appx::Packaging::FileNameHelper::Create((struct Appx::Packaging::FileNameHelper **)v11 + 1);
    v14 = retaddr;
    if ( StreamCurrentPosition < 0 )
    {
      v15 = 71;
      goto LABEL_4;
    }
    v45 = 0;
    v46 = 0;
    if ( !v6 )
    {
      KeyInfo = Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(
                  (Appx::Packaging::GlobalDevKeyInfo *)&v45,
                  (const struct APPX_KEY_INFO **)&v48);
      StreamCurrentPosition = KeyInfo;
      v18 = retaddr;
      if ( KeyInfo < 0 )
      {
        v19 = (unsigned int)KeyInfo;
        v20 = 77;
LABEL_13:
        wil::details::in1diag3::_Log_Hr(
          v18,
          (void *)v20,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)v19,
          v43);
LABEL_14:
        Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo((Appx::Packaging::GlobalDevKeyInfo *)&v45);
        goto LABEL_5;
      }
      v6 = v48;
    }
    v21 = v11 + 5;
    CipherBlockAlignedSize = Appx::Packaging::EncryptionProvider::Create(
                               a3->encryptionAlgorithm,
                               a3->options & 1,
                               v6->keyLength,
                               v6->key,
                               (struct Appx::Packaging::EncryptionProvider **)v11 + 5);
    StreamCurrentPosition = CipherBlockAlignedSize;
    v18 = retaddr;
    if ( CipherBlockAlignedSize < 0 )
    {
      v20 = 85;
LABEL_24:
      v19 = (unsigned int)CipherBlockAlignedSize;
      goto LABEL_13;
    }
    v23 = *v21;
    if ( *(_DWORD *)(*v21 + 52LL) != a3->keyLength )
    {
      v24 = 88;
LABEL_20:
      StreamCurrentPosition = -2147024809;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)(unsigned int)StreamCurrentPosition,
        v43);
      goto LABEL_14;
    }
    LODWORD(bstrString[0]) = 0;
    CipherBlockAlignedSize = Appx::Packaging::EncryptionProvider::GetCipherBlockAlignedSize(
                               *(_DWORD *)(v23 + 48),
                               0x10000u,
                               (unsigned int *)bstrString);
    StreamCurrentPosition = CipherBlockAlignedSize;
    v18 = retaddr;
    if ( CipherBlockAlignedSize < 0 )
    {
      v20 = 91;
      goto LABEL_24;
    }
    if ( LODWORD(bstrString[0]) > 0x10000 )
    {
      v24 = 94;
      goto LABEL_20;
    }
    v25 = (Appx::Packaging::EncryptedAppxHeader *)operator new(0xE8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v25 )
      v25 = (Appx::Packaging::EncryptedAppxHeader *)Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader(v25);
    v26 = v11 + 6;
    Common::AutoPtr<Appx::Packaging::EncryptedAppxHeader,&void Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxHeader>(Appx::Packaging::EncryptedAppxHeader *)>::operator=(
      v11 + 6,
      v25);
    if ( !v11[6] )
    {
      StreamCurrentPosition = -2147024882;
      v24 = 98;
      goto LABEL_21;
    }
    *(_DWORD *)(*v26 + 88LL) = *(_DWORD *)(*v21 + 52LL);
    v27 = operator new[](v6->keyIdLength, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v27;
    if ( !v27 )
    {
      StreamCurrentPosition = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)0x8007000ELL,
        v43);
      operator delete(0, v29);
      goto LABEL_14;
    }
    memcpy_0(v27, v6->keyId, v6->keyIdLength);
    v30 = Common::Array<unsigned char,Common::ContainerOperations<unsigned char,unsigned char>,Common::NoKey,Common::ContainerOperations<Common::NoKey,unsigned char>,Common::ArrayOperations<unsigned char,Common::NoKey>>::Add(
            *v26 + 96LL,
            v28);
    StreamCurrentPosition = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)(unsigned int)v30,
        v43);
      operator delete(0, v31);
      goto LABEL_14;
    }
    *(_BYTE *)(*v26 + 128LL) = v6->keyIdLength;
    if ( a2 )
      *(_DWORD *)*v26 = 1212307525;
    v32 = Appx::Packaging::StringHelper::AllocAndCopyString(
            a3->encryptionAlgorithm,
            (unsigned __int16 **)(*v26 + 160LL),
            (unsigned int *)(*v26 + 152LL));
    StreamCurrentPosition = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)(unsigned int)v32,
        v43);
      operator delete(0, v33);
      goto LABEL_14;
    }
    *(_BYTE *)(*v26 + 168LL) = a3->options & 1;
    blockMapHashAlgorithm = a3->blockMapHashAlgorithm;
    if ( blockMapHashAlgorithm )
    {
      bstrString[0] = 0;
      v35 = ((__int64 (__fastcall *)(IUri *, BSTR *))blockMapHashAlgorithm->lpVtbl->GetAbsoluteUri)(
              blockMapHashAlgorithm,
              bstrString);
      StreamCurrentPosition = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v35,
          v43);
        SysFreeString(bstrString[0]);
        operator delete(0, v36);
        goto LABEL_14;
      }
      v37 = Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeBlockMapWriter(
              (Appx::Packaging::Production::EncryptedPackageWriterHelper *)v11,
              bstrString[0]);
      StreamCurrentPosition = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v37,
          v43);
        SysFreeString(bstrString[0]);
        operator delete(0, v38);
        goto LABEL_14;
      }
      SysFreeString(bstrString[0]);
    }
    v39 = a5;
    if ( a5 )
    {
      v40 = Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeVersionNeutralPackageFullName(
              (Appx::Packaging::Production::EncryptedPackageWriterHelper *)v11,
              a5);
      StreamCurrentPosition = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v40,
          v43);
        operator delete(0, v41);
        goto LABEL_14;
      }
    }
    *a6 = (struct Appx::Packaging::Production::EncryptedPackageWriterHelper *)v11;
    operator delete(0, (unsigned __int64)v39);
    Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo((Appx::Packaging::GlobalDevKeyInfo *)&v45);
LABEL_50:
    v16 = 0;
    goto LABEL_51;
  }
  v15 = 63;
LABEL_4:
  wil::details::in1diag3::_Log_Hr(
    v14,
    (void *)v15,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
    (const char *)(unsigned int)StreamCurrentPosition,
    v43);
LABEL_5:
  v16 = v11;
LABEL_51:
  Common::AutoPtrDeallocate<Appx::Packaging::Production::EncryptedPackageWriterHelper>(v16);
  return (unsigned int)StreamCurrentPosition;
}

```

## disassembly

```asm
0x18008281c  mov     [rsp-40h+arg_18], r9
0x180082821  push    rbp
0x180082822  push    rbx
0x180082823  push    rsi
0x180082824  push    rdi
0x180082825  push    r12
0x180082827  push    r13
0x180082829  push    r14
0x18008282b  push    r15
0x18008282d  mov     rbp, rsp
0x180082830  sub     rsp, 68h
0x180082834  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18008283c  mov     r14, r9
0x18008283f  mov     r15, r8
0x180082842  mov     r13b, dl
0x180082845  mov     rbx, rcx
0x180082848  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008284f  mov     ecx, 80h; unsigned __int64
0x180082854  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180082859  mov     rdi, rax
0x18008285c  xor     r12d, r12d
0x18008285f  test    rax, rax
0x180082862  jz      loc_180082C52
0x180082868  mov     [rax], r12
0x18008286b  mov     [rax+8], r12
0x18008286f  mov     [rax+10h], r12
0x180082873  mov     [rax+18h], r12
0x180082877  mov     [rax+20h], r12
0x18008287b  mov     [rax+28h], r12
0x18008287f  mov     [rax+30h], r12
0x180082883  mov     [rax+38h], r12
0x180082887  mov     [rax+40h], r12
0x18008288b  mov     [rax+48h], r12
0x18008288f  mov     [rax+50h], r12
0x180082893  mov     [rax+58h], r12
0x180082897  mov     [rax+60h], r12
0x18008289b  mov     [rax+68h], r12
0x18008289f  mov     [rax+70h], r12
0x1800828a3  mov     [rax+78h], r12w
0x1800828a8  lea     rcx, [rax+50h]
0x1800828ac  mov     rdx, rbx
0x1800828af  call    ??4?$ComPtr@VManifestComparisonHelper@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@PEAVManifestComparisonHelper@Packaging@Appx@@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=(Appx::Packaging::ManifestComparisonHelper *)
0x1800828b4  lea     rdx, [rdi+68h]; struct IStream *
0x1800828b8  mov     rcx, rbx; this
0x1800828bb  call    ?GetStreamCurrentPosition@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamCurrentPosition(IStream *,unsigned __int64 *)
0x1800828c0  mov     ebx, eax
0x1800828c2  mov     rcx, [rbp+40h]; this
0x1800828c6  test    eax, eax
0x1800828c8  jns     short loc_1800828E6
0x1800828ca  lea     edx, [r12+3Fh]; void *
0x1800828cf  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x1800828d6  mov     r9d, ebx; char *
0x1800828d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800828de  mov     rcx, rdi
0x1800828e1  jmp     loc_180082C71
0x1800828e6  mov     rax, [rdi+68h]
0x1800828ea  mov     [rdi+70h], rax
0x1800828ee  test    byte ptr [r15+18h], 2
0x1800828f3  jz      short loc_1800828F9
0x1800828f5  mov     byte ptr [rdi+79h], 1
0x1800828f9  lea     rcx, [rdi+8]; struct Appx::Packaging::FileNameHelper **
0x1800828fd  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x180082902  mov     ebx, eax
0x180082904  mov     rcx, [rbp+40h]
0x180082908  test    eax, eax
0x18008290a  jns     short loc_180082913
0x18008290c  mov     edx, 47h ; 'G'
0x180082911  jmp     short loc_1800828CF
0x180082913  xorps   xmm0, xmm0
0x180082916  xor     eax, eax
0x180082918  movups  [rbp+var_28], xmm0
0x18008291c  mov     [rbp+var_18], rax
0x180082920  test    r14, r14
0x180082923  jnz     short loc_18008295E
0x180082925  lea     rdx, [rbp+arg_18]; struct APPX_KEY_INFO **
0x180082929  lea     rcx, [rbp+var_28]; this
0x18008292d  call    ?GetKeyInfo@GlobalDevKeyInfo@Packaging@Appx@@QEAAJPEAPEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(APPX_KEY_INFO const * *)
0x180082932  mov     ebx, eax
0x180082934  mov     rcx, [rbp+40h]; this
0x180082938  test    eax, eax
0x18008293a  jns     short loc_18008295A
0x18008293c  mov     r9d, eax; char *
0x18008293f  lea     edx, [r14+4Dh]; void *
0x180082943  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x18008294a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008294f  lea     rcx, [rbp+var_28]; this
0x180082953  call    ??1GlobalDevKeyInfo@Packaging@Appx@@QEAA@XZ; Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo(void)
0x180082958  jmp     short loc_1800828DE
0x18008295a  mov     r14, [rbp+arg_18]
0x18008295e  lea     r12, [rdi+28h]
0x180082962  mov     dl, [r15+18h]
0x180082966  and     dl, 1; bool
0x180082969  mov     qword ptr [rsp+68h+var_48], r12; int
0x18008296e  mov     r9, [r14+8]; unsigned __int8 *
0x180082972  mov     r8d, [r14]; unsigned int
0x180082975  mov     rcx, [r15+8]; pszAlgId
0x180082979  call    ?Create@EncryptionProvider@Packaging@Appx@@SAJPEBG_NIPEBEPEAPEAV123@@Z; Appx::Packaging::EncryptionProvider::Create(ushort const *,bool,uint,uchar const *,Appx::Packaging::EncryptionProvider * *)
0x18008297e  mov     ebx, eax
0x180082980  mov     rcx, [rbp+40h]
0x180082984  test    eax, eax
0x180082986  jns     short loc_18008298F
0x180082988  mov     edx, 55h ; 'U'
0x18008298d  jmp     short loc_1800829E3
0x18008298f  mov     rcx, [r12]
0x180082993  mov     eax, [r15]
0x180082996  cmp     [rcx+34h], eax
0x180082999  jz      short loc_1800829BA
0x18008299b  mov     edx, 58h ; 'X'; void *
0x1800829a0  mov     ebx, 80070057h
0x1800829a5  mov     rcx, [rbp+40h]; this
0x1800829a9  mov     r9d, ebx; char *
0x1800829ac  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x1800829b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800829b8  jmp     short loc_18008294F
0x1800829ba  mov     dword ptr [rbp+bstrString], 0
0x1800829c1  lea     r8, [rbp+bstrString]; unsigned int *
0x1800829c5  mov     esi, 10000h
0x1800829ca  mov     edx, esi; unsigned int
0x1800829cc  mov     ecx, [rcx+30h]; unsigned int
0x1800829cf  call    ?GetCipherBlockAlignedSize@EncryptionProvider@Packaging@Appx@@SAJIIPEAI@Z; Appx::Packaging::EncryptionProvider::GetCipherBlockAlignedSize(uint,uint,uint *)
0x1800829d4  mov     ebx, eax
0x1800829d6  mov     rcx, [rbp+40h]
0x1800829da  test    eax, eax
0x1800829dc  jns     short loc_1800829EB
0x1800829de  mov     edx, 5Bh ; '['
0x1800829e3  mov     r9d, eax
0x1800829e6  jmp     loc_180082943
0x1800829eb  cmp     dword ptr [rbp+bstrString], esi
0x1800829ee  jbe     short loc_1800829F7
0x1800829f0  mov     edx, 5Eh ; '^'
0x1800829f5  jmp     short loc_1800829A0
0x1800829f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800829fe  mov     ecx, 0E8h; unsigned __int64
0x180082a03  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180082a08  test    rax, rax
0x180082a0b  jz      short loc_180082A15
0x180082a0d  mov     rcx, rax; this
0x180082a10  call    ??0EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader(void)
0x180082a15  lea     rsi, [rdi+30h]
0x180082a19  mov     rdx, rax
0x180082a1c  mov     rcx, rsi
0x180082a1f  call    ??4?$AutoPtr@VEncryptedAppxHeader@Packaging@Appx@@$1??$AutoPtrDeallocate@VEncryptedAppxHeader@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@QEAAPEAVEncryptedAppxHeader@Packaging@Appx@@PEAV234@@Z; Common::AutoPtr<Appx::Packaging::EncryptedAppxHeader,&Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxHeader>(Appx::Packaging::EncryptedAppxHeader *)>::operator=(Appx::Packaging::EncryptedAppxHeader *)
0x180082a24  mov     rdx, [rsi]
0x180082a27  test    rdx, rdx
0x180082a2a  jnz     short loc_180082A3B
0x180082a2c  mov     ebx, 8007000Eh
0x180082a31  mov     edx, 62h ; 'b'
0x180082a36  jmp     loc_1800829A5
0x180082a3b  mov     rax, [r12]
0x180082a3f  mov     ecx, [rax+34h]
0x180082a42  mov     [rdx+58h], ecx
0x180082a45  mov     ecx, [r14+4]; unsigned __int64
0x180082a49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082a50  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082a55  mov     rbx, rax
0x180082a58  test    rax, rax
0x180082a5b  jnz     short loc_180082A86
0x180082a5d  mov     rcx, [rbp+40h]; this
0x180082a61  mov     ebx, 8007000Eh
0x180082a66  mov     r9d, ebx; char *
0x180082a69  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082a70  lea     edx, [rax+67h]; void *
0x180082a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082a78  nop
0x180082a79  xor     ecx, ecx; void *
0x180082a7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082a80  nop
0x180082a81  jmp     loc_18008294F
0x180082a86  mov     r8d, [r14+4]; Size
0x180082a8a  mov     rdx, [r14+10h]; Src
0x180082a8e  mov     rcx, rbx; void *
0x180082a91  call    memcpy_0
0x180082a96  mov     rcx, [rsi]
0x180082a99  add     rcx, 60h ; '`'
0x180082a9d  mov     rdx, rbx
0x180082aa0  call    ?Add@?$Array@EV?$ContainerOperations@EE@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@E@2@V?$ArrayOperations@EVNoKey@Common@@@2@@Common@@QEAAJPEAE@Z; Common::Array<uchar,Common::ContainerOperations<uchar,uchar>,Common::NoKey,Common::ContainerOperations<Common::NoKey,uchar>,Common::ArrayOperations<uchar,Common::NoKey>>::Add(uchar *)
0x180082aa5  mov     ebx, eax
0x180082aa7  mov     rcx, [rbp+40h]; this
0x180082aab  test    eax, eax
0x180082aad  jns     short loc_180082AD1
0x180082aaf  mov     r9d, eax; char *
0x180082ab2  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082ab9  mov     edx, 69h ; 'i'; void *
0x180082abe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082ac3  nop
0x180082ac4  xor     ecx, ecx; void *
0x180082ac6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082acb  nop
0x180082acc  jmp     loc_18008294F
0x180082ad1  mov     rcx, [rsi]
0x180082ad4  mov     al, [r14+4]
0x180082ad8  mov     [rcx+80h], al
0x180082ade  test    r13b, r13b
0x180082ae1  jz      short loc_180082AEC
0x180082ae3  mov     rax, [rsi]
0x180082ae6  mov     dword ptr [rax], 48425845h
0x180082aec  mov     rdx, [rsi]
0x180082aef  lea     r8, [rdx+98h]; unsigned int *
0x180082af6  add     rdx, 0A0h; unsigned __int16 **
0x180082afd  mov     rcx, [r15+8]; unsigned __int16 *
0x180082b01  call    ?AllocAndCopyString@StringHelper@Packaging@Appx@@SAJPEBGPEAPEAGPEAI@Z; Appx::Packaging::StringHelper::AllocAndCopyString(ushort const *,ushort * *,uint *)
0x180082b06  mov     ebx, eax
0x180082b08  mov     rcx, [rbp+40h]; this
0x180082b0c  test    eax, eax
0x180082b0e  jns     short loc_180082B32
0x180082b10  mov     r9d, eax; char *
0x180082b13  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082b1a  mov     edx, 74h ; 't'; void *
0x180082b1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082b24  nop
0x180082b25  xor     ecx, ecx; void *
0x180082b27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082b2c  nop
0x180082b2d  jmp     loc_18008294F
0x180082b32  mov     cl, [r15+18h]
0x180082b36  and     cl, 1
0x180082b39  mov     rax, [rsi]
0x180082b3c  mov     [rax+0A8h], cl
0x180082b42  mov     rcx, [r15+10h]
0x180082b46  test    rcx, rcx
0x180082b49  jz      loc_180082BFB
0x180082b4f  mov     [rbp+bstrString], 0
0x180082b57  mov     rax, [rcx]
0x180082b5a  lea     rdx, [rbp+bstrString]
0x180082b5e  mov     rax, [rax+38h]
0x180082b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b67  mov     ebx, eax
0x180082b69  mov     rcx, [rbp+40h]; this
0x180082b6d  test    eax, eax
0x180082b6f  jns     short loc_180082BA3
0x180082b71  mov     r9d, eax; char *
0x180082b74  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082b7b  mov     edx, 7Dh ; '}'; void *
0x180082b80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082b85  mov     rcx, [rbp+bstrString]; bstrString
0x180082b89  call    cs:__imp_SysFreeString
0x180082b90  nop     dword ptr [rax+rax+00h]
0x180082b95  nop
0x180082b96  xor     ecx, ecx; void *
0x180082b98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082b9d  nop
0x180082b9e  jmp     loc_18008294F
0x180082ba3  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180082ba7  mov     rcx, rdi; this
0x180082baa  call    ?InitializeBlockMapWriter@EncryptedPackageWriterHelper@Production@Packaging@Appx@@QEAAJPEBG@Z; Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeBlockMapWriter(ushort const *)
0x180082baf  mov     ebx, eax
0x180082bb1  mov     rcx, [rbp+40h]; this
0x180082bb5  test    eax, eax
0x180082bb7  jns     short loc_180082BEB
0x180082bb9  mov     r9d, eax; char *
0x180082bbc  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082bc3  mov     edx, 7Eh ; '~'; void *
0x180082bc8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082bcd  mov     rcx, [rbp+bstrString]; bstrString
0x180082bd1  call    cs:__imp_SysFreeString
0x180082bd8  nop     dword ptr [rax+rax+00h]
0x180082bdd  nop
0x180082bde  xor     ecx, ecx; void *
0x180082be0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082be5  nop
0x180082be6  jmp     loc_18008294F
0x180082beb  mov     rcx, [rbp+bstrString]; bstrString
0x180082bef  call    cs:__imp_SysFreeString
0x180082bf6  nop     dword ptr [rax+rax+00h]
0x180082bfb  mov     rdx, [rbp+arg_20]; unsigned __int64
0x180082bff  test    rdx, rdx
0x180082c02  jz      short loc_180082C38
0x180082c04  mov     rcx, rdi; this
0x180082c07  call    ?InitializeVersionNeutralPackageFullName@EncryptedPackageWriterHelper@Production@Packaging@Appx@@QEAAJPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeVersionNeutralPackageFullName(IAppxManifestPackageId *)
0x180082c0c  mov     ebx, eax
0x180082c0e  mov     rcx, [rbp+40h]; this
0x180082c12  test    eax, eax
0x180082c14  jns     short loc_180082C38
0x180082c16  mov     r9d, eax; char *
0x180082c19  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082c20  mov     edx, 85h; void *
0x180082c25  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082c2a  nop
0x180082c2b  xor     ecx, ecx; void *
0x180082c2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082c32  nop
0x180082c33  jmp     loc_18008294F
0x180082c38  mov     rax, [rbp+arg_28]
0x180082c3c  mov     [rax], rdi
0x180082c3f  xor     ecx, ecx; void *
0x180082c41  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180082c46  nop
0x180082c47  lea     rcx, [rbp+var_28]; this
0x180082c4b  call    ??1GlobalDevKeyInfo@Packaging@Appx@@QEAA@XZ; Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo(void)
0x180082c50  jmp     short loc_180082C6F
0x180082c52  mov     rcx, [rbp+40h]; this
0x180082c56  mov     ebx, 8007000Eh
0x180082c5b  mov     r9d, ebx; char *
0x180082c5e  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180082c65  mov     edx, 3Ch ; '<'; void *
0x180082c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c6f  xor     ecx, ecx
0x180082c71  call    ??$AutoPtrDeallocate@VEncryptedPackageWriterHelper@Production@Packaging@Appx@@@Common@@YAXPEAVEncryptedPackageWriterHelper@Production@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Production::EncryptedPackageWriterHelper>(Appx::Packaging::Production::EncryptedPackageWriterHelper *)
0x180082c76  mov     eax, ebx
0x180082c78  add     rsp, 68h
  ... truncated ...
```

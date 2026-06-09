# CreateTpmKeyHelper(_GUID const &,unsigned __int64,ulong,ushort const *,_NGC_RPC_KEY_CREATION_PARAMS const *,Properties::Key::ImplementationType,int,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::unique_ptr<Properties::KeyMaterial,std::default_delete<Properties::KeyMaterial>> *)

- ea: `0x18001ea1c`
- end: `0x18001ed97`
- name: `?CreateTpmKeyHelper@@YAJAEBU_GUID@@_KKPEBGPEBU_NGC_RPC_KEY_CREATION_PARAMS@@W4ImplementationType@Key@Properties@@HKPEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@7@@Z`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021c60`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000d62c`
- `0x1800108c8`
- `0x180011174`
- `0x180011c1c`
- `0x180018818`
- `0x18001d5bc`
- `0x18001e0c4`
- `0x18001e90c`
- `0x18001ea1c`
- `0x180020a54`
- `0x18006612c`
- `0x180066ba0`
- `0x18006f1ec`
- `0x180070ef0`
- `0x1800762ac`
- `0x180076364`
- `0x180076894`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18001ea8f`
- `bcrypt!BCryptGenRandom` at `0x18001ea8f`

## string_xrefs

- `0x18001eaa0`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18001ebd7`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18001ec7f`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18001ed27`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateTpmKeyHelper(
        int a1,
        int a2,
        int a3,
        const WCHAR *a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 *a11)
{
  NTSTATUS StringFromGuid; // ebx
  __int64 v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned int v17; // r9d
  int KeyAlgorithmTypeFromId; // edi
  struct VsmUtils::Vtl0Tpm *v19; // rax
  int TpmKeyMaterial; // eax
  __int64 v21; // rdx
  struct VsmUtils::Vtl0Tpm *v22; // rax
  RTL_SRWLOCK *v23; // rbx
  NCRYPT_PROV_HANDLE *v24; // rax
  int v25; // eax
  int v26; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v33; // [rsp+68h] [rbp-98h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v36[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 *v40; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B8h] [rbp-48h]
  UCHAR pbBuffer[16]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE pbOutput[40]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  int v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int64 v48; // [rsp+110h] [rbp+10h]
  char v49; // [rsp+118h] [rbp+18h]
  struct _GUID v50; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  LODWORD(v33) = a3;
  v39 = a9;
  v38 = a10;
  *(_OWORD *)pbBuffer = 0;
  StringFromGuid = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  if ( StringFromGuid >= 0 )
  {
    memset_0(&v50, 0, 0x4Eu);
    StringFromGuid = NgcUtils::GetStringFromGuid((NgcUtils *)pbBuffer, &v50, v16, v17);
    if ( StringFromGuid < 0 )
    {
      v15 = 449;
      goto LABEL_3;
    }
    v35 = 0;
    *(_OWORD *)v36 = 0;
    v37 = 0;
    KeyAlgorithmTypeFromId = GetKeyAlgorithmTypeFromId(a4);
    v19 = VsmUtils::Vtl0Tpm::Instance();
    TpmKeyMaterial = NgcIsoTrustlet::CreateTpmKeyMaterial(
                       a1,
                       a2,
                       a6,
                       KeyAlgorithmTypeFromId,
                       a5,
                       *((_QWORD *)v19 + 1),
                       (__int64)&v35,
                       (__int64)v36);
    StringFromGuid = TpmKeyMaterial;
    if ( TpmKeyMaterial < 0 )
    {
      if ( KeyAlgorithmTypeFromId != 4
        && KeyAlgorithmTypeFromId != 5
        && KeyAlgorithmTypeFromId != 6
        && KeyAlgorithmTypeFromId != 7
        && (unsigned int)(KeyAlgorithmTypeFromId - 8) >= 2 )
      {
        v21 = 484;
        goto LABEL_17;
      }
      TpmKeyMaterial = CreateAndDeleteDummyEccTpmKey();
      StringFromGuid = TpmKeyMaterial;
      if ( TpmKeyMaterial < 0 )
      {
        v21 = 470;
        goto LABEL_17;
      }
      v22 = VsmUtils::Vtl0Tpm::Instance();
      TpmKeyMaterial = NgcIsoTrustlet::CreateTpmKeyMaterial(
                         a1,
                         a2,
                         a6,
                         KeyAlgorithmTypeFromId,
                         a5,
                         *((_QWORD *)v22 + 1),
                         (__int64)&v35,
                         (__int64)v36);
      StringFromGuid = TpmKeyMaterial;
      if ( TpmKeyMaterial < 0 )
      {
        v21 = 480;
        goto LABEL_17;
      }
    }
    hKey = 0;
    v23 = (RTL_SRWLOCK *)NgcCtnrCommon::KeyHandleCache::Instance();
    v24 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
    TpmKeyMaterial = NgcCtnrCommon::KeyHandleCache::CreateKey(v23, *v24, a4, (LPCWSTR)&v50, v29, v31, &hKey);
    StringFromGuid = TpmKeyMaterial;
    if ( TpmKeyMaterial >= 0 )
    {
      TpmKeyMaterial = VsmUtils::CreateVtl1ProtectedKey(
                         hKey,
                         (unsigned int)v33,
                         v36[0],
                         (unsigned __int8 *)(v36[2] - v36[0]),
                         v29);
      StringFromGuid = TpmKeyMaterial;
      if ( TpmKeyMaterial >= 0 )
      {
        *(_DWORD *)pbOutput = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v25 = VsmUtils::Vtl0KeyBlob::Load(pbOutput, hKey);
        StringFromGuid = v25;
        if ( v25 >= 0 )
        {
          v32 = 0;
          v40 = &v32;
          v41 = 0;
          v42 = 1;
          v26 = GetKeyAlgorithmTypeFromId(a4);
          StringFromGuid = NgcIsoTrustlet::FinalizeTpmKeyMaterial(
                             a1,
                             a7,
                             (unsigned int)pbOutput,
                             v26,
                             (__int64)&v50,
                             (__int64)&v35,
                             a7,
                             a8,
                             v39,
                             v38,
                             (__int64)&v41);
          wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(&v40);
          if ( StringFromGuid >= 0 )
          {
            std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
              a11,
              &v32);
            std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v32);
            VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
            StringFromGuid = 0;
            goto LABEL_28;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x206,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)StringFromGuid,
            v30);
          std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v32);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F8,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
            (const char *)(unsigned int)v25,
            v29);
        }
        VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob((VsmUtils::Vtl0KeyBlob *)pbOutput);
LABEL_28:
        std::vector<unsigned char>::_Tidy(v36);
        return (unsigned int)StringFromGuid;
      }
      v21 = 501;
    }
    else
    {
      v21 = 495;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)TpmKeyMaterial,
      v29);
    goto LABEL_28;
  }
  v15 = 443;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)(unsigned int)StringFromGuid,
    v28);
  return (unsigned int)StringFromGuid;
}

```

## disassembly

```asm
0x18001ea1c  push    rbp
0x18001ea1e  push    rbx
0x18001ea1f  push    rsi
0x18001ea20  push    rdi
0x18001ea21  push    r12
0x18001ea23  push    r13
0x18001ea25  push    r14
0x18001ea27  push    r15
0x18001ea29  lea     rbp, [rsp-88h]
0x18001ea31  sub     rsp, 188h
0x18001ea38  mov     rax, cs:__security_cookie
0x18001ea3f  xor     rax, rsp
0x18001ea42  mov     [rbp+0C0h+var_50], rax
0x18001ea46  mov     rsi, r9
0x18001ea49  mov     dword ptr [rsp+1C0h+var_158], r8d
0x18001ea4e  mov     r15, rdx
0x18001ea51  mov     r14, rcx
0x18001ea54  mov     r12, [rbp+0C0h+arg_20]
0x18001ea5b  mov     rax, [rbp+0C0h+arg_40]
0x18001ea62  mov     [rbp+0C0h+var_120], rax
0x18001ea66  mov     rax, [rbp+0C0h+arg_48]
0x18001ea6d  mov     [rbp+0C0h+var_128], rax
0x18001ea71  mov     r13, [rbp+0C0h+arg_50]
0x18001ea78  xorps   xmm0, xmm0
0x18001ea7b  movups  xmmword ptr [rbp+0C0h+pbBuffer], xmm0
0x18001ea7f  mov     r9d, 2; dwFlags
0x18001ea85  lea     r8d, [r9+0Eh]; cbBuffer
0x18001ea89  lea     rdx, [rbp+0C0h+pbBuffer]; pbBuffer
0x18001ea8d  xor     ecx, ecx; hAlgorithm
0x18001ea8f  call    cs:__imp_BCryptGenRandom
0x18001ea95  mov     ebx, eax
0x18001ea97  test    eax, eax
0x18001ea99  jns     short loc_18001EABB
0x18001ea9b  mov     edx, 1BBh; void *
0x18001eaa0  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001eaa7  mov     r9d, ebx; char *
0x18001eaaa  mov     rcx, [rbp+0C8h]; this
0x18001eab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eab6  jmp     loc_18001ED75
0x18001eabb  xor     edx, edx; Val
0x18001eabd  lea     r8d, [rdx+4Eh]; Size
0x18001eac1  lea     rcx, [rbp+0C0h+var_A0]; void *
0x18001eac5  call    memset_0
0x18001eaca  lea     rdx, [rbp+0C0h+var_A0]; struct _GUID *
0x18001eace  lea     rcx, [rbp+0C0h+pbBuffer]; this
0x18001ead2  call    ?GetStringFromGuid@NgcUtils@@YAJAEBU_GUID@@PEAGK@Z; NgcUtils::GetStringFromGuid(_GUID const &,ushort *,ulong)
0x18001ead7  mov     ebx, eax
0x18001ead9  test    eax, eax
0x18001eadb  jns     short loc_18001EAE4
0x18001eadd  mov     edx, 1C1h
0x18001eae2  jmp     short loc_18001EAA0
0x18001eae4  mov     [rsp+1C0h+var_148], 0
0x18001eaed  xorps   xmm0, xmm0
0x18001eaf0  movdqu  xmmword ptr [rbp+0C0h+var_140], xmm0
0x18001eaf5  mov     [rbp+0C0h+var_130], 0
0x18001eafd  mov     rcx, rsi
0x18001eb00  call    GetKeyAlgorithmTypeFromId
0x18001eb05  mov     edi, eax
0x18001eb07  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x18001eb0c  lea     rcx, [rbp+0C0h+var_140]
0x18001eb10  mov     [rsp+1C0h+var_188], rcx
0x18001eb15  lea     rcx, [rsp+1C0h+var_148]
0x18001eb1a  mov     [rsp+1C0h+var_190], rcx
0x18001eb1f  mov     rcx, [rax+8]
0x18001eb23  mov     qword ptr [rsp+1C0h+var_198], rcx; unsigned int
0x18001eb28  mov     qword ptr [rsp+1C0h+var_1A0], r12; int
0x18001eb2d  mov     r9d, edi
0x18001eb30  mov     r8d, [rbp+0C0h+arg_28]
0x18001eb37  mov     rdx, r15
0x18001eb3a  mov     rcx, r14
0x18001eb3d  call    ?CreateTpmKeyMaterial@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@PEBU_NGC_RPC_KEY_CREATION_PARAMS@@1PEAPEAXPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoTrustlet::CreateTpmKeyMaterial(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,_NGC_RPC_KEY_CREATION_PARAMS const *,unsigned __int64,void * *,std::vector<uchar> *)
0x18001eb42  mov     ebx, eax
0x18001eb44  test    eax, eax
0x18001eb46  jns     loc_18001EBE8
0x18001eb4c  mov     edx, edi
0x18001eb4e  sub     edx, 4
0x18001eb51  jz      short loc_18001EB73
0x18001eb53  sub     edx, 1
0x18001eb56  jz      short loc_18001EB73
0x18001eb58  sub     edx, 1
0x18001eb5b  jz      short loc_18001EB73
0x18001eb5d  sub     edx, 1
0x18001eb60  jz      short loc_18001EB73
0x18001eb62  sub     edx, 1
0x18001eb65  jz      short loc_18001EB73
0x18001eb67  cmp     edx, 1
0x18001eb6a  jz      short loc_18001EB73
0x18001eb6c  mov     edx, 1E4h
0x18001eb71  jmp     short loc_18001EBCD
0x18001eb73  call    ?CreateAndDeleteDummyEccTpmKey@@YAJXZ; CreateAndDeleteDummyEccTpmKey(void)
0x18001eb78  mov     ebx, eax
0x18001eb7a  test    eax, eax
0x18001eb7c  jns     short loc_18001EB85
0x18001eb7e  mov     edx, 1D6h
0x18001eb83  jmp     short loc_18001EBCD
0x18001eb85  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x18001eb8a  lea     rcx, [rbp+0C0h+var_140]
0x18001eb8e  mov     [rsp+1C0h+var_188], rcx
0x18001eb93  lea     rcx, [rsp+1C0h+var_148]
0x18001eb98  mov     [rsp+1C0h+var_190], rcx
0x18001eb9d  mov     rax, [rax+8]
0x18001eba1  mov     qword ptr [rsp+1C0h+var_198], rax
0x18001eba6  mov     qword ptr [rsp+1C0h+var_1A0], r12; int
0x18001ebab  mov     r9d, edi
0x18001ebae  mov     r8d, [rbp+0C0h+arg_28]
0x18001ebb5  mov     rdx, r15
0x18001ebb8  mov     rcx, r14
0x18001ebbb  call    ?CreateTpmKeyMaterial@NgcIsoTrustlet@@YAJAEBU_GUID@@_KW4ImplementationType@Key@Properties@@W4Algorithm@@PEBU_NGC_RPC_KEY_CREATION_PARAMS@@1PEAPEAXPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoTrustlet::CreateTpmKeyMaterial(_GUID const &,unsigned __int64,Properties::Key::ImplementationType,Algorithm,_NGC_RPC_KEY_CREATION_PARAMS const *,unsigned __int64,void * *,std::vector<uchar> *)
0x18001ebc0  mov     ebx, eax
0x18001ebc2  xor     edi, edi
0x18001ebc4  test    eax, eax
0x18001ebc6  jns     short loc_18001EBEA
0x18001ebc8  mov     edx, 1E0h; void *
0x18001ebcd  mov     rcx, [rbp+0C8h]; this
0x18001ebd4  mov     r9d, eax; char *
0x18001ebd7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001ebde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ebe3  jmp     loc_18001ED6C
0x18001ebe8  xor     edi, edi
0x18001ebea  mov     [rsp+1C0h+hKey], rdi
0x18001ebef  call    ?Instance@KeyHandleCache@NgcCtnrCommon@@SAAEAV12@XZ; NgcCtnrCommon::KeyHandleCache::Instance(void)
0x18001ebf4  mov     rbx, rax
0x18001ebf7  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x18001ebfc  lea     rcx, [rsp+1C0h+hKey]
0x18001ec01  mov     [rsp+1C0h+var_190], rcx; unsigned __int64 *
0x18001ec06  lea     r9, [rbp+0C0h+var_A0]; pszKeyName
0x18001ec0a  mov     r8, rsi; pszAlgId
0x18001ec0d  mov     rdx, [rax]; hProvider
0x18001ec10  mov     rcx, rbx; SRWLock
0x18001ec13  call    ?CreateKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBG1KKPEA_K@Z; NgcCtnrCommon::KeyHandleCache::CreateKey(unsigned __int64,ushort const *,ushort const *,ulong,ulong,unsigned __int64 *)
0x18001ec18  mov     ebx, eax
0x18001ec1a  test    eax, eax
0x18001ec1c  jns     short loc_18001EC25
0x18001ec1e  mov     edx, 1EFh
0x18001ec23  jmp     short loc_18001EBCD
0x18001ec25  mov     r9d, [rbp+0C0h+var_140+8]
0x18001ec29  mov     r8, qword ptr [rbp+0C0h+var_140]; unsigned int
0x18001ec2d  sub     r9d, r8d; unsigned __int8 *
0x18001ec30  mov     edx, dword ptr [rsp+1C0h+var_158]; unsigned __int64
0x18001ec34  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001ec39  call    ?CreateVtl1ProtectedKey@VsmUtils@@YAJ_KKPEAEK@Z; VsmUtils::CreateVtl1ProtectedKey(unsigned __int64,ulong,uchar *,ulong)
0x18001ec3e  mov     ebx, eax
0x18001ec40  test    eax, eax
0x18001ec42  jns     short loc_18001EC4B
0x18001ec44  mov     edx, 1F5h
0x18001ec49  jmp     short loc_18001EBCD
0x18001ec4b  mov     dword ptr [rbp+0C0h+pbOutput], edi
0x18001ec4e  mov     [rbp+0C0h+var_C8], rdi
0x18001ec52  mov     [rbp+0C0h+var_C0], edi
0x18001ec55  mov     [rbp+0C0h+var_B8], rdi
0x18001ec59  mov     [rbp+0C0h+var_B0], rdi
0x18001ec5d  mov     [rbp+0C0h+var_A8], dil
0x18001ec61  mov     rdx, [rsp+1C0h+hKey]; hObject
0x18001ec66  lea     rcx, [rbp+0C0h+pbOutput]; pbOutput
0x18001ec6a  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x18001ec6f  mov     ebx, eax
0x18001ec71  test    eax, eax
0x18001ec73  jns     short loc_18001EC9F
0x18001ec75  mov     rcx, [rbp+0C8h]; this
0x18001ec7c  mov     r9d, eax; char *
0x18001ec7f  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001ec86  mov     edx, 1F8h; void *
0x18001ec8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec90  nop
0x18001ec91  lea     rcx, [rbp+0C0h+pbOutput]; this
0x18001ec95  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x18001ec9a  jmp     loc_18001ED6C
0x18001ec9f  mov     [rsp+1C0h+var_160], rdi
0x18001eca4  lea     rax, [rsp+1C0h+var_160]
0x18001eca9  mov     [rbp+0C0h+var_118], rax
0x18001ecad  mov     [rbp+0C0h+var_110], rdi
0x18001ecb1  mov     [rbp+0C0h+var_108], 1
0x18001ecb5  mov     rcx, rsi
0x18001ecb8  call    GetKeyAlgorithmTypeFromId
0x18001ecbd  lea     rcx, [rbp+0C0h+var_110]
0x18001ecc1  mov     [rsp+1C0h+var_170], rcx
0x18001ecc6  mov     rcx, [rbp+0C0h+var_128]
0x18001ecca  mov     [rsp+1C0h+var_178], rcx
0x18001eccf  mov     rcx, [rbp+0C0h+var_120]
0x18001ecd3  mov     [rsp+1C0h+var_180], rcx
0x18001ecd8  mov     edx, [rbp+0C0h+arg_38]
0x18001ecde  mov     dword ptr [rsp+1C0h+var_188], edx
0x18001ece2  mov     edx, [rbp+0C0h+arg_30]
0x18001ece8  mov     dword ptr [rsp+1C0h+var_190], edx
0x18001ecec  lea     rcx, [rsp+1C0h+var_148]
0x18001ecf1  mov     qword ptr [rsp+1C0h+var_198], rcx
0x18001ecf6  lea     rcx, [rbp+0C0h+var_A0]
0x18001ecfa  mov     qword ptr [rsp+1C0h+var_1A0], rcx; int
0x18001ecff  mov     r9d, eax
0x18001ed02  lea     r8, [rbp+0C0h+pbOutput]
0x18001ed06  mov     rcx, r14
0x18001ed09  call    ?FinalizeTpmKeyMaterial@NgcIsoTrustlet@@YAJAEBU_GUID@@_KPEBEW4Algorithm@@PEBGPEAPEAXHK2PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAPEAUTpmKeyMaterial@Properties@@@Z; NgcIsoTrustlet::FinalizeTpmKeyMaterial(_GUID const &,unsigned __int64,uchar const *,Algorithm,ushort const *,void * *,int,ulong,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,Properties::TpmKeyMaterial * *)
0x18001ed0e  mov     ebx, eax
0x18001ed10  lea     rcx, [rbp+0C0h+var_118]
0x18001ed14  call    ??1?$out_param_t@V?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Properties::KeyMaterial>>::~out_param_t<std::unique_ptr<Properties::KeyMaterial>>(void)
0x18001ed19  test    ebx, ebx
0x18001ed1b  jns     short loc_18001ED48
0x18001ed1d  mov     rcx, [rbp+0C8h]; this
0x18001ed24  mov     r9d, ebx; char *
0x18001ed27  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001ed2e  mov     edx, 206h; void *
0x18001ed33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ed38  nop
0x18001ed39  lea     rcx, [rsp+1C0h+var_160]
0x18001ed3e  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x18001ed43  jmp     loc_18001EC91
0x18001ed48  lea     rdx, [rsp+1C0h+var_160]
0x18001ed4d  mov     rcx, r13
0x18001ed50  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x18001ed55  nop
0x18001ed56  lea     rcx, [rsp+1C0h+var_160]
0x18001ed5b  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x18001ed60  nop
0x18001ed61  lea     rcx, [rbp+0C0h+pbOutput]; this
0x18001ed65  call    ??1Vtl0KeyBlob@VsmUtils@@QEAA@XZ; VsmUtils::Vtl0KeyBlob::~Vtl0KeyBlob(void)
0x18001ed6a  mov     ebx, edi
0x18001ed6c  lea     rcx, [rbp+0C0h+var_140]
0x18001ed70  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001ed75  mov     eax, ebx
0x18001ed77  mov     rcx, [rbp+0C0h+var_50]
0x18001ed7b  xor     rcx, rsp; StackCookie
0x18001ed7e  call    __security_check_cookie
0x18001ed83  add     rsp, 188h
0x18001ed8a  pop     r15
0x18001ed8c  pop     r14
0x18001ed8e  pop     r13
0x18001ed90  pop     r12
0x18001ed92  pop     rdi
0x18001ed93  pop     rsi
0x18001ed94  pop     rbx
0x18001ed95  pop     rbp
0x18001ed96  retn
```

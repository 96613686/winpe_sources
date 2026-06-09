# NgcIsoVsmContainerImpl::AddSecureBioProtector(unsigned __int64,unsigned __int64,unsigned __int64,uchar const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x14003e670`
- end: `0x14003e9db`
- name: `?AddSecureBioProtector@NgcIsoVsmContainerImpl@@UEAAJ_K00PEBEPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `875`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000a888`
- `0x14000ac7c`
- `0x14000bc44`
- `0x14000e034`
- `0x14000f6a0`
- `0x1400104fc`
- `0x1400184c0`
- `0x14002bdcc`
- `0x14003e350`
- `0x14003e670`
- `0x14003ecac`
- `0x140046020`
- `0x140059778`

## import_xrefs

- `IumSdk!GetTaggedData` at `0x14003e84e`
- `IumSdk!GetTaggedData` at `0x14003e84e`
- `IumSdk!GetTaggedDataSize` at `0x14003e843`
- `IumSdk!GetTaggedDataSize` at `0x14003e843`
- `bcrypt!BCryptGenRandom` at `0x14003e755`
- `bcrypt!BCryptGenRandom` at `0x14003e755`

## string_xrefs

- `0x14003e6ce`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\vsmcontainerimpl.cpp`
- `0x14003e769`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\vsmcontainerimpl.cpp`
- `0x14003e7bd`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\vsmcontainerimpl.cpp`
- `0x14003e8c7`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\vsmcontainerimpl.cpp`
- `0x14003e984`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\vsmcontainerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcIsoVsmContainerImpl::AddSecureBioProtector(
        NgcIsoContainerImpl *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        _OWORD *a5,
        __int64 a6)
{
  unsigned int v9; // ebx
  char *v10; // r14
  __int64 v11; // rax
  NTSTATUS v12; // eax
  int SecureBioProtector; // eax
  void **v14; // rcx
  int SecretStore; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rbx
  int TaggedDataSize; // edi
  _OWORD *TaggedData; // rax
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  size_t v24; // rbx
  signed __int64 v25; // rdi
  __int64 v26; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h]
  _BYTE v33[24]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v35[368]; // [rsp+80h] [rbp-80h] BYREF
  UCHAR v36[368]; // [rsp+1F0h] [rbp+F0h] BYREF
  UCHAR pbBuffer[16]; // [rsp+360h] [rbp+260h] BYREF
  __int128 v38; // [rsp+370h] [rbp+270h]
  __int64 v39; // [rsp+380h] [rbp+280h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  if ( a4 == 16 )
  {
    Properties::SecretStore::SecretStore((Properties::SecretStore *)v36);
    *(_OWORD *)pbBuffer = 0;
    v38 = 0;
    v30 = 7;
    v10 = (char *)this + 128;
    v11 = std::_Hash<std::_Umap_traits<enum NgcCtnrProtectorId,Properties::SecretStore,std::_Uhash_compare<enum NgcCtnrProtectorId,std::hash<enum NgcCtnrProtectorId>,std::equal_to<enum NgcCtnrProtectorId>>,std::allocator<std::pair<enum NgcCtnrProtectorId const,Properties::SecretStore>>,0>>::_Try_emplace<enum NgcCtnrProtectorId const &,>(
            (char *)this + 128,
            Src,
            &v30);
    if ( !*(_QWORD *)(*(_QWORD *)v11 + 344LL)
      && *(_QWORD *)(*(_QWORD *)v11 + 32LL) == *(_QWORD *)(*(_QWORD *)v11 + 40LL) )
    {
      v12 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
      if ( v12 < 0 )
      {
        v9 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x51,
               (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\vsmcontainerimpl.cpp",
               (const char *)(unsigned int)v12,
               v28);
LABEL_24:
        Properties::SecretStore::~SecretStore((Properties::SecretStore *)v36);
        return v9;
      }
      std::vector<unsigned char>::vector<unsigned char>(v33, pbBuffer, &v39);
      SecureBioProtector = NgcIsoVsmContainerImpl::CreateSecureBioProtector(this, a2, a3);
      v9 = SecureBioProtector;
      if ( SecureBioProtector < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\vsmcontainerimpl.cpp",
          (const char *)(unsigned int)SecureBioProtector,
          v28);
        v14 = (void **)v33;
LABEL_9:
        std::vector<unsigned char>::_Tidy(v14);
        goto LABEL_24;
      }
      std::vector<unsigned char>::_Tidy(v33);
LABEL_16:
      *(_OWORD *)Src = 0;
      v32 = 0;
      v21 = VsmUtils::SignTrustletData((_DWORD)a5, 16, (unsigned int)pbBuffer, 32, (__int64)Src);
      v9 = v21;
      if ( v21 >= 0 )
      {
        v24 = (char *)Src[1] - (char *)Src[0];
        v25 = (char *)Src[1] - (char *)Src[0] + 64;
        if ( (void *)((char *)Src[1] - (char *)Src[0]) < (void *)0xFFFFFFFFFFFFFFC0LL )
        {
          std::vector<unsigned char>::vector<unsigned char>(v34, (char *)Src[1] - (char *)Src[0] + 64);
          v26 = v34[0];
          *(_QWORD *)v34[0] = v25;
          *(_QWORD *)(v26 + 8) = v24;
          *(_OWORD *)(v26 + 16) = *a5;
          *(_OWORD *)(v26 + 32) = *(_OWORD *)pbBuffer;
          *(_OWORD *)(v26 + 48) = v38;
          memcpy_0((void *)(v26 + 64), Src[0], v24);
          std::vector<unsigned char>::operator=(a6, v34);
          std::vector<unsigned char>::_Tidy(v34);
          std::vector<unsigned char>::_Tidy(Src);
          v9 = 0;
          goto LABEL_24;
        }
        v9 = -2147024362;
        v22 = 2147942934LL;
        v23 = 115;
      }
      else
      {
        v22 = (unsigned int)v21;
        v23 = 112;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\vsmcontainerimpl.cpp",
        (const char *)v22,
        v29);
      v14 = Src;
      goto LABEL_9;
    }
    Properties::SecretStore::SecretStore((Properties::SecretStore *)v35);
    SecretStore = NgcIsoContainerImpl::CreateSecretStore(this, a2, a3, (struct Properties::SecretStore *)v35);
    v9 = SecretStore;
    if ( SecretStore >= 0 )
    {
      v30 = 7;
      v18 = *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<enum NgcCtnrProtectorId,Properties::SecretStore,std::_Uhash_compare<enum NgcCtnrProtectorId,std::hash<enum NgcCtnrProtectorId>,std::equal_to<enum NgcCtnrProtectorId>>,std::allocator<std::pair<enum NgcCtnrProtectorId const,Properties::SecretStore>>,0>>::_Try_emplace<enum NgcCtnrProtectorId const &,>(
                                     v10,
                                     Src,
                                     &v30)
                      + 192LL);
      TaggedDataSize = GetTaggedDataSize(v18);
      TaggedData = (_OWORD *)GetTaggedData(v18);
      if ( TaggedData && TaggedDataSize == 32 )
      {
        *(_OWORD *)pbBuffer = *TaggedData;
        v38 = TaggedData[1];
        Properties::SecretStore::~SecretStore((Properties::SecretStore *)v35);
        goto LABEL_16;
      }
      v9 = -2147418113;
      v16 = 2147549183LL;
      v17 = 102;
    }
    else
    {
      v16 = (unsigned int)SecretStore;
      v17 = 94;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\vsmcontainerimpl.cpp",
      (const char *)v16,
      v28);
    Properties::SecretStore::~SecretStore((Properties::SecretStore *)v35);
    goto LABEL_24;
  }
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\vsmcontainerimpl.cpp",
    (const char *)0x80070057LL,
    v28);
  return v9;
}

```

## disassembly

```asm
0x14003e670  mov     [rsp-8+arg_8], rbx
0x14003e675  mov     [rsp-8+arg_10], rsi
0x14003e67a  push    rbp
0x14003e67b  push    rdi
0x14003e67c  push    r12
0x14003e67e  push    r14
0x14003e680  push    r15
0x14003e682  lea     rbp, [rsp-290h]
0x14003e68a  sub     rsp, 390h
0x14003e691  mov     rax, cs:__security_cookie
0x14003e698  xor     rax, rsp
0x14003e69b  mov     [rbp+2B0h+var_30], rax
0x14003e6a2  mov     rdi, r8
0x14003e6a5  mov     rsi, rdx
0x14003e6a8  mov     rbx, rcx
0x14003e6ab  mov     r15, [rbp+2B0h+arg_20]
0x14003e6b2  mov     r12, [rbp+2B0h+arg_28]
0x14003e6b9  cmp     r9, 10h
0x14003e6bd  jz      short loc_14003E6E4
0x14003e6bf  mov     rcx, [rbp+2B8h]; this
0x14003e6c6  mov     ebx, 80070057h
0x14003e6cb  mov     r9d, ebx; char *
0x14003e6ce  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14003e6d5  mov     edx, 43h ; 'C'; void *
0x14003e6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e6df  jmp     loc_14003E9AE
0x14003e6e4  lea     rcx, [rbp+2B0h+var_1C0]; this
0x14003e6eb  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x14003e6f0  nop
0x14003e6f1  xorps   xmm0, xmm0
0x14003e6f4  movups  xmmword ptr [rbp+2B0h+pbBuffer], xmm0
0x14003e6fb  movups  [rbp+2B0h+var_40], xmm0
0x14003e702  mov     [rsp+3B0h+var_380], 7
0x14003e70a  lea     r14, [rbx+80h]
0x14003e711  lea     r8, [rsp+3B0h+var_380]
0x14003e716  lea     rdx, [rsp+3B0h+Src]
0x14003e71b  mov     rcx, r14
0x14003e71e  call    ??$_Try_emplace@AEBW4NgcCtnrProtectorId@@$$V@?$_Hash@V?$_Umap_traits@W4NgcCtnrProtectorId@@USecretStore@Properties@@V?$_Uhash_compare@W4NgcCtnrProtectorId@@U?$hash@W4NgcCtnrProtectorId@@@std@@U?$equal_to@W4NgcCtnrProtectorId@@@3@@std@@V?$allocator@U?$pair@$$CBW4NgcCtnrProtectorId@@USecretStore@Properties@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4NgcCtnrProtectorId@@USecretStore@Properties@@@std@@PEAX@std@@_N@1@AEBW4NgcCtnrProtectorId@@@Z; std::_Hash<std::_Umap_traits<NgcCtnrProtectorId,Properties::SecretStore,std::_Uhash_compare<NgcCtnrProtectorId,std::hash<NgcCtnrProtectorId>,std::equal_to<NgcCtnrProtectorId>>,std::allocator<std::pair<NgcCtnrProtectorId const,Properties::SecretStore>>,0>>::_Try_emplace<NgcCtnrProtectorId const &,>(NgcCtnrProtectorId const &)
0x14003e723  mov     rcx, [rax]
0x14003e726  cmp     qword ptr [rcx+158h], 0
0x14003e72e  jnz     loc_14003E7ED
0x14003e734  mov     rax, [rcx+28h]
0x14003e738  cmp     [rcx+20h], rax
0x14003e73c  jnz     loc_14003E7ED
0x14003e742  mov     r9d, 2; dwFlags
0x14003e748  lea     r8d, [r9+1Eh]; cbBuffer
0x14003e74c  lea     rdx, [rbp+2B0h+pbBuffer]; pbBuffer
0x14003e753  xor     ecx, ecx; hAlgorithm
0x14003e755  call    cs:__imp_BCryptGenRandom
0x14003e75b  test    eax, eax
0x14003e75d  jns     short loc_14003E781
0x14003e75f  mov     rcx, [rbp+2B8h]; this
0x14003e766  mov     r9d, eax; char *
0x14003e769  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14003e770  mov     edx, 51h ; 'Q'; void *
0x14003e775  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14003e77a  mov     ebx, eax
0x14003e77c  jmp     loc_14003E9A2
0x14003e781  lea     r8, [rbp+2B0h+var_30]
0x14003e788  lea     rdx, [rbp+2B0h+pbBuffer]
0x14003e78f  lea     rcx, [rsp+3B0h+var_360]
0x14003e794  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x14003e799  nop
0x14003e79a  lea     r9, [rsp+3B0h+var_360]
0x14003e79f  mov     r8, rdi
0x14003e7a2  mov     rdx, rsi
0x14003e7a5  mov     rcx, rbx
0x14003e7a8  call    ?CreateSecureBioProtector@NgcIsoVsmContainerImpl@@AEAAJ_K0AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcIsoVsmContainerImpl::CreateSecureBioProtector(unsigned __int64,unsigned __int64,std::vector<uchar> const &)
0x14003e7ad  mov     ebx, eax
0x14003e7af  test    eax, eax
0x14003e7b1  jns     short loc_14003E7DE
0x14003e7b3  mov     rcx, [rbp+2B8h]; this
0x14003e7ba  mov     r9d, eax; char *
0x14003e7bd  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14003e7c4  mov     edx, 57h ; 'W'; void *
0x14003e7c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e7ce  nop
0x14003e7cf  lea     rcx, [rsp+3B0h+var_360]
0x14003e7d4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14003e7d9  jmp     loc_14003E9A2
0x14003e7de  lea     rcx, [rsp+3B0h+var_360]
0x14003e7e3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14003e7e8  jmp     loc_14003E884
0x14003e7ed  lea     rcx, [rbp+2B0h+var_330]; this
0x14003e7f1  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x14003e7f6  nop
0x14003e7f7  lea     r9, [rbp+2B0h+var_330]; struct Properties::SecretStore *
0x14003e7fb  mov     r8, rdi; unsigned __int64
0x14003e7fe  mov     rdx, rsi; unsigned __int64
0x14003e801  mov     rcx, rbx; this
0x14003e804  call    ?CreateSecretStore@NgcIsoContainerImpl@@IEAAJ_K0PEAUSecretStore@Properties@@@Z; NgcIsoContainerImpl::CreateSecretStore(unsigned __int64,unsigned __int64,Properties::SecretStore *)
0x14003e809  mov     ebx, eax
0x14003e80b  test    eax, eax
0x14003e80d  jns     short loc_14003E81C
0x14003e80f  mov     r9d, eax
0x14003e812  mov     edx, 5Eh ; '^'
0x14003e817  jmp     loc_14003E984
0x14003e81c  mov     [rsp+3B0h+var_380], 7
0x14003e824  lea     r8, [rsp+3B0h+var_380]
0x14003e829  lea     rdx, [rsp+3B0h+Src]
0x14003e82e  mov     rcx, r14
0x14003e831  call    ??$_Try_emplace@AEBW4NgcCtnrProtectorId@@$$V@?$_Hash@V?$_Umap_traits@W4NgcCtnrProtectorId@@USecretStore@Properties@@V?$_Uhash_compare@W4NgcCtnrProtectorId@@U?$hash@W4NgcCtnrProtectorId@@@std@@U?$equal_to@W4NgcCtnrProtectorId@@@3@@std@@V?$allocator@U?$pair@$$CBW4NgcCtnrProtectorId@@USecretStore@Properties@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4NgcCtnrProtectorId@@USecretStore@Properties@@@std@@PEAX@std@@_N@1@AEBW4NgcCtnrProtectorId@@@Z; std::_Hash<std::_Umap_traits<NgcCtnrProtectorId,Properties::SecretStore,std::_Uhash_compare<NgcCtnrProtectorId,std::hash<NgcCtnrProtectorId>,std::equal_to<NgcCtnrProtectorId>>,std::allocator<std::pair<NgcCtnrProtectorId const,Properties::SecretStore>>,0>>::_Try_emplace<NgcCtnrProtectorId const &,>(NgcCtnrProtectorId const &)
0x14003e836  mov     rcx, [rax]
0x14003e839  mov     rbx, [rcx+0C0h]
0x14003e840  mov     rcx, rbx
0x14003e843  call    cs:__imp_GetTaggedDataSize
0x14003e849  mov     edi, eax
0x14003e84b  mov     rcx, rbx
0x14003e84e  call    cs:__imp_GetTaggedData
0x14003e854  test    rax, rax
0x14003e857  jz      loc_14003E977
0x14003e85d  cmp     edi, 20h ; ' '
0x14003e860  jnz     loc_14003E977
0x14003e866  movups  xmm0, xmmword ptr [rax]
0x14003e869  movups  xmmword ptr [rbp+2B0h+pbBuffer], xmm0
0x14003e870  movups  xmm1, xmmword ptr [rax+10h]
0x14003e874  movups  [rbp+2B0h+var_40], xmm1
0x14003e87b  lea     rcx, [rbp+2B0h+var_330]; this
0x14003e87f  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x14003e884  xorps   xmm0, xmm0
0x14003e887  movdqu  xmmword ptr [rsp+3B0h+Src], xmm0
0x14003e88d  mov     [rsp+3B0h+var_368], 0
0x14003e896  lea     rax, [rsp+3B0h+Src]
0x14003e89b  mov     qword ptr [rsp+3B0h+var_390], rax; int
0x14003e8a0  mov     r9d, 20h ; ' '
0x14003e8a6  lea     r8, [rbp+2B0h+pbBuffer]
0x14003e8ad  lea     edx, [r9-10h]
0x14003e8b1  mov     rcx, r15
0x14003e8b4  call    ?SignTrustletData@VsmUtils@@YAJPEBE_K01PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VsmUtils::SignTrustletData(uchar const *,unsigned __int64,uchar const *,unsigned __int64,std::vector<uchar> *)
0x14003e8b9  mov     ebx, eax
0x14003e8bb  test    eax, eax
0x14003e8bd  jns     short loc_14003E8E5
0x14003e8bf  mov     r9d, eax; char *
0x14003e8c2  mov     edx, 70h ; 'p'; void *
0x14003e8c7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14003e8ce  mov     rcx, [rbp+2B8h]; this
0x14003e8d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e8da  nop
0x14003e8db  lea     rcx, [rsp+3B0h+Src]
0x14003e8e0  jmp     loc_14003E7D4
0x14003e8e5  mov     rbx, [rsp+3B0h+Src+8]
0x14003e8ea  sub     rbx, [rsp+3B0h+Src]
0x14003e8ef  lea     rdi, [rbx+40h]
0x14003e8f3  cmp     rdi, 40h ; '@'
0x14003e8f7  jnb     short loc_14003E908
0x14003e8f9  mov     ebx, 80070216h
0x14003e8fe  mov     r9d, ebx
0x14003e901  mov     edx, 73h ; 's'
0x14003e906  jmp     short loc_14003E8C7
0x14003e908  mov     rdx, rdi
0x14003e90b  lea     rcx, [rsp+3B0h+var_348]
0x14003e910  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x14003e915  mov     rcx, [rsp+3B0h+var_348]
0x14003e91a  mov     [rcx], rdi
0x14003e91d  mov     [rcx+8], rbx
0x14003e921  movups  xmm0, xmmword ptr [r15]
0x14003e925  movdqu  xmmword ptr [rcx+10h], xmm0
0x14003e92a  movups  xmm1, xmmword ptr [rbp+2B0h+pbBuffer]
0x14003e931  movups  xmmword ptr [rcx+20h], xmm1
0x14003e935  movups  xmm0, [rbp+2B0h+var_40]
0x14003e93c  movups  xmmword ptr [rcx+30h], xmm0
0x14003e940  add     rcx, 40h ; '@'; void *
0x14003e944  mov     r8, rbx; Size
0x14003e947  mov     rdx, [rsp+3B0h+Src]; Src
0x14003e94c  call    memcpy_0
0x14003e951  lea     rdx, [rsp+3B0h+var_348]
0x14003e956  mov     rcx, r12
0x14003e959  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x14003e95e  lea     rcx, [rsp+3B0h+var_348]
0x14003e963  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14003e968  nop
0x14003e969  lea     rcx, [rsp+3B0h+Src]
0x14003e96e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14003e973  xor     ebx, ebx
0x14003e975  jmp     short loc_14003E9A2
0x14003e977  mov     ebx, 8000FFFFh
0x14003e97c  mov     r9d, ebx; char *
0x14003e97f  mov     edx, 66h ; 'f'; void *
0x14003e984  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14003e98b  mov     rcx, [rbp+2B8h]; this
0x14003e992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e997  nop
0x14003e998  lea     rcx, [rbp+2B0h+var_330]; this
0x14003e99c  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x14003e9a1  nop
0x14003e9a2  lea     rcx, [rbp+2B0h+var_1C0]; this
0x14003e9a9  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x14003e9ae  mov     eax, ebx
0x14003e9b0  mov     rcx, [rbp+2B0h+var_30]
0x14003e9b7  xor     rcx, rsp; StackCookie
0x14003e9ba  call    __security_check_cookie
0x14003e9bf  lea     r11, [rsp+3B0h+var_20]
0x14003e9c7  mov     rbx, [r11+38h]
0x14003e9cb  mov     rsi, [r11+40h]
0x14003e9cf  mov     rsp, r11
0x14003e9d2  pop     r15
0x14003e9d4  pop     r14
0x14003e9d6  pop     r12
0x14003e9d8  pop     rdi
0x14003e9d9  pop     rbp
0x14003e9da  retn
```

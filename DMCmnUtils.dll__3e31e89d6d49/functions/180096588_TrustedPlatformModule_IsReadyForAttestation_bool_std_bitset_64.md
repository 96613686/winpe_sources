# TrustedPlatformModule::IsReadyForAttestation(bool &,std::bitset<64> *)

- ea: `0x180096588`
- end: `0x180096797`
- name: `?IsReadyForAttestation@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180062c10`

## callees

- `0x180007270`
- `0x180057c6c`
- `0x180096588`
- `0x1800967a0`
- `0x180096930`
- `0x180096b14`
- `0x180096b50`
- `0x1800975ec`
- `0x180097a88`
- `0x180098c64`
- `0x1800993d8`

## import_xrefs

- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x180096630`
- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x180096630`

## string_xrefs

- `0x1800965d7`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18009660f`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18009665a`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x1800966bc`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x180096706`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall TrustedPlatformModule::IsReadyForAttestation(TrustedPlatformModule *this, char *a2, _QWORD *a3)
{
  char v6; // bl
  int Version; // eax
  unsigned int v8; // edi
  int IsReadyForStorage; // eax
  unsigned int v11; // edi
  unsigned int TCG_Log; // edi
  __int64 v13; // r8
  __int64 v14; // rdx
  TrustedPlatformModule *v15; // rcx
  int IsEkCertificatePresent; // eax
  __int64 v17; // r8
  unsigned int v18; // edi
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // edi
  __int64 v22; // r8
  __int64 v23; // rax
  bool v24[4]; // [rsp+20h] [rbp-48h] BYREF
  int v25; // [rsp+24h] [rbp-44h] BYREF
  _BYTE v26[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v27; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v27 = 0;
  v25 = 0;
  v24[0] = 0;
  v6 = 1;
  v24[1] = 1;
  Version = TrustedPlatformModule::GetVersion(this, 0);
  v8 = Version;
  if ( Version >= 0 )
  {
    IsReadyForStorage = TrustedPlatformModule::IsReadyForStorage(this, v26, &v27);
    v11 = IsReadyForStorage;
    if ( IsReadyForStorage >= 0 )
    {
      TCG_Log = Tbsi_Get_TCG_Log_Ex(0, 0, &v25);
      if ( (int)(TCG_Log + 0x80000000) < 0 || TCG_Log == -2144845807 )
      {
        if ( !v25 )
        {
          LOBYTE(v13) = 1;
          std::bitset<64>::set(&v27, 0, v13);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl'::`2'::impl) )
          IsEkCertificatePresent = TrustedPlatformModule::CheckUpdateEkCertPresent(v15, v14, v24);
        else
          IsEkCertificatePresent = TrustedPlatformModule::IsEkCertificatePresent(v15, v24);
        v18 = IsEkCertificatePresent;
        if ( IsEkCertificatePresent >= 0 )
        {
          if ( !v24[0] )
          {
            LOBYTE(v17) = 1;
            std::bitset<64>::set(&v27, 1, v17);
          }
          v19 = TrustedPlatformModule::LostAuths(this, &v24[1]);
          v21 = v19;
          if ( v19 >= 0 )
          {
            if ( v24[1] )
            {
              LOBYTE(v20) = 1;
              std::bitset<64>::set(&v27, 2, v20);
            }
            if ( TrustedPlatformModule::HasAttestationVulnerability(this) )
            {
              LOBYTE(v22) = 1;
              std::bitset<64>::set(&v27, 4, v22);
            }
            v23 = 0;
            while ( !*(&v27 + v23) )
            {
              if ( ++v23 )
                goto LABEL_28;
            }
            v6 = 0;
LABEL_28:
            *a2 = v6;
            if ( a3 )
              *a3 = v27;
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
              (const char *)(unsigned int)v19,
              *(int *)v24);
            return v21;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAE,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
            (const char *)(unsigned int)IsEkCertificatePresent,
            *(int *)v24);
          return v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
          (const char *)TCG_Log,
          *(int *)v24);
        return TCG_Log;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
        (const char *)(unsigned int)IsReadyForStorage,
        *(int *)v24);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
      (const char *)(unsigned int)Version,
      *(int *)v24);
    return v8;
  }
}

```

## disassembly

```asm
0x180096588  push    rbx
0x18009658a  push    rsi
0x18009658b  push    rdi
0x18009658c  push    r14
0x18009658e  push    r15
0x180096590  sub     rsp, 40h
0x180096594  mov     rax, cs:__security_cookie
0x18009659b  xor     rax, rsp
0x18009659e  mov     [rsp+68h+var_30], rax
0x1800965a3  mov     r14, r8
0x1800965a6  mov     r15, rdx
0x1800965a9  mov     rsi, rcx
0x1800965ac  xor     eax, eax
0x1800965ae  mov     [rsp+68h+var_38], rax
0x1800965b3  mov     [rsp+68h+var_44], eax
0x1800965b7  mov     [rsp+68h+var_48], al; int
0x1800965bb  lea     ebx, [rax+1]
0x1800965be  mov     [rsp+68h+var_48+1], bl
0x1800965c2  xor     edx, edx
0x1800965c4  call    ?GetVersion@TrustedPlatformModule@@QEAAJPEAW4TpmVersion@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrustedPlatformModule::GetVersion(TpmVersion *,std::wstring *)
0x1800965c9  mov     edi, eax
0x1800965cb  test    eax, eax
0x1800965cd  jns     short loc_1800965EF
0x1800965cf  mov     rcx, [rsp+68h]; this
0x1800965d4  mov     r9d, eax; char *
0x1800965d7  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x1800965de  mov     edx, 8Ch; void *
0x1800965e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800965e8  mov     eax, edi
0x1800965ea  jmp     loc_18009677D
0x1800965ef  lea     r8, [rsp+68h+var_38]
0x1800965f4  lea     rdx, [rsp+68h+var_40]
0x1800965f9  mov     rcx, rsi
0x1800965fc  call    ?IsReadyForStorage@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReadyForStorage(bool &,std::bitset<64> *)
0x180096601  mov     edi, eax
0x180096603  test    eax, eax
0x180096605  jns     short loc_180096627
0x180096607  mov     rcx, [rsp+68h]; this
0x18009660c  mov     r9d, eax; char *
0x18009660f  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x180096616  mov     edx, 8Fh; void *
0x18009661b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096620  mov     eax, edi
0x180096622  jmp     loc_18009677D
0x180096627  lea     r8, [rsp+68h+var_44]
0x18009662c  xor     edx, edx
0x18009662e  xor     ecx, ecx
0x180096630  call    cs:__imp_Tbsi_Get_TCG_Log_Ex
0x180096637  nop     dword ptr [rax+rax+00h]
0x18009663c  mov     edi, eax
0x18009663e  mov     eax, 80000000h
0x180096643  lea     ecx, [rdi+rax]
0x180096646  test    eax, ecx
0x180096648  jnz     short loc_180096672
0x18009664a  cmp     edi, 80284011h
0x180096650  jz      short loc_180096672
0x180096652  mov     rcx, [rsp+68h]; this
0x180096657  mov     r9d, edi; char *
0x18009665a  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x180096661  mov     edx, 9Ch; void *
0x180096666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009666b  mov     eax, edi
0x18009666d  jmp     loc_18009677D
0x180096672  cmp     [rsp+68h+var_44], 0
0x180096677  jnz     short loc_180096688
0x180096679  mov     r8b, bl
0x18009667c  xor     edx, edx
0x18009667e  lea     rcx, [rsp+68h+var_38]
0x180096683  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180096688  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard> `wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl(void)'::`2'::impl
0x18009668f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(void)
0x180096694  test    al, al
0x180096696  jz      short loc_1800966A4
0x180096698  lea     r8, [rsp+68h+var_48]
0x18009669d  call    ?CheckUpdateEkCertPresent@TrustedPlatformModule@@QEAAJW4TpmAlgID@@AEA_N@Z; TrustedPlatformModule::CheckUpdateEkCertPresent(TpmAlgID,bool &)
0x1800966a2  jmp     short loc_1800966AE
0x1800966a4  lea     rdx, [rsp+68h+var_48]; bool *
0x1800966a9  call    ?IsEkCertificatePresent@TrustedPlatformModule@@QEAAJAEA_N@Z; TrustedPlatformModule::IsEkCertificatePresent(bool &)
0x1800966ae  mov     edi, eax
0x1800966b0  test    eax, eax
0x1800966b2  jns     short loc_1800966D4
0x1800966b4  mov     rcx, [rsp+68h]; this
0x1800966b9  mov     r9d, eax; char *
0x1800966bc  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x1800966c3  mov     edx, 0AEh; void *
0x1800966c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800966cd  mov     eax, edi
0x1800966cf  jmp     loc_18009677D
0x1800966d4  cmp     [rsp+68h+var_48], 0
0x1800966d9  jnz     short loc_1800966EB
0x1800966db  mov     r8b, bl
0x1800966de  mov     rdx, rbx
0x1800966e1  lea     rcx, [rsp+68h+var_38]
0x1800966e6  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x1800966eb  lea     rdx, [rsp+68h+var_48+1]; bool *
0x1800966f0  mov     rcx, rsi; this
0x1800966f3  call    ?LostAuths@TrustedPlatformModule@@AEAAJAEA_N@Z; TrustedPlatformModule::LostAuths(bool &)
0x1800966f8  mov     edi, eax
0x1800966fa  test    eax, eax
0x1800966fc  jns     short loc_18009671B
0x1800966fe  mov     rcx, [rsp+68h]; this
0x180096703  mov     r9d, eax; char *
0x180096706  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18009670d  mov     edx, 0BAh; void *
0x180096712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096717  mov     eax, edi
0x180096719  jmp     short loc_18009677D
0x18009671b  cmp     [rsp+68h+var_48+1], 0
0x180096720  jz      short loc_180096734
0x180096722  mov     r8b, bl
0x180096725  mov     edx, 2
0x18009672a  lea     rcx, [rsp+68h+var_38]
0x18009672f  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180096734  mov     rcx, rsi; this
0x180096737  call    ?HasAttestationVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasAttestationVulnerability(void)
0x18009673c  test    al, al
0x18009673e  jz      short loc_180096752
0x180096740  mov     r8b, bl
0x180096743  mov     edx, 4
0x180096748  lea     rcx, [rsp+68h+var_38]
0x18009674d  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180096752  xor     eax, eax
0x180096754  cmp     [rsp+rax*8+68h+var_38], 0
0x18009675a  jnz     short loc_180096763
0x18009675c  add     rax, rbx
0x18009675f  jz      short loc_180096754
0x180096761  jmp     short loc_180096765
0x180096763  xor     bl, bl
0x180096765  mov     [r15], bl
0x180096768  test    r14, r14
0x18009676b  jz      short loc_180096775
0x18009676d  mov     rax, [rsp+68h+var_38]
0x180096772  mov     [r14], rax
0x180096775  xor     eax, eax
0x180096777  jmp     short loc_18009677D
0x180096779  mov     eax, [rsp+68h+var_44]
0x18009677d  mov     rcx, [rsp+68h+var_30]
0x180096782  xor     rcx, rsp; StackCookie
0x180096785  call    __security_check_cookie
0x18009678a  add     rsp, 40h
0x18009678e  pop     r15
0x180096790  pop     r14
0x180096792  pop     rdi
0x180096793  pop     rsi
0x180096794  pop     rbx
0x180096795  retn
```

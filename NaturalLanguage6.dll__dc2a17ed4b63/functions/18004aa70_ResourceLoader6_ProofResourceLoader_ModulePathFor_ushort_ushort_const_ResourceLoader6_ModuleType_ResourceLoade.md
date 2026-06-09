# ResourceLoader6::ProofResourceLoader::ModulePathFor(ushort,ushort const *,ResourceLoader6::ModuleType,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *)

- ea: `0x18004aa70`
- end: `0x18004ae9f`
- name: `?ModulePathFor@ProofResourceLoader@ResourceLoader6@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GPEBGW4ModuleType@2@PEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(struct IUnknown *this, __int64, unsigned __int16, const unsigned __int16 *, unsigned int, IID *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180005190`
- `0x1800146f0`
- `0x180014ebc`
- `0x1800162e4`
- `0x180017858`
- `0x180030c5c`
- `0x180030ca8`
- `0x180032594`
- `0x180035640`
- `0x18003ed6c`
- `0x18004952c`
- `0x180049c00`
- `0x18004aa70`
- `0x18009e2c2`
- `0x18009e300`

## string_xrefs

- `0x18004ad9a`: `ProofLexPath`
- `0x18004ac34`: `ProofLexPathLID`
- `0x18004ac28`: `GrammarLexPathLID`
- `0x18004ac19`: `HyphenatorLexPathLID`
- `0x18004ac0a`: `ThesaurusLexPathLID`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::ProofResourceLoader::ModulePathFor(
        struct IUnknown *this,
        __int64 a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        IID *a6)
{
  unsigned __int16 v6; // r12
  __int64 v7; // rbx
  struct IUnknown *v8; // r13
  unsigned int v10; // r14d
  const wchar_t *v11; // r15
  struct _variant_t *Option; // rax
  unsigned __int16 v13; // r11
  unsigned __int64 v14; // r12
  struct IUnknownVtbl *lpVtbl; // rcx
  char *v16; // r8
  __int64 v17; // rdx
  unsigned __int16 v18; // cx
  char v19; // [rsp+50h] [rbp-968h]
  unsigned __int16 v21; // [rsp+58h] [rbp-960h]
  unsigned __int16 v22; // [rsp+64h] [rbp-954h]
  unsigned __int16 v23; // [rsp+68h] [rbp-950h]
  _BYTE v24[24]; // [rsp+78h] [rbp-940h] BYREF
  struct IUnknown *v25; // [rsp+90h] [rbp-928h]
  __int64 v26; // [rsp+98h] [rbp-920h]
  unsigned __int64 i; // [rsp+A0h] [rbp-918h]
  __int64 v28; // [rsp+A8h] [rbp-910h]
  _com_error *v29; // [rsp+B0h] [rbp-908h] BYREF
  _BYTE pExceptionObject[136]; // [rsp+B8h] [rbp-900h] BYREF
  unsigned __int16 v31[264]; // [rsp+140h] [rbp-878h] BYREF
  _BYTE v32[528]; // [rsp+350h] [rbp-668h] BYREF
  unsigned __int16 v33[256]; // [rsp+560h] [rbp-458h] BYREF
  unsigned __int16 v34[264]; // [rsp+760h] [rbp-258h] BYREF
  const void *retaddr; // [rsp+9B8h] [rbp+0h]

  v28 = -2;
  v6 = a3;
  v23 = a3;
  v7 = a2;
  v8 = this;
  v25 = this;
  v26 = a2;
  if ( (a3 & 0x3FF) == 0x11 && a5 == 512 )
    goto LABEL_20;
  if ( (int)a5 <= 259 )
  {
    if ( a5 == 259 )
      goto LABEL_47;
    if ( a5 < 2 )
      goto LABEL_16;
    if ( a5 == 256 || a5 - 257 <= 1 )
    {
LABEL_47:
      if ( LOWORD(this[22].lpVtbl) )
      {
        *(_QWORD *)(a2 + 24) = 7;
        *(_QWORD *)(a2 + 16) = 0;
        *(_WORD *)a2 = 0;
        return v7;
      }
LABEL_16:
      ResourceLoader6::SimpleResourceLoader::ModulePathFor(this, a2, a3, a4, a5, a6);
      return v7;
    }
LABEL_15:
    CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  switch ( a5 )
  {
    case 0x200u:
      v10 = 0;
      v11 = L"ProofLexPathLID";
      break;
    case 0x201u:
LABEL_20:
      v10 = 3;
      v11 = L"GrammarLexPathLID";
      break;
    case 0x202u:
      v10 = 1;
      v11 = L"HyphenatorLexPathLID";
      break;
    case 0x203u:
      v10 = 2;
      v11 = L"ThesaurusLexPathLID";
      break;
    case 0x204u:
      goto LABEL_16;
    default:
      goto LABEL_15;
  }
  try
  {
    Option = (struct _variant_t *)ResourceLoader6::ILoadResources::GetOption(this, v24);
    v19 = _variant_t::operator bool(Option);
    _variant_t::~_variant_t((_variant_t *)v24);
  }
  catch ( _com_error *v29 )
  {
    ImxTraceCatch(1, *((unsigned int *)v29 + 2), retaddr);
    v8 = v25;
    v6 = a3;
    v23 = a3;
    v7 = v26;
  }
  Option = (struct _variant_t *)ResourceLoader6::ILoadResources::GetOption(this, v24);
  v19 = _variant_t::operator bool(Option);
  _variant_t::~_variant_t((_variant_t *)v24);
  ImxTraceCatch(1, *((unsigned int *)v29 + 2), retaddr);
}

```

## disassembly

```asm
0x18004aa70  push    rbx
0x18004aa72  push    rsi
0x18004aa73  push    rdi
0x18004aa74  push    r12
0x18004aa76  push    r13
0x18004aa78  push    r14
0x18004aa7a  push    r15
0x18004aa7c  sub     rsp, 980h
0x18004aa83  mov     [rsp+9B8h+var_910], 0FFFFFFFFFFFFFFFEh
0x18004aa8f  mov     rax, cs:__security_cookie
0x18004aa96  xor     rax, rsp
0x18004aa99  mov     [rsp+9B8h+var_48], rax
0x18004aaa1  movzx   r12d, r8w
0x18004aaa5  mov     [rsp+9B8h+var_950], r8w
0x18004aaab  mov     rbx, rdx
0x18004aaae  mov     r13, rcx
0x18004aab1  mov     [rsp+9B8h+var_928], rcx
0x18004aab9  mov     [rsp+9B8h+var_920], rdx
0x18004aac1  mov     [rsp+9B8h+var_960], r8w
0x18004aac7  mov     r8, [rsp+9B8h+arg_28]
0x18004aacf  xor     edi, edi
0x18004aad1  mov     esi, edi
0x18004aad3  mov     [rsp+9B8h+var_958], edi
0x18004aad7  movzx   eax, r12w
0x18004aadb  mov     ecx, 3FFh
0x18004aae0  and     ax, cx
0x18004aae3  mov     ecx, [rsp+9B8h+arg_20]
0x18004aaea  cmp     ax, 11h
0x18004aaee  jnz     short loc_18004AAFC
0x18004aaf0  cmp     ecx, 200h
0x18004aaf6  jz      loc_18004AC22
0x18004aafc  mov     eax, 103h
0x18004ab01  cmp     ecx, eax
0x18004ab03  jg      short loc_18004AB64
0x18004ab05  jz      short loc_18004AB2C
0x18004ab07  mov     edx, ecx
0x18004ab09  test    ecx, ecx
0x18004ab0b  jz      loc_18004ABBD
0x18004ab11  sub     edx, 1
0x18004ab14  jz      loc_18004ABBD
0x18004ab1a  sub     edx, 0FFh
0x18004ab20  jz      short loc_18004AB2C
0x18004ab22  sub     edx, 1
0x18004ab25  jz      short loc_18004AB2C
0x18004ab27  cmp     edx, 1
0x18004ab2a  jnz     short loc_18004AB8E
0x18004ab2c  cmp     [r13+0B0h], di
0x18004ab34  jz      short loc_18004AB4A
0x18004ab36  mov     qword ptr [rbx+18h], 7
0x18004ab3e  mov     [rbx+10h], rdi
0x18004ab42  mov     [rbx], di
0x18004ab45  jmp     loc_18004ABD6
0x18004ab4a  mov     [rsp+9B8h+var_990], r8
0x18004ab4f  mov     [rsp+9B8h+var_998], ecx
0x18004ab53  movzx   r8d, r12w
0x18004ab57  mov     rdx, rbx
0x18004ab5a  mov     rcx, r13
0x18004ab5d  call    ?ModulePathFor@SimpleResourceLoader@ResourceLoader6@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GPEBGW4ModuleType@2@PEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@@Z; ResourceLoader6::SimpleResourceLoader::ModulePathFor(ushort,ushort const *,ResourceLoader6::ModuleType,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *)
0x18004ab62  jmp     short loc_18004ABD6
0x18004ab64  mov     edx, ecx
0x18004ab66  sub     edx, 200h
0x18004ab6c  jz      loc_18004AC31
0x18004ab72  sub     edx, 1
0x18004ab75  jz      loc_18004AC22
0x18004ab7b  sub     edx, 1
0x18004ab7e  jz      loc_18004AC13
0x18004ab84  sub     edx, 1
0x18004ab87  jz      short loc_18004AC04
0x18004ab89  cmp     edx, 1
0x18004ab8c  jz      short loc_18004ABBD
0x18004ab8e  mov     r8, [rsp+9B8h]; void *
0x18004ab96  mov     edx, 80004005h; int
0x18004ab9b  lea     rcx, [rsp+9B8h+pExceptionObject]; this
0x18004aba3  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004aba8  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004abaf  lea     rcx, [rsp+9B8h+pExceptionObject]; pExceptionObject
0x18004abb7  call    _CxxThrowException_0
0x18004abbd  mov     [rsp+9B8h+var_990], r8
0x18004abc2  mov     [rsp+9B8h+var_998], ecx
0x18004abc6  movzx   r8d, r12w
0x18004abca  mov     rdx, rbx
0x18004abcd  mov     rcx, r13
0x18004abd0  call    ?ModulePathFor@SimpleResourceLoader@ResourceLoader6@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GPEBGW4ModuleType@2@PEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@@Z; ResourceLoader6::SimpleResourceLoader::ModulePathFor(ushort,ushort const *,ResourceLoader6::ModuleType,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *)
0x18004abd5  nop
0x18004abd6  mov     [rsp+9B8h+var_958], 1
0x18004abde  mov     rax, rbx
0x18004abe1  mov     rcx, [rsp+9B8h+var_48]
0x18004abe9  xor     rcx, rsp; StackCookie
0x18004abec  call    __security_check_cookie
0x18004abf1  add     rsp, 980h
0x18004abf8  pop     r15
0x18004abfa  pop     r14
0x18004abfc  pop     r13
0x18004abfe  pop     r12
0x18004ac00  pop     rdi
0x18004ac01  pop     rsi
0x18004ac02  pop     rbx
0x18004ac03  retn
0x18004ac04  mov     r14d, 2
0x18004ac0a  lea     r15, aThesauruslexpa; "ThesaurusLexPathLID"
0x18004ac11  jmp     short loc_18004AC3B
0x18004ac13  mov     r14d, 1
0x18004ac19  lea     r15, aHyphenatorlexp; "HyphenatorLexPathLID"
0x18004ac20  jmp     short loc_18004AC3B
0x18004ac22  mov     r14d, 3
0x18004ac28  lea     r15, aGrammarlexpath; "GrammarLexPathLID"
0x18004ac2f  jmp     short loc_18004AC3B
0x18004ac31  mov     r14d, edi
0x18004ac34  lea     r15, aProoflexpathli_0; "ProofLexPathLID"
0x18004ac3b  mov     [rsp+9B8h+var_948], r15
0x18004ac40  mov     [rsp+9B8h+var_954], r14d
0x18004ac45  mov     [rsp+9B8h+var_968], dil
0x18004ac4a  lea     rdx, [rsp+9B8h+var_940]
0x18004ac4f  mov     rcx, r13
0x18004ac52  call    ?GetOption@ILoadResources@ResourceLoader6@@QEAA?AV_variant_t@@PEAG@Z; ResourceLoader6::ILoadResources::GetOption(ushort *)
0x18004ac57  nop
0x18004ac58  mov     rcx, rax; struct _variant_t *
0x18004ac5b  call    ??B_variant_t@@QEBA_NXZ; _variant_t::operator bool(void)
0x18004ac60  mov     [rsp+9B8h+var_968], al
0x18004ac64  lea     rcx, [rsp+9B8h+var_940]; this
0x18004ac69  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004ac6e  nop
0x18004ac6f  jmp     short loc_18004AC9D
0x18004ac71  xor     edi, edi
0x18004ac73  mov     r14d, [rsp+9B8h+var_954]
0x18004ac78  mov     r15, [rsp+9B8h+var_948]
0x18004ac7d  mov     esi, [rsp+9B8h+var_958]
0x18004ac81  mov     r13, [rsp+9B8h+var_928]
0x18004ac89  movzx   r12d, [rsp+9B8h+var_960]
0x18004ac8f  mov     [rsp+9B8h+var_950], r12w
0x18004ac95  mov     rbx, [rsp+9B8h+var_920]
0x18004ac9d  xor     edx, edx; Val
0x18004ac9f  mov     r8d, 20Ah; Size
0x18004aca5  lea     rcx, [rsp+9B8h+var_668]; void *
0x18004acad  call    memset_0
0x18004acb2  xor     edx, edx; Val
0x18004acb4  mov     r8d, 20Ah; Size
0x18004acba  lea     rcx, [rsp+9B8h+var_878]; void *
0x18004acc2  call    memset_0
0x18004acc7  test    r14d, r14d
0x18004acca  jnz     short loc_18004ACE5
0x18004accc  lea     rdx, [r13+0B0h]
0x18004acd3  cmp     [rdx], di
0x18004acd6  jz      short loc_18004ACE5
0x18004acd8  mov     rcx, rbx
0x18004acdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004ace0  jmp     loc_18004ABD6
0x18004ace5  movzx   ecx, r12w
0x18004ace9  mov     [rsp+9B8h+var_960], cx
0x18004acee  movzx   r11d, cx
0x18004acf2  mov     word ptr [rsp+9B8h+var_954], cx
0x18004acf7  mov     r12, rdi
0x18004acfa  mov     [rsp+9B8h+var_918], rdi
0x18004ad02  mov     rcx, [r13+10h]
0x18004ad06  mov     rax, [r13+18h]
0x18004ad0a  sub     rax, rcx
0x18004ad0d  sar     rax, 5
0x18004ad11  cmp     r12, rax
0x18004ad14  jnb     loc_18004AE67
0x18004ad1a  mov     r8, r12
0x18004ad1d  shl     r8, 5
0x18004ad21  add     r8, rcx
0x18004ad24  cmp     qword ptr [r8+18h], 8
0x18004ad29  jb      short loc_18004AD2E
0x18004ad2b  mov     r8, [r8]; unsigned __int16 *
0x18004ad2e  mov     edx, 105h; unsigned __int64
0x18004ad33  lea     rcx, [rsp+9B8h+var_258]; unsigned __int16 *
0x18004ad3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ad40  test    eax, eax
0x18004ad42  js      loc_18004AE57
0x18004ad48  lea     rax, [rsp+9B8h+var_258]
0x18004ad50  mov     [rsp+9B8h+var_980], rax
0x18004ad55  lea     rax, [rsp+9B8h+var_878]
0x18004ad5d  mov     [rsp+9B8h+var_990], rax
0x18004ad62  lea     r9, [rsp+9B8h+var_668]
0x18004ad6a  mov     r8d, r14d
0x18004ad6d  mov     dl, [rsp+9B8h+var_968]
0x18004ad71  movzx   ecx, r11w
0x18004ad75  call    ?FindStandardProofFiles@FindProof@NLG@@SA_NG_NW4proofType@12@PEAGH2H2H@Z; NLG::FindProof::FindStandardProofFiles(ushort,bool,NLG::FindProof::proofType,ushort *,int,ushort *,int,ushort *,int)
0x18004ad7a  test    al, al
0x18004ad7c  jz      loc_18004AE51
0x18004ad82  lea     rdx, [rsp+9B8h+var_878]; unsigned __int16 *
0x18004ad8a  lea     rcx, [rsp+9B8h+var_940]; this
0x18004ad8f  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004ad94  nop
0x18004ad95  lea     r8, [rsp+9B8h+var_940]; struct _variant_t *
0x18004ad9a  lea     rdx, aProoflexpath; "ProofLexPath"
0x18004ada1  mov     rcx, r13; this
0x18004ada4  call    ?PutOption@ILoadResources@ResourceLoader6@@QEAAXPEAGAEBV_variant_t@@@Z; ResourceLoader6::ILoadResources::PutOption(ushort *,_variant_t const &)
0x18004ada9  nop
0x18004adaa  lea     rcx, [rsp+9B8h+var_940]; this
0x18004adaf  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004adb4  movzx   eax, [rsp+9B8h+var_950]
0x18004adb9  mov     [rsp+9B8h+var_998], eax
0x18004adbd  mov     r9, r15
0x18004adc0  lea     r8, aS04x; "%s%04x"
0x18004adc7  mov     edx, 100h; unsigned __int64
0x18004adcc  lea     rcx, [rsp+9B8h+var_458]; unsigned __int16 *
0x18004add4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004add9  test    eax, eax
0x18004addb  js      short loc_18004AE2F
0x18004addd  lea     rdx, [rsp+9B8h+var_878]; unsigned __int16 *
0x18004ade5  lea     rcx, [rsp+9B8h+var_940]; this
0x18004adea  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004adef  nop
0x18004adf0  lea     r8, [rsp+9B8h+var_940]; struct _variant_t *
0x18004adf5  lea     rdx, [rsp+9B8h+var_458]; unsigned __int16 *
0x18004adfd  mov     rcx, r13; this
0x18004ae00  call    ?PutOption@ILoadResources@ResourceLoader6@@QEAAXPEAGAEBV_variant_t@@@Z; ResourceLoader6::ILoadResources::PutOption(ushort *,_variant_t const &)
0x18004ae05  nop
0x18004ae06  lea     rcx, [rsp+9B8h+var_940]; this
0x18004ae0b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004ae10  lea     rdx, [rsp+9B8h+var_668]
0x18004ae18  mov     rcx, rbx
0x18004ae1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004ae20  or      esi, 1
0x18004ae23  mov     [rsp+9B8h+var_958], esi
0x18004ae27  mov     rax, rbx
0x18004ae2a  jmp     loc_18004ABE1
0x18004ae2f  mov     [rbx+10h], rdi
0x18004ae33  mov     [rbx+18h], rdi
0x18004ae37  mov     qword ptr [rbx+18h], 7
0x18004ae3f  mov     [rbx], di
0x18004ae42  or      esi, 1
0x18004ae45  mov     [rsp+9B8h+var_958], esi
0x18004ae49  mov     rax, rbx
0x18004ae4c  jmp     loc_18004ABE1
0x18004ae51  movzx   r11d, word ptr [rsp+9B8h+var_954]
0x18004ae57  inc     r12
0x18004ae5a  mov     [rsp+9B8h+var_918], r12
0x18004ae62  jmp     loc_18004AD02
0x18004ae67  movzx   ecx, [rsp+9B8h+var_960]
0x18004ae6c  mov     eax, 3FFh
0x18004ae71  and     cx, ax
0x18004ae74  mov     [rsp+9B8h+var_960], cx
0x18004ae79  cmp     r11w, cx
0x18004ae7d  jnz     loc_18004ACEE
0x18004ae83  mov     qword ptr [rbx+18h], 7
0x18004ae8b  mov     [rbx+10h], rdi
0x18004ae8f  mov     [rbx], di
0x18004ae92  or      esi, 1
0x18004ae95  mov     [rsp+9B8h+var_958], esi
0x18004ae99  jmp     loc_18004ABDE
```

# _anonymous_namespace_::AddSaltedSession

- ea: `0x14005a97c`
- end: `0x14005ac69`
- name: `_anonymous_namespace_::AddSaltedSession`
- size: `749`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_SESSION *this, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14005ac70`

## callees

- `0x140007410`
- `0x14000e034`
- `0x14000fc8c`
- `0x14003d38c`
- `0x14003d3cc`
- `0x14005a97c`
- `0x14005c400`
- `0x14005c5c4`
- `0x1400624d4`
- `0x140062520`
- `0x140063ba0`
- `0x140064680`
- `0x140065c28`
- `0x1400698a4`
- `0x140069958`
- `0x140071010`

## string_xrefs

- `0x14005a9bd`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005aa5d`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005aafb`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005abda`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`
- `0x14005ac24`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::AddSaltedSession(
        tpm12class::TPMW8_SESSION *this,
        struct tpm12class::TPMW82B_BUFFER *a2,
        char a3)
{
  unsigned int TpmBindingItem; // ebx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rcx
  __int64 v8; // rdx
  unsigned __int16 v9; // r8
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // edx
  int v13; // eax
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  tpm12class::TPMW8_AUTH_PROVIDER *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  char v21; // [rsp+30h] [rbp-D0h]
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+70h] [rbp-90h]
  __int16 v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  _QWORD v29[3]; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  char v33; // [rsp+C0h] [rbp-40h]
  __int16 v34; // [rsp+C8h] [rbp-38h]
  __int64 v35; // [rsp+D0h] [rbp-30h]
  _BYTE v36[196]; // [rsp+E0h] [rbp-20h] BYREF
  int v37; // [rsp+1A4h] [rbp+A4h]
  __int64 v38; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]
  __int64 v40; // [rsp+270h] [rbp+170h] BYREF
  tpm12class::TPMW8_AUTH_PROVIDER *v41; // [rsp+288h] [rbp+188h]

  if ( this )
  {
    v22[1] = 0;
    v22[2] = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v22[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v27 = 0;
    v28 = 0;
    ProcessParameters = NtCurrentPeb()->ProcessParameters;
    if ( (ProcessParameters->Flags & 0x80000000) == 0 )
    {
      tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
      v37 = -2130706431;
      v11 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v36, 0);
      v13 = VsmUtils::MapTpmError((VsmUtils *)v11, v12);
      TpmBindingItem = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
          (const char *)(unsigned int)v13,
          v19[0]);
        tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
LABEL_24:
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v22);
        return TpmBindingItem;
      }
      tpm12class::TPMW82B_BUFFER::CopyFrom(
        (tpm12class::TPMW82B_BUFFER *)v22,
        (const struct tpm12class::TPMW82B_BUFFER *)(v38 + 760));
      tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v36);
    }
    else
    {
      v40 = 0;
      *(_QWORD *)v19 = &v40;
      v20 = 0;
      v21 = 1;
      TpmBindingItem = VsmUtils::GetTpmBindingItem(ProcessParameters, &v20);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(v19);
      if ( (TpmBindingItem & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
          (const char *)TpmBindingItem,
          v19[0]);
        v8 = v40;
        v40 = 0;
        if ( v8 )
          wil::hlocal_secure_deleter::operator()<unsigned char>();
        goto LABEL_24;
      }
      tpm12class::TPMW82B_BUFFER::CopyFrom(
        (tpm12class::TPMW82B_BUFFER *)v22,
        (const unsigned __int8 *)(v40 + 22),
        *(unsigned __int16 *)(v40 + 20));
      v10 = v40;
      v40 = 0;
      if ( v10 )
        wil::hlocal_secure_deleter::operator()<unsigned char>();
    }
    if ( a2 )
    {
      v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 97);
      if ( v14 )
        (**v14)(v14, 1);
      *((_QWORD *)this + 97) = 0;
      v29[1] = 0;
      v29[2] = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v29[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
      v34 = 0;
      v35 = 0;
      v15 = (tpm12class::TPMW8_AUTH_PROVIDER *)operator new(0x178u, (const struct std::nothrow_t *)std::nothrow);
      v41 = v15;
      if ( v15 )
        v16 = tpm12class::TPMW8_AUTH_PROVIDER::TPMW8_AUTH_PROVIDER(
                v15,
                (const struct tpm12class::TPMW82B_BUFFER *)v29,
                a2);
      else
        v16 = 0;
      *((_QWORD *)this + 97) = v16;
      if ( !v16 )
      {
        TpmBindingItem = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
          (const char *)0x8007000ELL,
          v19[0]);
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v29);
        goto LABEL_24;
      }
      tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v29);
    }
    *((_WORD *)this + 381) = 11;
    v17 = tpm12class::TPMW8_SESSION::AddSalt(this, v10, v9, (struct tpm12class::TPMW82B_BUFFER *)v22);
    TpmBindingItem = v17;
    if ( v17 >= 0 )
    {
      *((_BYTE *)this + 764) = a3;
      TpmBindingItem = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
        (const char *)(unsigned int)v17,
        v19[0]);
    }
    goto LABEL_24;
  }
  TpmBindingItem = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmhelper.cpp",
    (const char *)0x80004003LL,
    v19[0]);
  return TpmBindingItem;
}

```

## disassembly

```asm
0x14005a97c  mov     [rsp-8+arg_8], rbx
0x14005a981  mov     [rsp-8+arg_10], rsi
0x14005a986  push    rbp
0x14005a987  push    rdi
0x14005a988  push    r12
0x14005a98a  push    r14
0x14005a98c  push    r15
0x14005a98e  lea     rbp, [rsp-140h]
0x14005a996  sub     rsp, 240h
0x14005a99d  mov     r14b, r8b
0x14005a9a0  mov     rsi, rdx
0x14005a9a3  mov     rdi, rcx
0x14005a9a6  xor     r15d, r15d
0x14005a9a9  test    rcx, rcx
0x14005a9ac  jnz     short loc_14005A9D1
0x14005a9ae  mov     rcx, [rbp+168h]; this
0x14005a9b5  mov     ebx, 80004003h
0x14005a9ba  mov     r9d, ebx; char *
0x14005a9bd  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005a9c4  lea     edx, [rdi+25h]; void *
0x14005a9c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005a9cc  jmp     loc_14005AC4B
0x14005a9d1  mov     [rsp+260h+var_218], r15
0x14005a9d6  mov     [rsp+260h+var_210], r15
0x14005a9db  mov     [rsp+260h+var_208], r15d
0x14005a9e0  mov     [rsp+260h+var_200], r15
0x14005a9e5  mov     [rsp+260h+var_1F8], r15
0x14005a9ea  mov     [rsp+260h+var_1F0], r15b
0x14005a9ef  lea     r12, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x14005a9f6  mov     [rsp+260h+var_220], r12
0x14005a9fb  mov     [rsp+260h+var_1E8], r15w
0x14005aa01  mov     [rbp+160h+var_1E0], r15
0x14005aa05  mov     rax, gs:60h
0x14005aa0e  mov     rcx, [rax+20h]
0x14005aa12  cmp     [rcx+8], r15d
0x14005aa16  jge     loc_14005AAC5
0x14005aa1c  mov     [rbp+160h+arg_0], r15
0x14005aa23  lea     rax, [rbp+160h+arg_0]
0x14005aa2a  mov     qword ptr [rsp+260h+var_240], rax; int
0x14005aa2f  mov     [rsp+260h+var_238], r15
0x14005aa34  mov     [rsp+260h+var_230], 1
0x14005aa39  lea     rdx, [rsp+260h+var_238]
0x14005aa3e  call    ?GetTpmBindingItem@VsmUtils@@YAJW4tag_TPM_BINDING_ITEM_TYPE@@PEAPEAE@Z; VsmUtils::GetTpmBindingItem(tag_TPM_BINDING_ITEM_TYPE,uchar * *)
0x14005aa43  mov     ebx, eax
0x14005aa45  lea     rcx, [rsp+260h+var_240]
0x14005aa4a  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x14005aa4f  test    ebx, ebx
0x14005aa51  jns     short loc_14005AA90
0x14005aa53  mov     rcx, [rbp+168h]; this
0x14005aa5a  mov     r9d, ebx; char *
0x14005aa5d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005aa64  mov     edx, 2Ch ; ','; void *
0x14005aa69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005aa6e  nop
0x14005aa6f  mov     rdx, [rbp+160h+arg_0]
0x14005aa76  mov     [rbp+160h+arg_0], r15
0x14005aa7d  test    rdx, rdx
0x14005aa80  jz      loc_14005AC41
0x14005aa86  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x14005aa8b  jmp     loc_14005AC41
0x14005aa90  mov     rdx, [rbp+160h+arg_0]
0x14005aa97  movzx   r8d, word ptr [rdx+14h]; unsigned __int64
0x14005aa9c  add     rdx, 16h; unsigned __int8 *
0x14005aaa0  lea     rcx, [rsp+260h+var_220]; this
0x14005aaa5  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005aaaa  nop
0x14005aaab  mov     rdx, [rbp+160h+arg_0]
0x14005aab2  mov     [rbp+160h+arg_0], r15
0x14005aab9  test    rdx, rdx
0x14005aabc  jz      short loc_14005AB3D
0x14005aabe  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x14005aac3  jmp     short loc_14005AB3D
0x14005aac5  lea     rcx, [rbp+160h+var_180]; this
0x14005aac9  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x14005aace  nop
0x14005aacf  mov     [rbp+160h+var_BC], 81000001h
0x14005aad9  xor     edx, edx; void *
0x14005aadb  lea     rcx, [rbp+160h+var_180]; this
0x14005aadf  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14005aae4  mov     ecx, eax; this
0x14005aae6  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x14005aaeb  mov     ebx, eax
0x14005aaed  test    eax, eax
0x14005aaef  jns     short loc_14005AB1B
0x14005aaf1  mov     rcx, [rbp+168h]; this
0x14005aaf8  mov     r9d, eax; char *
0x14005aafb  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005ab02  mov     edx, 37h ; '7'; void *
0x14005ab07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ab0c  nop
0x14005ab0d  lea     rcx, [rbp+160h+var_180]; this
0x14005ab11  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x14005ab16  jmp     loc_14005AC41
0x14005ab1b  mov     rdx, [rbp+160h+var_B8]
0x14005ab22  add     rdx, 2F8h; struct tpm12class::TPMW82B_BUFFER *
0x14005ab29  lea     rcx, [rsp+260h+var_220]; this
0x14005ab2e  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x14005ab33  nop
0x14005ab34  lea     rcx, [rbp+160h+var_180]; this
0x14005ab38  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x14005ab3d  test    rsi, rsi
0x14005ab40  jz      loc_14005ABFE
0x14005ab46  mov     rcx, [rdi+308h]
0x14005ab4d  test    rcx, rcx
0x14005ab50  jz      short loc_14005AB62
0x14005ab52  mov     rax, [rcx]
0x14005ab55  mov     edx, 1
0x14005ab5a  mov     rax, [rax]
0x14005ab5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ab62  mov     [rdi+308h], r15
0x14005ab69  mov     [rbp+160h+var_1C8], r15
0x14005ab6d  mov     [rbp+160h+var_1C0], r15
0x14005ab71  mov     [rbp+160h+var_1B8], r15d
0x14005ab75  mov     [rbp+160h+var_1B0], r15
0x14005ab79  mov     [rbp+160h+var_1A8], r15
0x14005ab7d  mov     [rbp+160h+var_1A0], r15b
0x14005ab81  mov     [rbp+160h+var_1D0], r12
0x14005ab85  mov     [rbp+160h+var_198], r15w
0x14005ab8a  mov     [rbp+160h+var_190], r15
0x14005ab8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005ab95  mov     ecx, 178h; unsigned __int64
0x14005ab9a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14005ab9f  mov     [rbp+160h+arg_18], rax
0x14005aba6  test    rax, rax
0x14005aba9  jz      short loc_14005ABBC
0x14005abab  mov     r8, rsi; struct tpm12class::TPMW82B_BUFFER *
0x14005abae  lea     rdx, [rbp+160h+var_1D0]; struct tpm12class::TPMW82B_BUFFER *
0x14005abb2  mov     rcx, rax; this
0x14005abb5  call    ??0TPMW8_AUTH_PROVIDER@tpm12class@@QEAA@PEBVTPMW82B_BUFFER@1@0@Z; tpm12class::TPMW8_AUTH_PROVIDER::TPMW8_AUTH_PROVIDER(tpm12class::TPMW82B_BUFFER const *,tpm12class::TPMW82B_BUFFER const *)
0x14005abba  jmp     short loc_14005ABBF
0x14005abbc  mov     rax, r15
0x14005abbf  mov     [rdi+308h], rax
0x14005abc6  test    rax, rax
0x14005abc9  jnz     short loc_14005ABF5
0x14005abcb  mov     rcx, [rbp+168h]; this
0x14005abd2  mov     ebx, 8007000Eh
0x14005abd7  mov     r9d, ebx; char *
0x14005abda  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005abe1  lea     edx, [rax+45h]; void *
0x14005abe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005abe9  nop
0x14005abea  lea     rcx, [rbp+160h+var_1D0]; this
0x14005abee  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005abf3  jmp     short loc_14005AC41
0x14005abf5  lea     rcx, [rbp+160h+var_1D0]; this
0x14005abf9  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005abfe  mov     word ptr [rdi+2FAh], 0Bh
0x14005ac07  lea     r9, [rsp+260h+var_220]; struct tpm12class::TPMW82B_BUFFER *
0x14005ac0c  mov     rcx, rdi; this
0x14005ac0f  call    ?AddSalt@TPMW8_SESSION@tpm12class@@QEAAJIGPEAVTPMW82B_BUFFER@2@@Z; tpm12class::TPMW8_SESSION::AddSalt(uint,ushort,tpm12class::TPMW82B_BUFFER *)
0x14005ac14  mov     ebx, eax
0x14005ac16  test    eax, eax
0x14005ac18  jns     short loc_14005AC37
0x14005ac1a  mov     rcx, [rbp+168h]; this
0x14005ac21  mov     r9d, eax; char *
0x14005ac24  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\trustlet\\utils"...
0x14005ac2b  mov     edx, 4Ch ; 'L'; void *
0x14005ac30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ac35  jmp     short loc_14005AC41
0x14005ac37  mov     [rdi+2FCh], r14b
0x14005ac3e  mov     ebx, r15d
0x14005ac41  lea     rcx, [rsp+260h+var_220]; this
0x14005ac46  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x14005ac4b  mov     eax, ebx
0x14005ac4d  lea     r11, [rsp+260h+var_20]
0x14005ac55  mov     rbx, [r11+38h]
0x14005ac59  mov     rsi, [r11+40h]
0x14005ac5d  mov     rsp, r11
0x14005ac60  pop     r15
0x14005ac62  pop     r14
0x14005ac64  pop     r12
0x14005ac66  pop     rdi
0x14005ac67  pop     rbp
0x14005ac68  retn
```

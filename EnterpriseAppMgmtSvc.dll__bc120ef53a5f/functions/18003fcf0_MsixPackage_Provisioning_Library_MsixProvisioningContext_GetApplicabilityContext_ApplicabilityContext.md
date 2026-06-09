# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetApplicabilityContext(ApplicabilityContext * *)

- ea: `0x18003fcf0`
- end: `0x18003ff0c`
- name: `?GetApplicabilityContext@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEAPEAVApplicabilityContext@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct ApplicabilityContext **)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180036618`
- `0x1800562d4`
- `0x18005a710`

## callees

- `0x18000d3dc`
- `0x18003d4ec`
- `0x18003fcf0`
- `0x180042c94`
- `0x180062828`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fdae`

## string_xrefs

- `0x18003fe4c`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003fe86`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003fea3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003fedf`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003fe92`: `Failed to create applicability context.`
- `0x18003fd6c`: `CreateApplicabilityContext`
- `0x18003fe3d`: `Unable to GetProcAddress 'CreateApplicabilityContext'`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::GetApplicabilityContext(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this,
        struct ApplicabilityContext **a2)
{
  _QWORD *v2; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  char *v8; // rbp
  int Dynamic; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v12; // sf
  signed int v13; // eax
  unsigned __int64 i; // rbx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD); // rax
  int v16; // eax
  __int64 v17; // rdx
  DWORD v18; // r8d
  unsigned int v19; // ebp
  const char *v20; // rax
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-48h]
  char *v24; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a2 = 0;
  v2 = (_QWORD *)((char *)this + 752);
  if ( *((_DWORD *)this + 190) )
  {
LABEL_29:
    *a2 = (struct ApplicabilityContext *)*v2;
    return 0;
  }
  if ( this == (MsixPackage::Provisioning::Library::MsixProvisioningContext *)-752LL )
  {
    v5 = -2147024809;
    v6 = 706;
    v7 = 2147942487LL;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)v7,
      v23);
    goto LABEL_26;
  }
  v8 = (char *)this + 128;
  *v2 = 0;
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic((_QWORD *)this + 16);
  v5 = Dynamic;
  if ( Dynamic < 0 )
  {
    v6 = 709;
LABEL_24:
    v7 = (unsigned int)Dynamic;
    goto LABEL_25;
  }
  ProcAddress = (FARPROC)*((_QWORD *)v8 + 9);
  if ( ProcAddress
    || (ProcAddress = GetProcAddress(*((HMODULE *)v8 + 1), "CreateApplicabilityContext"),
        (*((_QWORD *)v8 + 9) = ProcAddress) != 0) )
  {
    Dynamic = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
    v5 = Dynamic;
    if ( Dynamic < 0 )
    {
      v6 = 721;
      goto LABEL_24;
    }
    goto LABEL_14;
  }
  LastError = GetLastError();
  v12 = LastError < 0;
  if ( LastError > 0 )
    v12 = 1;
  if ( v12 )
  {
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
LABEL_14:
      for ( i = 0; i < 3; ++i )
      {
        v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD))(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
        v16 = (**v15)(v15, *(unsigned int *)&aD_0[4 * i]);
        v19 = v16;
        if ( v16 < 0 )
        {
          LODWORD(v24) = *(_DWORD *)&aD_0[4 * i];
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
            (const char *)(unsigned int)v16,
            (int)"Failed to add scale %d to applicability context.",
            v24);
          return v19;
        }
      }
      if ( !(unsigned int)MUIOffline_EnumUILanguages(*((_WORD **)this + 68), v17, v18, (__int64)this) )
      {
        v20 = "Failed to enumerate languages.";
        v5 = -2147418113;
        v21 = 102;
        goto LABEL_27;
      }
      *((_DWORD *)this + 190) = 1;
      goto LABEL_29;
    }
  }
  else
  {
    v5 = -2147467259;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x2CD,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
    (const char *)v5,
    (int)"Unable to GetProcAddress 'CreateApplicabilityContext'",
    v24);
LABEL_26:
  v20 = "Failed to create applicability context.";
  v21 = 89;
LABEL_27:
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)v21,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
    (const char *)v5,
    (int)v20,
    v24);
  return v5;
}

```

## disassembly

```asm
0x18003fcf0  push    rbx
0x18003fcf2  push    rbp
0x18003fcf3  push    rsi
0x18003fcf4  push    rdi
0x18003fcf5  push    r12
0x18003fcf7  push    r14
0x18003fcf9  sub     rsp, 38h
0x18003fcfd  mov     qword ptr [rdx], 0
0x18003fd04  lea     rdi, [rcx+2F0h]
0x18003fd0b  cmp     dword ptr [rcx+2F8h], 0
0x18003fd12  mov     r14, rdx
0x18003fd15  mov     rsi, rcx
0x18003fd18  jnz     loc_18003FEC5
0x18003fd1e  test    rdi, rdi
0x18003fd21  jnz     short loc_18003FD35
0x18003fd23  mov     ebx, 80070057h
0x18003fd28  mov     edx, 2C2h
0x18003fd2d  mov     r9d, ebx
0x18003fd30  jmp     loc_18003FE81
0x18003fd35  lea     rbp, [rcx+80h]
0x18003fd3c  mov     qword ptr [rdi], 0
0x18003fd43  mov     rcx, rbp
0x18003fd46  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixApplicabilityEngine@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(void)
0x18003fd4b  mov     ebx, eax
0x18003fd4d  test    eax, eax
0x18003fd4f  jns     short loc_18003FD5B
0x18003fd51  mov     edx, 2C5h
0x18003fd56  jmp     loc_18003FE7E
0x18003fd5b  mov     rax, [rbp+48h]
0x18003fd5f  test    rax, rax
0x18003fd62  jnz     loc_18003FE67
0x18003fd68  mov     rcx, [rbp+8]; hModule
0x18003fd6c  lea     rdx, aCreateapplicab; "CreateApplicabilityContext"
0x18003fd73  call    cs:__imp_GetProcAddress
0x18003fd7a  nop     dword ptr [rax+rax+00h]
0x18003fd7f  mov     [rbp+48h], rax
0x18003fd83  test    rax, rax
0x18003fd86  jnz     loc_18003FE67
0x18003fd8c  call    cs:__imp_GetLastError
0x18003fd93  nop     dword ptr [rax+rax+00h]
0x18003fd98  mov     ebp, 80070000h
0x18003fd9d  test    eax, eax
0x18003fd9f  jle     short loc_18003FDA8
0x18003fda1  movzx   eax, ax
0x18003fda4  or      eax, ebp
0x18003fda6  test    eax, eax
0x18003fda8  jns     loc_18003FE33
0x18003fdae  call    cs:__imp_GetLastError
0x18003fdb5  nop     dword ptr [rax+rax+00h]
0x18003fdba  mov     ebx, eax
0x18003fdbc  test    eax, eax
0x18003fdbe  jle     short loc_18003FDC5
0x18003fdc0  movzx   ebx, ax
0x18003fdc3  or      ebx, ebp
0x18003fdc5  test    ebx, ebx
0x18003fdc7  js      short loc_18003FE38
0x18003fdc9  xor     ebx, ebx
0x18003fdcb  mov     rcx, [rdi]
0x18003fdce  mov     rax, [rcx]
0x18003fdd1  mov     rax, [rax+8]
0x18003fdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdda  mov     r8, rax
0x18003fddd  lea     r12, aD_0; "d"
0x18003fde4  mov     edx, [r12+rbx*4]
0x18003fde8  mov     rcx, [rax]
0x18003fdeb  mov     rax, [rcx]
0x18003fdee  mov     rcx, r8
0x18003fdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdf6  mov     ebp, eax
0x18003fdf8  test    eax, eax
0x18003fdfa  js      loc_18003FEDB
0x18003fe00  inc     rbx
0x18003fe03  cmp     rbx, 3
0x18003fe07  jb      short loc_18003FDCB
0x18003fe09  mov     rcx, [rsi+220h]
0x18003fe10  mov     r9, rsi
0x18003fe13  call    MUIOffline_EnumUILanguages
0x18003fe18  test    eax, eax
0x18003fe1a  jnz     loc_18003FEBB
0x18003fe20  lea     rax, aFailedToEnumer; "Failed to enumerate languages."
0x18003fe27  mov     ebx, 8000FFFFh
0x18003fe2c  mov     edx, 66h ; 'f'
0x18003fe31  jmp     short loc_18003FE9E
0x18003fe33  mov     ebx, 80004005h
0x18003fe38  mov     rcx, [rsp+68h]; this
0x18003fe3d  lea     rax, aUnableToGetpro_8; "Unable to GetProcAddress 'CreateApplica"...
0x18003fe44  mov     r9d, ebx; char *
0x18003fe47  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003fe4c  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fe53  mov     edx, 2CDh; void *
0x18003fe58  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003fe5d  test    ebx, ebx
0x18003fe5f  jns     loc_18003FDC9
0x18003fe65  jmp     short loc_18003FE92
0x18003fe67  mov     rcx, rdi
0x18003fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe6f  mov     ebx, eax
0x18003fe71  test    eax, eax
0x18003fe73  jns     loc_18003FDC9
0x18003fe79  mov     edx, 2D1h; void *
0x18003fe7e  mov     r9d, eax; char *
0x18003fe81  mov     rcx, [rsp+68h]; this
0x18003fe86  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fe8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe92  lea     rax, aFailedToCreate_18; "Failed to create applicability context."
0x18003fe99  mov     edx, 59h ; 'Y'; void *
0x18003fe9e  mov     rcx, [rsp+68h]; this
0x18003fea3  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003feaa  mov     r9d, ebx; char *
0x18003fead  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003feb2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003feb7  mov     eax, ebx
0x18003feb9  jmp     short loc_18003FECD
0x18003febb  mov     dword ptr [rsi+2F8h], 1
0x18003fec5  mov     rax, [rdi]
0x18003fec8  mov     [r14], rax
0x18003fecb  xor     eax, eax
0x18003fecd  add     rsp, 38h
0x18003fed1  pop     r14
0x18003fed3  pop     r12
0x18003fed5  pop     rdi
0x18003fed6  pop     rsi
0x18003fed7  pop     rbp
0x18003fed8  pop     rbx
0x18003fed9  retn
0x18003fedb  mov     eax, [r12+rbx*4]
0x18003fedf  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fee6  mov     rcx, [rsp+68h]; this
0x18003feeb  mov     r9d, ebp; char *
0x18003feee  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18003fef2  mov     edx, 61h ; 'a'; void *
0x18003fef7  lea     rax, aFailedToAddSca; "Failed to add scale %d to applicability"...
0x18003fefe  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003ff03  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ff08  mov     eax, ebp
0x18003ff0a  jmp     short loc_18003FECD
```

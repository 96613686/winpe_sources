# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetApplicabilityContext(ApplicabilityContext * *)

- ea: `0x18003c534`
- end: `0x18003c739`
- name: `?GetApplicabilityContext@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEAPEAVApplicabilityContext@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct ApplicabilityContext **)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800335d8`
- `0x180051edc`
- `0x1800560f8`

## callees

- `0x18000cfe8`
- `0x180039e9c`
- `0x18003c534`
- `0x18003f240`
- `0x18005db94`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c5b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5e2`

## string_xrefs

- `0x18003c67a`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003c6b4`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003c6d1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c70c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c6c0`: `Failed to create applicability context.`
- `0x18003c66b`: `Unable to GetProcAddress 'CreateApplicabilityContext'`
- `0x18003c5b0`: `CreateApplicabilityContext`

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
        v16 = (**v15)(v15, *(unsigned int *)&aD_0[2 * i]);
        v19 = v16;
        if ( v16 < 0 )
        {
          LODWORD(v24) = *(_DWORD *)&aD_0[2 * i];
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
0x18003c534  push    rbx
0x18003c536  push    rbp
0x18003c537  push    rsi
0x18003c538  push    rdi
0x18003c539  push    r12
0x18003c53b  push    r14
0x18003c53d  sub     rsp, 38h
0x18003c541  mov     qword ptr [rdx], 0
0x18003c548  lea     rdi, [rcx+2F0h]
0x18003c54f  cmp     dword ptr [rcx+2F8h], 0
0x18003c556  mov     r14, rdx
0x18003c559  mov     rsi, rcx
0x18003c55c  jnz     loc_18003C6F3
0x18003c562  test    rdi, rdi
0x18003c565  jnz     short loc_18003C579
0x18003c567  mov     ebx, 80070057h
0x18003c56c  mov     edx, 2C2h
0x18003c571  mov     r9d, ebx
0x18003c574  jmp     loc_18003C6AF
0x18003c579  lea     rbp, [rcx+80h]
0x18003c580  mov     qword ptr [rdi], 0
0x18003c587  mov     rcx, rbp
0x18003c58a  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixApplicabilityEngine@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(void)
0x18003c58f  mov     ebx, eax
0x18003c591  test    eax, eax
0x18003c593  jns     short loc_18003C59F
0x18003c595  mov     edx, 2C5h
0x18003c59a  jmp     loc_18003C6AC
0x18003c59f  mov     rax, [rbp+48h]
0x18003c5a3  test    rax, rax
0x18003c5a6  jnz     loc_18003C695
0x18003c5ac  mov     rcx, [rbp+8]; hModule
0x18003c5b0  lea     rdx, aCreateapplicab; "CreateApplicabilityContext"
0x18003c5b7  call    cs:__imp_GetProcAddress
0x18003c5bd  mov     [rbp+48h], rax
0x18003c5c1  test    rax, rax
0x18003c5c4  jnz     loc_18003C695
0x18003c5ca  call    cs:__imp_GetLastError
0x18003c5d0  mov     ebp, 80070000h
0x18003c5d5  test    eax, eax
0x18003c5d7  jle     short loc_18003C5E0
0x18003c5d9  movzx   eax, ax
0x18003c5dc  or      eax, ebp
0x18003c5de  test    eax, eax
0x18003c5e0  jns     short loc_18003C661
0x18003c5e2  call    cs:__imp_GetLastError
0x18003c5e8  mov     ebx, eax
0x18003c5ea  test    eax, eax
0x18003c5ec  jle     short loc_18003C5F3
0x18003c5ee  movzx   ebx, ax
0x18003c5f1  or      ebx, ebp
0x18003c5f3  test    ebx, ebx
0x18003c5f5  js      short loc_18003C666
0x18003c5f7  xor     ebx, ebx
0x18003c5f9  mov     rcx, [rdi]
0x18003c5fc  mov     rax, [rcx]
0x18003c5ff  mov     rax, [rax+8]
0x18003c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c608  mov     r8, rax
0x18003c60b  lea     r12, aD_0; "d"
0x18003c612  mov     edx, [r12+rbx*4]
0x18003c616  mov     rcx, [rax]
0x18003c619  mov     rax, [rcx]
0x18003c61c  mov     rcx, r8
0x18003c61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c624  mov     ebp, eax
0x18003c626  test    eax, eax
0x18003c628  js      loc_18003C708
0x18003c62e  inc     rbx
0x18003c631  cmp     rbx, 3
0x18003c635  jb      short loc_18003C5F9
0x18003c637  mov     rcx, [rsi+220h]
0x18003c63e  mov     r9, rsi
0x18003c641  call    MUIOffline_EnumUILanguages
0x18003c646  test    eax, eax
0x18003c648  jnz     loc_18003C6E9
0x18003c64e  lea     rax, aFailedToEnumer; "Failed to enumerate languages."
0x18003c655  mov     ebx, 8000FFFFh
0x18003c65a  mov     edx, 66h ; 'f'
0x18003c65f  jmp     short loc_18003C6CC
0x18003c661  mov     ebx, 80004005h
0x18003c666  mov     rcx, [rsp+68h]; this
0x18003c66b  lea     rax, aUnableToGetpro_8; "Unable to GetProcAddress 'CreateApplica"...
0x18003c672  mov     r9d, ebx; char *
0x18003c675  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003c67a  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c681  mov     edx, 2CDh; void *
0x18003c686  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c68b  test    ebx, ebx
0x18003c68d  jns     loc_18003C5F7
0x18003c693  jmp     short loc_18003C6C0
0x18003c695  mov     rcx, rdi
0x18003c698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c69d  mov     ebx, eax
0x18003c69f  test    eax, eax
0x18003c6a1  jns     loc_18003C5F7
0x18003c6a7  mov     edx, 2D1h; void *
0x18003c6ac  mov     r9d, eax; char *
0x18003c6af  mov     rcx, [rsp+68h]; this
0x18003c6b4  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c6bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c6c0  lea     rax, aFailedToCreate_18; "Failed to create applicability context."
0x18003c6c7  mov     edx, 59h ; 'Y'; void *
0x18003c6cc  mov     rcx, [rsp+68h]; this
0x18003c6d1  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c6d8  mov     r9d, ebx; char *
0x18003c6db  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003c6e0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c6e5  mov     eax, ebx
0x18003c6e7  jmp     short loc_18003C6FB
0x18003c6e9  mov     dword ptr [rsi+2F8h], 1
0x18003c6f3  mov     rax, [rdi]
0x18003c6f6  mov     [r14], rax
0x18003c6f9  xor     eax, eax
0x18003c6fb  add     rsp, 38h
0x18003c6ff  pop     r14
0x18003c701  pop     r12
0x18003c703  pop     rdi
0x18003c704  pop     rsi
0x18003c705  pop     rbp
0x18003c706  pop     rbx
0x18003c707  retn
0x18003c708  mov     eax, [r12+rbx*4]
0x18003c70c  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c713  mov     rcx, [rsp+68h]; this
0x18003c718  mov     r9d, ebp; char *
0x18003c71b  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18003c71f  mov     edx, 61h ; 'a'; void *
0x18003c724  lea     rax, aFailedToAddSca; "Failed to add scale %d to applicability"...
0x18003c72b  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003c730  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c735  mov     eax, ebp
0x18003c737  jmp     short loc_18003C6FB
```

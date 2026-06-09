# OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute(Windows::Internal::String const &,ulong)

- ea: `0x18013cc00`
- end: `0x18013ceca`
- name: `?AddAttribute@CExtensionRegistration@Internal@DEH@OSIntegration@@UEAA_NAEBVString@2Windows@@K@Z`
- size: `714`
- prototype: `bool __fastcall(OSIntegration::DEH::Internal::CExtensionRegistration *__hidden this, const struct Windows::Internal::String *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180036e7c`
- `0x180048794`
- `0x18004cb60`
- `0x18004d22c`
- `0x180074000`
- `0x18008a740`
- `0x1800d7ad0`
- `0x18013cc00`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18013cc8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18013cc8f`

## string_xrefs

- `0x18013cc4b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013ccc2`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013cd4c`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013cdbb`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013ce37`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013ce78`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18013cc44`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013ccbb`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013cd45`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013cdb4`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013ce30`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013ce71`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18013cd39`: `_spAttributesCollisionMap->Insert(keyName, keyName, &fReplaced)`
- `0x18013ce24`: `_spAttributesCollisionMap->Remove(keyName)`
- `0x18013cda8`: `_spPropertyValueFactory->CreateUInt32(value, &spPropertyValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute(
        __int64 **this,
        const struct Windows::Internal::String *a2,
        unsigned int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  char v12; // bl
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  wil::details *v20; // [rsp+28h] [rbp-28h]
  int v21; // [rsp+30h] [rbp-20h]
  RoVariant *v22; // [rsp+30h] [rbp-20h]
  struct IInspectable *v23; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  int v25; // [rsp+48h] [rbp-8h]
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+18h]
  char v27; // [rsp+88h] [rbp+38h] BYREF

  if ( !OSIntegration::DEH::Internal::ValidRegistrationName(a2, a2) )
  {
    LODWORD(v20) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "((HRESULT)0x80080204L)",
      v20,
      v21);
    if ( (byte_180245605 & 0x20) != 0 )
      McTemplateU0d_EventWriteTransfer(v7, &AttributeNameInvalid, 2148008452LL);
    details::appxLog<long>(2148008452LL, v6, &AttributeNameInvalid, 2148008452LL);
    return 0;
  }
  if ( WindowsGetStringLen(*(HSTRING *)a2) > 0x3FFF )
  {
    LODWORD(v20) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "((HRESULT)0x80080204L)",
      v20,
      v21);
    if ( (byte_180245605 & 0x20) != 0 )
      McTemplateU0d_EventWriteTransfer(v10, &AttributeNameInvalidLength, 2148008452LL);
    details::appxLog<long>(2148008452LL, v9, &AttributeNameInvalidLength, 2148008452LL);
  }
  if ( !OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide(
          (OSIntegration::DEH::Internal::CExtensionRegistration *)this,
          a2) )
    return 0;
  v27 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, char *))(*this[8] + 80))(
          this[8],
          *(_QWORD *)a2,
          *(_QWORD *)a2,
          &v27);
  if ( v11 >= 0 )
  {
    v24 = 0;
    v25 = 0;
    v13 = this[9];
    v14 = *v13;
    v22 = (RoVariant *)&v24;
    v23 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IInspectable **))(v14 + 88))(v13, a3, &v23);
    v16 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v20) = v15;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
        "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
        "_spPropertyValueFactory->CreateUInt32(value, &spPropertyValue)",
        v20,
        (int)&v24);
    }
    RoVariant::Attach(v22, v23);
    if ( v16 < 0
      || (v12 = 1,
          (*(int (__fastcall **)(__int64 *, _QWORD, __int64, char *))(*this[7] + 80))(this[7], *(_QWORD *)a2, v24, &v27) < 0) )
    {
      v12 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*this[8] + 88))(this[8], *(_QWORD *)a2);
      if ( v17 < 0 )
      {
        LODWORD(v20) = v17;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x129,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
          "_spAttributesCollisionMap->Remove(keyName)",
          v20,
          (int)v22);
      }
    }
    RoVariant::~RoVariant((RoVariant *)&v24);
    if ( v12 )
      return v12;
  }
  else
  {
    LODWORD(v20) = v11;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "_spAttributesCollisionMap->Insert(keyName, keyName, &fReplaced)",
      v20,
      v21);
    v12 = 0;
  }
  LODWORD(v20) = -2147024882;
  wil::details::in1diag5::_Log_Hr(
    retaddr,
    (void *)0x132,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
    "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
    "((HRESULT)0x8007000EL)",
    v20,
    (int)v22);
  if ( (byte_180245605 & 0x20) != 0 )
    McTemplateU0d_EventWriteTransfer(v19, &CollectorIsOutOfMemory, 2147942414LL);
  details::appxLog<long>(2147942414LL, v18, &CollectorIsOutOfMemory, 2147942414LL);
  return v12;
}

```

## disassembly

```asm
0x18013cc00  mov     [rsp-18h+arg_0], rbx
0x18013cc05  mov     [rsp-18h+arg_8], r12
0x18013cc0a  push    rbp
0x18013cc0b  push    r14
0x18013cc0d  push    r15
0x18013cc0f  mov     rbp, rsp
0x18013cc12  sub     rsp, 50h
0x18013cc16  mov     r12d, r8d
0x18013cc19  mov     r14, rdx
0x18013cc1c  mov     r15, rcx
0x18013cc1f  mov     rcx, rdx; this
0x18013cc22  call    ?ValidRegistrationName@Internal@DEH@OSIntegration@@YA_NAEBVString@1Windows@@@Z; OSIntegration::DEH::Internal::ValidRegistrationName(Windows::Internal::String const &)
0x18013cc27  test    al, al
0x18013cc29  jnz     short loc_18013CC8C
0x18013cc2b  mov     rcx, [rbp+18h]; this
0x18013cc2f  mov     ebx, 80080204h
0x18013cc34  mov     dword ptr [rsp+50h+var_28], ebx; wil::details *
0x18013cc38  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18013cc3f  mov     [rsp+50h+var_30], rax; char *
0x18013cc44  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013cc4b  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013cc52  mov     edx, 0FBh; void *
0x18013cc57  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013cc5c  test    cs:byte_180245605, 20h
0x18013cc63  jz      short loc_18013CC74
0x18013cc65  mov     r8d, ebx
0x18013cc68  lea     rdx, AttributeNameInvalid
0x18013cc6f  call    McTemplateU0d_EventWriteTransfer
0x18013cc74  mov     r9d, ebx
0x18013cc77  lea     r8, AttributeNameInvalid
0x18013cc7e  mov     ecx, ebx
0x18013cc80  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18013cc85  xor     al, al
0x18013cc87  jmp     loc_18013CEB5
0x18013cc8c  mov     rcx, [r14]; string
0x18013cc8f  call    cs:__imp_WindowsGetStringLen
0x18013cc96  nop     dword ptr [rax+rax+00h]
0x18013cc9b  cmp     eax, 3FFFh
0x18013cca0  jbe     short loc_18013CCFC
0x18013cca2  mov     rcx, [rbp+18h]; this
0x18013cca6  mov     ebx, 80080204h
0x18013ccab  mov     dword ptr [rsp+50h+var_28], ebx; wil::details *
0x18013ccaf  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18013ccb6  mov     [rsp+50h+var_30], rax; char *
0x18013ccbb  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013ccc2  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013ccc9  mov     edx, 105h; void *
0x18013ccce  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013ccd3  test    cs:byte_180245605, 20h
0x18013ccda  jz      short loc_18013CCEB
0x18013ccdc  mov     r8d, ebx
0x18013ccdf  lea     rdx, AttributeNameInvalidLength
0x18013cce6  call    McTemplateU0d_EventWriteTransfer
0x18013cceb  mov     r9d, ebx
0x18013ccee  lea     r8, AttributeNameInvalidLength
0x18013ccf5  mov     ecx, ebx
0x18013ccf7  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18013ccfc  mov     rdx, r14; struct Windows::Internal::String *
0x18013ccff  mov     rcx, r15; this
0x18013cd02  call    ?CheckAttributeNameDoesNotCollide@CExtensionRegistration@Internal@DEH@OSIntegration@@AEAA_NAEBVString@2Windows@@@Z; OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide(Windows::Internal::String const &)
0x18013cd07  test    al, al
0x18013cd09  jz      loc_18013CC85
0x18013cd0f  mov     [rbp+arg_18], 0
0x18013cd13  mov     rcx, [r15+40h]
0x18013cd17  mov     rax, [rcx]
0x18013cd1a  lea     r9, [rbp+arg_18]
0x18013cd1e  mov     r8, [r14]
0x18013cd21  mov     rdx, r8
0x18013cd24  mov     rax, [rax+50h]
0x18013cd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013cd2d  mov     rcx, [rbp+18h]; this
0x18013cd31  test    eax, eax
0x18013cd33  jns     short loc_18013CD64
0x18013cd35  mov     dword ptr [rsp+50h+var_28], eax; wil::details *
0x18013cd39  lea     rax, aSpattributesco_0; "_spAttributesCollisionMap->Insert(keyNa"...
0x18013cd40  mov     [rsp+50h+var_30], rax; char *
0x18013cd45  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013cd4c  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013cd53  mov     edx, 111h; void *
0x18013cd58  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013cd5d  xor     bl, bl
0x18013cd5f  jmp     loc_18013CE56
0x18013cd64  mov     [rbp+var_10], 0
0x18013cd6c  mov     [rbp+var_8], 0
0x18013cd73  mov     rcx, [r15+48h]
0x18013cd77  mov     rax, [rcx]
0x18013cd7a  lea     rdx, [rbp+var_10]
0x18013cd7e  mov     [rbp+var_20], rdx
0x18013cd82  mov     [rbp+var_18], 0
0x18013cd8a  lea     r8, [rbp+var_18]
0x18013cd8e  mov     edx, r12d
0x18013cd91  mov     rax, [rax+58h]
0x18013cd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013cd9a  mov     ebx, eax
0x18013cd9c  mov     rcx, [rbp+18h]; this
0x18013cda0  test    eax, eax
0x18013cda2  jns     short loc_18013CDCD
0x18013cda4  mov     dword ptr [rsp+50h+var_28], eax; wil::details *
0x18013cda8  lea     rax, aSppropertyvalu_0; "_spPropertyValueFactory->CreateUInt32(v"...
0x18013cdaf  mov     [rsp+50h+var_30], rax; char *
0x18013cdb4  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013cdbb  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013cdc2  mov     edx, 11Ch; void *
0x18013cdc7  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013cdcc  nop
0x18013cdcd  shr     ebx, 1Fh
0x18013cdd0  mov     rdx, [rbp+var_18]; struct IInspectable *
0x18013cdd4  mov     rcx, [rbp+var_20]; this
0x18013cdd8  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18013cddd  nop
0x18013cdde  test    bl, bl
0x18013cde0  jnz     short loc_18013CE03
0x18013cde2  mov     bl, 1
0x18013cde4  mov     rcx, [r15+38h]
0x18013cde8  mov     rax, [rcx]
0x18013cdeb  lea     r9, [rbp+arg_18]
0x18013cdef  mov     r8, [rbp+var_10]
0x18013cdf3  mov     rdx, [r14]
0x18013cdf6  mov     rax, [rax+50h]
0x18013cdfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013cdff  test    eax, eax
0x18013ce01  jns     short loc_18013CE49
0x18013ce03  xor     bl, bl
0x18013ce05  mov     rcx, [r15+40h]
0x18013ce09  mov     rax, [rcx]
0x18013ce0c  mov     rdx, [r14]
0x18013ce0f  mov     rax, [rax+58h]
0x18013ce13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ce18  mov     rcx, [rbp+18h]; this
0x18013ce1c  test    eax, eax
0x18013ce1e  jns     short loc_18013CE49
0x18013ce20  mov     dword ptr [rsp+50h+var_28], eax; wil::details *
0x18013ce24  lea     rax, aSpattributesco_1; "_spAttributesCollisionMap->Remove(keyNa"...
0x18013ce2b  mov     [rsp+50h+var_30], rax; char *
0x18013ce30  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013ce37  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013ce3e  mov     edx, 129h; void *
0x18013ce43  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013ce48  nop
0x18013ce49  lea     rcx, [rbp+var_10]; this
0x18013ce4d  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18013ce52  test    bl, bl
0x18013ce54  jnz     short loc_18013CEB3
0x18013ce56  mov     rcx, [rbp+18h]; this
0x18013ce5a  mov     r14d, 8007000Eh
0x18013ce60  mov     dword ptr [rsp+50h+var_28], r14d; wil::details *
0x18013ce65  lea     rax, aHresult0x80070_0; "((HRESULT)0x8007000EL)"
0x18013ce6c  mov     [rsp+50h+var_30], rax; char *
0x18013ce71  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18013ce78  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013ce7f  mov     edx, 132h; void *
0x18013ce84  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18013ce89  test    cs:byte_180245605, 20h
0x18013ce90  jz      short loc_18013CEA1
0x18013ce92  mov     r8d, r14d
0x18013ce95  lea     rdx, CollectorIsOutOfMemory
0x18013ce9c  call    McTemplateU0d_EventWriteTransfer
0x18013cea1  mov     r9d, r14d
0x18013cea4  lea     r8, CollectorIsOutOfMemory
0x18013ceab  mov     ecx, r14d
0x18013ceae  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18013ceb3  mov     al, bl
0x18013ceb5  mov     rbx, [rsp+50h+arg_0]
0x18013ceba  mov     r12, [rsp+50h+arg_8]
0x18013cebf  add     rsp, 50h
0x18013cec3  pop     r15
0x18013cec5  pop     r14
0x18013cec7  pop     rbp
0x18013cec8  retn
```

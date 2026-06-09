# CSMBHelperClass::ReproduceFailureThreadExecutive(void *)

- ea: `0x1800088e0`
- end: `0x180008a64`
- name: `?ReproduceFailureThreadExecutive@CSMBHelperClass@@SAKPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x180004ee0`
- `0x180008214`
- `0x1800088e0`
- `0x180008b64`
- `0x18000d750`
- `0x18000dd04`
- `0x18000e10c`
- `0x18000fc30`
- `0x180012010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180008a1b`
- `msvcrt!_itow_s` at `0x180008a1b`
- `ADVAPI32!EventActivityIdControl` at `0x180008953`
- `ADVAPI32!EventActivityIdControl` at `0x180008953`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000891b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18000891b`

## string_xrefs

- `0x18000892f`: `UNCPath`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailureThreadExecutive(char *Parameter)
{
  __int64 v2; // rsi
  AttributeList *v3; // r14
  unsigned __int16 *v4; // r15
  int v5; // eax
  __int64 v6; // rbx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-60h] BYREF
  wchar_t Buffer[16]; // [rsp+50h] [rbp-48h] BYREF

  v2 = *((_QWORD *)Parameter + 22);
  v12 = v2;
  ImpersonateLoggedOnUser(*((HANDLE *)Parameter + 34));
  try
  {
    v3 = (AttributeList *)(Parameter + 208);
    v4 = *(unsigned __int16 **)(AttributeList::getAttribute(Parameter + 208, v13, L"UNCPath", 1) + 8);
    EventActivityIdControl(2u, (LPGUID)(Parameter + 140));
    v5 = CSMBHelperClass::TransferActivityID();
  }
  catch ( enum TestException )
  {
    v8 = v12;
    if ( v12 )
    {
      v12 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v12,
        L"CSMBHelperClass::ReproduceFailure UNCPath not found");
      v9 = v12;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v8 + 24LL))(
        v8,
        2,
        0,
        L"SMBHelperClass",
        v12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 8), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24), v9 - 24);
    }
    return 2147500037LL;
  }
  catch ( exception )
  {
    v10 = v12;
    if ( v12 )
    {
      v12 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v12,
        L"CSMBHelperClass::ReproduceFailureThreadExecutive Unknown Exception");
      v11 = v12;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v10 + 24LL))(
        v10,
        2,
        0,
        L"SMBHelperClass",
        v12);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 8), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24), v11 - 24);
    }
    return 2147500037LL;
  }
  v3 = (AttributeList *)(Parameter + 208);
  v4 = *(unsigned __int16 **)(AttributeList::getAttribute(Parameter + 208, v13, L"UNCPath", 1) + 8);
  EventActivityIdControl(2u, (LPGUID)(Parameter + 140));
  v5 = CSMBHelperClass::TransferActivityID();
}

```

## disassembly

```asm
0x1800088e0  mov     [rsp+arg_8], rbx
0x1800088e5  mov     [rsp+arg_10], rsi
0x1800088ea  push    rdi
0x1800088eb  push    r14
0x1800088ed  push    r15
0x1800088ef  sub     rsp, 80h
0x1800088f6  mov     rax, cs:__security_cookie
0x1800088fd  xor     rax, rsp
0x180008900  mov     [rsp+98h+var_28], rax
0x180008905  mov     rdi, rcx
0x180008908  mov     rsi, [rcx+0B0h]
0x18000890f  mov     [rsp+98h+var_68], rsi
0x180008914  mov     rcx, [rcx+110h]; hToken
0x18000891b  call    cs:__imp_ImpersonateLoggedOnUser
0x180008921  nop
0x180008922  lea     r14, [rdi+0D0h]
0x180008929  mov     r9d, 1
0x18000892f  lea     r8, aUncpath; "UNCPath"
0x180008936  lea     rdx, [rsp+98h+var_60]
0x18000893b  mov     rcx, r14
0x18000893e  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180008943  mov     r15, [rax+8]
0x180008947  lea     rdx, [rdi+8Ch]; ActivityId
0x18000894e  mov     ecx, 2; ControlCode
0x180008953  call    cs:__imp_EventActivityIdControl
0x180008959  call    ?TransferActivityID@CSMBHelperClass@@SAJXZ; CSMBHelperClass::TransferActivityID(void)
0x18000895e  test    eax, eax
0x180008960  jns     short loc_1800089E0
0x180008962  test    rsi, rsi
0x180008965  jz      short loc_1800089E0
0x180008967  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000896e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008975  mov     rax, [rax+18h]
0x180008979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897e  add     rax, 18h
0x180008982  mov     [rsp+98h+var_68], rax
0x180008987  lea     rdx, aCsmbhelperclas_7; "CSMBHelperClass::TransferActivityID() F"...
0x18000898e  lea     rcx, [rsp+98h+var_68]
0x180008993  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180008998  mov     rax, [rsi]
0x18000899b  xor     r8d, r8d
0x18000899e  mov     rbx, [rsp+98h+var_68]
0x1800089a3  mov     [rsp+98h+var_78], rbx
0x1800089a8  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x1800089af  lea     edx, [r8+2]
0x1800089b3  mov     rcx, rsi
0x1800089b6  mov     rax, [rax+18h]
0x1800089ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089bf  nop
0x1800089c0  lea     rdx, [rbx-18h]
0x1800089c4  or      eax, 0FFFFFFFFh
0x1800089c7  lock xadd [rdx+10h], eax
0x1800089cc  sub     eax, 1
0x1800089cf  jg      short loc_1800089E0
0x1800089d1  mov     rcx, [rdx]
0x1800089d4  mov     rax, [rcx]
0x1800089d7  mov     rax, [rax+8]
0x1800089db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e0  lea     rbx, [rdi+88h]
0x1800089e7  mov     r8, rbx; unsigned int *
0x1800089ea  mov     rdx, [rdi+0B0h]; struct INDFEtw *
0x1800089f1  mov     rcx, r15; unsigned __int16 *
0x1800089f4  call    ?ReproduceFailure@CSMBHelperClass@@CAJPEAGPEAUINDFEtw@@AEAK@Z; CSMBHelperClass::ReproduceFailure(ushort *,INDFEtw *,ulong &)
0x1800089f9  lea     rdx, aErrorcode; "ErrorCode"
0x180008a00  mov     rcx, r14; this
0x180008a03  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x180008a08  test    eax, eax
0x180008a0a  jnz     short loc_180008A35
0x180008a0c  lea     r9d, [rax+0Ah]; Radix
0x180008a10  lea     r8d, [rax+10h]; BufferCount
0x180008a14  lea     rdx, [rsp+98h+Buffer]; Buffer
0x180008a19  mov     ecx, [rbx]; Value
0x180008a1b  call    cs:__imp__itow_s
0x180008a21  lea     r8, [rsp+98h+Buffer]; unsigned __int16 *
0x180008a26  lea     rdx, aErrorcode; "ErrorCode"
0x180008a2d  mov     rcx, r14; this
0x180008a30  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180008a35  xor     eax, eax
0x180008a37  jmp     short loc_180008A3E
0x180008a39  mov     eax, 80004005h
0x180008a3e  mov     rcx, [rsp+98h+var_28]
0x180008a43  xor     rcx, rsp; StackCookie
0x180008a46  call    __security_check_cookie
0x180008a4b  lea     r11, [rsp+98h+var_18]
0x180008a53  mov     rbx, [r11+28h]
0x180008a57  mov     rsi, [r11+30h]
0x180008a5b  mov     rsp, r11
0x180008a5e  pop     r15
0x180008a60  pop     r14
0x180008a62  pop     rdi
0x180008a63  retn
```

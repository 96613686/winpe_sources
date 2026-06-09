# CEditionUpgradeHelper::Initialize(void)

- ea: `0x1800096e8`
- end: `0x180009880`
- name: `?Initialize@CEditionUpgradeHelper@@AEAAJXZ`
- size: `408`
- prototype: `__int64 __fastcall(CEditionUpgradeHelper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008bf0`
- `0x18000a480`
- `0x18000aed0`

## callees

- `0x1800018e0`
- `0x180008c60`
- `0x1800096e8`
- `0x180009978`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009753`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000973a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000973a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009768`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009768`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeHelper::Initialize(CEditionUpgradeHelper *this)
{
  int ActivationFactory; // eax
  __int64 v3; // rcx
  unsigned int v4; // edx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // [rsp+20h] [rbp-50h] BYREF
  __int64 v9; // [rsp+28h] [rbp-48h] BYREF
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF

  v11 = 0;
  v10 = 0;
  v9 = 0;
  v8 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10);
  if ( ActivationFactory < 0 )
    goto LABEL_11;
  if ( v10 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL))(v10, &v9);
    if ( ActivationFactory >= 0 )
    {
      if ( !v9 )
        goto LABEL_5;
      ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
                            v9,
                            &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f,
                            &v8);
      if ( ActivationFactory >= 0 )
      {
        if ( !v8 )
          goto LABEL_5;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v11);
        v4 = ActivationFactory;
        if ( ActivationFactory >= 0 )
          goto LABEL_13;
      }
    }
LABEL_11:
    v3 = (unsigned int)ActivationFactory;
    goto LABEL_12;
  }
LABEL_5:
  v3 = 2147745807LL;
LABEL_12:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v5 = (*(__int64 (__fastcall **)(CEditionUpgradeHelper *, __int64))(*(_QWORD *)this + 24LL))(this, v11);
  v6 = v5;
  if ( v5 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x1800096e8  mov     [rsp-8+arg_8], rbx
0x1800096ed  push    rbp
0x1800096ee  mov     rbp, rsp
0x1800096f1  sub     rsp, 70h
0x1800096f5  mov     rax, cs:__security_cookie
0x1800096fc  xor     rax, rsp
0x1800096ff  mov     [rbp+var_10], rax
0x180009703  mov     rbx, rcx
0x180009706  mov     [rbp+var_38], 0
0x18000970e  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x180009715  mov     [rbp+var_40], 0
0x18000971d  lea     r9, [rbp+string]; string
0x180009721  mov     [rbp+var_48], 0
0x180009729  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000972d  mov     [rbp+var_50], 0
0x180009735  mov     edx, 1Ah; length
0x18000973a  call    cs:__imp_WindowsCreateStringReference
0x180009740  test    eax, eax
0x180009742  jns     short loc_180009759
0x180009744  xor     r9d, r9d; lpArguments
0x180009747  xor     r8d, r8d; nNumberOfArguments
0x18000974a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000974f  lea     edx, [r9+1]; dwExceptionFlags
0x180009753  call    cs:__imp_RaiseException
0x180009759  mov     rcx, [rbp+string]
0x18000975d  lea     r8, [rbp+var_40]
0x180009761  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x180009768  call    cs:__imp_RoGetActivationFactory
0x18000976e  mov     edx, eax
0x180009770  test    eax, eax
0x180009772  js      short loc_1800097E0
0x180009774  mov     rcx, [rbp+var_40]
0x180009778  test    rcx, rcx
0x18000977b  jnz     short loc_180009786
0x18000977d  mov     ecx, 8004000Fh
0x180009782  mov     edx, ecx
0x180009784  jmp     short loc_1800097E2
0x180009786  mov     rax, [rcx]
0x180009789  lea     rdx, [rbp+var_48]
0x18000978d  mov     rax, [rax+30h]
0x180009791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009796  mov     edx, eax
0x180009798  test    eax, eax
0x18000979a  js      short loc_1800097E0
0x18000979c  mov     rcx, [rbp+var_48]
0x1800097a0  test    rcx, rcx
0x1800097a3  jz      short loc_18000977D
0x1800097a5  mov     rax, [rcx]
0x1800097a8  lea     r8, [rbp+var_50]
0x1800097ac  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x1800097b3  mov     rax, [rax]
0x1800097b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097bb  mov     edx, eax
0x1800097bd  test    eax, eax
0x1800097bf  js      short loc_1800097E0
0x1800097c1  mov     rcx, [rbp+var_50]
0x1800097c5  test    rcx, rcx
0x1800097c8  jz      short loc_18000977D
0x1800097ca  mov     rax, [rcx]
0x1800097cd  lea     rdx, [rbp+var_38]
0x1800097d1  mov     rax, [rax+18h]
0x1800097d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097da  mov     edx, eax
0x1800097dc  test    eax, eax
0x1800097de  jns     short loc_1800097E7
0x1800097e0  mov     ecx, eax
0x1800097e2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800097e7  mov     ecx, edx
0x1800097e9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800097ee  mov     rcx, [rbp+var_50]
0x1800097f2  test    rcx, rcx
0x1800097f5  jz      short loc_18000980B
0x1800097f7  mov     rax, [rcx]
0x1800097fa  mov     rax, [rax+10h]
0x1800097fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009803  mov     [rbp+var_50], 0
0x18000980b  mov     rcx, [rbp+var_48]
0x18000980f  test    rcx, rcx
0x180009812  jz      short loc_180009828
0x180009814  mov     rax, [rcx]
0x180009817  mov     rax, [rax+10h]
0x18000981b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009820  mov     [rbp+var_48], 0
0x180009828  mov     rcx, [rbp+var_40]
0x18000982c  test    rcx, rcx
0x18000982f  jz      short loc_18000983D
0x180009831  mov     rax, [rcx]
0x180009834  mov     rax, [rax+10h]
0x180009838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983d  mov     rax, [rbx]
0x180009840  mov     rcx, rbx
0x180009843  mov     rdx, [rbp+var_38]
0x180009847  mov     rax, [rax+18h]
0x18000984b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009850  mov     ebx, eax
0x180009852  test    eax, eax
0x180009854  jns     short loc_18000985D
0x180009856  mov     ecx, eax
0x180009858  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000985d  mov     ecx, ebx
0x18000985f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180009864  mov     eax, ebx
0x180009866  mov     rcx, [rbp+var_10]
0x18000986a  xor     rcx, rsp; StackCookie
0x18000986d  call    __security_check_cookie
0x180009872  mov     rbx, [rsp+70h+arg_8]
0x18000987a  add     rsp, 70h
0x18000987e  pop     rbp
0x18000987f  retn
```

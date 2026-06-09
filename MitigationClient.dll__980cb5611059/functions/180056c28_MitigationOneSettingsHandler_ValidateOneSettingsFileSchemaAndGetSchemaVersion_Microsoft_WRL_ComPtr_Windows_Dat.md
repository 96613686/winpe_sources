# MitigationOneSettingsHandler::ValidateOneSettingsFileSchemaAndGetSchemaVersion(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::Wrappers::HString &)

- ea: `0x180056c28`
- end: `0x180056d33`
- name: `?ValidateOneSettingsFileSchemaAndGetSchemaVersion@MitigationOneSettingsHandler@@CAJAEBV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@34@AEAVHString@Wrappers@34@@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800557c8`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x180054760`
- `0x180056c28`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d12`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationOneSettingsHandler::ValidateOneSettingsFileSchemaAndGetSchemaVersion(
        _QWORD *a1,
        __int64 *a2,
        HSTRING *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v13; // rax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v16[32]; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  string = 0;
  v6 = *a1;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 96LL))(*a1, a2);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v11 = *a2;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
      WindowsDeleteString(*a3);
      *a3 = 0;
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              v16,
              &MitigationOneSettingsHandler::s_oneSettingsSchemaVersionRef);
      v8 = v12(v11, *(_QWORD *)(v13 + 24), a3);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v9 = 0;
        goto LABEL_9;
      }
      v10 = 406;
    }
    else
    {
      v10 = 403;
    }
  }
  else
  {
    v10 = 400;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationonesettingshandler.cpp",
    (const char *)(unsigned int)v8,
    (int)string);
LABEL_9:
  WindowsDeleteString(string);
  return v9;
}

```

## disassembly

```asm
0x180056c28  push    rbx
0x180056c2a  push    rsi
0x180056c2b  push    rdi
0x180056c2c  push    r14
0x180056c2e  push    r15
0x180056c30  sub     rsp, 50h
0x180056c34  mov     rax, cs:__security_cookie
0x180056c3b  xor     rax, rsp
0x180056c3e  mov     [rsp+78h+var_30], rax
0x180056c43  mov     r14, r8
0x180056c46  mov     rsi, rdx
0x180056c49  mov     r15, rcx
0x180056c4c  mov     [rsp+78h+string], 0
0x180056c55  mov     rdi, [rcx]
0x180056c58  mov     rax, [rdi]
0x180056c5b  mov     rbx, [rax+38h]
0x180056c5f  xor     ecx, ecx; string
0x180056c61  call    cs:__imp_WindowsDeleteString
0x180056c67  mov     [rsp+78h+string], 0; int
0x180056c70  lea     rdx, [rsp+78h+string]
0x180056c75  mov     rcx, rdi
0x180056c78  mov     rax, rbx
0x180056c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c80  mov     ebx, eax
0x180056c82  test    eax, eax
0x180056c84  jns     short loc_180056C8D
0x180056c86  mov     edx, 190h
0x180056c8b  jmp     short loc_180056CAA
0x180056c8d  mov     rcx, [r15]
0x180056c90  mov     rax, [rcx]
0x180056c93  mov     rdx, rsi
0x180056c96  mov     rax, [rax+60h]
0x180056c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c9f  mov     ebx, eax
0x180056ca1  test    eax, eax
0x180056ca3  jns     short loc_180056CC0
0x180056ca5  mov     edx, 193h; void *
0x180056caa  mov     rcx, [rsp+78h]; this
0x180056caf  mov     r9d, eax; char *
0x180056cb2  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180056cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056cbe  jmp     short loc_180056D0D
0x180056cc0  mov     rdi, [rsi]
0x180056cc3  mov     rax, [rdi]
0x180056cc6  mov     rbx, [rax+50h]
0x180056cca  mov     rcx, [r14]; string
0x180056ccd  call    cs:__imp_WindowsDeleteString
0x180056cd3  mov     qword ptr [r14], 0
0x180056cda  lea     rdx, ?s_oneSettingsSchemaVersionRef@MitigationOneSettingsHandler@@2QEBGEB; ushort const * const MitigationOneSettingsHandler::s_oneSettingsSchemaVersionRef
0x180056ce1  lea     rcx, [rsp+78h+var_50]
0x180056ce6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180056ceb  nop
0x180056cec  mov     r8, r14
0x180056cef  mov     rdx, [rax+18h]
0x180056cf3  mov     rcx, rdi
0x180056cf6  mov     rax, rbx
0x180056cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cfe  mov     ebx, eax
0x180056d00  test    eax, eax
0x180056d02  jns     short loc_180056D0B
0x180056d04  mov     edx, 196h
0x180056d09  jmp     short loc_180056CAA
0x180056d0b  xor     ebx, ebx
0x180056d0d  mov     rcx, [rsp+78h+string]; string
0x180056d12  call    cs:__imp_WindowsDeleteString
0x180056d18  mov     eax, ebx
0x180056d1a  mov     rcx, [rsp+78h+var_30]
0x180056d1f  xor     rcx, rsp; StackCookie
0x180056d22  call    __security_check_cookie
0x180056d27  add     rsp, 50h
0x180056d2b  pop     r15
0x180056d2d  pop     r14
0x180056d2f  pop     rdi
0x180056d30  pop     rsi
0x180056d31  pop     rbx
0x180056d32  retn
```

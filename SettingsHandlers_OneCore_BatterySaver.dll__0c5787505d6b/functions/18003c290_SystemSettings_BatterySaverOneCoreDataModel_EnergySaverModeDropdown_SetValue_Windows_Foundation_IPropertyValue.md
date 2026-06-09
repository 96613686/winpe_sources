# SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x18003c290`
- end: `0x18003c382`
- name: `?SetValue@EnergySaverModeDropdown@BatterySaverOneCoreDataModel@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000eacc`
- `0x18003c290`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c378`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18003c328`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18003c328`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::SetValue(
        SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const WCHAR *StringRawBuffer; // rbp
  __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+58h] [rbp+10h] BYREF

  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::m_dropdownValues;
    v10 = qword_180065E08;
    while ( 1 )
    {
      if ( v9 == v10 )
      {
        WindowsDeleteString(string);
        return 2147500037LL;
      }
      if ( !StrCmpLogicalW(*(PCWSTR *)v9, StringRawBuffer) )
        break;
      v9 += 16;
    }
    *((_DWORD *)this + 74) = *(_DWORD *)(v9 + 8);
    (*(void (__fastcall **)(SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *, SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown *))(*(_QWORD *)this + 192LL))(
      this,
      this);
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\energysaverdropdown.cpp",
      (const char *)(unsigned int)v5,
      v11);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x18003c290  push    rbx
0x18003c292  push    rbp
0x18003c293  push    rsi
0x18003c294  push    rdi
0x18003c295  sub     rsp, 28h
0x18003c299  mov     rdi, rdx
0x18003c29c  mov     rsi, rcx
0x18003c29f  mov     [rsp+48h+string], 0
0x18003c2a8  mov     rax, [rdx]
0x18003c2ab  mov     rbx, [rax+98h]
0x18003c2b2  xor     ecx, ecx; string
0x18003c2b4  call    cs:__imp_WindowsDeleteString
0x18003c2ba  mov     [rsp+48h+string], 0
0x18003c2c3  lea     rdx, [rsp+48h+string]
0x18003c2c8  mov     rcx, rdi
0x18003c2cb  mov     rax, rbx
0x18003c2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2d3  mov     ebx, eax
0x18003c2d5  test    eax, eax
0x18003c2d7  jns     short loc_18003C302
0x18003c2d9  mov     rcx, [rsp+48h]; this
0x18003c2de  mov     r9d, eax; char *
0x18003c2e1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\coresettinghandlers"...
0x18003c2e8  mov     edx, 0B7h; void *
0x18003c2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2f2  nop
0x18003c2f3  mov     rcx, [rsp+48h+string]; string
0x18003c2f8  call    cs:__imp_WindowsDeleteString
0x18003c2fe  mov     eax, ebx
0x18003c300  jmp     short loc_18003C34B
0x18003c302  xor     edx, edx; length
0x18003c304  mov     rcx, [rsp+48h+string]; string
0x18003c309  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c30f  mov     rbp, rax
0x18003c312  mov     rbx, cs:?m_dropdownValues@EnergySaverModeDropdown@BatterySaverOneCoreDataModel@SystemSettings@@0V?$vector@UDropdownValuePair@EnergySaverModeDropdown@BatterySaverOneCoreDataModel@SystemSettings@@V?$allocator@UDropdownValuePair@EnergySaverModeDropdown@BatterySaverOneCoreDataModel@SystemSettings@@@std@@@std@@B; std::vector<SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::DropdownValuePair> const SystemSettings::BatterySaverOneCoreDataModel::EnergySaverModeDropdown::m_dropdownValues
0x18003c319  mov     rdi, cs:qword_180065E08
0x18003c320  jmp     short loc_18003C336
0x18003c322  mov     rdx, rbp; psz2
0x18003c325  mov     rcx, [rbx]; psz1
0x18003c328  call    cs:__imp_StrCmpLogicalW
0x18003c32e  test    eax, eax
0x18003c330  jz      short loc_18003C354
0x18003c332  add     rbx, 10h
0x18003c336  cmp     rbx, rdi
0x18003c339  jnz     short loc_18003C322
0x18003c33b  mov     rcx, [rsp+48h+string]; string
0x18003c340  call    cs:__imp_WindowsDeleteString
0x18003c346  mov     eax, 80004005h
0x18003c34b  add     rsp, 28h
0x18003c34f  pop     rdi
0x18003c350  pop     rsi
0x18003c351  pop     rbp
0x18003c352  pop     rbx
0x18003c353  retn
0x18003c354  mov     eax, [rbx+8]
0x18003c357  mov     [rsi+128h], eax
0x18003c35d  mov     rax, [rsi]
0x18003c360  mov     rdx, rsi
0x18003c363  mov     rcx, rsi
0x18003c366  mov     rax, [rax+0C0h]
0x18003c36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c372  nop
0x18003c373  mov     rcx, [rsp+48h+string]; string
0x18003c378  call    cs:__imp_WindowsDeleteString
0x18003c37e  xor     eax, eax
0x18003c380  jmp     short loc_18003C34B
```

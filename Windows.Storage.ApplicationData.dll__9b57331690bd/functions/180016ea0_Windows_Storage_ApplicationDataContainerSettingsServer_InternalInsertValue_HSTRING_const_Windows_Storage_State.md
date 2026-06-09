# Windows::Storage::ApplicationDataContainerSettingsServer::InternalInsertValue(HSTRING__ * const &,Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter &,_FILETIME const *)

- ea: `0x180016ea0`
- end: `0x180016fd4`
- name: `?InternalInsertValue@ApplicationDataContainerSettingsServer@Storage@Windows@@EEAAJAEBQEAUHSTRING__@@AEAVSettingPropertyToApiSetValueConverter@StateABIHelpers@23@PEBU_FILETIME@@@Z`
- size: `308`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, HSTRING__ *const *key, Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter *apiSetValue, const _FILETIME *time)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180016ea0`
- `0x180016fdc`
- `0x180017004`
- `0x18001702c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fb7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!WriteStateContainerValue` at `0x180016f07`
- `ext-ms-win-appmodel-state-ext-l1-2-0!WriteStateContainerValue` at `0x180016f07`

## string_xrefs

- `0x180016fcb`: `Remove %ws type %u`
- `0x180016f86`: `WriteStateContainerValue %ws %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerSettingsServer::InternalInsertValue(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        HSTRING *key,
        Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter *apiSetValue,
        const _FILETIME *time)
{
  unsigned int SettingValueBufferBytes; // esi
  unsigned __int8 *SettingValueBuffer; // rdi
  tag_STATE_VALUE_TYPE SettingValueType; // ebx
  PCWSTR StringRawBuffer; // rax
  HRESULT v13; // edi
  signed int LastError; // eax
  tag_STATE_VALUE_TYPE v15; // ebx
  PCWSTR v16; // rax
  tag_STATE_VALUE_TYPE v17; // ebx
  PCWSTR v18; // rax
  tag_STATE_VALUE_TYPE v19; // [rsp+30h] [rbp-48h]
  tag_STATE_VALUE_TYPE v20; // [rsp+30h] [rbp-48h]
  void *retaddr; // [rsp+78h] [rbp+0h]

  if ( Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(apiSetValue) )
  {
    SettingValueBufferBytes = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBufferBytes(apiSetValue);
    SettingValueBuffer = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBuffer(apiSetValue);
    SettingValueType = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(apiSetValue);
    StringRawBuffer = WindowsGetStringRawBuffer(*key, 0);
    if ( (unsigned int)WriteStateContainerValue(
                         this->m_containerHandle,
                         StringRawBuffer,
                         (unsigned int)SettingValueType,
                         SettingValueBuffer,
                         SettingValueBufferBytes,
                         time) )
      return 0;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v13, 0xDu);
    if ( v13 < 0 )
    {
      v15 = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(apiSetValue);
      v16 = WindowsGetStringRawBuffer(*key, 0);
      v19 = v15;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x2DBu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
        v13,
        "WriteStateContainerValue %ws %u",
        v16,
        v19);
    }
  }
  else
  {
    v13 = this->Remove(this, *key);
    if ( v13 < 0 )
    {
      v17 = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(apiSetValue);
      v18 = WindowsGetStringRawBuffer(*key, 0);
      v20 = v17;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x2CCu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
        v13,
        "Remove %ws type %u",
        v18,
        v20);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016ea0  push    rbx
0x180016ea2  push    rbp
0x180016ea3  push    rsi
0x180016ea4  push    rdi
0x180016ea5  push    r12
0x180016ea7  push    r14
0x180016ea9  push    r15
0x180016eab  sub     rsp, 40h
0x180016eaf  mov     r15, this
0x180016eb2  mov     r12, time
0x180016eb5  mov     this, apiSetValue; this
0x180016eb8  mov     rbp, apiSetValue
0x180016ebb  mov     r14, key
0x180016ebe  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x180016ec3  test    eax, eax
0x180016ec5  jz      short loc_180016F22
0x180016ec7  mov     this, rbp; this
0x180016eca  call    ?GetSettingValueBufferBytes@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BIXZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBufferBytes(void)
0x180016ecf  mov     this, rbp; this
0x180016ed2  mov     esi, eax
0x180016ed4  call    ?GetSettingValueBuffer@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBAPEAEXZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBuffer(void)
0x180016ed9  mov     this, rbp; this
0x180016edc  mov     rdi, rax
0x180016edf  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x180016ee4  mov     this, [r14]; string
0x180016ee7  xor     edx, edx; length
0x180016ee9  mov     ebx, eax
0x180016eeb  call    cs:__imp_WindowsGetStringRawBuffer
0x180016ef1  mov     this, [r15+58h]
0x180016ef5  mov     time, rdi
0x180016ef8  mov     key, rax
0x180016efb  mov     [rsp+78h+var_50], r12
0x180016f00  mov     r8d, ebx
0x180016f03  mov     dword ptr [rsp+78h+formatString], esi
0x180016f07  call    cs:__imp_WriteStateContainerValue
0x180016f0d  test    eax, eax
0x180016f0f  jz      short loc_180016F3E
0x180016f11  xor     eax, eax
0x180016f13  add     rsp, 40h
0x180016f17  pop     r15
0x180016f19  pop     r14
0x180016f1b  pop     r12
0x180016f1d  pop     rdi
0x180016f1e  pop     rsi
0x180016f1f  pop     rbp
0x180016f20  pop     rbx
0x180016f21  retn
0x180016f22  mov     rax, [r15]
0x180016f25  mov     this, r15
0x180016f28  mov     key, [r14]
0x180016f2b  mov     rax, [rax+58h]
0x180016f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f34  mov     edi, eax
0x180016f36  test    eax, eax
0x180016f38  js      short loc_180016FA8
0x180016f3a  mov     eax, edi
0x180016f3c  jmp     short loc_180016F13
0x180016f3e  call    cs:__imp_GetLastError
0x180016f44  mov     edi, eax
0x180016f46  test    eax, eax
0x180016f48  jle     short loc_180016F53
0x180016f4a  movzx   edi, ax
0x180016f4d  or      edi, 80070000h
0x180016f53  mov     edx, 0Dh; idsValue
0x180016f58  mov     ecx, edi; hr
0x180016f5a  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180016f5f  test    edi, edi
0x180016f61  jns     short loc_180016F3A
0x180016f63  mov     this, rbp; this
0x180016f66  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x180016f6b  mov     this, [r14]; string
0x180016f6e  xor     edx, edx; length
0x180016f70  mov     ebx, eax
0x180016f72  call    cs:__imp_WindowsGetStringRawBuffer
0x180016f78  mov     [rsp+78h+var_48], ebx
0x180016f7c  mov     edx, 2DBh; lineNumber
0x180016f81  mov     [rsp+78h+var_50], rax
0x180016f86  lea     rax, aWritestatecont_0; "WriteStateContainerValue %ws %u"
0x180016f8d  mov     this, [rsp+78h]; callerReturnAddress
0x180016f92  lea     apiSetValue, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180016f99  mov     r9d, edi; hr
0x180016f9c  mov     [rsp+78h+formatString], rax; formatString
0x180016fa1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016fa6  jmp     short loc_180016F3A
0x180016fa8  mov     this, rbp; this
0x180016fab  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x180016fb0  mov     this, [r14]; string
0x180016fb3  xor     edx, edx; length
0x180016fb5  mov     ebx, eax
0x180016fb7  call    cs:__imp_WindowsGetStringRawBuffer
0x180016fbd  mov     [rsp+78h+var_48], ebx
0x180016fc1  mov     edx, 2CCh
0x180016fc6  mov     [rsp+78h+var_50], rax
0x180016fcb  lea     rax, aRemoveWsTypeU; "Remove %ws type %u"
0x180016fd2  jmp     short loc_180016F8D
```

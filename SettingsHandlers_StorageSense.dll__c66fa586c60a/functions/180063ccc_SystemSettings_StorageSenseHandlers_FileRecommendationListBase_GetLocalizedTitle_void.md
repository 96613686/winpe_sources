# SystemSettings::StorageSenseHandlers::FileRecommendationListBase::GetLocalizedTitle(void)

- ea: `0x180063ccc`
- end: `0x180063dae`
- name: `?GetLocalizedTitle@FileRecommendationListBase@StorageSenseHandlers@SystemSettings@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800641c0`

## callees

- `0x18001dfe8`
- `0x180023578`
- `0x180024a80`
- `0x1800352b4`
- `0x180063ccc`
- `0x180066c78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063d95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063d68`

## string_xrefs

- `0x180063d0f`: `SystemSettings_StorageSense_StorageRecommendations_OldFilesList`
- `0x180063d08`: `SystemSettings_StorageSense_StorageRecommendations_NewFilesList`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall SystemSettings::StorageSenseHandlers::FileRecommendationListBase::GetLocalizedTitle(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx
  wchar_t *v8; // rbx
  HSTRING *v9; // r8
  int ResourceStringById; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rax
  int v16; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  v3 = a1 + 312;
  if ( *(_QWORD *)(a1 + 328) )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 312);
    *v5 = v4;
    v6 = std::_WChar_traits<unsigned short>::length(v4);
    *(_QWORD *)(v7 + 8) = v6;
  }
  else
  {
    v8 = L"SystemSettings_StorageSense_StorageRecommendations_OldFilesList";
    if ( *(_DWORD *)(a1 + 344) )
      v8 = L"SystemSettings_StorageSense_StorageRecommendations_NewFilesList";
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v8, &string, v9);
    if ( ResourceStringById >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign(v3, StringRawBuffer);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
      *a2 = v14;
      a2[1] = std::_WChar_traits<unsigned short>::length(v14);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(retaddr, v11, v12, (const char *)(unsigned int)ResourceStringById, v16);
      *a2 = 0;
      a2[1] = 0;
    }
    WindowsDeleteString(string);
  }
  return a2;
}

```

## disassembly

```asm
0x180063ccc  mov     [rsp+arg_8], rbx
0x180063cd1  mov     [rsp+arg_10], rsi
0x180063cd6  push    rdi; int
0x180063cd7  sub     rsp, 20h
0x180063cdb  mov     rdi, rdx
0x180063cde  lea     rsi, [rcx+138h]
0x180063ce5  cmp     qword ptr [rsi+10h], 0
0x180063cea  jz      short loc_180063D08
0x180063cec  mov     rcx, rsi
0x180063cef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063cf4  mov     [rdx], rax
0x180063cf7  mov     rcx, rax
0x180063cfa  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180063cff  mov     [rdx+8], rax
0x180063d03  jmp     loc_180063D9B
0x180063d08  lea     rax, aSystemsettings_301; "SystemSettings_StorageSense_StorageReco"...
0x180063d0f  lea     rbx, aSystemsettings_191; "SystemSettings_StorageSense_StorageReco"...
0x180063d16  cmp     dword ptr [rcx+158h], 0
0x180063d1d  cmovnz  rbx, rax
0x180063d21  xor     ecx, ecx; string
0x180063d23  call    cs:__imp_WindowsDeleteString
0x180063d29  mov     [rsp+28h+string], 0
0x180063d32  lea     rdx, [rsp+28h+string]; HSTRING *
0x180063d37  mov     rcx, rbx; this
0x180063d3a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180063d3f  test    eax, eax
0x180063d41  jns     short loc_180063D61
0x180063d43  mov     rcx, [rsp+28h]; this
0x180063d48  mov     r9d, eax; char *
0x180063d4b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180063d50  mov     qword ptr [rdi], 0
0x180063d57  mov     qword ptr [rdi+8], 0
0x180063d5f  jmp     short loc_180063D90
0x180063d61  xor     edx, edx; length
0x180063d63  mov     rcx, [rsp+28h+string]; string
0x180063d68  call    cs:__imp_WindowsGetStringRawBuffer
0x180063d6e  mov     rdx, rax
0x180063d71  mov     rcx, rsi
0x180063d74  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180063d79  mov     rcx, rsi
0x180063d7c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063d81  mov     [rdi], rax
0x180063d84  mov     rcx, rax
0x180063d87  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180063d8c  mov     [rdi+8], rax
0x180063d90  mov     rcx, [rsp+28h+string]; string
0x180063d95  call    cs:__imp_WindowsDeleteString
0x180063d9b  mov     rax, rdi
0x180063d9e  mov     rbx, [rsp+28h+arg_8]
0x180063da3  mov     rsi, [rsp+28h+arg_10]
0x180063da8  add     rsp, 20h
0x180063dac  pop     rdi
0x180063dad  retn
```

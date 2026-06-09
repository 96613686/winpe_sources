# _lambda_36d8af0aefe94a900d3d1375f4bc9632_::operator()

- ea: `0x1802125cc`
- end: `0x1802127dd`
- name: `_lambda_36d8af0aefe94a900d3d1375f4bc9632_::operator()`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180210cd8`

## callees

- `0x18000f880`
- `0x1800a3a38`
- `0x1800a4348`
- `0x1800e1320`
- `0x1801244c0`
- `0x1801ceb7c`
- `0x1802125cc`
- `0x180213790`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802125fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180212644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802127a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802127b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802125fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180212644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802127a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802127b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180212671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021269e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802126be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802126de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180212766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180212671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021269e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802126be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802126de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180212766`

## string_xrefs

- `0x18021262d`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_36d8af0aefe94a900d3d1375f4bc9632_::operator()(__int64 a1, __int64 a2, _BYTE *a3)
{
  int ElementValue; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v9; // rdx
  PCWSTR v10; // rdx
  PCWSTR v11; // rax
  __int64 v12; // r8
  _QWORD *v13; // rcx
  PCWSTR v14; // rax
  __int64 v15; // rbx
  HSTRING string; // [rsp+20h] [rbp-C8h] BYREF
  _QWORD v17[2]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE Src[32]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v20[32]; // [rsp+80h] [rbp-68h] BYREF
  _QWORD v21[4]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  *a3 = 0;
  WindowsDeleteString(0);
  string = 0;
  ElementValue = StateRepoHelper::GetElementValue(L"#text", a2, &string);
  v6 = ElementValue;
  if ( ElementValue >= 0 )
  {
    v17[0] = **(_QWORD **)a1;
    v17[1] = **(_QWORD **)(a1 + 8);
    StringRawBuffer = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 16), 0);
    try
    {
      std::wstring::wstring(v18, StringRawBuffer);
      std::wstring::wstring(Src, L"{");
      v9 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(v20, v9);
      v10 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 24), 0);
      std::wstring::wstring(v21, v10);
      v11 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 32), 0);
      v15 = -1;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      std::wstring::_Append<wchar_t>(Src);
      std::wstring::_Append<wchar_t>(Src);
      v13 = v21;
      if ( v21[3] > 7u )
        v13 = (_QWORD *)v21[0];
      if ( *((_WORD *)v13 + v21[2] - 1) != 92 )
        std::wstring::_Append<wchar_t>(v21);
      v14 = WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 40), 0);
      do
        ++v15;
      while ( v14[v15] );
      std::wstring::_Append<wchar_t>(v21);
      std::vector<StateRepoHelper::FilterInfo>::push_back(*(_QWORD *)(a1 + 48), v17);
      StateRepoHelper::FilterInfo::~FilterInfo((StateRepoHelper::FilterInfo *)v17);
      WindowsDeleteString(string);
      result = 0;
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        662,
        "onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp");
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ElementValue,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1802125cc  push    rbx
0x1802125ce  push    rdi
0x1802125cf  push    r14
0x1802125d1  sub     rsp, 0D0h
0x1802125d8  mov     rax, cs:__security_cookie
0x1802125df  xor     rax, rsp
0x1802125e2  mov     [rsp+0E8h+var_28], rax
0x1802125ea  mov     rbx, rdx
0x1802125ed  mov     rdi, rcx
0x1802125f0  xor     r14d, r14d
0x1802125f3  mov     [r8], r14b
0x1802125f6  mov     [rsp+0E8h+string], r14
0x1802125fb  xor     ecx, ecx; string
0x1802125fd  call    cs:__imp_WindowsDeleteString
0x180212603  mov     [rsp+0E8h+string], r14; int
0x180212608  lea     r8, [rsp+0E8h+string]
0x18021260d  mov     rdx, rbx
0x180212610  lea     rcx, aText_0; "#text"
0x180212617  call    ?GetElementValue@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; StateRepoHelper::GetElementValue(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ * *)
0x18021261c  mov     ebx, eax
0x18021261e  test    eax, eax
0x180212620  jns     short loc_180212651
0x180212622  mov     rcx, [rsp+0E8h]; this
0x18021262a  mov     r9d, eax; char *
0x18021262d  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x180212634  mov     edx, 296h; void *
0x180212639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021263e  nop
0x18021263f  mov     rcx, [rsp+0E8h+string]; string
0x180212644  call    cs:__imp_WindowsDeleteString
0x18021264a  mov     eax, ebx
0x18021264c  jmp     loc_1802127C1
0x180212651  mov     rax, [rdi]
0x180212654  mov     rcx, [rax]
0x180212657  mov     [rsp+0E8h+var_B8], rcx
0x18021265c  mov     rax, [rdi+8]
0x180212660  mov     rcx, [rax]
0x180212663  mov     [rsp+0E8h+var_B0], rcx
0x180212668  mov     rcx, [rdi+10h]
0x18021266c  xor     edx, edx; length
0x18021266e  mov     rcx, [rcx]; string
0x180212671  call    cs:__imp_WindowsGetStringRawBuffer
0x180212677  mov     rdx, rax
0x18021267a  lea     rcx, [rsp+0E8h+var_A8]
0x18021267f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180212684  nop
0x180212685  lea     rdx, asc_18026C9AC; "{"
0x18021268c  lea     rcx, [rsp+0E8h+Src]
0x180212691  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180212696  nop
0x180212697  xor     edx, edx; length
0x180212699  mov     rcx, [rsp+0E8h+string]; string
0x18021269e  call    cs:__imp_WindowsGetStringRawBuffer
0x1802126a4  mov     rdx, rax
0x1802126a7  lea     rcx, [rsp+0E8h+var_68]
0x1802126af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802126b4  nop
0x1802126b5  mov     rcx, [rdi+18h]
0x1802126b9  xor     edx, edx; length
0x1802126bb  mov     rcx, [rcx]; string
0x1802126be  call    cs:__imp_WindowsGetStringRawBuffer
0x1802126c4  mov     rdx, rax
0x1802126c7  lea     rcx, [rsp+0E8h+var_48]
0x1802126cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802126d4  nop
0x1802126d5  mov     rcx, [rdi+20h]
0x1802126d9  xor     edx, edx; length
0x1802126db  mov     rcx, [rcx]; string
0x1802126de  call    cs:__imp_WindowsGetStringRawBuffer
0x1802126e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802126e8  mov     r8, rbx
0x1802126eb  inc     r8
0x1802126ee  cmp     [rax+r8*2], r14w
0x1802126f3  jnz     short loc_1802126EB
0x1802126f5  mov     rdx, rax
0x1802126f8  lea     rcx, [rsp+0E8h+Src]; Src
0x1802126fd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180212702  mov     r8d, 1
0x180212708  lea     rdx, asc_18026C9A8; "}"
0x18021270f  lea     rcx, [rsp+0E8h+Src]; Src
0x180212714  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180212719  lea     rcx, [rsp+0E8h+var_48]
0x180212721  cmp     [rsp+0E8h+var_30], 7
0x18021272a  cmova   rcx, [rsp+0E8h+var_48]
0x180212733  mov     rax, [rsp+0E8h+var_38]
0x18021273b  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x180212741  jz      short loc_18021275D
0x180212743  mov     r8d, 1
0x180212749  lea     rdx, StringValue; "\\"
0x180212750  lea     rcx, [rsp+0E8h+var_48]; Src
0x180212758  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18021275d  mov     rcx, [rdi+28h]
0x180212761  xor     edx, edx; length
0x180212763  mov     rcx, [rcx]; string
0x180212766  call    cs:__imp_WindowsGetStringRawBuffer
0x18021276c  inc     rbx
0x18021276f  cmp     [rax+rbx*2], r14w
0x180212774  jnz     short loc_18021276C
0x180212776  mov     r8, rbx
0x180212779  mov     rdx, rax
0x18021277c  lea     rcx, [rsp+0E8h+var_48]; Src
0x180212784  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180212789  lea     rdx, [rsp+0E8h+var_B8]
0x18021278e  mov     rcx, [rdi+30h]
0x180212792  call    ?push_back@?$vector@UFilterInfo@StateRepoHelper@@V?$allocator@UFilterInfo@StateRepoHelper@@@std@@@std@@QEAAX$$QEAUFilterInfo@StateRepoHelper@@@Z; std::vector<StateRepoHelper::FilterInfo>::push_back(StateRepoHelper::FilterInfo &&)
0x180212797  nop
0x180212798  lea     rcx, [rsp+0E8h+var_B8]; this
0x18021279d  call    ??1FilterInfo@StateRepoHelper@@QEAA@XZ; StateRepoHelper::FilterInfo::~FilterInfo(void)
0x1802127a2  nop
0x1802127a3  mov     rcx, [rsp+0E8h+string]; string
0x1802127a8  call    cs:__imp_WindowsDeleteString
0x1802127ae  xor     eax, eax
0x1802127b0  jmp     short loc_1802127C1
0x1802127b2  mov     rcx, [rsp+0E8h+string]; string
0x1802127b7  call    cs:__imp_WindowsDeleteString
0x1802127bd  mov     eax, [rsp+0E8h+var_C0]
0x1802127c1  mov     rcx, [rsp+0E8h+var_28]
0x1802127c9  xor     rcx, rsp; StackCookie
0x1802127cc  call    __security_check_cookie
0x1802127d1  add     rsp, 0D0h
0x1802127d8  pop     r14
0x1802127da  pop     rdi
0x1802127db  pop     rbx
0x1802127dc  retn
```

# Windows::AI::IsolationEnvironment::ProvisionResult::RuntimeClassInitialize(Windows::AI::IsolationEnvironment::IsolationProvisionStatus,long,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180048000`
- end: `0x1800480e1`
- name: `?RuntimeClassInitialize@ProvisionResult@IsolationEnvironment@AI@Windows@@QEAAJW4IsolationProvisionStatus@234@JAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `225`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014380`
- `0x180014464`
- `0x1800219dc`
- `0x180022424`

## callees

- `0x18000a464`
- `0x180047b38`
- `0x180047bac`
- `0x180048000`
- `0x180048478`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004809a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004809a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480d7`

## string_xrefs

- `0x1800480c0`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\provisionresult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::ProvisionResult::RuntimeClassInitialize(
        __int64 a1,
        int a2,
        int a3,
        _QWORD *a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdi
  _QWORD *v7; // rbp
  const WCHAR *v8; // rax
  HRESULT v9; // eax
  unsigned int v10; // ebx
  HSTRING *v11; // rdx
  HSTRING v12; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  const WCHAR *v17; // [rsp+58h] [rbp+20h] BYREF

  *(_DWORD *)(a1 + 48) = a2;
  *(_DWORD *)(a1 + 52) = a3;
  v5 = a1 + 104;
  std::vector<Microsoft::WRL::Wrappers::HString>::reserve(a1 + 104, (__int64)(a4[1] - *a4) >> 5);
  v6 = (_QWORD *)*a4;
  v7 = (_QWORD *)a4[1];
  while ( 1 )
  {
    if ( v6 == v7 )
      return 0;
    string = 0;
    v8 = v6[3] <= 7u ? (const WCHAR *)v6 : (const WCHAR *)*v6;
    v17 = v8;
    v9 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&string, &v17);
    v10 = v9;
    if ( v9 < 0 )
      break;
    v11 = *(HSTRING **)(v5 + 8);
    if ( v11 == *(HSTRING **)(v5 + 16) )
    {
      std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(
        v5,
        v11,
        &string);
      v12 = string;
    }
    else
    {
      *v11 = string;
      v12 = 0;
      string = 0;
      *(_QWORD *)(v5 + 8) += 8LL;
    }
    WindowsDeleteString(v12);
    v6 += 4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\provisionresult.cpp",
    (const char *)(unsigned int)v9,
    v14);
  WindowsDeleteString(string);
  return v10;
}

```

## disassembly

```asm
0x180048000  mov     [rsp+arg_8], rbx
0x180048005  push    rbp
0x180048006  push    rsi
0x180048007  push    rdi
0x180048008  sub     rsp, 20h
0x18004800c  mov     rbx, r9
0x18004800f  mov     [rcx+30h], edx
0x180048012  mov     [rcx+34h], r8d
0x180048016  lea     rsi, [rcx+68h]
0x18004801a  mov     rdx, [r9+8]
0x18004801e  sub     rdx, [r9]
0x180048021  sar     rdx, 5
0x180048025  mov     rcx, rsi
0x180048028  call    ?reserve@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAAX_K@Z; std::vector<Microsoft::WRL::Wrappers::HString>::reserve(unsigned __int64)
0x18004802d  mov     rdi, [rbx]
0x180048030  mov     rbp, [rbx+8]
0x180048034  jmp     short loc_1800480A4
0x180048036  mov     [rsp+38h+string], 0
0x18004803f  cmp     qword ptr [rdi+18h], 7
0x180048044  jbe     short loc_18004804B
0x180048046  mov     rax, [rdi]
0x180048049  jmp     short loc_18004804E
0x18004804b  mov     rax, rdi
0x18004804e  mov     [rsp+38h+arg_18], rax
0x180048053  lea     rdx, [rsp+38h+arg_18]
0x180048058  lea     rcx, [rsp+38h+string]; string
0x18004805d  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180048062  mov     ebx, eax
0x180048064  test    eax, eax
0x180048066  js      short loc_1800480B8
0x180048068  mov     rdx, [rsi+8]
0x18004806c  cmp     rdx, [rsi+10h]
0x180048070  jz      short loc_180048088
0x180048072  mov     rax, [rsp+38h+string]
0x180048077  mov     [rdx], rax
0x18004807a  xor     ecx, ecx
0x18004807c  mov     [rsp+38h+string], rcx
0x180048081  add     qword ptr [rsi+8], 8
0x180048086  jmp     short loc_18004809A
0x180048088  lea     r8, [rsp+38h+string]
0x18004808d  mov     rcx, rsi
0x180048090  call    ??$_Emplace_reallocate@VHString@Wrappers@WRL@Microsoft@@@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAVHString@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString * const,Microsoft::WRL::Wrappers::HString &&)
0x180048095  mov     rcx, [rsp+38h+string]; string
0x18004809a  call    cs:__imp_WindowsDeleteString
0x1800480a0  add     rdi, 20h ; ' '
0x1800480a4  cmp     rdi, rbp
0x1800480a7  jnz     short loc_180048036
0x1800480a9  xor     eax, eax
0x1800480ab  mov     rbx, [rsp+38h+arg_8]
0x1800480b0  add     rsp, 20h
0x1800480b4  pop     rdi
0x1800480b5  pop     rsi
0x1800480b6  pop     rbp
0x1800480b7  retn
0x1800480b8  mov     rcx, [rsp+38h]; this
0x1800480bd  mov     r9d, ebx; char *
0x1800480c0  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800480c7  mov     edx, 12h; void *
0x1800480cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480d1  nop
0x1800480d2  mov     rcx, [rsp+38h+string]; string
0x1800480d7  call    cs:__imp_WindowsDeleteString
0x1800480dd  mov     eax, ebx
0x1800480df  jmp     short loc_1800480AB
```

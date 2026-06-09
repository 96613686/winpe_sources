# _lambda_094ae5f9b4fc1013eabe3ab3e7d83e48_::operator()

- ea: `0x140047fd8`
- end: `0x1400480e5`
- name: `_lambda_094ae5f9b4fc1013eabe3ab3e7d83e48_::operator()`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400474c4`

## callees

- `0x140028044`
- `0x140047fd8`
- `0x1400480ec`
- `0x140048418`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140048011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004803c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400480b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400480ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140048011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004803c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400480b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400480ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140048086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140048095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140048086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140048095`

## string_xrefs

- `0x14004806a`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140048026`: `@ProtocolName`
- `0x140048051`: `@ProtocolActivatorCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_094ae5f9b4fc1013eabe3ab3e7d83e48_::operator()(__int64 *a1, __int64 a2, __int64 a3)
{
  int ElementValue; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v10; // rax
  HSTRING v12[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  v12[1] = (HSTRING)-2LL;
  string = 0;
  WindowsDeleteString(0);
  v12[0] = 0;
  ElementValue = StateRepoHelper::GetElementValue(L"@ProtocolName", a2, v12);
  v7 = ElementValue;
  if ( ElementValue < 0 )
    goto LABEL_3;
  WindowsDeleteString(string);
  string = 0;
  ElementValue = StateRepoHelper::GetElementValue(L"@ProtocolActivatorCLSID", a2, &string);
  v7 = ElementValue;
  if ( ElementValue < 0
    || (v8 = *a1,
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
        v10 = WindowsGetStringRawBuffer(v12[0], 0),
        ElementValue = lambda_3922738b78a3dc4c77f3f6a2e5a0db54_::operator()(v8, v10, StringRawBuffer, a3),
        v7 = ElementValue,
        ElementValue < 0) )
  {
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ElementValue,
      (int)v12[0]);
  }
  else
  {
    v7 = 0;
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v12[0]);
  return v7;
}

```

## disassembly

```asm
0x140047fd8  push    rbp
0x140047fda  push    rdi
0x140047fdb  push    r14
0x140047fdd  mov     rbp, rsp
0x140047fe0  sub     rsp, 30h
0x140047fe4  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x140047fec  mov     [rsp+30h+arg_0], rbx
0x140047ff1  mov     [rsp+30h+arg_8], rsi
0x140047ff6  mov     rsi, r8
0x140047ff9  mov     rdi, rdx
0x140047ffc  mov     r14, rcx
0x140047fff  mov     [rbp+var_10], 0
0x140048007  mov     [rbp+string], 0
0x14004800f  xor     ecx, ecx; string
0x140048011  call    cs:__imp_WindowsDeleteString
0x140048017  mov     [rbp+var_10], 0
0x14004801f  lea     r8, [rbp+var_10]
0x140048023  mov     rdx, rdi
0x140048026  lea     rcx, aProtocolname; "@ProtocolName"
0x14004802d  call    ?GetElementValue@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; StateRepoHelper::GetElementValue(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ * *)
0x140048032  mov     ebx, eax
0x140048034  test    eax, eax
0x140048036  js      short loc_140048063
0x140048038  mov     rcx, [rbp+string]; string
0x14004803c  call    cs:__imp_WindowsDeleteString
0x140048042  mov     [rbp+string], 0
0x14004804a  lea     r8, [rbp+string]
0x14004804e  mov     rdx, rdi
0x140048051  lea     rcx, aProtocolactiva; "@ProtocolActivatorCLSID"
0x140048058  call    ?GetElementValue@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; StateRepoHelper::GetElementValue(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ * *)
0x14004805d  mov     ebx, eax
0x14004805f  test    eax, eax
0x140048061  jns     short loc_14004807D
0x140048063  mov     rcx, [rbp+18h]; this
0x140048067  mov     r9d, eax; char *
0x14004806a  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140048071  mov     edx, 8Eh; void *
0x140048076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004807b  jmp     short loc_1400480B4
0x14004807d  mov     rdi, [r14]
0x140048080  xor     edx, edx; length
0x140048082  mov     rcx, [rbp+string]; string
0x140048086  call    cs:__imp_WindowsGetStringRawBuffer
0x14004808c  mov     rbx, rax
0x14004808f  xor     edx, edx; length
0x140048091  mov     rcx, [rbp+var_10]; string
0x140048095  call    cs:__imp_WindowsGetStringRawBuffer
0x14004809b  mov     r9, rsi
0x14004809e  mov     r8, rbx
0x1400480a1  mov     rdx, rax
0x1400480a4  mov     rcx, rdi
0x1400480a7  call    _lambda_3922738b78a3dc4c77f3f6a2e5a0db54___operator__
0x1400480ac  mov     ebx, eax
0x1400480ae  test    eax, eax
0x1400480b0  js      short loc_140048063
0x1400480b2  xor     ebx, ebx
0x1400480b4  mov     rcx, [rbp+string]; string
0x1400480b8  call    cs:__imp_WindowsDeleteString
0x1400480be  mov     [rbp+string], 0
0x1400480c6  mov     rcx, [rbp+var_10]; string
0x1400480ca  call    cs:__imp_WindowsDeleteString
0x1400480d0  mov     eax, ebx
0x1400480d2  mov     rbx, [rsp+30h+arg_0]
0x1400480d7  mov     rsi, [rsp+30h+arg_8]
0x1400480dc  add     rsp, 30h
0x1400480e0  pop     r14
0x1400480e2  pop     rdi
0x1400480e3  pop     rbp
0x1400480e4  retn
```

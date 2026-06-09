# Windows::UI::Composition::CompositionAnimation::GetPropertiesForParameter(ushort const *,Windows::UI::Composition::ExpressionAnimation *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x18013ebec`
- end: `0x18013ec8a`
- name: `?GetPropertiesForParameter@CompositionAnimation@Composition@UI@Windows@@IEAAJPEBGPEAVExpressionAnimation@234@PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180078820`
- `0x1800799d0`

## callees

- `0x18001358c`
- `0x180076934`
- `0x1800c983c`
- `0x18013ebec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013ec57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013ec57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ec13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ec72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ec13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013ec72`

## string_xrefs

- `0x18013ec3a`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimation.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimation::GetPropertiesForParameter(
        __int64 a1,
        __int64 a2,
        Windows::UI::Composition::ExpressionAnimation *a3,
        __int64 a4)
{
  int Expression; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  Expression = Windows::UI::Composition::ExpressionAnimation::GetExpression(a3, &string);
  v8 = Expression;
  if ( Expression >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    Windows::UI::Composition::CompositionAnimation::GetReferencedPropertiesFromExpression(v10, a2, StringRawBuffer, a4);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F9,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimation.cpp",
      (const char *)(unsigned int)Expression,
      v12);
  }
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x18013ebec  mov     rax, rsp
0x18013ebef  mov     [rax+10h], rbx
0x18013ebf3  mov     [rax+18h], rsi
0x18013ebf7  mov     [rax+8], rcx
0x18013ebfb  push    rdi; int
0x18013ebfc  sub     rsp, 20h
0x18013ec00  xor     ecx, ecx; string
0x18013ec02  mov     qword ptr [rax+8], 0
0x18013ec0a  mov     rdi, r9
0x18013ec0d  mov     rbx, r8
0x18013ec10  mov     rsi, rdx
0x18013ec13  call    cs:__imp_WindowsDeleteString
0x18013ec19  lea     rdx, [rsp+28h+string]; HSTRING *
0x18013ec1e  mov     [rsp+28h+string], 0
0x18013ec27  mov     rcx, rbx; this
0x18013ec2a  call    ?GetExpression@ExpressionAnimation@Composition@UI@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::ExpressionAnimation::GetExpression(HSTRING__ * *)
0x18013ec2f  mov     ebx, eax
0x18013ec31  test    eax, eax
0x18013ec33  jns     short loc_18013EC50
0x18013ec35  mov     rcx, [rsp+28h]; this
0x18013ec3a  lea     r8, aOnecoreuapWind_155; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18013ec41  mov     r9d, eax; char *
0x18013ec44  mov     edx, 5F9h; void *
0x18013ec49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ec4e  jmp     short loc_18013EC6D
0x18013ec50  mov     rcx, [rsp+28h+string]; string
0x18013ec55  xor     edx, edx; length
0x18013ec57  call    cs:__imp_WindowsGetStringRawBuffer
0x18013ec5d  mov     r9, rdi
0x18013ec60  mov     rdx, rsi
0x18013ec63  mov     r8, rax
0x18013ec66  call    ?GetReferencedPropertiesFromExpression@CompositionAnimation@Composition@UI@Windows@@IEAAXPEBG0PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Windows::UI::Composition::CompositionAnimation::GetReferencedPropertiesFromExpression(ushort const *,ushort const *,std::vector<std::wstring> *)
0x18013ec6b  xor     ebx, ebx
0x18013ec6d  mov     rcx, [rsp+28h+string]; string
0x18013ec72  call    cs:__imp_WindowsDeleteString
0x18013ec78  mov     rsi, [rsp+28h+arg_10]
0x18013ec7d  mov     eax, ebx
0x18013ec7f  mov     rbx, [rsp+28h+arg_8]
0x18013ec84  add     rsp, 20h
0x18013ec88  pop     rdi
0x18013ec89  retn
```

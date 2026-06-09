# SetRegistrationProperty<OpaqueString,OpaqueString>(Optional<OpaqueString> &,OpaqueString)

- ea: `0x1801480f0`
- end: `0x1801481e2`
- name: `??$SetRegistrationProperty@VOpaqueString@@V1@@@YAJAEAU?$Optional@VOpaqueString@@@@VOpaqueString@@@Z`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180164d44`
- `0x18016b8b0`

## callees

- `0x1800502a4`
- `0x18006a4c8`
- `0x1801480f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014813d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014816e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180148195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801481a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801481be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014813d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014816e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180148195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801481a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801481be`

## string_xrefs

- `0x180148124`: `onecore\private\com\inc\deployment\RegistrationStore.hpp`

## pseudocode

```c
__int64 __fastcall SetRegistrationProperty<OpaqueString,OpaqueString>(__int64 a1, HSTRING *a2)
{
  __int64 result; // rax
  const struct OpaqueString *v5; // rdi
  OpaqueString *v6; // rbx
  char *v7; // [rsp+28h] [rbp-20h]
  int v8; // [rsp+30h] [rbp-18h]
  wil::details::in1diag5 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  HSTRING newString; // [rsp+60h] [rbp+18h] BYREF

  if ( *(_BYTE *)a1 )
  {
    LODWORD(v7) = -2147483635;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x527,
      (unsigned int)"onecore\\private\\com\\inc\\deployment\\RegistrationStore.hpp",
      "SetRegistrationProperty",
      "property.Present",
      v7,
      v8);
    WindowsDeleteString(*a2);
    result = 2147483661LL;
  }
  else
  {
    v5 = OpaqueString::OpaqueString(&newString, (const struct OpaqueString *)a2);
    v6 = OpaqueString::OpaqueString(&string, v5);
    WindowsDeleteString(*(HSTRING *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)v6;
    *(_QWORD *)v6 = 0;
    WindowsDeleteString(string);
    WindowsDeleteString(*(HSTRING *)v5);
    *(_QWORD *)v5 = 0;
    *(_BYTE *)a1 = 1;
    WindowsDeleteString(*a2);
    result = 0;
  }
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1801480f0  mov     [rsp+arg_8], rbx
0x1801480f5  push    rsi
0x1801480f6  push    rdi
0x1801480f7  push    r14; int
0x1801480f9  sub     rsp, 30h
0x1801480fd  cmp     byte ptr [rcx], 0
0x180148100  mov     rsi, rdx
0x180148103  mov     r14, rcx
0x180148106  jz      short loc_18014814D
0x180148108  mov     rcx, [rsp+48h]; this
0x18014810d  lea     rdx, aPropertyPresen_0; "property.Present"
0x180148114  mov     ebx, 8000000Dh
0x180148119  lea     r9, aSetregistratio_55; "SetRegistrationProperty"
0x180148120  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x180148124  lea     r8, aOnecorePrivate_1; "onecore\\private\\com\\inc\\deployment"...
0x18014812b  mov     [rsp+48h+var_28], rdx; char *
0x180148130  mov     edx, 527h; void *
0x180148135  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014813a  mov     rcx, [rsi]; string
0x18014813d  call    cs:__imp_WindowsDeleteString
0x180148144  nop     dword ptr [rax+rax+00h]
0x180148149  mov     eax, ebx
0x18014814b  jmp     short loc_1801481CC
0x18014814d  lea     rcx, [rsp+48h+newString]; newString
0x180148152  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x180148157  mov     rdx, rax; struct OpaqueString *
0x18014815a  lea     rcx, [rsp+48h+string]; newString
0x18014815f  mov     rdi, rax
0x180148162  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x180148167  mov     rcx, [r14+8]; string
0x18014816b  mov     rbx, rax
0x18014816e  call    cs:__imp_WindowsDeleteString
0x180148175  nop     dword ptr [rax+rax+00h]
0x18014817a  mov     qword ptr [r14+8], 0
0x180148182  mov     rcx, [rbx]
0x180148185  mov     [r14+8], rcx
0x180148189  mov     qword ptr [rbx], 0
0x180148190  mov     rcx, [rsp+48h+string]; string
0x180148195  call    cs:__imp_WindowsDeleteString
0x18014819c  nop     dword ptr [rax+rax+00h]
0x1801481a1  mov     rcx, [rdi]; string
0x1801481a4  call    cs:__imp_WindowsDeleteString
0x1801481ab  nop     dword ptr [rax+rax+00h]
0x1801481b0  mov     qword ptr [rdi], 0
0x1801481b7  mov     byte ptr [r14], 1
0x1801481bb  mov     rcx, [rsi]; string
0x1801481be  call    cs:__imp_WindowsDeleteString
0x1801481c5  nop     dword ptr [rax+rax+00h]
0x1801481ca  xor     eax, eax
0x1801481cc  mov     rbx, [rsp+48h+arg_8]
0x1801481d1  mov     qword ptr [rsi], 0
0x1801481d8  add     rsp, 30h
0x1801481dc  pop     r14
0x1801481de  pop     rdi
0x1801481df  pop     rsi
0x1801481e0  retn
```

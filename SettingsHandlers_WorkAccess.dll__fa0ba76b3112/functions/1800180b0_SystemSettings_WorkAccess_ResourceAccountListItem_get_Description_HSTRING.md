# SystemSettings::WorkAccess::ResourceAccountListItem::get_Description(HSTRING__ * *)

- ea: `0x1800180b0`
- end: `0x1800181c4`
- name: `?get_Description@ResourceAccountListItem@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `276`
- prototype: `int(SystemSettings::WorkAccess::ResourceAccountListItem *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180017744`
- `0x1800180b0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001813f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001813f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001811b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001811b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800180e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800180e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181a5`

## string_xrefs

- `0x180018177`: `shellcommon\shell\settingshandlers\workaccess\lib\resourceaccount.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::ResourceAccountListItem::get_Description(
        SystemSettings::WorkAccess::ResourceAccountListItem *this,
        HSTRING *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const WCHAR *StringRawBuffer; // rax
  HSTRING *v9; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  string = 0;
  v3 = *((_QWORD *)this + 27);
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v3 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(v3, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, &sourceString, -1, 1) == 2 )
    {
      v5 = SystemSettings::DataModel::WindowsCreateString(
             (SystemSettings::DataModel *)L"ResourceAccount",
             (const unsigned __int16 *)a2,
             v9);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 209;
        goto LABEL_6;
      }
    }
    else
    {
      v5 = WindowsDuplicateString(string, a2);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 204;
        goto LABEL_6;
      }
    }
    v6 = 0;
    goto LABEL_10;
  }
  v7 = 201;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\resourceaccount.cpp",
    (const char *)(unsigned int)v5,
    bIgnoreCase);
LABEL_10:
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x1800180b0  mov     [rsp+arg_8], rbx
0x1800180b5  mov     [rsp+arg_10], rsi
0x1800180ba  push    rdi
0x1800180bb  sub     rsp, 30h
0x1800180bf  mov     rsi, rdx
0x1800180c2  mov     qword ptr [rdx], 0
0x1800180c9  mov     [rsp+38h+string], 0
0x1800180d2  mov     rdi, [rcx+0D8h]
0x1800180d9  mov     rax, [rdi]
0x1800180dc  mov     rbx, [rax+60h]
0x1800180e0  xor     ecx, ecx; string
0x1800180e2  call    cs:__imp_WindowsDeleteString
0x1800180e9  nop     dword ptr [rax+rax+00h]
0x1800180ee  mov     [rsp+38h+string], 0
0x1800180f7  lea     rdx, [rsp+38h+string]
0x1800180fc  mov     rcx, rdi
0x1800180ff  mov     rax, rbx
0x180018102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018107  mov     ebx, eax
0x180018109  test    eax, eax
0x18001810b  jns     short loc_180018114
0x18001810d  mov     edx, 0C9h
0x180018112  jmp     short loc_18001816F
0x180018114  xor     edx, edx; length
0x180018116  mov     rcx, [rsp+38h+string]; string
0x18001811b  call    cs:__imp_WindowsGetStringRawBuffer
0x180018122  nop     dword ptr [rax+rax+00h]
0x180018127  mov     [rsp+38h+bIgnoreCase], 1; int
0x18001812f  or      edx, 0FFFFFFFFh; cchCount1
0x180018132  mov     r9d, edx; cchCount2
0x180018135  lea     r8, sourceString; lpString2
0x18001813c  mov     rcx, rax; lpString1
0x18001813f  call    cs:__imp_CompareStringOrdinal
0x180018146  nop     dword ptr [rax+rax+00h]
0x18001814b  mov     rdx, rsi; unsigned __int16 *
0x18001814e  cmp     eax, 2
0x180018151  jz      short loc_180018185
0x180018153  mov     rcx, [rsp+38h+string]; string
0x180018158  call    cs:__imp_WindowsDuplicateString
0x18001815f  nop     dword ptr [rax+rax+00h]
0x180018164  mov     ebx, eax
0x180018166  test    eax, eax
0x180018168  jns     short loc_18001819E
0x18001816a  mov     edx, 0CCh; void *
0x18001816f  mov     rcx, [rsp+38h]; this
0x180018174  mov     r9d, eax; char *
0x180018177  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\w"...
0x18001817e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018183  jmp     short loc_1800181A0
0x180018185  lea     rcx, aResourceaccoun; "ResourceAccount"
0x18001818c  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x180018191  mov     ebx, eax
0x180018193  test    eax, eax
0x180018195  jns     short loc_18001819E
0x180018197  mov     edx, 0D1h
0x18001819c  jmp     short loc_18001816F
0x18001819e  xor     ebx, ebx
0x1800181a0  mov     rcx, [rsp+38h+string]; string
0x1800181a5  call    cs:__imp_WindowsDeleteString
0x1800181ac  nop     dword ptr [rax+rax+00h]
0x1800181b1  mov     eax, ebx
0x1800181b3  mov     rbx, [rsp+38h+arg_8]
0x1800181b8  mov     rsi, [rsp+38h+arg_10]
0x1800181bd  add     rsp, 30h
0x1800181c1  pop     rdi
0x1800181c2  retn
```

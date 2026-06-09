# to_winstring(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001870c`
- end: `0x1800187be`
- name: `?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x1800174ac`
- `0x180017e74`
- `0x18001823c`
- `0x1800286e4`
- `0x18002bcc0`
- `0x180032450`
- `0x180060c00`
- `0x180060de0`
- `0x180069990`
- `0x18006a160`

## callees

- `0x18001870c`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001875f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001875f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001874a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001874a`

## string_xrefs

- `0x180018786`: `onecoreuap\shell\appreadiness\src\core\StdUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall to_winstring(HSTRING *string, const WCHAR *sourceString)
{
  const WCHAR *v2; // rbx
  UINT32 v4; // esi
  HRESULT v5; // eax
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-30h] BYREF

  v2 = sourceString;
  *string = 0;
  v4 = *((_DWORD *)sourceString + 4);
  if ( *((_QWORD *)sourceString + 3) > 7u )
    v2 = *(const WCHAR **)sourceString;
  WindowsDeleteString(0);
  *string = 0;
  v5 = WindowsCreateString(v2, v4, string);
  if ( v5 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v5,
      "s.Set(str.c_str(), static_cast<UINT>(str.length()))",
      "to_winstring",
      "onecoreuap\\shell\\appreadiness\\src\\core\\StdUtils.h",
      26);
    throw (Windows::HResultException *)pExceptionObject;
  }
  return string;
}

```

## disassembly

```asm
0x18001870c  mov     rax, rsp
0x18001870f  mov     [rax+10h], rbx
0x180018713  mov     [rax+18h], rsi
0x180018717  mov     [rax+8], rcx
0x18001871b  push    rdi
0x18001871c  sub     rsp, 60h
0x180018720  mov     rbx, rdx
0x180018723  mov     rdi, rcx
0x180018726  mov     dword ptr [rax-38h], 0
0x18001872d  mov     qword ptr [rcx], 0
0x180018734  mov     dword ptr [rax-38h], 1
0x18001873b  mov     esi, [rdx+10h]
0x18001873e  cmp     qword ptr [rdx+18h], 7
0x180018743  jbe     short loc_180018748
0x180018745  mov     rbx, [rdx]
0x180018748  xor     ecx, ecx; string
0x18001874a  call    cs:__imp_WindowsDeleteString
0x180018750  mov     qword ptr [rdi], 0
0x180018757  mov     r8, rdi; string
0x18001875a  mov     edx, esi; length
0x18001875c  mov     rcx, rbx; sourceString
0x18001875f  call    cs:__imp_WindowsCreateString
0x180018765  test    eax, eax
0x180018767  js      short loc_18001877E
0x180018769  mov     rax, rdi
0x18001876c  lea     r11, [rsp+68h+var_8]
0x180018771  mov     rbx, [r11+18h]
0x180018775  mov     rsi, [r11+20h]
0x180018779  mov     rsp, r11
0x18001877c  pop     rdi
0x18001877d  retn
0x18001877e  mov     [rsp+68h+var_40], 1Ah; int
0x180018786  lea     rcx, aOnecoreuapShel_3; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001878d  mov     [rsp+68h+var_48], rcx; char *
0x180018792  lea     r9, aToWinstring; "to_winstring"
0x180018799  lea     r8, aSSetStrCStrSta; "s.Set(str.c_str(), static_cast<UINT>(st"...
0x1800187a0  mov     edx, eax; int
0x1800187a2  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800187a7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800187ac  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800187b3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800187b8  call    _CxxThrowException_0
```

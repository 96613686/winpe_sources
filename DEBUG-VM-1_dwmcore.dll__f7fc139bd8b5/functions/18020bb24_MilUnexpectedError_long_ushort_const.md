# MilUnexpectedError(long,ushort const *)

- ea: `0x18020bb24`
- end: `0x18020bc1d`
- name: `?MilUnexpectedError@@YAXJPEBG@Z`
- size: `249`
- prototype: `void __fastcall(int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180111330`

## callees

- `0x180008e08`
- `0x180202b60`
- `0x18020bb24`
- `0x180228490`
- `0x180278c74`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18020bb75`
- `ntdll!DbgPrintEx` at `0x18020bb75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020bbad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020bbad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18020bbd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18020bbd4`

## string_xrefs

- `0x18020bbed`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

## pseudocode

```c
void __fastcall MilUnexpectedError(unsigned int a1, const unsigned __int16 *a2)
{
  bool Dword; // bl
  int phkResult; // [rsp+20h] [rbp-238h]
  unsigned int v4; // [rsp+30h] [rbp-228h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-220h] BYREF
  unsigned __int16 v6[256]; // [rsp+40h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  StringCchPrintfW(v6, 0x100u, L"MIL FAILURE: Unexpected HRESULT 0x%08x in caller: %s", a1, L"batch processing error");
  DbgPrintEx(0x65u, 0, "%S\n", v6);
  v4 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey) )
  {
    Dword = RegGetDword(hKey, L"BreakOnUnexpectedErrors", &v4);
    RegCloseKey(hKey);
    if ( Dword )
    {
      if ( v4 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\windows\\dwm\\common\\util\\utillib\\debugbreak.cpp",
          (const char *)0x8007029CLL,
          phkResult);
    }
  }
}

```

## disassembly

```asm
0x18020bb24  push    rbx
0x18020bb26  sub     rsp, 250h
0x18020bb2d  mov     rax, cs:__security_cookie
0x18020bb34  xor     rax, rsp
0x18020bb37  mov     [rsp+258h+var_18], rax
0x18020bb3f  lea     rax, aBatchProcessin; "batch processing error"
0x18020bb46  mov     r9d, ecx
0x18020bb49  lea     rcx, [rsp+258h+var_218]; unsigned __int16 *
0x18020bb4e  mov     qword ptr [rsp+258h+phkResult], rax
0x18020bb53  lea     r8, aMilFailureUnex; "MIL FAILURE: Unexpected HRESULT 0x%08x "...
0x18020bb5a  mov     edx, 100h; unsigned __int64
0x18020bb5f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18020bb64  xor     edx, edx; Level
0x18020bb66  lea     r9, [rsp+258h+var_218]
0x18020bb6b  lea     r8, Format; "%S\n"
0x18020bb72  lea     ecx, [rdx+65h]; ComponentId
0x18020bb75  call    cs:__imp_DbgPrintEx
0x18020bb7b  lea     rax, [rsp+258h+hKey]
0x18020bb80  mov     [rsp+258h+var_228], 0
0x18020bb88  mov     r9d, 20019h; samDesired
0x18020bb8e  mov     qword ptr [rsp+258h+phkResult], rax; int
0x18020bb93  xor     r8d, r8d; ulOptions
0x18020bb96  mov     [rsp+258h+hKey], 0
0x18020bb9f  lea     rdx, SubKey; "Software\\Microsoft\\Avalon.Graphics"
0x18020bba6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18020bbad  call    cs:__imp_RegOpenKeyExW
0x18020bbb3  test    eax, eax
0x18020bbb5  jnz     short loc_18020BC04
0x18020bbb7  mov     rcx, [rsp+258h+hKey]; HKEY
0x18020bbbc  lea     r8, [rsp+258h+var_228]; unsigned int *
0x18020bbc1  lea     rdx, aBreakonunexpec; "BreakOnUnexpectedErrors"
0x18020bbc8  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x18020bbcd  mov     rcx, [rsp+258h+hKey]; hKey
0x18020bbd2  mov     bl, al
0x18020bbd4  call    cs:__imp_RegCloseKey
0x18020bbda  test    bl, bl
0x18020bbdc  jz      short loc_18020BC04
0x18020bbde  cmp     [rsp+258h+var_228], 0
0x18020bbe3  jz      short loc_18020BC04
0x18020bbe5  mov     rcx, [rsp+258h]; this
0x18020bbed  lea     r8, aOnecoreuapWind_216; "onecoreuap\\windows\\dwm\\common\\util"...
0x18020bbf4  mov     r9d, 8007029Ch; char *
0x18020bbfa  mov     edx, 0AAh; void *
0x18020bbff  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18020bc04  mov     rcx, [rsp+258h+var_18]
0x18020bc0c  xor     rcx, rsp; StackCookie
0x18020bc0f  call    __security_check_cookie
0x18020bc14  add     rsp, 250h
0x18020bc1b  pop     rbx
0x18020bc1c  retn
```

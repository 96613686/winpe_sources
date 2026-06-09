# UtilElevatedManager::EnableDriverUpdate(void)

- ea: `0x180049830`
- end: `0x180049873`
- name: `?EnableDriverUpdate@UtilElevatedManager@@UEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(UtilElevatedManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180027aec`
- `0x180049830`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180049849`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180049849`

## string_xrefs

- `0x180049858`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`
- `0x180049834`: `OOBEInProgressDriverUpdatesPostponed`

## pseudocode

```c
__int64 __fastcall UtilElevatedManager::EnableDriverUpdate(UtilElevatedManager *this)
{
  unsigned int v1; // eax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = SHDeleteValueW(HKEY_LOCAL_MACHINE, L"System\\Setup", L"OOBEInProgressDriverUpdatesPostponed");
  if ( v1 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
      (const char *)v1,
      v3);
  return 0;
}

```

## disassembly

```asm
0x180049830  sub     rsp, 28h
0x180049834  lea     r8, pszValue; "OOBEInProgressDriverUpdatesPostponed"
0x18004983b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180049842  lea     rdx, pszSubKey; "System\\Setup"
0x180049849  call    cs:__imp_SHDeleteValueW
0x18004984f  test    eax, eax
0x180049851  jz      short loc_18004986C
0x180049853  mov     rcx, [rsp+28h]; this
0x180049858  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x18004985f  mov     r9d, eax; char *
0x180049862  mov     edx, 38h ; '8'; void *
0x180049867  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18004986c  xor     eax, eax
0x18004986e  add     rsp, 28h
0x180049872  retn
```

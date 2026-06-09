# GetResInst

- ea: `0x14007abf8`
- end: `0x14007ad1a`
- name: `GetResInst`
- size: `290`
- prototype: `HMODULE()`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140025b04`
- `0x14002c488`

## callees

- `0x140004c78`
- `0x140004f64`
- `0x14007abf8`
- `0x14007ad20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007ac6f`
- `KERNEL32!GetLastError` at `0x14007acd9`
- `KERNEL32!GetLastError` at `0x14007ac6f`
- `KERNEL32!GetLastError` at `0x14007acd9`
- `KERNEL32!LoadLibraryW` at `0x14007aca9`
- `KERNEL32!LoadLibraryW` at `0x14007aca9`

## string_xrefs

- `0x14007ac82`: `FXSRESM.DLL`
- `0x14007aca2`: `FXSRESM.DLL`
- `0x14007acec`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE GetResInst()
{
  HMODULE result; // rax
  char LastError; // al
  char v2; // al

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  result = hLibModule;
  if ( !hLibModule )
  {
    result = LoadLibraryFromLocalFolder();
    hLibModule = result;
    if ( !result )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
          (unsigned int)L"FXSRESM.DLL",
          LastError);
      }
      result = LoadLibraryW(L"FXSRESM.DLL");
      hLibModule = result;
      if ( !result
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v2 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
          (unsigned int)L"FXSRESM.DLL",
          v2);
        return hLibModule;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14007abf8  push    rdi
0x14007abfa  sub     rsp, 30h
0x14007abfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac05  lea     rdi, WPP_GLOBAL_Control
0x14007ac0c  cmp     rcx, rdi
0x14007ac0f  jz      short loc_14007AC32
0x14007ac11  test    byte ptr [rcx+1Ch], 2
0x14007ac15  jz      short loc_14007AC32
0x14007ac17  cmp     byte ptr [rcx+19h], 5
0x14007ac1b  jb      short loc_14007AC32
0x14007ac1d  mov     rcx, [rcx+10h]
0x14007ac21  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007ac28  mov     edx, 0Ah
0x14007ac2d  call    WPP_SF_
0x14007ac32  mov     rax, cs:hLibModule
0x14007ac39  test    rax, rax
0x14007ac3c  jnz     loc_14007AD13
0x14007ac42  call    LoadLibraryFromLocalFolder
0x14007ac47  mov     cs:hLibModule, rax
0x14007ac4e  test    rax, rax
0x14007ac51  jnz     loc_14007AD13
0x14007ac57  mov     rax, cs:WPP_GLOBAL_Control
0x14007ac5e  cmp     rax, rdi
0x14007ac61  jz      short loc_14007ACA2
0x14007ac63  test    byte ptr [rax+1Ch], 2
0x14007ac67  jz      short loc_14007ACA2
0x14007ac69  cmp     byte ptr [rax+19h], 2
0x14007ac6d  jb      short loc_14007ACA2
0x14007ac6f  call    cs:__imp_GetLastError
0x14007ac76  nop     dword ptr [rax+rax+00h]
0x14007ac7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac82  lea     r9, aFxsresmDll; "FXSRESM.DLL"
0x14007ac89  mov     edx, 0Bh
0x14007ac8e  mov     [rsp+38h+var_18], eax
0x14007ac92  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007ac99  mov     rcx, [rcx+10h]
0x14007ac9d  call    WPP_SF_Sd
0x14007aca2  lea     rcx, aFxsresmDll; "FXSRESM.DLL"
0x14007aca9  call    cs:__imp_LoadLibraryW
0x14007acb0  nop     dword ptr [rax+rax+00h]
0x14007acb5  mov     cs:hLibModule, rax
0x14007acbc  test    rax, rax
0x14007acbf  jnz     short loc_14007AD13
0x14007acc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14007acc8  cmp     rcx, rdi
0x14007accb  jz      short loc_14007AD13
0x14007accd  test    byte ptr [rcx+1Ch], 2
0x14007acd1  jz      short loc_14007AD13
0x14007acd3  cmp     byte ptr [rcx+19h], 2
0x14007acd7  jb      short loc_14007AD13
0x14007acd9  call    cs:__imp_GetLastError
0x14007ace0  nop     dword ptr [rax+rax+00h]
0x14007ace5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007acec  lea     r9, aFxsresmDll; "FXSRESM.DLL"
0x14007acf3  mov     edx, 0Ch
0x14007acf8  mov     [rsp+38h+var_18], eax
0x14007acfc  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007ad03  mov     rcx, [rcx+10h]
0x14007ad07  call    WPP_SF_Sd
0x14007ad0c  mov     rax, cs:hLibModule
0x14007ad13  add     rsp, 30h
0x14007ad17  pop     rdi
0x14007ad18  retn
```

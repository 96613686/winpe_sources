# PlatformUtils::SetOobeCompleted(void)

- ea: `0x14000a340`
- end: `0x14000a4ee`
- name: `?SetOobeCompleted@PlatformUtils@@YAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(PlatformUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a340`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000a37e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a37e`
- `ADVAPI32!RegCloseKey` at `0x14000a4d8`
- `ADVAPI32!RegCloseKey` at `0x14000a4d8`
- `ADVAPI32!RegSetValueExW` at `0x14000a43d`
- `ADVAPI32!RegSetValueExW` at `0x14000a43d`
- `KERNEL32!IsDebuggerPresent` at `0x14000a3ce`
- `KERNEL32!IsDebuggerPresent` at `0x14000a48f`
- `KERNEL32!IsDebuggerPresent` at `0x14000a3ce`
- `KERNEL32!IsDebuggerPresent` at `0x14000a48f`

## string_xrefs

- `0x14000a3c2`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a3e2`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a483`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a4ae`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14000a3a4`: `PlatformUtils::SetOobeCompleted`
- `0x14000a465`: `PlatformUtils::SetOobeCompleted`
- `0x14000a425`: `OOBECompleted`

## pseudocode

```c
__int64 __fastcall PlatformUtils::SetOobeCompleted(PlatformUtils *this)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // r8
  LSTATUS v5; // eax
  unsigned int v7; // [rsp+30h] [rbp-28h]
  unsigned int v8; // [rsp+38h] [rbp-20h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  Data = 1;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows MultiPoint Server", 0, 0x20006u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      0x44u,
      L"PlatformUtils::SetOobeCompleted",
      L"CBRAEx",
      L"lr == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 68;
LABEL_6:
      v8 = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
        v3,
        L"PlatformUtils::SetOobeCompleted",
        L"CBRAEx",
        L"lr == 0L",
        v8);
      goto LABEL_16;
    }
    v4 = 68;
  }
  else
  {
    v2 = 0;
    v5 = RegSetValueExW(hKey, L"OOBECompleted", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      0x47u,
      L"PlatformUtils::SetOobeCompleted",
      L"CBRAEx",
      L"lr == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 71;
      goto LABEL_6;
    }
    v4 = 71;
  }
  v7 = v2;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
    v4,
    L"PlatformUtils::SetOobeCompleted",
    L"CBRAEx",
    L"lr == 0L",
    v7);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x14000a340  mov     rax, rsp
0x14000a343  mov     [rax+18h], rbx
0x14000a347  push    rbp
0x14000a348  push    rsi
0x14000a349  push    r14
0x14000a34b  sub     rsp, 40h
0x14000a34f  mov     qword ptr [rax+10h], 0
0x14000a357  mov     r9d, 20006h; samDesired
0x14000a35d  mov     dword ptr [rax+8], 1
0x14000a364  lea     rax, [rax+10h]
0x14000a368  xor     r8d, r8d; ulOptions
0x14000a36b  mov     [rsp+58h+phkResult], rax; phkResult
0x14000a370  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14000a377  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a37e  call    cs:__imp_RegOpenKeyExW
0x14000a384  mov     ebx, eax
0x14000a386  test    eax, eax
0x14000a388  jz      loc_14000A419
0x14000a38e  jle     short loc_14000A399
0x14000a390  movzx   ebx, ax
0x14000a393  or      ebx, 80070000h
0x14000a399  lea     r14, aCbraex; "CBRAEx"
0x14000a3a0  mov     [rsp+58h+cbData], ebx; int
0x14000a3a4  lea     rsi, aPlatformutilsS; "PlatformUtils::SetOobeCompleted"
0x14000a3ab  mov     r9, r14; unsigned __int16 *
0x14000a3ae  lea     rbp, aLr0l; "lr == 0L"
0x14000a3b5  mov     r8, rsi; unsigned __int16 *
0x14000a3b8  mov     edx, 44h ; 'D'; unsigned int
0x14000a3bd  mov     [rsp+58h+phkResult], rbp; unsigned __int16 *
0x14000a3c2  lea     rcx, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a3c9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a3ce  call    cs:__imp_IsDebuggerPresent
0x14000a3d4  test    eax, eax
0x14000a3d6  jz      short loc_14000A40E
0x14000a3d8  mov     r9d, 44h ; 'D'
0x14000a3de  mov     [rsp+58h+var_20], ebx
0x14000a3e2  lea     r8, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a3e9  mov     [rsp+58h+var_28], rbp
0x14000a3ee  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a3f5  mov     qword ptr [rsp+58h+cbData], r14
0x14000a3fa  mov     ecx, 2; unsigned __int8
0x14000a3ff  mov     [rsp+58h+phkResult], rsi
0x14000a404  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a409  jmp     loc_14000A4CE
0x14000a40e  mov     r8d, 44h ; 'D'
0x14000a414  jmp     loc_14000A4AA
0x14000a419  mov     rcx, [rsp+58h+hKey]; hKey
0x14000a41e  lea     rax, [rsp+58h+Data]
0x14000a423  xor     ebx, ebx
0x14000a425  lea     rdx, aOobecompleted; "OOBECompleted"
0x14000a42c  xor     r8d, r8d; Reserved
0x14000a42f  lea     r9d, [rbx+4]; dwType
0x14000a433  mov     [rsp+58h+cbData], r9d; cbData
0x14000a438  mov     [rsp+58h+phkResult], rax; lpData
0x14000a43d  call    cs:__imp_RegSetValueExW
0x14000a443  test    eax, eax
0x14000a445  jz      loc_14000A4CE
0x14000a44b  jg      short loc_14000A451
0x14000a44d  mov     ebx, eax
0x14000a44f  jmp     short loc_14000A45A
0x14000a451  movzx   ebx, ax
0x14000a454  or      ebx, 80070000h
0x14000a45a  lea     r14, aCbraex; "CBRAEx"
0x14000a461  mov     [rsp+58h+cbData], ebx; int
0x14000a465  lea     rsi, aPlatformutilsS; "PlatformUtils::SetOobeCompleted"
0x14000a46c  mov     r9, r14; unsigned __int16 *
0x14000a46f  lea     rbp, aLr0l; "lr == 0L"
0x14000a476  mov     r8, rsi; unsigned __int16 *
0x14000a479  mov     edx, 47h ; 'G'; unsigned int
0x14000a47e  mov     [rsp+58h+phkResult], rbp; unsigned __int16 *
0x14000a483  lea     rcx, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a48a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a48f  call    cs:__imp_IsDebuggerPresent
0x14000a495  test    eax, eax
0x14000a497  jz      short loc_14000A4A4
0x14000a499  mov     r9d, 47h ; 'G'
0x14000a49f  jmp     loc_14000A3DE
0x14000a4a4  mov     r8d, 47h ; 'G'
0x14000a4aa  mov     dword ptr [rsp+58h+var_28], ebx
0x14000a4ae  lea     rdx, aTermsrvWmsSrcC_0; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a4b5  mov     qword ptr [rsp+58h+cbData], rbp
0x14000a4ba  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a4c1  mov     r9, rsi
0x14000a4c4  mov     [rsp+58h+phkResult], r14
0x14000a4c9  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a4ce  mov     rcx, [rsp+58h+hKey]; hKey
0x14000a4d3  test    rcx, rcx
0x14000a4d6  jz      short loc_14000A4DE
0x14000a4d8  call    cs:__imp_RegCloseKey
0x14000a4de  mov     eax, ebx
0x14000a4e0  mov     rbx, [rsp+58h+arg_10]
0x14000a4e5  add     rsp, 40h
0x14000a4e9  pop     r14
0x14000a4eb  pop     rsi
0x14000a4ec  pop     rbp
0x14000a4ed  retn
```

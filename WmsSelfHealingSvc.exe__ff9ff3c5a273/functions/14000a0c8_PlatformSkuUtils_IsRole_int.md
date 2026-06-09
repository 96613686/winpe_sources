# PlatformSkuUtils::IsRole(int *)

- ea: `0x14000a0c8`
- end: `0x14000a1ff`
- name: `?IsRole@PlatformSkuUtils@@YAJPEAH@Z`
- size: `311`
- prototype: `__int64 __fastcall(PlatformSkuUtils *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a0c8`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000a123`
- `ADVAPI32!RegGetValueW` at `0x14000a123`
- `KERNEL32!IsDebuggerPresent` at `0x14000a17a`
- `KERNEL32!IsDebuggerPresent` at `0x14000a17a`

## string_xrefs

- `0x14000a16e`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x14000a188`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x14000a1b6`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x14000a0ed`: `RoleInstalled`

## pseudocode

```c
__int64 __fastcall PlatformSkuUtils::IsRole(PlatformSkuUtils *this, int *a2)
{
  LSTATUS ValueW; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-28h]
  unsigned int v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+68h] [rbp+10h] BYREF
  DWORD v9; // [rsp+70h] [rbp+18h] BYREF

  v8 = 0;
  v9 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server",
             L"RoleInstalled",
             0x10u,
             0,
             &v8,
             &v9);
  v4 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\platformskuutils.cpp",
      0x20u,
      L"PlatformSkuUtils::IsRole",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      v4);
    if ( IsDebuggerPresent() )
    {
      v7 = v4;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\platformskuutils.cpp",
        32,
        L"PlatformSkuUtils::IsRole",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v7);
    }
    else
    {
      LODWORD(v6) = v4;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\platformskuutils.cpp",
        32,
        L"PlatformSkuUtils::IsRole",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v6);
    }
  }
  else
  {
    v4 = 0;
    *(_DWORD *)this = v8 != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x14000a0c8  mov     r11, rsp
0x14000a0cb  mov     [r11+8], rbx
0x14000a0cf  mov     [r11+20h], rdi
0x14000a0d3  push    r12
0x14000a0d5  push    r14
0x14000a0d7  push    r15
0x14000a0d9  sub     rsp, 40h
0x14000a0dd  lea     rax, [r11+18h]
0x14000a0e1  mov     [rsp+58h+arg_8], 0
0x14000a0e9  mov     [r11-28h], rax
0x14000a0ed  lea     r8, aRoleinstalled; "RoleInstalled"
0x14000a0f4  lea     rax, [r11+10h]
0x14000a0f8  mov     [rsp+58h+arg_10], 4
0x14000a100  mov     rdi, rcx
0x14000a103  mov     [r11-30h], rax
0x14000a107  mov     r9d, 10h; dwFlags
0x14000a10d  mov     qword ptr [r11-38h], 0
0x14000a115  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14000a11c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000a123  call    cs:__imp_RegGetValueW
0x14000a129  mov     ebx, eax
0x14000a12b  test    eax, 0FFFFFFFDh
0x14000a130  jz      loc_14000A1DB
0x14000a136  test    eax, eax
0x14000a138  jle     short loc_14000A143
0x14000a13a  movzx   ebx, ax
0x14000a13d  or      ebx, 80070000h
0x14000a143  lea     r12, aCbraex; "CBRAEx"
0x14000a14a  mov     [rsp+58h+var_30], ebx; int
0x14000a14e  lea     r14, aPlatformskuuti; "PlatformSkuUtils::IsRole"
0x14000a155  mov     edi, 20h ; ' '
0x14000a15a  lea     r15, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14000a161  mov     r9, r12; unsigned __int16 *
0x14000a164  mov     r8, r14; unsigned __int16 *
0x14000a167  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x14000a16c  mov     edx, edi; unsigned int
0x14000a16e  lea     rcx, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a175  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a17a  call    cs:__imp_IsDebuggerPresent
0x14000a180  test    eax, eax
0x14000a182  jz      short loc_14000A1B2
0x14000a184  mov     [rsp+58h+var_20], ebx
0x14000a188  lea     r8, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a18f  mov     [rsp+58h+var_28], r15
0x14000a194  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a19b  mov     qword ptr [rsp+58h+var_30], r12
0x14000a1a0  lea     ecx, [rdi-1Eh]; unsigned __int8
0x14000a1a3  mov     r9d, edi
0x14000a1a6  mov     [rsp+58h+var_38], r14
0x14000a1ab  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a1b0  jmp     short loc_14000A1E8
0x14000a1b2  mov     dword ptr [rsp+58h+var_28], ebx
0x14000a1b6  lea     rdx, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a1bd  mov     qword ptr [rsp+58h+var_30], r15
0x14000a1c2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a1c9  mov     r9, r14
0x14000a1cc  mov     [rsp+58h+var_38], r12
0x14000a1d1  mov     r8d, edi
0x14000a1d4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a1d9  jmp     short loc_14000A1E8
0x14000a1db  xor     ecx, ecx
0x14000a1dd  xor     ebx, ebx
0x14000a1df  cmp     [rsp+58h+arg_8], ecx
0x14000a1e3  setnz   cl
0x14000a1e6  mov     [rdi], ecx
0x14000a1e8  mov     rdi, [rsp+58h+arg_18]
0x14000a1ed  mov     eax, ebx
0x14000a1ef  mov     rbx, [rsp+58h+arg_0]
0x14000a1f4  add     rsp, 40h
0x14000a1f8  pop     r15
0x14000a1fa  pop     r14
0x14000a1fc  pop     r12
0x14000a1fe  retn
```

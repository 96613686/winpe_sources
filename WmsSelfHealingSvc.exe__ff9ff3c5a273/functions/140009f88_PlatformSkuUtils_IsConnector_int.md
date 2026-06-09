# PlatformSkuUtils::IsConnector(int *)

- ea: `0x140009f88`
- end: `0x14000a0bf`
- name: `?IsConnector@PlatformSkuUtils@@YAJPEAH@Z`
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
- `0x140009f88`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140009fe3`
- `ADVAPI32!RegGetValueW` at `0x140009fe3`
- `KERNEL32!IsDebuggerPresent` at `0x14000a03a`
- `KERNEL32!IsDebuggerPresent` at `0x14000a03a`

## string_xrefs

- `0x14000a02e`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x14000a048`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x14000a076`: `termsrv\wms\src\common\srcutils\platformskuutils.cpp`
- `0x140009fad`: `ConnectorInstalled`

## pseudocode

```c
__int64 __fastcall PlatformSkuUtils::IsConnector(PlatformSkuUtils *this, int *a2)
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
             L"ConnectorInstalled",
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
      0x3Au,
      L"PlatformSkuUtils::IsConnector",
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
        58,
        L"PlatformSkuUtils::IsConnector",
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
        58,
        L"PlatformSkuUtils::IsConnector",
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
0x140009f88  mov     r11, rsp
0x140009f8b  mov     [r11+8], rbx
0x140009f8f  mov     [r11+20h], rdi
0x140009f93  push    r12
0x140009f95  push    r14
0x140009f97  push    r15
0x140009f99  sub     rsp, 40h
0x140009f9d  lea     rax, [r11+18h]
0x140009fa1  mov     [rsp+58h+arg_8], 0
0x140009fa9  mov     [r11-28h], rax
0x140009fad  lea     r8, aConnectorinsta; "ConnectorInstalled"
0x140009fb4  lea     rax, [r11+10h]
0x140009fb8  mov     [rsp+58h+arg_10], 4
0x140009fc0  mov     rdi, rcx
0x140009fc3  mov     [r11-30h], rax
0x140009fc7  mov     r9d, 10h; dwFlags
0x140009fcd  mov     qword ptr [r11-38h], 0
0x140009fd5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140009fdc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140009fe3  call    cs:__imp_RegGetValueW
0x140009fe9  mov     ebx, eax
0x140009feb  test    eax, 0FFFFFFFDh
0x140009ff0  jz      loc_14000A09B
0x140009ff6  test    eax, eax
0x140009ff8  jle     short loc_14000A003
0x140009ffa  movzx   ebx, ax
0x140009ffd  or      ebx, 80070000h
0x14000a003  lea     r12, aCbraex; "CBRAEx"
0x14000a00a  mov     [rsp+58h+var_30], ebx; int
0x14000a00e  lea     r14, aPlatformskuuti_0; "PlatformSkuUtils::IsConnector"
0x14000a015  mov     edi, 3Ah ; ':'
0x14000a01a  lea     r15, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14000a021  mov     r9, r12; unsigned __int16 *
0x14000a024  mov     r8, r14; unsigned __int16 *
0x14000a027  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x14000a02c  mov     edx, edi; unsigned int
0x14000a02e  lea     rcx, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a035  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a03a  call    cs:__imp_IsDebuggerPresent
0x14000a040  test    eax, eax
0x14000a042  jz      short loc_14000A072
0x14000a044  mov     [rsp+58h+var_20], ebx
0x14000a048  lea     r8, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a04f  mov     [rsp+58h+var_28], r15
0x14000a054  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000a05b  mov     qword ptr [rsp+58h+var_30], r12
0x14000a060  lea     ecx, [rdi-38h]; unsigned __int8
0x14000a063  mov     r9d, edi
0x14000a066  mov     [rsp+58h+var_38], r14
0x14000a06b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000a070  jmp     short loc_14000A0A8
0x14000a072  mov     dword ptr [rsp+58h+var_28], ebx
0x14000a076  lea     rdx, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x14000a07d  mov     qword ptr [rsp+58h+var_30], r15
0x14000a082  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000a089  mov     r9, r14
0x14000a08c  mov     [rsp+58h+var_38], r12
0x14000a091  mov     r8d, edi
0x14000a094  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000a099  jmp     short loc_14000A0A8
0x14000a09b  xor     ecx, ecx
0x14000a09d  xor     ebx, ebx
0x14000a09f  cmp     [rsp+58h+arg_8], ecx
0x14000a0a3  setnz   cl
0x14000a0a6  mov     [rdi], ecx
0x14000a0a8  mov     rdi, [rsp+58h+arg_18]
0x14000a0ad  mov     eax, ebx
0x14000a0af  mov     rbx, [rsp+58h+arg_0]
0x14000a0b4  add     rsp, 40h
0x14000a0b8  pop     r15
0x14000a0ba  pop     r14
0x14000a0bc  pop     r12
0x14000a0be  retn
```

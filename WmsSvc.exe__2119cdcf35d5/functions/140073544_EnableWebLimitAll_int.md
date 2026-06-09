# EnableWebLimitAll(int)

- ea: `0x140073544`
- end: `0x14007370e`
- name: `?EnableWebLimitAll@@YAJH@Z`
- size: `458`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019100`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140073544`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400736f5`
- `ADVAPI32!RegCloseKey` at `0x1400736f5`
- `ADVAPI32!RegCreateKeyExW` at `0x14007359b`
- `ADVAPI32!RegCreateKeyExW` at `0x14007359b`
- `ADVAPI32!RegSetValueExW` at `0x14007365a`
- `ADVAPI32!RegSetValueExW` at `0x14007365a`
- `KERNEL32!IsDebuggerPresent` at `0x1400735eb`
- `KERNEL32!IsDebuggerPresent` at `0x1400736ac`
- `KERNEL32!IsDebuggerPresent` at `0x1400735eb`
- `KERNEL32!IsDebuggerPresent` at `0x1400736ac`

## string_xrefs

- `0x1400735df`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`
- `0x1400735ff`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`
- `0x1400736a0`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`
- `0x1400736cb`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`

## pseudocode

```c
__int64 __fastcall EnableWebLimitAll(int a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // r8
  LSTATUS v5; // eax
  __int64 v7; // [rsp+30h] [rbp-38h]
  __int64 v8; // [rsp+38h] [rbp-30h]
  int Data; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Multipoint Server\\Orchestration\\WebLimiting\\Global",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
      0xF3u,
      L"EnableWebLimitAll",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 243;
LABEL_6:
      LODWORD(v8) = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
        v3,
        L"EnableWebLimitAll",
        L"CBRAEx",
        L"err == 0L",
        v8);
      goto LABEL_16;
    }
    v4 = 243;
  }
  else
  {
    v2 = 0;
    v5 = RegSetValueExW(hKey, L"IsLimited", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
      0xF7u,
      L"EnableWebLimitAll",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 247;
      goto LABEL_6;
    }
    v4 = 247;
  }
  LODWORD(v7) = v2;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
    v4,
    L"EnableWebLimitAll",
    L"CBRAEx",
    L"err == 0L",
    v7);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140073544  mov     r11, rsp
0x140073547  mov     [r11+18h], rbx
0x14007354b  mov     [rsp+Data], ecx
0x14007354f  push    rbp
0x140073550  push    rsi
0x140073551  push    r14
0x140073553  sub     rsp, 50h
0x140073557  mov     qword ptr [r11-28h], 0
0x14007355f  lea     rax, [r11+10h]
0x140073563  mov     [r11-30h], rax
0x140073567  lea     rdx, aSoftwareMicros_38; "Software\\Microsoft\\Windows Multipoint"...
0x14007356e  mov     qword ptr [r11-38h], 0
0x140073576  xor     r9d, r9d; lpClass
0x140073579  mov     [rsp+68h+samDesired], 20006h; samDesired
0x140073581  xor     r8d, r8d; Reserved
0x140073584  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007358b  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140073593  mov     qword ptr [r11+10h], 0
0x14007359b  call    cs:__imp_RegCreateKeyExW
0x1400735a1  mov     ebx, eax
0x1400735a3  test    eax, eax
0x1400735a5  jz      loc_140073636
0x1400735ab  jle     short loc_1400735B6
0x1400735ad  movzx   ebx, ax
0x1400735b0  or      ebx, 80070000h
0x1400735b6  lea     r14, aCbraex; "CBRAEx"
0x1400735bd  mov     [rsp+68h+samDesired], ebx; int
0x1400735c1  lea     rsi, aEnableweblimit_1; "EnableWebLimitAll"
0x1400735c8  mov     r9, r14; unsigned __int16 *
0x1400735cb  lea     rbp, aErr0l; "err == 0L"
0x1400735d2  mov     r8, rsi; unsigned __int16 *
0x1400735d5  mov     edx, 0F3h; unsigned int
0x1400735da  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x1400735df  lea     rcx, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x1400735e6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400735eb  call    cs:__imp_IsDebuggerPresent
0x1400735f1  test    eax, eax
0x1400735f3  jz      short loc_14007362B
0x1400735f5  mov     r9d, 0F3h
0x1400735fb  mov     dword ptr [rsp+68h+var_30], ebx
0x1400735ff  lea     r8, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x140073606  mov     [rsp+68h+var_38], rbp
0x14007360b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140073612  mov     qword ptr [rsp+68h+samDesired], r14
0x140073617  mov     ecx, 2; unsigned __int8
0x14007361c  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140073621  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140073626  jmp     loc_1400736EB
0x14007362b  mov     r8d, 0F3h
0x140073631  jmp     loc_1400736C7
0x140073636  mov     rcx, [rsp+68h+hKey]; hKey
0x14007363b  lea     rax, [rsp+68h+Data]
0x140073640  xor     ebx, ebx
0x140073642  lea     rdx, aIslimited_0; "IsLimited"
0x140073649  xor     r8d, r8d; Reserved
0x14007364c  lea     r9d, [rbx+4]; dwType
0x140073650  mov     [rsp+68h+samDesired], r9d; cbData
0x140073655  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x14007365a  call    cs:__imp_RegSetValueExW
0x140073660  test    eax, eax
0x140073662  jz      loc_1400736EB
0x140073668  jg      short loc_14007366E
0x14007366a  mov     ebx, eax
0x14007366c  jmp     short loc_140073677
0x14007366e  movzx   ebx, ax
0x140073671  or      ebx, 80070000h
0x140073677  lea     r14, aCbraex; "CBRAEx"
0x14007367e  mov     [rsp+68h+samDesired], ebx; int
0x140073682  lea     rsi, aEnableweblimit_1; "EnableWebLimitAll"
0x140073689  mov     r9, r14; unsigned __int16 *
0x14007368c  lea     rbp, aErr0l; "err == 0L"
0x140073693  mov     r8, rsi; unsigned __int16 *
0x140073696  mov     edx, 0F7h; unsigned int
0x14007369b  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x1400736a0  lea     rcx, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x1400736a7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400736ac  call    cs:__imp_IsDebuggerPresent
0x1400736b2  test    eax, eax
0x1400736b4  jz      short loc_1400736C1
0x1400736b6  mov     r9d, 0F7h
0x1400736bc  jmp     loc_1400735FB
0x1400736c1  mov     r8d, 0F7h
0x1400736c7  mov     dword ptr [rsp+68h+var_38], ebx
0x1400736cb  lea     rdx, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x1400736d2  mov     qword ptr [rsp+68h+samDesired], rbp
0x1400736d7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400736de  mov     r9, rsi
0x1400736e1  mov     qword ptr [rsp+68h+dwOptions], r14
0x1400736e6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400736eb  mov     rcx, [rsp+68h+hKey]; hKey
0x1400736f0  test    rcx, rcx
0x1400736f3  jz      short loc_1400736FB
0x1400736f5  call    cs:__imp_RegCloseKey
0x1400736fb  mov     eax, ebx
0x1400736fd  mov     rbx, [rsp+68h+arg_10]
0x140073705  add     rsp, 50h
0x140073709  pop     r14
0x14007370b  pop     rsi
0x14007370c  pop     rbp
0x14007370d  retn
```

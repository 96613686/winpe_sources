# CWmsWebService::s_SetRegValueBool(HKEY__ *,ushort const *,ushort const *,int)

- ea: `0x140053434`
- end: `0x14005360b`
- name: `?s_SetRegValueBool@CWmsWebService@@CAJPEAUHKEY__@@PEBG1H@Z`
- size: `471`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14004e580`
- `0x1400518d0`
- `0x140051af0`
- `0x140051e70`
- `0x140051ee0`

## callees

- `0x140053434`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400535ee`
- `ADVAPI32!RegCloseKey` at `0x1400535ee`
- `ADVAPI32!RegCreateKeyExW` at `0x140053497`
- `ADVAPI32!RegCreateKeyExW` at `0x140053497`
- `ADVAPI32!RegSetValueExW` at `0x140053554`
- `ADVAPI32!RegSetValueExW` at `0x140053554`
- `KERNEL32!IsDebuggerPresent` at `0x1400534ea`
- `KERNEL32!IsDebuggerPresent` at `0x1400535a9`
- `KERNEL32!IsDebuggerPresent` at `0x1400534ea`
- `KERNEL32!IsDebuggerPresent` at `0x1400535a9`

## string_xrefs

- `0x1400534c7`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140053586`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x1400534bd`: `CWmsWebService::s_SetRegValueBool`
- `0x14005357c`: `CWmsWebService::s_SetRegValueBool`

## pseudocode

```c
__int64 __fastcall CWmsWebService::s_SetRegValueBool(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  __int64 v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+38h] [rbp-30h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  BOOL Data; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  Data = a4 != 0;
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 2u, 0, &hKey, 0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x8F1u,
      L"CWmsWebService::s_SetRegValueBool",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v7 = 2289;
LABEL_6:
      LODWORD(v12) = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        v7,
        L"CWmsWebService::s_SetRegValueBool",
        L"CBRAEx",
        L"lr == 0L",
        v12);
      goto LABEL_16;
    }
    v8 = 2289;
  }
  else
  {
    v6 = 0;
    v9 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v9 )
      goto LABEL_16;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    else
      v6 = v9;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x8F4u,
      L"CWmsWebService::s_SetRegValueBool",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v7 = 2292;
      goto LABEL_6;
    }
    v8 = 2292;
  }
  LODWORD(v11) = v6;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
    v8,
    L"CWmsWebService::s_SetRegValueBool",
    L"CBRAEx",
    L"lr == 0L",
    v11);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x140053434  mov     r11, rsp
0x140053437  mov     [r11+10h], rbx
0x14005343b  mov     [r11+18h], rbp
0x14005343f  mov     [r11+8], rcx
0x140053443  push    rsi
0x140053444  push    rdi
0x140053445  push    r14
0x140053447  sub     rsp, 50h
0x14005344b  xor     eax, eax
0x14005344d  mov     qword ptr [r11-28h], 0
0x140053455  test    r9d, r9d
0x140053458  mov     qword ptr [r11+8], 0
0x140053460  mov     rdi, r8
0x140053463  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005346a  setnz   al
0x14005346d  xor     r9d, r9d; lpClass
0x140053470  mov     [r11+20h], eax
0x140053474  xor     r8d, r8d; Reserved
0x140053477  lea     rax, [r11+8]
0x14005347b  mov     [r11-30h], rax
0x14005347f  mov     qword ptr [r11-38h], 0
0x140053487  mov     [rsp+68h+samDesired], 2; samDesired
0x14005348f  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140053497  call    cs:__imp_RegCreateKeyExW
0x14005349d  mov     ebx, eax
0x14005349f  test    eax, eax
0x1400534a1  jz      loc_140053531
0x1400534a7  jle     short loc_1400534B2
0x1400534a9  movzx   ebx, ax
0x1400534ac  or      ebx, 80070000h
0x1400534b2  lea     r14, aCbraex; "CBRAEx"
0x1400534b9  mov     [rsp+68h+samDesired], ebx; int
0x1400534bd  lea     rsi, aCwmswebservice_95; "CWmsWebService::s_SetRegValueBool"
0x1400534c4  mov     r9, r14; unsigned __int16 *
0x1400534c7  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400534ce  mov     r8, rsi; unsigned __int16 *
0x1400534d1  lea     rbp, aLr0l; "lr == 0L"
0x1400534d8  mov     rcx, rdi; unsigned __int16 *
0x1400534db  mov     edx, 8F1h; unsigned int
0x1400534e0  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x1400534e5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400534ea  call    cs:__imp_IsDebuggerPresent
0x1400534f0  test    eax, eax
0x1400534f2  jz      short loc_140053526
0x1400534f4  mov     r9d, 8F1h
0x1400534fa  mov     dword ptr [rsp+68h+var_30], ebx
0x1400534fe  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140053505  mov     [rsp+68h+var_38], rbp
0x14005350a  mov     r8, rdi
0x14005350d  mov     qword ptr [rsp+68h+samDesired], r14
0x140053512  mov     ecx, 2; unsigned __int8
0x140053517  mov     qword ptr [rsp+68h+dwOptions], rsi
0x14005351c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140053521  jmp     loc_1400535E4
0x140053526  mov     r8d, 8F1h
0x14005352c  jmp     loc_1400535C4
0x140053531  mov     rcx, [rsp+68h+hKey]; hKey
0x140053536  lea     rax, [rsp+68h+Data]
0x14005353e  xor     ebx, ebx
0x140053540  xor     r8d, r8d; Reserved
0x140053543  mov     rdx, rdi; lpValueName
0x140053546  lea     r9d, [rbx+4]; dwType
0x14005354a  mov     [rsp+68h+samDesired], r9d; cbData
0x14005354f  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140053554  call    cs:__imp_RegSetValueExW
0x14005355a  test    eax, eax
0x14005355c  jz      loc_1400535E4
0x140053562  jg      short loc_140053568
0x140053564  mov     ebx, eax
0x140053566  jmp     short loc_140053571
0x140053568  movzx   ebx, ax
0x14005356b  or      ebx, 80070000h
0x140053571  lea     r14, aCbraex; "CBRAEx"
0x140053578  mov     [rsp+68h+samDesired], ebx; int
0x14005357c  lea     rsi, aCwmswebservice_95; "CWmsWebService::s_SetRegValueBool"
0x140053583  mov     r9, r14; unsigned __int16 *
0x140053586  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005358d  mov     r8, rsi; unsigned __int16 *
0x140053590  lea     rbp, aLr0l; "lr == 0L"
0x140053597  mov     rcx, rdi; unsigned __int16 *
0x14005359a  mov     edx, 8F4h; unsigned int
0x14005359f  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x1400535a4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400535a9  call    cs:__imp_IsDebuggerPresent
0x1400535af  test    eax, eax
0x1400535b1  jz      short loc_1400535BE
0x1400535b3  mov     r9d, 8F4h
0x1400535b9  jmp     loc_1400534FA
0x1400535be  mov     r8d, 8F4h
0x1400535c4  mov     dword ptr [rsp+68h+var_38], ebx
0x1400535c8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400535cf  mov     qword ptr [rsp+68h+samDesired], rbp
0x1400535d4  mov     r9, rsi
0x1400535d7  mov     rdx, rdi
0x1400535da  mov     qword ptr [rsp+68h+dwOptions], r14
0x1400535df  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400535e4  mov     rcx, [rsp+68h+hKey]; hKey
0x1400535e9  test    rcx, rcx
0x1400535ec  jz      short loc_1400535F4
0x1400535ee  call    cs:__imp_RegCloseKey
0x1400535f4  lea     r11, [rsp+68h+var_18]
0x1400535f9  mov     eax, ebx
0x1400535fb  mov     rbx, [r11+28h]
0x1400535ff  mov     rbp, [r11+30h]
0x140053603  mov     rsp, r11
0x140053606  pop     r14
0x140053608  pop     rdi
0x140053609  pop     rsi
0x14005360a  retn
```

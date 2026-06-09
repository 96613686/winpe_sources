# SetWebLimitAllSetting(int,ushort *,ushort *)

- ea: `0x140073714`
- end: `0x140073989`
- name: `?SetWebLimitAllSetting@@YAJHPEAG0@Z`
- size: `629`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017fc0`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140073714`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140073965`
- `ADVAPI32!RegCloseKey` at `0x140073965`
- `ADVAPI32!RegCreateKeyExW` at `0x1400737c3`
- `ADVAPI32!RegCreateKeyExW` at `0x1400737c3`
- `ADVAPI32!RegSetValueExW` at `0x140073827`
- `ADVAPI32!RegSetValueExW` at `0x140073827`
- `KERNEL32!IsDebuggerPresent` at `0x140073886`
- `KERNEL32!IsDebuggerPresent` at `0x140073919`
- `KERNEL32!IsDebuggerPresent` at `0x140073886`
- `KERNEL32!IsDebuggerPresent` at `0x140073919`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140073802`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140073802`

## string_xrefs

- `0x140073862`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`
- `0x1400738f8`: `termsrv\wms\src\common\srcutils\weblimitutil.cpp`

## pseudocode

```c
__int64 __fastcall SetWebLimitAllSetting(int a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r13d
  __int64 v6; // rdi
  UINT v7; // eax
  LSTATUS v8; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+38h] [rbp-39h]
  PHKEY phkResult; // [rsp+40h] [rbp-31h]
  LPCWSTR lpValueName; // [rsp+58h] [rbp-19h]
  DWORD dwType; // [rsp+60h] [rbp-11h]
  BSTR bstr[2]; // [rsp+68h] [rbp-9h]
  int v15; // [rsp+78h] [rbp+7h]
  unsigned __int16 *v16; // [rsp+80h] [rbp+Fh]
  const wchar_t *v17; // [rsp+88h] [rbp+17h]
  int v18; // [rsp+90h] [rbp+1Fh]
  int *v19; // [rsp+98h] [rbp+27h]
  int v20; // [rsp+D8h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp+6Fh] BYREF

  v20 = a1;
  lpValueName = L"AllowList";
  bstr[0] = a2;
  bstr[1] = L"BlockList";
  v16 = a3;
  v17 = L"IsAllowList";
  hKey = 0;
  v19 = &v20;
  dwType = 1;
  v15 = 1;
  v18 = 4;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Multipoint Server\\Orchestration\\WebLimiting\\Global",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = 195;
  }
  else
  {
    v6 = 0;
    while ( 1 )
    {
      if ( LODWORD(bstr[3 * v6]) == 1 )
      {
        v7 = SysStringByteLen(bstr[3 * v6]);
      }
      else
      {
        if ( LODWORD(bstr[3 * v6]) != 4 )
        {
          v4 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
            0xD2u,
            L"SetWebLimitAllSetting",
            L"CBRA",
            L"0",
            -2147467259);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = -2147467259;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
              210,
              L"SetWebLimitAllSetting",
              L"CBRA",
              L"0",
              phkResult);
          }
          else
          {
            LODWORD(lpSecurityAttributes) = -2147467259;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
              210,
              L"SetWebLimitAllSetting",
              L"CBRA",
              L"0",
              lpSecurityAttributes);
          }
          goto LABEL_23;
        }
        v7 = 4;
      }
      v8 = RegSetValueExW(hKey, (&lpValueName)[3 * v6], 0, (DWORD)bstr[3 * v6], (const BYTE *)bstr[3 * v6], v7);
      v4 = v8;
      if ( v8 )
        break;
      if ( (unsigned __int64)++v6 >= 3 )
        goto LABEL_23;
    }
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v5 = 215;
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
    v5,
    L"SetWebLimitAllSetting",
    L"CBRAEx",
    L"err == 0L",
    v4);
  if ( IsDebuggerPresent() )
  {
    LODWORD(phkResult) = v4;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
      v5,
      L"SetWebLimitAllSetting",
      L"CBRAEx",
      L"err == 0L",
      phkResult);
  }
  else
  {
    LODWORD(lpSecurityAttributes) = v4;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\weblimitutil.cpp",
      v5,
      L"SetWebLimitAllSetting",
      L"CBRAEx",
      L"err == 0L",
      lpSecurityAttributes);
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140073714  mov     rax, rsp
0x140073717  mov     [rax+18h], rbx
0x14007371b  mov     [rax+20h], rsi
0x14007371f  mov     [rax+8], ecx
0x140073722  push    rbp
0x140073723  push    rdi
0x140073724  push    r13
0x140073726  push    r14
0x140073728  push    r15
0x14007372a  lea     rbp, [rax-5Fh]
0x14007372e  sub     rsp, 0A0h
0x140073735  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x14007373e  lea     rax, aAllowlist_0; "AllowList"
0x140073745  mov     [rbp+57h+lpValueName], rax
0x140073749  mov     esi, 4
0x14007374e  lea     rax, aBlocklist_0; "BlockList"
0x140073755  mov     [rbp+57h+bstr], rdx
0x140073759  mov     [rbp+57h+var_58], rax
0x14007375d  lea     rdx, aSoftwareMicros_38; "Software\\Microsoft\\Windows Multipoint"...
0x140073764  lea     rax, aIsallowlist_0; "IsAllowList"
0x14007376b  mov     [rbp+57h+var_48], r8
0x14007376f  mov     [rbp+57h+var_40], rax
0x140073773  xor     r9d, r9d; lpClass
0x140073776  lea     rax, [rbp+57h+arg_0]
0x14007377a  mov     [rbp+57h+hKey], 0
0x140073782  mov     [rbp+57h+var_30], rax
0x140073786  xor     r8d, r8d; Reserved
0x140073789  lea     rax, [rbp+57h+hKey]
0x14007378d  mov     [rbp+57h+dwType], 1
0x140073794  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140073799  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400737a0  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400737a9  mov     [rsp+0C0h+samDesired], 20006h; samDesired
0x1400737b1  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x1400737b9  mov     [rbp+57h+var_50], 1
0x1400737c0  mov     [rbp+57h+var_38], esi
0x1400737c3  call    cs:__imp_RegCreateKeyExW
0x1400737c9  mov     ebx, eax
0x1400737cb  test    eax, eax
0x1400737cd  jz      short loc_1400737E5
0x1400737cf  jle     short loc_1400737DA
0x1400737d1  movzx   ebx, ax
0x1400737d4  or      ebx, 80070000h
0x1400737da  mov     r13d, 0C3h
0x1400737e0  jmp     loc_1400738E3
0x1400737e5  xor     edi, edi
0x1400737e7  lea     rbx, [rdi+rdi*2]
0x1400737eb  mov     eax, [rbp+rbx*8+57h+dwType]
0x1400737ef  sub     eax, 1
0x1400737f2  jz      short loc_1400737FD
0x1400737f4  cmp     eax, 3
0x1400737f7  jnz     short loc_140073845
0x1400737f9  mov     eax, esi
0x1400737fb  jmp     short loc_140073808
0x1400737fd  mov     rcx, [rbp+rbx*8+57h+bstr]; bstr
0x140073802  call    cs:__imp_SysStringByteLen
0x140073808  mov     r9d, [rbp+rbx*8+57h+dwType]; dwType
0x14007380d  xor     r8d, r8d; Reserved
0x140073810  mov     rdx, [rbp+rbx*8+57h+lpValueName]; lpValueName
0x140073815  mov     rcx, [rbp+57h+hKey]; hKey
0x140073819  mov     [rsp+0C0h+samDesired], eax; cbData
0x14007381d  mov     rax, [rbp+rbx*8+57h+bstr]
0x140073822  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x140073827  call    cs:__imp_RegSetValueExW
0x14007382d  mov     ebx, eax
0x14007382f  test    eax, eax
0x140073831  jnz     loc_1400738D2
0x140073837  inc     rdi
0x14007383a  cmp     rdi, 3
0x14007383e  jb      short loc_1400737E7
0x140073840  jmp     loc_14007395C
0x140073845  mov     ebx, 80004005h
0x14007384a  lea     r13, aCbra; "CBRA"
0x140073851  lea     rsi, aSetweblimitall; "SetWebLimitAllSetting"
0x140073858  mov     [rsp+0C0h+samDesired], ebx; int
0x14007385c  mov     r14d, 0D2h
0x140073862  lea     rdi, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x140073869  lea     r15, a0; "0"
0x140073870  mov     r9, r13; unsigned __int16 *
0x140073873  mov     r8, rsi; unsigned __int16 *
0x140073876  mov     qword ptr [rsp+0C0h+dwOptions], r15; unsigned __int16 *
0x14007387b  mov     edx, r14d; unsigned int
0x14007387e  mov     rcx, rdi; unsigned __int16 *
0x140073881  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140073886  call    cs:__imp_IsDebuggerPresent
0x14007388c  test    eax, eax
0x14007388e  jz      short loc_1400738BF
0x140073890  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x140073894  mov     r9d, r14d
0x140073897  mov     [rsp+0C0h+lpSecurityAttributes], r15
0x14007389c  mov     qword ptr [rsp+0C0h+samDesired], r13
0x1400738a1  mov     r8, rdi
0x1400738a4  mov     qword ptr [rsp+0C0h+dwOptions], rsi
0x1400738a9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400738b0  mov     ecx, 2; unsigned __int8
0x1400738b5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400738ba  jmp     loc_14007395C
0x1400738bf  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], ebx
0x1400738c3  mov     r8d, r14d
0x1400738c6  mov     qword ptr [rsp+0C0h+samDesired], r15
0x1400738cb  mov     qword ptr [rsp+0C0h+dwOptions], r13
0x1400738d0  jmp     short loc_14007394A
0x1400738d2  jle     short loc_1400738DD
0x1400738d4  movzx   ebx, ax
0x1400738d7  or      ebx, 80070000h
0x1400738dd  mov     r13d, 0D7h
0x1400738e3  lea     r15, aCbraex; "CBRAEx"
0x1400738ea  mov     [rsp+0C0h+samDesired], ebx; int
0x1400738ee  lea     rsi, aSetweblimitall; "SetWebLimitAllSetting"
0x1400738f5  mov     r9, r15; unsigned __int16 *
0x1400738f8  lea     rdi, aTermsrvWmsSrcC_10; "termsrv\\wms\\src\\common\\srcutils\\we"...
0x1400738ff  mov     r8, rsi; unsigned __int16 *
0x140073902  lea     r14, aErr0l; "err == 0L"
0x140073909  mov     rcx, rdi; unsigned __int16 *
0x14007390c  mov     edx, r13d; unsigned int
0x14007390f  mov     qword ptr [rsp+0C0h+dwOptions], r14; unsigned __int16 *
0x140073914  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140073919  call    cs:__imp_IsDebuggerPresent
0x14007391f  test    eax, eax
0x140073921  jz      short loc_140073939
0x140073923  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x140073927  mov     r9d, r13d
0x14007392a  mov     [rsp+0C0h+lpSecurityAttributes], r14
0x14007392f  mov     qword ptr [rsp+0C0h+samDesired], r15
0x140073934  jmp     loc_1400738A1
0x140073939  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], ebx
0x14007393d  mov     r8d, r13d
0x140073940  mov     qword ptr [rsp+0C0h+samDesired], r14
0x140073945  mov     qword ptr [rsp+0C0h+dwOptions], r15
0x14007394a  mov     r9, rsi
0x14007394d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140073954  mov     rdx, rdi
0x140073957  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007395c  mov     rcx, [rbp+57h+hKey]; hKey
0x140073960  test    rcx, rcx
0x140073963  jz      short loc_14007396B
0x140073965  call    cs:__imp_RegCloseKey
0x14007396b  lea     r11, [rsp+0C0h+var_20]
0x140073973  mov     eax, ebx
0x140073975  mov     rbx, [r11+40h]
0x140073979  mov     rsi, [r11+48h]
0x14007397d  mov     rsp, r11
0x140073980  pop     r15
0x140073982  pop     r14
0x140073984  pop     r13
0x140073986  pop     rdi
0x140073987  pop     rbp
0x140073988  retn
```

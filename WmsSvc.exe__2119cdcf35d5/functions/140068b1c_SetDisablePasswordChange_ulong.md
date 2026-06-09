# SetDisablePasswordChange(ulong)

- ea: `0x140068b1c`
- end: `0x140068ce6`
- name: `?SetDisablePasswordChange@@YAJK@Z`
- size: `458`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140009778`
- `0x14000b980`
- `0x14002f784`
- `0x14006e19c`
- `0x14006e81c`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140068b1c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140068ccd`
- `ADVAPI32!RegCloseKey` at `0x140068ccd`
- `ADVAPI32!RegCreateKeyExW` at `0x140068b73`
- `ADVAPI32!RegCreateKeyExW` at `0x140068b73`
- `ADVAPI32!RegSetValueExW` at `0x140068c32`
- `ADVAPI32!RegSetValueExW` at `0x140068c32`
- `KERNEL32!IsDebuggerPresent` at `0x140068bc3`
- `KERNEL32!IsDebuggerPresent` at `0x140068c84`
- `KERNEL32!IsDebuggerPresent` at `0x140068bc3`
- `KERNEL32!IsDebuggerPresent` at `0x140068c84`

## string_xrefs

- `0x140068bb7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068bd7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068c78`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068ca3`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068b3f`: `System\CurrentControlSet\Services\Netlogon\Parameters`

## pseudocode

```c
__int64 __fastcall SetDisablePasswordChange(int a1)
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
         L"System\\CurrentControlSet\\Services\\Netlogon\\Parameters",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x898u,
      L"SetDisablePasswordChange",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 2200;
LABEL_6:
      LODWORD(v8) = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v3,
        L"SetDisablePasswordChange",
        L"CBRAEx",
        L"err == 0L",
        v8);
      goto LABEL_16;
    }
    v4 = 2200;
  }
  else
  {
    v2 = 0;
    v5 = RegSetValueExW(hKey, L"DisablePasswordChange", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x89Bu,
      L"SetDisablePasswordChange",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 2203;
      goto LABEL_6;
    }
    v4 = 2203;
  }
  LODWORD(v7) = v2;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
    v4,
    L"SetDisablePasswordChange",
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
0x140068b1c  mov     r11, rsp
0x140068b1f  mov     [r11+18h], rbx
0x140068b23  mov     [rsp+Data], ecx
0x140068b27  push    rbp
0x140068b28  push    rsi
0x140068b29  push    r14
0x140068b2b  sub     rsp, 50h
0x140068b2f  mov     qword ptr [r11-28h], 0
0x140068b37  lea     rax, [r11+10h]
0x140068b3b  mov     [r11-30h], rax
0x140068b3f  lea     rdx, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\Ne"...
0x140068b46  mov     qword ptr [r11-38h], 0
0x140068b4e  xor     r9d, r9d; lpClass
0x140068b51  mov     [rsp+68h+samDesired], 2; samDesired
0x140068b59  xor     r8d, r8d; Reserved
0x140068b5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140068b63  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140068b6b  mov     qword ptr [r11+10h], 0
0x140068b73  call    cs:__imp_RegCreateKeyExW
0x140068b79  mov     ebx, eax
0x140068b7b  test    eax, eax
0x140068b7d  jz      loc_140068C0E
0x140068b83  jle     short loc_140068B8E
0x140068b85  movzx   ebx, ax
0x140068b88  or      ebx, 80070000h
0x140068b8e  lea     r14, aCbraex; "CBRAEx"
0x140068b95  mov     [rsp+68h+samDesired], ebx; int
0x140068b99  lea     rsi, aSetdisablepass; "SetDisablePasswordChange"
0x140068ba0  mov     r9, r14; unsigned __int16 *
0x140068ba3  lea     rbp, aErr0l; "err == 0L"
0x140068baa  mov     r8, rsi; unsigned __int16 *
0x140068bad  mov     edx, 898h; unsigned int
0x140068bb2  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140068bb7  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140068bbe  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140068bc3  call    cs:__imp_IsDebuggerPresent
0x140068bc9  test    eax, eax
0x140068bcb  jz      short loc_140068C03
0x140068bcd  mov     r9d, 898h
0x140068bd3  mov     dword ptr [rsp+68h+var_30], ebx
0x140068bd7  lea     r8, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140068bde  mov     [rsp+68h+var_38], rbp
0x140068be3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140068bea  mov     qword ptr [rsp+68h+samDesired], r14
0x140068bef  mov     ecx, 2; unsigned __int8
0x140068bf4  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140068bf9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140068bfe  jmp     loc_140068CC3
0x140068c03  mov     r8d, 898h
0x140068c09  jmp     loc_140068C9F
0x140068c0e  mov     rcx, [rsp+68h+hKey]; hKey
0x140068c13  lea     rax, [rsp+68h+Data]
0x140068c18  xor     ebx, ebx
0x140068c1a  lea     rdx, aDisablepasswor_1; "DisablePasswordChange"
0x140068c21  xor     r8d, r8d; Reserved
0x140068c24  lea     r9d, [rbx+4]; dwType
0x140068c28  mov     [rsp+68h+samDesired], r9d; cbData
0x140068c2d  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140068c32  call    cs:__imp_RegSetValueExW
0x140068c38  test    eax, eax
0x140068c3a  jz      loc_140068CC3
0x140068c40  jg      short loc_140068C46
0x140068c42  mov     ebx, eax
0x140068c44  jmp     short loc_140068C4F
0x140068c46  movzx   ebx, ax
0x140068c49  or      ebx, 80070000h
0x140068c4f  lea     r14, aCbraex; "CBRAEx"
0x140068c56  mov     [rsp+68h+samDesired], ebx; int
0x140068c5a  lea     rsi, aSetdisablepass; "SetDisablePasswordChange"
0x140068c61  mov     r9, r14; unsigned __int16 *
0x140068c64  lea     rbp, aErr0l; "err == 0L"
0x140068c6b  mov     r8, rsi; unsigned __int16 *
0x140068c6e  mov     edx, 89Bh; unsigned int
0x140068c73  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140068c78  lea     rcx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140068c7f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140068c84  call    cs:__imp_IsDebuggerPresent
0x140068c8a  test    eax, eax
0x140068c8c  jz      short loc_140068C99
0x140068c8e  mov     r9d, 89Bh
0x140068c94  jmp     loc_140068BD3
0x140068c99  mov     r8d, 89Bh
0x140068c9f  mov     dword ptr [rsp+68h+var_38], ebx
0x140068ca3  lea     rdx, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140068caa  mov     qword ptr [rsp+68h+samDesired], rbp
0x140068caf  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140068cb6  mov     r9, rsi
0x140068cb9  mov     qword ptr [rsp+68h+dwOptions], r14
0x140068cbe  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140068cc3  mov     rcx, [rsp+68h+hKey]; hKey
0x140068cc8  test    rcx, rcx
0x140068ccb  jz      short loc_140068CD3
0x140068ccd  call    cs:__imp_RegCloseKey
0x140068cd3  mov     eax, ebx
0x140068cd5  mov     rbx, [rsp+68h+arg_10]
0x140068cdd  add     rsp, 50h
0x140068ce1  pop     r14
0x140068ce3  pop     rsi
0x140068ce4  pop     rbp
0x140068ce5  retn
```

# FwRuleSerializeInterfaceTypesAndLUIDs(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,_tag_FW_INTERFACE_LUIDS *,ulong)

- ea: `0x1800151e8`
- end: `0x180015426`
- name: `?FwRuleSerializeInterfaceTypesAndLUIDs@@YAJPEAG_KPEAPEAGPEA_KPEAU_tag_FW_INTERFACE_LUIDS@@K@Z`
- size: `574`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, struct _tag_FW_INTERFACE_LUIDS *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a328`
- `0x180032ec0`

## callees

- `0x1800042c4`
- `0x18000cff0`
- `0x1800151e8`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015271`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152c6`

## string_xrefs

- `0x1800153d7`: `RemoteAccess`

## pseudocode

```c
__int64 __fastcall FwRuleSerializeInterfaceTypesAndLUIDs(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        struct _tag_FW_INTERFACE_LUIDS *a5,
        unsigned int a6)
{
  HRESULT v6; // ebx
  unsigned int v7; // edi
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp-18h] BYREF
  LPOLESTR lpsz; // [rsp+60h] [rbp-10h] BYREF

  v6 = 0;
  pszDest = a1;
  lpsz = 0;
  v7 = 0;
  v12 = a2;
  while ( 1 )
  {
    if ( v7 >= *(_DWORD *)a5 )
    {
      if ( a6 )
      {
        if ( (a6 & 1) != 0 )
        {
          v6 = StringCchPrintfExW(pszDest, v12, &pszDest, &v12, 0x800u, L"%s%s%s", L"IFType=", L"Lan", L"|");
          if ( v6 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        if ( (a6 & 2) != 0 )
        {
          v6 = StringCchPrintfExW(pszDest, v12, &pszDest, &v12, 0x800u, L"%s%s%s", L"IFType=", L"Wireless", L"|");
          if ( v6 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        if ( (a6 & 4) != 0 )
        {
          v6 = StringCchPrintfExW(pszDest, v12, &pszDest, &v12, 0x800u, L"%s%s%s", L"IFType=", L"RemoteAccess", L"|");
          if ( v6 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
      *a3 = pszDest;
      *a4 = v12;
      return (unsigned int)v6;
    }
    v6 = StringFromCLSID((const IID *const)(*((_QWORD *)a5 + 1) + 16LL * v7), &lpsz);
    if ( v6 < 0 )
      break;
    v6 = StringCchPrintfExW(pszDest, v12, &pszDest, &v12, 0x800u, L"%s%s%s", L"IF=", lpsz, L"|");
    CoTaskMemFree(lpsz);
    lpsz = 0;
    if ( v6 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ++v7;
  }
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800151e8  push    rbp
0x1800151ea  push    rbx
0x1800151eb  push    rsi
0x1800151ec  push    rdi
0x1800151ed  push    r13
0x1800151ef  push    r14
0x1800151f1  push    r15
0x1800151f3  mov     rbp, rsp
0x1800151f6  sub     rsp, 70h
0x1800151fa  mov     rax, cs:__security_cookie
0x180015201  xor     rax, rsp
0x180015204  mov     [rbp+var_8], rax
0x180015208  mov     rsi, [rbp+arg_20]
0x18001520c  lea     r13, asc_18003D4F8; "|"
0x180015213  xor     ebx, ebx
0x180015215  mov     [rbp+pszDest], rcx
0x180015219  mov     [rbp+lpsz], rbx
0x18001521d  xor     edi, edi
0x18001521f  mov     r15, r9
0x180015222  mov     [rbp+var_18], rdx
0x180015226  mov     r14, r8
0x180015229  cmp     edi, [rsi]
0x18001522b  jb      short loc_180015263
0x18001522d  mov     edi, [rbp+arg_28]
0x180015230  test    edi, edi
0x180015232  jnz     loc_180015322
0x180015238  mov     rax, [rbp+pszDest]
0x18001523c  mov     [r14], rax
0x18001523f  mov     rax, [rbp+var_18]
0x180015243  mov     [r15], rax
0x180015246  mov     eax, ebx
0x180015248  mov     rcx, [rbp+var_8]
0x18001524c  xor     rcx, rsp; StackCookie
0x18001524f  call    __security_check_cookie
0x180015254  add     rsp, 70h
0x180015258  pop     r15
0x18001525a  pop     r14
0x18001525c  pop     r13
0x18001525e  pop     rdi
0x18001525f  pop     rsi
0x180015260  pop     rbx
0x180015261  pop     rbp
0x180015262  retn
0x180015263  mov     ecx, edi
0x180015265  lea     rdx, [rbp+lpsz]; lplpsz
0x180015269  shl     rcx, 4
0x18001526d  add     rcx, [rsi+8]; rclsid
0x180015271  call    cs:__imp_StringFromCLSID
0x180015277  mov     ebx, eax
0x180015279  test    eax, eax
0x18001527b  js      short loc_1800152E4
0x18001527d  mov     rax, [rbp+lpsz]
0x180015281  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180015285  mov     rdx, [rbp+var_18]; unsigned __int64
0x180015289  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18001528d  mov     rcx, [rbp+pszDest]; pszDest
0x180015291  mov     [rsp+70h+var_30], r13
0x180015296  mov     [rsp+70h+var_38], rax
0x18001529b  lea     rax, aIf; "IF="
0x1800152a2  mov     [rsp+70h+var_40], rax
0x1800152a7  lea     rax, aSSS_2; "%s%s%s"
0x1800152ae  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800152b3  mov     [rsp+70h+var_50], 800h; unsigned int
0x1800152bb  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800152c0  mov     rcx, [rbp+lpsz]; pv
0x1800152c4  mov     ebx, eax
0x1800152c6  call    cs:__imp_CoTaskMemFree
0x1800152cc  mov     [rbp+lpsz], 0
0x1800152d4  test    ebx, ebx
0x1800152d6  jns     short loc_1800152DD
0x1800152d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800152dd  inc     edi
0x1800152df  jmp     loc_180015229
0x1800152e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152eb  lea     rax, WPP_GLOBAL_Control
0x1800152f2  cmp     rcx, rax
0x1800152f5  jz      loc_180015246
0x1800152fb  test    byte ptr [rcx+1Ch], 1
0x1800152ff  jz      loc_180015246
0x180015305  mov     rcx, [rcx+10h]
0x180015309  lea     r8, WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids
0x180015310  mov     edx, 12h
0x180015315  mov     r9d, ebx
0x180015318  call    WPP_SF_d
0x18001531d  jmp     loc_180015246
0x180015322  lea     rsi, aIftype; "IFType="
0x180015329  test    dil, 1
0x18001532d  jz      short loc_180015379
0x18001532f  mov     rdx, [rbp+var_18]; unsigned __int64
0x180015333  lea     rax, aLan; "Lan"
0x18001533a  mov     rcx, [rbp+pszDest]; pszDest
0x18001533e  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180015342  mov     [rsp+70h+var_30], r13
0x180015347  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18001534b  mov     [rsp+70h+var_38], rax
0x180015350  lea     rax, aSSS_2; "%s%s%s"
0x180015357  mov     [rsp+70h+var_40], rsi
0x18001535c  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180015361  mov     [rsp+70h+var_50], 800h; unsigned int
0x180015369  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001536e  mov     ebx, eax
0x180015370  test    eax, eax
0x180015372  jns     short loc_180015379
0x180015374  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015379  test    dil, 2
0x18001537d  jz      short loc_1800153C9
0x18001537f  mov     rdx, [rbp+var_18]; unsigned __int64
0x180015383  lea     rax, aWireless; "Wireless"
0x18001538a  mov     rcx, [rbp+pszDest]; pszDest
0x18001538e  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180015392  mov     [rsp+70h+var_30], r13
0x180015397  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18001539b  mov     [rsp+70h+var_38], rax
0x1800153a0  lea     rax, aSSS_2; "%s%s%s"
0x1800153a7  mov     [rsp+70h+var_40], rsi
0x1800153ac  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800153b1  mov     [rsp+70h+var_50], 800h; unsigned int
0x1800153b9  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800153be  mov     ebx, eax
0x1800153c0  test    eax, eax
0x1800153c2  jns     short loc_1800153C9
0x1800153c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800153c9  test    dil, 4
0x1800153cd  jz      loc_180015238
0x1800153d3  mov     rdx, [rbp+var_18]; unsigned __int64
0x1800153d7  lea     rax, aRemoteaccess; "RemoteAccess"
0x1800153de  mov     rcx, [rbp+pszDest]; pszDest
0x1800153e2  lea     r9, [rbp+var_18]; unsigned __int64 *
0x1800153e6  mov     [rsp+70h+var_30], r13
0x1800153eb  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800153ef  mov     [rsp+70h+var_38], rax
0x1800153f4  lea     rax, aSSS_2; "%s%s%s"
0x1800153fb  mov     [rsp+70h+var_40], rsi
0x180015400  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180015405  mov     [rsp+70h+var_50], 800h; unsigned int
0x18001540d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180015412  mov     ebx, eax
0x180015414  test    eax, eax
0x180015416  jns     loc_180015238
0x18001541c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015421  jmp     loc_180015238
```

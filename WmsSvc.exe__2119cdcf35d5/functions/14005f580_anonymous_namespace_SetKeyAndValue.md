# _anonymous_namespace_::SetKeyAndValue

- ea: `0x14005f580`
- end: `0x14005faf0`
- name: `_anonymous_namespace_::SetKeyAndValue`
- size: `1392`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005ee54`

## callees

- `0x14002e718`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005f580`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005fabe`
- `ADVAPI32!RegCloseKey` at `0x14005fabe`
- `ADVAPI32!RegCreateKeyExW` at `0x14005f7e8`
- `ADVAPI32!RegCreateKeyExW` at `0x14005f7e8`
- `ADVAPI32!RegSetValueExW` at `0x14005f9ca`
- `ADVAPI32!RegSetValueExW` at `0x14005f9ca`
- `KERNEL32!IsDebuggerPresent` at `0x14005f67f`
- `KERNEL32!IsDebuggerPresent` at `0x14005f721`
- `KERNEL32!IsDebuggerPresent` at `0x14005f793`
- `KERNEL32!IsDebuggerPresent` at `0x14005f839`
- `KERNEL32!IsDebuggerPresent` at `0x14005f8eb`
- `KERNEL32!IsDebuggerPresent` at `0x14005f96d`
- `KERNEL32!IsDebuggerPresent` at `0x14005fa1f`
- `KERNEL32!IsDebuggerPresent` at `0x14005fa79`
- `KERNEL32!IsDebuggerPresent` at `0x14005f67f`
- `KERNEL32!IsDebuggerPresent` at `0x14005f721`
- `KERNEL32!IsDebuggerPresent` at `0x14005f793`
- `KERNEL32!IsDebuggerPresent` at `0x14005f839`
- `KERNEL32!IsDebuggerPresent` at `0x14005f8eb`
- `KERNEL32!IsDebuggerPresent` at `0x14005f96d`
- `KERNEL32!IsDebuggerPresent` at `0x14005fa1f`
- `KERNEL32!IsDebuggerPresent` at `0x14005fa79`

## string_xrefs

- `0x14005f65c`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f6fe`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f770`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f816`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f8c8`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f94f`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005f9fc`: `termsrv\wms\src\common\ntservice\registry.cpp`
- `0x14005fa53`: `termsrv\wms\src\common\ntservice\registry.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::SetKeyAndValue(
        WCHAR *a1,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        const BYTE *a4)
{
  WCHAR *v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rax
  WCHAR *v12; // rcx
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // r15
  const unsigned __int16 *v15; // r14
  __int64 v16; // r9
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  LSTATUS v20; // eax
  _WORD *v21; // r9
  __int64 v22; // r8
  const BYTE *v23; // rax
  _WORD *v24; // rcx
  __int64 v25; // rcx
  _WORD *v26; // rax
  unsigned __int64 v27; // rax
  LSTATUS v28; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[528]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[1024]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  memset_0(v33, 0, 0x208u);
  v8 = SubKey;
  v9 = 2147483646;
  v10 = 1024;
  v11 = 2147483646;
  do
  {
    if ( !v11 )
      break;
    if ( !*a1 )
      break;
    *v8++ = *a1++;
    --v11;
    --v10;
  }
  while ( v10 );
  v12 = v8 - 1;
  v13 = v10 == 0 ? 0x8007007A : 0;
  if ( v10 )
    v12 = v8;
  *v12 = 0;
  if ( v10 )
  {
    if ( !a2 )
      goto LABEL_21;
    v18 = StringCchCatW(SubKey, 0x400u, L"\\");
    v13 = v18;
    if ( v18 < 0 )
    {
      v14 = L"CHRA";
      v15 = L"hr";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        0x2Au,
        L"`anonymous-namespace'::SetKeyAndValue",
        L"CHRA",
        L"hr",
        v18);
      if ( IsDebuggerPresent() )
      {
        v16 = 42;
        goto LABEL_10;
      }
      v17 = 42;
      goto LABEL_57;
    }
    v19 = StringCchCatW(SubKey, 0x400u, a2);
    v13 = v19;
    if ( v19 < 0 )
    {
      v14 = L"CHRA";
      v15 = L"hr";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        0x2Du,
        L"`anonymous-namespace'::SetKeyAndValue",
        L"CHRA",
        L"hr",
        v19);
      if ( IsDebuggerPresent() )
      {
        v16 = 45;
        goto LABEL_10;
      }
      v17 = 45;
    }
    else
    {
LABEL_21:
      v20 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
      if ( v20 )
      {
        if ( v20 > 0 )
          v13 = (unsigned __int16)v20 | 0x80070000;
        else
          v13 = v20;
        v14 = L"CBRAEx";
        v15 = L"lResult == 0L";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
          0x39u,
          L"`anonymous-namespace'::SetKeyAndValue",
          L"CBRAEx",
          L"lResult == 0L",
          v13);
        if ( IsDebuggerPresent() )
        {
          v16 = 57;
          goto LABEL_10;
        }
        v17 = 57;
      }
      else
      {
        if ( !a4 )
          goto LABEL_58;
        v21 = v33;
        v22 = 260;
        v23 = a4;
        do
        {
          if ( !v9 )
            break;
          if ( !*(_WORD *)v23 )
            break;
          *v21 = *(_WORD *)v23;
          v23 += 2;
          ++v21;
          --v9;
          --v22;
        }
        while ( v22 );
        v24 = v21 - 1;
        v13 = v22 == 0 ? 0x8007007A : 0;
        if ( v22 )
          v24 = v21;
        *v24 = 0;
        if ( v22 )
        {
          v25 = 260;
          v26 = v33;
          do
          {
            if ( !*v26 )
              break;
            ++v26;
            --v25;
          }
          while ( v25 );
          v13 = v25 == 0 ? 0x80070057 : 0;
          if ( v25 )
          {
            v27 = ((2 * (260 - v25)) & -(__int64)(v25 != 0)) + 2;
            if ( v27 > 0xFFFFFFFF )
            {
              v13 = -2147024362;
              v14 = L"CHRA";
              v15 = L"hr";
              LOGASSERTHR(
                L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                0x4Bu,
                L"`anonymous-namespace'::SetKeyAndValue",
                L"CHRA",
                L"hr",
                -2147024362);
              if ( IsDebuggerPresent() )
              {
                v16 = 75;
                goto LABEL_10;
              }
              v17 = 75;
            }
            else
            {
              v13 = 0;
              v28 = RegSetValueExW(hKey, a3, 0, 1u, a4, v27);
              if ( !v28 )
                goto LABEL_58;
              if ( v28 > 0 )
                v13 = (unsigned __int16)v28 | 0x80070000;
              else
                v13 = v28;
              v14 = L"CBRAEx";
              v15 = L"lResult == 0L";
              LOGASSERTHR(
                L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
                0x4Eu,
                L"`anonymous-namespace'::SetKeyAndValue",
                L"CBRAEx",
                L"lResult == 0L",
                v13);
              if ( IsDebuggerPresent() )
              {
                v16 = 78;
                goto LABEL_10;
              }
              v17 = 78;
            }
          }
          else
          {
            v14 = L"CHRA";
            v15 = L"hr";
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
              0x42u,
              L"`anonymous-namespace'::SetKeyAndValue",
              L"CHRA",
              L"hr",
              -2147024809);
            if ( IsDebuggerPresent() )
            {
              v16 = 66;
              goto LABEL_10;
            }
            v17 = 66;
          }
        }
        else
        {
          v14 = L"CHRA";
          v15 = L"hr";
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
            0x3Fu,
            L"`anonymous-namespace'::SetKeyAndValue",
            L"CHRA",
            L"hr",
            -2147024774);
          if ( IsDebuggerPresent() )
          {
            v16 = 63;
            goto LABEL_10;
          }
          v17 = 63;
        }
      }
    }
  }
  else
  {
    v14 = L"CHRA";
    v15 = L"hr";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
      0x23u,
      L"`anonymous-namespace'::SetKeyAndValue",
      L"CHRA",
      L"hr",
      -2147024774);
    if ( IsDebuggerPresent() )
    {
      v16 = 35;
LABEL_10:
      LODWORD(phkResult) = v13;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
        v16,
        L"`anonymous-namespace'::SetKeyAndValue",
        v14,
        v15,
        phkResult);
      goto LABEL_58;
    }
    v17 = 35;
  }
LABEL_57:
  LODWORD(lpSecurityAttributes) = v13;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\common\\ntservice\\registry.cpp",
    v17,
    L"`anonymous-namespace'::SetKeyAndValue",
    v14,
    v15,
    lpSecurityAttributes);
LABEL_58:
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x14005f580  mov     [rsp-8+arg_0], rbx
0x14005f585  push    rbp
0x14005f586  push    rsi
0x14005f587  push    rdi
0x14005f588  push    r12
0x14005f58a  push    r13
0x14005f58c  push    r14
0x14005f58e  push    r15
0x14005f590  lea     rbp, [rsp-980h]
0x14005f598  sub     rsp, 0A80h
0x14005f59f  mov     rax, cs:__security_cookie
0x14005f5a6  xor     rax, rsp
0x14005f5a9  mov     [rbp+9B0h+var_40], rax
0x14005f5b0  mov     r15, r8
0x14005f5b3  mov     r14, rdx
0x14005f5b6  mov     rbx, rcx
0x14005f5b9  xor     r12d, r12d
0x14005f5bc  xor     edx, edx; Val
0x14005f5be  mov     [rsp+0AB0h+hKey], r12
0x14005f5c3  mov     r8d, 800h; Size
0x14005f5c9  lea     rcx, [rbp+9B0h+SubKey]; void *
0x14005f5d0  mov     rsi, r9
0x14005f5d3  call    memset_0
0x14005f5d8  xor     edx, edx; Val
0x14005f5da  lea     rcx, [rsp+0AB0h+var_A50]; void *
0x14005f5df  mov     r8d, 208h; Size
0x14005f5e5  call    memset_0
0x14005f5ea  mov     r9d, 400h
0x14005f5f0  lea     r8, [rbp+9B0h+SubKey]
0x14005f5f7  mov     edi, 7FFFFFFEh
0x14005f5fc  lea     r13d, [r12+2]
0x14005f601  mov     edx, r9d
0x14005f604  mov     eax, edi
0x14005f606  test    rax, rax
0x14005f609  jz      short loc_14005F626
0x14005f60b  movzx   ecx, word ptr [rbx]
0x14005f60e  test    cx, cx
0x14005f611  jz      short loc_14005F626
0x14005f613  mov     [r8], cx
0x14005f617  add     rbx, r13
0x14005f61a  add     r8, r13
0x14005f61d  dec     rax
0x14005f620  sub     rdx, 1
0x14005f624  jnz     short loc_14005F606
0x14005f626  mov     rax, rdx
0x14005f629  lea     rcx, [r8-2]
0x14005f62d  neg     rax
0x14005f630  sbb     ebx, ebx
0x14005f632  not     ebx
0x14005f634  and     ebx, 8007007Ah
0x14005f63a  test    rdx, rdx
0x14005f63d  cmovnz  rcx, r8
0x14005f641  mov     [rcx], r12w
0x14005f645  jnz     short loc_14005F6C4
0x14005f647  lea     r15, aChra; "CHRA"
0x14005f64e  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005f652  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f659  mov     r9, r15; unsigned __int16 *
0x14005f65c  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f663  mov     r8, rsi; unsigned __int16 *
0x14005f666  lea     r14, aHr; "hr"
0x14005f66d  mov     rcx, rdi; unsigned __int16 *
0x14005f670  mov     edx, 23h ; '#'; unsigned int
0x14005f675  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f67a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f67f  call    cs:__imp_IsDebuggerPresent
0x14005f685  test    eax, eax
0x14005f687  jz      short loc_14005F6B9
0x14005f689  mov     r9d, 23h ; '#'
0x14005f68f  mov     dword ptr [rsp+0AB0h+phkResult], ebx
0x14005f693  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005f69a  mov     [rsp+0AB0h+lpSecurityAttributes], r14
0x14005f69f  mov     r8, rdi
0x14005f6a2  mov     qword ptr [rsp+0AB0h+samDesired], r15
0x14005f6a7  mov     ecx, r13d; unsigned __int8
0x14005f6aa  mov     qword ptr [rsp+0AB0h+dwOptions], rsi
0x14005f6af  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005f6b4  jmp     loc_14005FAB4
0x14005f6b9  mov     r8d, 23h ; '#'
0x14005f6bf  jmp     loc_14005FA94
0x14005f6c4  test    r14, r14
0x14005f6c7  jz      loc_14005F7B3
0x14005f6cd  lea     r8, asc_14009DFC0; "\\"
0x14005f6d4  mov     rdx, r9; unsigned __int64
0x14005f6d7  lea     rcx, [rbp+9B0h+SubKey]; unsigned __int16 *
0x14005f6de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005f6e3  mov     ebx, eax
0x14005f6e5  test    eax, eax
0x14005f6e7  jns     short loc_14005F741
0x14005f6e9  mov     [rsp+0AB0h+samDesired], eax; int
0x14005f6ed  lea     r15, aChra; "CHRA"
0x14005f6f4  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f6fb  mov     r9, r15; unsigned __int16 *
0x14005f6fe  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f705  mov     r8, rsi; unsigned __int16 *
0x14005f708  lea     r14, aHr; "hr"
0x14005f70f  mov     rcx, rdi; unsigned __int16 *
0x14005f712  mov     edx, 2Ah ; '*'; unsigned int
0x14005f717  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f71c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f721  call    cs:__imp_IsDebuggerPresent
0x14005f727  test    eax, eax
0x14005f729  jz      short loc_14005F736
0x14005f72b  mov     r9d, 2Ah ; '*'
0x14005f731  jmp     loc_14005F68F
0x14005f736  mov     r8d, 2Ah ; '*'
0x14005f73c  jmp     loc_14005FA94
0x14005f741  mov     r8, r14; unsigned __int16 *
0x14005f744  lea     rcx, [rbp+9B0h+SubKey]; unsigned __int16 *
0x14005f74b  mov     edx, 400h; unsigned __int64
0x14005f750  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005f755  mov     ebx, eax
0x14005f757  test    eax, eax
0x14005f759  jns     short loc_14005F7B3
0x14005f75b  mov     [rsp+0AB0h+samDesired], eax; int
0x14005f75f  lea     r15, aChra; "CHRA"
0x14005f766  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f76d  mov     r9, r15; unsigned __int16 *
0x14005f770  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f777  mov     r8, rsi; unsigned __int16 *
0x14005f77a  lea     r14, aHr; "hr"
0x14005f781  mov     rcx, rdi; unsigned __int16 *
0x14005f784  mov     edx, 2Dh ; '-'; unsigned int
0x14005f789  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f78e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f793  call    cs:__imp_IsDebuggerPresent
0x14005f799  test    eax, eax
0x14005f79b  jz      short loc_14005F7A8
0x14005f79d  mov     r9d, 2Dh ; '-'
0x14005f7a3  jmp     loc_14005F68F
0x14005f7a8  mov     r8d, 2Dh ; '-'
0x14005f7ae  jmp     loc_14005FA94
0x14005f7b3  mov     [rsp+0AB0h+lpdwDisposition], r12; lpdwDisposition
0x14005f7b8  lea     rax, [rsp+0AB0h+hKey]
0x14005f7bd  mov     [rsp+0AB0h+phkResult], rax; phkResult
0x14005f7c2  lea     rdx, [rbp+9B0h+SubKey]; lpSubKey
0x14005f7c9  mov     [rsp+0AB0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14005f7ce  xor     r9d, r9d; lpClass
0x14005f7d1  mov     [rsp+0AB0h+samDesired], 0F003Fh; samDesired
0x14005f7d9  xor     r8d, r8d; Reserved
0x14005f7dc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14005f7e3  mov     [rsp+0AB0h+dwOptions], r12d; dwOptions
0x14005f7e8  call    cs:__imp_RegCreateKeyExW
0x14005f7ee  test    eax, eax
0x14005f7f0  jz      short loc_14005F859
0x14005f7f2  jg      short loc_14005F7F8
0x14005f7f4  mov     ebx, eax
0x14005f7f6  jmp     short loc_14005F801
0x14005f7f8  movzx   ebx, ax
0x14005f7fb  or      ebx, 80070000h
0x14005f801  lea     r15, aCbraex; "CBRAEx"
0x14005f808  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005f80c  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f813  mov     r9, r15; unsigned __int16 *
0x14005f816  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f81d  mov     r8, rsi; unsigned __int16 *
0x14005f820  lea     r14, aLresult0l; "lResult == 0L"
0x14005f827  mov     rcx, rdi; unsigned __int16 *
0x14005f82a  mov     edx, 39h ; '9'; unsigned int
0x14005f82f  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f834  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f839  call    cs:__imp_IsDebuggerPresent
0x14005f83f  test    eax, eax
0x14005f841  jz      short loc_14005F84E
0x14005f843  mov     r9d, 39h ; '9'
0x14005f849  jmp     loc_14005F68F
0x14005f84e  mov     r8d, 39h ; '9'
0x14005f854  jmp     loc_14005FA94
0x14005f859  test    rsi, rsi
0x14005f85c  jz      loc_14005FAB4
0x14005f862  mov     edx, 104h
0x14005f867  lea     r9, [rsp+0AB0h+var_A50]
0x14005f86c  mov     r8d, edx
0x14005f86f  mov     rax, rsi
0x14005f872  test    rdi, rdi
0x14005f875  jz      short loc_14005F892
0x14005f877  movzx   ecx, word ptr [rax]
0x14005f87a  test    cx, cx
0x14005f87d  jz      short loc_14005F892
0x14005f87f  mov     [r9], cx
0x14005f883  add     rax, r13
0x14005f886  add     r9, r13
0x14005f889  dec     rdi
0x14005f88c  sub     r8, 1
0x14005f890  jnz     short loc_14005F872
0x14005f892  mov     rax, r8
0x14005f895  lea     rcx, [r9-2]
0x14005f899  neg     rax
0x14005f89c  sbb     ebx, ebx
0x14005f89e  not     ebx
0x14005f8a0  and     ebx, 8007007Ah
0x14005f8a6  test    r8, r8
0x14005f8a9  cmovnz  rcx, r9
0x14005f8ad  mov     [rcx], r12w
0x14005f8b1  jnz     short loc_14005F90B
0x14005f8b3  lea     r15, aChra; "CHRA"
0x14005f8ba  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005f8be  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f8c5  mov     r9, r15; unsigned __int16 *
0x14005f8c8  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f8cf  mov     r8, rsi; unsigned __int16 *
0x14005f8d2  lea     r14, aHr; "hr"
0x14005f8d9  mov     rcx, rdi; unsigned __int16 *
0x14005f8dc  mov     edx, 3Fh ; '?'; unsigned int
0x14005f8e1  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f8e6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f8eb  call    cs:__imp_IsDebuggerPresent
0x14005f8f1  test    eax, eax
0x14005f8f3  jz      short loc_14005F900
0x14005f8f5  mov     r9d, 3Fh ; '?'
0x14005f8fb  jmp     loc_14005F68F
0x14005f900  mov     r8d, 3Fh ; '?'
0x14005f906  jmp     loc_14005FA94
0x14005f90b  mov     rcx, rdx
0x14005f90e  lea     rax, [rsp+0AB0h+var_A50]
0x14005f913  cmp     [rax], r12w
0x14005f917  jz      short loc_14005F922
0x14005f919  add     rax, r13
0x14005f91c  sub     rcx, 1
0x14005f920  jnz     short loc_14005F913
0x14005f922  mov     rax, rcx
0x14005f925  neg     rax
0x14005f928  sbb     ebx, ebx
0x14005f92a  not     ebx
0x14005f92c  and     ebx, 80070057h
0x14005f932  test    rcx, rcx
0x14005f935  jnz     short loc_14005F98D
0x14005f937  lea     edx, [rcx+42h]; unsigned int
0x14005f93a  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005f93e  lea     r15, aChra; "CHRA"
0x14005f945  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f94c  mov     r9, r15; unsigned __int16 *
0x14005f94f  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005f956  mov     r8, rsi; unsigned __int16 *
0x14005f959  lea     r14, aHr; "hr"
0x14005f960  mov     rcx, rdi; unsigned __int16 *
0x14005f963  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005f968  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005f96d  call    cs:__imp_IsDebuggerPresent
0x14005f973  test    eax, eax
0x14005f975  jz      short loc_14005F982
0x14005f977  mov     r9d, 42h ; 'B'
0x14005f97d  jmp     loc_14005F68F
0x14005f982  mov     r8d, 42h ; 'B'
0x14005f988  jmp     loc_14005FA94
0x14005f98d  sub     rdx, rcx
0x14005f990  add     rdx, rdx
0x14005f993  neg     rcx
0x14005f996  mov     ecx, 0FFFFFFFFh
0x14005f99b  sbb     rax, rax
0x14005f99e  and     rax, rdx
0x14005f9a1  add     rax, r13
0x14005f9a4  cmp     rax, rcx
0x14005f9a7  ja      loc_14005FA3C
0x14005f9ad  mov     rcx, [rsp+0AB0h+hKey]; hKey
0x14005f9b2  mov     r9d, 1; dwType
0x14005f9b8  mov     [rsp+0AB0h+samDesired], eax; cbData
0x14005f9bc  xor     r8d, r8d; Reserved
0x14005f9bf  mov     rdx, r15; lpValueName
0x14005f9c2  mov     qword ptr [rsp+0AB0h+dwOptions], rsi; lpData
0x14005f9c7  mov     ebx, r12d
0x14005f9ca  call    cs:__imp_RegSetValueExW
0x14005f9d0  test    eax, eax
0x14005f9d2  jz      loc_14005FAB4
0x14005f9d8  jg      short loc_14005F9DE
0x14005f9da  mov     ebx, eax
0x14005f9dc  jmp     short loc_14005F9E7
0x14005f9de  movzx   ebx, ax
0x14005f9e1  or      ebx, 80070000h
0x14005f9e7  lea     r15, aCbraex; "CBRAEx"
0x14005f9ee  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005f9f2  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005f9f9  mov     r9, r15; unsigned __int16 *
0x14005f9fc  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fa03  mov     r8, rsi; unsigned __int16 *
0x14005fa06  lea     r14, aLresult0l; "lResult == 0L"
0x14005fa0d  mov     rcx, rdi; unsigned __int16 *
0x14005fa10  mov     edx, 4Eh ; 'N'; unsigned int
0x14005fa15  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005fa1a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fa1f  call    cs:__imp_IsDebuggerPresent
0x14005fa25  test    eax, eax
0x14005fa27  jz      short loc_14005FA34
0x14005fa29  mov     r9d, 4Eh ; 'N'
0x14005fa2f  jmp     loc_14005F68F
0x14005fa34  mov     r8d, 4Eh ; 'N'
0x14005fa3a  jmp     short loc_14005FA94
0x14005fa3c  mov     ebx, 80070216h
0x14005fa41  lea     r15, aChra; "CHRA"
0x14005fa48  lea     rsi, aAnonymousNames; "`anonymous-namespace'::SetKeyAndValue"
0x14005fa4f  mov     [rsp+0AB0h+samDesired], ebx; int
0x14005fa53  lea     rdi, aTermsrvWmsSrcC; "termsrv\\wms\\src\\common\\ntservice\\r"...
0x14005fa5a  mov     r9, r15; unsigned __int16 *
0x14005fa5d  lea     r14, aHr; "hr"
0x14005fa64  mov     r8, rsi; unsigned __int16 *
0x14005fa67  mov     rcx, rdi; unsigned __int16 *
0x14005fa6a  mov     qword ptr [rsp+0AB0h+dwOptions], r14; unsigned __int16 *
0x14005fa6f  mov     edx, 4Bh ; 'K'; unsigned int
0x14005fa74  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005fa79  call    cs:__imp_IsDebuggerPresent
  ... truncated ...
```

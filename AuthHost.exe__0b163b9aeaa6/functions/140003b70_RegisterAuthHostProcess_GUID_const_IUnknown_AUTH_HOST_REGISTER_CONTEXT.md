# RegisterAuthHostProcess(_GUID const &,IUnknown *,_AUTH_HOST_REGISTER_CONTEXT *)

- ea: `0x140003b70`
- end: `0x14000401d`
- name: `?RegisterAuthHostProcess@@YAJAEBU_GUID@@PEAUIUnknown@@PEAU_AUTH_HOST_REGISTER_CONTEXT@@@Z`
- size: `1197`
- prototype: `int(const struct _GUID *, struct IUnknown *, struct _AUTH_HOST_REGISTER_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003500`

## callees

- `0x140002c98`
- `0x140003b70`
- `0x140004024`
- `0x14000407c`
- `0x140004160`
- `0x14000429c`
- `0x1400042fc`
- `0x140012f2e`
- `0x140012f60`

## import_xrefs

- `msvcrt!wcstoul` at `0x140003c15`
- `msvcrt!wcstoul` at `0x140003c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003eed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003ee3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003ee3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e96`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e96`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003dbc`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140003dbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003ff5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140003bb2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140003bb2`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140003bcc`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x140003bcc`

## string_xrefs

- `0x140003bef`: `-AuthHostPurgeSsoCache`
- `0x140003cda`: `-AuthHostBrokerActivated`
- `0x140003e0f`: `AuthHostCompleteRegisterEvent`

## pseudocode

```c
__int64 __fastcall RegisterAuthHostProcess(
        const struct _GUID *a1,
        struct IUnknown *a2,
        struct _AUTH_HOST_REGISTER_CONTEXT *a3)
{
  const wchar_t **v4; // rbp
  const WCHAR *CommandLineW; // rax
  const WCHAR *v6; // rsi
  LPWSTR *v7; // rax
  int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  HRESULT v11; // eax
  signed int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const wchar_t *v17; // rdi
  __int64 v18; // r9
  size_t *v19; // r8
  __int64 v20; // r11
  unsigned __int64 v21; // r8
  wchar_t *v22; // rax
  __int64 v23; // rdx
  HANDLE EventW; // rax
  signed int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  signed int LastError; // eax
  LPDWORD lpdwRegister; // [rsp+20h] [rbp-278h]
  LPDWORD lpdwRegistera; // [rsp+20h] [rbp-278h]
  int pNumArgs; // [rsp+30h] [rbp-268h] BYREF
  _DWORD v33[3]; // [rsp+34h] [rbp-264h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-258h] BYREF

  v33[0] = 0;
  *(_OWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  pNumArgs = 0;
  v4 = 0;
  CommandLineW = GetCommandLineW();
  v6 = CommandLineW;
  if ( !CommandLineW
    || (v7 = CommandLineToArgvW(CommandLineW, &pNumArgs), (v4 = (const wchar_t **)v7) == 0)
    || (v8 = pNumArgs, pNumArgs < 2) )
  {
    v12 = -2147023257;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 3u )
    {
      goto LABEL_79;
    }
    v16 = 10;
    goto LABEL_78;
  }
  if ( !wcscmp_0(L"-AuthHostPurgeSsoCache", v7[1]) )
  {
    if ( v8 >= 3 )
    {
      v9 = wcstoul(v4[2], 0, 0);
      v10 = v9;
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids, v9);
        }
        v11 = PurgeAuthHostAppContainerCache(v10);
        v12 = v11;
        if ( v11 < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
          {
            v14 = 13;
LABEL_28:
            v18 = (unsigned int)v11;
LABEL_29:
            WPP_SF_d(v13[7], v14, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids, v18);
            goto LABEL_79;
          }
          goto LABEL_79;
        }
        v12 = 1;
        goto LABEL_63;
      }
    }
    v12 = -2147023257;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 3u )
    {
      goto LABEL_79;
    }
    v16 = 11;
LABEL_78:
    WPP_SF_S(v15[7], v16, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids, v6);
    goto LABEL_79;
  }
  if ( wcscmp_0(L"-AuthHostBrokerActivated", v4[1]) || v8 < 3 )
  {
    v12 = -2147023257;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 3u )
    {
      goto LABEL_79;
    }
    v16 = 14;
    goto LABEL_78;
  }
  v17 = v4[2];
  v11 = IsSsoAppContainer(v33);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( !v33[0] )
    {
      *((_DWORD *)a3 + 4) = 1;
      v11 = PurgeAuthHostAppContainerCache(0xFFFFFFFFLL);
      v12 = v11;
      if ( v11 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v14 = 16;
          goto LABEL_28;
        }
        goto LABEL_79;
      }
    }
    v11 = CoRegisterClassObject(&CLSID_AuthHostObject, &pUnk, 4u, 0, (LPDWORD)a3);
    v12 = v11;
    if ( v11 < 0 )
    {
      *(_DWORD *)a3 = 0;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v14 = 17;
        goto LABEL_28;
      }
      goto LABEL_79;
    }
    pszDest[0] = 0;
    v12 = StringCopyWorkerW(pszDest, 0x104u, v19, L"AuthHostCompleteRegisterEvent", (size_t)lpdwRegister);
    if ( v12 < 0 )
      goto LABEL_66;
    v21 = (unsigned int)v20;
    v22 = pszDest;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v12 = v21 == 0 ? 0x80070057 : 0;
    if ( v21 )
    {
      v23 = (v20 - v21) & ((unsigned __int128)-(__int128)v21 >> 64);
      v12 = StringCopyWorkerW(&pszDest[v23], v20 - v23, (size_t *)v21, v17, (size_t)lpdwRegistera);
    }
    if ( v12 < 0 )
    {
LABEL_66:
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v14 = 18;
        v18 = (unsigned int)v12;
        goto LABEL_29;
      }
      goto LABEL_79;
    }
    EventW = CreateEventW(0, 0, 0, pszDest);
    *((_QWORD *)a3 + 1) = EventW;
    if ( EventW )
    {
      if ( SetEvent(EventW) )
      {
        v12 = 0;
        goto LABEL_80;
      }
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v27 = 20;
        goto LABEL_62;
      }
    }
    else
    {
      v25 = GetLastError();
      v12 = v25;
      if ( v25 > 0 )
        v12 = (unsigned __int16)v25 | 0x80070000;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v27 = 19;
LABEL_62:
        WPP_SF_d(v26[7], v27, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids, (unsigned int)v12);
      }
    }
LABEL_63:
    if ( v12 < 0 )
      goto LABEL_79;
LABEL_80:
    LocalFree(v4);
    return (unsigned int)v12;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    v14 = 15;
    goto LABEL_28;
  }
LABEL_79:
  UnregisterAuthHostProcess(a3);
  if ( v4 )
    goto LABEL_80;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140003b70  push    rbx
0x140003b72  push    rbp
0x140003b73  push    rsi
0x140003b74  push    rdi
0x140003b75  push    r14
0x140003b77  push    r15
0x140003b79  sub     rsp, 268h
0x140003b80  mov     rax, cs:__security_cookie
0x140003b87  xor     rax, rsp
0x140003b8a  mov     [rsp+298h+var_48], rax
0x140003b92  xor     r15d, r15d
0x140003b95  xorps   xmm0, xmm0
0x140003b98  xor     eax, eax
0x140003b9a  mov     [rsp+298h+var_264], r15d
0x140003b9f  movups  xmmword ptr [r8], xmm0
0x140003ba3  mov     [r8+10h], rax
0x140003ba7  mov     r14, r8
0x140003baa  mov     [rsp+298h+pNumArgs], r15d
0x140003baf  mov     ebp, r15d
0x140003bb2  call    cs:__imp_GetCommandLineW
0x140003bb8  mov     rsi, rax
0x140003bbb  test    rax, rax
0x140003bbe  jz      loc_140003FA9
0x140003bc4  lea     rdx, [rsp+298h+pNumArgs]; pNumArgs
0x140003bc9  mov     rcx, rax; lpCmdLine
0x140003bcc  call    cs:__imp_CommandLineToArgvW
0x140003bd2  mov     rbp, rax
0x140003bd5  test    rax, rax
0x140003bd8  jz      loc_140003FA9
0x140003bde  mov     ebx, [rsp+298h+pNumArgs]
0x140003be2  cmp     ebx, 2
0x140003be5  jl      loc_140003FA9
0x140003beb  mov     rdx, [rax+8]; String2
0x140003bef  lea     rcx, aAuthhostpurges; "-AuthHostPurgeSsoCache"
0x140003bf6  call    wcscmp_0
0x140003bfb  test    eax, eax
0x140003bfd  jnz     loc_140003CD6
0x140003c03  cmp     ebx, 3
0x140003c06  jl      loc_140003C9C
0x140003c0c  mov     rcx, [rbp+10h]; String
0x140003c10  xor     r8d, r8d; Radix
0x140003c13  xor     edx, edx; EndPtr
0x140003c15  call    cs:__imp_wcstoul
0x140003c1b  mov     ebx, eax
0x140003c1d  test    eax, eax
0x140003c1f  jz      short loc_140003C9C
0x140003c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c28  lea     rdi, WPP_GLOBAL_Control
0x140003c2f  cmp     rcx, rdi
0x140003c32  jz      short loc_140003C57
0x140003c34  test    byte ptr [rcx+44h], 10h
0x140003c38  jz      short loc_140003C57
0x140003c3a  cmp     byte ptr [rcx+41h], 4
0x140003c3e  jb      short loc_140003C57
0x140003c40  mov     rcx, [rcx+38h]
0x140003c44  lea     edx, [r15+0Ch]
0x140003c48  mov     r9d, eax
0x140003c4b  lea     r8, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids
0x140003c52  call    WPP_SF_d
0x140003c57  mov     ecx, ebx
0x140003c59  call    _PurgeAuthHostAppContainerCache
0x140003c5e  mov     ebx, eax
0x140003c60  test    eax, eax
0x140003c62  jns     short loc_140003C92
0x140003c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c6b  cmp     rcx, rdi
0x140003c6e  jz      loc_140003FE5
0x140003c74  test    byte ptr [rcx+44h], 10h
0x140003c78  jz      loc_140003FE5
0x140003c7e  cmp     byte ptr [rcx+41h], 3
0x140003c82  jb      loc_140003FE5
0x140003c88  mov     edx, 0Dh
0x140003c8d  jmp     loc_140003D3B
0x140003c92  mov     ebx, 1
0x140003c97  jmp     loc_140003F39
0x140003c9c  mov     ebx, 80070667h
0x140003ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ca8  lea     rdi, WPP_GLOBAL_Control
0x140003caf  cmp     rcx, rdi
0x140003cb2  jz      loc_140003FE5
0x140003cb8  test    byte ptr [rcx+44h], 10h
0x140003cbc  jz      loc_140003FE5
0x140003cc2  cmp     byte ptr [rcx+41h], 3
0x140003cc6  jb      loc_140003FE5
0x140003ccc  mov     edx, 0Bh
0x140003cd1  jmp     loc_140003FD2
0x140003cd6  mov     rdx, [rbp+8]; String2
0x140003cda  lea     rcx, aAuthhostbroker; "-AuthHostBrokerActivated"
0x140003ce1  call    wcscmp_0
0x140003ce6  test    eax, eax
0x140003ce8  jnz     loc_140003F7E
0x140003cee  cmp     ebx, 3
0x140003cf1  jl      loc_140003F7E
0x140003cf7  mov     rdi, [rbp+10h]
0x140003cfb  lea     rcx, [rsp+298h+var_264]
0x140003d00  call    _IsSsoAppContainer
0x140003d05  mov     ebx, eax
0x140003d07  test    eax, eax
0x140003d09  jns     short loc_140003D53
0x140003d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d12  lea     rdi, WPP_GLOBAL_Control
0x140003d19  cmp     rcx, rdi
0x140003d1c  jz      loc_140003FE5
0x140003d22  test    byte ptr [rcx+44h], 10h
0x140003d26  jz      loc_140003FE5
0x140003d2c  cmp     byte ptr [rcx+41h], 2
0x140003d30  jb      loc_140003FE5
0x140003d36  mov     edx, 0Fh
0x140003d3b  mov     r9d, eax
0x140003d3e  mov     rcx, [rcx+38h]
0x140003d42  lea     r8, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids
0x140003d49  call    WPP_SF_d
0x140003d4e  jmp     loc_140003FE5
0x140003d53  cmp     [rsp+298h+var_264], r15d
0x140003d58  jnz     short loc_140003DA2
0x140003d5a  or      ecx, 0FFFFFFFFh
0x140003d5d  mov     dword ptr [r14+10h], 1
0x140003d65  call    _PurgeAuthHostAppContainerCache
0x140003d6a  mov     ebx, eax
0x140003d6c  test    eax, eax
0x140003d6e  jns     short loc_140003DA2
0x140003d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d77  lea     rdi, WPP_GLOBAL_Control
0x140003d7e  cmp     rcx, rdi
0x140003d81  jz      loc_140003FE5
0x140003d87  test    byte ptr [rcx+44h], 10h
0x140003d8b  jz      loc_140003FE5
0x140003d91  cmp     byte ptr [rcx+41h], 2
0x140003d95  jb      loc_140003FE5
0x140003d9b  mov     edx, 10h
0x140003da0  jmp     short loc_140003D3B
0x140003da2  xor     r9d, r9d; flags
0x140003da5  mov     [rsp+298h+lpdwRegister], r14; cchToCopy
0x140003daa  lea     rdx, pUnk; pUnk
0x140003db1  lea     rcx, CLSID_AuthHostObject; rclsid
0x140003db8  lea     r8d, [r9+4]; dwClsContext
0x140003dbc  call    cs:__imp_CoRegisterClassObject
0x140003dc2  mov     ebx, eax
0x140003dc4  test    eax, eax
0x140003dc6  jns     short loc_140003E00
0x140003dc8  mov     [r14], r15d
0x140003dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dd2  lea     rdi, WPP_GLOBAL_Control
0x140003dd9  cmp     rcx, rdi
0x140003ddc  jz      loc_140003FE5
0x140003de2  test    byte ptr [rcx+44h], 10h
0x140003de6  jz      loc_140003FE5
0x140003dec  cmp     byte ptr [rcx+41h], 2
0x140003df0  jb      loc_140003FE5
0x140003df6  mov     edx, 11h
0x140003dfb  jmp     loc_140003D3B
0x140003e00  mov     r11d, 104h
0x140003e06  mov     [rsp+298h+pszDest], r15w
0x140003e0c  mov     edx, r11d; cchDest
0x140003e0f  lea     r9, aAuthhostcomple; "AuthHostCompleteRegisterEvent"
0x140003e16  lea     rcx, [rsp+298h+pszDest]; pszDest
0x140003e1b  call    StringCopyWorkerW
0x140003e20  mov     ebx, eax
0x140003e22  test    eax, eax
0x140003e24  js      loc_140003F4E
0x140003e2a  mov     r8d, r11d
0x140003e2d  lea     rax, [rsp+298h+pszDest]
0x140003e32  cmp     [rax], r15w
0x140003e36  jz      short loc_140003E42
0x140003e38  add     rax, 2
0x140003e3c  sub     r8, 1; pcchNewDestLength
0x140003e40  jnz     short loc_140003E32
0x140003e42  mov     rax, r8
0x140003e45  mov     rcx, r11
0x140003e48  neg     rax
0x140003e4b  mov     rax, r8
0x140003e4e  sbb     ebx, ebx
0x140003e50  sub     rcx, r8
0x140003e53  not     ebx
0x140003e55  and     ebx, 80070057h
0x140003e5b  neg     rax
0x140003e5e  sbb     rdx, rdx
0x140003e61  and     rdx, rcx
0x140003e64  test    r8, r8
0x140003e67  jz      short loc_140003E82
0x140003e69  sub     r11, rdx
0x140003e6c  lea     rcx, [rsp+298h+pszDest]
0x140003e71  lea     rcx, [rcx+rdx*2]; pszDest
0x140003e75  mov     r9, rdi; pszSrc
0x140003e78  mov     rdx, r11; cchDest
0x140003e7b  call    StringCopyWorkerW
0x140003e80  mov     ebx, eax
0x140003e82  test    ebx, ebx
0x140003e84  js      loc_140003F4E
0x140003e8a  lea     r9, [rsp+298h+pszDest]; lpName
0x140003e8f  xor     r8d, r8d; bInitialState
0x140003e92  xor     edx, edx; bManualReset
0x140003e94  xor     ecx, ecx; lpEventAttributes
0x140003e96  call    cs:__imp_CreateEventW
0x140003e9c  mov     [r14+8], rax
0x140003ea0  test    rax, rax
0x140003ea3  jnz     short loc_140003EE0
0x140003ea5  call    cs:__imp_GetLastError
0x140003eab  mov     ebx, eax
0x140003ead  test    eax, eax
0x140003eaf  jle     short loc_140003EBA
0x140003eb1  movzx   ebx, ax
0x140003eb4  or      ebx, 80070000h
0x140003eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ec1  lea     rdi, WPP_GLOBAL_Control
0x140003ec8  cmp     rcx, rdi
0x140003ecb  jz      short loc_140003F39
0x140003ecd  test    byte ptr [rcx+44h], 10h
0x140003ed1  jz      short loc_140003F39
0x140003ed3  cmp     byte ptr [rcx+41h], 2
0x140003ed7  jb      short loc_140003F39
0x140003ed9  mov     edx, 13h
0x140003ede  jmp     short loc_140003F26
0x140003ee0  mov     rcx, rax; hEvent
0x140003ee3  call    cs:__imp_SetEvent
0x140003ee9  test    eax, eax
0x140003eeb  jnz     short loc_140003F46
0x140003eed  call    cs:__imp_GetLastError
0x140003ef3  mov     ebx, eax
0x140003ef5  test    eax, eax
0x140003ef7  jle     short loc_140003F02
0x140003ef9  movzx   ebx, ax
0x140003efc  or      ebx, 80070000h
0x140003f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f09  lea     rdi, WPP_GLOBAL_Control
0x140003f10  cmp     rcx, rdi
0x140003f13  jz      short loc_140003F39
0x140003f15  test    byte ptr [rcx+44h], 10h
0x140003f19  jz      short loc_140003F39
0x140003f1b  cmp     byte ptr [rcx+41h], 2
0x140003f1f  jb      short loc_140003F39
0x140003f21  mov     edx, 14h
0x140003f26  mov     rcx, [rcx+38h]
0x140003f2a  lea     r8, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids
0x140003f31  mov     r9d, ebx
0x140003f34  call    WPP_SF_d
0x140003f39  test    ebx, ebx
0x140003f3b  jns     loc_140003FF2
0x140003f41  jmp     loc_140003FE5
0x140003f46  mov     ebx, r15d
0x140003f49  jmp     loc_140003FF2
0x140003f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f55  lea     rdi, WPP_GLOBAL_Control
0x140003f5c  cmp     rcx, rdi
0x140003f5f  jz      loc_140003FE5
0x140003f65  test    byte ptr [rcx+44h], 10h
0x140003f69  jz      short loc_140003FE5
0x140003f6b  cmp     byte ptr [rcx+41h], 2
0x140003f6f  jb      short loc_140003FE5
0x140003f71  mov     edx, 12h
0x140003f76  mov     r9d, ebx
0x140003f79  jmp     loc_140003D3E
0x140003f7e  mov     ebx, 80070667h
0x140003f83  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f8a  lea     rdi, WPP_GLOBAL_Control
0x140003f91  cmp     rcx, rdi
0x140003f94  jz      short loc_140003FE5
0x140003f96  test    byte ptr [rcx+44h], 10h
0x140003f9a  jz      short loc_140003FE5
0x140003f9c  cmp     byte ptr [rcx+41h], 3
0x140003fa0  jb      short loc_140003FE5
0x140003fa2  mov     edx, 0Eh
0x140003fa7  jmp     short loc_140003FD2
0x140003fa9  mov     ebx, 80070667h
0x140003fae  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fb5  lea     rdi, WPP_GLOBAL_Control
0x140003fbc  cmp     rcx, rdi
0x140003fbf  jz      short loc_140003FE5
0x140003fc1  test    byte ptr [rcx+44h], 10h
0x140003fc5  jz      short loc_140003FE5
0x140003fc7  cmp     byte ptr [rcx+41h], 3
0x140003fcb  jb      short loc_140003FE5
0x140003fcd  mov     edx, 0Ah
0x140003fd2  mov     rcx, [rcx+38h]
0x140003fd6  lea     r8, WPP_d672079daa5c3533fef55dc4d0763d25_Traceguids
0x140003fdd  mov     r9, rsi
0x140003fe0  call    WPP_SF_S
0x140003fe5  mov     rcx, r14; struct _AUTH_HOST_REGISTER_CONTEXT *
0x140003fe8  call    ?UnregisterAuthHostProcess@@YAJPEAU_AUTH_HOST_REGISTER_CONTEXT@@@Z; UnregisterAuthHostProcess(_AUTH_HOST_REGISTER_CONTEXT *)
0x140003fed  test    rbp, rbp
0x140003ff0  jz      short loc_140003FFB
0x140003ff2  mov     rcx, rbp; hMem
0x140003ff5  call    cs:__imp_LocalFree
0x140003ffb  mov     eax, ebx
0x140003ffd  mov     rcx, [rsp+298h+var_48]
0x140004005  xor     rcx, rsp; StackCookie
0x140004008  call    __security_check_cookie
0x14000400d  add     rsp, 268h
0x140004014  pop     r15
0x140004016  pop     r14
0x140004018  pop     rdi
0x140004019  pop     rsi
0x14000401a  pop     rbp
0x14000401b  pop     rbx
0x14000401c  retn
```

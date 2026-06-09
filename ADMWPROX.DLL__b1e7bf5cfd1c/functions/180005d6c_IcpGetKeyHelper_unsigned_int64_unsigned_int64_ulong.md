# IcpGetKeyHelper(unsigned __int64 *,unsigned __int64,ulong)

- ea: `0x180005d6c`
- end: `0x180005f20`
- name: `?IcpGetKeyHelper@@YAJPEA_K_KK@Z`
- size: `436`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, HCRYPTPROV hProv, ALG_ID Algid)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800053bc`

## callees

- `0x180004870`
- `0x180005d6c`
- `0x180007234`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005e20`
- `KERNEL32!EnterCriticalSection` at `0x180005e20`
- `KERNEL32!LeaveCriticalSection` at `0x180005f0f`
- `KERNEL32!LeaveCriticalSection` at `0x180005f0f`
- `ADVAPI32!CryptGetUserKey` at `0x180005dbd`
- `ADVAPI32!CryptGetUserKey` at `0x180005e2e`
- `ADVAPI32!CryptGetUserKey` at `0x180005dbd`
- `ADVAPI32!CryptGetUserKey` at `0x180005e2e`
- `ADVAPI32!CryptGenKey` at `0x180005e7c`
- `ADVAPI32!CryptGenKey` at `0x180005e7c`

## string_xrefs

- `0x180005dfb`: `IcpGetKeyHelper.CryptGetUserKey (advapi32.dll) failed err=0x%x.toast.\n`
- `0x180005eaf`: `IcpGetKeyHelper.CryptGenKey (advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IcpGetKeyHelper(HCRYPTKEY *phKey, HCRYPTPROV hProv, ALG_ID Algid)
{
  HCRYPTKEY v6; // rax
  int LastError; // eax
  int v9; // ebx
  int v10; // eax
  char v11; // [rsp+28h] [rbp-30h]

  if ( dword_18000FC34 )
  {
    if ( CryptGetUserKey(hProv, Algid, phKey) )
      return 0;
    LastError = IcpGetLastError();
    v9 = LastError;
    if ( LastError == -2146893811 )
    {
      v9 = 0;
      EnterCriticalSection(&IcpGlobals);
      if ( !CryptGetUserKey(hProv, Algid, phKey) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            0x63Au,
            "IcpGetKeyHelper",
            "IcpGetKeyHelper.CryptGetUserKey:failed, lets try to generate another key.\n",
            v11);
        if ( CryptGenKey(hProv, Algid, 0, phKey) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              0x648u,
              "IcpGetKeyHelper",
              "IcpGetKeyHelper.CryptGenKey:key generated.\n",
              v11);
        }
        else
        {
          v10 = IcpGetLastError();
          v9 = v10;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              0x644u,
              "IcpGetKeyHelper",
              "IcpGetKeyHelper.CryptGenKey (advapi32.dll) failed err=0x%x.\n",
              v10);
          if ( v9 < 0 )
            *phKey = 0;
        }
      }
      LeaveCriticalSection(&IcpGlobals);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        0x61Bu,
        "IcpGetKeyHelper",
        "IcpGetKeyHelper.CryptGetUserKey (advapi32.dll) failed err=0x%x.toast.\n",
        LastError);
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( hProv == 1984918096 )
    {
      v6 = 1801020747;
      if ( Algid != 1 )
        v6 = 1799842131;
      *phKey = v6;
      return 0;
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180005d6c  push    rbx
0x180005d6e  push    rbp
0x180005d6f  push    rsi
0x180005d70  push    rdi
0x180005d71  sub     rsp, 38h
0x180005d75  cmp     cs:dword_18000FC34, 0
0x180005d7c  mov     ebp, r8d
0x180005d7f  mov     rsi, rdx
0x180005d82  mov     rdi, rcx
0x180005d85  jnz     short loc_180005DB5
0x180005d87  cmp     rdx, 764F7250h
0x180005d8e  jnz     short loc_180005DAB
0x180005d90  cmp     r8d, 1
0x180005d94  mov     eax, 6B59654Bh
0x180005d99  mov     ecx, 6B476953h
0x180005d9e  cmovnz  eax, ecx
0x180005da1  mov     [rdi], rax
0x180005da4  xor     eax, eax
0x180005da6  jmp     loc_180005F17
0x180005dab  mov     eax, 80070057h
0x180005db0  jmp     loc_180005F17
0x180005db5  mov     r8, rdi; phUserKey
0x180005db8  mov     edx, ebp; dwKeySpec
0x180005dba  mov     rcx, rsi; hProv
0x180005dbd  call    cs:__imp_CryptGetUserKey
0x180005dc3  test    eax, eax
0x180005dc5  jnz     short loc_180005DA4
0x180005dc7  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180005dcc  mov     ebx, eax
0x180005dce  cmp     eax, 8009000Dh
0x180005dd3  jz      short loc_180005E17
0x180005dd5  test    byte ptr cs:g_dwDebugFlags, 3
0x180005ddc  jz      loc_180005F15
0x180005de2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005de9  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x180005df0  mov     dword ptr [rsp+58h+var_30], eax; char
0x180005df4  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180005dfb  lea     rax, aIcpgetkeyhelpe_3; "IcpGetKeyHelper.CryptGetUserKey (advapi"...
0x180005e02  mov     r8d, 61Bh; unsigned int
0x180005e08  mov     [rsp+58h+var_38], rax; char *
0x180005e0d  call    PuDbgPrint
0x180005e12  jmp     loc_180005F15
0x180005e17  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180005e1e  xor     ebx, ebx
0x180005e20  call    cs:__imp_EnterCriticalSection
0x180005e26  mov     r8, rdi; phUserKey
0x180005e29  mov     edx, ebp; dwKeySpec
0x180005e2b  mov     rcx, rsi; hProv
0x180005e2e  call    cs:__imp_CryptGetUserKey
0x180005e34  test    eax, eax
0x180005e36  jnz     loc_180005F08
0x180005e3c  test    byte ptr cs:g_dwDebugFlags, 3
0x180005e43  jz      short loc_180005E71
0x180005e45  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005e4c  lea     rax, aIcpgetkeyhelpe_1; "IcpGetKeyHelper.CryptGetUserKey:failed,"...
0x180005e53  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x180005e5a  mov     [rsp+58h+var_38], rax; char *
0x180005e5f  mov     r8d, 63Ah; unsigned int
0x180005e65  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180005e6c  call    PuDbgPrint
0x180005e71  mov     r9, rdi; phKey
0x180005e74  xor     r8d, r8d; dwFlags
0x180005e77  mov     edx, ebp; Algid
0x180005e79  mov     rcx, rsi; hProv
0x180005e7c  call    cs:__imp_CryptGenKey
0x180005e82  test    eax, eax
0x180005e84  jnz     short loc_180005ED3
0x180005e86  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180005e8b  test    byte ptr cs:g_dwDebugFlags, 3
0x180005e92  mov     ebx, eax
0x180005e94  jz      short loc_180005EC6
0x180005e96  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005e9d  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x180005ea4  mov     dword ptr [rsp+58h+var_30], eax; char
0x180005ea8  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180005eaf  lea     rax, aIcpgetkeyhelpe; "IcpGetKeyHelper.CryptGenKey (advapi32.d"...
0x180005eb6  mov     r8d, 644h; unsigned int
0x180005ebc  mov     [rsp+58h+var_38], rax; char *
0x180005ec1  call    PuDbgPrint
0x180005ec6  test    ebx, ebx
0x180005ec8  jns     short loc_180005F08
0x180005eca  mov     qword ptr [rdi], 0
0x180005ed1  jmp     short loc_180005F08
0x180005ed3  test    byte ptr cs:g_dwDebugFlags, 3
0x180005eda  jz      short loc_180005F08
0x180005edc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005ee3  lea     rax, aIcpgetkeyhelpe_0; "IcpGetKeyHelper.CryptGenKey:key generat"...
0x180005eea  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x180005ef1  mov     [rsp+58h+var_38], rax; char *
0x180005ef6  mov     r8d, 648h; unsigned int
0x180005efc  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x180005f03  call    PuDbgPrint
0x180005f08  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x180005f0f  call    cs:__imp_LeaveCriticalSection
0x180005f15  mov     eax, ebx
0x180005f17  add     rsp, 38h
0x180005f1b  pop     rdi
0x180005f1c  pop     rsi
0x180005f1d  pop     rbp
0x180005f1e  pop     rbx
0x180005f1f  retn
```

# sub_1803CAB7C

- ea: `0x1803cab7c`
- end: `0x1803cb132`
- name: `sub_1803CAB7C`
- size: `1462`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1803cc1e0`

## callees

- `0x180067aa0`
- `0x1800a3680`
- `0x1800a7750`
- `0x1800b6d50`
- `0x1800b6dcc`
- `0x1800b6ecc`
- `0x1801c62e4`
- `0x180219ac0`
- `0x1802bcb34`
- `0x1803b466c`
- `0x1803c5664`
- `0x1803cab7c`
- `0x180473120`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1803cb0fa`
- `KERNEL32!LeaveCriticalSection` at `0x1803cb0fa`
- `KERNEL32!EnterCriticalSection` at `0x1803cabda`
- `KERNEL32!EnterCriticalSection` at `0x1803cabda`
- `KERNEL32!GlobalFree` at `0x1803cad30`
- `KERNEL32!GlobalFree` at `0x1803cad43`
- `KERNEL32!GlobalFree` at `0x1803caf14`
- `KERNEL32!GlobalFree` at `0x1803caf24`
- `KERNEL32!GlobalFree` at `0x1803caf38`
- `KERNEL32!GlobalFree` at `0x1803cb0ce`
- `KERNEL32!GlobalFree` at `0x1803cb0de`
- `KERNEL32!GlobalFree` at `0x1803cb0ee`
- `KERNEL32!GlobalFree` at `0x1803cad30`
- `KERNEL32!GlobalFree` at `0x1803cad43`
- `KERNEL32!GlobalFree` at `0x1803caf14`
- `KERNEL32!GlobalFree` at `0x1803caf24`
- `KERNEL32!GlobalFree` at `0x1803caf38`
- `KERNEL32!GlobalFree` at `0x1803cb0ce`
- `KERNEL32!GlobalFree` at `0x1803cb0de`
- `KERNEL32!GlobalFree` at `0x1803cb0ee`
- `KERNEL32!GetLastError` at `0x1803caeb7`
- `KERNEL32!GetLastError` at `0x1803caeb7`
- `WINHTTP!WinHttpOpen` at `0x1803cae66`
- `WINHTTP!WinHttpOpen` at `0x1803cae66`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1803cafdf`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1803cafdf`
- `WINHTTP!WinHttpConnect` at `0x1803cb05c`
- `WINHTTP!WinHttpConnect` at `0x1803cb05c`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1803cacc1`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1803cacc1`
- `WINHTTP!WinHttpSetTimeouts` at `0x1803caea9`
- `WINHTTP!WinHttpSetTimeouts` at `0x1803caea9`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1803cacad`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1803cacad`
- `WINHTTP!WinHttpSetOption` at `0x1803caf64`
- `WINHTTP!WinHttpSetOption` at `0x1803caf90`
- `WINHTTP!WinHttpSetOption` at `0x1803caf64`
- `WINHTTP!WinHttpSetOption` at `0x1803caf90`

## pseudocode

```c
__int64 __fastcall sub_1803CAB7C(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  const WCHAR *lpszProxy; // r15
  const WCHAR *lpszProxyBypass; // r12
  int v6; // eax
  DWORD v7; // r14d
  LPWSTR lpszAutoConfigUrl; // rdx
  __int64 v9; // r8
  __int128 *v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rax
  WINHTTP_PROXY_INFO *p_pProxyInfo; // rdx
  void *v16; // rcx
  __int64 v17; // rdx
  DWORD LastError; // edi
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  int v22; // r8d
  const WCHAR *v23; // rdx
  HINTERNET v24; // rax
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig_8; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v27[3]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v28; // [rsp+80h] [rbp-88h]
  unsigned __int64 v29; // [rsp+88h] [rbp-80h]
  int Buffer; // [rsp+90h] [rbp-78h] BYREF
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v32; // [rsp+B0h] [rbp-58h]
  __int128 v33; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v35; // [rsp+D0h] [rbp-38h]
  _BYTE v36[32]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v37[2]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v38; // [rsp+110h] [rbp+8h]
  _BYTE v39[32]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v40[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v41[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v42[32]; // [rsp+178h] [rbp+70h] BYREF
  int v43; // [rsp+198h] [rbp+90h]

  if ( *(_BYTE *)(a1 + 1096) )
    return 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 272);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
  if ( !*(_BYTE *)(a1 + 1096) )
  {
    memset(&pProxyConfig_8, 0, sizeof(pProxyConfig_8));
    lpszProxy = 0;
    lpszProxyBypass = 0;
    *(_BYTE *)(a1 + 1121) = 0;
    *(_OWORD *)&v27[1] = 0;
    v28 = 0;
    v29 = 7;
    LOWORD(v27[1]) = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    sub_1800A3680(&v33, &dword_1804B6234, 1);
    sub_1801C62E4(v36);
    v6 = *(_DWORD *)(a1 + 600);
    if ( v6 )
    {
      if ( v6 == 2 )
      {
        v7 = 1;
      }
      else if ( v6 == 1 )
      {
        v7 = sub_1803C5664();
        if ( v7 != 4 )
        {
          *(_BYTE *)(a1 + 1121) = 1;
          memset(&pProxyInfo, 0, sizeof(pProxyInfo));
          if ( (!WinHttpGetDefaultProxyConfiguration(&pProxyInfo) || pProxyInfo.dwAccessType == 1)
            && WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig_8) )
          {
            if ( pProxyConfig_8.fAutoDetect )
            {
              *(_BYTE *)(a1 + 1121) = 1;
            }
            else
            {
              lpszAutoConfigUrl = pProxyConfig_8.lpszAutoConfigUrl;
              if ( pProxyConfig_8.lpszAutoConfigUrl )
              {
                *(_BYTE *)(a1 + 1121) = 1;
                v9 = -1;
                do
                  ++v9;
                while ( lpszAutoConfigUrl[v9] );
                sub_1800B6DCC(a1 + 1128, lpszAutoConfigUrl);
              }
              else if ( pProxyConfig_8.lpszProxy )
              {
                v7 = 3;
                lpszProxy = pProxyConfig_8.lpszProxy;
                if ( pProxyConfig_8.lpszProxyBypass )
                  lpszProxyBypass = pProxyConfig_8.lpszProxyBypass;
              }
            }
          }
          if ( pProxyInfo.lpszProxy )
            GlobalFree(pProxyInfo.lpszProxy);
          if ( pProxyInfo.lpszProxyBypass )
            GlobalFree(pProxyInfo.lpszProxyBypass);
        }
      }
      else
      {
        v7 = 3;
        sub_1803B466C(&v33);
        if ( !v34 )
          goto LABEL_35;
        v10 = &v33;
        if ( v35 > 7 )
          v10 = (__int128 *)v33;
        if ( v34 == 1 && !(unsigned int)sub_1800B6ECC(v10, &dword_1804B6234, 1) || v43 )
        {
LABEL_35:
          v11 = v37;
          if ( v38 > 7 )
            v11 = (_QWORD *)v37[0];
          sub_1800B6DCC(&v27[1], v11);
          if ( v43 > 0 )
          {
            v13 = v28;
            if ( v28 >= v29 )
            {
              LOBYTE(v12) = 0;
              sub_180219AC0(&v27[1], 1, v12, 58);
            }
            else
            {
              ++v28;
              v14 = &v27[1];
              if ( v29 > 7 )
                v14 = (_QWORD *)v27[1];
              *(_DWORD *)((char *)v14 + 2 * v13) = 58;
            }
            sub_1802BCB34(&pProxyInfo, (unsigned int)v43);
            p_pProxyInfo = &pProxyInfo;
            if ( v32 > 7 )
              p_pProxyInfo = *(WINHTTP_PROXY_INFO **)&pProxyInfo.dwAccessType;
            sub_1800B6D50(&v27[1], p_pProxyInfo, pProxyInfo.lpszProxyBypass);
            sub_1800A7750(&pProxyInfo);
          }
          lpszProxy = (const WCHAR *)&v27[1];
          if ( v29 > 7 )
            lpszProxy = (const WCHAR *)v27[1];
        }
        else
        {
          lpszProxy = (const WCHAR *)v37;
          if ( v38 > 7 )
            lpszProxy = (const WCHAR *)v37[0];
        }
      }
    }
    else
    {
      v7 = sub_1803C5664();
    }
    v16 = WinHttpOpen(0, v7, lpszProxy, lpszProxyBypass, 0x10000000u);
    *(_QWORD *)(a1 + 1104) = v16;
    if ( !v16 )
      goto LABEL_52;
    v17 = *(_QWORD *)(a1 + 744) / 1000LL;
    if ( (int)v17 < 1 )
      LODWORD(v17) = 1;
    if ( !WinHttpSetTimeouts(v16, v17, v17, v17, v17) )
      goto LABEL_52;
    if ( *(_BYTE *)(a1 + 736) )
    {
      Buffer = 1;
      if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 1104), 0x49u, &Buffer, 4u) )
        goto LABEL_52;
    }
    LODWORD(v27[0]) = 2720;
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 1104), 0x54u, v27, 4u) )
      goto LABEL_52;
    v19 = *(_QWORD *)(a1 + 888);
    if ( v19 )
    {
      v26 = *(_QWORD *)(a1 + 1104);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 16LL))(v19, &v26);
    }
    if ( WinHttpSetStatusCallback(*(HINTERNET *)(a1 + 1104), (WINHTTP_STATUS_CALLBACK)fnInternetCallback, 0x97F4C30u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      goto LABEL_52;
    v20 = *(_QWORD *)(a1 + 56);
    if ( !v20 )
      goto LABEL_71;
    v21 = a1 + 40;
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v21 = *(_QWORD *)(a1 + 40);
    if ( v20 == 1 && !(unsigned int)sub_1800B6ECC(v21, &dword_1804B6234, 1) || *(_DWORD *)(a1 + 264) )
LABEL_71:
      v22 = *(_DWORD *)(a1 + 264);
    else
      LOWORD(v22) = *(_BYTE *)(a1 + 1120) != 0 ? 443 : 80;
    v23 = (const WCHAR *)(a1 + 104);
    if ( *(_QWORD *)(a1 + 128) > 7u )
      v23 = *(const WCHAR **)v23;
    v24 = WinHttpConnect(*(HINTERNET *)(a1 + 1104), v23, v22, 0);
    *(_QWORD *)(a1 + 1112) = v24;
    if ( !v24 )
    {
LABEL_52:
      LastError = GetLastError();
      sub_1800A7750(v42);
      sub_1800A7750(v41);
      sub_1800A7750(v40);
      sub_1800A7750(v39);
      sub_1800A7750(v37);
      sub_1800A7750(v36);
      sub_1800A7750(&v33);
      sub_1800A7750(&v27[1]);
      if ( pProxyConfig_8.lpszAutoConfigUrl )
        GlobalFree(pProxyConfig_8.lpszAutoConfigUrl);
      if ( pProxyConfig_8.lpszProxy )
        GlobalFree(pProxyConfig_8.lpszProxy);
      if ( pProxyConfig_8.lpszProxyBypass )
        GlobalFree(pProxyConfig_8.lpszProxyBypass);
      goto LABEL_82;
    }
    *(_BYTE *)(a1 + 1096) = 1;
    sub_1800A7750(v42);
    sub_1800A7750(v41);
    sub_1800A7750(v40);
    sub_1800A7750(v39);
    sub_1800A7750(v37);
    sub_1800A7750(v36);
    sub_1800A7750(&v33);
    sub_1800A7750(&v27[1]);
    if ( pProxyConfig_8.lpszAutoConfigUrl )
      GlobalFree(pProxyConfig_8.lpszAutoConfigUrl);
    if ( pProxyConfig_8.lpszProxy )
      GlobalFree(pProxyConfig_8.lpszProxy);
    if ( pProxyConfig_8.lpszProxyBypass )
      GlobalFree(pProxyConfig_8.lpszProxyBypass);
  }
  LastError = 0;
LABEL_82:
  LeaveCriticalSection(v3);
  return LastError;
}

```

## disassembly

```asm
0x1803cab7c  mov     rax, rsp
0x1803cab7f  mov     [rax+10h], rbx
0x1803cab83  mov     [rax+18h], rsi
0x1803cab87  mov     [rax+20h], rdi
0x1803cab8b  push    rbp
0x1803cab8c  push    r12
0x1803cab8e  push    r13
0x1803cab90  push    r14
0x1803cab92  push    r15
0x1803cab94  lea     rbp, [rax-0D8h]
0x1803cab9b  sub     rsp, 1B0h
0x1803caba2  mov     rax, cs:__security_cookie
0x1803caba9  xor     rax, rsp
0x1803cabac  mov     [rbp+0D0h+var_30], rax
0x1803cabb3  mov     rdi, rcx
0x1803cabb6  xor     r13d, r13d
0x1803cabb9  mov     al, [rcx+448h]
0x1803cabbf  nop
0x1803cabc0  test    al, al
0x1803cabc2  jz      short loc_1803CABCB
0x1803cabc4  xor     eax, eax
0x1803cabc6  jmp     loc_1803CB102
0x1803cabcb  lea     rbx, [rcx+110h]
0x1803cabd2  mov     qword ptr [rsp+1D0h+pProxyConfig.fAutoDetect], rbx
0x1803cabd7  mov     rcx, rbx; lpCriticalSection
0x1803cabda  call    cs:__imp_EnterCriticalSection
0x1803cabe0  nop
0x1803cabe1  mov     al, [rdi+448h]
0x1803cabe7  nop
0x1803cabe8  test    al, al
0x1803cabea  jnz     loc_1803CB0F4
0x1803cabf0  xorps   xmm0, xmm0
0x1803cabf3  movups  xmmword ptr [rsp+1D0h+pProxyConfig.lpszAutoConfigUrl], xmm0
0x1803cabf8  movups  xmmword ptr [rsp+1D0h+pProxyConfig.lpszProxyBypass], xmm0
0x1803cabfd  mov     r15, r13
0x1803cac00  mov     r12, r13
0x1803cac03  mov     [rdi+461h], r13b
0x1803cac0a  movups  xmmword ptr [rsp+1D0h+var_170+8], xmm0
0x1803cac0f  mov     [rsp+1D0h+var_158], r13
0x1803cac14  mov     [rbp+0D0h+var_150], 7
0x1803cac1c  mov     word ptr [rsp+1D0h+var_170+8], r13w
0x1803cac22  movups  [rbp+0D0h+var_120], xmm0
0x1803cac26  mov     [rbp+0D0h+var_110], r13
0x1803cac2a  mov     [rbp+0D0h+var_108], r13
0x1803cac2e  mov     esi, 1
0x1803cac33  mov     r8d, esi
0x1803cac36  lea     rdx, dword_1804B6234
0x1803cac3d  lea     rcx, [rbp+0D0h+var_120]
0x1803cac41  call    sub_1800A3680
0x1803cac46  nop
0x1803cac47  lea     rcx, [rbp+0D0h+var_100]
0x1803cac4b  call    sub_1801C62E4
0x1803cac50  nop
0x1803cac51  lea     rdx, [rdi+170h]
0x1803cac58  mov     eax, [rdx+0E8h]
0x1803cac5e  test    eax, eax
0x1803cac60  jnz     short loc_1803CAC6F
0x1803cac62  call    sub_1803C5664
0x1803cac67  mov     r14d, eax
0x1803cac6a  jmp     loc_1803CAE53
0x1803cac6f  cmp     eax, 2
0x1803cac72  jnz     short loc_1803CAC7C
0x1803cac74  mov     r14d, esi
0x1803cac77  jmp     loc_1803CAE53
0x1803cac7c  cmp     eax, esi
0x1803cac7e  jnz     loc_1803CAD4E
0x1803cac84  call    sub_1803C5664
0x1803cac89  mov     r14d, eax
0x1803cac8c  cmp     eax, 4
0x1803cac8f  jz      loc_1803CAE53
0x1803cac95  mov     [rdi+461h], sil
0x1803cac9c  xorps   xmm0, xmm0
0x1803cac9f  xor     eax, eax
0x1803caca1  movups  xmmword ptr [rbp+0D0h+pProxyInfo.dwAccessType], xmm0
0x1803caca5  mov     [rbp+0D0h+pProxyInfo.lpszProxyBypass], rax
0x1803caca9  lea     rcx, [rbp+0D0h+pProxyInfo]; pProxyInfo
0x1803cacad  call    cs:WinHttpGetDefaultProxyConfiguration
0x1803cacb3  test    eax, eax
0x1803cacb5  jz      short loc_1803CACBC
0x1803cacb7  cmp     [rbp+0D0h+pProxyInfo.dwAccessType], esi
0x1803cacba  jnz     short loc_1803CAD27
0x1803cacbc  lea     rcx, [rsp+1D0h+pProxyConfig.lpszAutoConfigUrl]; pProxyConfig
0x1803cacc1  call    cs:WinHttpGetIEProxyConfigForCurrentUser
0x1803cacc7  test    eax, eax
0x1803cacc9  jz      short loc_1803CAD27
0x1803caccb  cmp     dword ptr [rsp+1D0h+pProxyConfig.lpszAutoConfigUrl], r13d
0x1803cacd0  jz      short loc_1803CACDB
0x1803cacd2  mov     [rdi+461h], sil
0x1803cacd9  jmp     short loc_1803CAD27
0x1803cacdb  mov     rdx, [rsp+1D0h+pProxyConfig.lpszProxy]
0x1803cace0  test    rdx, rdx
0x1803cace3  jz      short loc_1803CAD08
0x1803cace5  mov     [rdi+461h], sil
0x1803cacec  or      r8, 0FFFFFFFFFFFFFFFFh
0x1803cacf0  inc     r8
0x1803cacf3  cmp     [rdx+r8*2], r13w
0x1803cacf8  jnz     short loc_1803CACF0
0x1803cacfa  lea     rcx, [rdi+468h]
0x1803cad01  call    sub_1800B6DCC
0x1803cad06  jmp     short loc_1803CAD27
0x1803cad08  mov     rax, [rsp+1D0h+pProxyConfig.lpszProxyBypass]
0x1803cad0d  test    rax, rax
0x1803cad10  jz      short loc_1803CAD27
0x1803cad12  mov     r14d, 3
0x1803cad18  mov     r15, rax
0x1803cad1b  mov     rax, [rsp+1D0h+hMem]
0x1803cad20  test    rax, rax
0x1803cad23  cmovnz  r12, rax
0x1803cad27  mov     rcx, [rbp+0D0h+pProxyInfo.lpszProxy]; hMem
0x1803cad2b  test    rcx, rcx
0x1803cad2e  jz      short loc_1803CAD36
0x1803cad30  call    cs:GlobalFree
0x1803cad36  mov     rcx, [rbp+0D0h+pProxyInfo.lpszProxyBypass]; hMem
0x1803cad3a  test    rcx, rcx
0x1803cad3d  jz      loc_1803CAE53
0x1803cad43  call    cs:GlobalFree
0x1803cad49  jmp     loc_1803CAE53
0x1803cad4e  mov     r14d, 3
0x1803cad54  lea     rcx, [rbp+0D0h+var_120]
0x1803cad58  call    sub_1803B466C
0x1803cad5d  mov     r8, [rbp+0D0h+var_110]
0x1803cad61  test    r8, r8
0x1803cad64  jz      short loc_1803CADA5
0x1803cad66  lea     rcx, [rbp+0D0h+var_120]
0x1803cad6a  cmp     [rbp+0D0h+var_108], 7
0x1803cad6f  cmova   rcx, qword ptr [rbp+0D0h+var_120]
0x1803cad74  cmp     r8, rsi
0x1803cad77  jnz     short loc_1803CAD89
0x1803cad79  lea     rdx, dword_1804B6234
0x1803cad80  call    sub_1800B6ECC
0x1803cad85  test    eax, eax
0x1803cad87  jz      short loc_1803CADA5
0x1803cad89  cmp     [rbp+0D0h+var_40], r13d
0x1803cad90  jnz     short loc_1803CADA5
0x1803cad92  lea     r15, [rbp+0D0h+var_E0]
0x1803cad96  cmp     [rbp+0D0h+var_C8], 7
0x1803cad9b  cmova   r15, [rbp+0D0h+var_E0]
0x1803cada0  jmp     loc_1803CAE53
0x1803cada5  lea     rdx, [rbp+0D0h+var_E0]
0x1803cada9  cmp     [rbp+0D0h+var_C8], 7
0x1803cadae  cmova   rdx, [rbp+0D0h+var_E0]
0x1803cadb3  mov     r8, [rbp+0D0h+var_D0]
0x1803cadb7  lea     rcx, [rsp+1D0h+var_170+8]
0x1803cadbc  call    sub_1800B6DCC
0x1803cadc1  cmp     [rbp+0D0h+var_40], r13d
0x1803cadc8  jle     short loc_1803CAE43
0x1803cadca  mov     rcx, [rsp+1D0h+var_158]
0x1803cadcf  cmp     rcx, [rbp+0D0h+var_150]
0x1803cadd3  jnb     short loc_1803CADF7
0x1803cadd5  lea     rax, [rcx+1]
0x1803cadd9  mov     [rsp+1D0h+var_158], rax
0x1803cadde  lea     rax, [rsp+1D0h+var_170+8]
0x1803cade3  cmp     [rbp+0D0h+var_150], 7
0x1803cade8  cmova   rax, qword ptr [rsp+1D0h+var_170+8]
0x1803cadee  mov     dword ptr [rax+rcx*2], 3Ah ; ':'
0x1803cadf5  jmp     short loc_1803CAE0D
0x1803cadf7  mov     r9d, 3Ah ; ':'
0x1803cadfd  mov     r8b, r13b
0x1803cae00  mov     rdx, rsi
0x1803cae03  lea     rcx, [rsp+1D0h+var_170+8]
0x1803cae08  call    sub_180219AC0
0x1803cae0d  mov     edx, [rbp+0D0h+var_40]
0x1803cae13  lea     rcx, [rbp+0D0h+pProxyInfo]
0x1803cae17  call    sub_1802BCB34
0x1803cae1c  nop
0x1803cae1d  lea     rdx, [rbp+0D0h+pProxyInfo]
0x1803cae21  cmp     [rbp+0D0h+var_128], 7
0x1803cae26  cmova   rdx, qword ptr [rbp+0D0h+pProxyInfo.dwAccessType]
0x1803cae2b  mov     r8, [rbp+0D0h+pProxyInfo.lpszProxyBypass]
0x1803cae2f  lea     rcx, [rsp+1D0h+var_170+8]
0x1803cae34  call    sub_1800B6D50
0x1803cae39  nop
0x1803cae3a  lea     rcx, [rbp+0D0h+pProxyInfo]
0x1803cae3e  call    sub_1800A7750
0x1803cae43  lea     r15, [rsp+1D0h+var_170+8]
0x1803cae48  cmp     [rbp+0D0h+var_150], 7
0x1803cae4d  cmova   r15, qword ptr [rsp+1D0h+var_170+8]
0x1803cae53  mov     [rsp+1D0h+dwFlags], 10000000h; dwFlags
0x1803cae5b  mov     r9, r12; pszProxyBypassW
0x1803cae5e  mov     r8, r15; pszProxyW
0x1803cae61  mov     edx, r14d; dwAccessType
0x1803cae64  xor     ecx, ecx; pszAgentW
0x1803cae66  call    cs:WinHttpOpen
0x1803cae6c  mov     rcx, rax; hInternet
0x1803cae6f  mov     [rdi+450h], rax
0x1803cae76  test    rax, rax
0x1803cae79  jz      short loc_1803CAEB7
0x1803cae7b  mov     rax, 20C49BA5E353F7CFh
0x1803cae85  imul    qword ptr [rdi+2E8h]
0x1803cae8c  sar     rdx, 7
0x1803cae90  mov     rax, rdx
0x1803cae93  shr     rax, 3Fh
0x1803cae97  add     rdx, rax
0x1803cae9a  cmp     edx, esi
0x1803cae9c  cmovl   edx, esi; nResolveTimeout
0x1803cae9f  mov     [rsp+1D0h+dwFlags], edx; nReceiveTimeout
0x1803caea3  mov     r9d, edx; nSendTimeout
0x1803caea6  mov     r8d, edx; nConnectTimeout
0x1803caea9  call    cs:WinHttpSetTimeouts
0x1803caeaf  test    eax, eax
0x1803caeb1  jnz     loc_1803CAF43
0x1803caeb7  call    cs:GetLastError
0x1803caebd  mov     edi, eax
0x1803caebf  lea     rcx, [rbp+0D0h+var_60]
0x1803caec3  call    sub_1800A7750
0x1803caec8  lea     rcx, [rbp+0D0h+var_80]
0x1803caecc  call    sub_1800A7750
0x1803caed1  lea     rcx, [rbp+0D0h+var_A0]
0x1803caed5  call    sub_1800A7750
0x1803caeda  lea     rcx, [rbp+0D0h+var_C0]
0x1803caede  call    sub_1800A7750
0x1803caee3  lea     rcx, [rbp+0D0h+var_E0]
0x1803caee7  call    sub_1800A7750
0x1803caeec  lea     rcx, [rbp+0D0h+var_100]
0x1803caef0  call    sub_1800A7750
0x1803caef5  lea     rcx, [rbp+0D0h+var_120]
0x1803caef9  call    sub_1800A7750
0x1803caefe  nop
0x1803caeff  lea     rcx, [rsp+1D0h+var_170+8]
0x1803caf04  call    sub_1800A7750
0x1803caf09  nop
0x1803caf0a  mov     rcx, [rsp+1D0h+pProxyConfig.lpszProxy]; hMem
0x1803caf0f  test    rcx, rcx
0x1803caf12  jz      short loc_1803CAF1A
0x1803caf14  call    cs:GlobalFree
0x1803caf1a  mov     rcx, [rsp+1D0h+pProxyConfig.lpszProxyBypass]; hMem
0x1803caf1f  test    rcx, rcx
0x1803caf22  jz      short loc_1803CAF2A
0x1803caf24  call    cs:GlobalFree
0x1803caf2a  mov     rcx, [rsp+1D0h+hMem]; hMem
0x1803caf2f  test    rcx, rcx
0x1803caf32  jz      loc_1803CB0F7
0x1803caf38  call    cs:GlobalFree
0x1803caf3e  jmp     loc_1803CB0F7
0x1803caf43  cmp     [rdi+2E0h], r13b
0x1803caf4a  jz      short loc_1803CAF72
0x1803caf4c  mov     [rbp+0D0h+Buffer], esi
0x1803caf4f  mov     r9d, 4; dwBufferLength
0x1803caf55  lea     r8, [rbp+0D0h+Buffer]; lpBuffer
0x1803caf59  lea     edx, [r9+45h]; dwOption
0x1803caf5d  mov     rcx, [rdi+450h]; hInternet
0x1803caf64  call    cs:WinHttpSetOption
0x1803caf6a  test    eax, eax
0x1803caf6c  jz      loc_1803CAEB7
0x1803caf72  mov     dword ptr [rsp+1D0h+var_170], 0AA0h
0x1803caf7a  mov     r9d, 4; dwBufferLength
0x1803caf80  lea     r8, [rsp+1D0h+var_170]; lpBuffer
0x1803caf85  lea     edx, [r9+50h]; dwOption
0x1803caf89  mov     rcx, [rdi+450h]; hInternet
0x1803caf90  call    cs:WinHttpSetOption
0x1803caf96  test    eax, eax
0x1803caf98  jz      loc_1803CAEB7
0x1803caf9e  mov     rax, [rdi+450h]
0x1803cafa5  mov     rcx, [rdi+378h]
0x1803cafac  test    rcx, rcx
0x1803cafaf  jz      short loc_1803CAFC8
0x1803cafb1  mov     [rsp+1D0h+var_178], rax
0x1803cafb6  mov     rax, [rcx]
0x1803cafb9  lea     rdx, [rsp+1D0h+var_178]
0x1803cafbe  mov     rax, [rax+10h]
0x1803cafc2  call    cs:__guard_dispatch_icall_fptr
0x1803cafc8  xor     r9d, r9d; dwReserved
0x1803cafcb  mov     r8d, 97F4C30h; dwNotificationFlags
0x1803cafd1  lea     rdx, fnInternetCallback; lpfnInternetCallback
0x1803cafd8  mov     rcx, [rdi+450h]; hInternet
0x1803cafdf  call    cs:WinHttpSetStatusCallback
0x1803cafe5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803cafe9  jz      loc_1803CAEB7
0x1803cafef  mov     r8, [rdi+38h]
0x1803caff3  test    r8, r8
0x1803caff6  jz      short loc_1803CB03D
0x1803caff8  lea     rcx, [rdi+28h]
0x1803caffc  cmp     qword ptr [rdi+40h], 7
0x1803cb001  jbe     short loc_1803CB007
0x1803cb003  mov     rcx, [rdi+28h]
0x1803cb007  cmp     r8, rsi
0x1803cb00a  jnz     short loc_1803CB01C
0x1803cb00c  lea     rdx, dword_1804B6234
0x1803cb013  call    sub_1800B6ECC
0x1803cb018  test    eax, eax
0x1803cb01a  jz      short loc_1803CB03D
0x1803cb01c  cmp     [rdi+108h], r13d
0x1803cb023  jnz     short loc_1803CB03D
0x1803cb025  mov     al, [rdi+460h]
0x1803cb02b  neg     al
0x1803cb02d  sbb     r8d, r8d
0x1803cb030  and     r8d, 16Bh
0x1803cb037  add     r8d, 50h ; 'P'
0x1803cb03b  jmp     short loc_1803CB044
0x1803cb03d  mov     r8d, [rdi+108h]; nServerPort
0x1803cb044  lea     rdx, [rdi+68h]
0x1803cb048  cmp     qword ptr [rdx+18h], 7
0x1803cb04d  jbe     short loc_1803CB052
0x1803cb04f  mov     rdx, [rdx]; pswzServerName
0x1803cb052  xor     r9d, r9d; dwReserved
0x1803cb055  mov     rcx, [rdi+450h]; hSession
0x1803cb05c  call    cs:WinHttpConnect
0x1803cb062  mov     [rdi+458h], rax
0x1803cb069  test    rax, rax
0x1803cb06c  jz      loc_1803CAEB7
  ... truncated ...
```

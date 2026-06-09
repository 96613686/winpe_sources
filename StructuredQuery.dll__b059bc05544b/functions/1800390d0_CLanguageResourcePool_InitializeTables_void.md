# CLanguageResourcePool::_InitializeTables(void)

- ea: `0x1800390d0`
- end: `0x180039540`
- name: `?_InitializeTables@CLanguageResourcePool@@AEAAJXZ`
- size: `1136`
- prototype: `__int64 __fastcall(CLanguageResourcePool *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180038624`

## callees

- `0x180020250`
- `0x1800390d0`
- `0x180039548`
- `0x18005daf0`
- `0x18005db64`
- `0x18005e740`
- `0x1800849bc`
- `0x180084b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039302`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039356`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039302`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039356`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800391a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800391a5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003926d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003926d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003914e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800392ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003914e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800392ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039484`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180039112`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180039112`
- `SHCORE!__imp_GUIDFromStringW` at `0x18003938a`
- `SHCORE!__imp_GUIDFromStringW` at `0x18003938a`

## pseudocode

```c
__int64 __fastcall CLanguageResourcePool::_InitializeTables(CLanguageResourcePool *this)
{
  char v2; // al
  WCHAR *v3; // rdx
  LSTATUS v4; // eax
  signed int v5; // ebx
  DWORD *v6; // r12
  LSTATUS InfoKeyW; // eax
  unsigned __int64 v8; // rcx
  _QWORD *v9; // r13
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rdi
  DWORD v12; // r15d
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  bool v16; // sf
  LSTATUS v17; // eax
  bool v18; // sf
  __int64 v19; // r8
  unsigned __int8 *v20; // rdx
  int v21; // ecx
  int v22; // eax
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // r14
  _OWORD *v28; // rax
  _OWORD *v29; // rdi
  unsigned int v30; // r9d
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  __int128 v37; // [rsp+88h] [rbp-78h] BYREF
  BYTE v38[80]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF

  CLanguageResourcePool::_ClearTables(this);
  hKey = 0;
  phkResult = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled()
    || !GetSearchRegistryRedirect(L"WSearch", (struct CSearchRegistryRedirectHelper **)&phkResult)
    || (v16 = CSearchRegistryRedirectHelper::MapRegistryKeyPath(
                (CSearchRegistryRedirectHelper *)phkResult,
                L"SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language",
                Name,
                v30) < 0,
        v2 = 1,
        v16) )
  {
    v2 = 0;
  }
  v3 = Name;
  if ( !v2 )
    v3 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = (DWORD *)((char *)this + 32);
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)this + 8, 0, 0, 0, 0, 0, 0, 0);
    v5 = InfoKeyW;
    if ( InfoKeyW > 0 )
      v5 = (unsigned __int16)InfoKeyW | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_46;
    v8 = *v6;
    v9 = (_QWORD *)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    phkResult = 0;
    if ( is_mul_ok(v8, 0x14u) )
    {
      v5 = CTCoAllocPolicy::Alloc((void *)v8, 1u, 20 * v8, (void **)this + 5);
      if ( v5 < 0 )
      {
LABEL_46:
        RegCloseKey(hKey);
        return (unsigned int)v5;
      }
      v10 = *v6;
      v11 = (_QWORD *)((char *)this + 48);
      *((_QWORD *)this + 6) = 0;
      phkResult = 0;
      if ( is_mul_ok(v10, 0x68u) )
      {
        v5 = CTCoAllocPolicy::Alloc((void *)v10, 1u, 104 * v10, (void **)this + 6);
        if ( v5 >= 0 )
        {
          v12 = 0;
          while ( v12 < *v6 )
          {
            cchName = 255;
            v13 = RegEnumKeyExW(hKey, v12, Name, &cchName, 0, 0, 0, 0);
            v5 = v13;
            if ( v13 > 0 )
              v5 = (unsigned __int16)v13 | 0x80070000;
            if ( v5 >= 0 )
            {
              phkResult = 0;
              v14 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
              v5 = v14;
              if ( v14 > 0 )
                v5 = (unsigned __int16)v14 | 0x80070000;
              if ( v5 >= 0 )
              {
                Type = 0;
                *(_DWORD *)Data = 0;
                cbData = 4;
                v15 = RegQueryValueExW(phkResult, L"Locale", 0, &Type, Data, &cbData);
                v16 = v15 < 0;
                if ( v15 > 0 )
                  v16 = 1;
                if ( !v16 && Type == 4 )
                {
                  cbData = 78;
                  v17 = RegQueryValueExW(phkResult, L"WBreakerClass", 0, &Type, v38, &cbData);
                  v18 = v17 < 0;
                  if ( v17 > 0 )
                    v18 = 1;
                  if ( !v18 && Type == 1 )
                  {
                    v37 = 0;
                    if ( (unsigned int)GUIDFromStringW(v38, &v37) )
                    {
                      v19 = 16;
                      *(_DWORD *)(*v9 + 20LL * *((unsigned int *)this + 9)) = *(_DWORD *)Data;
                      v20 = (unsigned __int8 *)&v37;
                      *(_OWORD *)(*v9 + 20LL * (unsigned int)(*((_DWORD *)this + 9))++ + 4) = v37;
                      v21 = 0;
                      do
                      {
                        v22 = *v20++;
                        v21 = v22 + 101 * v21;
                        --v19;
                      }
                      while ( v19 );
                      v23 = (_QWORD *)(*v11 + 104LL * (314159269 * v21 % 0x3B9ACA07u % *v6));
                      v24 = *v23 - *(_QWORD *)&GUID_NULL.Data1;
                      if ( *v23 == *(_QWORD *)&GUID_NULL.Data1 )
                        v24 = v23[1] - *(_QWORD *)GUID_NULL.Data4;
                      if ( v24 )
                      {
                        while ( 1 )
                        {
                          v25 = *v23 - v37;
                          if ( *v23 == (_QWORD)v37 )
                            v25 = v23[1] - *((_QWORD *)&v37 + 1);
                          if ( !v25 )
                            break;
                          v26 = v23 + 12;
                          v23 = (_QWORD *)v23[12];
                          if ( !v23 )
                          {
                            v28 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
                            v29 = v28;
                            if ( v28 )
                            {
                              *v28 = v37;
                              memset_0(v28 + 1, 0, 0x50u);
                              *((_QWORD *)v29 + 12) = 0;
                              *v26 = v29;
                            }
                            else
                            {
                              v5 = -2147024882;
                            }
                            v11 = (_QWORD *)((char *)this + 48);
                            break;
                          }
                        }
                      }
                      else
                      {
                        *(_OWORD *)v23 = v37;
                      }
                    }
                  }
                }
                RegCloseKey(phkResult);
              }
              ++v12;
              if ( v5 >= 0 )
                continue;
            }
            CLanguageResourcePool::_ClearTables(this);
            goto LABEL_46;
          }
        }
        goto LABEL_46;
      }
    }
    v5 = -2147024362;
    goto LABEL_46;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800390d0  push    rbp
0x1800390d2  push    rbx
0x1800390d3  push    rsi
0x1800390d4  push    rdi
0x1800390d5  push    r12
0x1800390d7  push    r13
0x1800390d9  push    r14
0x1800390db  push    r15
0x1800390dd  lea     rbp, [rsp-218h]
0x1800390e5  sub     rsp, 318h
0x1800390ec  mov     rax, cs:__security_cookie
0x1800390f3  xor     rax, rsp
0x1800390f6  mov     [rbp+250h+var_50], rax
0x1800390fd  mov     rsi, rcx
0x180039100  call    ?_ClearTables@CLanguageResourcePool@@AEAAXXZ; CLanguageResourcePool::_ClearTables(void)
0x180039105  xor     r14d, r14d
0x180039108  mov     [rsp+350h+hKey], r14
0x18003910d  mov     [rsp+350h+var_2E8], r14
0x180039112  call    cs:__imp_RtlIsStateSeparationEnabled
0x180039118  lea     rbx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Con"...
0x18003911f  test    al, al
0x180039121  jnz     loc_1800394FD
0x180039127  mov     al, r14b
0x18003912a  test    al, al
0x18003912c  lea     rdx, [rbp+250h+Name]
0x180039130  lea     rax, [rsp+350h+hKey]
0x180039135  mov     r9d, 20019h; samDesired
0x18003913b  cmovz   rdx, rbx; lpSubKey
0x18003913f  mov     [rsp+350h+phkResult], rax; phkResult
0x180039144  xor     r8d, r8d; ulOptions
0x180039147  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003914e  call    cs:__imp_RegOpenKeyExW
0x180039154  mov     ebx, eax
0x180039156  mov     edi, 80070000h
0x18003915b  test    eax, eax
0x18003915d  jle     short loc_180039164
0x18003915f  movzx   ebx, ax
0x180039162  or      ebx, edi
0x180039164  test    ebx, ebx
0x180039166  js      loc_18003948A
0x18003916c  mov     rcx, [rsp+350h+hKey]; hKey
0x180039171  lea     r12, [rsi+20h]
0x180039175  mov     [rsp+350h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18003917a  xor     r9d, r9d; lpReserved
0x18003917d  mov     [rsp+350h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180039182  xor     r8d, r8d; lpcchClass
0x180039185  mov     [rsp+350h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18003918a  xor     edx, edx; lpClass
0x18003918c  mov     [rsp+350h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180039191  mov     [rsp+350h+lpcValues], r14; lpcValues
0x180039196  mov     [rsp+350h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18003919b  mov     [rsp+350h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800391a0  mov     [rsp+350h+phkResult], r12; lpcSubKeys
0x1800391a5  call    cs:__imp_RegQueryInfoKeyW
0x1800391ab  mov     ebx, eax
0x1800391ad  test    eax, eax
0x1800391af  jle     short loc_1800391B6
0x1800391b1  movzx   ebx, ax
0x1800391b4  or      ebx, edi
0x1800391b6  test    ebx, ebx
0x1800391b8  js      loc_18003947F
0x1800391be  mov     ecx, [r12]; void *
0x1800391c2  lea     r13, [rsi+28h]
0x1800391c6  mov     eax, 14h
0x1800391cb  mov     [r13+0], r14
0x1800391cf  mul     rcx
0x1800391d2  mov     [rsp+350h+var_2E8], r14
0x1800391d7  test    rdx, rdx
0x1800391da  jnz     loc_180039536
0x1800391e0  mov     r9, r13; void **
0x1800391e3  mov     r8, rax; unsigned __int64
0x1800391e6  mov     edx, 1; unsigned int
0x1800391eb  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800391f0  mov     ebx, eax
0x1800391f2  test    eax, eax
0x1800391f4  js      loc_18003947F
0x1800391fa  mov     ecx, [r12]; void *
0x1800391fe  lea     rdi, [rsi+30h]
0x180039202  mov     eax, 68h ; 'h'
0x180039207  mov     [rdi], r14
0x18003920a  mul     rcx
0x18003920d  mov     [rsp+350h+var_2E8], r14
0x180039212  test    rdx, rdx
0x180039215  jnz     loc_180039536
0x18003921b  mov     r9, rdi; void **
0x18003921e  mov     r8, rax; unsigned __int64
0x180039221  mov     edx, 1; unsigned int
0x180039226  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003922b  mov     ebx, eax
0x18003922d  test    eax, eax
0x18003922f  js      loc_18003947F
0x180039235  mov     r15d, r14d
0x180039238  cmp     r15d, [r12]
0x18003923c  jnb     loc_18003947F
0x180039242  mov     rcx, [rsp+350h+hKey]; hKey
0x180039247  lea     r9, [rbp+250h+cchName]; lpcchName
0x18003924b  mov     [rsp+350h+lpcValues], r14; lpftLastWriteTime
0x180039250  lea     r8, [rbp+250h+Name]; lpName
0x180039254  mov     [rsp+350h+lpcbMaxClassLen], r14; lpcchClass
0x180039259  mov     edx, r15d; dwIndex
0x18003925c  mov     [rsp+350h+lpcbMaxSubKeyLen], r14; lpClass
0x180039261  mov     [rsp+350h+phkResult], r14; lpReserved
0x180039266  mov     [rbp+250h+cchName], 0FFh
0x18003926d  call    cs:__imp_RegEnumKeyExW
0x180039273  mov     ebx, eax
0x180039275  test    eax, eax
0x180039277  jle     short loc_180039282
0x180039279  movzx   ebx, ax
0x18003927c  or      ebx, 80070000h
0x180039282  test    ebx, ebx
0x180039284  js      loc_180039477
0x18003928a  mov     rcx, [rsp+350h+hKey]; hKey
0x18003928f  lea     rax, [rsp+350h+var_2E8]
0x180039294  mov     r9d, 20019h; samDesired
0x18003929a  mov     [rsp+350h+phkResult], rax; phkResult
0x18003929f  xor     r8d, r8d; ulOptions
0x1800392a2  mov     [rsp+350h+var_2E8], r14
0x1800392a7  lea     rdx, [rbp+250h+Name]; lpSubKey
0x1800392ab  call    cs:__imp_RegOpenKeyExW
0x1800392b1  mov     ebx, eax
0x1800392b3  test    eax, eax
0x1800392b5  jle     short loc_1800392C0
0x1800392b7  movzx   ebx, ax
0x1800392ba  or      ebx, 80070000h
0x1800392c0  test    ebx, ebx
0x1800392c2  js      loc_18003946C
0x1800392c8  mov     rcx, [rsp+350h+var_2E8]; hKey
0x1800392cd  lea     rax, [rsp+350h+cbData]
0x1800392d2  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800392d7  lea     r9, [rsp+350h+Type]; lpType
0x1800392dc  lea     rax, [rsp+350h+Data]
0x1800392e1  mov     [rsp+350h+Type], r14d
0x1800392e6  xor     r8d, r8d; lpReserved
0x1800392e9  mov     [rsp+350h+phkResult], rax; lpData
0x1800392ee  lea     rdx, aLocale; "Locale"
0x1800392f5  mov     dword ptr [rsp+350h+Data], r14d
0x1800392fa  mov     [rsp+350h+cbData], 4
0x180039302  call    cs:__imp_RegQueryValueExW
0x180039308  test    eax, eax
0x18003930a  jle     short loc_180039316
0x18003930c  movzx   eax, ax
0x18003930f  or      eax, 80070000h
0x180039314  test    eax, eax
0x180039316  js      loc_180039461
0x18003931c  cmp     [rsp+350h+Type], 4
0x180039321  jnz     loc_180039461
0x180039327  mov     rcx, [rsp+350h+var_2E8]; hKey
0x18003932c  lea     rax, [rsp+350h+cbData]
0x180039331  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x180039336  lea     r9, [rsp+350h+Type]; lpType
0x18003933b  lea     rax, [rbp+250h+var_2B0]
0x18003933f  mov     [rsp+350h+cbData], 4Eh ; 'N'
0x180039347  xor     r8d, r8d; lpReserved
0x18003934a  mov     [rsp+350h+phkResult], rax; lpData
0x18003934f  lea     rdx, aWbreakerclass; "WBreakerClass"
0x180039356  call    cs:__imp_RegQueryValueExW
0x18003935c  test    eax, eax
0x18003935e  jle     short loc_18003936A
0x180039360  movzx   eax, ax
0x180039363  or      eax, 80070000h
0x180039368  test    eax, eax
0x18003936a  js      loc_180039461
0x180039370  cmp     [rsp+350h+Type], 1
0x180039375  jnz     loc_180039461
0x18003937b  xorps   xmm0, xmm0
0x18003937e  lea     rdx, [rbp+250h+var_2C8]
0x180039382  lea     rcx, [rbp+250h+var_2B0]
0x180039386  movups  [rbp+250h+var_2C8], xmm0
0x18003938a  call    cs:__imp_GUIDFromStringW
0x180039390  test    eax, eax
0x180039392  jz      loc_180039461
0x180039398  mov     eax, [rsi+24h]
0x18003939b  mov     r8d, 10h
0x1800393a1  mov     rcx, [r13+0]
0x1800393a5  lea     rdx, [rax+rax*4]
0x1800393a9  mov     eax, dword ptr [rsp+350h+Data]
0x1800393ad  mov     [rcx+rdx*4], eax
0x1800393b0  lea     rdx, [rbp+250h+var_2C8]
0x1800393b4  mov     eax, [rsi+24h]
0x1800393b7  movups  xmm0, [rbp+250h+var_2C8]
0x1800393bb  lea     rcx, [rax+rax*4]
0x1800393bf  mov     rax, [r13+0]
0x1800393c3  movdqu  xmmword ptr [rax+rcx*4+4], xmm0
0x1800393c9  inc     dword ptr [rsi+24h]
0x1800393cc  mov     ecx, r14d
0x1800393cf  movzx   eax, byte ptr [rdx]
0x1800393d2  inc     rdx
0x1800393d5  imul    ecx, 65h ; 'e'
0x1800393d8  add     ecx, eax
0x1800393da  sub     r8, 1
0x1800393de  jnz     short loc_1800393CF
0x1800393e0  imul    r8d, ecx, 12B9B0A5h
0x1800393e7  mov     eax, 12E0BE63h
0x1800393ec  mul     r8d
0x1800393ef  mov     ecx, r8d
0x1800393f2  sub     ecx, edx
0x1800393f4  shr     ecx, 1
0x1800393f6  add     ecx, edx
0x1800393f8  xor     edx, edx
0x1800393fa  shr     ecx, 1Dh
0x1800393fd  imul    ecx, 3B9ACA07h
0x180039403  sub     r8d, ecx
0x180039406  mov     eax, r8d
0x180039409  div     dword ptr [r12]
0x18003940d  mov     ecx, edx
0x18003940f  imul    rax, rcx, 68h ; 'h'
0x180039413  add     rax, [rdi]
0x180039416  mov     rcx, [rax]
0x180039419  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x180039420  jnz     short loc_18003942D
0x180039422  mov     rcx, [rax+8]
0x180039426  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x18003942d  test    rcx, rcx
0x180039430  jz      short loc_180039459
0x180039432  mov     rcx, [rax]
0x180039435  sub     rcx, qword ptr [rbp+250h+var_2C8]
0x180039439  jnz     short loc_180039443
0x18003943b  mov     rcx, [rax+8]
0x18003943f  sub     rcx, qword ptr [rbp+250h+var_2C8+8]
0x180039443  test    rcx, rcx
0x180039446  jz      short loc_180039461
0x180039448  lea     r14, [rax+60h]
0x18003944c  mov     rax, [r14]
0x18003944f  test    rax, rax
0x180039452  jz      short loc_1800394AF
0x180039454  xor     r14d, r14d
0x180039457  jmp     short loc_180039432
0x180039459  movups  xmm0, [rbp+250h+var_2C8]
0x18003945d  movdqu  xmmword ptr [rax], xmm0
0x180039461  mov     rcx, [rsp+350h+var_2E8]; hKey
0x180039466  call    cs:__imp_RegCloseKey
0x18003946c  inc     r15d
0x18003946f  test    ebx, ebx
0x180039471  jns     loc_180039238
0x180039477  mov     rcx, rsi; this
0x18003947a  call    ?_ClearTables@CLanguageResourcePool@@AEAAXXZ; CLanguageResourcePool::_ClearTables(void)
0x18003947f  mov     rcx, [rsp+350h+hKey]; hKey
0x180039484  call    cs:__imp_RegCloseKey
0x18003948a  mov     eax, ebx
0x18003948c  mov     rcx, [rbp+250h+var_50]
0x180039493  xor     rcx, rsp; StackCookie
0x180039496  call    __security_check_cookie
0x18003949b  add     rsp, 318h
0x1800394a2  pop     r15
0x1800394a4  pop     r14
0x1800394a6  pop     r13
0x1800394a8  pop     r12
0x1800394aa  pop     rdi
0x1800394ab  pop     rsi
0x1800394ac  pop     rbx
0x1800394ad  pop     rbp
0x1800394ae  retn
0x1800394af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800394b6  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800394bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800394c0  mov     rdi, rax
0x1800394c3  test    rax, rax
0x1800394c6  jz      short loc_1800394F6
0x1800394c8  movups  xmm0, [rbp+250h+var_2C8]
0x1800394cc  xor     edx, edx; Val
0x1800394ce  lea     rcx, [rax+10h]; void *
0x1800394d2  movdqu  xmmword ptr [rax], xmm0
0x1800394d6  lea     r8d, [rdx+50h]; Size
0x1800394da  call    memset_0
0x1800394df  mov     qword ptr [rdi+60h], 0
0x1800394e7  mov     [r14], rdi
0x1800394ea  xor     r14d, r14d
0x1800394ed  lea     rdi, [rsi+30h]
0x1800394f1  jmp     loc_180039461
0x1800394f6  mov     ebx, 8007000Eh
0x1800394fb  jmp     short loc_1800394EA
0x1800394fd  lea     rdx, [rsp+350h+var_2E8]; struct CSearchRegistryRedirectHelper **
0x180039502  lea     rcx, aWsearch; "WSearch"
0x180039509  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x18003950e  test    al, al
0x180039510  jz      loc_180039127
0x180039516  mov     rcx, [rsp+350h+var_2E8]; this
0x18003951b  lea     r8, [rbp+250h+Name]; wchar_t *
0x18003951f  mov     rdx, rbx; wchar_t *
0x180039522  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180039527  test    eax, eax
0x180039529  mov     al, 1
0x18003952b  jns     loc_18003912A
0x180039531  jmp     loc_180039127
0x180039536  mov     ebx, 80070216h
0x18003953b  jmp     loc_18003947F
```

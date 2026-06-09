# DeleteContextIfEmpty

- ea: `0x180107450`
- end: `0x1801077ec`
- name: `DeleteContextIfEmpty`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801077f4`

## callees

- `0x18000b9e0`
- `0x180011fe0`
- `0x180107450`
- `0x180107b50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801074ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010761d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180107716`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801074ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010761d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180107716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180107792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801077c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801075af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801076a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180107762`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801075af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801076a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180107762`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801075d5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801076ce`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180107774`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801075d5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801076ce`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180107774`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18010754e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180107654`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180107737`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18010754e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180107654`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180107737`

## pseudocode

```c
__int64 __fastcall DeleteContextIfEmpty(__int64 a1)
{
  bool v1; // zf
  HKEY v2; // r14
  signed int ContextKey; // ebx
  LSTATUS v5; // eax
  __int64 v6; // rbx
  HKEY v7; // r15
  __int64 v8; // rdi
  char IsStateSeparationEnabled; // al
  const WCHAR *v10; // r12
  const wchar_t *v11; // r9
  LSTATUS v12; // eax
  bool v13; // cc
  __int64 v14; // rbx
  _BOOL8 v15; // r15
  char v16; // al
  const wchar_t *v17; // r9
  LSTATUS v18; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22; // [rsp+70h] [rbp-90h] BYREF
  DWORD cValues; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  HKEY v25; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v1 = *(_DWORD *)a1 == 0;
  v25 = 0;
  hKey = 0;
  v2 = (HKEY)(!v1 - 0x7FFFFFFFLL);
  phkResult = 0;
  v22 = 0;
  cValues = 0;
  cSubKeys = 0;
  ContextKey = GetContextKey(a1, &hKey);
  if ( ContextKey >= 0 )
  {
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    if ( v5 )
    {
      if ( v5 <= 0 )
      {
LABEL_4:
        ContextKey = v5;
        goto LABEL_35;
      }
      ContextKey = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      RegCloseKey(hKey);
      hKey = 0;
      if ( cValues < 2 )
      {
        v6 = *(_QWORD *)(a1 + 16);
        v7 = (HKEY)((*(_DWORD *)a1 != 0) - 0x7FFFFFFFLL);
        v8 = *(_QWORD *)(a1 + 24);
        IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
        v10 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
        v11 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
        if ( !IsStateSeparationEnabled )
          v11 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
        ContextKey = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", v11, v6, v8);
        if ( ContextKey >= 0 )
        {
          v12 = RegOpenKeyExW(v7, SubKey, 0, 0x2011Fu, &phkResult);
          if ( v12 )
          {
            if ( v12 > 0 )
              ContextKey = (unsigned __int16)v12 | 0x80070000;
            else
              ContextKey = v12;
          }
        }
        if ( ContextKey >= 0 )
        {
          v5 = RegDeleteKeyW(phkResult, *(LPCWSTR *)(a1 + 32));
          v13 = v5 <= 0;
          if ( v5 )
            goto LABEL_33;
          v5 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          v13 = v5 <= 0;
          if ( v5 )
            goto LABEL_33;
          RegCloseKey(phkResult);
          phkResult = 0;
          if ( !cSubKeys )
          {
            v14 = *(_QWORD *)(a1 + 16);
            v15 = *(_DWORD *)a1 != 0;
            v16 = RtlIsStateSeparationEnabled();
            v17 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
            if ( !v16 )
              v17 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
            ContextKey = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v17, v14);
            if ( ContextKey >= 0 )
            {
              v18 = RegOpenKeyExW((HKEY)(v15 - 0x7FFFFFFF), SubKey, 0, 0x2011Fu, &v22);
              if ( v18 )
              {
                if ( v18 > 0 )
                  ContextKey = (unsigned __int16)v18 | 0x80070000;
                else
                  ContextKey = v18;
              }
            }
            if ( ContextKey >= 0 )
            {
              v5 = RegDeleteKeyW(v22, *(LPCWSTR *)(a1 + 24));
              v13 = v5 <= 0;
              if ( v5 )
                goto LABEL_33;
              v5 = RegQueryInfoKeyW(v22, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
              v13 = v5 <= 0;
              if ( v5 )
                goto LABEL_33;
              RegCloseKey(v22);
              v22 = 0;
              if ( !cSubKeys )
              {
                if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
                  v10 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
                v5 = RegOpenKeyExW(v2, v10, 0, 0x2011Fu, &v25);
                v13 = v5 <= 0;
                if ( v5 || (v5 = RegDeleteKeyW(v25, *(LPCWSTR *)(a1 + 16)), v13 = v5 <= 0, v5) )
                {
LABEL_33:
                  if ( v13 )
                    goto LABEL_4;
                  ContextKey = (unsigned __int16)v5 | 0x80070000;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  if ( v25 )
    RegCloseKey(v25);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v22 )
    RegCloseKey(v22);
  return (unsigned int)ContextKey;
}

```

## disassembly

```asm
0x180107450  push    rbp
0x180107452  push    rbx
0x180107453  push    rsi
0x180107454  push    rdi
0x180107455  push    r12
0x180107457  push    r13
0x180107459  push    r14
0x18010745b  push    r15
0x18010745d  lea     rbp, [rsp-1B8h]
0x180107465  sub     rsp, 2B8h
0x18010746c  mov     rax, cs:__security_cookie
0x180107473  xor     rax, rsp
0x180107476  mov     [rbp+1F0h+var_50], rax
0x18010747d  xor     r13d, r13d
0x180107480  lea     rdx, [rbp+1F0h+hKey]
0x180107484  cmp     [rcx], r13d
0x180107487  mov     r14d, r13d
0x18010748a  mov     rdi, 0FFFFFFFF80000001h
0x180107491  mov     [rbp+1F0h+var_268], r13
0x180107495  setnz   r14b
0x180107499  mov     [rbp+1F0h+hKey], r13
0x18010749d  add     r14, rdi
0x1801074a0  mov     [rsp+2F0h+phkResult], r13
0x1801074a5  mov     rsi, rcx
0x1801074a8  mov     [rsp+2F0h+var_280], r13
0x1801074ad  mov     [rsp+2F0h+cValues], r13d
0x1801074b2  mov     [rsp+2F0h+cSubKeys], r13d
0x1801074b7  call    GetContextKey
0x1801074bc  mov     ebx, eax
0x1801074be  test    eax, eax
0x1801074c0  js      loc_180107789
0x1801074c6  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1801074ca  lea     rax, [rsp+2F0h+cValues]
0x1801074cf  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1801074d4  xor     r9d, r9d; lpReserved
0x1801074d7  mov     [rsp+2F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1801074dc  xor     r8d, r8d; lpcchClass
0x1801074df  mov     [rsp+2F0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1801074e4  xor     edx, edx; lpClass
0x1801074e6  mov     [rsp+2F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1801074eb  mov     [rsp+2F0h+lpcValues], rax; lpcValues
0x1801074f0  mov     [rsp+2F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1801074f5  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1801074fa  mov     [rsp+2F0h+lpcSubKeys], r13; lpcSubKeys
0x1801074ff  call    cs:__imp_RegQueryInfoKeyW
0x180107505  test    eax, eax
0x180107507  jz      short loc_180107520
0x180107509  jg      short loc_180107512
0x18010750b  mov     ebx, eax
0x18010750d  jmp     loc_180107789
0x180107512  movzx   ebx, ax
0x180107515  or      ebx, 80070000h
0x18010751b  jmp     loc_180107789
0x180107520  mov     rcx, [rbp+1F0h+hKey]; hKey
0x180107524  call    cs:__imp_RegCloseKey
0x18010752a  cmp     [rsp+2F0h+cValues], 2
0x18010752f  mov     [rbp+1F0h+hKey], r13
0x180107533  jnb     loc_180107789
0x180107539  cmp     [rsi], r13d
0x18010753c  mov     r15, r13
0x18010753f  mov     rbx, [rsi+10h]
0x180107543  setnz   r15b
0x180107547  add     r15, rdi
0x18010754a  mov     rdi, [rsi+18h]
0x18010754e  call    cs:__imp_RtlIsStateSeparationEnabled
0x180107554  lea     rcx, aSoftwareMicros_22; "Software\\Microsoft\\EnterpriseResource"...
0x18010755b  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rdi
0x180107560  test    al, al
0x180107562  mov     [rsp+2F0h+lpcSubKeys], rbx
0x180107567  lea     r12, aOsdataSoftware_61; "OSData\\Software\\Microsoft\\Enterprise"...
0x18010756e  mov     edx, 104h; unsigned __int64
0x180107573  mov     r9, r12
0x180107576  lea     r8, aSSS; "%s\\%s\\%s"
0x18010757d  cmovz   r9, rcx
0x180107581  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180107585  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010758a  mov     ebx, eax
0x18010758c  mov     edi, 80070000h
0x180107591  test    eax, eax
0x180107593  js      short loc_1801075C4
0x180107595  lea     rax, [rsp+2F0h+phkResult]
0x18010759a  mov     r9d, 2011Fh; samDesired
0x1801075a0  xor     r8d, r8d; ulOptions
0x1801075a3  mov     [rsp+2F0h+lpcSubKeys], rax; phkResult
0x1801075a8  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1801075ac  mov     rcx, r15; hKey
0x1801075af  call    cs:__imp_RegOpenKeyExW
0x1801075b5  test    eax, eax
0x1801075b7  jz      short loc_1801075C4
0x1801075b9  jg      short loc_1801075BF
0x1801075bb  mov     ebx, eax
0x1801075bd  jmp     short loc_1801075C4
0x1801075bf  movzx   ebx, ax
0x1801075c2  or      ebx, edi
0x1801075c4  test    ebx, ebx
0x1801075c6  js      loc_180107789
0x1801075cc  mov     rdx, [rsi+20h]; lpSubKey
0x1801075d0  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x1801075d5  call    cs:__imp_RegDeleteKeyW
0x1801075db  test    eax, eax
0x1801075dd  jnz     loc_18010777E
0x1801075e3  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x1801075e8  lea     rax, [rsp+2F0h+cSubKeys]
0x1801075ed  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1801075f2  xor     r9d, r9d; lpReserved
0x1801075f5  mov     [rsp+2F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1801075fa  xor     r8d, r8d; lpcchClass
0x1801075fd  mov     [rsp+2F0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180107602  xor     edx, edx; lpClass
0x180107604  mov     [rsp+2F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180107609  mov     [rsp+2F0h+lpcValues], r13; lpcValues
0x18010760e  mov     [rsp+2F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180107613  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180107618  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x18010761d  call    cs:__imp_RegQueryInfoKeyW
0x180107623  test    eax, eax
0x180107625  jnz     loc_18010777E
0x18010762b  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180107630  call    cs:__imp_RegCloseKey
0x180107636  mov     [rsp+2F0h+phkResult], r13
0x18010763b  cmp     [rsp+2F0h+cSubKeys], r13d
0x180107640  jnz     loc_180107789
0x180107646  cmp     [rsi], r13d
0x180107649  mov     r15, r13
0x18010764c  mov     rbx, [rsi+10h]
0x180107650  setnz   r15b
0x180107654  call    cs:__imp_RtlIsStateSeparationEnabled
0x18010765a  mov     r9, r12
0x18010765d  mov     [rsp+2F0h+lpcSubKeys], rbx
0x180107662  test    al, al
0x180107664  lea     r8, aSS; "%s\\%s"
0x18010766b  lea     rax, aSoftwareMicros_22; "Software\\Microsoft\\EnterpriseResource"...
0x180107672  mov     edx, 104h; unsigned __int64
0x180107677  cmovz   r9, rax
0x18010767b  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18010767f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180107684  mov     ebx, eax
0x180107686  test    eax, eax
0x180107688  js      short loc_1801076BD
0x18010768a  lea     rax, [rsp+2F0h+var_280]
0x18010768f  mov     r9d, 2011Fh; samDesired
0x180107695  xor     r8d, r8d; ulOptions
0x180107698  mov     [rsp+2F0h+lpcSubKeys], rax; phkResult
0x18010769d  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1801076a1  lea     rcx, [r15-7FFFFFFFh]; hKey
0x1801076a8  call    cs:__imp_RegOpenKeyExW
0x1801076ae  test    eax, eax
0x1801076b0  jz      short loc_1801076BD
0x1801076b2  jg      short loc_1801076B8
0x1801076b4  mov     ebx, eax
0x1801076b6  jmp     short loc_1801076BD
0x1801076b8  movzx   ebx, ax
0x1801076bb  or      ebx, edi
0x1801076bd  test    ebx, ebx
0x1801076bf  js      loc_180107789
0x1801076c5  mov     rdx, [rsi+18h]; lpSubKey
0x1801076c9  mov     rcx, [rsp+2F0h+var_280]; hKey
0x1801076ce  call    cs:__imp_RegDeleteKeyW
0x1801076d4  test    eax, eax
0x1801076d6  jnz     loc_18010777E
0x1801076dc  mov     rcx, [rsp+2F0h+var_280]; hKey
0x1801076e1  lea     rax, [rsp+2F0h+cSubKeys]
0x1801076e6  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1801076eb  xor     r9d, r9d; lpReserved
0x1801076ee  mov     [rsp+2F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1801076f3  xor     r8d, r8d; lpcchClass
0x1801076f6  mov     [rsp+2F0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1801076fb  xor     edx, edx; lpClass
0x1801076fd  mov     [rsp+2F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180107702  mov     [rsp+2F0h+lpcValues], r13; lpcValues
0x180107707  mov     [rsp+2F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18010770c  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180107711  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x180107716  call    cs:__imp_RegQueryInfoKeyW
0x18010771c  test    eax, eax
0x18010771e  jnz     short loc_18010777E
0x180107720  mov     rcx, [rsp+2F0h+var_280]; hKey
0x180107725  call    cs:__imp_RegCloseKey
0x18010772b  mov     [rsp+2F0h+var_280], r13
0x180107730  cmp     [rsp+2F0h+cSubKeys], r13d
0x180107735  jnz     short loc_180107789
0x180107737  call    cs:__imp_RtlIsStateSeparationEnabled
0x18010773d  mov     r9d, 2011Fh; samDesired
0x180107743  mov     rcx, r14; hKey
0x180107746  test    al, al
0x180107748  lea     rax, aSoftwareMicros_22; "Software\\Microsoft\\EnterpriseResource"...
0x18010774f  cmovz   r12, rax
0x180107753  lea     rax, [rbp+1F0h+var_268]
0x180107757  mov     rdx, r12; lpSubKey
0x18010775a  mov     [rsp+2F0h+lpcSubKeys], rax; phkResult
0x18010775f  xor     r8d, r8d; ulOptions
0x180107762  call    cs:__imp_RegOpenKeyExW
0x180107768  test    eax, eax
0x18010776a  jnz     short loc_18010777E
0x18010776c  mov     rdx, [rsi+10h]; lpSubKey
0x180107770  mov     rcx, [rbp+1F0h+var_268]; hKey
0x180107774  call    cs:__imp_RegDeleteKeyW
0x18010777a  test    eax, eax
0x18010777c  jz      short loc_180107789
0x18010777e  jle     loc_18010750B
0x180107784  movzx   ebx, ax
0x180107787  or      ebx, edi
0x180107789  mov     rcx, [rbp+1F0h+var_268]; hKey
0x18010778d  test    rcx, rcx
0x180107790  jz      short loc_180107798
0x180107792  call    cs:__imp_RegCloseKey
0x180107798  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18010779c  test    rcx, rcx
0x18010779f  jz      short loc_1801077A7
0x1801077a1  call    cs:__imp_RegCloseKey
0x1801077a7  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x1801077ac  test    rcx, rcx
0x1801077af  jz      short loc_1801077B7
0x1801077b1  call    cs:__imp_RegCloseKey
0x1801077b7  mov     rcx, [rsp+2F0h+var_280]; hKey
0x1801077bc  test    rcx, rcx
0x1801077bf  jz      short loc_1801077C7
0x1801077c1  call    cs:__imp_RegCloseKey
0x1801077c7  mov     eax, ebx
0x1801077c9  mov     rcx, [rbp+1F0h+var_50]
0x1801077d0  xor     rcx, rsp; StackCookie
0x1801077d3  call    __security_check_cookie
0x1801077d8  add     rsp, 2B8h
0x1801077df  pop     r15
0x1801077e1  pop     r14
0x1801077e3  pop     r13
0x1801077e5  pop     r12
0x1801077e7  pop     rdi
0x1801077e8  pop     rsi
0x1801077e9  pop     rbx
0x1801077ea  pop     rbp
0x1801077eb  retn
```

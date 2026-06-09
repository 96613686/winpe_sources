# _lambda_f8c8c34b84b8557185e1f0d0c38e6c1b_::operator()

- ea: `0x180020d1c`
- end: `0x180021443`
- name: `_lambda_f8c8c34b84b8557185e1f0d0c38e6c1b_::operator()`
- size: `1831`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021a40`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000e064`
- `0x18000e428`
- `0x18000e504`
- `0x180020d1c`
- `0x180021644`
- `0x18003fa7c`
- `0x1800425fc`
- `0x1800426a8`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020ed2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020efc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002100a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800210b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800212d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800212f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021339`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020ed2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020efc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002100a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800210b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800212d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800212f5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180021339`
- `KERNEL32!GetLastError` at `0x180020e76`
- `KERNEL32!GetLastError` at `0x180020e76`
- `ntdll!RtlAllocateHeap` at `0x180021145`
- `ntdll!RtlAllocateHeap` at `0x180021145`
- `SHLWAPI!StrToIntExW` at `0x180020fb6`
- `SHLWAPI!StrToIntExW` at `0x180020fb6`
- `SHELL32!CommandLineToArgvW` at `0x180020e54`
- `SHELL32!CommandLineToArgvW` at `0x180020e54`

## string_xrefs

- `0x180020e89`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x180020d76`: `Commandline: %ws`
- `0x1800213f6`: `CommandLine is null/empty.`
- `0x180020ecb`: `-PluginExists`
- `0x180020d83`: `InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()`
- `0x180021403`: `InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()`
- `0x180020db2`: `InventoryMatchingPlugin `

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
LPCWSTR *__fastcall lambda_f8c8c34b84b8557185e1f0d0c38e6c1b_::operator()(LPCWSTR **a1)
{
  _WORD *v2; // rcx
  WCHAR *v3; // rbx
  __int64 v4; // rax
  unsigned int v5; // r9d
  int *v6; // rdx
  LPCWSTR *result; // rax
  LPCWSTR v8; // rbx
  int i; // r15d
  _WORD *v10; // r9
  LPCWSTR *v11; // rcx
  unsigned __int64 v12; // rdx
  char *v13; // r12
  __int64 v14; // rbx
  int v15; // ecx
  int v16; // r12d
  __int64 v17; // kr10_8
  int v18; // ecx
  unsigned __int64 j; // rbx
  __int64 v20; // r15
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  LPCWSTR *v23; // rdx
  LPCWSTR *v24; // rdx
  LPCWSTR *v25; // rdx
  __int64 v26; // r15
  __int64 v27; // r12
  __int64 v28; // r13
  unsigned int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // [rsp+20h] [rbp-B8h]
  int v32; // [rsp+30h] [rbp-A8h]
  __int64 v33; // [rsp+40h] [rbp-98h]
  __int64 v34; // [rsp+40h] [rbp-98h]
  _OWORD Src[2]; // [rsp+60h] [rbp-78h] BYREF
  _OWORD v36[2]; // [rsp+80h] [rbp-58h] BYREF

  v2 = **a1;
  if ( !v2 || !*v2 )
    return (LPCWSTR *)AslLogCallPrintf(
                        1,
                        "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                        364,
                        "CommandLine is null/empty.");
  AslLogCallPrintf(
    3,
    "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
    368,
    "Commandline: %ws",
    v2);
  v3 = (WCHAR *)**a1;
  memset(Src, 0, sizeof(Src));
  std::wstring::_Construct<1,unsigned short const *>(Src, L"InventoryMatchingPlugin ", 24);
  v4 = std::wstring::append(Src, v3);
  v36[0] = *(_OWORD *)v4;
  v36[1] = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 7;
  *(_WORD *)v4 = 0;
  std::wstring::operator=(a1[1], v36);
  std::wstring::~wstring(v36);
  std::wstring::~wstring(Src);
  v6 = (int *)a1[1];
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(int **)v6;
  result = (LPCWSTR *)AppCompatUtility::CheckCacheMatchingPlugin(
                        (AppCompatUtility *)*a1[2],
                        v6,
                        (const unsigned __int16 *)*(unsigned int *)a1[3],
                        v5);
  if ( !(_DWORD)result )
  {
    *a1[4] = (LPCWSTR)CommandLineToArgvW(**a1, (int *)a1[5]);
    if ( !*a1[4] )
    {
      v8 = **a1;
      v32 = *(_DWORD *)a1[5];
      LODWORD(v31) = GetLastError();
      return (LPCWSTR *)AslLogCallPrintf(
                          1,
                          "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                          388,
                          "CommandLineToArgvW failed %d, %ws, numArgs=%d",
                          v31,
                          v8,
                          v32);
    }
    for ( i = 0; ; i += 2 )
    {
      if ( i >= *(_DWORD *)a1[5] )
      {
LABEL_52:
        v23 = a1[6];
        if ( !v23[2] || !a1[9][2] || !*a1[10] )
          return (LPCWSTR *)AslLogCallPrintf(
                              1,
                              "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                              494,
                              "Missing parameters. -Inventory, -AssetType and -Conditions are required.");
        if ( (unsigned __int64)v23[3] > 7 )
          v23 = (LPCWSTR *)*v23;
        if ( !(unsigned int)_o__wcsicmp(L"App", v23) )
          goto LABEL_73;
        v24 = a1[6];
        if ( (unsigned __int64)v24[3] > 7 )
          v24 = (LPCWSTR *)*v24;
        if ( (unsigned int)_o__wcsicmp(L"Device", v24) )
          return (LPCWSTR *)AslLogCallPrintf(
                              1,
                              "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                              499,
                              "Invalid Inventory. Must be 'App' or 'Device'.");
LABEL_73:
        if ( !*(_DWORD *)a1[8] )
        {
          v25 = a1[6];
          if ( (unsigned __int64)v25[3] > 7 )
            v25 = (LPCWSTR *)*v25;
          if ( !(unsigned int)_o__wcsicmp(L"Device", v25) )
            *(_DWORD *)a1[7] = 3;
        }
        v26 = (__int64)*a1[10];
        v27 = (__int64)*a1[11];
        v28 = std::wstring::wstring(v36, a1[9]);
        v29 = *(_DWORD *)a1[7];
        v30 = std::wstring::wstring(Src, a1[6]);
        *(_DWORD *)a1[12] = GetInventoryMatch(*a1[2], v30, v29, v28, v27, v26);
        result = a1[12];
        if ( *(_DWORD *)result )
          return (LPCWSTR *)AslLogCallPrintf(
                              1,
                              "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                              512,
                              "Error trying to get Inventory Match [0x%x].",
                              *(_DWORD *)result);
        return result;
      }
      if ( !(unsigned int)_o__wcsicmp(L"-PluginExists", *(_QWORD *)&(*a1[4])[4 * i]) )
      {
        result = a1[2];
        *(_DWORD *)*result = 1;
        return result;
      }
      if ( !(unsigned int)_o__wcsicmp(L"-Inventory", *(_QWORD *)&(*a1[4])[4 * i]) )
        break;
      if ( (unsigned int)_o__wcsicmp(L"-Flags", *(_QWORD *)&(*a1[4])[4 * i]) )
      {
        if ( (unsigned int)_o__wcsicmp(L"-AssetType", *(_QWORD *)&(*a1[4])[4 * i]) )
        {
          if ( (unsigned int)_o__wcsicmp(L"-Conditions", *(_QWORD *)&(*a1[4])[4 * i]) )
            return (LPCWSTR *)AslLogCallPrintf(
                                1,
                                "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                487,
                                "Unexpected parameter '%ls'.",
                                *(const wchar_t **)&(*a1[4])[4 * i]);
          v15 = *(_DWORD *)a1[5];
          v16 = i + 1;
          if ( i + 1 == v15 )
            return (LPCWSTR *)AslLogCallPrintf(
                                1,
                                "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                441,
                                "Incorrect number of parameters. Missing value for Conditions.");
          v17 = v15 + ~i;
          v18 = (v15 + ~i) / 4;
          if ( (((BYTE4(v17) & 3) + (_DWORD)v17) & 3) != (BYTE4(v17) & 3) )
            return (LPCWSTR *)AslLogCallPrintf(
                                1,
                                "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                446,
                                "Incorrect number of parameters. -Conditions values must be a multiple of 4 and be always at last.");
          *a1[10] = (LPCWSTR)v18;
          *a1[11] = (LPCWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 32LL * (_QWORD)*a1[10]);
          if ( !*a1[11] )
            return (LPCWSTR *)AslLogCallPrintf(
                                1,
                                "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                454,
                                "Failed to allocate memory for Conditions.");
          for ( j = 0; j < (unsigned __int64)*a1[10]; ++j )
          {
            v20 = 32 * j;
            *(_QWORD *)&(*a1[11])[(unsigned __int64)v20 / 2] = *(_QWORD *)&(*a1[4])[4 * v16];
            v21 = *a1[4];
            *(_QWORD *)&(*a1[11])[(unsigned __int64)v20 / 2 + 4] = *(_QWORD *)&v21[4 * v16 + 4];
            v33 = (__int64)*a1[11];
            if ( !AppCompatUtility::IsValidVariableType(*(wchar_t **)(v33 + 32 * j + 8), v21) )
              return (LPCWSTR *)AslLogCallPrintf(
                                  1,
                                  "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                  467,
                                  "Incorrect Type for Condition %zu. Must be 'int', 'string', 'double' or 'version'.",
                                  j);
            *(_QWORD *)(v33 + v20 + 16) = *(_QWORD *)&(*a1[4])[4 * v16 + 8];
            v34 = (__int64)*a1[11];
            if ( !AppCompatUtility::IsValidComparisonOperation(*(wchar_t **)(v34 + v20 + 16), v22) )
              return (LPCWSTR *)AslLogCallPrintf(
                                  1,
                                  "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                                  474,
                                  "Incorrect Operator for Condition %zu. Must be 'eq', 'ne', 'gt', 'gte', 'lt' or 'lte'.",
                                  j);
            *(_QWORD *)(v34 + v20 + 24) = *(_QWORD *)&(*a1[4])[4 * v16 + 12];
            v16 += 4;
          }
          goto LABEL_52;
        }
        if ( i + 1 == *(_DWORD *)a1[5] )
          return (LPCWSTR *)AslLogCallPrintf(
                              1,
                              "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                              430,
                              "Incorrect number of parameters. Missing value for AssetType.");
        v10 = *(_WORD **)&(*a1[4])[4 * i + 4];
        v11 = a1[9];
        v12 = -1;
        do
          ++v12;
        while ( v10[v12] );
        if ( v12 > (unsigned __int64)v11[3] )
        {
LABEL_35:
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v11);
          continue;
        }
        goto LABEL_31;
      }
      if ( i + 1 == *(_DWORD *)a1[5] )
        return (LPCWSTR *)AslLogCallPrintf(
                            1,
                            "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                            413,
                            "Incorrect number of parameters. Missing value for Flags.");
      if ( !StrToIntExW(*(PCWSTR *)&(*a1[4])[4 * i + 4], 1, (int *)a1[7]) )
        return (LPCWSTR *)AslLogCallPrintf(
                            1,
                            "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                            419,
                            "Failed to convert Flags from string to dword: '%ls'.",
                            *(const wchar_t **)&(*a1[4])[4 * i + 4]);
      *(_DWORD *)a1[8] = 1;
LABEL_36:
      ;
    }
    if ( i + 1 == *(_DWORD *)a1[5] )
      return (LPCWSTR *)AslLogCallPrintf(
                          1,
                          "InventoryMatchingPlugin::<lambda_f8c8c34b84b8557185e1f0d0c38e6c1b>::operator ()",
                          402,
                          "Incorrect number of parameters. Missing value for Inventory.");
    v10 = *(_WORD **)&(*a1[4])[4 * i + 4];
    v11 = a1[6];
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    if ( v12 > (unsigned __int64)v11[3] )
      goto LABEL_35;
LABEL_31:
    if ( (unsigned __int64)v11[3] <= 7 )
      v13 = (char *)v11;
    else
      v13 = (char *)*v11;
    v11[2] = (LPCWSTR)v12;
    v14 = 2 * v12;
    memmove_0(v13, v10, 2 * v12);
    *(_WORD *)&v13[v14] = 0;
    goto LABEL_36;
  }
  return result;
}

```

## disassembly

```asm
0x180020d1c  mov     rax, rsp
0x180020d1f  push    rdi
0x180020d20  push    r12
0x180020d22  push    r13
0x180020d24  push    r14
0x180020d26  push    r15
0x180020d28  sub     rsp, 0B0h
0x180020d2f  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFFFFFFEh
0x180020d38  mov     [rax+10h], rbx
0x180020d3c  mov     [rax+18h], rsi
0x180020d40  mov     rax, cs:__security_cookie
0x180020d47  xor     rax, rsp
0x180020d4a  mov     [rsp+0D8h+var_38], rax
0x180020d52  mov     rsi, rcx
0x180020d55  xor     r13d, r13d
0x180020d58  mov     rax, [rcx]
0x180020d5b  mov     rcx, [rax]
0x180020d5e  test    rcx, rcx
0x180020d61  jz      loc_1800213F6
0x180020d67  cmp     r13w, [rcx]
0x180020d6b  jz      loc_1800213F6
0x180020d71  mov     [rsp+0D8h+var_B8], rcx
0x180020d76  lea     r9, aCommandlineWs; "Commandline: %ws"
0x180020d7d  mov     r8d, 170h
0x180020d83  lea     r14, aInventorymatch_3; "InventoryMatchingPlugin::<lambda_f8c8c3"...
0x180020d8a  mov     rdx, r14
0x180020d8d  lea     ecx, [r13+3]
0x180020d91  call    AslLogCallPrintf
0x180020d96  nop
0x180020d97  mov     rax, [rsi]
0x180020d9a  mov     rbx, [rax]
0x180020d9d  xorps   xmm0, xmm0
0x180020da0  movups  [rsp+0D8h+Src], xmm0
0x180020da5  xorps   xmm1, xmm1
0x180020da8  movdqu  [rsp+0D8h+var_68], xmm1
0x180020dae  lea     r8d, [r13+18h]
0x180020db2  lea     rdx, aInventorymatch_1; "InventoryMatchingPlugin "
0x180020db9  lea     rcx, [rsp+0D8h+Src]
0x180020dbe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180020dc3  nop
0x180020dc4  mov     rdx, rbx; void *
0x180020dc7  lea     rcx, [rsp+0D8h+Src]; Src
0x180020dcc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180020dd1  movups  xmm0, xmmword ptr [rax]
0x180020dd4  movups  [rsp+0D8h+var_58], xmm0
0x180020ddc  movups  xmm1, xmmword ptr [rax+10h]
0x180020de0  movups  [rsp+0D8h+var_48], xmm1
0x180020de8  mov     [rax+10h], r13
0x180020dec  mov     qword ptr [rax+18h], 7
0x180020df4  mov     [rax], r13w
0x180020df8  lea     rdx, [rsp+0D8h+var_58]
0x180020e00  mov     rcx, [rsi+8]
0x180020e04  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020e09  lea     rcx, [rsp+0D8h+var_58]; void *
0x180020e11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020e16  nop
0x180020e17  lea     rcx, [rsp+0D8h+Src]; void *
0x180020e1c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020e21  mov     rax, [rsi+18h]
0x180020e25  mov     rdx, [rsi+8]
0x180020e29  cmp     qword ptr [rdx+18h], 7
0x180020e2e  jbe     short loc_180020E33
0x180020e30  mov     rdx, [rdx]; int *
0x180020e33  mov     rcx, [rsi+10h]
0x180020e37  mov     r8d, [rax]; unsigned __int16 *
0x180020e3a  mov     rcx, [rcx]; this
0x180020e3d  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x180020e42  test    eax, eax
0x180020e44  jnz     loc_180021415
0x180020e4a  mov     rcx, [rsi]
0x180020e4d  mov     rdx, [rsi+28h]; pNumArgs
0x180020e51  mov     rcx, [rcx]; lpCmdLine
0x180020e54  call    cs:__imp_CommandLineToArgvW
0x180020e5a  mov     rcx, [rsi+20h]
0x180020e5e  mov     [rcx], rax
0x180020e61  mov     rax, [rsi+20h]
0x180020e65  cmp     [rax], r13
0x180020e68  jnz     short loc_180020EA8
0x180020e6a  mov     rax, [rsi+28h]
0x180020e6e  mov     edi, [rax]
0x180020e70  mov     rax, [rsi]
0x180020e73  mov     rbx, [rax]
0x180020e76  call    cs:__imp_GetLastError
0x180020e7c  mov     [rsp+0D8h+var_A8], edi
0x180020e80  mov     [rsp+0D8h+var_B0], rbx
0x180020e85  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180020e89  lea     r9, aCommandlinetoa_0; "CommandLineToArgvW failed %d, %ws, numA"...
0x180020e90  mov     r8d, 184h
0x180020e96  mov     rdx, r14
0x180020e99  mov     ecx, 1
0x180020e9e  call    AslLogCallPrintf
0x180020ea3  jmp     loc_180021415
0x180020ea8  mov     r15d, r13d
0x180020eab  mov     edi, 1
0x180020eb0  mov     rax, [rsi+28h]
0x180020eb4  cmp     r15d, [rax]
0x180020eb7  jge     loc_18002129C
0x180020ebd  movsxd  rbx, r15d
0x180020ec0  mov     rax, [rsi+20h]
0x180020ec4  mov     rdx, [rax]
0x180020ec7  mov     rdx, [rdx+rbx*8]
0x180020ecb  lea     rcx, aPluginexists; "-PluginExists"
0x180020ed2  call    cs:__imp__o__wcsicmp
0x180020ed8  test    eax, eax
0x180020eda  jnz     short loc_180020EEA
0x180020edc  mov     rax, [rsi+10h]
0x180020ee0  mov     rcx, [rax]
0x180020ee3  mov     [rcx], edi
0x180020ee5  jmp     loc_180021415
0x180020eea  mov     rax, [rsi+20h]
0x180020eee  mov     rdx, [rax]
0x180020ef1  mov     rdx, [rdx+rbx*8]
0x180020ef5  lea     rcx, aInventory; "-Inventory"
0x180020efc  call    cs:__imp__o__wcsicmp
0x180020f02  test    eax, eax
0x180020f04  jnz     short loc_180020F60
0x180020f06  lea     ecx, [r15+1]
0x180020f0a  mov     rax, [rsi+28h]
0x180020f0e  cmp     ecx, [rax]
0x180020f10  jnz     short loc_180020F2E
0x180020f12  lea     r9, aIncorrectNumbe_2; "Incorrect number of parameters. Missing"...
0x180020f19  mov     r8d, 192h
0x180020f1f  mov     rdx, r14
0x180020f22  mov     ecx, edi
0x180020f24  call    AslLogCallPrintf
0x180020f29  jmp     loc_180021415
0x180020f2e  mov     rax, [rsi+20h]
0x180020f32  mov     rcx, [rax]
0x180020f35  mov     r9, [rcx+rbx*8+8]
0x180020f3a  mov     rcx, [rsi+30h]
0x180020f3e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020f42  inc     rdx
0x180020f45  cmp     [r9+rdx*2], r13w
0x180020f4a  jnz     short loc_180020F42
0x180020f4c  cmp     rdx, [rcx+18h]
0x180020f50  jbe     loc_180021064
0x180020f56  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180020f5b  jmp     loc_180021095
0x180020f60  mov     rax, [rsi+20h]
0x180020f64  mov     rdx, [rax]
0x180020f67  mov     rdx, [rdx+rbx*8]
0x180020f6b  lea     rcx, aFlags; "-Flags"
0x180020f72  call    cs:__imp__o__wcsicmp
0x180020f78  test    eax, eax
0x180020f7a  jnz     short loc_180020FF8
0x180020f7c  lea     ecx, [r15+1]
0x180020f80  mov     rax, [rsi+28h]
0x180020f84  cmp     ecx, [rax]
0x180020f86  jnz     short loc_180020FA4
0x180020f88  lea     r9, aIncorrectNumbe_6; "Incorrect number of parameters. Missing"...
0x180020f8f  mov     r8d, 19Dh
0x180020f95  mov     rdx, r14
0x180020f98  mov     ecx, edi
0x180020f9a  call    AslLogCallPrintf
0x180020f9f  jmp     loc_180021415
0x180020fa4  mov     rax, [rsi+20h]
0x180020fa8  mov     rcx, [rax]
0x180020fab  mov     r8, [rsi+38h]; piRet
0x180020faf  mov     edx, edi; dwFlags
0x180020fb1  mov     rcx, [rcx+rbx*8+8]; pszString
0x180020fb6  call    cs:__imp_StrToIntExW
0x180020fbc  test    eax, eax
0x180020fbe  jnz     short loc_180020FED
0x180020fc0  mov     rax, [rsi+20h]
0x180020fc4  mov     rcx, [rax]
0x180020fc7  mov     rax, [rcx+rbx*8+8]
0x180020fcc  mov     [rsp+0D8h+var_B8], rax
0x180020fd1  lea     r9, aFailedToConver_17; "Failed to convert Flags from string to "...
0x180020fd8  mov     r8d, 1A3h
0x180020fde  mov     rdx, r14
0x180020fe1  mov     ecx, edi
0x180020fe3  call    AslLogCallPrintf
0x180020fe8  jmp     loc_180021415
0x180020fed  mov     rax, [rsi+40h]
0x180020ff1  mov     [rax], edi
0x180020ff3  jmp     loc_180021095
0x180020ff8  mov     rax, [rsi+20h]
0x180020ffc  mov     rdx, [rax]
0x180020fff  mov     rdx, [rdx+rbx*8]
0x180021003  lea     rcx, aAssettype; "-AssetType"
0x18002100a  call    cs:__imp__o__wcsicmp
0x180021010  test    eax, eax
0x180021012  jnz     loc_18002109E
0x180021018  lea     ecx, [r15+1]
0x18002101c  mov     rax, [rsi+28h]
0x180021020  cmp     ecx, [rax]
0x180021022  jnz     short loc_180021040
0x180021024  lea     r9, aIncorrectNumbe_5; "Incorrect number of parameters. Missing"...
0x18002102b  mov     r8d, 1AEh
0x180021031  mov     rdx, r14
0x180021034  mov     ecx, edi
0x180021036  call    AslLogCallPrintf
0x18002103b  jmp     loc_180021415
0x180021040  mov     rax, [rsi+20h]
0x180021044  mov     rcx, [rax]
0x180021047  mov     r9, [rcx+rbx*8+8]
0x18002104c  mov     rcx, [rsi+48h]
0x180021050  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180021054  inc     rdx
0x180021057  cmp     [r9+rdx*2], r13w
0x18002105c  jnz     short loc_180021054
0x18002105e  cmp     rdx, [rcx+18h]
0x180021062  ja      short loc_180021090
0x180021064  cmp     qword ptr [rcx+18h], 7
0x180021069  jbe     short loc_180021070
0x18002106b  mov     r12, [rcx]
0x18002106e  jmp     short loc_180021073
0x180021070  mov     r12, rcx
0x180021073  mov     [rcx+10h], rdx
0x180021077  lea     rbx, [rdx+rdx]
0x18002107b  mov     r8, rbx; Size
0x18002107e  mov     rdx, r9; Src
0x180021081  mov     rcx, r12; void *
0x180021084  call    memmove_0
0x180021089  mov     [r12+rbx], r13w
0x18002108e  jmp     short loc_180021095
0x180021090  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180021095  add     r15d, 2
0x180021099  jmp     loc_180020EB0
0x18002109e  mov     rax, [rsi+20h]
0x1800210a2  mov     rdx, [rax]
0x1800210a5  mov     rdx, [rdx+rbx*8]
0x1800210a9  lea     rcx, aConditions; "-Conditions"
0x1800210b0  call    cs:__imp__o__wcsicmp
0x1800210b6  test    eax, eax
0x1800210b8  jnz     loc_18002126D
0x1800210be  mov     rax, [rsi+28h]
0x1800210c2  mov     ecx, [rax]
0x1800210c4  lea     r12d, [r15+1]
0x1800210c8  cmp     r12d, ecx
0x1800210cb  jnz     short loc_1800210E9
0x1800210cd  lea     r9, aIncorrectNumbe_8; "Incorrect number of parameters. Missing"...
0x1800210d4  mov     r8d, 1B9h
0x1800210da  mov     rdx, r14
0x1800210dd  mov     ecx, edi
0x1800210df  call    AslLogCallPrintf
0x1800210e4  jmp     loc_180021415
0x1800210e9  not     r15d
0x1800210ec  lea     eax, [rcx+r15]
0x1800210f0  cdq
0x1800210f1  and     edx, 3
0x1800210f4  add     eax, edx
0x1800210f6  mov     ecx, eax
0x1800210f8  and     eax, 3
0x1800210fb  sar     ecx, 2
0x1800210fe  cmp     eax, edx
0x180021100  jz      short loc_18002111E
0x180021102  lea     r9, aIncorrectNumbe_4; "Incorrect number of parameters. -Condit"...
0x180021109  mov     r8d, 1BEh
0x18002110f  mov     rdx, r14
0x180021112  mov     ecx, edi
0x180021114  call    AslLogCallPrintf
0x180021119  jmp     loc_180021415
0x18002111e  movsxd  rcx, ecx
0x180021121  mov     rax, [rsi+50h]
0x180021125  mov     [rax], rcx
0x180021128  mov     rax, [rsi+50h]
0x18002112c  mov     r8, [rax]
0x18002112f  shl     r8, 5; Size
0x180021133  mov     rcx, gs:60h
0x18002113c  mov     edx, 8; Flags
0x180021141  mov     rcx, [rcx+30h]; HeapHandle
0x180021145  call    cs:__imp_RtlAllocateHeap
0x18002114b  mov     rcx, [rsi+58h]
0x18002114f  mov     [rcx], rax
0x180021152  mov     rax, [rsi+58h]
0x180021156  cmp     [rax], r13
0x180021159  jnz     short loc_180021177
0x18002115b  lea     r9, aFailedToAlloca; "Failed to allocate memory for Condition"...
0x180021162  mov     r8d, 1C6h
0x180021168  mov     rdx, r14
0x18002116b  mov     ecx, edi
0x18002116d  call    AslLogCallPrintf
0x180021172  jmp     loc_180021415
0x180021177  mov     rbx, r13
0x18002117a  mov     rax, [rsi+50h]
0x18002117e  cmp     rbx, [rax]
0x180021181  jnb     loc_180021299
0x180021187  movsxd  r13, r12d
0x18002118a  mov     r15, rbx
0x18002118d  shl     r15, 5
0x180021191  mov     rax, [rsi+20h]
0x180021195  mov     rdx, [rax]
0x180021198  mov     rax, [rsi+58h]
0x18002119c  mov     rcx, [rax]
0x18002119f  mov     rax, [rdx+r13*8]
0x1800211a3  mov     [r15+rcx], rax
0x1800211a7  mov     rax, [rsi+20h]
0x1800211ab  mov     rdx, [rax]; unsigned __int16 *
0x1800211ae  mov     rax, [rsi+58h]
0x1800211b2  mov     rcx, [rax]
0x1800211b5  mov     rax, [rdx+r13*8+8]
0x1800211ba  mov     [rcx+r15+8], rax
0x1800211bf  mov     rax, [rsi+58h]
0x1800211c3  mov     rax, [rax]
0x1800211c6  mov     [rsp+0D8h+var_98], rax
0x1800211cb  mov     rcx, [rax+r15+8]; String1
0x1800211d0  call    ?IsValidVariableType@AppCompatUtility@@YA_NPEBG@Z; AppCompatUtility::IsValidVariableType(ushort const *)
0x1800211d5  test    al, al
0x1800211d7  jnz     short loc_1800211FA
  ... truncated ...
```

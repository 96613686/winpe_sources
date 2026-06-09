# Throttler::ProcessOccurrence(ushort const *)

- ea: `0x180006530`
- end: `0x18000682a`
- name: `?ProcessOccurrence@Throttler@@QEAA?AW4ThrottleResult@1@PEBG@Z`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800038cc`
- `0x180003ac8`

## callees

- `0x180002590`
- `0x180005d44`
- `0x180005ee4`
- `0x180006530`
- `0x180006830`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800065fd`
- `KERNEL32!HeapAlloc` at `0x1800065fd`
- `KERNEL32!SetLastError` at `0x180006810`
- `KERNEL32!SetLastError` at `0x180006810`
- `KERNEL32!GetProcessHeap` at `0x1800065ef`
- `KERNEL32!GetProcessHeap` at `0x1800065ef`
- `ADVAPI32!RegCreateKeyExW` at `0x180006771`
- `ADVAPI32!RegCreateKeyExW` at `0x180006771`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065c5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066d3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800065c5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800066d3`
- `ADVAPI32!RegCloseKey` at `0x18000673a`
- `ADVAPI32!RegCloseKey` at `0x1800067e7`
- `ADVAPI32!RegCloseKey` at `0x1800067fa`
- `ADVAPI32!RegCloseKey` at `0x18000673a`
- `ADVAPI32!RegCloseKey` at `0x1800067e7`
- `ADVAPI32!RegCloseKey` at `0x1800067fa`

## pseudocode

```c
__int64 __fastcall Throttler::ProcessOccurrence(Throttler *a1, WCHAR *a2)
{
  WCHAR *v2; // r14
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  bool v6; // cf
  __int64 v7; // r15
  unsigned int v8; // edi
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  const WCHAR *v11; // rax
  const WCHAR *v12; // rbx
  unsigned __int64 v13; // r8
  unsigned int v14; // edx
  __int64 v15; // rax
  WCHAR *v16; // r9
  WCHAR *v17; // rcx
  WCHAR v18; // ax
  WCHAR *v19; // rcx
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  Throttler *v22; // rcx
  unsigned int v24; // [rsp+98h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a2;
  phkResult = 0;
  if ( !a2 || !*a2 )
  {
    SetLastError(0xA0u);
    return 4;
  }
  v4 = *(const WCHAR **)a1;
  if ( !*(_QWORD *)a1 )
    return 3;
  if ( !*v4 )
    return 3;
  if ( !*((_DWORD *)a1 + 2) )
    return 3;
  v5 = *((_DWORD *)a1 + 3);
  if ( !v5 || !*((_DWORD *)a1 + 4) || *((_DWORD *)a1 + 2) > v5 )
    return 3;
  v6 = *((_DWORD *)a1 + 5) != 0;
  hKey = 0;
  if ( RegOpenKeyExW((HKEY)(-(__int64)v6 - 2147483646), v4, 0, 0x2001Fu, &hKey) )
    return 4;
  v7 = -1;
  v8 = 0;
  v9 = -1;
  do
    ++v9;
  while ( v2[v9] );
  ProcessHeap = GetProcessHeap();
  v11 = (const WCHAR *)HeapAlloc(ProcessHeap, 0, 2 * v9 + 2);
  v12 = v11;
  if ( v11 )
  {
    do
      ++v7;
    while ( v2[v7] );
    v13 = v7 + 1;
    if ( v7 == -1 )
    {
      v14 = -2147024809;
LABEL_46:
      DebugPrint(0, "THROTTLE ERROR: %s:%d - hr = 0x%08X\n", "Throttler::ProcessOccurrence", 191, v14);
      goto LABEL_47;
    }
    if ( v13 > 0x7FFFFFFF )
    {
      v14 = -2147024809;
      *v11 = 0;
      goto LABEL_46;
    }
    v15 = 2147483646;
    v16 = (WCHAR *)v12;
    do
    {
      if ( !v15 )
        break;
      if ( !*v2 )
        break;
      *v16++ = *v2++;
      --v15;
      --v13;
    }
    while ( v13 );
    v17 = v16 - 1;
    v14 = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v17 = v16;
    *v17 = 0;
    if ( !v13 )
      goto LABEL_46;
    v18 = *v12;
    if ( *v12 )
    {
      v19 = (WCHAR *)v12;
      do
      {
        if ( v18 == 92 )
          *v19 = 47;
        v18 = *++v19;
      }
      while ( *v19 );
    }
    v20 = RegOpenKeyExW(hKey, v12, 0, 0x2001Fu, &phkResult);
    if ( v20 )
    {
      if ( v20 != 2 )
      {
LABEL_32:
        v8 = 4;
        goto LABEL_47;
      }
    }
    else if ( phkResult )
    {
      v24 = 0;
      if ( Throttler::CountRecentAndCleanOldOccurs(a1, phkResult, &v24) < 0 )
        goto LABEL_32;
      if ( v24 >= *((_DWORD *)a1 + 2) )
      {
        v8 = 1;
        goto LABEL_47;
      }
    }
    v8 = Throttler::ThrottleAnyIdInvocations(a1, hKey);
    if ( v8 )
      goto LABEL_47;
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    v21 = RegCreateKeyExW(hKey, v12, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    if ( v21 )
    {
      DebugPrint(0, "THROTTLE ERROR: %s:%d - res = %d\n", "Throttler::ProcessOccurrence", 237, v21);
    }
    else if ( Throttler::AddNewTimestampValue(v22, phkResult) >= 0 )
    {
      goto LABEL_47;
    }
    goto LABEL_32;
  }
  DebugPrint(0, "THROTTLE ERROR: %s:%d - hr = 0x%08X\n", "Throttler::ProcessOccurrence", 189, -2147024882);
LABEL_47:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v8;
}

```

## disassembly

```asm
0x180006530  push    rbp
0x180006532  push    rbx
0x180006533  push    rsi
0x180006534  push    rdi
0x180006535  push    r12
0x180006537  push    r14
0x180006539  push    r15
0x18000653b  mov     rbp, rsp
0x18000653e  sub     rsp, 50h
0x180006542  xor     r12d, r12d
0x180006545  mov     r14, rdx
0x180006548  mov     [rbp+arg_10], r12
0x18000654c  mov     rsi, rcx
0x18000654f  test    rdx, rdx
0x180006552  jz      loc_18000680B
0x180006558  cmp     [rdx], r12w
0x18000655c  jz      loc_18000680B
0x180006562  mov     rdx, [rcx]; lpSubKey
0x180006565  test    rdx, rdx
0x180006568  jz      loc_180006804
0x18000656e  cmp     [rdx], r12w
0x180006572  jz      loc_180006804
0x180006578  cmp     [rcx+8], r12d
0x18000657c  jz      loc_180006804
0x180006582  mov     eax, [rcx+0Ch]
0x180006585  test    eax, eax
0x180006587  jz      loc_180006804
0x18000658d  cmp     [rcx+10h], r12d
0x180006591  jz      loc_180006804
0x180006597  cmp     [rcx+8], eax
0x18000659a  ja      loc_180006804
0x1800065a0  mov     eax, [rcx+14h]
0x1800065a3  mov     r9d, 2001Fh; samDesired
0x1800065a9  neg     eax
0x1800065ab  mov     [rbp+hKey], r12
0x1800065af  lea     rax, [rbp+hKey]
0x1800065b3  sbb     rcx, rcx
0x1800065b6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800065bb  add     rcx, 0FFFFFFFF80000002h; hKey
0x1800065c2  xor     r8d, r8d; ulOptions
0x1800065c5  call    cs:__imp_RegOpenKeyExW
0x1800065cb  test    eax, eax
0x1800065cd  jnz     loc_180006816
0x1800065d3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800065d7  mov     edi, r12d
0x1800065da  mov     rbx, r15
0x1800065dd  inc     rbx
0x1800065e0  cmp     [r14+rbx*2], r12w
0x1800065e5  jnz     short loc_1800065DD
0x1800065e7  lea     rbx, ds:2[rbx*2]
0x1800065ef  call    cs:__imp_GetProcessHeap
0x1800065f5  mov     r8, rbx; dwBytes
0x1800065f8  xor     edx, edx; dwFlags
0x1800065fa  mov     rcx, rax; hHeap
0x1800065fd  call    cs:__imp_HeapAlloc
0x180006603  mov     rbx, rax
0x180006606  test    rax, rax
0x180006609  jnz     short loc_18000661E
0x18000660b  mov     dword ptr [rsp+50h+phkResult], 8007000Eh
0x180006613  mov     r9d, 0BDh
0x180006619  jmp     loc_1800067C9
0x18000661e  inc     r15
0x180006621  cmp     [r14+r15*2], r12w
0x180006626  jnz     short loc_18000661E
0x180006628  lea     r8, [r15+1]
0x18000662c  test    r8, r8
0x18000662f  jz      loc_1800067B1
0x180006635  cmp     r8, 7FFFFFFFh
0x18000663c  jbe     short loc_180006648
0x18000663e  mov     edx, 80070057h
0x180006643  jmp     loc_1800067BB
0x180006648  mov     eax, 7FFFFFFEh
0x18000664d  mov     r9, rbx
0x180006650  test    rax, rax
0x180006653  jz      short loc_180006673
0x180006655  movzx   ecx, word ptr [r14]
0x180006659  test    cx, cx
0x18000665c  jz      short loc_180006673
0x18000665e  mov     [r9], cx
0x180006662  add     r14, 2
0x180006666  add     r9, 2
0x18000666a  dec     rax
0x18000666d  sub     r8, 1
0x180006671  jnz     short loc_180006650
0x180006673  mov     rax, r8
0x180006676  lea     rcx, [r9-2]
0x18000667a  neg     rax
0x18000667d  sbb     edx, edx
0x18000667f  not     edx
0x180006681  and     edx, 8007007Ah
0x180006687  test    r8, r8
0x18000668a  cmovnz  rcx, r9
0x18000668e  mov     [rcx], r12w
0x180006692  jz      loc_1800067BF
0x180006698  movzx   eax, word ptr [rbx]
0x18000669b  test    ax, ax
0x18000669e  jz      short loc_1800066BA
0x1800066a0  mov     rcx, rbx
0x1800066a3  cmp     ax, 5Ch ; '\'
0x1800066a7  jnz     short loc_1800066AE
0x1800066a9  mov     word ptr [rcx], 2Fh ; '/'
0x1800066ae  add     rcx, 2
0x1800066b2  movzx   eax, word ptr [rcx]
0x1800066b5  test    ax, ax
0x1800066b8  jnz     short loc_1800066A3
0x1800066ba  mov     rcx, [rbp+hKey]; hKey
0x1800066be  lea     rax, [rbp+arg_10]
0x1800066c2  mov     r9d, 2001Fh; samDesired
0x1800066c8  mov     [rsp+50h+phkResult], rax; phkResult
0x1800066cd  xor     r8d, r8d; ulOptions
0x1800066d0  mov     rdx, rbx; lpSubKey
0x1800066d3  call    cs:__imp_RegOpenKeyExW
0x1800066d9  test    eax, eax
0x1800066db  jz      short loc_1800066EC
0x1800066dd  cmp     eax, 2
0x1800066e0  jz      short loc_18000671B
0x1800066e2  mov     edi, 4
0x1800066e7  jmp     loc_1800067DE
0x1800066ec  mov     rdx, [rbp+arg_10]; HKEY
0x1800066f0  test    rdx, rdx
0x1800066f3  jz      short loc_18000671B
0x1800066f5  lea     r8, [rbp+arg_8]; unsigned int *
0x1800066f9  mov     [rbp+arg_8], r12d
0x1800066fd  mov     rcx, rsi; this
0x180006700  call    ?CountRecentAndCleanOldOccurs@Throttler@@AEAAJPEAUHKEY__@@PEAK@Z; Throttler::CountRecentAndCleanOldOccurs(HKEY__ *,ulong *)
0x180006705  test    eax, eax
0x180006707  js      short loc_1800066E2
0x180006709  mov     eax, [rsi+8]
0x18000670c  cmp     [rbp+arg_8], eax
0x18000670f  jb      short loc_18000671B
0x180006711  mov     edi, 1
0x180006716  jmp     loc_1800067DE
0x18000671b  mov     rdx, [rbp+hKey]
0x18000671f  mov     rcx, rsi
0x180006722  call    ?ThrottleAnyIdInvocations@Throttler@@AEAA?AW4ThrottleResult@1@PEAUHKEY__@@@Z; Throttler::ThrottleAnyIdInvocations(HKEY__ *)
0x180006727  mov     edi, eax
0x180006729  test    eax, eax
0x18000672b  jnz     loc_1800067DE
0x180006731  mov     rcx, [rbp+arg_10]; hKey
0x180006735  test    rcx, rcx
0x180006738  jz      short loc_180006744
0x18000673a  call    cs:__imp_RegCloseKey
0x180006740  mov     [rbp+arg_10], r12
0x180006744  mov     rcx, [rbp+hKey]; hKey
0x180006748  lea     rax, [rbp+arg_10]
0x18000674c  mov     [rsp+50h+lpdwDisposition], r12; lpdwDisposition
0x180006751  xor     r9d, r9d; lpClass
0x180006754  mov     [rsp+50h+var_18], rax; phkResult
0x180006759  xor     r8d, r8d; Reserved
0x18000675c  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180006761  mov     rdx, rbx; lpSubKey
0x180006764  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18000676c  mov     dword ptr [rsp+50h+phkResult], r12d; dwOptions
0x180006771  call    cs:__imp_RegCreateKeyExW
0x180006777  test    eax, eax
0x180006779  jz      short loc_18000679F
0x18000677b  mov     r9d, 0EDh
0x180006781  mov     dword ptr [rsp+50h+phkResult], eax
0x180006785  lea     r8, aThrottlerProce; "Throttler::ProcessOccurrence"
0x18000678c  xor     ecx, ecx; Level
0x18000678e  lea     rdx, aThrottleErrorS_1; "THROTTLE ERROR: %s:%d - res = %d\n"
0x180006795  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000679a  jmp     loc_1800066E2
0x18000679f  mov     rdx, [rbp+arg_10]; HKEY
0x1800067a3  call    ?AddNewTimestampValue@Throttler@@AEAAJPEAUHKEY__@@@Z; Throttler::AddNewTimestampValue(HKEY__ *)
0x1800067a8  test    eax, eax
0x1800067aa  jns     short loc_1800067DE
0x1800067ac  jmp     loc_1800066E2
0x1800067b1  mov     edx, 80070057h
0x1800067b6  test    r8, r8
0x1800067b9  jz      short loc_1800067BF
0x1800067bb  mov     [rax], r12w
0x1800067bf  mov     dword ptr [rsp+50h+phkResult], edx
0x1800067c3  mov     r9d, 0BFh
0x1800067c9  lea     r8, aThrottlerProce; "Throttler::ProcessOccurrence"
0x1800067d0  xor     ecx, ecx; Level
0x1800067d2  lea     rdx, aThrottleErrorS_0; "THROTTLE ERROR: %s:%d - hr = 0x%08X\n"
0x1800067d9  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x1800067de  mov     rcx, [rbp+hKey]; hKey
0x1800067e2  test    rcx, rcx
0x1800067e5  jz      short loc_1800067F1
0x1800067e7  call    cs:__imp_RegCloseKey
0x1800067ed  mov     [rbp+hKey], r12
0x1800067f1  mov     rcx, [rbp+arg_10]; hKey
0x1800067f5  test    rcx, rcx
0x1800067f8  jz      short loc_180006800
0x1800067fa  call    cs:__imp_RegCloseKey
0x180006800  mov     eax, edi
0x180006802  jmp     short loc_18000681B
0x180006804  mov     eax, 3
0x180006809  jmp     short loc_18000681B
0x18000680b  mov     ecx, 0A0h; dwErrCode
0x180006810  call    cs:__imp_SetLastError
0x180006816  mov     eax, 4
0x18000681b  add     rsp, 50h
0x18000681f  pop     r15
0x180006821  pop     r14
0x180006823  pop     r12
0x180006825  pop     rdi
0x180006826  pop     rsi
0x180006827  pop     rbx
0x180006828  pop     rbp
0x180006829  retn
```

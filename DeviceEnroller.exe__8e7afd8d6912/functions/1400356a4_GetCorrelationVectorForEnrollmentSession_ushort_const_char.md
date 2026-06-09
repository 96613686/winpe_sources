# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x1400356a4`
- end: `0x1400359de`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `826`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140019a6c`
- `0x1400347e8`

## callees

- `0x1400042f0`
- `0x140004314`
- `0x1400045a8`
- `0x140034754`
- `0x1400353e4`
- `0x1400356a4`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x14003586e`
- `DMCmnUtils!UnicodeToMB` at `0x14003586e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140035723`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140035723`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400358a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003591a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400358a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003591a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035892`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003590c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140035892`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003590c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400357b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400357b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140035713`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400357ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140035713`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400357ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035756`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400357f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035756`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400357f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003570b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400357c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400359a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003570b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400357c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400359a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035794`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035826`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035794`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140035826`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(LPCWSTR lpValueName, char *a2)
{
  DWORD LastError; // ebx
  char IsStateSeparationEnabled; // al
  LSTATUS v6; // eax
  signed int v7; // ebx
  bool v8; // cc
  LSTATUS v9; // eax
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  void *v12; // rdi
  __int64 v13; // rax
  char *v14; // r8
  __int64 v15; // rcx
  char *v16; // rdx
  char v17; // r9
  char *v18; // rax
  HANDLE v19; // rax
  void *v20; // rax
  volatile signed __int64 *v21; // rbx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_lpMem; // [rsp+58h] [rbp-A8h]
  char *v30; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v33[136]; // [rsp+C0h] [rbp-40h] BYREF

  if ( !a2 || !lpValueName )
    return 2147942487LL;
  hKey = 0;
  *a2 = 0;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6
    || (cbData = 78,
        v6 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData),
        v7 = v6,
        v8 = v6 <= 0,
        v6) )
  {
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v9 = RegQueryValueExW(phkResult, lpValueName, 0, 0, (LPBYTE)v33, &lpcbData);
    v7 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      lpMem = 0;
      v27 = 0;
      p_lpMem = &lpMem;
      v30 = 0;
      v31 = 1;
      v7 = UnicodeToMB(v33, 0xFDE9u, &v30, &v27);
      if ( v31 )
      {
        v10 = *p_lpMem;
        *p_lpMem = v30;
        if ( v10 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v10);
        }
      }
      v12 = lpMem;
      if ( v7 >= 0 && lpMem )
      {
        v13 = 2147483646;
        v14 = (char *)lpMem;
        v15 = 129;
        v16 = a2;
        do
        {
          if ( !v13 )
            break;
          v17 = *v14;
          if ( !*v14 )
            break;
          ++v14;
          *v16++ = v17;
          --v13;
          --v15;
        }
        while ( v15 );
        v18 = v16 - 1;
        if ( v15 )
          v18 = v16;
        *v18 = 0;
        v7 = v15 == 0 ? 0x8007007A : 0;
      }
      lpMem = 0;
      if ( v12 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v12);
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( v7 < 0 )
  {
    v20 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v20
        ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v20)
        : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v21,
      _InterlockedExchangeAdd64(v21 + 17, 0),
      a2);
    if ( v21 )
      operator delete((void *)v21);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1400356a4  mov     [rsp-8+arg_10], rbx
0x1400356a9  mov     [rsp-8+arg_18], rsi
0x1400356ae  push    rbp
0x1400356af  push    rdi
0x1400356b0  push    r14
0x1400356b2  lea     rbp, [rsp-0E0h]
0x1400356ba  sub     rsp, 1E0h
0x1400356c1  mov     rax, cs:__security_cookie
0x1400356c8  xor     rax, rsp
0x1400356cb  mov     [rbp+0F0h+var_20], rax
0x1400356d2  mov     rsi, rdx
0x1400356d5  mov     r14, rcx
0x1400356d8  test    rdx, rdx
0x1400356db  jz      loc_1400359B2
0x1400356e1  test    rcx, rcx
0x1400356e4  jz      loc_1400359B2
0x1400356ea  mov     [rsp+1F0h+hKey], 0
0x1400356f3  mov     byte ptr [rdx], 0
0x1400356f6  mov     rdi, [rsp+1F0h+hKey]
0x1400356fb  test    rdi, rdi
0x1400356fe  jz      short loc_14003571A
0x140035700  call    cs:__imp_GetLastError
0x140035706  mov     ebx, eax
0x140035708  mov     rcx, rdi; hKey
0x14003570b  call    cs:__imp_RegCloseKey
0x140035711  mov     ecx, ebx; dwErrCode
0x140035713  call    cs:__imp_SetLastError
0x140035719  nop
0x14003571a  mov     [rsp+1F0h+hKey], 0
0x140035723  call    cs:__imp_RtlIsStateSeparationEnabled
0x140035729  neg     al
0x14003572b  sbb     rdx, rdx
0x14003572e  and     edx, 8
0x140035731  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x140035738  lea     rax, [rsp+1F0h+hKey]
0x14003573d  mov     [rsp+1F0h+phkResult], rax; phkResult
0x140035742  mov     r9d, 20019h; samDesired
0x140035748  xor     r8d, r8d; ulOptions
0x14003574b  mov     rdx, [rdx+rcx]; lpSubKey
0x14003574f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140035756  call    cs:__imp_RegOpenKeyExW
0x14003575c  mov     ebx, eax
0x14003575e  test    eax, eax
0x140035760  jnz     loc_140035940
0x140035766  mov     [rsp+1F0h+cbData], 4Eh ; 'N'
0x14003576e  lea     rax, [rsp+1F0h+cbData]
0x140035773  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x140035778  lea     rax, [rsp+1F0h+Data]
0x14003577d  mov     [rsp+1F0h+phkResult], rax; lpData
0x140035782  xor     r9d, r9d; lpType
0x140035785  xor     r8d, r8d; lpReserved
0x140035788  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x14003578f  mov     rcx, [rsp+1F0h+hKey]; hKey
0x140035794  call    cs:__imp_RegQueryValueExW
0x14003579a  mov     ebx, eax
0x14003579c  test    eax, eax
0x14003579e  jnz     loc_140035940
0x1400357a4  mov     [rsp+1F0h+var_1B8], 0
0x1400357ad  mov     rdi, [rsp+1F0h+var_1B8]
0x1400357b2  test    rdi, rdi
0x1400357b5  jz      short loc_1400357D1
0x1400357b7  call    cs:__imp_GetLastError
0x1400357bd  mov     ebx, eax
0x1400357bf  mov     rcx, rdi; hKey
0x1400357c2  call    cs:__imp_RegCloseKey
0x1400357c8  mov     ecx, ebx; dwErrCode
0x1400357ca  call    cs:__imp_SetLastError
0x1400357d0  nop
0x1400357d1  mov     [rsp+1F0h+var_1B8], 0
0x1400357da  lea     rax, [rsp+1F0h+var_1B8]
0x1400357df  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1400357e4  mov     r9d, 20019h; samDesired
0x1400357ea  xor     r8d, r8d; ulOptions
0x1400357ed  lea     rdx, [rsp+1F0h+Data]; lpSubKey
0x1400357f2  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1400357f7  call    cs:__imp_RegOpenKeyExW
0x1400357fd  mov     [rsp+1F0h+var_1AC], 102h
0x140035805  lea     rax, [rsp+1F0h+var_1AC]
0x14003580a  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x14003580f  lea     rax, [rbp+0F0h+var_130]
0x140035813  mov     [rsp+1F0h+phkResult], rax; lpData
0x140035818  xor     r9d, r9d; lpType
0x14003581b  xor     r8d, r8d; lpReserved
0x14003581e  mov     rdx, r14; lpValueName
0x140035821  mov     rcx, [rsp+1F0h+var_1B8]; hKey
0x140035826  call    cs:__imp_RegQueryValueExW
0x14003582c  mov     ebx, eax
0x14003582e  test    eax, eax
0x140035830  jnz     loc_140035922
0x140035836  mov     [rsp+1F0h+lpMem], 0
0x14003583f  mov     [rsp+1F0h+var_1A8], eax
0x140035843  lea     rax, [rsp+1F0h+lpMem]
0x140035848  mov     [rsp+1F0h+var_198], rax
0x14003584d  mov     [rsp+1F0h+var_190], 0
0x140035856  mov     [rsp+1F0h+var_188], 1
0x14003585b  lea     r9, [rsp+1F0h+var_1A8]
0x140035860  lea     r8, [rsp+1F0h+var_190]
0x140035865  mov     edx, 0FDE9h
0x14003586a  lea     rcx, [rbp+0F0h+var_130]
0x14003586e  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x140035874  mov     ebx, eax
0x140035876  cmp     [rsp+1F0h+var_188], 0
0x14003587b  jz      short loc_1400358A6
0x14003587d  mov     rdx, [rsp+1F0h+var_198]
0x140035882  mov     rdi, [rdx]
0x140035885  mov     rcx, [rsp+1F0h+var_190]
0x14003588a  mov     [rdx], rcx
0x14003588d  test    rdi, rdi
0x140035890  jz      short loc_1400358A6
0x140035892  call    cs:__imp_GetProcessHeap
0x140035898  mov     rcx, rax; hHeap
0x14003589b  mov     r8, rdi; lpMem
0x14003589e  xor     edx, edx; dwFlags
0x1400358a0  call    cs:__imp_HeapFree
0x1400358a6  mov     rdi, [rsp+1F0h+lpMem]
0x1400358ab  test    ebx, ebx
0x1400358ad  js      short loc_1400358FE
0x1400358af  test    rdi, rdi
0x1400358b2  jz      short loc_1400358FE
0x1400358b4  mov     eax, 7FFFFFFEh
0x1400358b9  mov     r8, rdi
0x1400358bc  mov     ecx, 81h
0x1400358c1  mov     rdx, rsi
0x1400358c4  test    rax, rax
0x1400358c7  jz      short loc_1400358E3
0x1400358c9  mov     r9b, [r8]
0x1400358cc  test    r9b, r9b
0x1400358cf  jz      short loc_1400358E3
0x1400358d1  inc     r8
0x1400358d4  mov     [rdx], r9b
0x1400358d7  inc     rdx
0x1400358da  dec     rax
0x1400358dd  sub     rcx, 1
0x1400358e1  jnz     short loc_1400358C4
0x1400358e3  lea     rax, [rdx-1]
0x1400358e7  test    rcx, rcx
0x1400358ea  cmovnz  rax, rdx
0x1400358ee  mov     byte ptr [rax], 0
0x1400358f1  neg     rcx
0x1400358f4  sbb     ebx, ebx
0x1400358f6  not     ebx
0x1400358f8  and     ebx, 8007007Ah
0x1400358fe  mov     [rsp+1F0h+lpMem], 0
0x140035907  test    rdi, rdi
0x14003590a  jz      short loc_14003592D
0x14003590c  call    cs:__imp_GetProcessHeap
0x140035912  mov     rcx, rax; hHeap
0x140035915  mov     r8, rdi; lpMem
0x140035918  xor     edx, edx; dwFlags
0x14003591a  call    cs:__imp_HeapFree
0x140035920  jmp     short loc_14003592D
0x140035922  jle     short loc_14003592D
0x140035924  movzx   ebx, ax
0x140035927  or      ebx, 80070000h
0x14003592d  mov     rcx, [rsp+1F0h+var_1B8]; hKey
0x140035932  test    rcx, rcx
0x140035935  jz      short loc_14003593E
0x140035937  call    cs:__imp_RegCloseKey
0x14003593d  nop
0x14003593e  jmp     short loc_14003594B
0x140035940  jle     short loc_14003594B
0x140035942  movzx   ebx, ax
0x140035945  or      ebx, 80070000h
0x14003594b  test    ebx, ebx
0x14003594d  jns     short loc_14003599D
0x14003594f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140035956  mov     edi, 90h
0x14003595b  mov     ecx, edi; unsigned __int64
0x14003595d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140035962  test    rax, rax
0x140035965  jz      short loc_140035974
0x140035967  mov     rcx, rax
0x14003596a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x14003596f  mov     rbx, rax
0x140035972  jmp     short loc_140035976
0x140035974  xor     ebx, ebx
0x140035976  xor     edx, edx
0x140035978  lock xadd [rbx+88h], rdx; unsigned __int64
0x140035981  mov     r8, rsi; char *
0x140035984  mov     rcx, rbx; this
0x140035987  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x14003598c  test    rbx, rbx
0x14003598f  jz      short loc_14003599D
0x140035991  mov     rdx, rdi
0x140035994  mov     rcx, rbx; Block
0x140035997  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003599c  nop
0x14003599d  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1400359a2  test    rcx, rcx
0x1400359a5  jz      short loc_1400359AE
0x1400359a7  call    cs:__imp_RegCloseKey
0x1400359ad  nop
0x1400359ae  xor     eax, eax
0x1400359b0  jmp     short loc_1400359B7
0x1400359b2  mov     eax, 80070057h
0x1400359b7  mov     rcx, [rbp+0F0h+var_20]
0x1400359be  xor     rcx, rsp; StackCookie
0x1400359c1  call    __security_check_cookie
0x1400359c6  lea     r11, [rsp+1F0h+var_10]
0x1400359ce  mov     rbx, [r11+30h]
0x1400359d2  mov     rsi, [r11+38h]
0x1400359d6  mov     rsp, r11
0x1400359d9  pop     r14
0x1400359db  pop     rdi
0x1400359dc  pop     rbp
0x1400359dd  retn
```

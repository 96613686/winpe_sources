# winreGetWinReGuid

- ea: `0x180035300`
- end: `0x180035596`
- name: `winreGetWinReGuid`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180012f58`
- `0x1800174a0`
- `0x180024df0`
- `0x18002f6a0`

## callees

- `0x1800059fc`
- `0x180035300`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035552`
- `ntdll!RtlNtStatusToDosError` at `0x180035552`
- `KERNEL32!HeapFree` at `0x180035533`
- `KERNEL32!HeapFree` at `0x180035533`
- `KERNEL32!HeapAlloc` at `0x1800353f3`
- `KERNEL32!HeapAlloc` at `0x1800353f3`
- `KERNEL32!GetProcessHeap` at `0x1800353e0`
- `KERNEL32!GetProcessHeap` at `0x180035525`
- `KERNEL32!GetProcessHeap` at `0x1800353e0`
- `KERNEL32!GetProcessHeap` at `0x180035525`
- `bcd!BcdGetElementDataWithFlags` at `0x1800353b6`
- `bcd!BcdGetElementDataWithFlags` at `0x1800353b6`
- `bcd!BcdCloseStore` at `0x18003551a`
- `bcd!BcdCloseStore` at `0x18003551a`
- `bcd!BcdCloseObject` at `0x180035470`
- `bcd!BcdCloseObject` at `0x180035503`
- `bcd!BcdCloseObject` at `0x180035470`
- `bcd!BcdCloseObject` at `0x180035503`
- `bcd!BcdGetElementData` at `0x180035443`
- `bcd!BcdGetElementData` at `0x1800354b9`
- `bcd!BcdGetElementData` at `0x180035443`
- `bcd!BcdGetElementData` at `0x1800354b9`
- `bcd!BcdOpenObject` at `0x180035382`
- `bcd!BcdOpenObject` at `0x180035495`
- `bcd!BcdOpenObject` at `0x180035382`
- `bcd!BcdOpenObject` at `0x180035495`
- `bcd!BcdOpenStore` at `0x180035352`
- `bcd!BcdOpenStore` at `0x180035352`

## string_xrefs

- `0x18003535e`: `winreGetWinReGuid open store failed: 0x%x`
- `0x18003538e`: `winreGetWinReGuid BcdOpenObject failed: 0x%x`
- `0x180035401`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x1800354e4`: `BcdOpenObject(WinRE) failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetWinReGuid(__int64 a1, _OWORD *a2)
{
  ULONG v2; // esi
  _OWORD *v5; // r14
  int v6; // eax
  NTSTATUS ElementDataWithFlags; // edi
  const wchar_t *v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  _OWORD *v12; // rax
  int ElementData; // eax
  unsigned int v14; // r15d
  unsigned int i; // ebx
  int v16; // eax
  HANDLE v17; // rax
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  unsigned int dwBytes; // [rsp+40h] [rbp-20h] BYREF
  __int16 dwBytes_4; // [rsp+44h] [rbp-1Ch] BYREF
  __int128 v23; // [rsp+48h] [rbp-18h] BYREF

  v2 = 0;
  v20 = 0;
  v19 = 0;
  dwBytes = 0;
  dwBytes_4 = 0;
  v23 = 0;
  v5 = 0;
  v6 = BcdOpenStore(0, 0, &v20);
  ElementDataWithFlags = v6;
  if ( v6 < 0 )
  {
    v8 = L"winreGetWinReGuid open store failed: 0x%x";
LABEL_3:
    v9 = (unsigned int)v6;
LABEL_4:
    UnattendLogW(2, v8, v9);
    goto LABEL_28;
  }
  v6 = BcdOpenObject(v20, a1, &v19);
  ElementDataWithFlags = v6;
  if ( v6 < 0 )
  {
    v8 = L"winreGetWinReGuid BcdOpenObject failed: 0x%x";
    goto LABEL_3;
  }
  dwBytes = 0;
  ElementDataWithFlags = BcdGetElementDataWithFlags(v19, 335544328, 0, 0, &dwBytes);
  if ( (int)(ElementDataWithFlags + 0x80000000) >= 0 && ElementDataWithFlags != -1073741789 )
  {
    v9 = (unsigned int)ElementDataWithFlags;
LABEL_11:
    v8 = L"Failed to get recovery entries: 0x%x";
    goto LABEL_4;
  }
  v10 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, v10);
  v5 = v12;
  if ( !v12 )
  {
    v2 = 8;
    UnattendLogW(
      2,
      L"winreGetWinReGuid %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
      221);
    goto LABEL_28;
  }
  ElementData = BcdGetElementData(v19, 335544328, v12, &dwBytes);
  ElementDataWithFlags = ElementData;
  if ( ElementData < 0 )
  {
    v9 = (unsigned int)ElementData;
    goto LABEL_11;
  }
  v14 = dwBytes >> 4;
  for ( i = 0; i < v14; ++i )
  {
    if ( v19 )
    {
      BcdCloseObject();
      v19 = 0;
    }
    v23 = v5[i];
    v16 = BcdOpenObject(v20, &v23, &v19);
    ElementDataWithFlags = v16;
    if ( v16 < 0 )
    {
      UnattendLogW(1, L"BcdOpenObject(WinRE) failed: 0x%x", (unsigned int)v16);
      goto LABEL_28;
    }
    dwBytes = 2;
    ElementDataWithFlags = BcdGetElementData(v19, 1174405136, &dwBytes_4, &dwBytes);
    if ( ElementDataWithFlags >= 0 && dwBytes == 2 && (_BYTE)dwBytes_4 )
    {
      *a2 = v23;
      goto LABEL_28;
    }
  }
  ElementDataWithFlags = -1073741809;
LABEL_28:
  if ( v19 )
  {
    BcdCloseObject();
    v19 = 0;
  }
  if ( v20 )
    BcdCloseStore();
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  if ( ElementDataWithFlags < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    v2 = RtlNtStatusToDosError(ElementDataWithFlags);
  }
  if ( v2 )
    UnattendLogW(0, L"winreGetWinReGuid returning 0X%X", v2);
  return v2;
}

```

## disassembly

```asm
0x180035300  mov     [rsp-28h+arg_10], rbx
0x180035305  mov     [rsp-28h+arg_18], rsi
0x18003530a  push    rbp
0x18003530b  push    rdi
0x18003530c  push    r12
0x18003530e  push    r14
0x180035310  push    r15
0x180035312  mov     rbp, rsp
0x180035315  sub     rsp, 60h
0x180035319  mov     rax, cs:__security_cookie
0x180035320  xor     rax, rsp
0x180035323  mov     [rbp+var_8], rax
0x180035327  xor     esi, esi
0x180035329  lea     r8, [rbp+var_28]
0x18003532d  mov     r12, rdx
0x180035330  mov     [rbp+var_28], rsi
0x180035334  mov     rbx, rcx
0x180035337  mov     [rbp+var_30], rsi
0x18003533b  xorps   xmm0, xmm0
0x18003533e  mov     dword ptr [rbp+dwBytes], esi
0x180035341  xor     eax, eax
0x180035343  xor     edx, edx
0x180035345  xor     ecx, ecx
0x180035347  mov     word ptr [rbp+dwBytes+4], ax
0x18003534b  movups  [rbp+var_18], xmm0
0x18003534f  xor     r14d, r14d
0x180035352  call    cs:__imp_BcdOpenStore
0x180035358  mov     edi, eax
0x18003535a  test    eax, eax
0x18003535c  jns     short loc_180035377
0x18003535e  lea     rdx, aWinregetwinreg; "winreGetWinReGuid open store failed: 0x"...
0x180035365  mov     r8d, eax
0x180035368  mov     ecx, 2
0x18003536d  call    UnattendLogW
0x180035372  jmp     loc_1800354FA
0x180035377  mov     rcx, [rbp+var_28]
0x18003537b  lea     r8, [rbp+var_30]
0x18003537f  mov     rdx, rbx
0x180035382  call    cs:__imp_BcdOpenObject
0x180035388  mov     edi, eax
0x18003538a  test    eax, eax
0x18003538c  jns     short loc_180035397
0x18003538e  lea     rdx, aWinregetwinreg_1; "winreGetWinReGuid BcdOpenObject failed:"...
0x180035395  jmp     short loc_180035365
0x180035397  mov     rcx, [rbp+var_30]
0x18003539b  lea     rax, [rbp+dwBytes]
0x18003539f  mov     r15d, 14000008h
0x1800353a5  mov     dword ptr [rbp+dwBytes], esi
0x1800353a8  mov     edx, r15d
0x1800353ab  mov     [rsp+60h+var_40], rax
0x1800353b0  xor     r9d, r9d
0x1800353b3  xor     r8d, r8d
0x1800353b6  call    cs:__imp_BcdGetElementDataWithFlags
0x1800353bc  mov     ecx, 80000000h
0x1800353c1  mov     edi, eax
0x1800353c3  add     eax, ecx
0x1800353c5  test    ecx, eax
0x1800353c7  jnz     short loc_1800353DD
0x1800353c9  cmp     edi, 0C0000023h
0x1800353cf  jz      short loc_1800353DD
0x1800353d1  mov     r8d, edi
0x1800353d4  lea     rdx, aFailedToGetRec_0; "Failed to get recovery entries: 0x%x"
0x1800353db  jmp     short loc_180035368
0x1800353dd  mov     ebx, dword ptr [rbp+dwBytes]
0x1800353e0  call    cs:__imp_GetProcessHeap
0x1800353e6  mov     r8d, ebx; dwBytes
0x1800353e9  mov     ebx, 8
0x1800353ee  mov     edx, ebx; dwFlags
0x1800353f0  mov     rcx, rax; hHeap
0x1800353f3  call    cs:__imp_HeapAlloc
0x1800353f9  mov     r14, rax
0x1800353fc  test    rax, rax
0x1800353ff  jnz     short loc_180035435
0x180035401  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180035408  mov     [rsp+60h+var_38], 0DDh
0x180035410  mov     r9d, ebx
0x180035413  mov     [rsp+60h+var_40], rax
0x180035418  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18003541f  mov     esi, ebx
0x180035421  lea     rdx, aWinregetwinreg_2; "winreGetWinReGuid %s (0x%x) in file %S "...
0x180035428  lea     ecx, [rbx-6]
0x18003542b  call    UnattendLogW
0x180035430  jmp     loc_1800354FA
0x180035435  mov     rcx, [rbp+var_30]
0x180035439  lea     r9, [rbp+dwBytes]
0x18003543d  mov     r8, r14
0x180035440  mov     edx, r15d
0x180035443  call    cs:__imp_BcdGetElementData
0x180035449  mov     edi, eax
0x18003544b  test    eax, eax
0x18003544d  jns     short loc_180035454
0x18003544f  mov     r8d, eax
0x180035452  jmp     short loc_1800353D4
0x180035454  mov     r15d, dword ptr [rbp+dwBytes]
0x180035458  shr     r15d, 4
0x18003545c  xor     ebx, ebx
0x18003545e  cmp     ebx, r15d
0x180035461  jnb     loc_1800354F5
0x180035467  mov     rcx, [rbp+var_30]
0x18003546b  test    rcx, rcx
0x18003546e  jz      short loc_18003547A
0x180035470  call    cs:__imp_BcdCloseObject
0x180035476  mov     [rbp+var_30], rsi
0x18003547a  mov     rcx, [rbp+var_28]
0x18003547e  lea     r8, [rbp+var_30]
0x180035482  mov     eax, ebx
0x180035484  lea     rdx, [rbp+var_18]
0x180035488  add     rax, rax
0x18003548b  movups  xmm0, xmmword ptr [r14+rax*8]
0x180035490  movdqu  [rbp+var_18], xmm0
0x180035495  call    cs:__imp_BcdOpenObject
0x18003549b  mov     edi, eax
0x18003549d  test    eax, eax
0x18003549f  js      short loc_1800354E1
0x1800354a1  mov     rcx, [rbp+var_30]
0x1800354a5  lea     r9, [rbp+dwBytes]
0x1800354a9  lea     r8, [rbp+dwBytes+4]
0x1800354ad  mov     dword ptr [rbp+dwBytes], 2
0x1800354b4  mov     edx, 46000010h
0x1800354b9  call    cs:__imp_BcdGetElementData
0x1800354bf  mov     edi, eax
0x1800354c1  test    eax, eax
0x1800354c3  js      short loc_1800354D1
0x1800354c5  cmp     dword ptr [rbp+dwBytes], 2
0x1800354c9  jnz     short loc_1800354D1
0x1800354cb  cmp     byte ptr [rbp+dwBytes+4], sil
0x1800354cf  jnz     short loc_1800354D5
0x1800354d1  inc     ebx
0x1800354d3  jmp     short loc_18003545E
0x1800354d5  movups  xmm0, [rbp+var_18]
0x1800354d9  movdqu  xmmword ptr [r12], xmm0
0x1800354df  jmp     short loc_1800354FA
0x1800354e1  mov     r8d, eax
0x1800354e4  lea     rdx, aBcdopenobjectW; "BcdOpenObject(WinRE) failed: 0x%x"
0x1800354eb  mov     ecx, 1
0x1800354f0  jmp     loc_18003536D
0x1800354f5  mov     edi, 0C000000Fh
0x1800354fa  mov     rcx, [rbp+var_30]
0x1800354fe  test    rcx, rcx
0x180035501  jz      short loc_180035511
0x180035503  call    cs:__imp_BcdCloseObject
0x180035509  mov     [rbp+var_30], 0
0x180035511  mov     rcx, [rbp+var_28]
0x180035515  test    rcx, rcx
0x180035518  jz      short loc_180035520
0x18003551a  call    cs:__imp_BcdCloseStore
0x180035520  test    r14, r14
0x180035523  jz      short loc_180035539
0x180035525  call    cs:__imp_GetProcessHeap
0x18003552b  mov     r8, r14; lpMem
0x18003552e  xor     edx, edx; dwFlags
0x180035530  mov     rcx, rax; hHeap
0x180035533  call    cs:__imp_HeapFree
0x180035539  test    edi, edi
0x18003553b  jns     short loc_18003555A
0x18003553d  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180035544  jnz     short loc_180035550
0x180035546  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180035550  mov     ecx, edi; Status
0x180035552  call    cs:__imp_RtlNtStatusToDosError
0x180035558  mov     esi, eax
0x18003555a  test    esi, esi
0x18003555c  jz      short loc_18003556F
0x18003555e  mov     r8d, esi
0x180035561  lea     rdx, aWinregetwinreg_0; "winreGetWinReGuid returning 0X%X"
0x180035568  xor     ecx, ecx
0x18003556a  call    UnattendLogW
0x18003556f  mov     eax, esi
0x180035571  mov     rcx, [rbp+var_8]
0x180035575  xor     rcx, rsp; StackCookie
0x180035578  call    __security_check_cookie
0x18003557d  lea     r11, [rsp+60h+var_s0]
0x180035582  mov     rbx, [r11+40h]
0x180035586  mov     rsi, [r11+48h]
0x18003558a  mov     rsp, r11
0x18003558d  pop     r15
0x18003558f  pop     r14
0x180035591  pop     r12
0x180035593  pop     rdi
0x180035594  pop     rbp
0x180035595  retn
```

# BfeDbSetObjectState

- ea: `0x180005830`
- end: `0x180005a53`
- name: `BfeDbSetObjectState`
- size: `547`
- prototype: `__int64 __fastcall(__int64, HKEY, unsigned int *, __int64 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004fc0`
- `0x180044c80`
- `0x1800660fc`

## callees

- `0x1800039e4`
- `0x180004850`
- `0x1800049f8`
- `0x180005830`
- `0x180005a5c`
- `0x18000e000`
- `0x18000e4e0`
- `0x18001236c`
- `0x180018b74`
- `0x1800575c4`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800058d0`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800058d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800059b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800059b0`

## string_xrefs

- `0x180005a36`: `BfeRegSetBinary`
- `0x180005a25`: `RegSetValueExW`

## pseudocode

```c
__int64 __fastcall BfeDbSetObjectState(__int64 a1, HKEY a2, unsigned int *a3, __int64 *a4)
{
  __int64 v4; // rbx
  __int64 v5; // r14
  DWORD cbData; // r12d
  BYTE *lpData; // r13
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  void *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  const char *v18; // rdx
  DWORD v19; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v20; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h]
  __int128 v22; // [rsp+88h] [rbp-78h] BYREF
  __int128 v23; // [rsp+98h] [rbp-68h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-58h]
  wchar_t pszDest[40]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = *a4;
  v5 = gBfeObjMgr;
  v24 = 0;
  cbData = 0;
  lpData = 0;
  v22 = 0;
  v10 = 408LL * (int)a1;
  v23 = 0;
  hKey = a2;
  v19 = 0;
  v20 = 0;
  LODWORD(v22) = a1;
  if ( !(unsigned int)BfeObjectTypeIdIsValid(a1) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = WfpMidlObjectEncode(*(_QWORD *)(v10 + v5 + 48), v4, &v23, (char *)&v22 + 8);
  v12 = v11;
  if ( v11 )
  {
    WfpReportError(v11, "BfeObjectEncodePublicState");
  }
  else
  {
    v13 = (void *)a4[1];
    if ( v13 )
    {
      DWORD2(v23) = RtlLengthSecurityDescriptor(v13);
      v24 = a4[1];
    }
    v14 = WfpMidlObjectEncode(&BFE_PERSISTENT_OBJECT_MARSHAL_Encode, &v22, &v20, &v19);
    cbData = v19;
    v12 = v14;
    lpData = v20;
  }
  WfpMemFree(&v23);
  if ( v12 )
  {
    v18 = "BfeDbObjectEncode";
LABEL_17:
    WfpReportError(v12, v18);
    goto LABEL_11;
  }
  StringCchPrintfW(
    pszDest,
    0x27u,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    *a3,
    *((unsigned __int16 *)a3 + 2),
    *((unsigned __int16 *)a3 + 3),
    *((unsigned __int8 *)a3 + 8),
    *((unsigned __int8 *)a3 + 9),
    *((unsigned __int8 *)a3 + 10),
    *((unsigned __int8 *)a3 + 11),
    *((unsigned __int8 *)a3 + 12),
    *((unsigned __int8 *)a3 + 13),
    *((unsigned __int8 *)a3 + 14),
    *((unsigned __int8 *)a3 + 15));
  BfeCallGetSysTxn();
  v12 = 0;
  v15 = RegSetValueExW(hKey, pszDest, 0, 3u, lpData, cbData);
  if ( v15 )
    v12 = WfpReportSysErrorAsWinError(v16, "RegSetValueExW", v15);
  BfeRegCloseKey(0);
  if ( v12 )
  {
    v18 = "BfeRegSetBinary";
    goto LABEL_17;
  }
LABEL_11:
  WfpMemFree(&v20);
  if ( v12 )
    WfpReportError(v12, "BfeDbSetObjectState");
  return v12;
}

```

## disassembly

```asm
0x180005830  push    rbp
0x180005832  push    rbx
0x180005833  push    rsi
0x180005834  push    rdi
0x180005835  push    r12
0x180005837  push    r13
0x180005839  push    r14
0x18000583b  push    r15
0x18000583d  lea     rbp, [rsp-18h]
0x180005842  sub     rsp, 118h
0x180005849  mov     rax, cs:__security_cookie
0x180005850  xor     rax, rsp
0x180005853  mov     [rbp+50h+var_50], rax
0x180005857  mov     rbx, [r9]
0x18000585a  xor     eax, eax
0x18000585c  mov     r14, cs:gBfeObjMgr
0x180005863  xorps   xmm0, xmm0
0x180005866  mov     [rbp+50h+var_A8], rax
0x18000586a  xor     r12d, r12d
0x18000586d  movsxd  rax, ecx
0x180005870  xor     r13d, r13d
0x180005873  movups  [rbp+50h+var_C8], xmm0
0x180005877  mov     rdi, r9
0x18000587a  mov     r15, r8
0x18000587d  imul    rsi, rax, 198h
0x180005884  movups  [rbp+50h+var_B8], xmm0
0x180005888  mov     [rbp+50h+hKey], rdx
0x18000588c  mov     [rsp+150h+var_E0], r12d
0x180005891  mov     [rsp+150h+var_D8], r13
0x180005896  mov     dword ptr [rbp+50h+var_C8], ecx
0x180005899  call    BfeObjectTypeIdIsValid
0x18000589e  test    eax, eax
0x1800058a0  jz      loc_1800059F8
0x1800058a6  mov     rcx, [rsi+r14+30h]
0x1800058ab  lea     r9, [rbp+50h+var_C8+8]
0x1800058af  lea     r8, [rbp+50h+var_B8]
0x1800058b3  mov     rdx, rbx
0x1800058b6  call    WfpMidlObjectEncode
0x1800058bb  mov     rbx, rax
0x1800058be  test    rax, rax
0x1800058c1  jnz     loc_180005A02
0x1800058c7  mov     rcx, [rdi+8]; SecurityDescriptor
0x1800058cb  test    rcx, rcx
0x1800058ce  jz      short loc_1800058E1
0x1800058d0  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800058d6  mov     dword ptr [rbp+50h+var_B8+8], eax
0x1800058d9  mov     rax, [rdi+8]
0x1800058dd  mov     [rbp+50h+var_A8], rax
0x1800058e1  lea     r9, [rsp+150h+var_E0]
0x1800058e6  lea     r8, [rsp+150h+var_D8]
0x1800058eb  lea     rdx, [rbp+50h+var_C8]
0x1800058ef  lea     rcx, BFE_PERSISTENT_OBJECT_MARSHAL_Encode
0x1800058f6  call    WfpMidlObjectEncode
0x1800058fb  mov     r12d, [rsp+150h+var_E0]
0x180005900  mov     rbx, rax
0x180005903  mov     r13, [rsp+150h+var_D8]
0x180005908  lea     rcx, [rbp+50h+var_B8]
0x18000590c  call    WfpMemFree
0x180005911  test    rbx, rbx
0x180005914  jnz     loc_180005A16
0x18000591a  movzx   ecx, byte ptr [r15+0Eh]
0x18000591f  movzx   edx, byte ptr [r15+0Dh]
0x180005924  movzx   r8d, byte ptr [r15+0Ch]
0x180005929  movzx   eax, byte ptr [r15+0Fh]
0x18000592e  movzx   r10d, byte ptr [r15+0Bh]
0x180005933  movzx   r11d, byte ptr [r15+0Ah]
0x180005938  movzx   ebx, byte ptr [r15+9]
0x18000593d  movzx   edi, byte ptr [r15+8]
0x180005942  movzx   esi, word ptr [r15+6]
0x180005947  movzx   r14d, word ptr [r15+4]
0x18000594c  mov     r9d, [r15]
0x18000594f  mov     [rsp+150h+var_E8], eax
0x180005953  mov     [rsp+150h+var_F0], ecx
0x180005957  lea     rcx, [rbp+50h+pszDest]; pszDest
0x18000595b  mov     [rsp+150h+var_F8], edx
0x18000595f  mov     edx, 27h ; '''; cchDest
0x180005964  mov     [rsp+150h+var_100], r8d
0x180005969  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180005970  mov     [rsp+150h+var_108], r10d
0x180005975  mov     [rsp+150h+var_110], r11d
0x18000597a  mov     [rsp+150h+var_118], ebx
0x18000597e  mov     [rsp+150h+var_120], edi
0x180005982  mov     [rsp+150h+cbData], esi
0x180005986  mov     dword ptr [rsp+150h+lpData], r14d
0x18000598b  call    StringCchPrintfW
0x180005990  call    BfeCallGetSysTxn
0x180005995  mov     rcx, [rbp+50h+hKey]; hKey
0x180005999  lea     rdx, [rbp+50h+pszDest]; lpValueName
0x18000599d  xor     ebx, ebx
0x18000599f  mov     [rsp+150h+cbData], r12d; cbData
0x1800059a4  xor     r8d, r8d; Reserved
0x1800059a7  mov     [rsp+150h+lpData], r13; lpData
0x1800059ac  lea     r9d, [rbx+3]; dwType
0x1800059b0  call    cs:__imp_RegSetValueExW
0x1800059b6  test    eax, eax
0x1800059b8  jnz     short loc_180005A22
0x1800059ba  xor     ecx, ecx
0x1800059bc  call    BfeRegCloseKey
0x1800059c1  test    rbx, rbx
0x1800059c4  jnz     short loc_180005A36
0x1800059c6  lea     rcx, [rsp+150h+var_D8]
0x1800059cb  call    WfpMemFree
0x1800059d0  test    rbx, rbx
0x1800059d3  jnz     short loc_180005A42
0x1800059d5  mov     rax, rbx
0x1800059d8  mov     rcx, [rbp+50h+var_50]
0x1800059dc  xor     rcx, rsp; StackCookie
0x1800059df  call    __security_check_cookie
0x1800059e4  add     rsp, 118h
0x1800059eb  pop     r15
0x1800059ed  pop     r14
0x1800059ef  pop     r13
0x1800059f1  pop     r12
0x1800059f3  pop     rdi
0x1800059f4  pop     rsi
0x1800059f5  pop     rbx
0x1800059f6  pop     rbp
0x1800059f7  retn
0x1800059f8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800059fd  jmp     loc_1800058A6
0x180005a02  lea     rdx, aBfeobjectencod; "BfeObjectEncodePublicState"
0x180005a09  mov     rcx, rax
0x180005a0c  call    WfpReportError
0x180005a11  jmp     loc_180005908
0x180005a16  lea     rdx, aBfedbobjectenc; "BfeDbObjectEncode"
0x180005a1d  jmp     loc_18008856A
0x180005a22  mov     r8d, eax
0x180005a25  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180005a2c  call    WfpReportSysErrorAsWinError
0x180005a31  mov     rbx, rax
0x180005a34  jmp     short loc_1800059BA
0x180005a36  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x180005a3d  jmp     loc_18008856A
0x180005a42  lea     rdx, aBfedbsetobject; "BfeDbSetObjectState"
0x180005a49  mov     rcx, rbx
0x180005a4c  call    WfpReportError
0x180005a51  jmp     short loc_1800059D5
0x18008856a  mov     rcx, rbx
0x18008856d  call    WfpReportError
0x180088572  nop
0x180088573  jmp     loc_1800059C6
```

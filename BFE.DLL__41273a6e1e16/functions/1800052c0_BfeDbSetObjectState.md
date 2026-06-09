# BfeDbSetObjectState

- ea: `0x1800052c0`
- end: `0x1800054f0`
- name: `BfeDbSetObjectState`
- size: `560`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004f04`
- `0x18001ead0`
- `0x180068614`

## callees

- `0x180004070`
- `0x1800048a8`
- `0x180005238`
- `0x1800052c0`
- `0x1800057e4`
- `0x18000e7e0`
- `0x18000ecf0`
- `0x180012d8c`
- `0x1800197d0`
- `0x1800592f4`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180005360`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180005360`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005446`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005446`

## string_xrefs

- `0x1800054c2`: `RegSetValueExW`
- `0x1800054d3`: `BfeRegSetBinary`

## pseudocode

```c
__int64 __fastcall BfeDbSetObjectState(int a1, HKEY a2, unsigned int *a3, __int64 *a4)
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
  v10 = 408LL * a1;
  v23 = 0;
  hKey = a2;
  v19 = 0;
  v20 = 0;
  LODWORD(v22) = a1;
  if ( !(unsigned int)BfeObjectTypeIdIsValid() )
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
0x1800052c0  push    rbp
0x1800052c2  push    rbx
0x1800052c3  push    rsi
0x1800052c4  push    rdi
0x1800052c5  push    r12
0x1800052c7  push    r13
0x1800052c9  push    r14
0x1800052cb  push    r15
0x1800052cd  lea     rbp, [rsp-18h]
0x1800052d2  sub     rsp, 118h
0x1800052d9  mov     rax, cs:__security_cookie
0x1800052e0  xor     rax, rsp
0x1800052e3  mov     [rbp+50h+var_50], rax
0x1800052e7  mov     rbx, [r9]
0x1800052ea  xor     eax, eax
0x1800052ec  mov     r14, cs:gBfeObjMgr
0x1800052f3  xorps   xmm0, xmm0
0x1800052f6  mov     [rbp+50h+var_A8], rax
0x1800052fa  xor     r12d, r12d
0x1800052fd  movsxd  rax, ecx
0x180005300  xor     r13d, r13d
0x180005303  movups  [rbp+50h+var_C8], xmm0
0x180005307  mov     rdi, r9
0x18000530a  mov     r15, r8
0x18000530d  imul    rsi, rax, 198h
0x180005314  movups  [rbp+50h+var_B8], xmm0
0x180005318  mov     [rbp+50h+hKey], rdx
0x18000531c  mov     [rsp+150h+var_E0], r12d
0x180005321  mov     [rsp+150h+var_D8], r13
0x180005326  mov     dword ptr [rbp+50h+var_C8], ecx
0x180005329  call    BfeObjectTypeIdIsValid
0x18000532e  test    eax, eax
0x180005330  jz      loc_180005495
0x180005336  mov     rcx, [rsi+r14+30h]
0x18000533b  lea     r9, [rbp+50h+var_C8+8]
0x18000533f  lea     r8, [rbp+50h+var_B8]
0x180005343  mov     rdx, rbx
0x180005346  call    WfpMidlObjectEncode
0x18000534b  mov     rbx, rax
0x18000534e  test    rax, rax
0x180005351  jnz     loc_18000549F
0x180005357  mov     rcx, [rdi+8]; SecurityDescriptor
0x18000535b  test    rcx, rcx
0x18000535e  jz      short loc_180005377
0x180005360  call    cs:__imp_RtlLengthSecurityDescriptor
0x180005367  nop     dword ptr [rax+rax+00h]
0x18000536c  mov     dword ptr [rbp+50h+var_B8+8], eax
0x18000536f  mov     rax, [rdi+8]
0x180005373  mov     [rbp+50h+var_A8], rax
0x180005377  lea     r9, [rsp+150h+var_E0]
0x18000537c  lea     r8, [rsp+150h+var_D8]
0x180005381  lea     rdx, [rbp+50h+var_C8]
0x180005385  lea     rcx, BFE_PERSISTENT_OBJECT_MARSHAL_Encode
0x18000538c  call    WfpMidlObjectEncode
0x180005391  mov     r12d, [rsp+150h+var_E0]
0x180005396  mov     rbx, rax
0x180005399  mov     r13, [rsp+150h+var_D8]
0x18000539e  lea     rcx, [rbp+50h+var_B8]
0x1800053a2  call    WfpMemFree
0x1800053a7  test    rbx, rbx
0x1800053aa  jnz     loc_1800054B3
0x1800053b0  movzx   ecx, byte ptr [r15+0Eh]
0x1800053b5  movzx   edx, byte ptr [r15+0Dh]
0x1800053ba  movzx   r8d, byte ptr [r15+0Ch]
0x1800053bf  movzx   eax, byte ptr [r15+0Fh]
0x1800053c4  movzx   r10d, byte ptr [r15+0Bh]
0x1800053c9  movzx   r11d, byte ptr [r15+0Ah]
0x1800053ce  movzx   ebx, byte ptr [r15+9]
0x1800053d3  movzx   edi, byte ptr [r15+8]
0x1800053d8  movzx   esi, word ptr [r15+6]
0x1800053dd  movzx   r14d, word ptr [r15+4]
0x1800053e2  mov     r9d, [r15]
0x1800053e5  mov     [rsp+150h+var_E8], eax
0x1800053e9  mov     [rsp+150h+var_F0], ecx
0x1800053ed  lea     rcx, [rbp+50h+pszDest]; pszDest
0x1800053f1  mov     [rsp+150h+var_F8], edx
0x1800053f5  mov     edx, 27h ; '''; cchDest
0x1800053fa  mov     [rsp+150h+var_100], r8d
0x1800053ff  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180005406  mov     [rsp+150h+var_108], r10d
0x18000540b  mov     [rsp+150h+var_110], r11d
0x180005410  mov     [rsp+150h+var_118], ebx
0x180005414  mov     [rsp+150h+var_120], edi
0x180005418  mov     [rsp+150h+cbData], esi
0x18000541c  mov     dword ptr [rsp+150h+lpData], r14d
0x180005421  call    StringCchPrintfW
0x180005426  call    BfeCallGetSysTxn
0x18000542b  mov     rcx, [rbp+50h+hKey]; hKey
0x18000542f  lea     rdx, [rbp+50h+pszDest]; lpValueName
0x180005433  xor     ebx, ebx
0x180005435  mov     [rsp+150h+cbData], r12d; cbData
0x18000543a  xor     r8d, r8d; Reserved
0x18000543d  mov     [rsp+150h+lpData], r13; lpData
0x180005442  lea     r9d, [rbx+3]; dwType
0x180005446  call    cs:__imp_RegSetValueExW
0x18000544d  nop     dword ptr [rax+rax+00h]
0x180005452  test    eax, eax
0x180005454  jnz     short loc_1800054BF
0x180005456  xor     ecx, ecx
0x180005458  call    BfeRegCloseKey
0x18000545d  test    rbx, rbx
0x180005460  jnz     short loc_1800054D3
0x180005462  lea     rcx, [rsp+150h+var_D8]
0x180005467  call    WfpMemFree
0x18000546c  test    rbx, rbx
0x18000546f  jnz     short loc_1800054DF
0x180005471  mov     rax, rbx
0x180005474  mov     rcx, [rbp+50h+var_50]
0x180005478  xor     rcx, rsp; StackCookie
0x18000547b  call    __security_check_cookie
0x180005480  add     rsp, 118h
0x180005487  pop     r15
0x180005489  pop     r14
0x18000548b  pop     r13
0x18000548d  pop     r12
0x18000548f  pop     rdi
0x180005490  pop     rsi
0x180005491  pop     rbx
0x180005492  pop     rbp
0x180005493  retn
0x180005495  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000549a  jmp     loc_180005336
0x18000549f  lea     rdx, aBfeobjectencod; "BfeObjectEncodePublicState"
0x1800054a6  mov     rcx, rax
0x1800054a9  call    WfpReportError
0x1800054ae  jmp     loc_18000539E
0x1800054b3  lea     rdx, aBfedbobjectenc; "BfeDbObjectEncode"
0x1800054ba  jmp     loc_18008B568
0x1800054bf  mov     r8d, eax
0x1800054c2  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x1800054c9  call    WfpReportSysErrorAsWinError
0x1800054ce  mov     rbx, rax
0x1800054d1  jmp     short loc_180005456
0x1800054d3  lea     rdx, aBferegsetbinar; "BfeRegSetBinary"
0x1800054da  jmp     loc_18008B568
0x1800054df  lea     rdx, aBfedbsetobject; "BfeDbSetObjectState"
0x1800054e6  mov     rcx, rbx
0x1800054e9  call    WfpReportError
0x1800054ee  jmp     short loc_180005471
0x18008b568  mov     rcx, rbx
0x18008b56b  call    WfpReportError
0x18008b570  nop
0x18008b571  jmp     loc_180005462
```

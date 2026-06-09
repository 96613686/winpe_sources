# FSMDeviceWatcher::IsMatchingAssociatedPackagedApp(ushort const *,ushort const *,bool *)

- ea: `0x1800141c4`
- end: `0x180014404`
- name: `?IsMatchingAssociatedPackagedApp@FSMDeviceWatcher@@SAJPEBG0PEA_N@Z`
- size: `576`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWCH lpString1, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c78`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d3b0`
- `0x18000d3d8`
- `0x1800141c4`
- `0x180017e78`
- `0x180017ec4`
- `0x180040914`
- `0x180041160`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800143a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800143a8`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::IsMatchingAssociatedPackagedApp(
        LPCWSTR pszDeviceInterface,
        const char *lpString1,
        bool *a3)
{
  int v6; // r8d
  const char *v7; // rax
  const char *v8; // r9
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const WCHAR *v12; // rbp
  unsigned __int8 Level; // al
  int v14; // r8d
  int v15; // ecx
  unsigned int v17[4]; // [rsp+30h] [rbp-D8h] BYREF
  WCHAR String2[72]; // [rsp+40h] [rbp-C8h] BYREF

  memset_0(String2, 0, 0x84u);
  v17[0] = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v7 = lpString1;
    LODWORD(v8) = (_DWORD)pszDeviceInterface;
    if ( !lpString1 )
      v7 = L"<nullptr>";
    if ( !pszDeviceInterface )
      v8 = L"<nullptr>";
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 27), 83, v6, (_DWORD)v8, (__int64)v7);
  }
  if ( !pszDeviceInterface )
  {
    v9 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_20;
    v11 = 84;
    goto LABEL_19;
  }
  if ( !lpString1 )
  {
    v9 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_20;
    v11 = 85;
    goto LABEL_19;
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        0,
        -2147467261);
    goto LABEL_20;
  }
  *a3 = 0;
  v12 = FSGetPfnFromTaggedPfn((LPCWCH)lpString1);
  if ( !v12 )
  {
    v9 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_20;
    v11 = 87;
LABEL_19:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, 0, v10);
LABEL_20:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 90, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, v9);
    return v9;
  }
  v9 = 0;
  FSGetDeviceInterfaceProperty(
    pszDeviceInterface,
    (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn,
    (PBYTE)String2,
    0x82u,
    v17);
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v15 >= 0 )
  {
    if ( Level >= 8u )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 27), 89, v14, (_DWORD)v12, (__int64)String2);
    *a3 = CompareStringOrdinal(v12, -1, String2, -1, 1) == 2;
  }
  else if ( Level >= 8u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 88, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27), 91, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, 0, *a3);
  return v9;
}

```

## disassembly

```asm
0x1800141c4  push    rbx
0x1800141c6  push    rbp
0x1800141c7  push    rsi
0x1800141c8  push    rdi
0x1800141c9  push    r14
0x1800141cb  sub     rsp, 0E0h
0x1800141d2  mov     rax, cs:__security_cookie
0x1800141d9  xor     rax, rsp
0x1800141dc  mov     [rsp+108h+var_38], rax
0x1800141e4  mov     rsi, r8
0x1800141e7  mov     rbx, rdx
0x1800141ea  mov     r14, rcx
0x1800141ed  xor     edx, edx; Val
0x1800141ef  mov     r8d, 84h; Size
0x1800141f5  lea     rcx, [rsp+108h+String2]; void *
0x1800141fa  call    memset_0
0x1800141ff  mov     [rsp+108h+var_D8], 0
0x180014207  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001420c  cmp     al, 8
0x18001420e  jb      short loc_180014248
0x180014210  test    rbx, rbx
0x180014213  lea     rcx, aNullptr; "<nullptr>"
0x18001421a  mov     rax, rbx
0x18001421d  mov     r9, r14
0x180014220  cmovz   rax, rcx
0x180014224  mov     edx, 53h ; 'S'
0x180014229  test    r14, r14
0x18001422c  mov     qword ptr [rsp+108h+bIgnoreCase], rax
0x180014231  cmovz   r9, rcx
0x180014235  mov     rcx, cs:WPP_GLOBAL_Control
0x18001423c  mov     rcx, [rcx+0D8h]
0x180014243  call    WPP_SF_SS
0x180014248  lea     rdi, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18001424f  test    r14, r14
0x180014252  jnz     short loc_18001426A
0x180014254  mov     ecx, 80070057h
0x180014259  mov     ebx, ecx
0x18001425b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014260  cmp     al, 1
0x180014262  jb      short loc_1800142E2
0x180014264  lea     edx, [r14+54h]
0x180014268  jmp     short loc_1800142C8
0x18001426a  test    rbx, rbx
0x18001426d  jnz     short loc_180014286
0x18001426f  mov     ecx, 80070057h
0x180014274  mov     ebx, ecx
0x180014276  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001427b  cmp     al, 1
0x18001427d  jb      short loc_1800142E2
0x18001427f  mov     edx, 55h ; 'U'
0x180014284  jmp     short loc_1800142C8
0x180014286  test    rsi, rsi
0x180014289  jnz     short loc_1800142A2
0x18001428b  mov     ebx, 80004003h
0x180014290  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014295  cmp     al, 1
0x180014297  jb      short loc_1800142E2
0x180014299  lea     edx, [rsi+56h]
0x18001429c  mov     [rsp+108h+bIgnoreCase], ebx
0x1800142a0  jmp     short loc_1800142CC
0x1800142a2  mov     rcx, rbx; lpString1
0x1800142a5  mov     byte ptr [rsi], 0
0x1800142a8  call    ?FSGetPfnFromTaggedPfn@@YAPEBGPEBG@Z; FSGetPfnFromTaggedPfn(ushort const *)
0x1800142ad  mov     rbp, rax
0x1800142b0  test    rax, rax
0x1800142b3  jnz     short loc_180014312
0x1800142b5  mov     ecx, 80070057h
0x1800142ba  mov     ebx, ecx
0x1800142bc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800142c1  cmp     al, 1
0x1800142c3  jb      short loc_1800142E2
0x1800142c5  lea     edx, [rbp+57h]
0x1800142c8  mov     [rsp+108h+bIgnoreCase], ecx
0x1800142cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142d3  xor     r9d, r9d
0x1800142d6  mov     r8, rdi
0x1800142d9  mov     rcx, [rcx+10h]
0x1800142dd  call    WPP_SF_qD
0x1800142e2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800142e7  cmp     al, 1
0x1800142e9  jb      loc_1800143E4
0x1800142ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142f6  mov     edx, 5Ah ; 'Z'
0x1800142fb  mov     r9d, ebx
0x1800142fe  mov     r8, rdi
0x180014301  mov     rcx, [rcx+0D8h]
0x180014308  call    WPP_SF_d
0x18001430d  jmp     loc_1800143E4
0x180014312  lea     rax, [rsp+108h+var_D8]
0x180014317  mov     r9d, 82h; unsigned int
0x18001431d  lea     r8, [rsp+108h+String2]; PropertyBuffer
0x180014322  mov     qword ptr [rsp+108h+bIgnoreCase], rax; unsigned int *
0x180014327  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_ConfigAppPfn; PropertyKey
0x18001432e  mov     rcx, r14; pszDeviceInterface
0x180014331  xor     ebx, ebx
0x180014333  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180014338  mov     ecx, eax
0x18001433a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001433f  lea     rdi, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180014346  test    ecx, ecx
0x180014348  jns     short loc_180014369
0x18001434a  cmp     al, 8
0x18001434c  jb      short loc_1800143B6
0x18001434e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014355  lea     edx, [rbx+58h]
0x180014358  mov     r8, rdi
0x18001435b  mov     rcx, [rcx+0D8h]
0x180014362  call    WPP_SF_
0x180014367  jmp     short loc_1800143B6
0x180014369  cmp     al, 8
0x18001436b  jb      short loc_180014392
0x18001436d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014374  lea     rax, [rsp+108h+String2]
0x180014379  mov     edx, 59h ; 'Y'
0x18001437e  mov     qword ptr [rsp+108h+bIgnoreCase], rax
0x180014383  mov     r9, rbp
0x180014386  mov     rcx, [rcx+0D8h]
0x18001438d  call    WPP_SF_SS
0x180014392  or      edx, 0FFFFFFFFh; cchCount1
0x180014395  mov     [rsp+108h+bIgnoreCase], 1; bIgnoreCase
0x18001439d  mov     r9d, edx; cchCount2
0x1800143a0  lea     r8, [rsp+108h+String2]; lpString2
0x1800143a5  mov     rcx, rbp; lpString1
0x1800143a8  call    cs:__imp_CompareStringOrdinal
0x1800143ae  cmp     eax, 2
0x1800143b1  setz    al
0x1800143b4  mov     [rsi], al
0x1800143b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800143bb  cmp     al, 8
0x1800143bd  jb      short loc_1800143E4
0x1800143bf  movzx   ecx, byte ptr [rsi]
0x1800143c2  mov     edx, 5Bh ; '['
0x1800143c7  mov     [rsp+108h+bIgnoreCase], ecx
0x1800143cb  mov     r9d, ebx
0x1800143ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d5  mov     r8, rdi
0x1800143d8  mov     rcx, [rcx+0D8h]
0x1800143df  call    WPP_SF_Dd
0x1800143e4  mov     eax, ebx
0x1800143e6  mov     rcx, [rsp+108h+var_38]
0x1800143ee  xor     rcx, rsp; StackCookie
0x1800143f1  call    __security_check_cookie
0x1800143f6  add     rsp, 0E0h
0x1800143fd  pop     r14
0x1800143ff  pop     rdi
0x180014400  pop     rsi
0x180014401  pop     rbp
0x180014402  pop     rbx
0x180014403  retn
```

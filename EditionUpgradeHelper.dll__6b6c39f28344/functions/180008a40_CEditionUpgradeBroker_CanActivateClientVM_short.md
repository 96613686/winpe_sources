# CEditionUpgradeBroker::CanActivateClientVM(short *)

- ea: `0x180008a40`
- end: `0x180008ba3`
- name: `?CanActivateClientVM@CEditionUpgradeBroker@@UEAAJPEAF@Z`
- size: `355`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008a40`
- `0x180008c60`
- `0x180009978`
- `0x18000b49c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008afa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008afa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b77`
- `CLIPC!ClipGetLicenseAndPolicyForPfn` at `0x180008b3f`
- `CLIPC!ClipGetLicenseAndPolicyForPfn` at `0x180008b3f`

## string_xrefs

- `0x180008a60`: `Virtualization-DesktopAccess`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::CanActivateClientVM(CEditionUpgradeBroker *this, __int16 *a2)
{
  PBYTE v2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rcx
  HRESULT v6; // eax
  __int64 v7; // rcx
  int v8; // esi
  PBYTE v9; // rcx
  __int16 v10; // ax
  int v12; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+44h] [rbp-1Ch] BYREF
  PBYTE ppbValue; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-10h]
  UINT pcbValue; // [rsp+98h] [rbp+38h] BYREF
  SLDATATYPE peDataType; // [rsp+A0h] [rbp+40h] BYREF
  int v18; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  v15[0] = L"Virtualization-InheritedActivation";
  v15[1] = L"Virtualization-DesktopAccess";
  v18 = 0;
  v13 = 0;
  v12 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_3;
  }
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  v6 = SLGetWindowsInformation(L"Clip-SubscriptionPFN", &peDataType, &pcbValue, &ppbValue);
  v4 = v6;
  if ( v6 >= 0 )
  {
    if ( peDataType == SL_DATA_SZ && pcbValue >= 2 && (pcbValue & 1) == 0 )
    {
      v2 = ppbValue;
      ppbValue = 0;
      goto LABEL_13;
    }
    v4 = -2147418113;
    v7 = 2147549183LL;
  }
  else
  {
    v7 = (unsigned int)v6;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( ppbValue )
    LocalFree(ppbValue);
  if ( (v4 & 0x80000000) == 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = 0;
      if ( v2 )
        v9 = v2;
      if ( (int)ClipGetLicenseAndPolicyForPfn(v9, v15[v8], &v13, 4, &v12, &v18, 0) >= 0 )
      {
        if ( v18 != 4 || v12 != 4 )
        {
          v4 = -2147418113;
          v5 = 2147549183LL;
          goto LABEL_4;
        }
        if ( v13 == 1 )
          break;
      }
      if ( (unsigned int)++v8 >= 2 )
      {
        v10 = 0;
LABEL_25:
        *a2 = v10;
        goto LABEL_26;
      }
    }
    v10 = -1;
    goto LABEL_25;
  }
LABEL_3:
  v5 = v4;
LABEL_4:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_26:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
    LocalFree(v2);
  return v4;
}

```

## disassembly

```asm
0x180008a40  mov     [rsp-28h+arg_0], rbx
0x180008a45  push    rbp
0x180008a46  push    rsi
0x180008a47  push    rdi
0x180008a48  push    r12
0x180008a4a  push    r14
0x180008a4c  mov     rbp, rsp
0x180008a4f  sub     rsp, 60h
0x180008a53  xor     ebx, ebx
0x180008a55  lea     rax, aVirtualization_0; "Virtualization-InheritedActivation"
0x180008a5c  mov     [rbp+var_10], rax
0x180008a60  lea     rax, aVirtualization; "Virtualization-DesktopAccess"
0x180008a67  mov     [rbp+var_8], rax
0x180008a6b  mov     r14, rdx
0x180008a6e  mov     [rbp+arg_18], ebx
0x180008a71  mov     [rbp+var_1C], ebx
0x180008a74  mov     [rbp+var_20], ebx
0x180008a77  test    rdx, rdx
0x180008a7a  jnz     short loc_180008A8D
0x180008a7c  mov     edi, 80070057h
0x180008a81  mov     ecx, edi
0x180008a83  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008a88  jmp     loc_180008B68
0x180008a8d  lea     r9, [rbp+ppbValue]; ppbValue
0x180008a91  mov     [rbp+peDataType], ebx
0x180008a94  lea     r8, [rbp+pcbValue]; pcbValue
0x180008a98  mov     [rbp+pcbValue], ebx
0x180008a9b  lea     rdx, [rbp+peDataType]; peDataType
0x180008a9f  mov     [rbp+ppbValue], rbx
0x180008aa3  lea     rcx, pwszValueName; "Clip-SubscriptionPFN"
0x180008aaa  call    SLGetWindowsInformation
0x180008aaf  mov     edi, eax
0x180008ab1  mov     r12d, 8000FFFFh
0x180008ab7  test    eax, eax
0x180008ab9  jns     short loc_180008ABF
0x180008abb  mov     ecx, eax
0x180008abd  jmp     short loc_180008AE5
0x180008abf  cmp     [rbp+peDataType], 1
0x180008ac3  jnz     short loc_180008ADF
0x180008ac5  cmp     [rbp+pcbValue], 2
0x180008ac9  jb      short loc_180008ADF
0x180008acb  test    byte ptr [rbp+pcbValue], 1
0x180008acf  jnz     short loc_180008ADF
0x180008ad1  mov     rbx, [rbp+ppbValue]
0x180008ad5  mov     [rbp+ppbValue], 0
0x180008add  jmp     short loc_180008AEA
0x180008adf  mov     edi, r12d
0x180008ae2  mov     ecx, r12d
0x180008ae5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008aea  mov     ecx, edi
0x180008aec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008af1  mov     rcx, [rbp+ppbValue]; hMem
0x180008af5  test    rcx, rcx
0x180008af8  jz      short loc_180008B00
0x180008afa  call    cs:__imp_LocalFree
0x180008b00  test    edi, edi
0x180008b02  js      loc_180008A81
0x180008b08  xor     esi, esi
0x180008b0a  xor     ecx, ecx
0x180008b0c  mov     [rsp+60h+var_30], 0
0x180008b14  lea     rax, [rbp+arg_18]
0x180008b18  movsxd  rdx, esi
0x180008b1b  mov     [rsp+60h+var_38], rax
0x180008b20  lea     r8, [rbp+var_1C]
0x180008b24  lea     rax, [rbp+var_20]
0x180008b28  test    rbx, rbx
0x180008b2b  mov     r9d, 4
0x180008b31  mov     [rsp+60h+var_40], rax
0x180008b36  mov     rdx, [rbp+rdx*8+var_10]
0x180008b3b  cmovnz  rcx, rbx
0x180008b3f  call    cs:__imp_ClipGetLicenseAndPolicyForPfn
0x180008b45  test    eax, eax
0x180008b47  js      short loc_180008B5B
0x180008b49  cmp     [rbp+arg_18], 4
0x180008b4d  jnz     short loc_180008B98
0x180008b4f  cmp     [rbp+var_20], 4
0x180008b53  jnz     short loc_180008B98
0x180008b55  cmp     [rbp+var_1C], 1
0x180008b59  jz      short loc_180008B93
0x180008b5b  inc     esi
0x180008b5d  cmp     esi, 2
0x180008b60  jb      short loc_180008B0A
0x180008b62  xor     eax, eax
0x180008b64  mov     [r14], ax
0x180008b68  mov     ecx, edi
0x180008b6a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008b6f  test    rbx, rbx
0x180008b72  jz      short loc_180008B7D
0x180008b74  mov     rcx, rbx; hMem
0x180008b77  call    cs:__imp_LocalFree
0x180008b7d  mov     rbx, [rsp+60h+arg_0]
0x180008b85  mov     eax, edi
0x180008b87  add     rsp, 60h
0x180008b8b  pop     r14
0x180008b8d  pop     r12
0x180008b8f  pop     rdi
0x180008b90  pop     rsi
0x180008b91  pop     rbp
0x180008b92  retn
0x180008b93  or      eax, 0FFFFFFFFh
0x180008b96  jmp     short loc_180008B64
0x180008b98  mov     edi, r12d
0x180008b9b  mov     ecx, r12d
0x180008b9e  jmp     loc_180008A83
```

# CommonUtil::UtilRemoveTrustLabelAceForObject(_SE_OBJECT_TYPE,void *)

- ea: `0x1400108f4`
- end: `0x140010aa5`
- name: `?UtilRemoveTrustLabelAceForObject@CommonUtil@@YAJW4_SE_OBJECT_TYPE@@PEAX@Z`
- size: `433`
- prototype: `__int64 __fastcall(SE_OBJECT_TYPE ObjectType, HANDLE handle, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14008a040`
- `0x14008af18`

## callees

- `0x1400108f4`
- `0x140014b10`
- `0x140017738`
- `0x140018dc5`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010a42`
- `KERNEL32!LocalFree` at `0x140010a42`
- `KERNEL32!GetLastError` at `0x1400109df`
- `KERNEL32!GetLastError` at `0x1400109df`
- `ADVAPI32!SetSecurityInfo` at `0x140010a22`
- `ADVAPI32!SetSecurityInfo` at `0x140010a22`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1400109d0`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1400109d0`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRemoveTrustLabelAceForObject(
        SE_OBJECT_TYPE ObjectType,
        HANDLE handle,
        const wchar_t *a3)
{
  __int64 v5; // rsi
  const struct std::nothrow_t *v6; // rdx
  signed int LastFailure; // edi
  signed int LastError; // eax
  signed int v9; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  PACL pSacl; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-20h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+58h] [rbp-18h] BYREF
  WINBOOL bSaclPresent; // [rsp+5Ch] [rbp-14h] BYREF

  SecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  StringSecurityDescriptor = 0;
  LastFailure = CommonUtil::NewSprintfW((CommonUtil *)&StringSecurityDescriptor, (wchar_t **)L"S:", a3);
  if ( LastFailure >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW_0(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      LastFailure = 0;
    else
      LastFailure = HrGetLastFailure();
    if ( LastFailure >= 0 )
    {
      if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        LastError = GetLastError();
        LastFailure = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          LastFailure = LastError;
      }
      if ( LastFailure >= 0 )
      {
        v9 = SetSecurityInfo(handle, ObjectType, 0x80u, 0, 0, 0, pSacl);
        LastFailure = (unsigned __int16)v9 | 0x80070000;
        if ( v9 <= 0 )
          LastFailure = v9;
      }
    }
    v5 = WPP_GLOBAL_Control;
  }
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && (*(_BYTE *)(v5 + 28) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(v5 + 16), 58, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids, (unsigned int)LastFailure);
  if ( StringSecurityDescriptor )
    operator delete((void *)StringSecurityDescriptor, v6);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x1400108f4  mov     [rsp-28h+arg_10], rsi
0x1400108f9  push    rbp
0x1400108fa  push    rdi
0x1400108fb  push    r13
0x1400108fd  push    r14
0x1400108ff  push    r15
0x140010901  mov     rbp, rsp
0x140010904  sub     rsp, 70h
0x140010908  mov     rax, cs:__security_cookie
0x14001090f  xor     rax, rsp
0x140010912  mov     [rbp+var_10], rax
0x140010916  mov     r15, rdx
0x140010919  mov     [rbp+SecurityDescriptor], 0
0x140010921  mov     r14d, ecx
0x140010924  mov     [rbp+pSacl], 0
0x14001092c  mov     [rbp+bSaclPresent], 0
0x140010933  mov     [rbp+bSaclDefaulted], 0
0x14001093a  mov     rsi, cs:WPP_GLOBAL_Control
0x140010941  lea     r13, WPP_GLOBAL_Control
0x140010948  cmp     rsi, r13
0x14001094b  jz      short loc_14001096F
0x14001094d  test    byte ptr [rsi+1Ch], 4
0x140010951  jz      short loc_14001096F
0x140010953  mov     rcx, [rsi+10h]
0x140010957  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x14001095e  mov     edx, 39h ; '9'
0x140010963  call    WPP_SF_
0x140010968  mov     rsi, cs:WPP_GLOBAL_Control
0x14001096f  lea     rdx, aS_0; "S:"
0x140010976  mov     [rbp+StringSecurityDescriptor], 0
0x14001097e  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x140010982  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140010987  mov     edi, eax
0x140010989  shr     eax, 1Fh
0x14001098c  test    al, al
0x14001098e  jnz     loc_140010A39
0x140010994  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x140010998  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001099c  xor     r9d, r9d; SecurityDescriptorSize
0x14001099f  lea     edx, [r9+1]; StringSDRevision
0x1400109a3  call    ConvertStringSecurityDescriptorToSecurityDescriptorW_0
0x1400109a8  test    eax, eax
0x1400109aa  jz      short loc_1400109B0
0x1400109ac  xor     edi, edi
0x1400109ae  jmp     short loc_1400109B7
0x1400109b0  call    HrGetLastFailure
0x1400109b5  mov     edi, eax
0x1400109b7  mov     eax, edi
0x1400109b9  shr     eax, 1Fh
0x1400109bc  test    al, al
0x1400109be  jnz     short loc_140010A32
0x1400109c0  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1400109c4  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x1400109c8  lea     r8, [rbp+pSacl]; pSacl
0x1400109cc  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x1400109d0  call    cs:__imp_GetSecurityDescriptorSacl
0x1400109d6  mov     esi, 80070000h
0x1400109db  test    eax, eax
0x1400109dd  jnz     short loc_1400109EF
0x1400109df  call    cs:__imp_GetLastError
0x1400109e5  movzx   edi, ax
0x1400109e8  or      edi, esi
0x1400109ea  test    eax, eax
0x1400109ec  cmovle  edi, eax
0x1400109ef  mov     eax, edi
0x1400109f1  shr     eax, 1Fh
0x1400109f4  test    al, al
0x1400109f6  jnz     short loc_140010A32
0x1400109f8  mov     rax, [rbp+pSacl]
0x1400109fc  xor     r9d, r9d; psidOwner
0x1400109ff  mov     [rsp+70h+var_40], rax; pSacl
0x140010a04  mov     r8d, 80h; SecurityInfo
0x140010a0a  mov     [rsp+70h+pDacl], 0; pDacl
0x140010a13  mov     edx, r14d; ObjectType
0x140010a16  mov     rcx, r15; handle
0x140010a19  mov     [rsp+70h+psidGroup], 0; psidGroup
0x140010a22  call    cs:__imp_SetSecurityInfo
0x140010a28  movzx   edi, ax
0x140010a2b  or      edi, esi
0x140010a2d  test    eax, eax
0x140010a2f  cmovle  edi, eax
0x140010a32  mov     rsi, cs:WPP_GLOBAL_Control
0x140010a39  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140010a3d  test    rcx, rcx
0x140010a40  jz      short loc_140010A4F
0x140010a42  call    cs:__imp_LocalFree
0x140010a48  mov     rsi, cs:WPP_GLOBAL_Control
0x140010a4f  cmp     rsi, r13
0x140010a52  jz      short loc_140010A72
0x140010a54  test    byte ptr [rsi+1Ch], 4
0x140010a58  jz      short loc_140010A72
0x140010a5a  mov     rcx, [rsi+10h]
0x140010a5e  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010a65  mov     edx, 3Ah ; ':'
0x140010a6a  mov     r9d, edi
0x140010a6d  call    WPP_SF_d
0x140010a72  cmp     [rbp+StringSecurityDescriptor], 0
0x140010a77  jz      short loc_140010A82
0x140010a79  mov     rcx, [rbp+StringSecurityDescriptor]; void *
0x140010a7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010a82  mov     eax, edi
0x140010a84  mov     rcx, [rbp+var_10]
0x140010a88  xor     rcx, rsp; StackCookie
0x140010a8b  call    __security_check_cookie
0x140010a90  mov     rsi, [rsp+70h+arg_10]
0x140010a98  add     rsp, 70h
0x140010a9c  pop     r15
0x140010a9e  pop     r14
0x140010aa0  pop     r13
0x140010aa2  pop     rdi
0x140010aa3  pop     rbp
0x140010aa4  retn
```

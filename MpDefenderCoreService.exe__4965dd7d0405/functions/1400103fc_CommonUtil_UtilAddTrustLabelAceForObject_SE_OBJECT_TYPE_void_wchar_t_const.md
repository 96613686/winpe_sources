# CommonUtil::UtilAddTrustLabelAceForObject(_SE_OBJECT_TYPE,void *,wchar_t const *)

- ea: `0x1400103fc`
- end: `0x140010597`
- name: `?UtilAddTrustLabelAceForObject@CommonUtil@@YAJW4_SE_OBJECT_TYPE@@PEAXPEB_W@Z`
- size: `411`
- prototype: `__int64 __fastcall(SE_OBJECT_TYPE ObjectType, HANDLE handle, LPCWSTR StringSecurityDescriptor, const wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14008a040`
- `0x14008af18`

## callees

- `0x1400103fc`
- `0x140017738`
- `0x140018dc5`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010540`
- `KERNEL32!LocalFree` at `0x140010540`
- `KERNEL32!GetLastError` at `0x1400104db`
- `KERNEL32!GetLastError` at `0x1400104db`
- `ADVAPI32!SetSecurityInfo` at `0x140010522`
- `ADVAPI32!SetSecurityInfo` at `0x140010522`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1400104d1`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1400104d1`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilAddTrustLabelAceForObject(
        SE_OBJECT_TYPE ObjectType,
        HANDLE handle,
        LPCWSTR StringSecurityDescriptor,
        const wchar_t *a4)
{
  signed int LastFailure; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-38h] BYREF
  PACL pSacl; // [rsp+48h] [rbp-30h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+50h] [rbp-28h] BYREF
  WINBOOL bSaclPresent; // [rsp+54h] [rbp-24h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids);
  SecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !handle || !StringSecurityDescriptor || (unsigned int)(ObjectType - 1) > 0xC )
    return 2147942487LL;
  _mm_lfence();
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
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      56,
      WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids,
      (unsigned int)LastFailure);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x1400103fc  mov     [rsp+arg_18], rbx
0x140010401  push    rsi
0x140010402  push    rdi
0x140010403  push    r15
0x140010405  sub     rsp, 60h
0x140010409  mov     rax, cs:__security_cookie
0x140010410  xor     rax, rsp
0x140010413  mov     [rsp+78h+var_20], rax
0x140010418  mov     rbx, r8
0x14001041b  mov     rdi, rdx
0x14001041e  mov     esi, ecx
0x140010420  mov     rcx, cs:WPP_GLOBAL_Control
0x140010427  lea     r15, WPP_GLOBAL_Control
0x14001042e  cmp     rcx, r15
0x140010431  jz      short loc_14001044E
0x140010433  test    byte ptr [rcx+1Ch], 4
0x140010437  jz      short loc_14001044E
0x140010439  mov     rcx, [rcx+10h]
0x14001043d  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010444  mov     edx, 37h ; '7'
0x140010449  call    WPP_SF_
0x14001044e  mov     [rsp+78h+SecurityDescriptor], 0
0x140010457  mov     [rsp+78h+pSacl], 0
0x140010460  mov     [rsp+78h+bSaclPresent], 0
0x140010468  mov     [rsp+78h+bSaclDefaulted], 0
0x140010470  test    rdi, rdi
0x140010473  jz      loc_140010574
0x140010479  test    rbx, rbx
0x14001047c  jz      loc_140010574
0x140010482  lea     eax, [rsi-1]
0x140010485  cmp     eax, 0Ch
0x140010488  ja      loc_140010574
0x14001048e  lfence
0x140010491  xor     r9d, r9d; SecurityDescriptorSize
0x140010494  lea     r8, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x140010499  mov     rcx, rbx; StringSecurityDescriptor
0x14001049c  lea     edx, [r9+1]; StringSDRevision
0x1400104a0  call    ConvertStringSecurityDescriptorToSecurityDescriptorW_0
0x1400104a5  test    eax, eax
0x1400104a7  jz      short loc_1400104AD
0x1400104a9  xor     ebx, ebx
0x1400104ab  jmp     short loc_1400104B4
0x1400104ad  call    HrGetLastFailure
0x1400104b2  mov     ebx, eax
0x1400104b4  mov     eax, ebx
0x1400104b6  shr     eax, 1Fh
0x1400104b9  test    al, al
0x1400104bb  jnz     short loc_140010536
0x1400104bd  mov     rcx, [rsp+78h+SecurityDescriptor]; pSecurityDescriptor
0x1400104c2  lea     r9, [rsp+78h+bSaclDefaulted]; lpbSaclDefaulted
0x1400104c7  lea     r8, [rsp+78h+pSacl]; pSacl
0x1400104cc  lea     rdx, [rsp+78h+bSaclPresent]; lpbSaclPresent
0x1400104d1  call    cs:__imp_GetSecurityDescriptorSacl
0x1400104d7  test    eax, eax
0x1400104d9  jnz     short loc_1400104EF
0x1400104db  call    cs:__imp_GetLastError
0x1400104e1  movzx   ebx, ax
0x1400104e4  or      ebx, 80070000h
0x1400104ea  test    eax, eax
0x1400104ec  cmovle  ebx, eax
0x1400104ef  mov     eax, ebx
0x1400104f1  shr     eax, 1Fh
0x1400104f4  test    al, al
0x1400104f6  jnz     short loc_140010536
0x1400104f8  mov     rax, [rsp+78h+pSacl]
0x1400104fd  xor     r9d, r9d; psidOwner
0x140010500  mov     [rsp+78h+var_48], rax; pSacl
0x140010505  mov     r8d, 80h; SecurityInfo
0x14001050b  mov     [rsp+78h+pDacl], 0; pDacl
0x140010514  mov     edx, esi; ObjectType
0x140010516  mov     rcx, rdi; handle
0x140010519  mov     [rsp+78h+psidGroup], 0; psidGroup
0x140010522  call    cs:__imp_SetSecurityInfo
0x140010528  movzx   ebx, ax
0x14001052b  or      ebx, 80070000h
0x140010531  test    eax, eax
0x140010533  cmovle  ebx, eax
0x140010536  mov     rcx, [rsp+78h+SecurityDescriptor]; hMem
0x14001053b  test    rcx, rcx
0x14001053e  jz      short loc_140010546
0x140010540  call    cs:__imp_LocalFree
0x140010546  mov     rcx, cs:WPP_GLOBAL_Control
0x14001054d  cmp     rcx, r15
0x140010550  jz      short loc_140010570
0x140010552  test    byte ptr [rcx+1Ch], 4
0x140010556  jz      short loc_140010570
0x140010558  mov     rcx, [rcx+10h]
0x14001055c  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010563  mov     edx, 38h ; '8'
0x140010568  mov     r9d, ebx
0x14001056b  call    WPP_SF_d
0x140010570  mov     eax, ebx
0x140010572  jmp     short loc_140010579
0x140010574  mov     eax, 80070057h
0x140010579  mov     rcx, [rsp+78h+var_20]
0x14001057e  xor     rcx, rsp; StackCookie
0x140010581  call    __security_check_cookie
0x140010586  mov     rbx, [rsp+78h+arg_18]
0x14001058e  add     rsp, 60h
0x140010592  pop     r15
0x140010594  pop     rdi
0x140010595  pop     rsi
0x140010596  retn
```

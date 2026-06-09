# ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)

- ea: `0x180012870`
- end: `0x180012d01`
- name: `?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z`
- size: `1169`
- prototype: `void __fastcall(LPCWSTR lpName, void *, void *, HANDLE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011fa8`
- `0x180012234`

## callees

- `0x180004564`
- `0x18000e82c`
- `0x18000f45c`
- `0x18000f830`
- `0x18000fb68`
- `0x180012870`
- `0x1800197b4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180012a1a`
- `KERNEL32!CreateMutexW` at `0x180012a1a`
- `KERNEL32!OpenMutexW` at `0x1800129dc`
- `KERNEL32!OpenMutexW` at `0x1800129dc`
- `KERNEL32!FreeLibrary` at `0x180012a65`
- `KERNEL32!FreeLibrary` at `0x180012a65`
- `KERNEL32!CloseHandle` at `0x1800129f8`
- `KERNEL32!CloseHandle` at `0x180012a36`
- `KERNEL32!CloseHandle` at `0x1800129f8`
- `KERNEL32!CloseHandle` at `0x180012a36`
- `KERNEL32!GetLastError` at `0x1800128c1`
- `KERNEL32!GetLastError` at `0x180012a84`
- `KERNEL32!GetLastError` at `0x180012aef`
- `KERNEL32!GetLastError` at `0x180012b59`
- `KERNEL32!GetLastError` at `0x180012bc3`
- `KERNEL32!GetLastError` at `0x180012c2d`
- `KERNEL32!GetLastError` at `0x180012c97`
- `KERNEL32!GetLastError` at `0x1800128c1`
- `KERNEL32!GetLastError` at `0x180012a84`
- `KERNEL32!GetLastError` at `0x180012aef`
- `KERNEL32!GetLastError` at `0x180012b59`
- `KERNEL32!GetLastError` at `0x180012bc3`
- `KERNEL32!GetLastError` at `0x180012c2d`
- `KERNEL32!GetLastError` at `0x180012c97`
- `ADVAPI32!GetLengthSid` at `0x1800128d9`
- `ADVAPI32!GetLengthSid` at `0x1800128d9`
- `ADVAPI32!InitializeAcl` at `0x180012903`
- `ADVAPI32!InitializeAcl` at `0x180012903`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001297a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001297a`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012958`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012958`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18001292c`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18001292c`

## string_xrefs

- `0x1800128a5`: `PrintConfigConnections`
- `0x1800129a6`: `PrintConfigConnections`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(LPCWSTR lpName, void *a2, void *a3, HANDLE *a4)
{
  size_t v8; // rbx
  __int64 v9; // r8
  ACL *v10; // rsi
  HANDLE v11; // rbx
  HANDLE MutexW; // rbx
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  unsigned int v16; // ebx
  signed int v17; // eax
  unsigned int v18; // ebx
  signed int v19; // eax
  unsigned int v20; // ebx
  signed int v21; // eax
  unsigned int v22; // ebx
  signed int v23; // eax
  unsigned int v24; // ebx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-79h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v28; // [rsp+88h] [rbp-41h]
  __int64 v29; // [rsp+90h] [rbp-39h]
  PACL pAcl[3]; // [rsp+98h] [rbp-31h] BYREF
  _QWORD v31[7]; // [rsp+B0h] [rbp-19h] BYREF
  HMODULE hLibModule; // [rsp+E8h] [rbp+1Fh]

  v29 = -2;
  Kernel32RAII::Kernel32RAII((Kernel32RAII *)v31);
  if ( !((__int64 (__fastcall *)(void *, const wchar_t *))v31[1])(a2, L"PrintConfigConnections") && GetLastError() != 52 )
  {
    v8 = GetLengthSid(a3) + 16;
    std::vector<unsigned char>::vector<unsigned char>((__int64 *)pAcl, v8, v9);
    v10 = pAcl[0];
    if ( !InitializeAcl(pAcl[0], v8, 2u) )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x1Fu,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v16);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v16);
      throw (hr_error *)pExceptionObject;
    }
    if ( !AddAccessAllowedAceEx(v10, 2u, 0, 0x10000000u, a3) )
    {
      v17 = GetLastError();
      v18 = v17;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x20u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v18);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v18);
      throw (hr_error *)pExceptionObject;
    }
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    v28 = 0;
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      v19 = GetLastError();
      v20 = v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x21u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v20);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v20);
      throw (hr_error *)pExceptionObject;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v10, 0) )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x22u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v22);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v22);
      throw (hr_error *)pExceptionObject;
    }
    v26[0] = 24;
    v26[2] = 0;
    v26[1] = pSecurityDescriptor;
    if ( !((__int64 (__fastcall *)(_QWORD *, void *, const wchar_t *))v31[0])(v26, a2, L"PrintConfigConnections") )
    {
      v23 = GetLastError();
      v24 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x23u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v24);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v24);
      throw (hr_error *)pExceptionObject;
    }
    std::vector<char>::~vector<char>((char **)pAcl);
  }
  v11 = OpenMutexW(0x10000000u, 1, lpName);
  if ( (char *)*a4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*a4);
  *a4 = v11;
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    MutexW = CreateMutexW(0, 0, lpName);
    if ( (char *)*a4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(*a4);
    *a4 = MutexW;
    if ( (((unsigned __int64)MutexW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v13 = GetLastError();
      v14 = v13;
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x24u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v14);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v14);
      throw (hr_error *)pExceptionObject;
    }
  }
  v31[6] = &ModuleRAII::`vftable';
  if ( hLibModule )
    FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180012870  push    rbp
0x180012872  push    rbx
0x180012873  push    rsi
0x180012874  push    rdi
0x180012875  push    r12
0x180012877  push    r14
0x180012879  push    r15
0x18001287b  lea     rbp, [rsp-27h]
0x180012880  sub     rsp, 0F0h
0x180012887  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18001288f  mov     rdi, r9
0x180012892  mov     r14, r8
0x180012895  mov     r12, rdx
0x180012898  mov     r15, rcx
0x18001289b  lea     rcx, [rbp+57h+var_70]; this
0x18001289f  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x1800128a4  nop
0x1800128a5  lea     rdx, aPrintconfigcon; "PrintConfigConnections"
0x1800128ac  mov     rcx, r12
0x1800128af  mov     rax, [rbp+57h+var_68]
0x1800128b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b8  test    rax, rax
0x1800128bb  jnz     loc_1800129CF
0x1800128c1  call    cs:__imp_GetLastError
0x1800128c8  nop     dword ptr [rax+rax+00h]
0x1800128cd  cmp     eax, 34h ; '4'
0x1800128d0  jz      loc_1800129CF
0x1800128d6  mov     rcx, r14; pSid
0x1800128d9  call    cs:__imp_GetLengthSid
0x1800128e0  nop     dword ptr [rax+rax+00h]
0x1800128e5  lea     ebx, [rax+10h]
0x1800128e8  mov     edx, ebx
0x1800128ea  lea     rcx, [rbp+57h+pAcl]
0x1800128ee  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800128f3  nop
0x1800128f4  mov     rsi, [rbp+57h+pAcl]
0x1800128f8  mov     r8d, 2; dwAclRevision
0x1800128fe  mov     edx, ebx; nAclLength
0x180012900  mov     rcx, rsi; pAcl
0x180012903  call    cs:__imp_InitializeAcl
0x18001290a  nop     dword ptr [rax+rax+00h]
0x18001290f  test    eax, eax
0x180012911  jz      loc_180012AEF
0x180012917  mov     [rsp+120h+pSid], r14; pSid
0x18001291c  mov     r9d, 10000000h; AccessMask
0x180012922  xor     r8d, r8d; AceFlags
0x180012925  lea     edx, [r8+2]; dwAceRevision
0x180012929  mov     rcx, rsi; pAcl
0x18001292c  call    cs:__imp_AddAccessAllowedAceEx
0x180012933  nop     dword ptr [rax+rax+00h]
0x180012938  test    eax, eax
0x18001293a  jz      loc_180012B59
0x180012940  xorps   xmm0, xmm0
0x180012943  xor     eax, eax
0x180012945  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180012949  movups  [rbp+57h+var_A8], xmm0
0x18001294d  mov     [rbp+57h+var_98], rax
0x180012951  lea     edx, [rax+1]; dwRevision
0x180012954  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180012958  call    cs:__imp_InitializeSecurityDescriptor
0x18001295f  nop     dword ptr [rax+rax+00h]
0x180012964  test    eax, eax
0x180012966  jz      loc_180012BC3
0x18001296c  xor     r9d, r9d; bDaclDefaulted
0x18001296f  mov     r8, rsi; pDacl
0x180012972  lea     edx, [r9+1]; bDaclPresent
0x180012976  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18001297a  call    cs:__imp_SetSecurityDescriptorDacl
0x180012981  nop     dword ptr [rax+rax+00h]
0x180012986  test    eax, eax
0x180012988  jz      loc_180012C2D
0x18001298e  mov     [rbp+57h+var_D0], 18h
0x180012996  mov     [rbp+57h+var_C0], 0
0x18001299e  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1800129a2  mov     [rbp+57h+var_C8], rax
0x1800129a6  lea     r8, aPrintconfigcon; "PrintConfigConnections"
0x1800129ad  mov     rdx, r12
0x1800129b0  lea     rcx, [rbp+57h+var_D0]
0x1800129b4  mov     rax, [rbp+57h+var_70]
0x1800129b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129bd  test    rax, rax
0x1800129c0  jz      loc_180012C97
0x1800129c6  lea     rcx, [rbp+57h+pAcl]
0x1800129ca  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800129cf  mov     r8, r15; lpName
0x1800129d2  mov     edx, 1; bInheritHandle
0x1800129d7  mov     ecx, 10000000h; dwDesiredAccess
0x1800129dc  call    cs:__imp_OpenMutexW
0x1800129e3  nop     dword ptr [rax+rax+00h]
0x1800129e8  mov     rbx, rax
0x1800129eb  mov     rcx, [rdi]; hObject
0x1800129ee  lea     rdx, [rcx-1]
0x1800129f2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800129f6  ja      short loc_180012A04
0x1800129f8  call    cs:__imp_CloseHandle
0x1800129ff  nop     dword ptr [rax+rax+00h]
0x180012a04  mov     [rdi], rbx
0x180012a07  lea     rax, [rbx+1]
0x180012a0b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012a11  jnz     short loc_180012A51
0x180012a13  mov     r8, r15; lpName
0x180012a16  xor     edx, edx; bInitialOwner
0x180012a18  xor     ecx, ecx; lpMutexAttributes
0x180012a1a  call    cs:__imp_CreateMutexW
0x180012a21  nop     dword ptr [rax+rax+00h]
0x180012a26  mov     rbx, rax
0x180012a29  mov     rcx, [rdi]; hObject
0x180012a2c  lea     rdx, [rcx-1]
0x180012a30  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180012a34  ja      short loc_180012A42
0x180012a36  call    cs:__imp_CloseHandle
0x180012a3d  nop     dword ptr [rax+rax+00h]
0x180012a42  mov     [rdi], rbx
0x180012a45  lea     rax, [rbx+1]
0x180012a49  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012a4f  jz      short loc_180012A84
0x180012a51  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180012a58  mov     [rbp+57h+var_40], rax
0x180012a5c  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180012a60  test    rcx, rcx
0x180012a63  jz      short loc_180012A71
0x180012a65  call    cs:__imp_FreeLibrary
0x180012a6c  nop     dword ptr [rax+rax+00h]
0x180012a71  add     rsp, 0F0h
0x180012a78  pop     r15
0x180012a7a  pop     r14
0x180012a7c  pop     r12
0x180012a7e  pop     rdi
0x180012a7f  pop     rsi
0x180012a80  pop     rbx
0x180012a81  pop     rbp
0x180012a82  retn
0x180012a84  call    cs:__imp_GetLastError
0x180012a8b  nop     dword ptr [rax+rax+00h]
0x180012a90  nop
0x180012a91  mov     ebx, eax
0x180012a93  test    eax, eax
0x180012a95  jle     short loc_180012AA0
0x180012a97  movzx   ebx, ax
0x180012a9a  or      ebx, 80070000h
0x180012aa0  lea     rax, WPP_GLOBAL_Control
0x180012aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012aae  cmp     rcx, rax
0x180012ab1  jz      short loc_180012AD1
0x180012ab3  test    byte ptr [rcx+44h], 1
0x180012ab7  jz      short loc_180012AD1
0x180012ab9  mov     edx, 24h ; '$'
0x180012abe  mov     r9d, ebx
0x180012ac1  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012ac8  mov     rcx, [rcx+38h]
0x180012acc  call    WPP_SF_d
0x180012ad1  mov     edx, ebx; int
0x180012ad3  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012ad8  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012add  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012ae4  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012ae9  call    _CxxThrowException_0
0x180012aef  call    cs:__imp_GetLastError
0x180012af6  nop     dword ptr [rax+rax+00h]
0x180012afb  mov     ebx, eax
0x180012afd  test    eax, eax
0x180012aff  jle     short loc_180012B0A
0x180012b01  movzx   ebx, ax
0x180012b04  or      ebx, 80070000h
0x180012b0a  lea     rax, WPP_GLOBAL_Control
0x180012b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b18  cmp     rcx, rax
0x180012b1b  jz      short loc_180012B3B
0x180012b1d  test    byte ptr [rcx+44h], 1
0x180012b21  jz      short loc_180012B3B
0x180012b23  mov     edx, 1Fh
0x180012b28  mov     r9d, ebx
0x180012b2b  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012b32  mov     rcx, [rcx+38h]
0x180012b36  call    WPP_SF_d
0x180012b3b  mov     edx, ebx; int
0x180012b3d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012b42  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012b47  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012b4e  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012b53  call    _CxxThrowException_0
0x180012b59  call    cs:__imp_GetLastError
0x180012b60  nop     dword ptr [rax+rax+00h]
0x180012b65  mov     ebx, eax
0x180012b67  test    eax, eax
0x180012b69  jle     short loc_180012B74
0x180012b6b  movzx   ebx, ax
0x180012b6e  or      ebx, 80070000h
0x180012b74  lea     rax, WPP_GLOBAL_Control
0x180012b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b82  cmp     rcx, rax
0x180012b85  jz      short loc_180012BA5
0x180012b87  test    byte ptr [rcx+44h], 1
0x180012b8b  jz      short loc_180012BA5
0x180012b8d  mov     edx, 20h ; ' '
0x180012b92  mov     r9d, ebx
0x180012b95  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012b9c  mov     rcx, [rcx+38h]
0x180012ba0  call    WPP_SF_d
0x180012ba5  mov     edx, ebx; int
0x180012ba7  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012bac  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012bb1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012bb8  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012bbd  call    _CxxThrowException_0
0x180012bc3  call    cs:__imp_GetLastError
0x180012bca  nop     dword ptr [rax+rax+00h]
0x180012bcf  mov     ebx, eax
0x180012bd1  test    eax, eax
0x180012bd3  jle     short loc_180012BDE
0x180012bd5  movzx   ebx, ax
0x180012bd8  or      ebx, 80070000h
0x180012bde  lea     rax, WPP_GLOBAL_Control
0x180012be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bec  cmp     rcx, rax
0x180012bef  jz      short loc_180012C0F
0x180012bf1  test    byte ptr [rcx+44h], 1
0x180012bf5  jz      short loc_180012C0F
0x180012bf7  mov     edx, 21h ; '!'
0x180012bfc  mov     r9d, ebx
0x180012bff  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012c06  mov     rcx, [rcx+38h]
0x180012c0a  call    WPP_SF_d
0x180012c0f  mov     edx, ebx; int
0x180012c11  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012c16  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012c1b  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012c22  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012c27  call    _CxxThrowException_0
0x180012c2d  call    cs:__imp_GetLastError
0x180012c34  nop     dword ptr [rax+rax+00h]
0x180012c39  mov     ebx, eax
0x180012c3b  test    eax, eax
0x180012c3d  jle     short loc_180012C48
0x180012c3f  movzx   ebx, ax
0x180012c42  or      ebx, 80070000h
0x180012c48  lea     rax, WPP_GLOBAL_Control
0x180012c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c56  cmp     rcx, rax
0x180012c59  jz      short loc_180012C79
0x180012c5b  test    byte ptr [rcx+44h], 1
0x180012c5f  jz      short loc_180012C79
0x180012c61  mov     edx, 22h ; '"'
0x180012c66  mov     r9d, ebx
0x180012c69  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012c70  mov     rcx, [rcx+38h]
0x180012c74  call    WPP_SF_d
0x180012c79  mov     edx, ebx; int
0x180012c7b  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012c80  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012c85  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012c8c  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012c91  call    _CxxThrowException_0
0x180012c97  call    cs:__imp_GetLastError
0x180012c9e  nop     dword ptr [rax+rax+00h]
0x180012ca3  mov     ebx, eax
0x180012ca5  test    eax, eax
0x180012ca7  jle     short loc_180012CB2
0x180012ca9  movzx   ebx, ax
0x180012cac  or      ebx, 80070000h
0x180012cb2  lea     rax, WPP_GLOBAL_Control
0x180012cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cc0  cmp     rcx, rax
0x180012cc3  jz      short loc_180012CE3
0x180012cc5  test    byte ptr [rcx+44h], 1
0x180012cc9  jz      short loc_180012CE3
0x180012ccb  mov     edx, 23h ; '#'
0x180012cd0  mov     r9d, ebx
0x180012cd3  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012cda  mov     rcx, [rcx+38h]
0x180012cde  call    WPP_SF_d
0x180012ce3  mov     edx, ebx; int
0x180012ce5  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012cea  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012cef  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012cf6  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012cfb  call    _CxxThrowException_0
```

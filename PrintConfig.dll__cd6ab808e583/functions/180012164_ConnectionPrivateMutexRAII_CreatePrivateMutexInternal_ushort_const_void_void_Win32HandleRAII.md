# ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)

- ea: `0x180012164`
- end: `0x18001258e`
- name: `?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z`
- size: `1066`
- prototype: `void __fastcall(LPCWSTR lpName, void *, void *, struct Win32HandleRAII *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011954`
- `0x180011ba4`

## callees

- `0x180004424`
- `0x18000e420`
- `0x18000efdc`
- `0x18000f380`
- `0x18000f6a0`
- `0x180012164`
- `0x180018bbc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x1800122de`
- `KERNEL32!CreateMutexW` at `0x1800122de`
- `KERNEL32!OpenMutexW` at `0x1800122ac`
- `KERNEL32!OpenMutexW` at `0x1800122ac`
- `KERNEL32!FreeLibrary` at `0x18001231d`
- `KERNEL32!FreeLibrary` at `0x18001231d`
- `KERNEL32!CloseHandle` at `0x1800122c2`
- `KERNEL32!CloseHandle` at `0x1800122f4`
- `KERNEL32!CloseHandle` at `0x1800122c2`
- `KERNEL32!CloseHandle` at `0x1800122f4`
- `KERNEL32!GetLastError` at `0x1800121b5`
- `KERNEL32!GetLastError` at `0x180012335`
- `KERNEL32!GetLastError` at `0x18001239a`
- `KERNEL32!GetLastError` at `0x1800123fe`
- `KERNEL32!GetLastError` at `0x180012462`
- `KERNEL32!GetLastError` at `0x1800124c6`
- `KERNEL32!GetLastError` at `0x18001252a`
- `KERNEL32!GetLastError` at `0x1800121b5`
- `KERNEL32!GetLastError` at `0x180012335`
- `KERNEL32!GetLastError` at `0x18001239a`
- `KERNEL32!GetLastError` at `0x1800123fe`
- `KERNEL32!GetLastError` at `0x180012462`
- `KERNEL32!GetLastError` at `0x1800124c6`
- `KERNEL32!GetLastError` at `0x18001252a`
- `ADVAPI32!GetLengthSid` at `0x1800121c7`
- `ADVAPI32!GetLengthSid` at `0x1800121c7`
- `ADVAPI32!InitializeAcl` at `0x1800121eb`
- `ADVAPI32!InitializeAcl` at `0x1800121eb`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012250`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012250`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012234`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012234`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18001220e`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18001220e`

## string_xrefs

- `0x180012199`: `PrintConfigConnections`
- `0x180012276`: `PrintConfigConnections`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(LPCWSTR lpName, void *a2, void *a3, HANDLE *a4)
{
  __int64 v8; // rbx
  ACL *v9; // rsi
  HANDLE v10; // rbx
  HANDLE MutexW; // rbx
  signed int v12; // eax
  unsigned int v13; // ebx
  signed int LastError; // eax
  unsigned int v15; // ebx
  signed int v16; // eax
  unsigned int v17; // ebx
  signed int v18; // eax
  unsigned int v19; // ebx
  signed int v20; // eax
  unsigned int v21; // ebx
  signed int v22; // eax
  unsigned int v23; // ebx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v25[3]; // [rsp+50h] [rbp-79h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v27; // [rsp+88h] [rbp-41h]
  __int64 v28; // [rsp+90h] [rbp-39h]
  PACL pAcl[3]; // [rsp+98h] [rbp-31h] BYREF
  _QWORD v30[7]; // [rsp+B0h] [rbp-19h] BYREF
  HMODULE hLibModule; // [rsp+E8h] [rbp+1Fh]

  v28 = -2;
  Kernel32RAII::Kernel32RAII((Kernel32RAII *)v30);
  if ( !((__int64 (__fastcall *)(void *, const wchar_t *))v30[1])(a2, L"PrintConfigConnections") && GetLastError() != 52 )
  {
    v8 = GetLengthSid(a3) + 16;
    std::vector<unsigned char>::vector<unsigned char>(pAcl, v8);
    v9 = pAcl[0];
    if ( !InitializeAcl(pAcl[0], v8, 2u) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v15);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v15);
      throw (hr_error *)pExceptionObject;
    }
    if ( !AddAccessAllowedAceEx(v9, 2u, 0, 0x10000000u, a3) )
    {
      v16 = GetLastError();
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v17);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v17);
      throw (hr_error *)pExceptionObject;
    }
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    v27 = 0;
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      v18 = GetLastError();
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v19);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v19);
      throw (hr_error *)pExceptionObject;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0) )
    {
      v20 = GetLastError();
      v21 = v20;
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v21);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v21);
      throw (hr_error *)pExceptionObject;
    }
    v25[0] = 24;
    v25[2] = 0;
    v25[1] = pSecurityDescriptor;
    if ( !((__int64 (__fastcall *)(_QWORD *, void *, const wchar_t *))v30[0])(v25, a2, L"PrintConfigConnections") )
    {
      v22 = GetLastError();
      v23 = v22;
      if ( v22 > 0 )
        v23 = (unsigned __int16)v22 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v23);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v23);
      throw (hr_error *)pExceptionObject;
    }
    std::vector<char>::~vector<char>(pAcl);
  }
  v10 = OpenMutexW(0x10000000u, 1, lpName);
  if ( (char *)*a4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*a4);
  *a4 = v10;
  if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    MutexW = CreateMutexW(0, 0, lpName);
    if ( (char *)*a4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(*a4);
    *a4 = MutexW;
    if ( (((unsigned __int64)MutexW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v13);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v13);
      throw (hr_error *)pExceptionObject;
    }
  }
  v30[6] = &ModuleRAII::`vftable';
  if ( hLibModule )
    FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180012164  push    rbp
0x180012166  push    rbx
0x180012167  push    rsi
0x180012168  push    rdi
0x180012169  push    r12
0x18001216b  push    r14
0x18001216d  push    r15
0x18001216f  lea     rbp, [rsp-27h]
0x180012174  sub     rsp, 0F0h
0x18001217b  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180012183  mov     rdi, r9
0x180012186  mov     r14, r8
0x180012189  mov     r12, rdx
0x18001218c  mov     r15, rcx
0x18001218f  lea     rcx, [rbp+57h+var_70]; this
0x180012193  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x180012198  nop
0x180012199  lea     rdx, aPrintconfigcon; "PrintConfigConnections"
0x1800121a0  mov     rcx, r12
0x1800121a3  mov     rax, [rbp+57h+var_68]
0x1800121a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ac  test    rax, rax
0x1800121af  jnz     loc_18001229F
0x1800121b5  call    cs:__imp_GetLastError
0x1800121bb  cmp     eax, 34h ; '4'
0x1800121be  jz      loc_18001229F
0x1800121c4  mov     rcx, r14; pSid
0x1800121c7  call    cs:__imp_GetLengthSid
0x1800121cd  lea     ebx, [rax+10h]
0x1800121d0  mov     edx, ebx
0x1800121d2  lea     rcx, [rbp+57h+pAcl]
0x1800121d6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800121db  nop
0x1800121dc  mov     rsi, [rbp+57h+pAcl]
0x1800121e0  mov     r8d, 2; dwAclRevision
0x1800121e6  mov     edx, ebx; nAclLength
0x1800121e8  mov     rcx, rsi; pAcl
0x1800121eb  call    cs:__imp_InitializeAcl
0x1800121f1  test    eax, eax
0x1800121f3  jz      loc_18001239A
0x1800121f9  mov     [rsp+120h+pSid], r14; pSid
0x1800121fe  mov     r9d, 10000000h; AccessMask
0x180012204  xor     r8d, r8d; AceFlags
0x180012207  lea     edx, [r8+2]; dwAceRevision
0x18001220b  mov     rcx, rsi; pAcl
0x18001220e  call    cs:__imp_AddAccessAllowedAceEx
0x180012214  test    eax, eax
0x180012216  jz      loc_1800123FE
0x18001221c  xorps   xmm0, xmm0
0x18001221f  xor     eax, eax
0x180012221  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180012225  movups  [rbp+57h+var_A8], xmm0
0x180012229  mov     [rbp+57h+var_98], rax
0x18001222d  lea     edx, [rax+1]; dwRevision
0x180012230  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180012234  call    cs:__imp_InitializeSecurityDescriptor
0x18001223a  test    eax, eax
0x18001223c  jz      loc_180012462
0x180012242  xor     r9d, r9d; bDaclDefaulted
0x180012245  mov     r8, rsi; pDacl
0x180012248  lea     edx, [r9+1]; bDaclPresent
0x18001224c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180012250  call    cs:__imp_SetSecurityDescriptorDacl
0x180012256  test    eax, eax
0x180012258  jz      loc_1800124C6
0x18001225e  mov     [rbp+57h+var_D0], 18h
0x180012266  mov     [rbp+57h+var_C0], 0
0x18001226e  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180012272  mov     [rbp+57h+var_C8], rax
0x180012276  lea     r8, aPrintconfigcon; "PrintConfigConnections"
0x18001227d  mov     rdx, r12
0x180012280  lea     rcx, [rbp+57h+var_D0]
0x180012284  mov     rax, [rbp+57h+var_70]
0x180012288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001228d  test    rax, rax
0x180012290  jz      loc_18001252A
0x180012296  lea     rcx, [rbp+57h+pAcl]
0x18001229a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001229f  mov     r8, r15; lpName
0x1800122a2  mov     edx, 1; bInheritHandle
0x1800122a7  mov     ecx, 10000000h; dwDesiredAccess
0x1800122ac  call    cs:__imp_OpenMutexW
0x1800122b2  mov     rbx, rax
0x1800122b5  mov     rcx, [rdi]; hObject
0x1800122b8  lea     rdx, [rcx-1]
0x1800122bc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800122c0  ja      short loc_1800122C8
0x1800122c2  call    cs:__imp_CloseHandle
0x1800122c8  mov     [rdi], rbx
0x1800122cb  lea     rax, [rbx+1]
0x1800122cf  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800122d5  jnz     short loc_180012309
0x1800122d7  mov     r8, r15; lpName
0x1800122da  xor     edx, edx; bInitialOwner
0x1800122dc  xor     ecx, ecx; lpMutexAttributes
0x1800122de  call    cs:__imp_CreateMutexW
0x1800122e4  mov     rbx, rax
0x1800122e7  mov     rcx, [rdi]; hObject
0x1800122ea  lea     rdx, [rcx-1]
0x1800122ee  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800122f2  ja      short loc_1800122FA
0x1800122f4  call    cs:__imp_CloseHandle
0x1800122fa  mov     [rdi], rbx
0x1800122fd  lea     rax, [rbx+1]
0x180012301  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012307  jz      short loc_180012335
0x180012309  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180012310  mov     [rbp+57h+var_40], rax
0x180012314  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180012318  test    rcx, rcx
0x18001231b  jz      short loc_180012323
0x18001231d  call    cs:__imp_FreeLibrary
0x180012323  add     rsp, 0F0h
0x18001232a  pop     r15
0x18001232c  pop     r14
0x18001232e  pop     r12
0x180012330  pop     rdi
0x180012331  pop     rsi
0x180012332  pop     rbx
0x180012333  pop     rbp
0x180012334  retn
0x180012335  call    cs:__imp_GetLastError
0x18001233b  nop
0x18001233c  mov     ebx, eax
0x18001233e  test    eax, eax
0x180012340  jle     short loc_18001234B
0x180012342  movzx   ebx, ax
0x180012345  or      ebx, 80070000h
0x18001234b  lea     rax, WPP_GLOBAL_Control
0x180012352  mov     rcx, cs:WPP_GLOBAL_Control
0x180012359  cmp     rcx, rax
0x18001235c  jz      short loc_18001237C
0x18001235e  test    byte ptr [rcx+44h], 1
0x180012362  jz      short loc_18001237C
0x180012364  mov     edx, 24h ; '$'
0x180012369  mov     r9d, ebx
0x18001236c  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012373  mov     rcx, [rcx+38h]
0x180012377  call    WPP_SF_d
0x18001237c  mov     edx, ebx; int
0x18001237e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012383  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012388  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001238f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012394  call    _CxxThrowException_0
0x18001239a  call    cs:__imp_GetLastError
0x1800123a0  mov     ebx, eax
0x1800123a2  test    eax, eax
0x1800123a4  jle     short loc_1800123AF
0x1800123a6  movzx   ebx, ax
0x1800123a9  or      ebx, 80070000h
0x1800123af  lea     rax, WPP_GLOBAL_Control
0x1800123b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123bd  cmp     rcx, rax
0x1800123c0  jz      short loc_1800123E0
0x1800123c2  test    byte ptr [rcx+44h], 1
0x1800123c6  jz      short loc_1800123E0
0x1800123c8  mov     edx, 1Fh
0x1800123cd  mov     r9d, ebx
0x1800123d0  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x1800123d7  mov     rcx, [rcx+38h]
0x1800123db  call    WPP_SF_d
0x1800123e0  mov     edx, ebx; int
0x1800123e2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800123e7  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800123ec  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800123f3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800123f8  call    _CxxThrowException_0
0x1800123fe  call    cs:__imp_GetLastError
0x180012404  mov     ebx, eax
0x180012406  test    eax, eax
0x180012408  jle     short loc_180012413
0x18001240a  movzx   ebx, ax
0x18001240d  or      ebx, 80070000h
0x180012413  lea     rax, WPP_GLOBAL_Control
0x18001241a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012421  cmp     rcx, rax
0x180012424  jz      short loc_180012444
0x180012426  test    byte ptr [rcx+44h], 1
0x18001242a  jz      short loc_180012444
0x18001242c  mov     edx, 20h ; ' '
0x180012431  mov     r9d, ebx
0x180012434  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18001243b  mov     rcx, [rcx+38h]
0x18001243f  call    WPP_SF_d
0x180012444  mov     edx, ebx; int
0x180012446  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001244b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012450  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012457  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001245c  call    _CxxThrowException_0
0x180012462  call    cs:__imp_GetLastError
0x180012468  mov     ebx, eax
0x18001246a  test    eax, eax
0x18001246c  jle     short loc_180012477
0x18001246e  movzx   ebx, ax
0x180012471  or      ebx, 80070000h
0x180012477  lea     rax, WPP_GLOBAL_Control
0x18001247e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012485  cmp     rcx, rax
0x180012488  jz      short loc_1800124A8
0x18001248a  test    byte ptr [rcx+44h], 1
0x18001248e  jz      short loc_1800124A8
0x180012490  mov     edx, 21h ; '!'
0x180012495  mov     r9d, ebx
0x180012498  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18001249f  mov     rcx, [rcx+38h]
0x1800124a3  call    WPP_SF_d
0x1800124a8  mov     edx, ebx; int
0x1800124aa  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800124af  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800124b4  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800124bb  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800124c0  call    _CxxThrowException_0
0x1800124c6  call    cs:__imp_GetLastError
0x1800124cc  mov     ebx, eax
0x1800124ce  test    eax, eax
0x1800124d0  jle     short loc_1800124DB
0x1800124d2  movzx   ebx, ax
0x1800124d5  or      ebx, 80070000h
0x1800124db  lea     rax, WPP_GLOBAL_Control
0x1800124e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124e9  cmp     rcx, rax
0x1800124ec  jz      short loc_18001250C
0x1800124ee  test    byte ptr [rcx+44h], 1
0x1800124f2  jz      short loc_18001250C
0x1800124f4  mov     edx, 22h ; '"'
0x1800124f9  mov     r9d, ebx
0x1800124fc  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012503  mov     rcx, [rcx+38h]
0x180012507  call    WPP_SF_d
0x18001250c  mov     edx, ebx; int
0x18001250e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012513  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012518  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001251f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012524  call    _CxxThrowException_0
0x18001252a  call    cs:__imp_GetLastError
0x180012530  mov     ebx, eax
0x180012532  test    eax, eax
0x180012534  jle     short loc_18001253F
0x180012536  movzx   ebx, ax
0x180012539  or      ebx, 80070000h
0x18001253f  lea     rax, WPP_GLOBAL_Control
0x180012546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001254d  cmp     rcx, rax
0x180012550  jz      short loc_180012570
0x180012552  test    byte ptr [rcx+44h], 1
0x180012556  jz      short loc_180012570
0x180012558  mov     edx, 23h ; '#'
0x18001255d  mov     r9d, ebx
0x180012560  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012567  mov     rcx, [rcx+38h]
0x18001256b  call    WPP_SF_d
0x180012570  mov     edx, ebx; int
0x180012572  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180012577  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001257c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012583  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180012588  call    _CxxThrowException_0
```

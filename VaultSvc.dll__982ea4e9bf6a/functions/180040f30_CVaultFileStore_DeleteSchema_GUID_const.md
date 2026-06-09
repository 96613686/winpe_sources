# CVaultFileStore::DeleteSchema(_GUID const *)

- ea: `0x180040f30`
- end: `0x1800411d8`
- name: `?DeleteSchema@CVaultFileStore@@UEAAKPEBU_GUID@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(wchar_t **this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x18000eb30`
- `0x180011110`
- `0x180024220`
- `0x18002e2e0`
- `0x1800354f4`
- `0x180037870`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x180040f30`
- `0x180041818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004114e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004114e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041110`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041110`
- `ntdll!RtlReleaseResource` at `0x180040fbc`
- `ntdll!RtlReleaseResource` at `0x180041022`
- `ntdll!RtlReleaseResource` at `0x180041086`
- `ntdll!RtlReleaseResource` at `0x1800410f6`
- `ntdll!RtlReleaseResource` at `0x180041136`
- `ntdll!RtlReleaseResource` at `0x18004116a`
- `ntdll!RtlReleaseResource` at `0x1800411a2`
- `ntdll!RtlReleaseResource` at `0x180040fbc`
- `ntdll!RtlReleaseResource` at `0x180041022`
- `ntdll!RtlReleaseResource` at `0x180041086`
- `ntdll!RtlReleaseResource` at `0x1800410f6`
- `ntdll!RtlReleaseResource` at `0x180041136`
- `ntdll!RtlReleaseResource` at `0x18004116a`
- `ntdll!RtlReleaseResource` at `0x1800411a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CVaultFileStore::DeleteSchema(wchar_t **this, const struct _GUID *a2)
{
  __int64 v4; // r8
  DWORD IsSchemaReferenced; // eax
  DWORD LastError; // ebx
  ULONG v7; // edi
  _BYTE v9[8]; // [rsp+20h] [rbp-69h] BYREF
  __int64 ThreadInformation; // [rsp+28h] [rbp-61h] BYREF
  PRTL_RESOURCE Resource; // [rsp+30h] [rbp-59h] BYREF
  char v12; // [rsp+38h] [rbp-51h]
  __int64 v13; // [rsp+40h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-41h] BYREF
  int v15; // [rsp+50h] [rbp-39h]
  wchar_t v16[40]; // [rsp+60h] [rbp-29h] BYREF

  lpFileName = 0;
  v15 = 0;
  v13 = 0;
  v9[0] = 0;
  CVaultRtlLock::CVaultRtlLock(&Resource, this + 24, 1);
  ThreadInformation = 0;
  IsSchemaReferenced = CVaultMemoryStore::IsSchemaReferenced(this, a2, v4, v9);
  LastError = IsSchemaReferenced;
  if ( IsSchemaReferenced )
  {
    if ( IsSchemaReferenced != 1168 )
    {
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      if ( v12 )
        RtlReleaseResource(Resource);
LABEL_37:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return LastError;
    }
    LastError = 1168;
  }
  else
  {
    LastError = 0;
    if ( v9[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids);
      CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
      if ( v12 )
        RtlReleaseResource(Resource);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return 32;
    }
  }
  ConvertGuidToString(a2, v16, 0x25u);
  v7 = PathCombineExt(this[39], v16, (wchar_t *)L".vsch", (unsigned __int16 **)&lpFileName);
  if ( v7 )
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    if ( v12 )
      RtlReleaseResource(Resource);
LABEL_10:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
    return v7;
  }
  v7 = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v7);
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    if ( v12 )
      RtlReleaseResource(Resource);
    goto LABEL_10;
  }
  if ( DeleteFileW(lpFileName) )
  {
    if ( !LastError )
      LastError = CVaultMemoryStore::DeleteSchema((CVaultMemoryStore *)this, a2);
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    if ( v12 )
      RtlReleaseResource(Resource);
    goto LABEL_37;
  }
  if ( LastError != 1168 )
  {
    LastError = GetLastError();
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    if ( v12 )
      RtlReleaseResource(Resource);
    goto LABEL_37;
  }
  CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
  if ( v12 )
    RtlReleaseResource(Resource);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
  return 1168;
}

```

## disassembly

```asm
0x180040f30  mov     [rsp-8+arg_10], rbx
0x180040f35  push    rbp
0x180040f36  push    rsi
0x180040f37  push    rdi
0x180040f38  push    r14
0x180040f3a  push    r15
0x180040f3c  lea     rbp, [rsp-37h]
0x180040f41  sub     rsp, 0C0h
0x180040f48  mov     rax, cs:__security_cookie
0x180040f4f  xor     rax, rsp
0x180040f52  mov     [rbp+57h+var_30], rax
0x180040f56  mov     r14, rdx
0x180040f59  mov     rsi, rcx
0x180040f5c  xor     r15d, r15d
0x180040f5f  mov     [rbp+57h+lpFileName], r15
0x180040f63  mov     [rbp+57h+var_90], r15d
0x180040f67  mov     [rbp+57h+var_A0], r15
0x180040f6b  mov     [rbp+57h+var_C0], r15b
0x180040f6f  lea     rdx, [rcx+0C0h]
0x180040f76  lea     r8d, [r15+1]
0x180040f7a  lea     rcx, [rbp+57h+Resource]
0x180040f7e  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x180040f83  nop
0x180040f84  mov     [rbp+57h+ThreadInformation], r15
0x180040f88  lea     r9, [rbp+57h+var_C0]
0x180040f8c  mov     rdx, r14
0x180040f8f  mov     rcx, rsi
0x180040f92  call    ?IsSchemaReferenced@CVaultMemoryStore@@IEAAKPEBU_GUID@@W4EVaultSecurableAction@@PEAE@Z; CVaultMemoryStore::IsSchemaReferenced(_GUID const *,EVaultSecurableAction,uchar *)
0x180040f97  mov     ebx, eax
0x180040f99  test    eax, eax
0x180040f9b  jz      loc_18004103A
0x180040fa1  cmp     eax, 490h
0x180040fa6  jz      short loc_180040FD2
0x180040fa8  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180040fac  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180040fb1  nop
0x180040fb2  cmp     [rbp+57h+var_A8], r15b
0x180040fb6  jz      short loc_180040FC3
0x180040fb8  mov     rcx, [rbp+57h+Resource]; Resource
0x180040fbc  call    cs:__imp_RtlReleaseResource
0x180040fc2  nop
0x180040fc3  lea     rcx, [rbp+57h+var_A0]
0x180040fc7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040fcc  nop
0x180040fcd  jmp     loc_1800411B3
0x180040fd2  mov     ebx, 490h
0x180040fd7  mov     r8d, 25h ; '%'; unsigned int
0x180040fdd  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180040fe1  mov     rcx, r14; struct _GUID *
0x180040fe4  call    ?ConvertGuidToString@@YAKPEBU_GUID@@PEAGK@Z; ConvertGuidToString(_GUID const *,ushort *,ulong)
0x180040fe9  lea     r9, [rbp+57h+lpFileName]; unsigned __int16 **
0x180040fed  lea     r8, aVsch; ".vsch"
0x180040ff4  lea     rdx, [rbp+57h+var_80]; wchar_t *
0x180040ff8  mov     rcx, [rsi+138h]; Source
0x180040fff  call    ?PathCombineExt@@YAKPEBG00PEAPEAG@Z; PathCombineExt(ushort const *,ushort const *,ushort const *,ushort * *)
0x180041004  mov     edi, eax
0x180041006  test    eax, eax
0x180041008  jz      loc_1800410A1
0x18004100e  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180041012  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180041017  nop
0x180041018  cmp     [rbp+57h+var_A8], r15b
0x18004101c  jz      short loc_180041029
0x18004101e  mov     rcx, [rbp+57h+Resource]; Resource
0x180041022  call    cs:__imp_RtlReleaseResource
0x180041028  nop
0x180041029  lea     rcx, [rbp+57h+var_A0]
0x18004102d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180041032  nop
0x180041033  mov     eax, edi
0x180041035  jmp     loc_1800411B5
0x18004103a  mov     ebx, r15d
0x18004103d  cmp     [rbp+57h+var_C0], r15b
0x180041041  jz      short loc_180040FD7
0x180041043  lea     rax, WPP_GLOBAL_Control
0x18004104a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041051  cmp     rcx, rax
0x180041054  jz      short loc_180041072
0x180041056  test    byte ptr [rcx+1Ch], 2
0x18004105a  jz      short loc_180041072
0x18004105c  mov     edx, 27h ; '''
0x180041061  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x180041068  mov     rcx, [rcx+10h]
0x18004106c  call    WPP_SF_
0x180041071  nop
0x180041072  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180041076  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18004107b  nop
0x18004107c  cmp     [rbp+57h+var_A8], r15b
0x180041080  jz      short loc_18004108D
0x180041082  mov     rcx, [rbp+57h+Resource]; Resource
0x180041086  call    cs:__imp_RtlReleaseResource
0x18004108c  nop
0x18004108d  lea     rcx, [rbp+57h+var_A0]
0x180041091  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180041096  nop
0x180041097  mov     eax, 20h ; ' '
0x18004109c  jmp     loc_1800411B5
0x1800410a1  lea     rcx, [rbp+57h+ThreadInformation]; this
0x1800410a5  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x1800410aa  mov     edi, eax
0x1800410ac  test    eax, eax
0x1800410ae  jz      short loc_18004110C
0x1800410b0  lea     rax, WPP_GLOBAL_Control
0x1800410b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800410be  cmp     rcx, rax
0x1800410c1  jz      short loc_1800410E2
0x1800410c3  test    byte ptr [rcx+1Ch], 2
0x1800410c7  jz      short loc_1800410E2
0x1800410c9  mov     edx, 28h ; '('
0x1800410ce  mov     r9d, edi
0x1800410d1  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x1800410d8  mov     rcx, [rcx+10h]
0x1800410dc  call    WPP_SF_d
0x1800410e1  nop
0x1800410e2  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800410e6  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x1800410eb  nop
0x1800410ec  cmp     [rbp+57h+var_A8], r15b
0x1800410f0  jz      short loc_1800410FD
0x1800410f2  mov     rcx, [rbp+57h+Resource]; Resource
0x1800410f6  call    cs:__imp_RtlReleaseResource
0x1800410fc  nop
0x1800410fd  lea     rcx, [rbp+57h+var_A0]
0x180041101  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180041106  nop
0x180041107  jmp     loc_180041033
0x18004110c  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180041110  call    cs:__imp_DeleteFileW
0x180041116  test    eax, eax
0x180041118  jnz     short loc_18004117D
0x18004111a  cmp     ebx, 490h
0x180041120  jnz     short loc_18004114E
0x180041122  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180041126  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18004112b  nop
0x18004112c  cmp     [rbp+57h+var_A8], r15b
0x180041130  jz      short loc_18004113D
0x180041132  mov     rcx, [rbp+57h+Resource]; Resource
0x180041136  call    cs:__imp_RtlReleaseResource
0x18004113c  nop
0x18004113d  lea     rcx, [rbp+57h+var_A0]
0x180041141  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180041146  nop
0x180041147  mov     eax, 490h
0x18004114c  jmp     short loc_1800411B5
0x18004114e  call    cs:__imp_GetLastError
0x180041154  mov     ebx, eax
0x180041156  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18004115a  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18004115f  nop
0x180041160  cmp     [rbp+57h+var_A8], r15b
0x180041164  jz      short loc_180041171
0x180041166  mov     rcx, [rbp+57h+Resource]; Resource
0x18004116a  call    cs:__imp_RtlReleaseResource
0x180041170  nop
0x180041171  lea     rcx, [rbp+57h+var_A0]
0x180041175  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004117a  nop
0x18004117b  jmp     short loc_1800411B3
0x18004117d  test    ebx, ebx
0x18004117f  jnz     short loc_18004118E
0x180041181  mov     rdx, r14; struct _GUID *
0x180041184  mov     rcx, rsi; this
0x180041187  call    ?DeleteSchema@CVaultMemoryStore@@UEAAKPEBU_GUID@@@Z; CVaultMemoryStore::DeleteSchema(_GUID const *)
0x18004118c  mov     ebx, eax
0x18004118e  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x180041192  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180041197  nop
0x180041198  cmp     [rbp+57h+var_A8], r15b
0x18004119c  jz      short loc_1800411A9
0x18004119e  mov     rcx, [rbp+57h+Resource]; Resource
0x1800411a2  call    cs:__imp_RtlReleaseResource
0x1800411a8  nop
0x1800411a9  lea     rcx, [rbp+57h+var_A0]
0x1800411ad  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800411b2  nop
0x1800411b3  mov     eax, ebx
0x1800411b5  mov     rcx, [rbp+57h+var_30]
0x1800411b9  xor     rcx, rsp; StackCookie
0x1800411bc  call    __security_check_cookie
0x1800411c1  mov     rbx, [rsp+0E0h+arg_10]
0x1800411c9  add     rsp, 0C0h
0x1800411d0  pop     r15
0x1800411d2  pop     r14
0x1800411d4  pop     rdi
0x1800411d5  pop     rsi
0x1800411d6  pop     rbp
0x1800411d7  retn
```

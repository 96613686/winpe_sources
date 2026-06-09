# CProfMgr::DeleteLeastRecentlyUsedRoamingUserProfile(unsigned __int64,unsigned __int64)

- ea: `0x1800155b8`
- end: `0x18001591b`
- name: `?DeleteLeastRecentlyUsedRoamingUserProfile@CProfMgr@@AEAAX_K0@Z`
- size: `867`
- prototype: `void __fastcall(CProfMgr *__hidden this, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032a60`

## callees

- `0x180003f30`
- `0x1800155b8`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad08`
- `0x180031d1c`
- `0x1800326a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001573c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001573c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015660`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180015660`
- `USERENV!DeleteProfileW` at `0x180015774`
- `USERENV!DeleteProfileW` at `0x180015774`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800156cb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800156cb`

## string_xrefs

- `0x18001567f`: `ConvertStringSidToSid failed with error code : 0x%08x.`
- `0x1800158e7`: `IsReadOnlyRoamingProfilePolicyEnabled failed: 0x%x in %s`
- `0x1800158dd`: `CProfMgr::DeleteLeastRecentlyUsedRoamingUserProfile`
- `0x180015749`: `Attempting to delete %ws profile`
- `0x18001579a`: `DeleteProfile failed with error code : 0x%08x.`
- `0x180015826`: `Profile %ws deleted`

## pseudocode

```c
void __fastcall CProfMgr::DeleteLeastRecentlyUsedRoamingUserProfile(
        CProfMgr *this,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  int v6; // r15d
  unsigned int i; // r14d
  int OnlyRoamingProfilePolicyEnabled; // eax
  LPCWSTR *v9; // rcx
  signed int v10; // eax
  signed int LastError; // eax
  signed int v12; // eax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // r8d
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  _QWORD *v18; // r8
  unsigned __int16 *v19; // rcx
  __int64 v20; // rax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  unsigned int *v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v34[520]; // [rsp+4B0h] [rbp+3B0h] BYREF

  Sid = 0;
  cchName = 260;
  cchReferencedDomainName = 260;
  peUse = 0;
  v6 = 0;
  for ( i = 0; i < *((_DWORD *)this + 414) && a3 >= a2; ++i )
  {
    OnlyRoamingProfilePolicyEnabled = CProfMgr::IsReadOnlyRoamingProfilePolicyEnabled(this);
    if ( OnlyRoamingProfilePolicyEnabled < 0 )
    {
      _DbgPrintMessage(
        8,
        "IsReadOnlyRoamingProfilePolicyEnabled failed: 0x%x in %s",
        OnlyRoamingProfilePolicyEnabled,
        "CProfMgr::DeleteLeastRecentlyUsedRoamingUserProfile");
      return;
    }
    if ( *((_DWORD *)this + 404) == 1 )
      return;
    v9 = *(LPCWSTR **)(*((_QWORD *)this + 206) + 8LL * i);
    if ( v9 )
    {
      if ( ConvertStringSidToSidW(*v9, &Sid) )
      {
        cchName = 260;
        cchReferencedDomainName = 260;
        if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          v34[0] = 0;
          if ( StringCchPrintfW(v34, 0x208u, L"%s\\%s", ReferencedDomainName, Name) >= 0 )
            v6 = 1;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(1, "LookupAccountName failed with error code : 0x%08x.", LastError);
        }
        LocalFree(Sid);
      }
      else
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        _DbgPrintMessage(1, "ConvertStringSidToSid failed with error code : 0x%08x.", v10);
      }
      _DbgPrintMessage(1, "Attempting to delete %ws profile", **(_QWORD **)(*((_QWORD *)this + 206) + 8LL * i));
      if ( DeleteProfileW(**(LPCWSTR **)(*((_QWORD *)this + 206) + 8LL * i), 0, 0) )
      {
        v18 = *(_QWORD **)(*((_QWORD *)this + 206) + 8LL * i);
        a3 -= v18[3];
        _DbgPrintMessage(1, "Profile %ws deleted", *v18);
        if ( v6 )
          v19 = v34;
        else
          v19 = **(unsigned __int16 ***)(*((_QWORD *)this + 206) + 8LL * i);
        v26 = a2;
        v20 = -1;
        v27.Ptr = (ULONGLONG)v19;
        do
          ++v20;
        while ( v19[v20] );
        v16 = 2;
        v27.Size = 2 * v20 + 2;
        v28 = (__int64 *)&v26;
        v17 = &EVENT_TS_RUP_PROFILE_DELETION_INFO;
      }
      else
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        _DbgPrintMessage(1, "DeleteProfile failed with error code : 0x%08x.", v13);
        if ( v6 )
          v14 = v34;
        else
          v14 = **(unsigned __int16 ***)(*((_QWORD *)this + 206) + 8LL * i);
        v15 = -1;
        v24 = v13;
        v26 = a2;
        v27.Ptr = (ULONGLONG)v14;
        do
          ++v15;
        while ( v14[v15] );
        v31 = 4;
        v27.Size = 2 * v15 + 2;
        v16 = 3;
        v28 = (__int64 *)&v26;
        v17 = (const struct _EVENT_DESCRIPTOR *)EVENT_TS_RUP_PROFILE_DELETION_ERROR;
        v30 = &v24;
      }
      v27.Reserved = 0;
      v29 = 8;
      CrimsonHelper::RaiseEventInternal((CrimsonHelper *)&CrimsonHelper::s_instance, v17, v16, &v27);
      free(*(void **)(*((_QWORD *)this + 206) + 8LL * i));
      *(_QWORD *)(*((_QWORD *)this + 206) + 8LL * i) = 0;
    }
  }
}

```

## disassembly

```asm
0x1800155b8  push    rbp
0x1800155ba  push    rbx
0x1800155bb  push    rsi
0x1800155bc  push    rdi
0x1800155bd  push    r12
0x1800155bf  push    r13
0x1800155c1  push    r14
0x1800155c3  push    r15
0x1800155c5  lea     rbp, [rsp-7D8h]
0x1800155cd  sub     rsp, 8D8h
0x1800155d4  mov     rax, cs:__security_cookie
0x1800155db  xor     rax, rsp
0x1800155de  mov     [rbp+810h+var_50], rax
0x1800155e5  xor     ebx, ebx
0x1800155e7  mov     eax, 104h
0x1800155ec  mov     r13, r8
0x1800155ef  mov     [rsp+910h+Sid], rbx
0x1800155f4  mov     r12, rdx
0x1800155f7  mov     [rsp+910h+cchName], eax
0x1800155fb  mov     rdi, rcx
0x1800155fe  mov     [rsp+910h+var_8E0], eax
0x180015602  lea     esi, [rbx+1]
0x180015605  mov     [rsp+910h+var_8D8], ebx
0x180015609  mov     r15d, ebx
0x18001560c  mov     r14d, ebx
0x18001560f  cmp     r14d, [rdi+678h]
0x180015616  jnb     loc_1800158F8
0x18001561c  cmp     r13, r12
0x18001561f  jb      loc_1800158F8
0x180015625  mov     rcx, rdi; this
0x180015628  call    ?IsReadOnlyRoamingProfilePolicyEnabled@CProfMgr@@AEAAJXZ; CProfMgr::IsReadOnlyRoamingProfilePolicyEnabled(void)
0x18001562d  test    eax, eax
0x18001562f  js      loc_1800158DD
0x180015635  cmp     [rdi+650h], esi
0x18001563b  jz      loc_1800158F8
0x180015641  mov     rax, [rdi+670h]
0x180015648  mov     esi, r14d
0x18001564b  mov     rcx, [rax+rsi*8]
0x18001564f  test    rcx, rcx
0x180015652  jz      loc_1800158D0
0x180015658  mov     rcx, [rcx]; StringSid
0x18001565b  lea     rdx, [rsp+910h+Sid]; Sid
0x180015660  call    cs:__imp_ConvertStringSidToSidW
0x180015666  test    eax, eax
0x180015668  jnz     short loc_180015695
0x18001566a  call    cs:__imp_GetLastError
0x180015670  test    eax, eax
0x180015672  jle     short loc_18001567C
0x180015674  movzx   eax, ax
0x180015677  or      eax, 80070000h
0x18001567c  mov     r8d, eax
0x18001567f  lea     rdx, aConvertstrings_4; "ConvertStringSidToSid failed with error"...
0x180015686  mov     ecx, 1; int
0x18001568b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015690  jmp     loc_180015742
0x180015695  mov     rcx, [rsp+910h+Sid]; Sid
0x18001569a  lea     r9, [rbp+810h+ReferencedDomainName]; ReferencedDomainName
0x1800156a1  mov     eax, 104h
0x1800156a6  lea     r8, [rsp+910h+cchName]; cchName
0x1800156ab  mov     [rsp+910h+cchName], eax
0x1800156af  lea     rdx, [rbp+810h+Name]; Name
0x1800156b3  mov     [rsp+910h+var_8E0], eax
0x1800156b7  lea     rax, [rsp+910h+var_8D8]
0x1800156bc  mov     [rsp+910h+peUse], rax; peUse
0x1800156c1  lea     rax, [rsp+910h+var_8E0]
0x1800156c6  mov     [rsp+910h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800156cb  call    cs:__imp_LookupAccountSidLocalW
0x1800156d1  test    eax, eax
0x1800156d3  jnz     short loc_1800156FD
0x1800156d5  call    cs:__imp_GetLastError
0x1800156db  test    eax, eax
0x1800156dd  jle     short loc_1800156E7
0x1800156df  movzx   eax, ax
0x1800156e2  or      eax, 80070000h
0x1800156e7  mov     r8d, eax
0x1800156ea  lea     rdx, aLookupaccountn_0; "LookupAccountName failed with error cod"...
0x1800156f1  mov     ecx, 1; int
0x1800156f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800156fb  jmp     short loc_180015737
0x1800156fd  lea     rax, [rbp+810h+Name]
0x180015701  mov     [rbp+810h+var_460], bx
0x180015708  lea     r9, [rbp+810h+ReferencedDomainName]
0x18001570f  mov     [rsp+910h+cchReferencedDomainName], rax
0x180015714  lea     r8, aSS_0; "%s\\%s"
0x18001571b  mov     edx, 208h; unsigned __int64
0x180015720  lea     rcx, [rbp+810h+var_460]; unsigned __int16 *
0x180015727  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001572c  test    eax, eax
0x18001572e  mov     eax, 1
0x180015733  cmovns  r15d, eax
0x180015737  mov     rcx, [rsp+910h+Sid]; hMem
0x18001573c  call    cs:__imp_LocalFree
0x180015742  mov     rax, [rdi+670h]
0x180015749  lea     rdx, aAttemptingToDe; "Attempting to delete %ws profile"
0x180015750  mov     ecx, 1; int
0x180015755  mov     r8, [rax+rsi*8]
0x180015759  mov     r8, [r8]
0x18001575c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015761  mov     rax, [rdi+670h]
0x180015768  xor     r8d, r8d; lpComputerName
0x18001576b  xor     edx, edx; lpProfilePath
0x18001576d  mov     rcx, [rax+rsi*8]
0x180015771  mov     rcx, [rcx]; lpSidString
0x180015774  call    cs:__imp_DeleteProfileW
0x18001577a  test    eax, eax
0x18001577c  jnz     loc_18001581F
0x180015782  call    cs:__imp_GetLastError
0x180015788  mov     ebx, eax
0x18001578a  test    eax, eax
0x18001578c  jle     short loc_180015797
0x18001578e  movzx   ebx, ax
0x180015791  or      ebx, 80070000h
0x180015797  mov     r8d, ebx
0x18001579a  lea     rdx, aDeleteprofileF; "DeleteProfile failed with error code : "...
0x1800157a1  mov     ecx, 1; int
0x1800157a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800157ab  test    r15d, r15d
0x1800157ae  jz      short loc_1800157B9
0x1800157b0  lea     rcx, [rbp+810h+var_460]
0x1800157b7  jmp     short loc_1800157C7
0x1800157b9  mov     rax, [rdi+670h]
0x1800157c0  mov     rcx, [rax+rsi*8]
0x1800157c4  mov     rcx, [rcx]
0x1800157c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800157cb  mov     [rsp+910h+var_8D0], ebx
0x1800157cf  xor     ebx, ebx
0x1800157d1  mov     [rsp+910h+var_8C0], r12
0x1800157d6  mov     [rsp+910h+var_8B8.Ptr], rcx
0x1800157db  inc     rax
0x1800157de  cmp     [rcx+rax*2], bx
0x1800157e2  jnz     short loc_1800157DB
0x1800157e4  lea     eax, ds:2[rax*2]
0x1800157eb  mov     [rbp+810h+var_890], 4
0x1800157f3  mov     [rsp+910h+var_8B8.Size], eax
0x1800157f7  lea     r9, [rsp+910h+var_8B8]
0x1800157fc  lea     rax, [rsp+910h+var_8C0]
0x180015801  mov     r8d, 3
0x180015807  mov     [rsp+910h+var_8A8], rax
0x18001580c  lea     rdx, EVENT_TS_RUP_PROFILE_DELETION_ERROR
0x180015813  lea     rax, [rsp+910h+var_8D0]
0x180015818  mov     [rsp+910h+var_898], rax
0x18001581d  jmp     short loc_18001589C
0x18001581f  mov     rax, [rdi+670h]
0x180015826  lea     rdx, aProfileWsDelet; "Profile %ws deleted"
0x18001582d  mov     ecx, 1; int
0x180015832  mov     r8, [rax+rsi*8]
0x180015836  sub     r13, [r8+18h]
0x18001583a  mov     r8, [r8]
0x18001583d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015842  test    r15d, r15d
0x180015845  jz      short loc_180015850
0x180015847  lea     rcx, [rbp+810h+var_460]
0x18001584e  jmp     short loc_18001585E
0x180015850  mov     rax, [rdi+670h]
0x180015857  mov     rcx, [rax+rsi*8]
0x18001585b  mov     rcx, [rcx]
0x18001585e  mov     [rsp+910h+var_8C0], r12
0x180015863  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015867  mov     [rsp+910h+var_8B8.Ptr], rcx
0x18001586c  inc     rax
0x18001586f  cmp     [rcx+rax*2], bx
0x180015873  jnz     short loc_18001586C
0x180015875  lea     eax, ds:2[rax*2]
0x18001587c  mov     r8d, 2; unsigned int
0x180015882  mov     [rsp+910h+var_8B8.Size], eax
0x180015886  lea     r9, [rsp+910h+var_8B8]; struct _EVENT_DATA_DESCRIPTOR *
0x18001588b  lea     rax, [rsp+910h+var_8C0]
0x180015890  mov     [rsp+910h+var_8A8], rax
0x180015895  lea     rdx, EVENT_TS_RUP_PROFILE_DELETION_INFO; struct _EVENT_DESCRIPTOR *
0x18001589c  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x1800158a3  mov     dword ptr [rsp+910h+var_8B8.0Ch], ebx
0x1800158a7  mov     [rsp+910h+var_8A0], 8
0x1800158b0  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x1800158b5  mov     rcx, [rdi+670h]
0x1800158bc  mov     rcx, [rcx+rsi*8]; Block
0x1800158c0  call    free
0x1800158c5  mov     rax, [rdi+670h]
0x1800158cc  mov     [rax+rsi*8], rbx
0x1800158d0  mov     esi, 1
0x1800158d5  add     r14d, esi
0x1800158d8  jmp     loc_18001560F
0x1800158dd  lea     r9, aCprofmgrDelete; "CProfMgr::DeleteLeastRecentlyUsedRoamin"...
0x1800158e4  mov     r8d, eax
0x1800158e7  lea     rdx, aIsreadonlyroam; "IsReadOnlyRoamingProfilePolicyEnabled f"...
0x1800158ee  mov     ecx, 8; int
0x1800158f3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800158f8  mov     rcx, [rbp+810h+var_50]
0x1800158ff  xor     rcx, rsp; StackCookie
0x180015902  call    __security_check_cookie
0x180015907  add     rsp, 8D8h
0x18001590e  pop     r15
0x180015910  pop     r14
0x180015912  pop     r13
0x180015914  pop     r12
0x180015916  pop     rdi
0x180015917  pop     rsi
0x180015918  pop     rbx
0x180015919  pop     rbp
0x18001591a  retn
```

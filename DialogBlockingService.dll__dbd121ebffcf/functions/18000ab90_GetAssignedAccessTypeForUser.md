# GetAssignedAccessTypeForUser

- ea: `0x18000ab90`
- end: `0x18000ad4d`
- name: `GetAssignedAccessTypeForUser`
- size: `445`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, enum Windows::Internal::AssignedAccess::AssignedAccessType *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000a65c`

## callees

- `0x180001650`
- `0x180001c90`
- `0x180006804`
- `0x18000ab90`
- `0x18000b3c4`
- `0x18000b518`
- `0x18000b680`
- `0x18000b7d4`
- `0x18000b8ac`
- `0x18000bd2c`
- `0x18000be8c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad2a`

## string_xrefs

- `0x18000ac1e`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18000accf`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18000abba`: `AssignedAccessConfiguration`
- `0x18000abc6`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`

## pseudocode

```c
__int64 __fastcall GetAssignedAccessTypeForUser(
        unsigned __int16 *a1,
        __int64 a2,
        enum Windows::Internal::AssignedAccess::AssignedAccessType *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  const char *v7; // r9
  LPVOID v9; // rdi
  int AssignedAccessTypeForUserWithoutGroup; // eax
  unsigned int v11; // edi
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v5 = operator new(0x20u);
  pv = 0;
  v6 = v5;
  v5[3] = 0;
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              (char *)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
              (__int64)L"AssignedAccessConfiguration",
              &pv,
              v7) < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_4;
  }
  v9 = pv;
  if ( pv )
  {
    if ( *v6 )
      CoTaskMemFree((LPVOID)*v6);
    *v6 = v9;
    v6[2] = -1;
    v6[1] = -1;
    *((_DWORD *)v6 + 6) = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion((LPCWSTR *)v6);
    if ( Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesTargetProfileExist(
           (Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)v6,
           a1)
      || Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesGroupConfigExist((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)v6)
      || Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)v6) )
    {
      Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper((Windows::Internal::AssignedAccess::AAManagerHelper *)v12);
      AssignedAccessTypeForUserWithoutGroup = Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithoutGroup(
                                                (Windows::Internal::AssignedAccess::AAManagerHelper *)v12,
                                                a1,
                                                a3);
      v11 = AssignedAccessTypeForUserWithoutGroup;
      if ( AssignedAccessTypeForUserWithoutGroup < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
          (const char *)(unsigned int)AssignedAccessTypeForUserWithoutGroup);
        if ( v12[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
        if ( *v6 )
        {
          CoTaskMemFree((LPVOID)*v6);
          *v6 = 0;
        }
        goto LABEL_24;
      }
      if ( v12[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
    }
    else
    {
      *(_DWORD *)a3 = 0;
    }
    if ( *v6 )
    {
      CoTaskMemFree((LPVOID)*v6);
      *v6 = 0;
    }
    v11 = 0;
LABEL_24:
    v6[2] = 0;
    v6[1] = 0;
    operator delete(v6);
    return v11;
  }
LABEL_4:
  if ( *v6 )
  {
    CoTaskMemFree((LPVOID)*v6);
    *v6 = 0;
  }
  v6[1] = 0;
  v6[2] = 0;
  operator delete(v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29,
    (int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
    (const char *)0x8000FFFFLL);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000ab90  mov     [rsp+arg_0], rbx
0x18000ab95  mov     [rsp+arg_8], rbp
0x18000ab9a  push    rsi
0x18000ab9b  push    rdi
0x18000ab9c  push    r14
0x18000ab9e  sub     rsp, 30h
0x18000aba2  mov     rbp, rcx
0x18000aba5  mov     rsi, r8
0x18000aba8  mov     ecx, 20h ; ' '; Size
0x18000abad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000abb2  xor     r14d, r14d
0x18000abb5  lea     r8, [rsp+48h+pv]
0x18000abba  lea     rdx, aAssignedaccess; "AssignedAccessConfiguration"
0x18000abc1  mov     [rsp+48h+pv], r14
0x18000abc6  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x18000abcd  mov     rbx, rax
0x18000abd0  mov     [rax+18h], r14
0x18000abd4  mov     [rax], r14
0x18000abd7  mov     [rax+8], r14
0x18000abdb  mov     [rax+10h], r14
0x18000abdf  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000abe4  test    eax, eax
0x18000abe6  jns     short loc_18000AC4C
0x18000abe8  mov     rcx, [rsp+48h+pv]; pv
0x18000abed  test    rcx, rcx
0x18000abf0  jz      short loc_18000ABF8
0x18000abf2  call    cs:__imp_CoTaskMemFree
0x18000abf8  mov     rcx, [rbx]; pv
0x18000abfb  test    rcx, rcx
0x18000abfe  jz      short loc_18000AC09
0x18000ac00  call    cs:__imp_CoTaskMemFree
0x18000ac06  mov     [rbx], r14
0x18000ac09  mov     rcx, rbx; Block
0x18000ac0c  mov     [rbx+8], r14
0x18000ac10  mov     [rbx+10h], r14
0x18000ac14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ac19  mov     rcx, [rsp+48h]; this
0x18000ac1e  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x18000ac25  mov     ebx, 8000FFFFh
0x18000ac2a  mov     edx, 29h ; ')'; void *
0x18000ac2f  mov     r9d, ebx; char *
0x18000ac32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac37  mov     eax, ebx
0x18000ac39  mov     rbx, [rsp+48h+arg_0]
0x18000ac3e  mov     rbp, [rsp+48h+arg_8]
0x18000ac43  add     rsp, 30h
0x18000ac47  pop     r14
0x18000ac49  pop     rdi
0x18000ac4a  pop     rsi
0x18000ac4b  retn
0x18000ac4c  mov     rdi, [rsp+48h+pv]
0x18000ac51  test    rdi, rdi
0x18000ac54  jz      short loc_18000ABF8
0x18000ac56  mov     rcx, [rbx]; pv
0x18000ac59  test    rcx, rcx
0x18000ac5c  jz      short loc_18000AC64
0x18000ac5e  call    cs:__imp_CoTaskMemFree
0x18000ac64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ac68  mov     [rbx], rdi
0x18000ac6b  mov     rcx, rbx; this
0x18000ac6e  mov     [rbx+10h], rax
0x18000ac72  mov     [rbx+8], rax
0x18000ac76  call    ?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)
0x18000ac7b  mov     rdx, rbp; unsigned __int16 *
0x18000ac7e  mov     [rbx+18h], eax
0x18000ac81  mov     rcx, rbx; this
0x18000ac84  call    ?DoesTargetProfileExist@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NPEBG@Z; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesTargetProfileExist(ushort const *)
0x18000ac89  test    al, al
0x18000ac8b  jnz     short loc_18000ACAA
0x18000ac8d  mov     rcx, rbx; this
0x18000ac90  call    ?DoesGroupConfigExist@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::DoesGroupConfigExist(void)
0x18000ac95  test    al, al
0x18000ac97  jnz     short loc_18000ACAA
0x18000ac99  mov     rcx, rbx; this
0x18000ac9c  call    ?IsGlobalProfileConfigured@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@QEAA_NXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::IsGlobalProfileConfigured(void)
0x18000aca1  test    al, al
0x18000aca3  jnz     short loc_18000ACAA
0x18000aca5  mov     [rsi], r14d
0x18000aca8  jmp     short loc_18000AD22
0x18000acaa  lea     rcx, [rsp+48h+var_28]; this
0x18000acaf  call    ??0AAManagerHelper@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper(void)
0x18000acb4  mov     r8, rsi; enum Windows::Internal::AssignedAccess::AssignedAccessType *
0x18000acb7  lea     rcx, [rsp+48h+var_28]; this
0x18000acbc  mov     rdx, rbp; unsigned __int16 *
0x18000acbf  call    ?GetAssignedAccessTypeForUserWithoutGroup@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJPEBGPEAW4AssignedAccessType@234@@Z; Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessTypeForUserWithoutGroup(ushort const *,Windows::Internal::AssignedAccess::AssignedAccessType *)
0x18000acc4  mov     edi, eax
0x18000acc6  test    eax, eax
0x18000acc8  jns     short loc_18000AD0C
0x18000acca  mov     rcx, [rsp+48h]; this
0x18000accf  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x18000acd6  mov     r9d, eax; char *
0x18000acd9  mov     edx, 31h ; '1'; void *
0x18000acde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ace3  mov     rcx, [rsp+48h+var_28]
0x18000ace8  test    rcx, rcx
0x18000aceb  jz      short loc_18000ACF9
0x18000aced  mov     rdx, [rcx]
0x18000acf0  mov     rax, [rdx+10h]
0x18000acf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf9  mov     rcx, [rbx]; pv
0x18000acfc  test    rcx, rcx
0x18000acff  jz      short loc_18000AD36
0x18000ad01  call    cs:__imp_CoTaskMemFree
0x18000ad07  mov     [rbx], r14
0x18000ad0a  jmp     short loc_18000AD36
0x18000ad0c  mov     rcx, [rsp+48h+var_28]
0x18000ad11  test    rcx, rcx
0x18000ad14  jz      short loc_18000AD22
0x18000ad16  mov     rax, [rcx]
0x18000ad19  mov     rax, [rax+10h]
0x18000ad1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad22  mov     rcx, [rbx]; pv
0x18000ad25  test    rcx, rcx
0x18000ad28  jz      short loc_18000AD33
0x18000ad2a  call    cs:__imp_CoTaskMemFree
0x18000ad30  mov     [rbx], r14
0x18000ad33  mov     edi, r14d
0x18000ad36  mov     [rbx+10h], r14
0x18000ad3a  mov     rcx, rbx; Block
0x18000ad3d  mov     [rbx+8], r14
0x18000ad41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad46  mov     eax, edi
0x18000ad48  jmp     loc_18000AC39
```

# EnterpriseAppManager::EnumPendingInstallRequest(_GUID * *,ulong *)

- ea: `0x180003b80`
- end: `0x180003ce4`
- name: `?EnumPendingInstallRequest@EnterpriseAppManager@@UEAAJPEAPEAU_GUID@@PEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(EnterpriseAppManager *__hidden this, struct _GUID **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180003b80`
- `0x180006780`
- `0x180006858`
- `0x180012d84`
- `0x18001a374`
- `0x180066df0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003c66`
- `msvcrt!memcpy_s` at `0x180003c66`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003c84`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c43`

## string_xrefs

- `0x180003ba7`: `EnterpriseAppManager::EnumPendingInstallRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseAppManager::EnumPendingInstallRequest(
        EnterpriseAppManager *this,
        struct _GUID **a2,
        unsigned int *a3)
{
  EnterpriseAppManager *v5; // rbx
  int v6; // ebx
  void **v7; // rax
  __int64 v8; // rcx
  DWORD v9; // eax
  __int64 v10; // rdi
  struct _GUID *v11; // rax
  errno_t v12; // eax
  int v13; // ecx
  DWORD v15; // [rsp+30h] [rbp-58h] BYREF
  void *Source; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v17[4]; // [rsp+40h] [rbp-48h] BYREF

  v5 = this;
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 8) != 0 )
  {
    v17[2] = L"EnterpriseAppManager::EnumPendingInstallRequest";
    v17[3] = 96;
    McGenEventWrite_EventWriteTransfer(this, EnterpriseAppMgmtSvcApiBegin, a3, 2, v17);
  }
  if ( a2 && a3 )
  {
    if ( *((_QWORD *)v5 + 2) )
    {
      Source = 0;
      v15 = 0;
      v7 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>(&Source);
      v6 = EnrollmentManager::EnumeratePrimaryKeys(v8, (GUID **)v7, &v15);
      if ( v6 >= 0 )
      {
        v9 = v15;
        *a3 = v15;
        if ( v9 )
        {
          v10 = 16LL * v9;
          v11 = (struct _GUID *)CoTaskMemAlloc(v10);
          *a2 = v11;
          if ( v11 )
          {
            v12 = memcpy_s(v11, v10, Source, v10);
            v13 = v6;
            if ( v12 )
              v13 = -2147467259;
            v6 = v13;
          }
          else
          {
            v6 = -2147024882;
          }
        }
      }
      this = (EnterpriseAppManager *)Source;
      if ( Source )
        operator delete[](Source);
    }
    else
    {
      v6 = -2147467259;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 8) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      this,
      EnterpriseAppMgmtSvcApiEnd,
      L"EnterpriseAppManager::EnumPendingInstallRequest",
      (unsigned int)v6);
  if ( v6 < 0 && (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      this,
      EnterpriseAppMgmtSvcError,
      L"EnterpriseAppManager::EnumPendingInstallRequest",
      (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003b80  mov     r11, rsp
0x180003b83  mov     [r11+8], rbx
0x180003b87  push    rsi
0x180003b88  push    rdi
0x180003b89  push    r14
0x180003b8b  sub     rsp, 70h
0x180003b8f  mov     rax, cs:__security_cookie
0x180003b96  xor     rax, rsp
0x180003b99  mov     [rsp+88h+var_28], rax
0x180003b9e  mov     rdi, r8
0x180003ba1  mov     rsi, rdx
0x180003ba4  mov     rbx, rcx
0x180003ba7  lea     r14, aEnterpriseappm_11; "EnterpriseAppManager::EnumPendingInstal"...
0x180003bae  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x180003bb5  jz      short loc_180003BDD
0x180003bb7  mov     [r11-38h], r14
0x180003bbb  mov     qword ptr [r11-30h], 60h ; '`'
0x180003bc3  lea     rax, [r11-48h]
0x180003bc7  mov     [r11-68h], rax
0x180003bcb  mov     r9d, 2
0x180003bd1  lea     rdx, EnterpriseAppMgmtSvcApiBegin
0x180003bd8  call    McGenEventWrite_EventWriteTransfer
0x180003bdd  test    rsi, rsi
0x180003be0  jnz     short loc_180003BEC
0x180003be2  mov     ebx, 80070057h
0x180003be7  jmp     loc_180003C8A
0x180003bec  test    rdi, rdi
0x180003bef  jz      short loc_180003BE2
0x180003bf1  cmp     qword ptr [rbx+10h], 0
0x180003bf6  jnz     short loc_180003C02
0x180003bf8  mov     ebx, 80004005h
0x180003bfd  jmp     loc_180003C8A
0x180003c02  mov     [rsp+88h+Source], 0
0x180003c0b  mov     [rsp+88h+var_58], 0
0x180003c13  lea     rcx, [rsp+88h+Source]
0x180003c18  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x180003c1d  mov     rdx, rax
0x180003c20  lea     r8, [rsp+88h+var_58]
0x180003c25  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x180003c2a  mov     ebx, eax
0x180003c2c  test    eax, eax
0x180003c2e  js      short loc_180003C7A
0x180003c30  mov     eax, [rsp+88h+var_58]
0x180003c34  mov     [rdi], eax
0x180003c36  test    eax, eax
0x180003c38  jz      short loc_180003C7A
0x180003c3a  mov     edi, eax
0x180003c3c  shl     rdi, 4
0x180003c40  mov     rcx, rdi; cb
0x180003c43  call    cs:__imp_CoTaskMemAlloc
0x180003c49  mov     [rsi], rax
0x180003c4c  test    rax, rax
0x180003c4f  jnz     short loc_180003C58
0x180003c51  mov     ebx, 8007000Eh
0x180003c56  jmp     short loc_180003C7A
0x180003c58  mov     r9, rdi; SourceSize
0x180003c5b  mov     r8, [rsp+88h+Source]; Source
0x180003c60  mov     rdx, rdi; DestinationSize
0x180003c63  mov     rcx, rax; Destination
0x180003c66  call    cs:__imp_memcpy_s
0x180003c6c  mov     ecx, ebx
0x180003c6e  mov     ebx, 80004005h
0x180003c73  test    eax, eax
0x180003c75  cmovnz  ecx, ebx
0x180003c78  mov     ebx, ecx
0x180003c7a  mov     rcx, [rsp+88h+Source]
0x180003c7f  test    rcx, rcx
0x180003c82  jz      short loc_180003C8A
0x180003c84  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003c8a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x180003c91  jz      short loc_180003CA5
0x180003c93  mov     r9d, ebx
0x180003c96  mov     r8, r14
0x180003c99  lea     rdx, EnterpriseAppMgmtSvcApiEnd
0x180003ca0  call    McTemplateU0zq_EventWriteTransfer
0x180003ca5  test    ebx, ebx
0x180003ca7  jns     short loc_180003CC4
0x180003ca9  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180003cb0  jz      short loc_180003CC4
0x180003cb2  mov     r9d, ebx
0x180003cb5  mov     r8, r14
0x180003cb8  lea     rdx, EnterpriseAppMgmtSvcError
0x180003cbf  call    McTemplateU0zq_EventWriteTransfer
0x180003cc4  mov     eax, ebx
0x180003cc6  mov     rcx, [rsp+88h+var_28]
0x180003ccb  xor     rcx, rsp; StackCookie
0x180003cce  call    __security_check_cookie
0x180003cd3  mov     rbx, [rsp+88h+arg_0]
0x180003cdb  add     rsp, 70h
0x180003cdf  pop     r14
0x180003ce1  pop     rdi
0x180003ce2  pop     rsi
0x180003ce3  retn
```

# EnterpriseAppManager::EnumPendingInstallRequest(_GUID * *,ulong *)

- ea: `0x180003c90`
- end: `0x180003e07`
- name: `?EnumPendingInstallRequest@EnterpriseAppManager@@UEAAJPEAPEAU_GUID@@PEAK@Z`
- size: `375`
- prototype: `__int64 __fastcall(EnterpriseAppManager *__hidden this, struct _GUID **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180003c90`
- `0x1800069dc`
- `0x180006ac0`
- `0x1800137c8`
- `0x18001b63c`
- `0x18006c910`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003d7c`
- `msvcrt!memcpy_s` at `0x180003d7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003da0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003da0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003d53`

## string_xrefs

- `0x180003cb7`: `EnterpriseAppManager::EnumPendingInstallRequest`

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
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rdi
  struct _GUID *v11; // rax
  errno_t v12; // eax
  int v13; // ecx
  unsigned int v15; // [rsp+30h] [rbp-58h] BYREF
  void *Source[5]; // [rsp+38h] [rbp-50h] BYREF

  v5 = this;
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 8) != 0 )
  {
    Source[3] = L"EnterpriseAppManager::EnumPendingInstallRequest";
    Source[4] = (void *)96;
    McGenEventWrite_EventWriteTransfer(this, EnterpriseAppMgmtSvcApiBegin, a3, 2);
  }
  if ( a2 && a3 )
  {
    if ( *((_QWORD *)v5 + 2) )
    {
      Source[0] = 0;
      v15 = 0;
      v7 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>(Source);
      v6 = EnrollmentManager::EnumeratePrimaryKeys(v8, v7, &v15);
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
            v12 = memcpy_s(v11, v10, Source[0], v10);
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
      this = (EnterpriseAppManager *)Source[0];
      if ( Source[0] )
        operator delete[](Source[0]);
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
0x180003c90  mov     r11, rsp
0x180003c93  mov     [r11+8], rbx
0x180003c97  push    rsi
0x180003c98  push    rdi
0x180003c99  push    r14
0x180003c9b  sub     rsp, 70h
0x180003c9f  mov     rax, cs:__security_cookie
0x180003ca6  xor     rax, rsp
0x180003ca9  mov     [rsp+88h+var_28], rax
0x180003cae  mov     rdi, r8
0x180003cb1  mov     rsi, rdx
0x180003cb4  mov     rbx, rcx
0x180003cb7  lea     r14, aEnterpriseappm_11; "EnterpriseAppManager::EnumPendingInstal"...
0x180003cbe  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x180003cc5  jz      short loc_180003CED
0x180003cc7  mov     [r11-38h], r14
0x180003ccb  mov     qword ptr [r11-30h], 60h ; '`'
0x180003cd3  lea     rax, [r11-48h]
0x180003cd7  mov     [r11-68h], rax
0x180003cdb  mov     r9d, 2
0x180003ce1  lea     rdx, EnterpriseAppMgmtSvcApiBegin
0x180003ce8  call    McGenEventWrite_EventWriteTransfer
0x180003ced  test    rsi, rsi
0x180003cf0  jnz     short loc_180003CFC
0x180003cf2  mov     ebx, 80070057h
0x180003cf7  jmp     loc_180003DAC
0x180003cfc  test    rdi, rdi
0x180003cff  jz      short loc_180003CF2
0x180003d01  cmp     qword ptr [rbx+10h], 0
0x180003d06  jnz     short loc_180003D12
0x180003d08  mov     ebx, 80004005h
0x180003d0d  jmp     loc_180003DAC
0x180003d12  mov     [rsp+88h+Source], 0
0x180003d1b  mov     [rsp+88h+var_58], 0
0x180003d23  lea     rcx, [rsp+88h+Source]
0x180003d28  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x180003d2d  mov     rdx, rax
0x180003d30  lea     r8, [rsp+88h+var_58]
0x180003d35  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x180003d3a  mov     ebx, eax
0x180003d3c  test    eax, eax
0x180003d3e  js      short loc_180003D96
0x180003d40  mov     eax, [rsp+88h+var_58]
0x180003d44  mov     [rdi], eax
0x180003d46  test    eax, eax
0x180003d48  jz      short loc_180003D96
0x180003d4a  mov     edi, eax
0x180003d4c  shl     rdi, 4
0x180003d50  mov     rcx, rdi; cb
0x180003d53  call    cs:__imp_CoTaskMemAlloc
0x180003d5a  nop     dword ptr [rax+rax+00h]
0x180003d5f  mov     [rsi], rax
0x180003d62  test    rax, rax
0x180003d65  jnz     short loc_180003D6E
0x180003d67  mov     ebx, 8007000Eh
0x180003d6c  jmp     short loc_180003D96
0x180003d6e  mov     r9, rdi; SourceSize
0x180003d71  mov     r8, [rsp+88h+Source]; Source
0x180003d76  mov     rdx, rdi; DestinationSize
0x180003d79  mov     rcx, rax; Destination
0x180003d7c  call    cs:__imp_memcpy_s
0x180003d83  nop     dword ptr [rax+rax+00h]
0x180003d88  mov     ecx, ebx
0x180003d8a  mov     ebx, 80004005h
0x180003d8f  test    eax, eax
0x180003d91  cmovnz  ecx, ebx
0x180003d94  mov     ebx, ecx
0x180003d96  mov     rcx, [rsp+88h+Source]
0x180003d9b  test    rcx, rcx
0x180003d9e  jz      short loc_180003DAC
0x180003da0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003da7  nop     dword ptr [rax+rax+00h]
0x180003dac  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x180003db3  jz      short loc_180003DC7
0x180003db5  mov     r9d, ebx
0x180003db8  mov     r8, r14
0x180003dbb  lea     rdx, EnterpriseAppMgmtSvcApiEnd
0x180003dc2  call    McTemplateU0zq_EventWriteTransfer
0x180003dc7  test    ebx, ebx
0x180003dc9  jns     short loc_180003DE6
0x180003dcb  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180003dd2  jz      short loc_180003DE6
0x180003dd4  mov     r9d, ebx
0x180003dd7  mov     r8, r14
0x180003dda  lea     rdx, EnterpriseAppMgmtSvcError
0x180003de1  call    McTemplateU0zq_EventWriteTransfer
0x180003de6  mov     eax, ebx
0x180003de8  mov     rcx, [rsp+88h+var_28]
0x180003ded  xor     rcx, rsp; StackCookie
0x180003df0  call    __security_check_cookie
0x180003df5  mov     rbx, [rsp+88h+arg_0]
0x180003dfd  add     rsp, 70h
0x180003e01  pop     r14
0x180003e03  pop     rdi
0x180003e04  pop     rsi
0x180003e05  retn
```

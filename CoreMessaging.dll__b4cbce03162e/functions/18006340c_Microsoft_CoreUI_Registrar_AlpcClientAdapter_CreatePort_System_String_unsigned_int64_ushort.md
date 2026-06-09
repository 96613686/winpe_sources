# Microsoft::CoreUI::Registrar::AlpcClientAdapter::CreatePort(System::String *,unsigned __int64,ushort)

- ea: `0x18006340c`
- end: `0x180063567`
- name: `?CreatePort@AlpcClientAdapter@Registrar@CoreUI@Microsoft@@AEAAHPEAVString@System@@_KG@Z`
- size: `347`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::Registrar::AlpcClientAdapter *__hidden this, struct System::String *, unsigned __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062b8c`

## callees

- `0x180007d80`
- `0x180025234`
- `0x180030c30`
- `0x18003950c`
- `0x18006340c`
- `0x180063738`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063546`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800634a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800634a0`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Registrar::AlpcClientAdapter::CreatePort(
        Microsoft::CoreUI::Registrar::AlpcClientAdapter *this,
        struct System::String *a2,
        int a3,
        __int16 a4)
{
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  PSECURITY_DESCRIPTOR v10; // rdx
  int v11; // ebx
  signed int LastError; // eax
  struct IAlpcClientConnection *v14; // [rsp+30h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-9h] BYREF
  int v17; // [rsp+48h] [rbp-1h]
  __int16 v18; // [rsp+4Ch] [rbp+3h]
  __int16 v19; // [rsp+4Eh] [rbp+5h]
  __int64 v20; // [rsp+50h] [rbp+7h]
  __int128 v21; // [rsp+58h] [rbp+Fh] BYREF
  int v22; // [rsp+68h] [rbp+1Fh]
  int v23; // [rsp+6Ch] [rbp+23h]

  v14 = 0;
  CFlat::SmartPtr<Microsoft::CoreUI::ExportEndpointHandler>::operator=(&v14, a2);
  v16 = ((unsigned __int64)v14 + 32) & -(__int64)(v14 != 0);
  CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(&v14);
  v10 = 0;
  v17 = 0x10000;
  v18 = a4;
  v19 = a4;
  v20 = 0;
  SecurityDescriptor = 0;
  if ( Microsoft::CoreUI::Registrar::AlpcServerHost::s_runMode )
  {
    if ( Microsoft::CoreUI::Registrar::AlpcServerHost::s_runMode != 1
      && (unsigned int)(Microsoft::CoreUI::Registrar::AlpcServerHost::s_runMode - 2) >= 2 )
    {
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v7,
        0,
        v8,
        v9);
    }
  }
  else
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;0x01;;;S-1-5-80-1021139062-1866602279-1255292388-1008060685-2498416891)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CFlat::Abandonment::FailWithHR(LastError, 0, 0);
    }
    v10 = SecurityDescriptor;
  }
  v23 = 0;
  v22 = a3;
  v21 = xmmword_1800E4A90;
  v14 = 0;
  v11 = AlpcClientConnection::ConnectToServer(
          (const struct AlpcConnectionConfig *)&v16,
          v10,
          1,
          v9,
          (const struct ConnectionParams *)&v21,
          &v14);
  if ( v11 >= 0 )
  {
    v11 = 0;
    *((_QWORD *)this + 5) = v14;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006340c  push    rbp
0x18006340e  push    rbx
0x18006340f  push    rsi
0x180063410  push    rdi
0x180063411  lea     rbp, [rsp-3Fh]
0x180063416  sub     rsp, 88h
0x18006341d  mov     rax, cs:__security_cookie
0x180063424  xor     rax, rsp
0x180063427  mov     [rbp+57h+var_30], rax
0x18006342b  mov     rdi, rcx
0x18006342e  mov     [rbp+57h+var_70], 0
0x180063436  lea     rcx, [rbp+57h+var_70]
0x18006343a  movzx   ebx, r9w
0x18006343e  mov     rsi, r8
0x180063441  call    ??4?$SmartPtr@VExportEndpointHandler@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVExportEndpointHandler@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::ExportEndpointHandler>::operator=(Microsoft::CoreUI::ExportEndpointHandler *)
0x180063446  mov     rax, [rbp+57h+var_70]
0x18006344a  lea     rcx, [rbp+57h+var_70]; void *
0x18006344e  lea     rdx, [rax+20h]
0x180063452  neg     rax
0x180063455  sbb     rax, rax
0x180063458  and     rax, rdx
0x18006345b  mov     [rbp+57h+var_60], rax
0x18006345f  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x180063464  mov     eax, cs:?s_runMode@AlpcServerHost@Registrar@CoreUI@Microsoft@@0W4ServiceRunMode@234@A; Microsoft::CoreUI::Registrar::ServiceRunMode Microsoft::CoreUI::Registrar::AlpcServerHost::s_runMode
0x18006346a  xor     edx, edx
0x18006346c  mov     [rbp+57h+var_58], 10000h
0x180063473  mov     [rbp+57h+var_54], bx
0x180063477  mov     [rbp+57h+var_52], bx
0x18006347b  mov     [rbp+57h+var_50], 0
0x180063483  mov     [rbp+57h+SecurityDescriptor], rdx
0x180063487  test    eax, eax
0x180063489  jnz     loc_180063529
0x18006348f  xor     r9d, r9d; SecurityDescriptorSize
0x180063492  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180063496  lea     edx, [rax+1]; StringSDRevision
0x180063499  lea     rcx, StringSecurityDescriptor; "D:(A;;0x01;;;S-1-5-80-1021139062-186660"...
0x1800634a0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800634a6  test    eax, eax
0x1800634a8  jz      loc_180063546
0x1800634ae  mov     rdx, [rbp+57h+SecurityDescriptor]; void *
0x1800634b2  movups  xmm0, cs:xmmword_1800E4A90
0x1800634b9  lea     rax, [rbp+57h+var_70]
0x1800634bd  mov     [rbp+57h+var_34], 0
0x1800634c4  mov     [rsp+0A0h+var_78], rax; struct IAlpcClientConnection **
0x1800634c9  lea     rcx, [rbp+57h+var_60]; struct AlpcConnectionConfig *
0x1800634cd  lea     rax, [rbp+57h+var_48]
0x1800634d1  mov     [rbp+57h+var_38], esi
0x1800634d4  mov     r8b, 1; bool
0x1800634d7  mov     [rsp+0A0h+var_80], rax; struct ConnectionParams *
0x1800634dc  movdqu  [rbp+57h+var_48], xmm0
0x1800634e1  mov     [rbp+57h+var_70], 0
0x1800634e9  call    ?ConnectToServer@AlpcClientConnection@@SAJPEBUAlpcConnectionConfig@@PEAX_NKAEBUConnectionParams@@PEAPEAUIAlpcClientConnection@@@Z; AlpcClientConnection::ConnectToServer(AlpcConnectionConfig const *,void *,bool,ulong,ConnectionParams const &,IAlpcClientConnection * *)
0x1800634ee  mov     ebx, eax
0x1800634f0  test    eax, eax
0x1800634f2  jns     short loc_18006351D
0x1800634f4  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800634f8  test    rcx, rcx
0x1800634fb  jz      short loc_180063503
0x1800634fd  call    cs:__imp_LocalFree
0x180063503  mov     eax, ebx
0x180063505  mov     rcx, [rbp+57h+var_30]
0x180063509  xor     rcx, rsp; StackCookie
0x18006350c  call    __security_check_cookie
0x180063511  add     rsp, 88h
0x180063518  pop     rdi
0x180063519  pop     rsi
0x18006351a  pop     rbx
0x18006351b  pop     rbp
0x18006351c  retn
0x18006351d  mov     rax, [rbp+57h+var_70]
0x180063521  xor     ebx, ebx
0x180063523  mov     [rdi+28h], rax
0x180063527  jmp     short loc_1800634F4
0x180063529  sub     eax, 1
0x18006352c  jz      short loc_1800634B2
0x18006352e  sub     eax, 1
0x180063531  jz      loc_1800634B2
0x180063537  cmp     eax, 1
0x18006353a  jz      loc_1800634B2
0x180063540  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180063546  call    cs:__imp_GetLastError
0x18006354c  test    eax, eax
0x18006354e  jg      short loc_18006355D
0x180063550  xor     r8d, r8d; int
0x180063553  xor     edx, edx; void *
0x180063555  mov     ecx, eax; int
0x180063557  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18006355d  movzx   eax, ax
0x180063560  or      eax, 80070000h
0x180063565  jmp     short loc_180063550
```

# appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::initialize(_FLT_FILTER *,_UNICODE_STRING &,bool,ulong)

- ea: `0x18000d42c`
- end: `0x18000d52d`
- name: `?initialize@?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAAJPEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@_NK@Z`
- size: `257`
- prototype: `__int64 __usercall@<rax>(PVOID ServerPortCookie@<rcx>, PFLT_FILTER Filter@<rdx>, ACCESS_MASK DesiredAccess)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ade8`

## callees

- `0x18000d42c`

## import_xrefs

- `FLTMGR!FltFreeSecurityDescriptor` at `0x18000d50e`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x18000d50e`
- `FLTMGR!FltCreateCommunicationPort` at `0x18000d4ef`
- `FLTMGR!FltCreateCommunicationPort` at `0x18000d4ef`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x18000d46b`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x18000d46b`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::initialize(
        PFLT_PORT *ServerPortCookie,
        PFLT_FILTER Filter,
        struct _UNICODE_STRING *a3,
        char a4,
        ACCESS_MASK DesiredAccess)
{
  NTSTATUS v9; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-19h] BYREF

  SecurityDescriptor = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, DesiredAccess);
  if ( v9 >= 0 )
  {
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = a3;
    ObjectAttributes.SecurityQualityOfService = 0;
    v9 = FltCreateCommunicationPort(
           Filter,
           ServerPortCookie,
           &ObjectAttributes,
           ServerPortCookie,
           appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_connect,
           appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_disconnect,
           (PFLT_MESSAGE_NOTIFY)((unsigned __int64)appv::shared::kernel::default_flt_connection_manager::notify_client_message
                               & -(__int64)(a4 != 0)),
           1);
    *((_BYTE *)ServerPortCookie + 32) = a4;
    ServerPortCookie[5] = Filter;
  }
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d42c  push    rbp
0x18000d42e  push    rbx
0x18000d42f  push    rsi
0x18000d430  push    rdi
0x18000d431  push    r14
0x18000d433  push    r15
0x18000d435  lea     rbp, [rsp-27h]
0x18000d43a  sub     rsp, 88h
0x18000d441  xorps   xmm0, xmm0
0x18000d444  mov     [rbp+4Fh+SecurityDescriptor], 0
0x18000d44c  mov     r14, rdx
0x18000d44f  mov     rdi, rcx
0x18000d452  mov     edx, [rbp+4Fh+DesiredAccess]; DesiredAccess
0x18000d455  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000d459  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000d45d  mov     sil, r9b
0x18000d460  mov     r15, r8
0x18000d463  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000d467  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d46b  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x18000d472  nop     dword ptr [rax+rax+00h]
0x18000d477  mov     ebx, eax
0x18000d479  test    eax, eax
0x18000d47b  js      loc_18000D505
0x18000d481  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x18000d485  lea     rdx, ?notify_client_message@default_flt_connection_manager@kernel@shared@appv@@SAJPEAX0K0KPEAK@Z; appv::shared::kernel::default_flt_connection_manager::notify_client_message(void *,void *,ulong,void *,ulong,ulong *)
0x18000d48c  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x18000d490  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000d494  mov     [rsp+0B0h+MaxConnections], 1; MaxConnections
0x18000d49c  mov     al, sil
0x18000d49f  neg     al
0x18000d4a1  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000d4a8  lea     rax, ?notify_client_disconnect@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@CAXPEAX@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_disconnect(void *)
0x18000d4af  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18000d4b7  sbb     rcx, rcx
0x18000d4ba  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x18000d4c1  and     rcx, rdx
0x18000d4c4  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r15
0x18000d4c8  mov     [rsp+0B0h+MessageNotifyCallback], rcx; MessageNotifyCallback
0x18000d4cd  mov     r9, rdi; ServerPortCookie
0x18000d4d0  mov     [rsp+0B0h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x18000d4d5  mov     rdx, rdi; ServerPort
0x18000d4d8  lea     rax, ?notify_client_connect@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@CAJPEAU_FLT_PORT@@PEAX1KPEAPEAX@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_connect(_FLT_PORT *,void *,void *,ulong,void * *)
0x18000d4df  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], 0
0x18000d4e7  mov     rcx, r14; Filter
0x18000d4ea  mov     [rsp+0B0h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x18000d4ef  call    cs:__imp_FltCreateCommunicationPort
0x18000d4f6  nop     dword ptr [rax+rax+00h]
0x18000d4fb  mov     ebx, eax
0x18000d4fd  mov     [rdi+20h], sil
0x18000d501  mov     [rdi+28h], r14
0x18000d505  mov     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000d509  test    rcx, rcx
0x18000d50c  jz      short loc_18000D51A
0x18000d50e  call    cs:__imp_FltFreeSecurityDescriptor
0x18000d515  nop     dword ptr [rax+rax+00h]
0x18000d51a  mov     eax, ebx
0x18000d51c  add     rsp, 88h
0x18000d523  pop     r15
0x18000d525  pop     r14
0x18000d527  pop     rdi
0x18000d528  pop     rsi
0x18000d529  pop     rbx
0x18000d52a  pop     rbp
0x18000d52b  retn
```

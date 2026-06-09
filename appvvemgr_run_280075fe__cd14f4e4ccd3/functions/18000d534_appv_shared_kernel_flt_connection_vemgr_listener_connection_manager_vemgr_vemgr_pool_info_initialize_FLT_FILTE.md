# appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::initialize(_FLT_FILTER *,_UNICODE_STRING &,bool,ulong)

- ea: `0x18000d534`
- end: `0x18000d635`
- name: `?initialize@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAAJPEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@_NK@Z`
- size: `257`
- prototype: `__int64 __usercall@<rax>(PVOID ServerPortCookie@<rcx>, PFLT_FILTER Filter@<rdx>, ACCESS_MASK DesiredAccess)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b09c`

## callees

- `0x18000d534`

## import_xrefs

- `FLTMGR!FltFreeSecurityDescriptor` at `0x18000d616`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x18000d616`
- `FLTMGR!FltCreateCommunicationPort` at `0x18000d5f7`
- `FLTMGR!FltCreateCommunicationPort` at `0x18000d5f7`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x18000d573`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x18000d573`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::initialize(
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
           (PFLT_MESSAGE_NOTIFY)((unsigned __int64)vemgr_listener_connection_manager::notify_client_message
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
0x18000d534  push    rbp
0x18000d536  push    rbx
0x18000d537  push    rsi
0x18000d538  push    rdi
0x18000d539  push    r14
0x18000d53b  push    r15
0x18000d53d  lea     rbp, [rsp-27h]
0x18000d542  sub     rsp, 88h
0x18000d549  xorps   xmm0, xmm0
0x18000d54c  mov     [rbp+4Fh+SecurityDescriptor], 0
0x18000d554  mov     r14, rdx
0x18000d557  mov     rdi, rcx
0x18000d55a  mov     edx, [rbp+4Fh+DesiredAccess]; DesiredAccess
0x18000d55d  lea     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000d561  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18000d565  mov     sil, r9b
0x18000d568  mov     r15, r8
0x18000d56b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18000d56f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d573  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x18000d57a  nop     dword ptr [rax+rax+00h]
0x18000d57f  mov     ebx, eax
0x18000d581  test    eax, eax
0x18000d583  js      loc_18000D60D
0x18000d589  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x18000d58d  lea     rdx, ?notify_client_message@vemgr_listener_connection_manager@@SAJPEAX0K0KPEAK@Z; vemgr_listener_connection_manager::notify_client_message(void *,void *,ulong,void *,ulong,ulong *)
0x18000d594  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x18000d598  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000d59c  mov     [rsp+0B0h+MaxConnections], 1; MaxConnections
0x18000d5a4  mov     al, sil
0x18000d5a7  neg     al
0x18000d5a9  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000d5b0  lea     rax, ?notify_client_disconnect@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@CAXPEAX@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_disconnect(void *)
0x18000d5b7  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x18000d5bf  sbb     rcx, rcx
0x18000d5c2  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x18000d5c9  and     rcx, rdx
0x18000d5cc  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r15
0x18000d5d0  mov     [rsp+0B0h+MessageNotifyCallback], rcx; MessageNotifyCallback
0x18000d5d5  mov     r9, rdi; ServerPortCookie
0x18000d5d8  mov     [rsp+0B0h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x18000d5dd  mov     rdx, rdi; ServerPort
0x18000d5e0  lea     rax, ?notify_client_connect@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@CAJPEAU_FLT_PORT@@PEAX1KPEAPEAX@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::notify_client_connect(_FLT_PORT *,void *,void *,ulong,void * *)
0x18000d5e7  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], 0
0x18000d5ef  mov     rcx, r14; Filter
0x18000d5f2  mov     [rsp+0B0h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x18000d5f7  call    cs:__imp_FltCreateCommunicationPort
0x18000d5fe  nop     dword ptr [rax+rax+00h]
0x18000d603  mov     ebx, eax
0x18000d605  mov     [rdi+20h], sil
0x18000d609  mov     [rdi+28h], r14
0x18000d60d  mov     rcx, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x18000d611  test    rcx, rcx
0x18000d614  jz      short loc_18000D622
0x18000d616  call    cs:__imp_FltFreeSecurityDescriptor
0x18000d61d  nop     dword ptr [rax+rax+00h]
0x18000d622  mov     eax, ebx
0x18000d624  add     rsp, 88h
0x18000d62b  pop     r15
0x18000d62d  pop     r14
0x18000d62f  pop     rdi
0x18000d630  pop     rsi
0x18000d631  pop     rbx
0x18000d632  pop     rbp
0x18000d633  retn
```

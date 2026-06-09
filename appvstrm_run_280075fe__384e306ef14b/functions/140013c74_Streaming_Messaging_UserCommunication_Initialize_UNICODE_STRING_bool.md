# Streaming::Messaging::UserCommunication::Initialize(_UNICODE_STRING &,bool)

- ea: `0x140013c74`
- end: `0x140013d7b`
- name: `?Initialize@UserCommunication@Messaging@Streaming@@QEAAJAEAU_UNICODE_STRING@@_N@Z`
- size: `263`
- prototype: `__int64 __fastcall(PFLT_PORT *ServerPort, struct _UNICODE_STRING *, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140013d84`

## callees

- `0x140013c74`

## import_xrefs

- `FLTMGR!FltFreeSecurityDescriptor` at `0x140013d57`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140013d57`
- `FLTMGR!FltCreateCommunicationPort` at `0x140013d3c`
- `FLTMGR!FltCreateCommunicationPort` at `0x140013d3c`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x140013cb2`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x140013cb2`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::UserCommunication::Initialize(
        PFLT_PORT *ServerPort,
        struct _UNICODE_STRING *a2,
        char a3)
{
  NTSTATUS v6; // ebx
  NTSTATUS (__stdcall *MessageNotifyCallback)(PVOID, PVOID, ULONG, PVOID, ULONG, PULONG); // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp+38h] BYREF

  SecurityDescriptor = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
  if ( v6 >= 0 )
  {
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    MessageNotifyCallback = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    if ( !a3 )
      MessageNotifyCallback = NotifyPortMessage;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.SecurityQualityOfService = 0;
    v6 = FltCreateCommunicationPort(
           *((PFLT_FILTER *)Streaming::gStrmFltData + 1),
           ServerPort,
           &ObjectAttributes,
           0,
           NotifyPortConnect,
           NotifyPortDisconnect,
           MessageNotifyCallback,
           1);
    *((_BYTE *)ServerPort + 32) = a3;
  }
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140013c74  mov     [rsp-18h+arg_0], rbx
0x140013c79  mov     [rsp-18h+arg_8], rsi
0x140013c7e  push    rbp
0x140013c7f  push    rdi
0x140013c80  push    r14
0x140013c82  mov     rbp, rsp
0x140013c85  sub     rsp, 70h
0x140013c89  xorps   xmm0, xmm0
0x140013c8c  mov     [rbp+SecurityDescriptor], 0
0x140013c94  mov     r14, rdx
0x140013c97  mov     rsi, rcx
0x140013c9a  mov     edx, 1F0001h; DesiredAccess
0x140013c9f  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140013ca3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140013ca7  mov     dil, r8b
0x140013caa  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140013cae  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013cb2  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x140013cb9  nop     dword ptr [rax+rax+00h]
0x140013cbe  mov     ebx, eax
0x140013cc0  test    eax, eax
0x140013cc2  js      loc_140013D4E
0x140013cc8  mov     rax, [rbp+SecurityDescriptor]
0x140013ccc  lea     rcx, ?NotifyPortMessage@@YAJPEAX0K0KPEAK@Z; NotifyPortMessage(void *,void *,ulong,void *,ulong,ulong *)
0x140013cd3  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140013cd7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013cdb  xor     eax, eax
0x140013cdd  mov     [rsp+70h+MaxConnections], 1; MaxConnections
0x140013ce5  test    dil, dil
0x140013ce8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140013cef  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140013cf7  mov     rdx, rsi; ServerPort
0x140013cfa  cmovz   rax, rcx
0x140013cfe  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140013d05  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140013d0c  xor     r9d, r9d; ServerPortCookie
0x140013d0f  mov     [rsp+70h+MessageNotifyCallback], rax; MessageNotifyCallback
0x140013d14  lea     rax, ?NotifyPortDisconnect@@YAXPEAX@Z; NotifyPortDisconnect(void *)
0x140013d1b  mov     [rsp+70h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x140013d20  lea     rax, ?NotifyPortConnect@@YAJPEAU_FLT_PORT@@PEAX1KPEAPEAX@Z; NotifyPortConnect(_FLT_PORT *,void *,void *,ulong,void * *)
0x140013d27  mov     [rbp+ObjectAttributes.ObjectName], r14
0x140013d2b  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140013d33  mov     rcx, [rcx+8]; Filter
0x140013d37  mov     [rsp+70h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x140013d3c  call    cs:__imp_FltCreateCommunicationPort
0x140013d43  nop     dword ptr [rax+rax+00h]
0x140013d48  mov     ebx, eax
0x140013d4a  mov     [rsi+20h], dil
0x140013d4e  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140013d52  test    rcx, rcx
0x140013d55  jz      short loc_140013D63
0x140013d57  call    cs:__imp_FltFreeSecurityDescriptor
0x140013d5e  nop     dword ptr [rax+rax+00h]
0x140013d63  lea     r11, [rsp+70h+var_s0]
0x140013d68  mov     eax, ebx
0x140013d6a  mov     rbx, [r11+20h]
0x140013d6e  mov     rsi, [r11+28h]
0x140013d72  mov     rsp, r11
0x140013d75  pop     r14
0x140013d77  pop     rdi
0x140013d78  pop     rbp
0x140013d79  retn
```

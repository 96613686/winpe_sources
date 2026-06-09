# MessagingService::OnTransportsIdle(void)

- ea: `0x1800035d0`
- end: `0x180003672`
- name: `?OnTransportsIdle@MessagingService@@UEAAJXZ`
- size: `162`
- prototype: `__int64 __fastcall(MessagingService *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18000108c`
- `0x18000307c`
- `0x1800035d0`
- `0x1800061a0`
- `0x18000aa50`

## string_xrefs

- `0x18000364b`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`

## pseudocode

```c
__int64 __fastcall MessagingService::OnTransportsIdle(MessagingService *this)
{
  int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_1800100D9, 0, 0, 2u, &v6);
  v2 = ServiceBase::_ServiceCtrlHandler(1, 0, 0, (char *)this - 184);
  v4 = v2;
  if ( v2 > 0 )
    v4 = (unsigned __int16)v2 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    return 0;
  Log_HREvent(v4, v3, "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp", 97);
  return v4;
}

```

## disassembly

```asm
0x1800035d0  push    rbx
0x1800035d2  sub     rsp, 60h
0x1800035d6  mov     rax, cs:__security_cookie
0x1800035dd  xor     rax, rsp
0x1800035e0  mov     [rsp+68h+var_18], rax
0x1800035e5  mov     eax, cs:dword_180013018
0x1800035eb  mov     rbx, rcx
0x1800035ee  cmp     eax, 4
0x1800035f1  jbe     short loc_18000361E
0x1800035f3  lea     rax, [rsp+68h+var_38]
0x1800035f8  xor     r9d, r9d; int
0x1800035fb  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x180003600  lea     rdx, byte_1800100D9; int
0x180003607  xor     r8d, r8d; int
0x18000360a  mov     [rsp+68h+var_48], 2; ULONG
0x180003612  lea     rcx, dword_180013018; int
0x180003619  call    _tlgWriteTransfer_EventWriteTransfer
0x18000361e  xor     edx, edx; dwEventType
0x180003620  lea     r9, [rbx-0B8h]; lpContext
0x180003627  xor     r8d, r8d; lpEventData
0x18000362a  lea     ecx, [rdx+1]; dwControl
0x18000362d  call    ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)
0x180003632  mov     ebx, eax
0x180003634  test    eax, eax
0x180003636  jle     short loc_180003641
0x180003638  movzx   ebx, ax
0x18000363b  or      ebx, 80070000h
0x180003641  test    ebx, ebx
0x180003643  jns     short loc_18000365D
0x180003645  mov     r9d, 61h ; 'a'
0x18000364b  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x180003652  mov     ecx, ebx
0x180003654  call    Log_HREvent
0x180003659  mov     eax, ebx
0x18000365b  jmp     short loc_18000365F
0x18000365d  xor     eax, eax
0x18000365f  mov     rcx, [rsp+68h+var_18]
0x180003664  xor     rcx, rsp; StackCookie
0x180003667  call    __security_check_cookie
0x18000366c  add     rsp, 60h
0x180003670  pop     rbx
0x180003671  retn
```

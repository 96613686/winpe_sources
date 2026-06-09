# RMAPI::SetProxyBlanket(IUnknown *)

- ea: `0x1800097f0`
- end: `0x18000994c`
- name: `?SetProxyBlanket@RMAPI@@YAJPEAUIUnknown@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(RMAPI *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001dac0`

## callees

- `0x1800097f0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009923`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009923`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180009839`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180009839`

## pseudocode

```c
__int64 __fastcall RMAPI::SetProxyBlanket(IUnknown *this, struct IUnknown *a2)
{
  HRESULT v2; // eax
  int v3; // ebx
  _DWORD v5[2]; // [rsp+40h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-58h] BYREF
  char *v8; // [rsp+70h] [rbp-48h]
  int v9; // [rsp+78h] [rbp-40h]
  int v10; // [rsp+7Ch] [rbp-3Ch]
  const char *v11; // [rsp+80h] [rbp-38h]
  __int64 v12; // [rsp+88h] [rbp-30h]
  _DWORD *v13; // [rsp+90h] [rbp-28h]
  __int64 v14; // [rsp+98h] [rbp-20h]

  v2 = CoSetProxyBlanket(this, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  v3 = 0;
  if ( v2 != -2147467262 )
    v3 = v2;
  if ( v3 < 0 && (unsigned int)dword_180037050 > 2 )
  {
    v5[0] = v3;
    v13 = v5;
    v14 = 4;
    v11 = "CoSetProxyBlanket failed";
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_180037058;
    v12 = 25;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_180037058;
    v8 = byte_18003048D;
    UserData.Reserved = 2;
    v9 = 48;
    v10 = 1;
    v5[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800097f0  mov     [rsp+arg_8], rbx
0x1800097f5  push    rdi
0x1800097f6  sub     rsp, 0B0h
0x1800097fd  mov     rax, cs:__security_cookie
0x180009804  xor     rax, rsp
0x180009807  mov     [rsp+0B8h+var_18], rax
0x18000980f  mov     [rsp+0B8h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180009817  xor     edi, edi
0x180009819  mov     [rsp+0B8h+pAuthInfo], rdi; pAuthInfo
0x18000981e  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180009825  mov     [rsp+0B8h+dwImpLevel], 3; dwImpLevel
0x18000982d  xor     r8d, r8d; dwAuthzSvc
0x180009830  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180009835  mov     [rsp+0B8h+dwAuthnLevel], edi; dwAuthnLevel
0x180009839  call    cs:__imp_CoSetProxyBlanket
0x18000983f  cmp     eax, 80004002h
0x180009844  mov     ebx, edi
0x180009846  cmovnz  ebx, eax
0x180009849  test    ebx, ebx
0x18000984b  jns     loc_180009929
0x180009851  mov     eax, cs:dword_180037050
0x180009857  cmp     eax, 2
0x18000985a  jbe     loc_180009929
0x180009860  mov     [rsp+0B8h+var_78], ebx
0x180009864  lea     rax, [rsp+0B8h+var_78]
0x180009869  mov     [rsp+0B8h+var_28], rax
0x180009871  lea     rcx, _TraceLoggingMetadataEnd
0x180009878  lea     rax, aCosetproxyblan; "CoSetProxyBlanket failed"
0x18000987f  mov     [rsp+0B8h+var_20], 4
0x18000988b  mov     [rsp+0B8h+var_38], rax
0x180009893  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x180009898  movzx   eax, cs:word_180030483
0x18000989f  xor     r9d, r9d; RelatedActivityId
0x1800098a2  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x1800098a6  xor     r8d, r8d; ActivityId
0x1800098a9  mov     rax, cs:off_180037058
0x1800098b0  mov     [rsp+0B8h+UserData.Ptr], rax
0x1800098b5  mov     [rsp+0B8h+var_30], 19h
0x1800098c1  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x1800098c9  mov     [rsp+0B8h+EventDescriptor.Keyword], rdi
0x1800098ce  movzx   eax, word ptr [rax]
0x1800098d1  mov     [rsp+0B8h+UserData.Size], eax
0x1800098d5  lea     rax, byte_18003048D
0x1800098dc  mov     [rsp+0B8h+var_48], rax
0x1800098e1  lea     rax, _TraceLoggingMetadata
0x1800098e8  sub     ecx, eax
0x1800098ea  mov     dword ptr [rsp+0B8h+UserData.0Ch], 2
0x1800098f2  mov     [rsp+0B8h+var_40], 30h ; '0'
0x1800098fa  lea     rax, [rsp+0B8h+UserData]
0x1800098ff  mov     [rsp+0B8h+var_3C], 1
0x180009907  mov     [rsp+0B8h+var_74], ecx
0x18000990b  mov     ecx, [rsp+0B8h+var_74]
0x18000990f  mov     rcx, cs:RegHandle; RegHandle
0x180009916  mov     qword ptr [rsp+0B8h+dwImpLevel], rax; UserData
0x18000991b  mov     [rsp+0B8h+dwAuthnLevel], 4; UserDataCount
0x180009923  call    cs:__imp_EventWriteTransfer
0x180009929  mov     eax, ebx
0x18000992b  mov     rcx, [rsp+0B8h+var_18]
0x180009933  xor     rcx, rsp; StackCookie
0x180009936  call    __security_check_cookie
0x18000993b  mov     rbx, [rsp+0B8h+arg_8]
0x180009943  add     rsp, 0B0h
0x18000994a  pop     rdi
0x18000994b  retn
```

# CMidi2MidiSrv::RemoveClientSession(_GUID)

- ea: `0x180013730`
- end: `0x18001386f`
- name: `?RemoveClientSession@CMidi2MidiSrv@@QEAAJU_GUID@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CMidi2MidiSrv *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c830`

## callees

- `0x18000163c`
- `0x180002470`
- `0x180007e24`
- `0x180009bf8`
- `0x180011d1c`
- `0x180012610`
- `0x180013730`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18001380e`
- `RPCRT4!RpcBindingFree` at `0x18001384f`
- `RPCRT4!RpcBindingFree` at `0x18001380e`
- `RPCRT4!RpcBindingFree` at `0x18001384f`

## string_xrefs

- `0x18001378a`: `CMidi2MidiSrv::RemoveClientSession`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::RemoveClientSession(CMidi2MidiSrv *this, struct _GUID *a2)
{
  _DWORD *v4; // rcx
  int MidiSrvBindingHandle; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-79h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE v10; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+60h] [rbp-39h] BYREF
  const char *v13; // [rsp+80h] [rbp-19h]
  __int64 v14; // [rsp+88h] [rbp-11h]
  RPC_BINDING_HANDLE *p_Binding; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]
  const wchar_t *v17; // [rsp+A0h] [rbp+7h]
  __int64 v18; // [rsp+A8h] [rbp+Fh]
  struct _GUID *v19; // [rsp+B0h] [rbp+17h]
  __int64 v20; // [rsp+B8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    Binding = this;
    v17 = L"Removing client session";
    v19 = a2;
    p_Binding = &Binding;
    v20 = 16;
    v13 = "CMidi2MidiSrv::RemoveClientSession";
    v18 = 48;
    v16 = 8;
    v14 = 35;
    tlgWriteTransfer_EventWriteTransfer((__int64)v4, (unsigned __int8 *)qword_18001AAF0, 0, 0, 6u, &v12);
  }
  v10 = 0;
  MidiSrvBindingHandle = GetMidiSrvBindingHandle(&v10);
  if ( MidiSrvBindingHandle < 0 )
  {
    v6 = 379;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)(unsigned int)MidiSrvBindingHandle,
      v8);
    if ( v10 )
    {
      Binding = v10;
      RpcBindingFree(&Binding);
    }
    return (unsigned int)MidiSrvBindingHandle;
  }
  v11[1] = this;
  v11[0] = &v10;
  v11[2] = a2;
  MidiSrvBindingHandle = CMidi2MidiSrv::RemoveClientSession_::_16_::_lambda_1_::operator()(v11);
  if ( MidiSrvBindingHandle < 0 )
  {
    v6 = 390;
    goto LABEL_5;
  }
  if ( v10 )
  {
    Binding = v10;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x180013730  push    rbp
0x180013732  push    rbx
0x180013733  push    rsi
0x180013734  push    rdi
0x180013735  lea     rbp, [rsp-3Fh]
0x18001373a  sub     rsp, 0D8h
0x180013741  mov     rax, cs:__security_cookie
0x180013748  xor     rax, rsp
0x18001374b  mov     [rbp+57h+var_30], rax
0x18001374f  mov     rdi, rdx
0x180013752  mov     rsi, rcx
0x180013755  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18001375a  mov     rcx, [rax+8]
0x18001375e  mov     eax, [rcx]
0x180013760  cmp     eax, 4
0x180013763  jbe     short loc_1800137CE
0x180013765  lea     rax, aRemovingClient; "Removing client session"
0x18001376c  mov     [rbp+57h+Binding], rsi
0x180013770  mov     [rbp+57h+var_50], rax
0x180013774  lea     rdx, qword_18001AAF0
0x18001377b  lea     rax, [rbp+57h+Binding]
0x18001377f  mov     [rbp+57h+var_40], rdi
0x180013783  mov     [rbp+57h+var_60], rax
0x180013787  xor     r9d, r9d
0x18001378a  lea     rax, aCmidi2midisrvR; "CMidi2MidiSrv::RemoveClientSession"
0x180013791  mov     [rbp+57h+var_38], 10h
0x180013799  mov     [rbp+57h+var_70], rax
0x18001379d  xor     r8d, r8d
0x1800137a0  lea     rax, [rbp+57h+var_90]
0x1800137a4  mov     [rbp+57h+var_48], 30h ; '0'
0x1800137ac  mov     [rsp+0F0h+var_C8], rax
0x1800137b1  mov     [rsp+0F0h+var_D0], 6; int
0x1800137b9  mov     [rbp+57h+var_58], 8
0x1800137c1  mov     [rbp+57h+var_68], 23h ; '#'
0x1800137c9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800137ce  lea     rcx, [rbp+57h+var_B8]; Binding
0x1800137d2  mov     [rbp+57h+var_B8], 0
0x1800137da  call    ?GetMidiSrvBindingHandle@@YAJPEAPEAX@Z; GetMidiSrvBindingHandle(void * *)
0x1800137df  mov     ebx, eax
0x1800137e1  test    eax, eax
0x1800137e3  jns     short loc_180013818
0x1800137e5  mov     edx, 17Bh; void *
0x1800137ea  mov     rcx, [rbp+5Fh]; this
0x1800137ee  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x1800137f5  mov     r9d, ebx; char *
0x1800137f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137fd  mov     rcx, [rbp+57h+var_B8]
0x180013801  test    rcx, rcx
0x180013804  jz      short loc_180013814
0x180013806  mov     [rbp+57h+Binding], rcx
0x18001380a  lea     rcx, [rbp+57h+Binding]; Binding
0x18001380e  call    cs:__imp_RpcBindingFree
0x180013814  mov     eax, ebx
0x180013816  jmp     short loc_180013857
0x180013818  lea     rax, [rbp+57h+var_B8]
0x18001381c  mov     [rbp+57h+var_A8], rsi
0x180013820  lea     rcx, [rbp+57h+var_B0]
0x180013824  mov     [rbp+57h+var_B0], rax
0x180013828  mov     [rbp+57h+var_A0], rdi
0x18001382c  call    _CMidi2MidiSrv__RemoveClientSession____16____lambda_1___operator__
0x180013831  mov     ebx, eax
0x180013833  test    eax, eax
0x180013835  jns     short loc_18001383E
0x180013837  mov     edx, 186h
0x18001383c  jmp     short loc_1800137EA
0x18001383e  mov     rax, [rbp+57h+var_B8]
0x180013842  test    rax, rax
0x180013845  jz      short loc_180013855
0x180013847  lea     rcx, [rbp+57h+Binding]; Binding
0x18001384b  mov     [rbp+57h+Binding], rax
0x18001384f  call    cs:__imp_RpcBindingFree
0x180013855  xor     eax, eax
0x180013857  mov     rcx, [rbp+57h+var_30]
0x18001385b  xor     rcx, rsp; StackCookie
0x18001385e  call    __security_check_cookie
0x180013863  add     rsp, 0D8h
0x18001386a  pop     rdi
0x18001386b  pop     rsi
0x18001386c  pop     rbx
0x18001386d  pop     rbp
0x18001386e  retn
```

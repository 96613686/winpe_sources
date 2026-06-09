# CMidi2MidiSrv::UpdateClientSessionName(_GUID,ushort const *)

- ea: `0x180013a3c`
- end: `0x180013bec`
- name: `?UpdateClientSessionName@CMidi2MidiSrv@@QEAAJU_GUID@@PEBG@Z`
- size: `432`
- prototype: `__int64 __fastcall(CMidi2MidiSrv *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000c9a0`

## callees

- `0x18000163c`
- `0x180002470`
- `0x180007e24`
- `0x180009bf8`
- `0x180012064`
- `0x180012610`
- `0x180013a3c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180013b65`
- `RPCRT4!RpcBindingFree` at `0x180013bc0`
- `RPCRT4!RpcBindingFree` at `0x180013b65`
- `RPCRT4!RpcBindingFree` at `0x180013bc0`

## string_xrefs

- `0x180013ae1`: `CMidi2MidiSrv::UpdateClientSessionName`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::UpdateClientSessionName(
        CMidi2MidiSrv *this,
        struct _GUID *a2,
        const unsigned __int16 *a3)
{
  _DWORD *v5; // r10
  __int64 *v6; // rax
  __int64 v7; // rcx
  int v8; // ecx
  int MidiSrvBindingHandle; // ebx
  __int64 v10; // rdx
  int v12; // [rsp+28h] [rbp-79h]
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE v14; // [rsp+40h] [rbp-61h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+68h] [rbp-39h] BYREF
  const char *v17; // [rsp+88h] [rbp-19h]
  __int64 v18; // [rsp+90h] [rbp-11h]
  RPC_BINDING_HANDLE *p_Binding; // [rsp+98h] [rbp-9h]
  __int64 v20; // [rsp+A0h] [rbp-1h]
  const wchar_t *v21; // [rsp+A8h] [rbp+7h]
  __int64 v22; // [rsp+B0h] [rbp+Fh]
  struct _GUID *v23; // [rsp+B8h] [rbp+17h]
  __int64 v24; // [rsp+C0h] [rbp+1Fh]
  __int64 *v25; // [rsp+C8h] [rbp+27h]
  int v26; // [rsp+D0h] [rbp+2Fh]
  int v27; // [rsp+D4h] [rbp+33h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]
  const unsigned __int16 *v29; // [rsp+118h] [rbp+77h] BYREF

  v29 = a3;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v6 = (__int64 *)v29;
    Binding = this;
    if ( v29 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v29[v7] );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v6 = qword_180017FF0;
      v8 = 2;
    }
    v25 = v6;
    v26 = v8;
    v21 = L"Updating session name";
    v27 = 0;
    p_Binding = &Binding;
    v23 = a2;
    v17 = "CMidi2MidiSrv::UpdateClientSessionName";
    v24 = 16;
    v22 = 44;
    v20 = 8;
    v18 = 39;
    tlgWriteTransfer_EventWriteTransfer((__int64)v5, (unsigned __int8 *)&word_18001AB2E, 0, 0, 7u, &v16);
  }
  v14 = 0;
  MidiSrvBindingHandle = GetMidiSrvBindingHandle(&v14);
  if ( MidiSrvBindingHandle < 0 )
  {
    v10 = 343;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)(unsigned int)MidiSrvBindingHandle,
      v12);
    if ( v14 )
    {
      Binding = v14;
      RpcBindingFree(&Binding);
    }
    return (unsigned int)MidiSrvBindingHandle;
  }
  if ( !v29 )
  {
    MidiSrvBindingHandle = -2147024809;
    v10 = 344;
    goto LABEL_10;
  }
  v15[1] = this;
  v15[0] = &v14;
  v15[2] = a2;
  v15[3] = &v29;
  MidiSrvBindingHandle = CMidi2MidiSrv::UpdateClientSessionName_::_26_::_lambda_1_::operator()(v15);
  if ( MidiSrvBindingHandle < 0 )
  {
    v10 = 355;
    goto LABEL_10;
  }
  if ( v14 )
  {
    Binding = v14;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x180013a3c  mov     rax, rsp
0x180013a3f  mov     [rax+8], rbx
0x180013a43  mov     [rax+10h], rsi
0x180013a47  mov     [rax+18h], r8
0x180013a4b  push    rbp
0x180013a4c  push    rdi
0x180013a4d  push    r14
0x180013a4f  lea     rbp, [rax-5Fh]
0x180013a53  sub     rsp, 0E0h
0x180013a5a  mov     rax, cs:__security_cookie
0x180013a61  xor     rax, rsp
0x180013a64  mov     [rbp+57h+var_20], rax
0x180013a68  mov     rsi, rdx
0x180013a6b  mov     rdi, rcx
0x180013a6e  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x180013a73  xor     r14d, r14d
0x180013a76  mov     r10, [rax+8]
0x180013a7a  mov     eax, [r10]
0x180013a7d  cmp     eax, 4
0x180013a80  jbe     loc_180013B29
0x180013a86  mov     rax, [rbp+57h+arg_10]
0x180013a8a  mov     [rbp+57h+Binding], rdi
0x180013a8e  test    rax, rax
0x180013a91  jz      short loc_180013AAA
0x180013a93  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013a97  inc     rcx
0x180013a9a  cmp     [rax+rcx*2], r14w
0x180013a9f  jnz     short loc_180013A97
0x180013aa1  lea     ecx, ds:2[rcx*2]
0x180013aa8  jmp     short loc_180013AB6
0x180013aaa  lea     rax, qword_180017FF0
0x180013ab1  mov     ecx, 2
0x180013ab6  mov     [rbp+57h+var_30], rax
0x180013aba  lea     rdx, word_18001AB2E
0x180013ac1  lea     rax, aUpdatingSessio; "Updating session name"
0x180013ac8  mov     [rbp+57h+var_28], ecx
0x180013acb  mov     [rbp+57h+var_50], rax
0x180013acf  xor     r9d, r9d
0x180013ad2  lea     rax, [rbp+57h+Binding]
0x180013ad6  mov     [rbp+57h+var_24], r14d
0x180013ada  mov     [rbp+57h+var_60], rax
0x180013ade  xor     r8d, r8d
0x180013ae1  lea     rax, aCmidi2midisrvU_1; "CMidi2MidiSrv::UpdateClientSessionName"
0x180013ae8  mov     [rbp+57h+var_40], rsi
0x180013aec  mov     [rbp+57h+var_70], rax
0x180013af0  mov     rcx, r10
0x180013af3  lea     rax, [rbp+57h+var_90]
0x180013af7  mov     [rbp+57h+var_38], 10h
0x180013aff  mov     [rsp+0F0h+var_C8], rax
0x180013b04  mov     [rsp+0F0h+var_D0], 7; int
0x180013b0c  mov     [rbp+57h+var_48], 2Ch ; ','
0x180013b14  mov     [rbp+57h+var_58], 8
0x180013b1c  mov     [rbp+57h+var_68], 27h ; '''
0x180013b24  call    _tlgWriteTransfer_EventWriteTransfer
0x180013b29  lea     rcx, [rbp+57h+var_B8]; Binding
0x180013b2d  mov     [rbp+57h+var_B8], r14
0x180013b31  call    ?GetMidiSrvBindingHandle@@YAJPEAPEAX@Z; GetMidiSrvBindingHandle(void * *)
0x180013b36  mov     ebx, eax
0x180013b38  test    eax, eax
0x180013b3a  jns     short loc_180013B6F
0x180013b3c  mov     edx, 157h; void *
0x180013b41  mov     rcx, [rbp+5Fh]; this
0x180013b45  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x180013b4c  mov     r9d, ebx; char *
0x180013b4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b54  mov     rcx, [rbp+57h+var_B8]
0x180013b58  test    rcx, rcx
0x180013b5b  jz      short loc_180013B6B
0x180013b5d  mov     [rbp+57h+Binding], rcx
0x180013b61  lea     rcx, [rbp+57h+Binding]; Binding
0x180013b65  call    cs:__imp_RpcBindingFree
0x180013b6b  mov     eax, ebx
0x180013b6d  jmp     short loc_180013BC8
0x180013b6f  cmp     [rbp+57h+arg_10], r14
0x180013b73  jnz     short loc_180013B81
0x180013b75  mov     ebx, 80070057h
0x180013b7a  mov     edx, 158h
0x180013b7f  jmp     short loc_180013B41
0x180013b81  lea     rax, [rbp+57h+var_B8]
0x180013b85  mov     [rbp+57h+var_A8], rdi
0x180013b89  mov     [rbp+57h+var_B0], rax
0x180013b8d  lea     rcx, [rbp+57h+var_B0]
0x180013b91  lea     rax, [rbp+57h+arg_10]
0x180013b95  mov     [rbp+57h+var_A0], rsi
0x180013b99  mov     [rbp+57h+var_98], rax
0x180013b9d  call    _CMidi2MidiSrv__UpdateClientSessionName____26____lambda_1___operator__
0x180013ba2  mov     ebx, eax
0x180013ba4  test    eax, eax
0x180013ba6  jns     short loc_180013BAF
0x180013ba8  mov     edx, 163h
0x180013bad  jmp     short loc_180013B41
0x180013baf  mov     rax, [rbp+57h+var_B8]
0x180013bb3  test    rax, rax
0x180013bb6  jz      short loc_180013BC6
0x180013bb8  lea     rcx, [rbp+57h+Binding]; Binding
0x180013bbc  mov     [rbp+57h+Binding], rax
0x180013bc0  call    cs:__imp_RpcBindingFree
0x180013bc6  xor     eax, eax
0x180013bc8  mov     rcx, [rbp+57h+var_20]
0x180013bcc  xor     rcx, rsp; StackCookie
0x180013bcf  call    __security_check_cookie
0x180013bd4  lea     r11, [rsp+0F0h+var_10]
0x180013bdc  mov     rbx, [r11+20h]
0x180013be0  mov     rsi, [r11+28h]
0x180013be4  mov     rsp, r11
0x180013be7  pop     r14
0x180013be9  pop     rdi
0x180013bea  pop     rbp
0x180013beb  retn
```

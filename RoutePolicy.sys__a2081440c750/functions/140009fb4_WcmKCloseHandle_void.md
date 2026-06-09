# WcmKCloseHandle(void *)

- ea: `0x140009fb4`
- end: `0x140009ff2`
- name: `?WcmKCloseHandle@@YAXPEAX@Z`
- size: `62`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003f18`
- `0x140005034`
- `0x140006cc4`
- `0x140006e28`

## callees

- `0x14000935c`
- `0x140009fb4`

## import_xrefs

- `msrpc!RpcBindingUnbind` at `0x140009fbd`
- `msrpc!RpcBindingUnbind` at `0x140009fbd`
- `msrpc!RpcBindingFree` at `0x140009fd7`
- `msrpc!RpcBindingFree` at `0x140009fd7`

## pseudocode

```c
void __fastcall WcmKCloseHandle(void *a1)
{
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  Binding = a1;
  if ( RpcBindingUnbind(a1) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( RpcBindingFree(&Binding) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
}

```

## disassembly

```asm
0x140009fb4  mov     [rsp+Binding], rcx
0x140009fb9  sub     rsp, 28h
0x140009fbd  call    cs:__imp_RpcBindingUnbind
0x140009fc4  nop     dword ptr [rax+rax+00h]
0x140009fc9  test    eax, eax
0x140009fcb  jz      short loc_140009FD2
0x140009fcd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009fd2  lea     rcx, [rsp+28h+Binding]; Binding
0x140009fd7  call    cs:__imp_RpcBindingFree
0x140009fde  nop     dword ptr [rax+rax+00h]
0x140009fe3  test    eax, eax
0x140009fe5  jz      short loc_140009FEC
0x140009fe7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009fec  add     rsp, 28h
0x140009ff0  retn
```

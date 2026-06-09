# UbpmEnableTaskHostChannelRpcInterface

- ea: `0x18002cc0c`
- end: `0x18002cdb9`
- name: `UbpmEnableTaskHostChannelRpcInterface`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c420`

## callees

- `0x18002cc0c`
- `0x1800351ec`
- `0x180036c60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cc80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cc80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cc19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002cc19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc98`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002cd4d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002cd4d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002cce3`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002cce3`

## string_xrefs

- `0x18002cc12`: `rpcrt4.dll`
- `0x18002cc76`: `I_RpcOpenClientProcess`
- `0x18002ccd1`: `ubpmtaskhostchannel`

## pseudocode

```c
__int64 UbpmEnableTaskHostChannelRpcInterface()
{
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // eax
  DWORD v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  ModuleHandleW = GetModuleHandleW(L"rpcrt4.dll");
  if ( ModuleHandleW )
  {
    s_pfnI_RpcOpenClientProcess = (int (*)(void *, unsigned int, void **))GetProcAddress(
                                                                            ModuleHandleW,
                                                                            "I_RpcOpenClientProcess");
    if ( s_pfnI_RpcOpenClientProcess )
    {
      LastError = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"ubpmtaskhostchannel", 0);
      v2 = LastError;
      if ( !LastError || LastError == 1740 )
      {
        LastError = RpcServerRegisterIfEx(
                      qword_1800422C0,
                      0,
                      0,
                      0x21u,
                      0x4D2u,
                      (RPC_IF_CALLBACK_FN *)UbpmpTaskHostChannelInterfaceSecurityCb);
        v2 = LastError;
        if ( LastError )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 15;
            goto LABEL_5;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 14;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 13;
        goto LABEL_5;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 12;
LABEL_5:
      WPP_SF_d(v3[2], v4, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002cc0c  push    rbx
0x18002cc0e  sub     rsp, 30h
0x18002cc12  lea     rcx, ModuleName; "rpcrt4.dll"
0x18002cc19  call    cs:__imp_GetModuleHandleW
0x18002cc20  nop     dword ptr [rax+rax+00h]
0x18002cc25  test    rax, rax
0x18002cc28  jnz     short loc_18002CC76
0x18002cc2a  call    cs:__imp_GetLastError
0x18002cc31  nop     dword ptr [rax+rax+00h]
0x18002cc36  mov     ebx, eax
0x18002cc38  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc3f  lea     rdx, WPP_GLOBAL_Control
0x18002cc46  cmp     rcx, rdx
0x18002cc49  jz      loc_18002CDB0
0x18002cc4f  test    byte ptr [rcx+1Ch], 1
0x18002cc53  jz      loc_18002CDB0
0x18002cc59  mov     edx, 0Ch
0x18002cc5e  mov     rcx, [rcx+10h]
0x18002cc62  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002cc69  mov     r9d, eax
0x18002cc6c  call    WPP_SF_d
0x18002cc71  jmp     loc_18002CDB0
0x18002cc76  lea     rdx, ProcName; "I_RpcOpenClientProcess"
0x18002cc7d  mov     rcx, rax; hModule
0x18002cc80  call    cs:__imp_GetProcAddress
0x18002cc87  nop     dword ptr [rax+rax+00h]
0x18002cc8c  mov     cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA, rax; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x18002cc93  test    rax, rax
0x18002cc96  jnz     short loc_18002CCCE
0x18002cc98  call    cs:__imp_GetLastError
0x18002cc9f  nop     dword ptr [rax+rax+00h]
0x18002cca4  mov     ebx, eax
0x18002cca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccad  lea     rdx, WPP_GLOBAL_Control
0x18002ccb4  cmp     rcx, rdx
0x18002ccb7  jz      loc_18002CDB0
0x18002ccbd  test    byte ptr [rcx+1Ch], 1
0x18002ccc1  jz      loc_18002CDB0
0x18002ccc7  mov     edx, 0Dh
0x18002cccc  jmp     short loc_18002CC5E
0x18002ccce  xor     r9d, r9d; SecurityDescriptor
0x18002ccd1  lea     r8, Endpoint; "ubpmtaskhostchannel"
0x18002ccd8  lea     rcx, Protseq; "ncalrpc"
0x18002ccdf  lea     edx, [r9+0Ah]; MaxCalls
0x18002cce3  call    cs:__imp_RpcServerUseProtseqEpW
0x18002ccea  nop     dword ptr [rax+rax+00h]
0x18002ccef  mov     ebx, eax
0x18002ccf1  test    eax, eax
0x18002ccf3  jz      short loc_18002CD27
0x18002ccf5  cmp     eax, 6CCh
0x18002ccfa  jz      short loc_18002CD27
0x18002ccfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd03  lea     rdx, WPP_GLOBAL_Control
0x18002cd0a  cmp     rcx, rdx
0x18002cd0d  jz      loc_18002CDB0
0x18002cd13  test    byte ptr [rcx+1Ch], 1
0x18002cd17  jz      loc_18002CDB0
0x18002cd1d  mov     edx, 0Eh
0x18002cd22  jmp     loc_18002CC5E
0x18002cd27  lea     rax, UbpmpTaskHostChannelInterfaceSecurityCb
0x18002cd2e  mov     r9d, 21h ; '!'; Flags
0x18002cd34  mov     [rsp+38h+IfCallback], rax; IfCallback
0x18002cd39  lea     rcx, qword_1800422C0; IfSpec
0x18002cd40  xor     r8d, r8d; MgrEpv
0x18002cd43  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x18002cd4b  xor     edx, edx; MgrTypeUuid
0x18002cd4d  call    cs:__imp_RpcServerRegisterIfEx
0x18002cd54  nop     dword ptr [rax+rax+00h]
0x18002cd59  mov     ebx, eax
0x18002cd5b  test    eax, eax
0x18002cd5d  jz      short loc_18002CD82
0x18002cd5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd66  lea     rdx, WPP_GLOBAL_Control
0x18002cd6d  cmp     rcx, rdx
0x18002cd70  jz      short loc_18002CDB0
0x18002cd72  test    byte ptr [rcx+1Ch], 1
0x18002cd76  jz      short loc_18002CDB0
0x18002cd78  mov     edx, 0Fh
0x18002cd7d  jmp     loc_18002CC5E
0x18002cd82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd89  lea     rdx, WPP_GLOBAL_Control
0x18002cd90  cmp     rcx, rdx
0x18002cd93  jz      short loc_18002CDB0
0x18002cd95  test    byte ptr [rcx+1Ch], 80h
0x18002cd99  jz      short loc_18002CDB0
0x18002cd9b  mov     rcx, [rcx+10h]
0x18002cd9f  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002cda6  mov     edx, 10h
0x18002cdab  call    WPP_SF_
0x18002cdb0  mov     eax, ebx
0x18002cdb2  add     rsp, 30h
0x18002cdb6  pop     rbx
0x18002cdb7  retn
```

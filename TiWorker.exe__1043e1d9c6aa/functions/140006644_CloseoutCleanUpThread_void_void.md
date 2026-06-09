# CloseoutCleanUpThread(void *,void *)

- ea: `0x140006644`
- end: `0x1400066f5`
- name: `?CloseoutCleanUpThread@@YA_NPEAX0@Z`
- size: `177`
- prototype: `char __fastcall(HANDLE hHandle, HANDLE hEvent)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007228`

## callees

- `0x140006644`
- `0x14000e328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006676`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006676`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006668`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066b9`

## string_xrefs

- `0x140006680`: `Completed cleanup thread`
- `0x1400066a1`: `Directory cleanup thread timed out`
- `0x1400066cf`: `Error waiting for cleanup thread`

## pseudocode

```c
char __fastcall CloseoutCleanUpThread(HANDLE hHandle, HANDLE hEvent)
{
  char v2; // bl
  DWORD v4; // eax
  signed int LastError; // eax
  bool v6; // sf

  v2 = 0;
  if ( hHandle && hEvent )
  {
    SetEvent(hEvent);
    v4 = WaitForSingleObject(hHandle, 0x7D0u);
    if ( v4 )
    {
      if ( v4 == 258 )
      {
        CBSWdsLog(0x4000000u, 0, 0, "Directory cleanup thread timed out");
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v6 = LastError < 0;
        }
        if ( v6 )
          CBSWdsLog(0x4000000u, LastError, (size_t *)1, "Error waiting for cleanup thread");
      }
    }
    else
    {
      CBSWdsLog(0x4000000u, 0, 0, "Completed cleanup thread");
      return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140006644  mov     [rsp+arg_0], rbx
0x140006649  push    rdi
0x14000664a  sub     rsp, 20h
0x14000664e  xor     bl, bl
0x140006650  mov     rdi, rcx
0x140006653  test    rcx, rcx
0x140006656  jz      loc_1400066E8
0x14000665c  test    rdx, rdx
0x14000665f  jz      loc_1400066E8
0x140006665  mov     rcx, rdx; hEvent
0x140006668  call    cs:__imp_SetEvent
0x14000666e  mov     edx, 7D0h; dwMilliseconds
0x140006673  mov     rcx, rdi; hHandle
0x140006676  call    cs:__imp_WaitForSingleObject
0x14000667c  test    eax, eax
0x14000667e  jnz     short loc_14000669A
0x140006680  lea     r9, aCompletedClean; "Completed cleanup thread"
0x140006687  xor     r8d, r8d
0x14000668a  xor     edx, edx
0x14000668c  mov     ecx, 4000000h
0x140006691  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140006696  mov     bl, 1
0x140006698  jmp     short loc_1400066E8
0x14000669a  cmp     eax, 102h
0x14000669f  jnz     short loc_1400066B9
0x1400066a1  lea     r9, aDirectoryClean; "Directory cleanup thread timed out"
0x1400066a8  xor     r8d, r8d
0x1400066ab  xor     edx, edx
0x1400066ad  mov     ecx, 4000000h
0x1400066b2  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400066b7  jmp     short loc_1400066E8
0x1400066b9  call    cs:__imp_GetLastError
0x1400066bf  test    eax, eax
0x1400066c1  jle     short loc_1400066CD
0x1400066c3  movzx   eax, ax
0x1400066c6  or      eax, 80070000h
0x1400066cb  test    eax, eax
0x1400066cd  jns     short loc_1400066E8
0x1400066cf  lea     r9, aErrorWaitingFo; "Error waiting for cleanup thread"
0x1400066d6  mov     r8d, 1
0x1400066dc  mov     edx, eax
0x1400066de  mov     ecx, 4000000h
0x1400066e3  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400066e8  mov     al, bl
0x1400066ea  mov     rbx, [rsp+28h+arg_0]
0x1400066ef  add     rsp, 20h
0x1400066f3  pop     rdi
0x1400066f4  retn
```

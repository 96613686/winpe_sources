# Microsoft::CoreUI::ETW::ETWTrace::InitializeClass(bool)

- ea: `0x180083900`
- end: `0x180083951`
- name: `?InitializeClass@ETWTrace@ETW@CoreUI@Microsoft@@SAX_N@Z`
- size: `81`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ceac`

## callees

- `0x18001eb98`
- `0x180083900`
- `0x180083958`
- `0x18008c9f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180083929`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180083938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180083929`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180083938`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::ETW::ETWTrace::InitializeClass(char a1)
{
  DWORD CurrentProcessId; // eax
  __int64 v2; // rcx
  __int64 *v3; // rdx

  if ( !a1 )
  {
    McGenEventUnregister_EventUnregister();
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 1) == 0 )
      return;
    CurrentProcessId = GetCurrentProcessId();
    v3 = ETW_Uninit;
LABEL_7:
    McTemplateU0q_EventWriteTransfer(v2, v3, CurrentProcessId);
    return;
  }
  McGenEventRegister_EventRegister();
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 1) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v3 = ETW_Init;
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x180083900  sub     rsp, 28h
0x180083904  test    cl, cl
0x180083906  jnz     short loc_18008391B
0x180083908  call    McGenEventUnregister_EventUnregister
0x18008390d  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 1
0x180083914  jnz     short loc_180083938
0x180083916  add     rsp, 28h
0x18008391a  retn
0x18008391b  call    McGenEventRegister_EventRegister
0x180083920  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 1
0x180083927  jz      short loc_180083916
0x180083929  call    cs:__imp_GetCurrentProcessId
0x18008392f  lea     rdx, ETW_Init
0x180083936  jmp     short loc_180083945
0x180083938  call    cs:__imp_GetCurrentProcessId
0x18008393e  lea     rdx, ETW_Uninit
0x180083945  mov     r8d, eax
0x180083948  add     rsp, 28h
0x18008394c  jmp     McTemplateU0q_EventWriteTransfer
```

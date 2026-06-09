# AiSvcpConfigureAppID(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800031d0`
- end: `0x18000325f`
- name: `?AiSvcpConfigureAppID@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `143`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800031d0`
- `0x180004870`
- `0x1800049a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000322d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000322d`
- `USERENV!RegisterGPNotification` at `0x180003223`
- `USERENV!RegisterGPNotification` at `0x180003223`

## string_xrefs

- `0x1800031f6`: `AiSvcpConfigureAppID`

## pseudocode

```c
void __fastcall AiSvcpConfigureAppID(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  DWORD LastError; // eax
  __int64 v4; // r8

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids,
      "AiSvcpConfigureAppID");
  if ( AiSvcpSrpEnabled )
  {
    if ( !RegisterGPNotification(AiSvcpGroupPolicyChangeEvent, 1) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v4, LastError);
    }
  }
}

```

## disassembly

```asm
0x1800031d0  push    rdi
0x1800031d2  sub     rsp, 20h
0x1800031d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031dd  lea     rdi, WPP_GLOBAL_Control
0x1800031e4  cmp     rcx, rdi
0x1800031e7  jz      short loc_18000320E
0x1800031e9  test    dword ptr [rcx+1Ch], 400h
0x1800031f0  jz      short loc_18000320E
0x1800031f2  mov     rcx, [rcx+10h]
0x1800031f6  lea     r9, aAisvcpconfigur; "AiSvcpConfigureAppID"
0x1800031fd  mov     edx, 2Fh ; '/'
0x180003202  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x180003209  call    WPP_SF_s
0x18000320e  cmp     cs:?AiSvcpSrpEnabled@@3KA, 0; ulong AiSvcpSrpEnabled
0x180003215  jz      short loc_180003259
0x180003217  mov     rcx, cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA; hEvent
0x18000321e  mov     edx, 1; bMachine
0x180003223  call    cs:__imp_RegisterGPNotification
0x180003229  test    eax, eax
0x18000322b  jnz     short loc_180003259
0x18000322d  call    cs:__imp_GetLastError
0x180003233  mov     rcx, cs:WPP_GLOBAL_Control
0x18000323a  cmp     rcx, rdi
0x18000323d  jz      short loc_180003259
0x18000323f  test    dword ptr [rcx+1Ch], 400h
0x180003246  jz      short loc_180003259
0x180003248  mov     rcx, [rcx+10h]
0x18000324c  mov     edx, 30h ; '0'
0x180003251  mov     r9d, eax
0x180003254  call    WPP_SF_d
0x180003259  add     rsp, 20h
0x18000325d  pop     rdi
0x18000325e  retn
```

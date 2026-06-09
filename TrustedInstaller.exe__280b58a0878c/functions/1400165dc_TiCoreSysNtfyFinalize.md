# TiCoreSysNtfyFinalize

- ea: `0x1400165dc`
- end: `0x1400166e9`
- name: `TiCoreSysNtfyFinalize`
- size: `269`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140016210`
- `0x14001681c`

## callees

- `0x14000add4`
- `0x1400165dc`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1400166d2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1400166d2`

## string_xrefs

- `0x140016683`: `Winlogon: Unloading SysNotify DLL`

## pseudocode

```c
void TiCoreSysNtfyFinalize()
{
  int v0; // eax
  unsigned int v1; // ebx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( hLibModule )
  {
    if ( vpvWinlogonNotificationContext )
    {
      CBSWdsLogLight(0x4000000u, 0, 0, "Winlogon: Stopping notify server");
      if ( vpfnSysNotifyStartServer )
      {
        v0 = ((__int64 (__fastcall *)(void **))vpfnSysNotifyStopServer)(&vpvWinlogonNotificationContext);
        v1 = v0;
        if ( v0 )
        {
          if ( v0 > 0 )
            v1 = (unsigned __int16)v0 | 0x80070000;
          CBSWdsLogLight(0x4000000u, v1, (size_t *)1, "Failed unregistering for Winlogon notifications");
          if ( (v1 & 0x80000000) != 0 )
            CBSWdsLogLight(0x4000000u, v1, (size_t *)1, "Unable to unregister Winlogon notification");
        }
      }
      vpvWinlogonNotificationContext = 0;
    }
    CBSWdsLogLight(0x4000000u, 0, 0, "Winlogon: Unloading SysNotify DLL");
    if ( !hLibModule )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\base\\cbs\\ti\\cbssysntfywrapper.cpp",
        v2);
    vpfnSysNotifyStartServer = 0;
    vpfnSysNotifyStopServer = 0;
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
}

```

## disassembly

```asm
0x1400165dc  push    rbx
0x1400165de  sub     rsp, 20h
0x1400165e2  cmp     cs:hLibModule, 0
0x1400165ea  jz      loc_1400166E3
0x1400165f0  cmp     cs:?vpvWinlogonNotificationContext@@3PEAXEA, 0; void * vpvWinlogonNotificationContext
0x1400165f8  jz      loc_140016683
0x1400165fe  lea     r9, aWinlogonStoppi; "Winlogon: Stopping notify server"
0x140016605  xor     r8d, r8d
0x140016608  xor     edx, edx
0x14001660a  mov     ecx, 4000000h
0x14001660f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016614  cmp     cs:?vpfnSysNotifyStartServer@@3P6AJPEBDKPEBU_SN_NOTIFY_FUNCTIONS@@PEAXPEAPEAX@ZEA, 0; long (*vpfnSysNotifyStartServer)(char const *,ulong,_SN_NOTIFY_FUNCTIONS const *,void *,void * *)
0x14001661c  jz      short loc_140016678
0x14001661e  mov     rax, cs:?vpfnSysNotifyStopServer@@3P6AJPEAPEAX@ZEA; long (*vpfnSysNotifyStopServer)(void * *)
0x140016625  lea     rcx, ?vpvWinlogonNotificationContext@@3PEAXEA; void * vpvWinlogonNotificationContext
0x14001662c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016631  mov     ebx, eax
0x140016633  test    eax, eax
0x140016635  jz      short loc_140016678
0x140016637  jle     short loc_140016642
0x140016639  movzx   ebx, ax
0x14001663c  or      ebx, 80070000h
0x140016642  lea     r9, aFailedUnregist; "Failed unregistering for Winlogon notif"...
0x140016649  mov     r8d, 1
0x14001664f  mov     edx, ebx
0x140016651  mov     ecx, 4000000h
0x140016656  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001665b  test    ebx, ebx
0x14001665d  jns     short loc_140016678
0x14001665f  lea     r9, aUnableToUnregi; "Unable to unregister Winlogon notificat"...
0x140016666  mov     r8d, 1
0x14001666c  mov     edx, ebx
0x14001666e  mov     ecx, 4000000h
0x140016673  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016678  mov     cs:?vpvWinlogonNotificationContext@@3PEAXEA, 0; void * vpvWinlogonNotificationContext
0x140016683  lea     r9, aWinlogonUnload; "Winlogon: Unloading SysNotify DLL"
0x14001668a  xor     r8d, r8d
0x14001668d  xor     edx, edx
0x14001668f  mov     ecx, 4000000h
0x140016694  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016699  mov     rcx, cs:hLibModule; hLibModule
0x1400166a0  test    rcx, rcx
0x1400166a3  jnz     short loc_1400166BC
0x1400166a5  mov     rcx, [rsp+28h]; this
0x1400166aa  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\ti\\cbssysntfywrapp"...
0x1400166b1  mov     edx, 57h ; 'W'; void *
0x1400166b6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400166bc  mov     cs:?vpfnSysNotifyStartServer@@3P6AJPEBDKPEBU_SN_NOTIFY_FUNCTIONS@@PEAXPEAPEAX@ZEA, 0; long (*vpfnSysNotifyStartServer)(char const *,ulong,_SN_NOTIFY_FUNCTIONS const *,void *,void * *)
0x1400166c7  mov     cs:?vpfnSysNotifyStopServer@@3P6AJPEAPEAX@ZEA, 0; long (*vpfnSysNotifyStopServer)(void * *)
0x1400166d2  call    cs:__imp_FreeLibrary
0x1400166d8  mov     cs:hLibModule, 0
0x1400166e3  add     rsp, 20h
0x1400166e7  pop     rbx
0x1400166e8  retn
```

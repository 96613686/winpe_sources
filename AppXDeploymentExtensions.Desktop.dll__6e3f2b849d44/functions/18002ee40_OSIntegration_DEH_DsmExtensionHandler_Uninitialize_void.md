# OSIntegration::DEH::DsmExtensionHandler::Uninitialize(void)

- ea: `0x18002ee40`
- end: `0x18002f152`
- name: `?Uninitialize@DsmExtensionHandler@DEH@OSIntegration@@UEAAXXZ`
- size: `786`
- prototype: `void __fastcall(OSIntegration::DEH::DsmExtensionHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18002edc0`

## callees

- `0x180012fc8`
- `0x18002ee40`
- `0x180073e84`
- `0x180073ec8`
- `0x180073fc4`
- `0x180074504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f141`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ef60`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002ef60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ef43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002ef43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002eee3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ef78`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002eee3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ef78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ef30`
- `ntdll!RtlPublishWnfStateData` at `0x18002eea8`
- `ntdll!RtlPublishWnfStateData` at `0x18002f071`
- `ntdll!RtlPublishWnfStateData` at `0x18002eea8`
- `ntdll!RtlPublishWnfStateData` at `0x18002f071`

## string_xrefs

- `0x18002ef9e`: `onecore\admin\appmodel\osim\src\deh\dsm\dsmextensionhandler.cpp`
- `0x18002f093`: `onecore\admin\appmodel\osim\src\deh\dsm\dsmextensionhandler.cpp`
- `0x18002f0ee`: `onecore\admin\appmodel\osim\src\deh\dsm\dsmextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OSIntegration::DEH::DsmExtensionHandler::Uninitialize(OSIntegration::DEH::DsmExtensionHandler *this)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // eax
  unsigned int v6; // esi
  char *v7; // rcx
  HANDLE CurrentThread; // rax
  signed int v9; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  const WCHAR *v12; // rsi
  const WCHAR *v13; // rax
  const WCHAR *v14; // r9
  const WCHAR *v15; // rax
  signed int LastError; // eax
  __int64 v17; // r8
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE Token; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 64) )
  {
    Token = 0;
    if ( !NtCurrentTeb()->IsImpersonating )
      goto LABEL_3;
    Token = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &Token) && SetThreadToken(0, 0) )
    {
      v9 = 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\dsm\\dsmextensionhandler.cpp",
        (const char *)(unsigned int)v9,
        v22);
      v12 = &Value;
      if ( (byte_180245607 & 0x10) != 0 )
      {
        v13 = &Value;
        if ( *((_QWORD *)this + 7) )
          v13 = (const WCHAR *)*((_QWORD *)this + 7);
        v14 = &Value;
        if ( *((_QWORD *)this + 6) )
          v14 = (const WCHAR *)*((_QWORD *)this + 6);
        McTemplateU0dzz_EventWriteTransfer(v11, (unsigned int)DSMNoImpersonateError, v9, (_DWORD)v14, (__int64)v13);
      }
      v15 = &Value;
      if ( *((_QWORD *)this + 7) )
        v15 = (const WCHAR *)*((_QWORD *)this + 7);
      if ( *((_QWORD *)this + 6) )
        v12 = (const WCHAR *)*((_QWORD *)this + 6);
      details::appxLog<long,unsigned short *,unsigned short *>(
        v9,
        v10,
        (const struct _EVENT_DESCRIPTOR *)DSMNoImpersonateError,
        v9,
        v12,
        v15);
    }
    else
    {
LABEL_3:
      v2 = -1;
      if ( (unsigned int)(*((_DWORD *)this + 10) - 2) <= 1 )
      {
        v3 = *((_QWORD *)this + 7);
        if ( v3 )
        {
          v4 = -1;
          do
            ++v4;
          while ( *(_WORD *)(v3 + 2 * v4) );
          v5 = RtlPublishWnfStateData(WNF_DSM_DSMAPPREMOVED, 0, v3, (unsigned int)(2 * v4 + 2));
          v6 = v5 | 0x10000000;
          if ( v5 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x35,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\dsm\\dsmextensionhandler.cpp",
              (const char *)v6,
              0);
            if ( (byte_180245607 & 0x10) != 0 )
              McTemplateU0dz_EventWriteTransfer(
                &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
                DSMRemoveNotificationError,
                v6,
                *((_QWORD *)this + 7));
            details::appxLog<long,unsigned short const *>(
              v6,
              v21,
              (const struct _EVENT_DESCRIPTOR *)DSMRemoveNotificationError,
              v6,
              *((_QWORD *)this + 7));
          }
        }
      }
      if ( (unsigned int)(*((_DWORD *)this + 10) - 1) <= 1 )
      {
        v17 = *((_QWORD *)this + 6);
        if ( v17 )
        {
          do
            ++v2;
          while ( *(_WORD *)(v17 + 2 * v2) );
          v18 = RtlPublishWnfStateData(WNF_DSM_DSMAPPINSTALLED, 0, v17, (unsigned int)(2 * v2 + 2));
          v19 = v18 | 0x10000000;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x44,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\dsm\\dsmextensionhandler.cpp",
              (const char *)v19,
              0);
            if ( (byte_180245607 & 0x10) != 0 )
              McTemplateU0dz_EventWriteTransfer(
                &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
                DSMInstallNotificationError,
                v19,
                *((_QWORD *)this + 6));
            details::appxLog<long,unsigned short const *>(
              v19,
              v20,
              (const struct _EVENT_DESCRIPTOR *)DSMInstallNotificationError,
              v19,
              *((_QWORD *)this + 6));
          }
        }
      }
      *((_BYTE *)this + 64) = 0;
    }
    v7 = (char *)Token;
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
        GetLastError();
      if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(Token);
      v7 = 0;
      Token = 0;
    }
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v7);
  }
}

```

## disassembly

```asm
0x18002ee40  push    rbx
0x18002ee42  push    rbp
0x18002ee43  push    rsi
0x18002ee44  push    rdi
0x18002ee45  sub     rsp, 38h
0x18002ee49  mov     rdi, rcx
0x18002ee4c  xor     ebp, ebp
0x18002ee4e  cmp     [rcx+40h], bpl
0x18002ee52  jz      loc_18002EF18
0x18002ee58  mov     [rsp+58h+Token], rbp
0x18002ee5d  mov     eax, gs:179Ch
0x18002ee65  test    eax, eax
0x18002ee67  jnz     loc_18002EF3E
0x18002ee6d  mov     eax, [rdi+28h]
0x18002ee70  sub     eax, 2
0x18002ee73  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ee77  cmp     eax, 1
0x18002ee7a  ja      short loc_18002EEC2
0x18002ee7c  mov     r8, [rdi+38h]
0x18002ee80  test    r8, r8
0x18002ee83  jz      short loc_18002EEC2
0x18002ee85  mov     r9, rbx
0x18002ee88  inc     r9
0x18002ee8b  cmp     [r8+r9*2], bp
0x18002ee90  jnz     short loc_18002EE88
0x18002ee92  lea     r9d, ds:2[r9*2]
0x18002ee9a  mov     qword ptr [rsp+58h+var_38], rbp; int
0x18002ee9f  xor     edx, edx
0x18002eea1  mov     rcx, cs:WNF_DSM_DSMAPPREMOVED
0x18002eea8  call    cs:__imp_RtlPublishWnfStateData
0x18002eeaf  nop     dword ptr [rax+rax+00h]
0x18002eeb4  mov     esi, eax
0x18002eeb6  or      esi, 10000000h
0x18002eebc  jl      loc_18002F0E6
0x18002eec2  mov     eax, [rdi+28h]
0x18002eec5  dec     eax
0x18002eec7  cmp     eax, 1
0x18002eeca  jbe     loc_18002F044
0x18002eed0  mov     [rdi+40h], bpl
0x18002eed4  mov     rcx, [rsp+58h+Token]
0x18002eed9  test    rcx, rcx
0x18002eedc  jz      short loc_18002EF0E
0x18002eede  mov     rdx, rcx; Token
0x18002eee1  xor     ecx, ecx; Thread
0x18002eee3  call    cs:__imp_SetThreadToken
0x18002eeea  nop     dword ptr [rax+rax+00h]
0x18002eeef  test    eax, eax
0x18002eef1  jz      loc_18002F141
0x18002eef7  mov     rcx, [rsp+58h+Token]; hObject
0x18002eefc  lea     rax, [rcx-1]
0x18002ef00  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ef04  jbe     short loc_18002EF30
0x18002ef06  mov     rcx, rbp; hObject
0x18002ef09  mov     [rsp+58h+Token], rcx
0x18002ef0e  lea     rax, [rcx-1]
0x18002ef12  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ef16  jbe     short loc_18002EF22
0x18002ef18  add     rsp, 38h
0x18002ef1c  pop     rdi
0x18002ef1d  pop     rsi
0x18002ef1e  pop     rbp
0x18002ef1f  pop     rbx
0x18002ef20  retn
0x18002ef22  call    cs:__imp_CloseHandle
0x18002ef29  nop     dword ptr [rax+rax+00h]
0x18002ef2e  jmp     short loc_18002EF18
0x18002ef30  call    cs:__imp_CloseHandle
0x18002ef37  nop     dword ptr [rax+rax+00h]
0x18002ef3c  jmp     short loc_18002EF06
0x18002ef3e  mov     [rsp+58h+Token], rbp
0x18002ef43  call    cs:__imp_GetCurrentThread
0x18002ef4a  nop     dword ptr [rax+rax+00h]
0x18002ef4f  lea     r9, [rsp+58h+Token]; TokenHandle
0x18002ef54  mov     edx, 4; DesiredAccess
0x18002ef59  lea     r8d, [rdx-3]; OpenAsSelf
0x18002ef5d  mov     rcx, rax; ThreadHandle
0x18002ef60  call    cs:__imp_OpenThreadToken
0x18002ef67  nop     dword ptr [rax+rax+00h]
0x18002ef6c  test    eax, eax
0x18002ef6e  jz      loc_18002F020
0x18002ef74  xor     edx, edx; Token
0x18002ef76  xor     ecx, ecx; Thread
0x18002ef78  call    cs:__imp_SetThreadToken
0x18002ef7f  nop     dword ptr [rax+rax+00h]
0x18002ef84  test    eax, eax
0x18002ef86  jz      loc_18002F020
0x18002ef8c  mov     ebx, ebp
0x18002ef8e  test    ebx, ebx
0x18002ef90  jns     loc_18002EE6D
0x18002ef96  mov     rcx, [rsp+58h]; this
0x18002ef9b  mov     r9d, ebx; char *
0x18002ef9e  lea     r8, aOnecoreAdminAp_72; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002efa5  mov     edx, 52h ; 'R'; void *
0x18002efaa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002efaf  lea     rsi, Value
0x18002efb6  test    cs:byte_180245607, 10h
0x18002efbd  jz      short loc_18002EFEB
0x18002efbf  mov     rax, rsi
0x18002efc2  cmp     [rdi+38h], rbp
0x18002efc6  cmovnz  rax, [rdi+38h]
0x18002efcb  mov     r9, rsi
0x18002efce  cmp     [rdi+30h], rbp
0x18002efd2  cmovnz  r9, [rdi+30h]
0x18002efd7  mov     qword ptr [rsp+58h+var_38], rax
0x18002efdc  mov     r8d, ebx
0x18002efdf  lea     rdx, DSMNoImpersonateError
0x18002efe6  call    McTemplateU0dzz_EventWriteTransfer
0x18002efeb  mov     rax, rsi
0x18002efee  cmp     [rdi+38h], rbp
0x18002eff2  cmovnz  rax, [rdi+38h]
0x18002eff7  cmp     [rdi+30h], rbp
0x18002effb  cmovnz  rsi, [rdi+30h]
0x18002f000  mov     [rsp+58h+var_30], rax
0x18002f005  mov     qword ptr [rsp+58h+var_38], rsi
0x18002f00a  mov     r9d, ebx
0x18002f00d  lea     r8, DSMNoImpersonateError
0x18002f014  mov     ecx, ebx
0x18002f016  call    ??$appxLog@JPEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEAG2@Z; details::appxLog<long,ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort *,ushort *)
0x18002f01b  jmp     loc_18002EED4
0x18002f020  call    cs:__imp_GetLastError
0x18002f027  nop     dword ptr [rax+rax+00h]
0x18002f02c  test    eax, eax
0x18002f02e  mov     ebx, eax
0x18002f030  jle     loc_18002EF8E
0x18002f036  movzx   ebx, ax
0x18002f039  or      ebx, 80070000h
0x18002f03f  jmp     loc_18002EF8E
0x18002f044  mov     r8, [rdi+30h]
0x18002f048  test    r8, r8
0x18002f04b  jz      loc_18002EED0
0x18002f051  inc     rbx
0x18002f054  cmp     [r8+rbx*2], bp
0x18002f059  jnz     short loc_18002F051
0x18002f05b  lea     r9d, ds:2[rbx*2]
0x18002f063  mov     qword ptr [rsp+58h+var_38], rbp; int
0x18002f068  xor     edx, edx
0x18002f06a  mov     rcx, cs:WNF_DSM_DSMAPPINSTALLED
0x18002f071  call    cs:__imp_RtlPublishWnfStateData
0x18002f078  nop     dword ptr [rax+rax+00h]
0x18002f07d  mov     ebx, eax
0x18002f07f  or      ebx, 10000000h
0x18002f085  jge     loc_18002EED0
0x18002f08b  mov     rcx, [rsp+58h]; this
0x18002f090  mov     r9d, ebx; char *
0x18002f093  lea     r8, aOnecoreAdminAp_72; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002f09a  mov     edx, 44h ; 'D'; void *
0x18002f09f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f0a4  test    cs:byte_180245607, 10h
0x18002f0ab  jz      short loc_18002F0C7
0x18002f0ad  mov     r9, [rdi+30h]
0x18002f0b1  mov     r8d, ebx
0x18002f0b4  lea     rdx, DSMInstallNotificationError
0x18002f0bb  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002f0c2  call    McTemplateU0dz_EventWriteTransfer
0x18002f0c7  mov     rax, [rdi+30h]
0x18002f0cb  mov     qword ptr [rsp+58h+var_38], rax
0x18002f0d0  mov     r9d, ebx
0x18002f0d3  lea     r8, DSMInstallNotificationError
0x18002f0da  mov     ecx, ebx
0x18002f0dc  call    ??$appxLog@JPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG@Z; details::appxLog<long,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *)
0x18002f0e1  jmp     loc_18002EED0
0x18002f0e6  mov     rcx, [rsp+58h]; this
0x18002f0eb  mov     r9d, esi; char *
0x18002f0ee  lea     r8, aOnecoreAdminAp_72; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002f0f5  mov     edx, 35h ; '5'; void *
0x18002f0fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f0ff  test    cs:byte_180245607, 10h
0x18002f106  jz      short loc_18002F122
0x18002f108  mov     r9, [rdi+38h]
0x18002f10c  mov     r8d, esi
0x18002f10f  lea     rdx, DSMRemoveNotificationError
0x18002f116  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18002f11d  call    McTemplateU0dz_EventWriteTransfer
0x18002f122  mov     rax, [rdi+38h]
0x18002f126  mov     qword ptr [rsp+58h+var_38], rax
0x18002f12b  mov     r9d, esi
0x18002f12e  lea     r8, DSMRemoveNotificationError
0x18002f135  mov     ecx, esi
0x18002f137  call    ??$appxLog@JPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG@Z; details::appxLog<long,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *)
0x18002f13c  jmp     loc_18002EEC2
0x18002f141  call    cs:__imp_GetLastError
0x18002f148  nop     dword ptr [rax+rax+00h]
0x18002f14d  jmp     loc_18002EEF7
```

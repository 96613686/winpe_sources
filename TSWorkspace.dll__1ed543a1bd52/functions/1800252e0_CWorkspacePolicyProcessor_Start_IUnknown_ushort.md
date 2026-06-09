# CWorkspacePolicyProcessor::Start(IUnknown *,ushort *)

- ea: `0x1800252e0`
- end: `0x180025689`
- name: `?Start@CWorkspacePolicyProcessor@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `937`
- prototype: `__int64 __fastcall(CWorkspacePolicyProcessor *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800034b8`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180024644`
- `0x1800252e0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002551a`
- `ole32!CoCreateInstance` at `0x18002551a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025648`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800255e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800255e7`

## string_xrefs

- `0x1800254eb`: `QueryInterface for IID_ITaskHandlerStatus failed`
- `0x180025554`: `CoCreateInstance failed for CLSID_StdGlobalInterfaceTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkspacePolicyProcessor::Start(LPVOID *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  PVOID *v5; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int Instance; // ebx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // eax
  _QWORD *v12; // rax
  unsigned int v13; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  signed int v18; // eax
  __int64 v20; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v21; // [rsp+78h] [rbp+20h]

  v20 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_7a3859da1660308f99057c19da6b6dba_Traceguids,
      CurrentThreadActivityIdPrefix);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 25) )
  {
    Instance = CWorkspacePolicyProcessor::CleanUp((CWorkspacePolicyProcessor *)this);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 11;
        v10 = "CWorkspacePolicyProcessor::CleanUp failed";
LABEL_11:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)WPP_7a3859da1660308f99057c19da6b6dba_Traceguids,
          v8,
          (__int64)v10,
          Instance,
          -2);
        goto LABEL_53;
      }
      goto LABEL_53;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[2] )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_7a3859da1660308f99057c19da6b6dba_Traceguids,
        v11,
        -2147023840);
    }
    Instance = -2147023840;
  }
  else
  {
    v12 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v12;
    if ( v12 )
    {
      *v12 = &CWorkspaceSilentSetupManager::`vftable';
      v12[1] = 0;
      v12[2] = 3600000;
    }
    this[6] = v12;
    if ( v12 )
    {
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                   a2,
                   &IID_ITaskHandlerStatus,
                   &v20);
      if ( Instance >= 0 )
      {
        if ( this[4]
          || (Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, this + 4),
              Instance >= 0) )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, char *))(*(_QWORD *)this[4] + 24LL))(
                       this[4],
                       v20,
                       &IID_ITaskHandlerStatus,
                       (char *)this + 40);
          if ( Instance >= 0 )
          {
            v20 = 0;
            Thread = CreateThread(0, 0, CWorkspacePolicyProcessor::ProcessPolicyThreadProc, this, 0, 0);
            this[2] = Thread;
            if ( Thread )
            {
              Instance = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LastError = GetLastError();
                v16 = LastError;
                if ( LastError > 0 )
                  v16 = (unsigned __int16)LastError | 0x80070000;
                v17 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  WPP_7a3859da1660308f99057c19da6b6dba_Traceguids,
                  v17,
                  v16);
              }
              v18 = GetLastError();
              Instance = v18;
              if ( v18 > 0 )
                Instance = (unsigned __int16)v18 | 0x80070000;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = RdpWppGetCurrentThreadActivityIdPrefix();
            v9 = 16;
            v10 = "RegisterInterfaceInGlobal failed";
            goto LABEL_11;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 15;
          v10 = "CoCreateInstance failed for CLSID_StdGlobalInterfaceTable";
          goto LABEL_11;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 14;
        v10 = "QueryInterface for IID_ITaskHandlerStatus failed";
        goto LABEL_11;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_7a3859da1660308f99057c19da6b6dba_Traceguids,
          v13,
          -2147024882);
      }
      Instance = -2147024882;
    }
  }
LABEL_53:
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800252e0  mov     rax, rsp
0x1800252e3  push    rdi
0x1800252e4  push    r14
0x1800252e6  push    r15
0x1800252e8  sub     rsp, 40h
0x1800252ec  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800252f4  mov     [rax+10h], rbx
0x1800252f8  mov     [rax+18h], rsi
0x1800252fc  mov     rsi, rdx
0x1800252ff  mov     rdi, rcx
0x180025302  mov     qword ptr [rax+8], 0
0x18002530a  lea     r14, WPP_GLOBAL_Control
0x180025311  lea     r15, WPP_7a3859da1660308f99057c19da6b6dba_Traceguids
0x180025318  mov     rax, cs:WPP_GLOBAL_Control
0x18002531f  cmp     rax, r14
0x180025322  jz      short loc_180025357
0x180025324  test    byte ptr [rax+1Ch], 1
0x180025328  jz      short loc_180025357
0x18002532a  cmp     byte ptr [rax+19h], 4
0x18002532e  jb      short loc_180025357
0x180025330  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180025335  mov     edx, 0Ah
0x18002533a  mov     r9d, eax
0x18002533d  mov     r8, r15
0x180025340  mov     rcx, cs:WPP_GLOBAL_Control
0x180025347  mov     rcx, [rcx+10h]
0x18002534b  call    WPP_SF_D
0x180025350  mov     rax, cs:WPP_GLOBAL_Control
0x180025357  cmp     byte ptr [rdi+19h], 0
0x18002535b  jz      short loc_1800253CB
0x18002535d  mov     rcx, rdi; this
0x180025360  call    ?CleanUp@CWorkspacePolicyProcessor@@IEAAJXZ; CWorkspacePolicyProcessor::CleanUp(void)
0x180025365  mov     ebx, eax
0x180025367  test    eax, eax
0x180025369  jns     short loc_1800253C4
0x18002536b  mov     rax, cs:WPP_GLOBAL_Control
0x180025372  cmp     rax, r14
0x180025375  jz      loc_18002565D
0x18002537b  test    byte ptr [rax+1Ch], 8
0x18002537f  jz      loc_18002565D
0x180025385  cmp     byte ptr [rax+19h], 2
0x180025389  jb      loc_18002565D
0x18002538f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180025394  mov     edx, 0Bh
0x180025399  lea     rcx, aCworkspacepoli; "CWorkspacePolicyProcessor::CleanUp fail"...
0x1800253a0  mov     dword ptr [rsp+58h+lpThreadId], ebx
0x1800253a4  mov     [rsp+58h+ppv], rcx
0x1800253a9  mov     r9d, eax
0x1800253ac  mov     r8, r15
0x1800253af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253b6  mov     rcx, [rcx+10h]
0x1800253ba  call    WPP_SF_DsD
0x1800253bf  jmp     loc_18002565D
0x1800253c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800253cb  cmp     qword ptr [rdi+10h], 0
0x1800253d0  jz      short loc_180025415
0x1800253d2  cmp     rax, r14
0x1800253d5  jz      short loc_18002540B
0x1800253d7  test    byte ptr [rax+1Ch], 8
0x1800253db  jz      short loc_18002540B
0x1800253dd  cmp     byte ptr [rax+19h], 2
0x1800253e1  jb      short loc_18002540B
0x1800253e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800253e8  mov     edx, 0Ch
0x1800253ed  mov     dword ptr [rsp+58h+ppv], 80070420h
0x1800253f5  mov     r9d, eax
0x1800253f8  mov     r8, r15
0x1800253fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025402  mov     rcx, [rcx+10h]
0x180025406  call    WPP_SF_Dd
0x18002540b  mov     ebx, 80070420h
0x180025410  jmp     loc_18002565D
0x180025415  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002541c  mov     ecx, 18h; unsigned __int64
0x180025421  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025426  mov     [rsp+58h+arg_18], rax
0x18002542b  test    rax, rax
0x18002542e  jz      short loc_18002544A
0x180025430  lea     rcx, ??_7CWorkspaceSilentSetupManager@@6B@; const CWorkspaceSilentSetupManager::`vftable'
0x180025437  mov     [rax], rcx
0x18002543a  mov     qword ptr [rax+8], 0
0x180025442  mov     qword ptr [rax+10h], 36EE80h
0x18002544a  mov     [rdi+30h], rax
0x18002544e  test    rax, rax
0x180025451  jnz     short loc_18002549D
0x180025453  mov     rax, cs:WPP_GLOBAL_Control
0x18002545a  cmp     rax, r14
0x18002545d  jz      short loc_180025493
0x18002545f  test    byte ptr [rax+1Ch], 8
0x180025463  jz      short loc_180025493
0x180025465  cmp     byte ptr [rax+19h], 2
0x180025469  jb      short loc_180025493
0x18002546b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180025470  mov     edx, 0Dh
0x180025475  mov     dword ptr [rsp+58h+ppv], 8007000Eh
0x18002547d  mov     r9d, eax
0x180025480  mov     r8, r15
0x180025483  mov     rcx, cs:WPP_GLOBAL_Control
0x18002548a  mov     rcx, [rcx+10h]
0x18002548e  call    WPP_SF_Dd
0x180025493  mov     ebx, 8007000Eh
0x180025498  jmp     loc_18002565D
0x18002549d  mov     rax, [rsi]
0x1800254a0  lea     r8, [rsp+58h+arg_0]
0x1800254a5  lea     rdx, IID_ITaskHandlerStatus
0x1800254ac  mov     rcx, rsi
0x1800254af  mov     rax, [rax]
0x1800254b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254b7  mov     ebx, eax
0x1800254b9  test    eax, eax
0x1800254bb  jns     short loc_1800254F7
0x1800254bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800254c4  cmp     rax, r14
0x1800254c7  jz      loc_18002565D
0x1800254cd  test    byte ptr [rax+1Ch], 8
0x1800254d1  jz      loc_18002565D
0x1800254d7  cmp     byte ptr [rax+19h], 2
0x1800254db  jb      loc_18002565D
0x1800254e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800254e6  mov     edx, 0Eh
0x1800254eb  lea     rcx, aQueryinterface_1; "QueryInterface for IID_ITaskHandlerStat"...
0x1800254f2  jmp     loc_1800253A0
0x1800254f7  lea     rsi, [rdi+20h]
0x1800254fb  cmp     qword ptr [rsi], 0
0x1800254ff  jnz     short loc_180025560
0x180025501  mov     [rsp+58h+ppv], rsi; ppv
0x180025506  lea     r9, IID_IGlobalInterfaceTable; riid
0x18002550d  xor     edx, edx; pUnkOuter
0x18002550f  lea     r8d, [rdx+1]; dwClsContext
0x180025513  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18002551a  call    cs:__imp_CoCreateInstance
0x180025520  mov     ebx, eax
0x180025522  test    eax, eax
0x180025524  jns     short loc_180025560
0x180025526  mov     rax, cs:WPP_GLOBAL_Control
0x18002552d  cmp     rax, r14
0x180025530  jz      loc_18002565D
0x180025536  test    byte ptr [rax+1Ch], 8
0x18002553a  jz      loc_18002565D
0x180025540  cmp     byte ptr [rax+19h], 2
0x180025544  jb      loc_18002565D
0x18002554a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002554f  mov     edx, 0Fh
0x180025554  lea     rcx, aCocreateinstan_6; "CoCreateInstance failed for CLSID_StdGl"...
0x18002555b  jmp     loc_1800253A0
0x180025560  mov     rcx, [rsi]
0x180025563  mov     rax, [rcx]
0x180025566  lea     r9, [rdi+28h]
0x18002556a  lea     r8, IID_ITaskHandlerStatus
0x180025571  mov     rdx, [rsp+58h+arg_0]
0x180025576  mov     rax, [rax+18h]
0x18002557a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002557f  mov     ebx, eax
0x180025581  test    eax, eax
0x180025583  jns     short loc_1800255BF
0x180025585  mov     rax, cs:WPP_GLOBAL_Control
0x18002558c  cmp     rax, r14
0x18002558f  jz      loc_18002565D
0x180025595  test    byte ptr [rax+1Ch], 8
0x180025599  jz      loc_18002565D
0x18002559f  cmp     byte ptr [rax+19h], 2
0x1800255a3  jb      loc_18002565D
0x1800255a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800255ae  mov     edx, 10h
0x1800255b3  lea     rcx, aRegisterinterf; "RegisterInterfaceInGlobal failed"
0x1800255ba  jmp     loc_1800253A0
0x1800255bf  mov     [rsp+58h+arg_0], 0
0x1800255c8  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800255d1  mov     dword ptr [rsp+58h+ppv], 0; dwCreationFlags
0x1800255d9  mov     r9, rdi; lpParameter
0x1800255dc  lea     r8, ?ProcessPolicyThreadProc@CWorkspacePolicyProcessor@@KAKPEAX@Z; lpStartAddress
0x1800255e3  xor     edx, edx; dwStackSize
0x1800255e5  xor     ecx, ecx; lpThreadAttributes
0x1800255e7  call    cs:__imp_CreateThread
0x1800255ed  mov     [rdi+10h], rax
0x1800255f1  test    rax, rax
0x1800255f4  jnz     short loc_18002565B
0x1800255f6  mov     edi, 80070000h
0x1800255fb  mov     rax, cs:WPP_GLOBAL_Control
0x180025602  cmp     rax, r14
0x180025605  jz      short loc_180025648
0x180025607  test    byte ptr [rax+1Ch], 8
0x18002560b  jz      short loc_180025648
0x18002560d  cmp     byte ptr [rax+19h], 2
0x180025611  jb      short loc_180025648
0x180025613  call    cs:__imp_GetLastError
0x180025619  mov     ebx, eax
0x18002561b  test    eax, eax
0x18002561d  jle     short loc_180025624
0x18002561f  movzx   ebx, ax
0x180025622  or      ebx, edi
0x180025624  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180025629  mov     edx, 11h
0x18002562e  mov     dword ptr [rsp+58h+ppv], ebx
0x180025632  mov     r9d, eax
0x180025635  mov     r8, r15
0x180025638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002563f  mov     rcx, [rcx+10h]
0x180025643  call    WPP_SF_Dd
0x180025648  call    cs:__imp_GetLastError
0x18002564e  mov     ebx, eax
0x180025650  test    eax, eax
0x180025652  jle     short loc_18002565D
0x180025654  movzx   ebx, ax
0x180025657  or      ebx, edi
0x180025659  jmp     short loc_18002565D
0x18002565b  xor     ebx, ebx
0x18002565d  mov     rcx, [rsp+58h+arg_0]
0x180025662  test    rcx, rcx
0x180025665  jz      short loc_180025673
0x180025667  mov     rax, [rcx]
0x18002566a  mov     rax, [rax+10h]
0x18002566e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025673  mov     eax, ebx
0x180025675  mov     rbx, [rsp+58h+arg_8]
0x18002567a  mov     rsi, [rsp+58h+arg_10]
0x18002567f  add     rsp, 40h
0x180025683  pop     r15
0x180025685  pop     r14
0x180025687  pop     rdi
0x180025688  retn
```

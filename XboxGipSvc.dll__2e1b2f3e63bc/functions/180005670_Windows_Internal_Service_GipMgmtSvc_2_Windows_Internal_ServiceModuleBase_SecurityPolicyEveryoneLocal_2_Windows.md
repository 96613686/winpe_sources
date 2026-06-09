# Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(ulong,ulong,void *,void *)

- ea: `0x180005670`
- end: `0x18000578e`
- name: `?HandlerExStatic@?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z`
- size: `286`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002b70`
- `0x180005670`
- `0x1800069a4`
- `0x18000a450`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800056db`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800056db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000576d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000576d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005763`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005763`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  unsigned int v5; // ebx
  unsigned int started; // esi
  SERVICE_STATUS_HANDLE v7; // rcx

  v5 = 120;
  if ( dwControl != 32 )
  {
    if ( dwControl == 1 )
    {
      if ( ((*((_DWORD *)lpContext + 5) - 1) & 0xFFFFFFFD) != 0 )
      {
        v7 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 1);
        *((_DWORD *)lpContext + 5) = 3;
        SetServiceStatus(v7, (LPSERVICE_STATUS)(lpContext + 16));
      }
      SetEvent(*((HANDLE *)lpContext + 6));
    }
    else if ( dwControl != 4 )
    {
      return v5;
    }
    return 0;
  }
  if ( *((_DWORD *)lpContext + 5) == 3 )
  {
    return 1115;
  }
  else
  {
    v5 = 0;
    started = GipMgmtSvc::_StartCoexistence((SERVICE_STATUS_HANDLE *)lpContext);
    if ( (lpContext[224] & 1) == 0 )
    {
      CxsStopClient((struct _GIP_WLAN_CLIENT *)(lpContext + 56));
      if ( lpContext[232] )
      {
        InitOnceExecuteOnce(
          &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
          _lambda_253709c146e3c4eefdc38a0c994771db_::_lambda_invoker_cdecl_,
          0,
          0);
        byte_18001A570 = 1;
        (*(void (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                          + 24))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
        lpContext[232] = 0;
      }
    }
    if ( started
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids, started);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180005670  mov     [rsp+arg_0], rbx
0x180005675  mov     [rsp+arg_8], rsi
0x18000567a  push    rdi
0x18000567b  sub     rsp, 20h
0x18000567f  mov     rdi, r9
0x180005682  mov     ebx, 78h ; 'x'
0x180005687  cmp     ecx, 20h ; ' '
0x18000568a  jnz     loc_180005742
0x180005690  cmp     dword ptr [r9+14h], 3
0x180005695  jnz     short loc_1800056A1
0x180005697  mov     ebx, 45Bh
0x18000569c  jmp     loc_18000577C
0x1800056a1  mov     rcx, rdi; this
0x1800056a4  call    ?_StartCoexistence@GipMgmtSvc@@QEAAKXZ; GipMgmtSvc::_StartCoexistence(void)
0x1800056a9  xor     ebx, ebx
0x1800056ab  mov     esi, eax
0x1800056ad  test    byte ptr [rdi+0E0h], 1
0x1800056b4  jnz     short loc_180005705
0x1800056b6  lea     rcx, [rdi+38h]; struct _GIP_WLAN_CLIENT *
0x1800056ba  call    ?CxsStopClient@@YAXPEAU_GIP_WLAN_CLIENT@@@Z; CxsStopClient(_GIP_WLAN_CLIENT *)
0x1800056bf  cmp     [rdi+0E8h], bl
0x1800056c5  jz      short loc_180005705
0x1800056c7  xor     r9d, r9d; Context
0x1800056ca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_253709c146e3c4eefdc38a0c994771db_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800056d1  xor     r8d, r8d; Parameter
0x1800056d4  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800056db  call    cs:__imp_InitOnceExecuteOnce
0x1800056e1  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x1800056e8  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x1800056ef  mov     cs:byte_18001A570, 1
0x1800056f6  mov     rax, [rax+18h]
0x1800056fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ff  mov     [rdi+0E8h], bl
0x180005705  test    esi, esi
0x180005707  jz      short loc_18000577C
0x180005709  mov     rcx, cs:WPP_GLOBAL_Control
0x180005710  lea     rax, WPP_GLOBAL_Control
0x180005717  cmp     rcx, rax
0x18000571a  jz      short loc_18000577C
0x18000571c  test    byte ptr [rcx+1Ch], 1
0x180005720  jz      short loc_18000577C
0x180005722  cmp     byte ptr [rcx+19h], 2
0x180005726  jb      short loc_18000577C
0x180005728  mov     rcx, [rcx+10h]
0x18000572c  lea     r8, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids
0x180005733  mov     edx, 0Dh
0x180005738  mov     r9d, esi
0x18000573b  call    WPP_SF_D
0x180005740  jmp     short loc_18000577C
0x180005742  cmp     ecx, 1
0x180005745  jnz     short loc_180005775
0x180005747  lea     rdx, [r9+10h]; lpServiceStatus
0x18000574b  mov     eax, [rdx+4]
0x18000574e  dec     eax
0x180005750  test    eax, 0FFFFFFFDh
0x180005755  jz      short loc_180005769
0x180005757  mov     rcx, [r9+8]; hServiceStatus
0x18000575b  mov     dword ptr [r9+14h], 3
0x180005763  call    cs:__imp_SetServiceStatus
0x180005769  mov     rcx, [rdi+30h]; hEvent
0x18000576d  call    cs:__imp_SetEvent
0x180005773  jmp     short loc_18000577A
0x180005775  cmp     ecx, 4
0x180005778  jnz     short loc_18000577C
0x18000577a  xor     ebx, ebx
0x18000577c  mov     rsi, [rsp+28h+arg_8]
0x180005781  mov     eax, ebx
0x180005783  mov     rbx, [rsp+28h+arg_0]
0x180005788  add     rsp, 20h
0x18000578c  pop     rdi
0x18000578d  retn
```

# Apx::ApfWorkItemQueue::Initialize(void)

- ea: `0x18000caac`
- end: `0x18000cc66`
- name: `?Initialize@ApfWorkItemQueue@Apx@@QEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fb6c`
- `0x180011408`
- `0x180028390`

## callees

- `0x18000a12c`
- `0x18000caac`
- `0x18000d044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000cb75`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000cb75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbcb`

## pseudocode

```c
__int64 __fastcall Apx::ApfWorkItemQueue::Initialize(void **this)
{
  _QWORD *v2; // rcx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  char *Thread; // rbp
  void **v5; // r14
  void *v6; // r15
  DWORD LastError; // ebx
  signed int v8; // eax
  char v10; // [rsp+30h] [rbp-48h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    {
      WPP_SF_(v2[2], 18, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
  if ( !*((_BYTE *)this + 112) )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 11);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 12);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
      {
        Thread = (char *)CreateThread(0, 0, Apx::ApfWorkItemQueue::s_WorkItemThreadProc, this, 0, 0);
        v5 = this + 13;
        if ( this + 13 == (void **)&v10 )
        {
          if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(Thread);
        }
        else
        {
          v6 = *v5;
          if ( (char *)*v5 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            LastError = GetLastError();
            CloseHandle(v6);
            SetLastError(LastError);
          }
          *v5 = Thread;
        }
        if ( !*v5 )
        {
          v8 = GetLastError();
          event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v8;
          if ( v8 > 0 )
            event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (unsigned __int16)v8 | 0x80070000;
        }
      }
    }
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
  {
    WPP_SF_(v2[2], 19, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    *((_BYTE *)this + 112) = 1;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 15, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
  return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
}

```

## disassembly

```asm
0x18000caac  push    rbx
0x18000caae  push    rbp
0x18000caaf  push    rsi
0x18000cab0  push    rdi
0x18000cab1  push    r14
0x18000cab3  push    r15
0x18000cab5  sub     rsp, 48h
0x18000cab9  mov     rsi, rcx
0x18000cabc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cac3  lea     rbx, WPP_GLOBAL_Control
0x18000caca  cmp     rcx, rbx
0x18000cacd  jz      short loc_18000CB24
0x18000cacf  test    byte ptr [rcx+1Ch], 1
0x18000cad3  jz      short loc_18000CAF7
0x18000cad5  cmp     byte ptr [rcx+19h], 5
0x18000cad9  jb      short loc_18000CAF7
0x18000cadb  mov     rcx, [rcx+10h]
0x18000cadf  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000cae6  mov     edx, 0Eh
0x18000caeb  call    WPP_SF_
0x18000caf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caf7  cmp     rcx, rbx
0x18000cafa  jz      short loc_18000CB24
0x18000cafc  test    byte ptr [rcx+1Ch], 1
0x18000cb00  jz      short loc_18000CB24
0x18000cb02  cmp     byte ptr [rcx+19h], 5
0x18000cb06  jb      short loc_18000CB24
0x18000cb08  mov     rcx, [rcx+10h]
0x18000cb0c  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000cb13  mov     edx, 12h
0x18000cb18  call    WPP_SF_
0x18000cb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb24  xor     edi, edi
0x18000cb26  cmp     [rsi+70h], dil
0x18000cb2a  jnz     loc_18000CBF3
0x18000cb30  lea     rcx, [rsi+58h]
0x18000cb34  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cb39  mov     edi, eax
0x18000cb3b  test    eax, eax
0x18000cb3d  js      loc_18000CBEC
0x18000cb43  lea     rcx, [rsi+60h]
0x18000cb47  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000cb4c  mov     edi, eax
0x18000cb4e  test    eax, eax
0x18000cb50  js      loc_18000CBEC
0x18000cb56  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18000cb5f  lea     r8, ?s_WorkItemThreadProc@ApfWorkItemQueue@Apx@@CAKPEAX@Z; lpStartAddress
0x18000cb66  mov     r9, rsi; lpParameter
0x18000cb69  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18000cb71  xor     edx, edx; dwStackSize
0x18000cb73  xor     ecx, ecx; lpThreadAttributes
0x18000cb75  call    cs:__imp_CreateThread
0x18000cb7b  mov     rbp, rax
0x18000cb7e  lea     r14, [rsi+68h]
0x18000cb82  lea     rax, [rsp+78h+var_48]
0x18000cb87  cmp     r14, rax
0x18000cb8a  jz      short loc_18000CBBE
0x18000cb8c  mov     r15, [r14]
0x18000cb8f  lea     rdx, [r15-1]
0x18000cb93  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000cb97  ja      short loc_18000CBB9
0x18000cb99  call    cs:__imp_GetLastError
0x18000cb9f  mov     rcx, r15; hObject
0x18000cba2  mov     ebx, eax
0x18000cba4  call    cs:__imp_CloseHandle
0x18000cbaa  mov     ecx, ebx; dwErrCode
0x18000cbac  call    cs:__imp_SetLastError
0x18000cbb2  lea     rbx, WPP_GLOBAL_Control
0x18000cbb9  mov     [r14], rbp
0x18000cbbc  jmp     short loc_18000CBD1
0x18000cbbe  lea     rax, [rbp-1]
0x18000cbc2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cbc6  ja      short loc_18000CBD1
0x18000cbc8  mov     rcx, rbp; hObject
0x18000cbcb  call    cs:__imp_CloseHandle
0x18000cbd1  cmp     qword ptr [r14], 0
0x18000cbd5  jnz     short loc_18000CBEC
0x18000cbd7  call    cs:__imp_GetLastError
0x18000cbdd  mov     edi, eax
0x18000cbdf  test    eax, eax
0x18000cbe1  jle     short loc_18000CBEC
0x18000cbe3  movzx   edi, ax
0x18000cbe6  or      edi, 80070000h
0x18000cbec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbf3  cmp     rcx, rbx
0x18000cbf6  jz      short loc_18000CC20
0x18000cbf8  test    byte ptr [rcx+1Ch], 1
0x18000cbfc  jz      short loc_18000CC20
0x18000cbfe  cmp     byte ptr [rcx+19h], 5
0x18000cc02  jb      short loc_18000CC20
0x18000cc04  mov     rcx, [rcx+10h]
0x18000cc08  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000cc0f  mov     edx, 13h
0x18000cc14  call    WPP_SF_
0x18000cc19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc20  test    edi, edi
0x18000cc22  js      short loc_18000CC31
0x18000cc24  mov     byte ptr [rsi+70h], 1
0x18000cc28  xor     edi, edi
0x18000cc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc31  cmp     rcx, rbx
0x18000cc34  jz      short loc_18000CC57
0x18000cc36  test    byte ptr [rcx+1Ch], 1
0x18000cc3a  jz      short loc_18000CC57
0x18000cc3c  cmp     byte ptr [rcx+19h], 5
0x18000cc40  jb      short loc_18000CC57
0x18000cc42  mov     rcx, [rcx+10h]
0x18000cc46  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000cc4d  mov     edx, 0Fh
0x18000cc52  call    WPP_SF_
0x18000cc57  mov     eax, edi
0x18000cc59  add     rsp, 48h
0x18000cc5d  pop     r15
0x18000cc5f  pop     r14
0x18000cc61  pop     rdi
0x18000cc62  pop     rsi
0x18000cc63  pop     rbp
0x18000cc64  pop     rbx
0x18000cc65  retn
```

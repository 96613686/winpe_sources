# LogonSoundHelpers::LogonSoundPlayer::_SoundInitializationWorkItemProc(void *)

- ea: `0x180045230`
- end: `0x1800453a6`
- name: `?_SoundInitializationWorkItemProc@LogonSoundPlayer@LogonSoundHelpers@@CAKPEAX@Z`
- size: `374`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180045230`
- `0x1800453ac`
- `0x18005f1f8`
- `0x180062444`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x18004536c`
- `KERNEL32!WaitForMultipleObjects` at `0x18004536c`
- `KERNEL32!QueueUserWorkItem` at `0x180045300`
- `KERNEL32!QueueUserWorkItem` at `0x180045300`
- `KERNEL32!LocalFree` at `0x180045395`
- `KERNEL32!LocalFree` at `0x180045395`
- `KERNEL32!CreateEventExW` at `0x18004529a`
- `KERNEL32!CreateEventExW` at `0x180045326`
- `KERNEL32!CreateEventExW` at `0x18004529a`
- `KERNEL32!CreateEventExW` at `0x180045326`
- `KERNEL32!OpenEventW` at `0x1800452b6`
- `KERNEL32!OpenEventW` at `0x180045342`
- `KERNEL32!OpenEventW` at `0x1800452b6`
- `KERNEL32!OpenEventW` at `0x180045342`
- `KERNEL32!WaitForSingleObject` at `0x1800452d0`
- `KERNEL32!WaitForSingleObject` at `0x1800452d0`
- `KERNEL32!CloseHandle` at `0x180045375`
- `KERNEL32!CloseHandle` at `0x180045386`
- `KERNEL32!CloseHandle` at `0x180045375`
- `KERNEL32!CloseHandle` at `0x180045386`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180045278`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180045278`

## string_xrefs

- `0x180045318`: `Global\AudioEndPoint_PlaybackReady`
- `0x180045334`: `Global\AudioEndPoint_PlaybackReady`

## pseudocode

```c
__int64 __fastcall LogonSoundHelpers::LogonSoundPlayer::_SoundInitializationWorkItemProc(wil::details **Parameter)
{
  HANDLE v2; // rdi
  void *v3; // rdx
  HANDLE v4; // rsi
  void *v5; // rdx
  wil::details *v6; // rax
  HANDLE Handles[2]; // [rsp+30h] [rbp-38h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+40h] [rbp-28h] BYREF

  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  if ( LogonSoundHelpers::IsSoundOn() )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;0x00100003;;;S-1-5-80-2676549577-1911656217-2625096541-4178041876-1366760775)(A;;0x00100000;;;SY)",
           1u,
           &EventAttributes.lpSecurityDescriptor,
           0) )
    {
      v2 = CreateEventExW(&EventAttributes, L"Global\\AudioSrv_CanAcceptMMCClient", 1u, 0x100000u);
      if ( v2 || (v2 = OpenEventW(0x100000u, 0, L"Global\\AudioSrv_CanAcceptMMCClient")) != 0 )
      {
        if ( !WaitForSingleObject(v2, 0x2710u)
          && (int)_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                    Parameter,
                    1) >= 0 )
        {
          if ( !QueueUserWorkItem(
                  LogonSoundHelpers::LogonSoundPlayer::_PlaySoundWorkItemFromLogonUIProc,
                  Parameter,
                  0x10u) )
            wil::details::SetEvent(*Parameter, v3);
          v4 = CreateEventExW(&EventAttributes, L"Global\\AudioEndPoint_PlaybackReady", 1u, 0x100000u);
          if ( v4 || (v4 = OpenEventW(0x100000u, 0, L"Global\\AudioEndPoint_PlaybackReady")) != 0 )
          {
            v6 = *Parameter;
            Handles[0] = v4;
            Handles[1] = v6;
            WaitForMultipleObjects(2u, Handles, 0, 0x2710u);
            CloseHandle(v4);
          }
          wil::details::SetEvent(*Parameter, v5);
        }
        CloseHandle(v2);
      }
    }
  }
  if ( EventAttributes.lpSecurityDescriptor )
    LocalFree(EventAttributes.lpSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x180045230  push    rbp
0x180045232  push    rbx
0x180045233  push    rsi
0x180045234  push    rdi
0x180045235  mov     rbp, rsp
0x180045238  sub     rsp, 68h
0x18004523c  mov     rbx, rcx
0x18004523f  mov     qword ptr [rbp+EventAttributes.nLength], 18h
0x180045247  mov     [rbp+EventAttributes.lpSecurityDescriptor], 0
0x18004524f  mov     qword ptr [rbp+EventAttributes.bInheritHandle], 0
0x180045257  call    LogonSoundHelpers__IsSoundOn
0x18004525c  test    al, al
0x18004525e  jz      loc_18004538C
0x180045264  xor     r9d, r9d; SecurityDescriptorSize
0x180045267  lea     r8, [rbp+EventAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x18004526b  lea     rcx, aDA0x00100003S1; "D:(A;;0x00100003;;;S-1-5-80-2676549577-"...
0x180045272  lea     esi, [r9+1]
0x180045276  mov     edx, esi; StringSDRevision
0x180045278  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004527e  test    eax, eax
0x180045280  jz      loc_18004538C
0x180045286  mov     r9d, 100000h; dwDesiredAccess
0x18004528c  lea     rdx, aGlobalAudiosrv; "Global\\AudioSrv_CanAcceptMMCClient"
0x180045293  mov     r8d, esi; dwFlags
0x180045296  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18004529a  call    cs:__imp_CreateEventExW
0x1800452a0  mov     rdi, rax
0x1800452a3  test    rax, rax
0x1800452a6  jnz     short loc_1800452C8
0x1800452a8  lea     r8, aGlobalAudiosrv; "Global\\AudioSrv_CanAcceptMMCClient"
0x1800452af  xor     edx, edx; bInheritHandle
0x1800452b1  mov     ecx, 100000h; dwDesiredAccess
0x1800452b6  call    cs:__imp_OpenEventW
0x1800452bc  mov     rdi, rax
0x1800452bf  test    rax, rax
0x1800452c2  jz      loc_18004538C
0x1800452c8  mov     edx, 2710h; dwMilliseconds
0x1800452cd  mov     rcx, rdi; hHandle
0x1800452d0  call    cs:__imp_WaitForSingleObject
0x1800452d6  test    eax, eax
0x1800452d8  jnz     loc_180045383
0x1800452de  mov     edx, esi
0x1800452e0  mov     rcx, rbx
0x1800452e3  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800452e8  test    eax, eax
0x1800452ea  js      loc_180045383
0x1800452f0  mov     r8d, 10h; Flags
0x1800452f6  lea     rcx, ?_PlaySoundWorkItemFromLogonUIProc@LogonSoundPlayer@LogonSoundHelpers@@CAKPEAX@Z; Function
0x1800452fd  mov     rdx, rbx; Context
0x180045300  call    cs:__imp_QueueUserWorkItem
0x180045306  test    eax, eax
0x180045308  jnz     short loc_180045312
0x18004530a  mov     rcx, [rbx]; this
0x18004530d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180045312  mov     r9d, 100000h; dwDesiredAccess
0x180045318  lea     rdx, aGlobalAudioend; "Global\\AudioEndPoint_PlaybackReady"
0x18004531f  mov     r8d, esi; dwFlags
0x180045322  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180045326  call    cs:__imp_CreateEventExW
0x18004532c  mov     rsi, rax
0x18004532f  test    rax, rax
0x180045332  jnz     short loc_180045350
0x180045334  lea     r8, aGlobalAudioend; "Global\\AudioEndPoint_PlaybackReady"
0x18004533b  xor     edx, edx; bInheritHandle
0x18004533d  mov     ecx, 100000h; dwDesiredAccess
0x180045342  call    cs:__imp_OpenEventW
0x180045348  mov     rsi, rax
0x18004534b  test    rax, rax
0x18004534e  jz      short loc_18004537B
0x180045350  mov     rax, [rbx]
0x180045353  lea     rdx, [rbp+Handles]; lpHandles
0x180045357  xor     r8d, r8d; bWaitAll
0x18004535a  mov     [rbp+Handles], rsi
0x18004535e  mov     r9d, 2710h; dwMilliseconds
0x180045364  mov     [rbp+var_30], rax
0x180045368  lea     ecx, [r8+2]; nCount
0x18004536c  call    cs:__imp_WaitForMultipleObjects
0x180045372  mov     rcx, rsi; hObject
0x180045375  call    cs:__imp_CloseHandle
0x18004537b  mov     rcx, [rbx]; this
0x18004537e  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180045383  mov     rcx, rdi; hObject
0x180045386  call    cs:__imp_CloseHandle
0x18004538c  mov     rcx, [rbp+EventAttributes.lpSecurityDescriptor]; hMem
0x180045390  test    rcx, rcx
0x180045393  jz      short loc_18004539B
0x180045395  call    cs:__imp_LocalFree
0x18004539b  xor     eax, eax
0x18004539d  add     rsp, 68h
0x1800453a1  pop     rdi
0x1800453a2  pop     rsi
0x1800453a3  pop     rbx
0x1800453a4  pop     rbp
0x1800453a5  retn
```

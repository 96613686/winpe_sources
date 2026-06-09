# SensorActivityMonitor::Stop(void)

- ea: `0x18005ae70`
- end: `0x18005afb9`
- name: `?Stop@SensorActivityMonitor@@UEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(SensorActivityMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005fa0`
- `0x18005ae70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ae84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ae84`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005aed9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005af16`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005aed9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005af16`

## pseudocode

```c
__int64 __fastcall SensorActivityMonitor::Stop(SensorActivityMonitor *this)
{
  int v2; // ebx
  _DWORD *v3; // rsi
  __int64 v4; // rcx
  int v5; // ecx
  __int64 v6; // rdx
  _DWORD *v7; // r14
  int v8; // eax
  __int64 v9; // rdx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v2 = 0;
  v3 = (_DWORD *)((char *)this + 120);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 22, &WPP_dcb17cfa78d93d90e67ac602385b39d3_Traceguids, this, *v3);
  if ( *v3 )
  {
    v4 = *((_QWORD *)this + 13);
    *v3 = 3;
    if ( v4 )
    {
      v5 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      v2 = v5 | 0x10000000;
      if ( v5 >= 0 )
        v2 = 0;
      if ( v2 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_19;
        v6 = 23;
        goto LABEL_18;
      }
      *((_QWORD *)this + 13) = 0;
      v7 = (_DWORD *)((char *)this + 120);
    }
    else
    {
      v7 = (_DWORD *)((char *)this + 120);
    }
    if ( *((_QWORD *)this + 14) )
    {
      v8 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      v2 = v8 | 0x10000000;
      if ( v8 >= 0 )
        v2 = 0;
      if ( v2 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_19;
        v6 = 24;
LABEL_18:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_dcb17cfa78d93d90e67ac602385b39d3_Traceguids, this, v2);
LABEL_19:
        if ( byte_18008D62D )
        {
          v9 = 25;
LABEL_26:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v9,
            &WPP_dcb17cfa78d93d90e67ac602385b39d3_Traceguids,
            this,
            v2);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      *((_QWORD *)this + 14) = 0;
    }
    else
    {
      v7 = (_DWORD *)((char *)this + 120);
    }
    *v7 = 0;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v9 = 26;
    goto LABEL_26;
  }
LABEL_27:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005ae70  push    rbx
0x18005ae72  push    rbp
0x18005ae73  push    rsi
0x18005ae74  push    rdi
0x18005ae75  push    r12
0x18005ae77  push    r14
0x18005ae79  sub     rsp, 38h
0x18005ae7d  mov     rdi, rcx
0x18005ae80  add     rcx, 20h ; ' '; lpCriticalSection
0x18005ae84  call    cs:__imp_EnterCriticalSection
0x18005ae8a  xor     ebx, ebx
0x18005ae8c  cmp     cs:byte_18008D62D, 8
0x18005ae93  lea     rsi, [rdi+78h]
0x18005ae97  lea     r12, WPP_dcb17cfa78d93d90e67ac602385b39d3_Traceguids
0x18005ae9e  jb      short loc_18005AEC2
0x18005aea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aea7  lea     edx, [rbx+16h]
0x18005aeaa  mov     eax, [rsi]
0x18005aeac  mov     r9, rdi
0x18005aeaf  mov     r8, r12
0x18005aeb2  mov     [rsp+68h+var_48], eax
0x18005aeb6  mov     rcx, [rcx+0D8h]
0x18005aebd  call    WPP_SF_qD
0x18005aec2  cmp     [rsi], ebx
0x18005aec4  jz      loc_18005AF75
0x18005aeca  mov     rcx, [rdi+68h]
0x18005aece  mov     dword ptr [rsi], 3
0x18005aed4  test    rcx, rcx
0x18005aed7  jz      short loc_18005AF0A
0x18005aed9  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18005aedf  mov     ebx, eax
0x18005aee1  mov     ecx, eax
0x18005aee3  bts     ebx, 1Ch
0x18005aee7  xor     eax, eax
0x18005aee9  test    ecx, ecx
0x18005aeeb  cmovns  ebx, eax
0x18005aeee  test    ebx, ebx
0x18005aef0  jns     short loc_18005AF00
0x18005aef2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005aef9  jb      short loc_18005AF55
0x18005aefb  lea     edx, [rax+17h]
0x18005aefe  jmp     short loc_18005AF3B
0x18005af00  mov     [rdi+68h], rax
0x18005af04  lea     r14, [rdi+78h]
0x18005af08  jmp     short loc_18005AF0D
0x18005af0a  mov     r14, rsi
0x18005af0d  mov     rcx, [rdi+70h]
0x18005af11  test    rcx, rcx
0x18005af14  jz      short loc_18005AF6B
0x18005af16  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18005af1c  mov     ebx, eax
0x18005af1e  mov     ecx, eax
0x18005af20  bts     ebx, 1Ch
0x18005af24  xor     eax, eax
0x18005af26  test    ecx, ecx
0x18005af28  cmovns  ebx, eax
0x18005af2b  test    ebx, ebx
0x18005af2d  jns     short loc_18005AF65
0x18005af2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005af36  jb      short loc_18005AF55
0x18005af38  lea     edx, [rax+18h]
0x18005af3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af42  mov     r9, rdi
0x18005af45  mov     r8, r12
0x18005af48  mov     [rsp+68h+var_48], ebx
0x18005af4c  mov     rcx, [rcx+10h]
0x18005af50  call    WPP_SF_qD
0x18005af55  cmp     cs:byte_18008D62D, 1
0x18005af5c  jb      short loc_18005AFA0
0x18005af5e  mov     edx, 19h
0x18005af63  jmp     short loc_18005AF83
0x18005af65  mov     [rdi+70h], rax
0x18005af69  jmp     short loc_18005AF6E
0x18005af6b  mov     r14, rsi
0x18005af6e  mov     dword ptr [r14], 0
0x18005af75  cmp     cs:byte_18008D62D, 8
0x18005af7c  jb      short loc_18005AFA0
0x18005af7e  mov     edx, 1Ah
0x18005af83  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af8a  mov     r9, rdi
0x18005af8d  mov     r8, r12
0x18005af90  mov     [rsp+68h+var_48], ebx
0x18005af94  mov     rcx, [rcx+0D8h]
0x18005af9b  call    WPP_SF_qD
0x18005afa0  lea     rcx, [rdi+20h]; lpCriticalSection
0x18005afa4  call    cs:__imp_LeaveCriticalSection
0x18005afaa  mov     eax, ebx
0x18005afac  add     rsp, 38h
0x18005afb0  pop     r14
0x18005afb2  pop     r12
0x18005afb4  pop     rdi
0x18005afb5  pop     rsi
0x18005afb6  pop     rbp
0x18005afb7  pop     rbx
0x18005afb8  retn
```

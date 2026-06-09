# CAvEndpointBuilder::UnsubscribePostureChangeNotification(void)

- ea: `0x180054098`
- end: `0x180054193`
- name: `?UnsubscribePostureChangeNotification@CAvEndpointBuilder@@AEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049424`

## callees

- `0x180033464`
- `0x180034c5c`
- `0x180054098`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800540aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800540aa`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800540ee`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005413a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800540ee`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005413a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005416e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005416e`

## string_xrefs

- `0x18005414e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CAvEndpointBuilder::UnsubscribePostureChangeNotification(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  unsigned int v3; // eax
  __int64 v4; // rdx
  HANDLE OwningThread; // rcx
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  EnterCriticalSection(lpCriticalSection);
  v2 = 0;
  if ( lpCriticalSection[1].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion(lpCriticalSection[1].DebugInfo);
    if ( v3 )
    {
      v4 = 11675;
LABEL_16:
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
             (const char *)v3,
             v7);
      goto LABEL_20;
    }
    lpCriticalSection[1].DebugInfo = 0;
  }
  if ( *(_QWORD *)&lpCriticalSection[1].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion(*(_QWORD *)&lpCriticalSection[1].LockCount);
    if ( v3 )
    {
      v4 = 11682;
      goto LABEL_16;
    }
    *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  }
  OwningThread = lpCriticalSection[1].OwningThread;
  if ( OwningThread )
  {
    CoTaskMemFree(OwningThread);
    lpCriticalSection[1].OwningThread = 0;
  }
LABEL_20:
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x180054098  mov     [rsp+arg_0], rbx
0x18005409d  mov     [rsp+arg_8], rbp
0x1800540a2  push    rdi; unsigned int
0x1800540a3  sub     rsp, 20h
0x1800540a7  mov     rbx, rcx
0x1800540aa  call    cs:__imp_EnterCriticalSection
0x1800540b0  xor     edi, edi
0x1800540b2  lea     rbp, WPP_GLOBAL_Control
0x1800540b9  cmp     [rbx+28h], rdi
0x1800540bd  jz      short loc_180054103
0x1800540bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540c6  cmp     rcx, rbp
0x1800540c9  jz      short loc_1800540EA
0x1800540cb  test    byte ptr [rcx+1Ch], 4
0x1800540cf  jz      short loc_1800540EA
0x1800540d1  cmp     byte ptr [rcx+19h], 4
0x1800540d5  jb      short loc_1800540EA
0x1800540d7  mov     rcx, [rcx+10h]
0x1800540db  lea     edx, [rdi+6Fh]
0x1800540de  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x1800540e5  call    WPP_SF_
0x1800540ea  mov     rcx, [rbx+28h]
0x1800540ee  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800540f4  test    eax, eax
0x1800540f6  jz      short loc_1800540FF
0x1800540f8  mov     edx, 2D9Bh
0x1800540fd  jmp     short loc_180054149
0x1800540ff  mov     [rbx+28h], rdi
0x180054103  cmp     [rbx+30h], rdi
0x180054107  jz      short loc_180054165
0x180054109  mov     rcx, cs:WPP_GLOBAL_Control
0x180054110  cmp     rcx, rbp
0x180054113  jz      short loc_180054136
0x180054115  test    byte ptr [rcx+1Ch], 4
0x180054119  jz      short loc_180054136
0x18005411b  cmp     byte ptr [rcx+19h], 4
0x18005411f  jb      short loc_180054136
0x180054121  mov     rcx, [rcx+10h]
0x180054125  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x18005412c  mov     edx, 70h ; 'p'
0x180054131  call    WPP_SF_
0x180054136  mov     rcx, [rbx+30h]
0x18005413a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180054140  test    eax, eax
0x180054142  jz      short loc_180054161
0x180054144  mov     edx, 2DA2h; void *
0x180054149  mov     rcx, [rsp+28h]; this
0x18005414e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180054155  mov     r9d, eax; char *
0x180054158  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005415d  mov     edi, eax
0x18005415f  jmp     short loc_180054178
0x180054161  mov     [rbx+30h], rdi
0x180054165  mov     rcx, [rbx+38h]; pv
0x180054169  test    rcx, rcx
0x18005416c  jz      short loc_180054178
0x18005416e  call    cs:__imp_CoTaskMemFree
0x180054174  mov     [rbx+38h], rdi
0x180054178  mov     rcx, rbx; lpCriticalSection
0x18005417b  call    cs:__imp_LeaveCriticalSection
0x180054181  mov     rbx, [rsp+28h+arg_0]
0x180054186  mov     eax, edi
0x180054188  mov     rbp, [rsp+28h+arg_8]
0x18005418d  add     rsp, 20h
0x180054191  pop     rdi
0x180054192  retn
```

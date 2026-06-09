# CxsUnregisterWlanNotification(_GIP_WLAN_CLIENT *)

- ea: `0x18000a540`
- end: `0x18000a5eb`
- name: `?CxsUnregisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(struct _GIP_WLAN_CLIENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a9c0`

## callees

- `0x180002b70`
- `0x18000a540`
- `0x18000adf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a8`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000a55f`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000a55f`

## pseudocode

```c
__int64 __fastcall CxsUnregisterWlanNotification(struct _GIP_WLAN_CLIENT *a1)
{
  DWORD v2; // edi
  void *v3; // rcx

  v2 = NotifyServiceStatusChangeW(*((SC_HANDLE *)a1 + 9), 8u, (PSERVICE_NOTIFYW)((char *)a1 + 88));
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, v2);
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
    if ( (*(_DWORD *)a1 & 2) == 0 )
    {
      v3 = (void *)*((_QWORD *)a1 + 8);
      *(_DWORD *)a1 &= ~1u;
      if ( v3 )
      {
        CxspUnregisterWlanNotification(v3);
        *((_QWORD *)a1 + 8) = 0;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
  }
  return v2;
}

```

## disassembly

```asm
0x18000a540  mov     [rsp+arg_0], rbx
0x18000a545  mov     [rsp+arg_8], rsi
0x18000a54a  push    rdi
0x18000a54b  sub     rsp, 20h
0x18000a54f  mov     rbx, rcx
0x18000a552  lea     r8, [rcx+58h]; pNotifyBuffer
0x18000a556  mov     rcx, [rcx+48h]; hService
0x18000a55a  mov     edx, 8; dwNotifyMask
0x18000a55f  call    cs:__imp_NotifyServiceStatusChangeW
0x18000a565  mov     edi, eax
0x18000a567  test    eax, eax
0x18000a569  jz      short loc_18000A5A4
0x18000a56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a572  lea     rax, WPP_GLOBAL_Control
0x18000a579  cmp     rcx, rax
0x18000a57c  jz      short loc_18000A5D9
0x18000a57e  test    byte ptr [rcx+1Ch], 4
0x18000a582  jz      short loc_18000A5D9
0x18000a584  cmp     byte ptr [rcx+19h], 1
0x18000a588  jb      short loc_18000A5D9
0x18000a58a  mov     rcx, [rcx+10h]
0x18000a58e  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a595  mov     edx, 22h ; '"'
0x18000a59a  mov     r9d, edi
0x18000a59d  call    WPP_SF_D
0x18000a5a2  jmp     short loc_18000A5D9
0x18000a5a4  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a5a8  call    cs:__imp_EnterCriticalSection
0x18000a5ae  mov     eax, [rbx]
0x18000a5b0  test    al, 2
0x18000a5b2  jnz     short loc_18000A5CF
0x18000a5b4  mov     rcx, [rbx+40h]; hClientHandle
0x18000a5b8  and     eax, 0FFFFFFFEh
0x18000a5bb  mov     [rbx], eax
0x18000a5bd  test    rcx, rcx
0x18000a5c0  jz      short loc_18000A5CF
0x18000a5c2  call    ?CxspUnregisterWlanNotification@@YAXPEAX@Z; CxspUnregisterWlanNotification(void *)
0x18000a5c7  mov     qword ptr [rbx+40h], 0
0x18000a5cf  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a5d3  call    cs:__imp_LeaveCriticalSection
0x18000a5d9  mov     rbx, [rsp+28h+arg_0]
0x18000a5de  mov     eax, edi
0x18000a5e0  mov     rsi, [rsp+28h+arg_8]
0x18000a5e5  add     rsp, 20h
0x18000a5e9  pop     rdi
0x18000a5ea  retn
```

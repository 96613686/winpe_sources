# CxsRegisterWlanNotification(_GIP_WLAN_CLIENT *)

- ea: `0x18000a1b4`
- end: `0x18000a25d`
- name: `?CxsRegisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct _GIP_WLAN_CLIENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a9c0`

## callees

- `0x180002b70`
- `0x18000a1b4`
- `0x18000ac68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a245`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a245`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a21c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a21c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000a1d3`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18000a1d3`

## pseudocode

```c
__int64 __fastcall CxsRegisterWlanNotification(struct _GIP_WLAN_CLIENT *a1)
{
  unsigned int v2; // edi
  void (*v3)(struct _L2_NOTIFICATION_DATA *, void *); // rdx
  bool v4; // zf

  v2 = NotifyServiceStatusChangeW(*((SC_HANDLE *)a1 + 9), 1u, (PSERVICE_NOTIFYW)((char *)a1 + 88));
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, v2);
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
    if ( (*(_DWORD *)a1 & 2) == 0 )
    {
      v4 = *((_QWORD *)a1 + 8) == 0;
      *(_DWORD *)a1 |= 1u;
      if ( v4 )
        v2 = CxspRegisterWlanNotification((void **)a1, v3, a1);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
  }
  return v2;
}

```

## disassembly

```asm
0x18000a1b4  mov     [rsp+arg_0], rbx
0x18000a1b9  mov     [rsp+arg_8], rsi
0x18000a1be  push    rdi
0x18000a1bf  sub     rsp, 20h
0x18000a1c3  mov     rbx, rcx
0x18000a1c6  lea     r8, [rcx+58h]; pNotifyBuffer
0x18000a1ca  mov     rcx, [rcx+48h]; hService
0x18000a1ce  mov     edx, 1; dwNotifyMask
0x18000a1d3  call    cs:__imp_NotifyServiceStatusChangeW
0x18000a1d9  mov     edi, eax
0x18000a1db  test    eax, eax
0x18000a1dd  jz      short loc_18000A218
0x18000a1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1e6  lea     rax, WPP_GLOBAL_Control
0x18000a1ed  cmp     rcx, rax
0x18000a1f0  jz      short loc_18000A24B
0x18000a1f2  test    byte ptr [rcx+1Ch], 4
0x18000a1f6  jz      short loc_18000A24B
0x18000a1f8  cmp     byte ptr [rcx+19h], 1
0x18000a1fc  jb      short loc_18000A24B
0x18000a1fe  mov     rcx, [rcx+10h]
0x18000a202  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a209  mov     edx, 21h ; '!'
0x18000a20e  mov     r9d, edi
0x18000a211  call    WPP_SF_D
0x18000a216  jmp     short loc_18000A24B
0x18000a218  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a21c  call    cs:__imp_EnterCriticalSection
0x18000a222  mov     eax, [rbx]
0x18000a224  test    al, 2
0x18000a226  jnz     short loc_18000A241
0x18000a228  or      eax, 1
0x18000a22b  cmp     qword ptr [rbx+40h], 0
0x18000a230  mov     [rbx], eax
0x18000a232  jnz     short loc_18000A241
0x18000a234  mov     r8, rbx; void *
0x18000a237  mov     rcx, rbx; struct _GIP_WLAN_CLIENT *
0x18000a23a  call    ?CxspRegisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@P6AXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z2@Z; CxspRegisterWlanNotification(_GIP_WLAN_CLIENT *,void (*)(_L2_NOTIFICATION_DATA *,void *),void *)
0x18000a23f  mov     edi, eax
0x18000a241  lea     rcx, [rbx+8]; lpCriticalSection
0x18000a245  call    cs:__imp_LeaveCriticalSection
0x18000a24b  mov     rbx, [rsp+28h+arg_0]
0x18000a250  mov     eax, edi
0x18000a252  mov     rsi, [rsp+28h+arg_8]
0x18000a257  add     rsp, 20h
0x18000a25b  pop     rdi
0x18000a25c  retn
```

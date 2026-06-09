# DmWnfGetNotification(_WNF_STATE_NAME,ulong,uchar *,ulong *,ulong)

- ea: `0x18007a690`
- end: `0x18007a810`
- name: `?DmWnfGetNotification@@YAJU_WNF_STATE_NAME@@KPEAEPEAKK@Z`
- size: `384`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, unsigned __int8 *, unsigned int *, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063e10`
- `0x1800648f0`

## callees

- `0x18007a690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a6e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a6e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a792`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007a792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a7f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a7f6`
- `ntdll!RtlNtStatusToDosError` at `0x18007a777`
- `ntdll!RtlNtStatusToDosError` at `0x18007a777`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007a765`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007a765`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007a7e2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18007a7e2`

## pseudocode

```c
__int64 __fastcall DmWnfGetNotification(
        struct _WNF_STATE_NAME a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        DWORD dwMilliseconds)
{
  HANDLE EventW; // rdi
  signed int LastError; // eax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  DWORD v13; // eax
  __int64 v15; // [rsp+40h] [rbp-48h] BYREF
  __int128 v16; // [rsp+48h] [rbp-40h] BYREF
  HANDLE v17; // [rsp+58h] [rbp-30h]

  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    EventW = 0;
    v11 = -2147024809;
    goto LABEL_18;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    goto LABEL_5;
  LODWORD(v16) = *a4;
  DWORD1(v16) = a2;
  *((_QWORD *)&v16 + 1) = a3;
  v17 = EventW;
  v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RtlSubscribeWnfStateChangeNotification)(
          &v15,
          a1,
          0,
          wnf_query_callback,
          &v16,
          0,
          0,
          0);
  if ( v12 >= 0 )
  {
    v13 = WaitForSingleObject(EventW, dwMilliseconds);
    switch ( v13 )
    {
      case 0u:
        v11 = 0;
        *a4 = v16;
        goto LABEL_18;
      case 0x80u:
        goto LABEL_14;
      case 0x102u:
        v11 = -2147024638;
        goto LABEL_18;
    }
    if ( v13 != -1 )
    {
LABEL_14:
      v11 = -2147418113;
      goto LABEL_18;
    }
LABEL_5:
    LastError = GetLastError();
    goto LABEL_6;
  }
  LastError = RtlNtStatusToDosError(v12);
LABEL_6:
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
  if ( v15 )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( EventW )
    CloseHandle(EventW);
  return v11;
}

```

## disassembly

```asm
0x18007a690  push    rbx
0x18007a692  push    rbp
0x18007a693  push    rsi
0x18007a694  push    rdi
0x18007a695  push    r14
0x18007a697  sub     rsp, 60h
0x18007a69b  xor     eax, eax
0x18007a69d  mov     [rsp+88h+var_48], 0
0x18007a6a6  mov     [rsp+88h+var_30], rax
0x18007a6ab  xorps   xmm0, xmm0
0x18007a6ae  mov     rsi, r9
0x18007a6b1  mov     rbp, r8
0x18007a6b4  mov     r14d, edx
0x18007a6b7  mov     rbx, rcx
0x18007a6ba  movups  [rsp+88h+var_40], xmm0
0x18007a6bf  test    edx, edx
0x18007a6c1  jz      loc_18007A7D1
0x18007a6c7  test    r8, r8
0x18007a6ca  jz      loc_18007A7D1
0x18007a6d0  test    r9, r9
0x18007a6d3  jz      loc_18007A7D1
0x18007a6d9  xor     r9d, r9d; lpName
0x18007a6dc  xor     r8d, r8d; bInitialState
0x18007a6df  xor     edx, edx; bManualReset
0x18007a6e1  xor     ecx, ecx; lpEventAttributes
0x18007a6e3  call    cs:__imp_CreateEventW
0x18007a6ea  nop     dword ptr [rax+rax+00h]
0x18007a6ef  mov     rdi, rax
0x18007a6f2  test    rax, rax
0x18007a6f5  jnz     short loc_18007A71B
0x18007a6f7  call    cs:__imp_GetLastError
0x18007a6fe  nop     dword ptr [rax+rax+00h]
0x18007a703  mov     ebx, eax
0x18007a705  test    eax, eax
0x18007a707  jle     loc_18007A7D8
0x18007a70d  movzx   ebx, ax
0x18007a710  or      ebx, 80070000h
0x18007a716  jmp     loc_18007A7D8
0x18007a71b  mov     eax, [rsi]
0x18007a71d  lea     r9, wnf_query_callback
0x18007a724  mov     [rsp+88h+var_50], 0
0x18007a72c  lea     rcx, [rsp+88h+var_48]
0x18007a731  mov     dword ptr [rsp+88h+var_40], eax
0x18007a735  xor     r8d, r8d
0x18007a738  lea     rax, [rsp+88h+var_40]
0x18007a73d  mov     [rsp+88h+var_58], 0
0x18007a745  mov     [rsp+88h+var_60], 0
0x18007a74e  mov     rdx, rbx
0x18007a751  mov     [rsp+88h+var_68], rax
0x18007a756  mov     dword ptr [rsp+88h+var_40+4], r14d
0x18007a75b  mov     qword ptr [rsp+88h+var_40+8], rbp
0x18007a760  mov     [rsp+88h+var_30], rdi
0x18007a765  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18007a76c  nop     dword ptr [rax+rax+00h]
0x18007a771  test    eax, eax
0x18007a773  jns     short loc_18007A788
0x18007a775  mov     ecx, eax; Status
0x18007a777  call    cs:__imp_RtlNtStatusToDosError
0x18007a77e  nop     dword ptr [rax+rax+00h]
0x18007a783  jmp     loc_18007A703
0x18007a788  mov     edx, [rsp+88h+dwMilliseconds]; dwMilliseconds
0x18007a78f  mov     rcx, rdi; hHandle
0x18007a792  call    cs:__imp_WaitForSingleObject
0x18007a799  nop     dword ptr [rax+rax+00h]
0x18007a79e  test    eax, eax
0x18007a7a0  jz      short loc_18007A7C7
0x18007a7a2  cmp     eax, 80h
0x18007a7a7  jz      short loc_18007A7B9
0x18007a7a9  cmp     eax, 102h
0x18007a7ae  jz      short loc_18007A7C0
0x18007a7b0  cmp     eax, 0FFFFFFFFh
0x18007a7b3  jz      loc_18007A6F7
0x18007a7b9  mov     ebx, 8000FFFFh
0x18007a7be  jmp     short loc_18007A7D8
0x18007a7c0  mov     ebx, 80070102h
0x18007a7c5  jmp     short loc_18007A7D8
0x18007a7c7  mov     eax, dword ptr [rsp+88h+var_40]
0x18007a7cb  xor     ebx, ebx
0x18007a7cd  mov     [rsi], eax
0x18007a7cf  jmp     short loc_18007A7D8
0x18007a7d1  xor     edi, edi
0x18007a7d3  mov     ebx, 80070057h
0x18007a7d8  mov     rcx, [rsp+88h+var_48]
0x18007a7dd  test    rcx, rcx
0x18007a7e0  jz      short loc_18007A7EE
0x18007a7e2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18007a7e9  nop     dword ptr [rax+rax+00h]
0x18007a7ee  test    rdi, rdi
0x18007a7f1  jz      short loc_18007A802
0x18007a7f3  mov     rcx, rdi; hObject
0x18007a7f6  call    cs:__imp_CloseHandle
0x18007a7fd  nop     dword ptr [rax+rax+00h]
0x18007a802  mov     eax, ebx
0x18007a804  add     rsp, 60h
0x18007a808  pop     r14
0x18007a80a  pop     rdi
0x18007a80b  pop     rsi
0x18007a80c  pop     rbp
0x18007a80d  pop     rbx
0x18007a80e  retn
```

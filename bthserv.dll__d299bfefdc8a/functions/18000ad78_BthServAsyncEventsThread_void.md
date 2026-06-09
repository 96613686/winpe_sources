# BthServAsyncEventsThread(void *)

- ea: `0x18000ad78`
- end: `0x18000b0ee`
- name: `?BthServAsyncEventsThread@@YAKPEAX@Z`
- size: `886`
- prototype: `__int64 __fastcall(HANDLE hEvent)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b100`

## callees

- `0x18000ad78`
- `0x18000f2e8`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x18001b2b4`
- `0x18001b628`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ae99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ae99`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ae40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ae40`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000af6a`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000af6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b089`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b089`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000b062`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000b062`

## pseudocode

```c
__int64 __fastcall BthServAsyncEventsThread(HANDLE hEvent)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  bool v7; // dl
  int v8; // edx
  DWORD v9; // ebx
  int v10; // r8d
  _BYTE *v11; // rcx
  _UNKNOWN **v12; // rax
  bool v13; // dl
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  volatile signed __int32 *v17; // rbx
  _BYTE *v18; // rcx
  bool v19; // dl
  PVOID v20; // rax
  int v22; // [rsp+20h] [rbp-68h]
  int v23; // [rsp+28h] [rbp-60h]
  HANDLE *v24; // [rsp+50h] [rbp-38h] BYREF
  volatile signed __int32 *v25; // [rsp+58h] [rbp-30h]

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v2 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v2 + 5));
  BthServStartAutoConfigServiceMonitor();
  SetEvent(hEvent);
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  do
  {
    v9 = WaitForSingleObjectEx(::hEvent, 0xFFFFFFFF, 1);
    v11 = WPP_GLOBAL_Control;
    LOBYTE(v8) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    v12 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        131,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      v11 = WPP_GLOBAL_Control;
      v12 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
  }
  while ( v9 );
  v13 = v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 4u;
  if ( v13 || v12 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v11 + 2), v13, v12 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v11 + 5));
  BthServStopAutoConfigServiceMonitor();
  BthServGlobals::GetSafeRadioHandle(&Globals, &v24, v14);
  if ( v24 && (char *)*v24 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CancelIoEx(*v24, 0);
  v17 = v25;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = WPP_GLOBAL_Control;
  v19 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v18 = WPP_GLOBAL_Control;
  }
  v20 = pv;
  if ( pv )
  {
    LOBYTE(v15) = v18 != (_BYTE *)&WPP_GLOBAL_Control && v18[25] >= 4u;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v18 + 2), v15, v16, *((_QWORD *)v18 + 5));
      v20 = pv;
    }
    CM_Unregister_Notification(v20, v15, v16);
    v18 = WPP_GLOBAL_Control;
    pv = 0;
  }
  if ( *(&pv + 1) )
  {
    LocalFree(*(&pv + 1));
    v18 = WPP_GLOBAL_Control;
    *(&pv + 1) = 0;
  }
  if ( v18 == (_BYTE *)&WPP_GLOBAL_Control || v18[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v18 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v18 + 5));
  return 0;
}

```

## disassembly

```asm
0x18000ad78  push    rbx
0x18000ad7a  push    rbp
0x18000ad7b  push    rdi
0x18000ad7c  push    r12
0x18000ad7e  push    r15
0x18000ad80  sub     rsp, 60h
0x18000ad84  mov     rbx, rcx
0x18000ad87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad8e  lea     rbp, WPP_GLOBAL_Control
0x18000ad95  mov     edi, 1
0x18000ad9a  cmp     rcx, rbp
0x18000ad9d  jz      short loc_18000ADAA
0x18000ad9f  cmp     byte ptr [rcx+19h], 5
0x18000ada3  jb      short loc_18000ADAA
0x18000ada5  mov     dl, dil
0x18000ada8  jmp     short loc_18000ADAC
0x18000adaa  xor     dl, dl
0x18000adac  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000adb3  lea     r15, WPP_RECORDER_INITIALIZED
0x18000adba  cmp     rax, r15
0x18000adbd  lea     r12, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000adc4  setnz   r8b
0x18000adc8  test    dl, dl
0x18000adca  jnz     short loc_18000ADD1
0x18000adcc  test    r8b, r8b
0x18000adcf  jz      short loc_18000ADF8
0x18000add1  mov     r9, [rcx+28h]
0x18000add5  mov     rcx, [rcx+10h]
0x18000add9  mov     [rsp+88h+var_50], r12
0x18000adde  mov     [rsp+88h+var_58], 80h
0x18000ade5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000adea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adf1  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000adf8  cmp     rcx, rbp
0x18000adfb  jz      short loc_18000AE08
0x18000adfd  cmp     byte ptr [rcx+19h], 4
0x18000ae01  jb      short loc_18000AE08
0x18000ae03  mov     dl, dil
0x18000ae06  jmp     short loc_18000AE0A
0x18000ae08  xor     dl, dl
0x18000ae0a  cmp     rax, r15
0x18000ae0d  setnz   r8b
0x18000ae11  test    dl, dl
0x18000ae13  jnz     short loc_18000AE1A
0x18000ae15  test    r8b, r8b
0x18000ae18  jz      short loc_18000AE38
0x18000ae1a  mov     r9, [rcx+28h]
0x18000ae1e  mov     rcx, [rcx+10h]
0x18000ae22  mov     [rsp+88h+var_40], rbx
0x18000ae27  mov     [rsp+88h+var_50], r12
0x18000ae2c  mov     [rsp+88h+var_58], 81h
0x18000ae33  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000ae38  call    ?BthServStartAutoConfigServiceMonitor@@YAXXZ; BthServStartAutoConfigServiceMonitor(void)
0x18000ae3d  mov     rcx, rbx; hEvent
0x18000ae40  call    cs:__imp_SetEvent
0x18000ae46  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae4d  cmp     rcx, rbp
0x18000ae50  jz      short loc_18000AE5D
0x18000ae52  cmp     byte ptr [rcx+19h], 4
0x18000ae56  jb      short loc_18000AE5D
0x18000ae58  mov     dl, dil
0x18000ae5b  jmp     short loc_18000AE5F
0x18000ae5d  xor     dl, dl
0x18000ae5f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000ae66  setnz   r8b
0x18000ae6a  test    dl, dl
0x18000ae6c  jnz     short loc_18000AE73
0x18000ae6e  test    r8b, r8b
0x18000ae71  jz      short loc_18000AE8C
0x18000ae73  mov     r9, [rcx+28h]
0x18000ae77  mov     rcx, [rcx+10h]
0x18000ae7b  mov     [rsp+88h+var_50], r12
0x18000ae80  mov     [rsp+88h+var_58], 82h
0x18000ae87  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ae8c  mov     rcx, cs:hEvent; hHandle
0x18000ae93  mov     r8d, edi; bAlertable
0x18000ae96  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ae99  call    cs:__imp_WaitForSingleObjectEx
0x18000ae9f  mov     ebx, eax
0x18000aea1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aea8  cmp     rcx, rbp
0x18000aeab  jz      short loc_18000AEB8
0x18000aead  cmp     byte ptr [rcx+19h], 4
0x18000aeb1  jb      short loc_18000AEB8
0x18000aeb3  mov     dl, dil
0x18000aeb6  jmp     short loc_18000AEBA
0x18000aeb8  xor     dl, dl
0x18000aeba  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000aec1  cmp     rax, r15
0x18000aec4  setnz   r8b
0x18000aec8  test    dl, dl
0x18000aeca  jnz     short loc_18000AED1
0x18000aecc  test    r8b, r8b
0x18000aecf  jz      short loc_18000AEFC
0x18000aed1  mov     r9, [rcx+28h]
0x18000aed5  mov     rcx, [rcx+10h]
0x18000aed9  mov     dword ptr [rsp+88h+var_40], ebx
0x18000aedd  mov     [rsp+88h+var_50], r12
0x18000aee2  mov     [rsp+88h+var_58], 83h
0x18000aee9  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000aeee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aef5  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18000aefc  test    ebx, ebx
0x18000aefe  jnz     short loc_18000AE8C
0x18000af00  cmp     rcx, rbp
0x18000af03  jz      short loc_18000AF10
0x18000af05  cmp     byte ptr [rcx+19h], 4
0x18000af09  jb      short loc_18000AF10
0x18000af0b  mov     dl, dil
0x18000af0e  jmp     short loc_18000AF12
0x18000af10  xor     dl, dl
0x18000af12  cmp     rax, r15
0x18000af15  setnz   r8b
0x18000af19  test    dl, dl
0x18000af1b  jnz     short loc_18000AF22
0x18000af1d  test    r8b, r8b
0x18000af20  jz      short loc_18000AF3B
0x18000af22  mov     r9, [rcx+28h]
0x18000af26  mov     rcx, [rcx+10h]
0x18000af2a  mov     [rsp+88h+var_50], r12
0x18000af2f  mov     [rsp+88h+var_58], 84h
0x18000af36  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000af3b  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18000af40  lea     rdx, [rsp+88h+var_38]
0x18000af45  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18000af4c  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18000af51  mov     rax, [rsp+88h+var_38]
0x18000af56  test    rax, rax
0x18000af59  jz      short loc_18000AF70
0x18000af5b  mov     rcx, [rax]; hFile
0x18000af5e  lea     rax, [rcx-1]
0x18000af62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000af66  ja      short loc_18000AF70
0x18000af68  xor     edx, edx; lpOverlapped
0x18000af6a  call    cs:__imp_CancelIoEx
0x18000af70  mov     rbx, [rsp+88h+var_30]
0x18000af75  test    rbx, rbx
0x18000af78  jz      short loc_18000AFAF
0x18000af7a  or      eax, 0FFFFFFFFh
0x18000af7d  lock xadd [rbx+8], eax
0x18000af82  cmp     eax, edi
0x18000af84  jnz     short loc_18000AFAF
0x18000af86  mov     rax, [rbx]
0x18000af89  mov     rcx, rbx
0x18000af8c  mov     rax, [rax]
0x18000af8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af94  or      eax, 0FFFFFFFFh
0x18000af97  lock xadd [rbx+0Ch], eax
0x18000af9c  cmp     eax, edi
0x18000af9e  jnz     short loc_18000AFAF
0x18000afa0  mov     rax, [rbx]
0x18000afa3  mov     rcx, rbx
0x18000afa6  mov     rax, [rax+8]
0x18000afaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afb6  cmp     rcx, rbp
0x18000afb9  jz      short loc_18000AFC6
0x18000afbb  cmp     byte ptr [rcx+19h], 4
0x18000afbf  jb      short loc_18000AFC6
0x18000afc1  mov     dl, dil
0x18000afc4  jmp     short loc_18000AFC8
0x18000afc6  xor     dl, dl
0x18000afc8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000afcf  setnz   r8b
0x18000afd3  test    dl, dl
0x18000afd5  jnz     short loc_18000AFDC
0x18000afd7  test    r8b, r8b
0x18000afda  jz      short loc_18000B008
0x18000afdc  mov     rax, qword ptr cs:pv
0x18000afe3  mov     r9, [rcx+28h]
0x18000afe7  mov     rcx, [rcx+10h]
0x18000afeb  mov     [rsp+88h+var_40], rax
0x18000aff0  mov     [rsp+88h+var_50], r12
0x18000aff5  mov     [rsp+88h+var_58], 85h
0x18000affc  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b001  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b008  mov     rax, qword ptr cs:pv
0x18000b00f  test    rax, rax
0x18000b012  jz      short loc_18000B07A
0x18000b014  cmp     rcx, rbp
0x18000b017  jz      short loc_18000B024
0x18000b019  cmp     byte ptr [rcx+19h], 4
0x18000b01d  jb      short loc_18000B024
0x18000b01f  mov     dl, dil
0x18000b022  jmp     short loc_18000B026
0x18000b024  xor     dl, dl
0x18000b026  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b02d  setnz   r8b
0x18000b031  test    dl, dl
0x18000b033  jnz     short loc_18000B03A
0x18000b035  test    r8b, r8b
0x18000b038  jz      short loc_18000B05F
0x18000b03a  mov     r9, [rcx+28h]
0x18000b03e  mov     rcx, [rcx+10h]
0x18000b042  mov     [rsp+88h+var_40], rax
0x18000b047  mov     [rsp+88h+var_50], r12
0x18000b04c  mov     [rsp+88h+var_58], 86h
0x18000b053  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000b058  mov     rax, qword ptr cs:pv
0x18000b05f  mov     rcx, rax
0x18000b062  call    cs:__imp_CM_Unregister_Notification
0x18000b068  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b06f  mov     qword ptr cs:pv, 0
0x18000b07a  mov     rax, qword ptr cs:pv+8
0x18000b081  test    rax, rax
0x18000b084  jz      short loc_18000B0A1
0x18000b086  mov     rcx, rax; hMem
0x18000b089  call    cs:__imp_LocalFree
0x18000b08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b096  mov     qword ptr cs:pv+8, 0
0x18000b0a1  cmp     rcx, rbp
0x18000b0a4  jz      short loc_18000B0AC
0x18000b0a6  cmp     byte ptr [rcx+19h], 5
0x18000b0aa  jnb     short loc_18000B0AF
0x18000b0ac  xor     dil, dil
0x18000b0af  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b0b6  setnz   r8b
0x18000b0ba  test    dil, dil
0x18000b0bd  jnz     short loc_18000B0C4
0x18000b0bf  test    r8b, r8b
0x18000b0c2  jz      short loc_18000B0E0
0x18000b0c4  mov     r9, [rcx+28h]
0x18000b0c8  mov     dl, dil
0x18000b0cb  mov     rcx, [rcx+10h]
0x18000b0cf  mov     [rsp+88h+var_50], r12
0x18000b0d4  mov     [rsp+88h+var_58], 87h
0x18000b0db  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000b0e0  xor     eax, eax
0x18000b0e2  add     rsp, 60h
0x18000b0e6  pop     r15
0x18000b0e8  pop     r12
0x18000b0ea  pop     rdi
0x18000b0eb  pop     rbp
0x18000b0ec  pop     rbx
0x18000b0ed  retn
```

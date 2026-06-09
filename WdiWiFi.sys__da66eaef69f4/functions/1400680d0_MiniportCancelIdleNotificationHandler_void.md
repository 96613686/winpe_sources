# MiniportCancelIdleNotificationHandler(void *)

- ea: `0x1400680d0`
- end: `0x140068217`
- name: `?MiniportCancelIdleNotificationHandler@@YAXPEAX@Z`
- size: `327`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007630`
- `0x140034e04`
- `0x140034ec4`
- `0x1400680d0`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisMIdleNotificationComplete` at `0x1400681ac`
- `NDIS!NdisMIdleNotificationComplete` at `0x1400681ac`

## pseudocode

```c
void __fastcall MiniportCancelIdleNotificationHandler(CWdiDriver *a1)
{
  CWdiDriver *v1; // rdi
  struct CAdapter *AdapterFromAdapterContext; // rax
  int v3; // edx
  struct CAdapter *v4; // rbx
  void (__fastcall *LeCancelIdleNotificationHandler)(CWdiDriver *); // rax

  v1 = a1;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    a1 = (CWdiDriver *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        62,
        (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        63,
        (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids);
  }
  AdapterFromAdapterContext = CWdiDriver::GetAdapterFromAdapterContext(a1, v1);
  v4 = AdapterFromAdapterContext;
  if ( AdapterFromAdapterContext->m_UsbIdleState )
  {
    LeCancelIdleNotificationHandler = (void (__fastcall *)(CWdiDriver *))AdapterFromAdapterContext->m_MiniportDriver->m_MiniportWdiCharacteristics.LeCancelIdleNotificationHandler;
    if ( LeCancelIdleNotificationHandler )
    {
      LeCancelIdleNotificationHandler(v1);
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          1,
          64,
          (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids);
      NdisMIdleNotificationComplete(v4->m_MiniportAdapterHandle);
    }
    v4->m_UsbIdleState = WdiUsbIdleStateInit;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v3) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      1,
      65,
      (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids,
      0);
  }
}

```

## disassembly

```asm
0x1400680d0  push    rbx
0x1400680d2  push    rbp
0x1400680d3  push    rsi
0x1400680d4  push    rdi
0x1400680d5  push    r15
0x1400680d7  sub     rsp, 30h
0x1400680db  mov     rdi, rcx
0x1400680de  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400680e5  xor     esi, esi
0x1400680e7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400680ee  lea     r15, WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids
0x1400680f5  jz      short loc_14006812B
0x1400680f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400680fe  cmp     byte ptr [rcx+29h], 5
0x140068102  jb      loc_140068194
0x140068108  mov     rcx, [rcx+40h]
0x14006810c  mov     r9d, 3Eh ; '>'
0x140068112  mov     dl, 5
0x140068114  mov     [rsp+58h+var_38], r15
0x140068119  lea     r8d, [r9-3Dh]
0x14006811d  call    WPP_RECORDER_SF_
0x140068122  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140068129  jnz     short loc_140068171
0x14006812b  mov     rdx, rdi; void *
0x14006812e  call    ?GetAdapterFromAdapterContext@CWdiDriver@@QEAAPEAVCAdapter@@PEAX@Z; CWdiDriver::GetAdapterFromAdapterContext(void *)
0x140068133  mov     rbx, rax
0x140068136  cmp     [rax+0DF8h], esi
0x14006813c  jz      short loc_14006815C
0x14006813e  mov     rcx, [rax+68h]
0x140068142  mov     rax, [rcx+138h]
0x140068149  test    rax, rax
0x14006814c  jz      short loc_14006819F
0x14006814e  mov     rcx, rdi
0x140068151  call    _guard_dispatch_icall
0x140068156  mov     [rbx+0DF8h], esi
0x14006815c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140068163  jnz     short loc_1400681DD
0x140068165  add     rsp, 30h
0x140068169  pop     r15
0x14006816b  pop     rdi
0x14006816c  pop     rsi
0x14006816d  pop     rbp
0x14006816e  pop     rbx
0x14006816f  retn
0x140068171  mov     rcx, cs:WPP_GLOBAL_Control
0x140068178  mov     r9d, 3Fh ; '?'
0x14006817e  mov     dl, 4
0x140068180  mov     [rsp+58h+var_38], r15
0x140068185  mov     rcx, [rcx+40h]
0x140068189  lea     r8d, [r9-3Eh]
0x14006818d  call    WPP_RECORDER_SF_
0x140068192  jmp     short loc_14006812B
0x140068194  cmp     [rcx+48h], si
0x140068198  jz      short loc_140068122
0x14006819a  jmp     loc_140068108
0x14006819f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400681a6  jnz     short loc_1400681BA
0x1400681a8  mov     rcx, [rbx+58h]
0x1400681ac  call    cs:__imp_NdisMIdleNotificationComplete
0x1400681b3  nop     dword ptr [rax+rax+00h]
0x1400681b8  jmp     short loc_140068156
0x1400681ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400681c1  mov     r9d, 40h ; '@'
0x1400681c7  mov     dl, 4
0x1400681c9  mov     [rsp+58h+var_38], r15
0x1400681ce  mov     rcx, [rcx+40h]
0x1400681d2  lea     r8d, [r9-3Fh]
0x1400681d6  call    WPP_RECORDER_SF_
0x1400681db  jmp     short loc_1400681A8
0x1400681dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400681e4  cmp     byte ptr [rcx+29h], 5
0x1400681e8  jnb     short loc_1400681F4
0x1400681ea  cmp     [rcx+48h], si
0x1400681ee  jz      loc_140068165
0x1400681f4  mov     rcx, [rcx+40h]
0x1400681f8  mov     r9d, 41h ; 'A'
0x1400681fe  mov     [rsp+58h+var_30], esi
0x140068202  mov     dl, 5
0x140068204  mov     [rsp+58h+var_38], r15
0x140068209  lea     r8d, [r9-40h]
0x14006820d  call    WPP_RECORDER_SF_D
0x140068212  jmp     loc_140068165
```

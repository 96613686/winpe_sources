# UeIdleNotificationCompleteHandler(void *)

- ea: `0x1400a0460`
- end: `0x1400a0553`
- name: `?UeIdleNotificationCompleteHandler@@YAXPEAX@Z`
- size: `243`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002020`
- `0x140034e04`
- `0x140034ec4`
- `0x1400a0460`

## import_xrefs

- `NDIS!NdisMIdleNotificationComplete` at `0x1400a0502`
- `NDIS!NdisMIdleNotificationComplete` at `0x1400a0502`

## pseudocode

```c
void __fastcall UeIdleNotificationCompleteHandler(CWdiDriver *a1)
{
  CWdiDriver *v1; // rbx
  struct CAdapter *AdapterFromAdapterHandle; // rax
  int v3; // edx
  int v4; // [rsp+28h] [rbp-30h]

  v1 = a1;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    a1 = (CWdiDriver *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        69,
        (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      a1 = (CWdiDriver *)WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          1,
          70,
          (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids);
    }
  }
  AdapterFromAdapterHandle = CWdiDriver::GetAdapterFromAdapterHandle(a1, v1);
  if ( AdapterFromAdapterHandle->m_UsbIdleState )
  {
    AdapterFromAdapterHandle->m_UsbIdleState = WdiUsbIdleStateInit;
    NdisMIdleNotificationComplete(v1);
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v4 = 0;
    LOBYTE(v3) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      1,
      71,
      (__int64)WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x1400a0460  push    rbx
0x1400a0462  push    rbp
0x1400a0463  push    rdi
0x1400a0464  push    r15
0x1400a0466  sub     rsp, 38h
0x1400a046a  mov     rbx, rcx
0x1400a046d  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a0474  xor     edi, edi
0x1400a0476  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400a047d  lea     r15, WPP_c2f745067e8a3b9b8e989688fcfeb619_Traceguids
0x1400a0484  jz      short loc_1400A04E9
0x1400a0486  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a048d  cmp     byte ptr [rcx+29h], 5
0x1400a0491  jnb     short loc_1400A0499
0x1400a0493  cmp     [rcx+48h], di
0x1400a0497  jz      short loc_1400A04B3
0x1400a0499  mov     rcx, [rcx+40h]
0x1400a049d  mov     r9d, 45h ; 'E'
0x1400a04a3  mov     dl, 5
0x1400a04a5  mov     [rsp+58h+var_38], r15
0x1400a04aa  lea     r8d, [r9-44h]
0x1400a04ae  call    WPP_RECORDER_SF_
0x1400a04b3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400a04ba  jz      short loc_1400A04E9
0x1400a04bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a04c3  cmp     byte ptr [rcx+29h], 5
0x1400a04c7  jnb     short loc_1400A04CF
0x1400a04c9  cmp     [rcx+48h], di
0x1400a04cd  jz      short loc_1400A04E9
0x1400a04cf  mov     rcx, [rcx+40h]
0x1400a04d3  mov     r9d, 46h ; 'F'
0x1400a04d9  mov     dl, 5
0x1400a04db  mov     [rsp+58h+var_38], r15
0x1400a04e0  lea     r8d, [r9-45h]
0x1400a04e4  call    WPP_RECORDER_SF_
0x1400a04e9  mov     rdx, rbx; void *
0x1400a04ec  call    ?GetAdapterFromAdapterHandle@CWdiDriver@@QEAAPEAVCAdapter@@PEAX@Z; CWdiDriver::GetAdapterFromAdapterHandle(void *)
0x1400a04f1  cmp     [rax+0DF8h], edi
0x1400a04f7  jz      short loc_1400A050E
0x1400a04f9  mov     rcx, rbx
0x1400a04fc  mov     [rax+0DF8h], edi
0x1400a0502  call    cs:__imp_NdisMIdleNotificationComplete
0x1400a0509  nop     dword ptr [rax+rax+00h]
0x1400a050e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400a0515  jz      short loc_1400A0548
0x1400a0517  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a051e  cmp     byte ptr [rcx+29h], 5
0x1400a0522  jnb     short loc_1400A052A
0x1400a0524  cmp     [rcx+48h], di
0x1400a0528  jz      short loc_1400A0548
0x1400a052a  mov     rcx, [rcx+40h]
0x1400a052e  mov     r9d, 47h ; 'G'
0x1400a0534  mov     [rsp+58h+var_30], edi
0x1400a0538  mov     dl, 5
0x1400a053a  mov     [rsp+58h+var_38], r15
0x1400a053f  lea     r8d, [r9-46h]
0x1400a0543  call    WPP_RECORDER_SF_D
0x1400a0548  add     rsp, 38h
0x1400a054c  pop     r15
0x1400a054e  pop     rdi
0x1400a054f  pop     rbp
0x1400a0550  pop     rbx
0x1400a0551  retn
```

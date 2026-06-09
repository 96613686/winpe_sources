# CameraControlNotificationMonitor::SetErrorState(long)

- ea: `0x180065594`
- end: `0x180065662`
- name: `?SetErrorState@CameraControlNotificationMonitor@@AEAAXJ@Z`
- size: `206`
- prototype: `void(CameraControlNotificationMonitor *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064f1c`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180065594`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateMediaEvent` at `0x1800655ee`
- `MFPlat!MFCreateMediaEvent` at `0x1800655ee`
- `MFPlat!MFPutWorkItem` at `0x180065617`
- `MFPlat!MFPutWorkItem` at `0x180065617`

## pseudocode

```c
void __fastcall CameraControlNotificationMonitor::SetErrorState(CameraControlNotificationMonitor *this, HRESULT a2)
{
  IMFMediaEvent *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rdx
  IMFMediaEvent *ppEvent; // [rsp+40h] [rbp+8h] BYREF

  ppEvent = 0;
  _InterlockedExchange((volatile __int32 *)this + 49, -1);
  v4 = ppEvent;
  ppEvent = 0;
  if ( v4 )
    ((void (__fastcall *)(IMFMediaEvent *))v4->lpVtbl->Release)(v4);
  v5 = MFCreateMediaEvent(1u, &GUID_00000000_0000_0000_0000_000000000000, a2, 0, &ppEvent);
  if ( v5 >= 0 )
  {
    v5 = MFPutWorkItem(*((_DWORD *)this + 34), (IMFAsyncCallback *)this + 2, (IUnknown *)ppEvent);
    if ( v5 < 0 && g_wppLevels )
    {
      v6 = 77;
      goto LABEL_9;
    }
  }
  else if ( g_wppLevels )
  {
    v6 = 76;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_baf6de1ba3ee357d741c4ed31a2f3d4c_Traceguids, this, v5);
  }
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppEvent);
}

```

## disassembly

```asm
0x180065594  mov     r11, rsp
0x180065597  mov     [r11+10h], rbx
0x18006559b  push    rdi
0x18006559c  sub     rsp, 30h
0x1800655a0  mov     qword ptr [r11+8], 0
0x1800655a8  or      eax, 0FFFFFFFFh
0x1800655ab  xchg    eax, [rcx+0C4h]
0x1800655b1  mov     rbx, rcx
0x1800655b4  mov     edi, edx
0x1800655b6  mov     rcx, [r11+8]
0x1800655ba  mov     qword ptr [r11+8], 0
0x1800655c2  test    rcx, rcx
0x1800655c5  jz      short loc_1800655D3
0x1800655c7  mov     rax, [rcx]
0x1800655ca  mov     rax, [rax+10h]
0x1800655ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655d3  xor     r9d, r9d; pvValue
0x1800655d6  lea     rax, [rsp+38h+arg_0]
0x1800655db  mov     r8d, edi; hrStatus
0x1800655de  mov     [rsp+38h+ppEvent], rax; ppEvent
0x1800655e3  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x1800655ea  lea     ecx, [r9+1]; met
0x1800655ee  call    cs:__imp_MFCreateMediaEvent
0x1800655f4  test    eax, eax
0x1800655f6  jns     short loc_180065608
0x1800655f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800655ff  jb      short loc_18006564D
0x180065601  mov     edx, 4Ch ; 'L'
0x180065606  jmp     short loc_18006562F
0x180065608  mov     r8, [rsp+38h+arg_0]; pState
0x18006560d  lea     rdx, [rbx+10h]; pCallback
0x180065611  mov     ecx, [rbx+88h]; dwQueue
0x180065617  call    cs:__imp_MFPutWorkItem
0x18006561d  test    eax, eax
0x18006561f  jns     short loc_18006564D
0x180065621  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065628  jb      short loc_18006564D
0x18006562a  mov     edx, 4Dh ; 'M'
0x18006562f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065636  lea     r8, WPP_baf6de1ba3ee357d741c4ed31a2f3d4c_Traceguids
0x18006563d  mov     r9, rbx
0x180065640  mov     dword ptr [rsp+38h+ppEvent], eax
0x180065644  mov     rcx, [rcx+10h]
0x180065648  call    WPP_SF_qD
0x18006564d  lea     rcx, [rsp+38h+arg_0]
0x180065652  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180065657  mov     rbx, [rsp+38h+arg_8]
0x18006565c  add     rsp, 30h
0x180065660  pop     rdi
0x180065661  retn
```

# Avdtp_impl::AcquireRemoveLock(Avdtp_impl::RemoveLockClient)

- ea: `0x140046b04`
- end: `0x140046c63`
- name: `?AcquireRemoveLock@Avdtp_impl@@QEAAJW4RemoveLockClient@1@@Z`
- size: `351`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400132a0`
- `0x140019718`
- `0x1400473d0`
- `0x14004891c`

## callees

- `0x140036494`
- `0x14003b244`
- `0x140046b04`
- `0x140055f48`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140046b41`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140046b41`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::AcquireRemoveLock(__int64 a1, int a2)
{
  struct _IO_REMOVE_LOCK *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  bool v11; // r10
  int IfrRecorderLog; // eax
  PDEVICE_OBJECT *v13; // rdx
  bool v14; // r10
  __int64 v15; // r11
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  PVOID DeviceExtension; // r9
  ULONG RemlockSize; // [rsp+20h] [rbp-68h]

  v4 = *(struct _IO_REMOVE_LOCK **)(a1 + 1792);
  v5 = -1073741823;
  if ( v4 )
  {
    v5 = IoAcquireRemoveLockEx(
           v4,
           (PVOID)0x41564454,
           "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\btha2dp\\avdtp\\driver\\avdtp_impl.cpp",
           0x219u,
           0x20u);
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v7, v6, v8, v9) )
    {
      if ( a2 != 2 )
      {
        v11 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          IfrRecorderLog = GetIfrRecorderLog(0, *(_QWORD *)(a1 + 1792), v10);
          AttachedDevice = *(struct _DEVICE_OBJECT **)(v15 + 24);
          LODWORD(DeviceExtension) = IfrRecorderLog;
LABEL_20:
          LOBYTE(v13) = v14;
          WPP_RECORDER_AND_TRACE_SF_l_Avdtp_impl_RemoveLockClient_dq(
            (_DWORD)AttachedDevice,
            (_DWORD)v13,
            v10,
            (_DWORD)DeviceExtension,
            RemlockSize);
        }
      }
    }
    else
    {
      v13 = &WPP_GLOBAL_Control;
      v14 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        goto LABEL_20;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140046b04  push    rbx
0x140046b06  push    rbp
0x140046b07  push    rsi
0x140046b08  push    rdi
0x140046b09  sub     rsp, 68h
0x140046b0d  mov     rdi, rcx
0x140046b10  mov     esi, edx
0x140046b12  mov     rcx, [rcx+700h]; RemoveLock
0x140046b19  mov     ebx, 0C0000001h
0x140046b1e  test    rcx, rcx
0x140046b21  jz      loc_140046C57
0x140046b27  mov     r9d, 219h; Line
0x140046b2d  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x140046b35  lea     r8, File; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x140046b3c  mov     edx, 41564454h; Tag
0x140046b41  call    cs:__imp_IoAcquireRemoveLockEx
0x140046b48  nop     dword ptr [rax+rax+00h]
0x140046b4d  mov     ebx, eax
0x140046b4f  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140046b54  test    eax, eax
0x140046b56  jz      loc_140046BE1
0x140046b5c  cmp     esi, 2
0x140046b5f  jz      loc_140046C57
0x140046b65  mov     r11, cs:WPP_GLOBAL_Control
0x140046b6c  lea     rdx, WPP_GLOBAL_Control
0x140046b73  cmp     r11, rdx
0x140046b76  jz      short loc_140046B8C
0x140046b78  mov     eax, [r11+2Ch]
0x140046b7c  test    al, 8
0x140046b7e  jz      short loc_140046B8C
0x140046b80  cmp     byte ptr [r11+29h], 4
0x140046b85  jb      short loc_140046B8C
0x140046b87  mov     r10b, 1
0x140046b8a  jmp     short loc_140046B8F
0x140046b8c  xor     r10b, r10b
0x140046b8f  lea     rax, WPP_RECORDER_INITIALIZED
0x140046b96  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140046b9d  setnz   r8b
0x140046ba1  test    r10b, r10b
0x140046ba4  jnz     short loc_140046BAF
0x140046ba6  test    r8b, r8b
0x140046ba9  jz      loc_140046C57
0x140046baf  mov     rdx, [rdi+700h]
0x140046bb6  xor     ecx, ecx
0x140046bb8  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140046bbd  mov     rcx, [r11+18h]
0x140046bc1  mov     r9, rax
0x140046bc4  mov     eax, [rdx+4]
0x140046bc7  mov     [rsp+88h+var_30], rdi
0x140046bcc  mov     [rsp+88h+var_38], ebx
0x140046bd0  mov     [rsp+88h+var_40], esi
0x140046bd4  mov     [rsp+88h+var_48], eax
0x140046bd8  mov     [rsp+88h+var_58], 11h
0x140046bdf  jmp     short loc_140046C4F
0x140046be1  mov     rcx, cs:WPP_GLOBAL_Control
0x140046be8  lea     rdx, WPP_GLOBAL_Control
0x140046bef  cmp     rcx, rdx
0x140046bf2  jz      short loc_140046C06
0x140046bf4  mov     eax, [rcx+2Ch]
0x140046bf7  test    al, 8
0x140046bf9  jz      short loc_140046C06
0x140046bfb  cmp     byte ptr [rcx+29h], 4
0x140046bff  jb      short loc_140046C06
0x140046c01  mov     r10b, 1
0x140046c04  jmp     short loc_140046C09
0x140046c06  xor     r10b, r10b
0x140046c09  lea     rax, WPP_RECORDER_INITIALIZED
0x140046c10  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140046c17  setnz   r8b
0x140046c1b  test    r10b, r10b
0x140046c1e  jnz     short loc_140046C25
0x140046c20  test    r8b, r8b
0x140046c23  jz      short loc_140046C57
0x140046c25  mov     rax, [rdi+700h]
0x140046c2c  mov     r9, [rcx+40h]
0x140046c30  mov     rcx, [rcx+18h]
0x140046c34  mov     [rsp+88h+var_30], rdi
0x140046c39  mov     eax, [rax+4]
0x140046c3c  mov     [rsp+88h+var_38], ebx
0x140046c40  mov     [rsp+88h+var_40], esi
0x140046c44  mov     [rsp+88h+var_48], eax
0x140046c48  mov     [rsp+88h+var_58], 12h
0x140046c4f  mov     dl, r10b
0x140046c52  call    WPP_RECORDER_AND_TRACE_SF_l_Avdtp_impl_RemoveLockClient_dq
0x140046c57  mov     eax, ebx
0x140046c59  add     rsp, 68h
0x140046c5d  pop     rdi
0x140046c5e  pop     rsi
0x140046c5f  pop     rbp
0x140046c60  pop     rbx
0x140046c61  retn
```

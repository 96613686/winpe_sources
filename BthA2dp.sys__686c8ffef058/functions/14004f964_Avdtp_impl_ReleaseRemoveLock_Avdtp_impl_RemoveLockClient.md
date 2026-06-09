# Avdtp_impl::ReleaseRemoveLock(Avdtp_impl::RemoveLockClient)

- ea: `0x14004f964`
- end: `0x14004fab0`
- name: `?ReleaseRemoveLock@Avdtp_impl@@QEAAXW4RemoveLockClient@1@@Z`
- size: `332`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400132a0`
- `0x140019718`
- `0x140019c50`
- `0x1400473d0`

## callees

- `0x140036494`
- `0x14003b244`
- `0x14004f964`
- `0x140056048`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14004f993`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14004f993`

## pseudocode

```c
void __fastcall Avdtp_impl::ReleaseRemoveLock(__int64 a1, int a2)
{
  struct _IO_REMOVE_LOCK *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // edx
  __int64 v10; // r8
  bool v11; // r10
  int IfrRecorderLog; // eax
  bool v13; // r10
  __int64 v14; // r11
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  PVOID DeviceExtension; // r9

  v4 = *(struct _IO_REMOVE_LOCK **)(a1 + 1792);
  if ( v4 )
  {
    IoReleaseRemoveLockEx(v4, (PVOID)0x41564454, 0x20u);
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v6, v5, v7, v8) )
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
          AttachedDevice = *(struct _DEVICE_OBJECT **)(v14 + 24);
          LODWORD(DeviceExtension) = IfrRecorderLog;
LABEL_20:
          LOBYTE(v9) = v13;
          WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq((_DWORD)AttachedDevice, v9, v10, (_DWORD)DeviceExtension);
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        goto LABEL_20;
      }
    }
  }
}

```

## disassembly

```asm
0x14004f964  mov     [rsp+arg_0], rbx
0x14004f969  mov     [rsp+arg_8], rsi
0x14004f96e  push    rdi
0x14004f96f  sub     rsp, 60h
0x14004f973  mov     rbx, rcx
0x14004f976  mov     edi, edx
0x14004f978  mov     rcx, [rcx+700h]; RemoveLock
0x14004f97f  test    rcx, rcx
0x14004f982  jz      loc_14004FA9F
0x14004f988  mov     edx, 41564454h; Tag
0x14004f98d  mov     r8d, 20h ; ' '; RemlockSize
0x14004f993  call    cs:__imp_IoReleaseRemoveLockEx
0x14004f99a  nop     dword ptr [rax+rax+00h]
0x14004f99f  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004f9a4  test    eax, eax
0x14004f9a6  jz      loc_14004FA2D
0x14004f9ac  cmp     edi, 2
0x14004f9af  jz      loc_14004FA9F
0x14004f9b5  mov     r11, cs:WPP_GLOBAL_Control
0x14004f9bc  lea     rax, WPP_GLOBAL_Control
0x14004f9c3  cmp     r11, rax
0x14004f9c6  jz      short loc_14004F9DC
0x14004f9c8  mov     eax, [r11+2Ch]
0x14004f9cc  test    al, 8
0x14004f9ce  jz      short loc_14004F9DC
0x14004f9d0  cmp     byte ptr [r11+29h], 4
0x14004f9d5  jb      short loc_14004F9DC
0x14004f9d7  mov     r10b, 1
0x14004f9da  jmp     short loc_14004F9DF
0x14004f9dc  xor     r10b, r10b
0x14004f9df  lea     rax, WPP_RECORDER_INITIALIZED
0x14004f9e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004f9ed  setnz   r8b
0x14004f9f1  test    r10b, r10b
0x14004f9f4  jnz     short loc_14004F9FF
0x14004f9f6  test    r8b, r8b
0x14004f9f9  jz      loc_14004FA9F
0x14004f9ff  mov     rdx, [rbx+700h]
0x14004fa06  xor     ecx, ecx
0x14004fa08  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004fa0d  mov     rcx, [r11+18h]
0x14004fa11  mov     r9, rax
0x14004fa14  mov     eax, [rdx+4]
0x14004fa17  mov     [rsp+68h+var_18], rbx
0x14004fa1c  mov     [rsp+68h+var_20], edi
0x14004fa20  mov     [rsp+68h+var_28], eax
0x14004fa24  mov     [rsp+68h+var_38], 14h
0x14004fa2b  jmp     short loc_14004FA97
0x14004fa2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa34  lea     rax, WPP_GLOBAL_Control
0x14004fa3b  cmp     rcx, rax
0x14004fa3e  jz      short loc_14004FA52
0x14004fa40  mov     eax, [rcx+2Ch]
0x14004fa43  test    al, 8
0x14004fa45  jz      short loc_14004FA52
0x14004fa47  cmp     byte ptr [rcx+29h], 4
0x14004fa4b  jb      short loc_14004FA52
0x14004fa4d  mov     r10b, 1
0x14004fa50  jmp     short loc_14004FA55
0x14004fa52  xor     r10b, r10b
0x14004fa55  lea     rax, WPP_RECORDER_INITIALIZED
0x14004fa5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004fa63  setnz   r8b
0x14004fa67  test    r10b, r10b
0x14004fa6a  jnz     short loc_14004FA71
0x14004fa6c  test    r8b, r8b
0x14004fa6f  jz      short loc_14004FA9F
0x14004fa71  mov     rax, [rbx+700h]
0x14004fa78  mov     r9, [rcx+40h]
0x14004fa7c  mov     rcx, [rcx+18h]
0x14004fa80  mov     [rsp+68h+var_18], rbx
0x14004fa85  mov     eax, [rax+4]
0x14004fa88  mov     [rsp+68h+var_20], edi
0x14004fa8c  mov     [rsp+68h+var_28], eax
0x14004fa90  mov     [rsp+68h+var_38], 15h
0x14004fa97  mov     dl, r10b
0x14004fa9a  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq
0x14004fa9f  mov     rbx, [rsp+68h+arg_0]
0x14004faa4  mov     rsi, [rsp+68h+arg_8]
0x14004faa9  add     rsp, 60h
0x14004faad  pop     rdi
0x14004faae  retn
```

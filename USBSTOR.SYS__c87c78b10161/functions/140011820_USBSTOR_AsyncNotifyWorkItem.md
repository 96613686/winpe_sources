# USBSTOR_AsyncNotifyWorkItem

- ea: `0x140011820`
- end: `0x1400118f8`
- name: `USBSTOR_AsyncNotifyWorkItem`
- size: `216`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140003630`
- `0x140010664`
- `0x140011820`
- `0x140011c10`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400118db`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400118db`

## pseudocode

```c
void __fastcall USBSTOR_AsyncNotifyWorkItem(struct _DEVICE_OBJECT *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  char *DeviceExtension; // rdi
  int v5; // eax

  USBSTOR_LogEntry(1230458433, IoObject, 0, 0);
  DeviceExtension = (char *)IoObject->DeviceExtension;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v5 = USBSTOR_IssueAsyncNotificationRequest(IoObject);
  USBSTOR_LogEntry(1769434721, IoObject, v5, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), USBSTOR_AsyncNotifyWorkItem, 0x20u);
}

```

## disassembly

```asm
0x140011820  mov     [rsp+arg_0], rbx
0x140011825  mov     [rsp+arg_8], rsi
0x14001182a  push    rdi
0x14001182b  sub     rsp, 20h
0x14001182f  mov     rbx, rcx
0x140011832  mov     rdx, rcx
0x140011835  mov     ecx, 49574E41h
0x14001183a  xor     r9d, r9d
0x14001183d  xor     r8d, r8d
0x140011840  call    USBSTOR_LogEntry
0x140011845  mov     rdi, [rbx+40h]
0x140011849  mov     rcx, cs:WPP_GLOBAL_Control
0x140011850  lea     rsi, WPP_GLOBAL_Control
0x140011857  cmp     rcx, rsi
0x14001185a  jz      short loc_14001187E
0x14001185c  mov     eax, [rcx+2Ch]
0x14001185f  test    al, 1
0x140011861  jz      short loc_14001187E
0x140011863  cmp     byte ptr [rcx+29h], 5
0x140011867  jb      short loc_14001187E
0x140011869  mov     rcx, [rcx+18h]
0x14001186d  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140011874  mov     edx, 8Eh
0x140011879  call    WPP_SF_
0x14001187e  mov     rcx, rbx; Context
0x140011881  call    USBSTOR_IssueAsyncNotificationRequest
0x140011886  movsxd  r8, eax
0x140011889  xor     r9d, r9d
0x14001188c  mov     rdx, rbx
0x14001188f  mov     ecx, 69776E61h
0x140011894  call    USBSTOR_LogEntry
0x140011899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118a0  cmp     rcx, rsi
0x1400118a3  jz      short loc_1400118C7
0x1400118a5  mov     eax, [rcx+2Ch]
0x1400118a8  test    al, 1
0x1400118aa  jz      short loc_1400118C7
0x1400118ac  cmp     byte ptr [rcx+29h], 5
0x1400118b0  jb      short loc_1400118C7
0x1400118b2  mov     rcx, [rcx+18h]
0x1400118b6  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400118bd  mov     edx, 8Fh
0x1400118c2  call    WPP_SF_
0x1400118c7  lea     rcx, [rdi+728h]; RemoveLock
0x1400118ce  mov     r8d, 20h ; ' '; RemlockSize
0x1400118d4  lea     rdx, USBSTOR_AsyncNotifyWorkItem; Tag
0x1400118db  call    cs:__imp_IoReleaseRemoveLockEx
0x1400118e2  nop     dword ptr [rax+rax+00h]
0x1400118e7  mov     rbx, [rsp+28h+arg_0]
0x1400118ec  mov     rsi, [rsp+28h+arg_8]
0x1400118f1  add     rsp, 20h
0x1400118f5  pop     rdi
0x1400118f6  retn
```

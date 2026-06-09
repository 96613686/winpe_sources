# WskKnrCreateNameResNamedEvent

- ea: `0x140067f34`
- end: `0x140068186`
- name: `WskKnrCreateNameResNamedEvent`
- size: `594`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140068890`
- `0x1400689f0`

## callees

- `0x140067f34`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14006809e`
- `ntoskrnl!ZwCreateEvent` at `0x14006809e`
- `ntoskrnl!ZwClose` at `0x140068153`
- `ntoskrnl!ZwClose` at `0x140068153`
- `ntoskrnl!RtlInitUnicodeString` at `0x140068053`
- `ntoskrnl!RtlInitUnicodeString` at `0x140068053`
- `ntoskrnl!ObfDereferenceObject` at `0x14006813d`
- `ntoskrnl!ObfDereferenceObject` at `0x14006813d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140068033`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140068129`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140068033`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140068129`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006801e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400680f7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006801e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400680f7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400680d8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400680d8`

## string_xrefs

- `0x140068048`: `\BaseNamedObjects\NameRes_StartCompleted`

## pseudocode

```c
__int64 __fastcall WskKnrCreateNameResNamedEvent(PKSPIN_LOCK SpinLock)
{
  NTSTATUS v2; // esi
  KSPIN_LOCK v3; // rbx
  NTSTATUS v4; // eax
  PVOID v5; // rbx
  void *EventHandle; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Object; // [rsp+38h] [rbp-C8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  int v12; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v13; // [rsp+A4h] [rbp-5Ch]
  int v14; // [rsp+ACh] [rbp-54h]
  int v15; // [rsp+B0h] [rbp-50h]
  int v16; // [rsp+B4h] [rbp-4Ch]
  int v17; // [rsp+B8h] [rbp-48h]
  int v18; // [rsp+BCh] [rbp-44h]
  int v19; // [rsp+C0h] [rbp-40h]
  int v20; // [rsp+C4h] [rbp-3Ch]
  int v21; // [rsp+C8h] [rbp-38h]
  int v22; // [rsp+CCh] [rbp-34h]
  int v23; // [rsp+D0h] [rbp-30h]
  int v24; // [rsp+D4h] [rbp-2Ch]
  int v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+DCh] [rbp-24h]
  int v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+E4h] [rbp-1Ch]
  int v29; // [rsp+E8h] [rbp-18h]
  int v30; // [rsp+ECh] [rbp-14h]
  int v31; // [rsp+F0h] [rbp-10h]
  int v32; // [rsp+F4h] [rbp-Ch]

  v12 = -2147221503;
  v15 = 20;
  EventHandle = 0;
  v13 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = 0;
  v14 = 0;
  DestinationString = 0;
  v16 = 4456450;
  memset(&ObjectAttributes, 0, 44);
  v17 = 2;
  v18 = 1310720;
  v19 = 0x10000000;
  v20 = 257;
  v21 = 83886080;
  v22 = 18;
  v23 = 2621952;
  v24 = 131103;
  v25 = 1537;
  v26 = 83886080;
  v27 = 80;
  v28 = 859482183;
  v29 = 879914841;
  v30 = 863379149;
  v31 = 1145462774;
  v32 = -1906348614;
  KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
  v3 = SpinLock[12];
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !v3 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects\\NameRes_StartCompleted");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.SecurityDescriptor = &v12;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    v2 = ZwCreateEvent(&EventHandle, 0xC0000000, &ObjectAttributes, NotificationEvent, 0);
    if ( v2 >= 0 )
    {
      Object = 0;
      v4 = ObReferenceObjectByHandle(EventHandle, 0x1F0003u, 0, 0, &Object, 0);
      v5 = Object;
      v2 = v4;
      if ( v4 >= 0 )
      {
        KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
        if ( !SpinLock[12] )
        {
          SpinLock[12] = (KSPIN_LOCK)v5;
          v5 = 0;
        }
        if ( !SpinLock[13] )
        {
          SpinLock[13] = (KSPIN_LOCK)EventHandle;
          EventHandle = 0;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( v5 )
        ObfDereferenceObject(v5);
    }
  }
  if ( EventHandle )
    ZwClose(EventHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140067f34  mov     [rsp-8+arg_8], rbx
0x140067f39  mov     [rsp-8+arg_10], rsi
0x140067f3e  push    rbp
0x140067f3f  push    rdi
0x140067f40  push    r14
0x140067f42  lea     rbp, [rsp-10h]
0x140067f47  sub     rsp, 110h
0x140067f4e  mov     rax, cs:__security_cookie
0x140067f55  xor     rax, rsp
0x140067f58  mov     [rbp+20h+var_20], rax
0x140067f5c  xorps   xmm0, xmm0
0x140067f5f  mov     [rbp+20h+var_80], 80040001h
0x140067f66  xor     r14d, r14d
0x140067f69  mov     [rbp+20h+var_70], 14h
0x140067f70  xor     eax, eax
0x140067f72  mov     [rsp+120h+EventHandle], r14
0x140067f77  movups  xmmword ptr [rsp+120h+ObjectAttributes.ObjectName], xmm0
0x140067f7c  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x140067f81  mov     qword ptr [rsp+120h+LockHandle.OldIrql], rax
0x140067f86  movups  xmmword ptr [rsp+120h+ObjectAttributes+1Ch], xmm0
0x140067f8b  mov     rdi, rcx
0x140067f8e  mov     [rbp+20h+var_7C], r14
0x140067f92  movups  xmmword ptr [rsp+120h+LockHandle.LockQueue.Next], xmm0
0x140067f97  mov     esi, r14d
0x140067f9a  mov     [rbp+20h+var_74], r14d
0x140067f9e  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x140067fa2  mov     [rbp+20h+var_6C], 440002h
0x140067fa9  movups  xmmword ptr [rsp+120h+ObjectAttributes.Length], xmm0
0x140067fae  mov     [rbp+20h+var_68], 2
0x140067fb5  mov     [rbp+20h+var_64], 140000h
0x140067fbc  mov     [rbp+20h+var_60], 10000000h
0x140067fc3  mov     [rbp+20h+var_5C], 101h
0x140067fca  mov     [rbp+20h+var_58], 5000000h
0x140067fd1  mov     [rbp+20h+var_54], 12h
0x140067fd8  mov     [rbp+20h+var_50], 280200h
0x140067fdf  mov     [rbp+20h+var_4C], 2001Fh
0x140067fe6  mov     [rbp+20h+var_48], 601h
0x140067fed  mov     [rbp+20h+var_44], 5000000h
0x140067ff4  mov     [rbp+20h+var_40], 50h ; 'P'
0x140067ffb  mov     [rbp+20h+var_3C], 333AA847h
0x140068002  mov     [rbp+20h+var_38], 34726F59h
0x140068009  mov     [rbp+20h+var_34], 33761ECDh
0x140068010  mov     [rbp+20h+var_30], 44465FF6h
0x140068017  mov     [rbp+20h+var_2C], 8E5F6DBAh
0x14006801e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140068025  nop     dword ptr [rax+rax+00h]
0x14006802a  mov     rbx, [rdi+60h]
0x14006802e  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x140068033  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006803a  nop     dword ptr [rax+rax+00h]
0x14006803f  test    rbx, rbx
0x140068042  jnz     loc_140068149
0x140068048  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects\\NameRes_StartComple"...
0x14006804f  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x140068053  call    cs:__imp_RtlInitUnicodeString
0x14006805a  nop     dword ptr [rax+rax+00h]
0x14006805f  lea     rax, [rbp+20h+DestinationString]
0x140068063  mov     [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x14006806b  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x140068070  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x140068075  lea     rax, [rbp+20h+var_80]
0x140068079  mov     [rsp+120h+ObjectAttributes.RootDirectory], r14
0x14006807e  xor     r9d, r9d; EventType
0x140068081  mov     [rsp+120h+ObjectAttributes.SecurityDescriptor], rax
0x140068086  mov     edx, 0C0000000h; DesiredAccess
0x14006808b  mov     [rsp+120h+ObjectAttributes.Attributes], r14d
0x140068090  lea     rcx, [rsp+120h+EventHandle]; EventHandle
0x140068095  mov     [rbp+20h+ObjectAttributes.SecurityQualityOfService], r14
0x140068099  mov     [rsp+120h+InitialState], r14b; InitialState
0x14006809e  call    cs:__imp_ZwCreateEvent
0x1400680a5  nop     dword ptr [rax+rax+00h]
0x1400680aa  mov     esi, eax
0x1400680ac  test    eax, eax
0x1400680ae  js      loc_140068149
0x1400680b4  mov     rcx, [rsp+120h+EventHandle]; Handle
0x1400680b9  lea     rax, [rsp+120h+Object]
0x1400680be  mov     [rsp+120h+HandleInformation], r14; HandleInformation
0x1400680c3  xor     r9d, r9d; AccessMode
0x1400680c6  xor     r8d, r8d; ObjectType
0x1400680c9  mov     qword ptr [rsp+120h+InitialState], rax; Object
0x1400680ce  mov     edx, 1F0003h; DesiredAccess
0x1400680d3  mov     [rsp+120h+Object], r14
0x1400680d8  call    cs:__imp_ObReferenceObjectByHandle
0x1400680df  nop     dword ptr [rax+rax+00h]
0x1400680e4  mov     rbx, [rsp+120h+Object]
0x1400680e9  mov     esi, eax
0x1400680eb  test    eax, eax
0x1400680ed  js      short loc_140068135
0x1400680ef  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x1400680f4  mov     rcx, rdi; SpinLock
0x1400680f7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400680fe  nop     dword ptr [rax+rax+00h]
0x140068103  cmp     [rdi+60h], r14
0x140068107  jnz     short loc_140068110
0x140068109  mov     [rdi+60h], rbx
0x14006810d  mov     ebx, r14d
0x140068110  cmp     [rdi+68h], r14
0x140068114  jnz     short loc_140068124
0x140068116  mov     rax, [rsp+120h+EventHandle]
0x14006811b  mov     [rdi+68h], rax
0x14006811f  mov     [rsp+120h+EventHandle], r14
0x140068124  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x140068129  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140068130  nop     dword ptr [rax+rax+00h]
0x140068135  test    rbx, rbx
0x140068138  jz      short loc_140068149
0x14006813a  mov     rcx, rbx; Object
0x14006813d  call    cs:__imp_ObfDereferenceObject
0x140068144  nop     dword ptr [rax+rax+00h]
0x140068149  mov     rcx, [rsp+120h+EventHandle]; Handle
0x14006814e  test    rcx, rcx
0x140068151  jz      short loc_14006815F
0x140068153  call    cs:__imp_ZwClose
0x14006815a  nop     dword ptr [rax+rax+00h]
0x14006815f  mov     eax, esi
0x140068161  mov     rcx, [rbp+20h+var_20]
0x140068165  xor     rcx, rsp; StackCookie
0x140068168  call    __security_check_cookie
0x14006816d  lea     r11, [rsp+120h+var_10]
0x140068175  mov     rbx, [r11+28h]
0x140068179  mov     rsi, [r11+30h]
0x14006817d  mov     rsp, r11
0x140068180  pop     r14
0x140068182  pop     rdi
0x140068183  pop     rbp
0x140068184  retn
```

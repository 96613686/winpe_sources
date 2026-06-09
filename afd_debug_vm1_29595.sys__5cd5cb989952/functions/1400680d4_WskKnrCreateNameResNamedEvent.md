# WskKnrCreateNameResNamedEvent

- ea: `0x1400680d4`
- end: `0x140068326`
- name: `WskKnrCreateNameResNamedEvent`
- size: `594`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140068a30`
- `0x140068b90`

## callees

- `0x1400680d4`
- `0x140072840`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14006823e`
- `ntoskrnl!ZwCreateEvent` at `0x14006823e`
- `ntoskrnl!ZwClose` at `0x1400682f3`
- `ntoskrnl!ZwClose` at `0x1400682f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400681f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400681f3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400682dd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400682dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400681d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400682c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400681d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400682c9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400681be`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140068297`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400681be`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140068297`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140068278`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140068278`

## string_xrefs

- `0x1400681e8`: `\BaseNamedObjects\NameRes_StartCompleted`

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
0x1400680d4  mov     [rsp-8+arg_8], rbx
0x1400680d9  mov     [rsp-8+arg_10], rsi
0x1400680de  push    rbp
0x1400680df  push    rdi
0x1400680e0  push    r14
0x1400680e2  lea     rbp, [rsp-10h]
0x1400680e7  sub     rsp, 110h
0x1400680ee  mov     rax, cs:__security_cookie
0x1400680f5  xor     rax, rsp
0x1400680f8  mov     [rbp+20h+var_20], rax
0x1400680fc  xorps   xmm0, xmm0
0x1400680ff  mov     [rbp+20h+var_80], 80040001h
0x140068106  xor     r14d, r14d
0x140068109  mov     [rbp+20h+var_70], 14h
0x140068110  xor     eax, eax
0x140068112  mov     [rsp+120h+EventHandle], r14
0x140068117  movups  xmmword ptr [rsp+120h+ObjectAttributes.ObjectName], xmm0
0x14006811c  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x140068121  mov     qword ptr [rsp+120h+LockHandle.OldIrql], rax
0x140068126  movups  xmmword ptr [rsp+120h+ObjectAttributes+1Ch], xmm0
0x14006812b  mov     rdi, rcx
0x14006812e  mov     [rbp+20h+var_7C], r14
0x140068132  movups  xmmword ptr [rsp+120h+LockHandle.LockQueue.Next], xmm0
0x140068137  mov     esi, r14d
0x14006813a  mov     [rbp+20h+var_74], r14d
0x14006813e  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x140068142  mov     [rbp+20h+var_6C], 440002h
0x140068149  movups  xmmword ptr [rsp+120h+ObjectAttributes.Length], xmm0
0x14006814e  mov     [rbp+20h+var_68], 2
0x140068155  mov     [rbp+20h+var_64], 140000h
0x14006815c  mov     [rbp+20h+var_60], 10000000h
0x140068163  mov     [rbp+20h+var_5C], 101h
0x14006816a  mov     [rbp+20h+var_58], 5000000h
0x140068171  mov     [rbp+20h+var_54], 12h
0x140068178  mov     [rbp+20h+var_50], 280200h
0x14006817f  mov     [rbp+20h+var_4C], 2001Fh
0x140068186  mov     [rbp+20h+var_48], 601h
0x14006818d  mov     [rbp+20h+var_44], 5000000h
0x140068194  mov     [rbp+20h+var_40], 50h ; 'P'
0x14006819b  mov     [rbp+20h+var_3C], 333AA847h
0x1400681a2  mov     [rbp+20h+var_38], 34726F59h
0x1400681a9  mov     [rbp+20h+var_34], 33761ECDh
0x1400681b0  mov     [rbp+20h+var_30], 44465FF6h
0x1400681b7  mov     [rbp+20h+var_2C], 8E5F6DBAh
0x1400681be  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400681c5  nop     dword ptr [rax+rax+00h]
0x1400681ca  mov     rbx, [rdi+60h]
0x1400681ce  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x1400681d3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400681da  nop     dword ptr [rax+rax+00h]
0x1400681df  test    rbx, rbx
0x1400681e2  jnz     loc_1400682E9
0x1400681e8  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects\\NameRes_StartComple"...
0x1400681ef  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x1400681f3  call    cs:__imp_RtlInitUnicodeString
0x1400681fa  nop     dword ptr [rax+rax+00h]
0x1400681ff  lea     rax, [rbp+20h+DestinationString]
0x140068203  mov     [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x14006820b  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x140068210  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x140068215  lea     rax, [rbp+20h+var_80]
0x140068219  mov     [rsp+120h+ObjectAttributes.RootDirectory], r14
0x14006821e  xor     r9d, r9d; EventType
0x140068221  mov     [rsp+120h+ObjectAttributes.SecurityDescriptor], rax
0x140068226  mov     edx, 0C0000000h; DesiredAccess
0x14006822b  mov     [rsp+120h+ObjectAttributes.Attributes], r14d
0x140068230  lea     rcx, [rsp+120h+EventHandle]; EventHandle
0x140068235  mov     [rbp+20h+ObjectAttributes.SecurityQualityOfService], r14
0x140068239  mov     [rsp+120h+InitialState], r14b; InitialState
0x14006823e  call    cs:__imp_ZwCreateEvent
0x140068245  nop     dword ptr [rax+rax+00h]
0x14006824a  mov     esi, eax
0x14006824c  test    eax, eax
0x14006824e  js      loc_1400682E9
0x140068254  mov     rcx, [rsp+120h+EventHandle]; Handle
0x140068259  lea     rax, [rsp+120h+Object]
0x14006825e  mov     [rsp+120h+HandleInformation], r14; HandleInformation
0x140068263  xor     r9d, r9d; AccessMode
0x140068266  xor     r8d, r8d; ObjectType
0x140068269  mov     qword ptr [rsp+120h+InitialState], rax; Object
0x14006826e  mov     edx, 1F0003h; DesiredAccess
0x140068273  mov     [rsp+120h+Object], r14
0x140068278  call    cs:__imp_ObReferenceObjectByHandle
0x14006827f  nop     dword ptr [rax+rax+00h]
0x140068284  mov     rbx, [rsp+120h+Object]
0x140068289  mov     esi, eax
0x14006828b  test    eax, eax
0x14006828d  js      short loc_1400682D5
0x14006828f  lea     rdx, [rsp+120h+LockHandle]; LockHandle
0x140068294  mov     rcx, rdi; SpinLock
0x140068297  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006829e  nop     dword ptr [rax+rax+00h]
0x1400682a3  cmp     [rdi+60h], r14
0x1400682a7  jnz     short loc_1400682B0
0x1400682a9  mov     [rdi+60h], rbx
0x1400682ad  mov     ebx, r14d
0x1400682b0  cmp     [rdi+68h], r14
0x1400682b4  jnz     short loc_1400682C4
0x1400682b6  mov     rax, [rsp+120h+EventHandle]
0x1400682bb  mov     [rdi+68h], rax
0x1400682bf  mov     [rsp+120h+EventHandle], r14
0x1400682c4  lea     rcx, [rsp+120h+LockHandle]; LockHandle
0x1400682c9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400682d0  nop     dword ptr [rax+rax+00h]
0x1400682d5  test    rbx, rbx
0x1400682d8  jz      short loc_1400682E9
0x1400682da  mov     rcx, rbx; Object
0x1400682dd  call    cs:__imp_ObfDereferenceObject
0x1400682e4  nop     dword ptr [rax+rax+00h]
0x1400682e9  mov     rcx, [rsp+120h+EventHandle]; Handle
0x1400682ee  test    rcx, rcx
0x1400682f1  jz      short loc_1400682FF
0x1400682f3  call    cs:__imp_ZwClose
0x1400682fa  nop     dword ptr [rax+rax+00h]
0x1400682ff  mov     eax, esi
0x140068301  mov     rcx, [rbp+20h+var_20]
0x140068305  xor     rcx, rsp; StackCookie
0x140068308  call    __security_check_cookie
0x14006830d  lea     r11, [rsp+120h+var_10]
0x140068315  mov     rbx, [r11+28h]
0x140068319  mov     rsi, [r11+30h]
0x14006831d  mov     rsp, r11
0x140068320  pop     r14
0x140068322  pop     rdi
0x140068323  pop     rbp
0x140068324  retn
```

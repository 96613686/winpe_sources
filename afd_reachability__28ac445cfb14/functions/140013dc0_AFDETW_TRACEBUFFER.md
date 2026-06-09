# AFDETW_TRACEBUFFER

- ea: `0x140013dc0`
- end: `0x1400140fa`
- name: `AFDETW_TRACEBUFFER`
- size: `826`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008210`
- `0x14000a020`
- `0x14000d7f0`
- `0x140013a20`
- `0x140013c60`
- `0x140022d50`
- `0x1400277f0`
- `0x140029e10`
- `0x14003b9e0`
- `0x140053710`

## callees

- `0x140013990`
- `0x140013dc0`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140013f14`
- `ntoskrnl!EtwWriteTransfer` at `0x140014047`
- `ntoskrnl!EtwWriteTransfer` at `0x140013f14`
- `ntoskrnl!EtwWriteTransfer` at `0x140014047`
- `ntoskrnl!EtwWrite` at `0x140013fd2`
- `ntoskrnl!EtwWrite` at `0x1400140b4`
- `ntoskrnl!EtwWrite` at `0x140013fd2`
- `ntoskrnl!EtwWrite` at `0x1400140b4`

## pseudocode

```c
int __fastcall AFDETW_TRACEBUFFER(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int result; // eax
  int v7; // [rsp+30h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-31h] BYREF
  GUID RelatedActivityId; // [rsp+48h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-11h] BYREF
  int *v11; // [rsp+68h] [rbp-1h]
  __int64 v12; // [rsp+70h] [rbp+7h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp+Fh] BYREF
  int *v14; // [rsp+88h] [rbp+1Fh]
  __int64 v15; // [rsp+90h] [rbp+27h]

  if ( !g_AfdEtwTraceEnable )
  {
    result = Microsoft_Windows_Networking_CorrelationEnabled;
    if ( !Microsoft_Windows_Networking_CorrelationEnabled )
      return result;
  }
  *(_QWORD *)RelatedActivityId.Data4 = 0;
  if ( !a4 )
  {
    if ( !a2 )
    {
      if ( g_AfdEtwTraceEnable )
      {
        result = Microsoft_Windows_Networking_CorrelationEnabled;
        *(_QWORD *)ActivityId.Data4 = 0;
        *(_QWORD *)&ActivityId.Data1 = a3;
        if ( Microsoft_Windows_Networking_CorrelationEnabled )
          return EtwEx_tidActivityInfo(a1, &ActivityStart, &ActivityId);
      }
      return result;
    }
    goto LABEL_14;
  }
  *(_QWORD *)ActivityId.Data4 = 0;
  *(_QWORD *)&ActivityId.Data1 = a3;
  *(_QWORD *)&RelatedActivityId.Data1 = a4;
  if ( g_AfdEtwTraceEnable && Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v7 = 3;
    if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    {
      *(_QWORD *)&EventDescriptor.Id = &Microsoft_Windows_Networking_ProviderId;
      v14 = &v7;
      EventDescriptor.Keyword = 16;
      v15 = 4;
      EtwWrite(
        Microsoft_Windows_Networking_CorrelationHandle,
        &ActivityStart,
        &ActivityId,
        2u,
        (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
    }
    else
    {
      EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStart, &ActivityId, 0, 0);
    }
  }
  result = Microsoft_Windows_Networking_CorrelationEnabled;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
    v7 = 3;
    EventDescriptor.Keyword = 0x8000000000000001uLL;
    if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
    {
      UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
      v11 = &v7;
      *(_QWORD *)&UserData.Size = 16;
      v12 = 4;
      result = EtwWriteTransfer(
                 Microsoft_Windows_Networking_CorrelationHandle,
                 &EventDescriptor,
                 &ActivityId,
                 &RelatedActivityId,
                 2u,
                 &UserData);
    }
    else
    {
      result = EtwWriteTransfer(
                 Microsoft_Windows_Networking_CorrelationHandle,
                 &EventDescriptor,
                 &ActivityId,
                 &RelatedActivityId,
                 0,
                 0);
    }
  }
  if ( a2 )
  {
LABEL_14:
    result = Microsoft_Windows_Networking_CorrelationEnabled;
    *(_QWORD *)ActivityId.Data4 = 0;
    *(_QWORD *)&ActivityId.Data1 = a2;
    *(_QWORD *)RelatedActivityId.Data4 = 0;
    *(_QWORD *)&RelatedActivityId.Data1 = a3;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
      v7 = 4;
      EventDescriptor.Keyword = 0x8000000000000001uLL;
      if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
      {
        UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
        v11 = &v7;
        *(_QWORD *)&UserData.Size = 16;
        v12 = 4;
        result = EtwWriteTransfer(
                   Microsoft_Windows_Networking_CorrelationHandle,
                   &EventDescriptor,
                   &ActivityId,
                   &RelatedActivityId,
                   2u,
                   &UserData);
      }
      else
      {
        result = EtwWriteTransfer(
                   Microsoft_Windows_Networking_CorrelationHandle,
                   &EventDescriptor,
                   &ActivityId,
                   &RelatedActivityId,
                   0,
                   0);
      }
    }
    if ( g_AfdEtwTraceEnable )
    {
      result = Microsoft_Windows_Networking_CorrelationEnabled;
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v7 = 3;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
          v11 = &v7;
          *(_QWORD *)&UserData.Size = 16;
          v12 = 4;
          return EtwWrite(
                   Microsoft_Windows_Networking_CorrelationHandle,
                   &ActivityStop,
                   &RelatedActivityId,
                   2u,
                   &UserData);
        }
        else
        {
          return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStop, &RelatedActivityId, 0, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013dc0  push    rbp
0x140013dc2  push    rbx
0x140013dc3  push    rdi
0x140013dc4  lea     rbp, [rsp-47h]
0x140013dc9  sub     rsp, 0B0h
0x140013dd0  mov     rax, cs:__security_cookie
0x140013dd7  xor     rax, rsp
0x140013dda  mov     [rbp+57h+var_28], rax
0x140013dde  cmp     cs:g_AfdEtwTraceEnable, 0
0x140013de5  mov     rdi, r8
0x140013de8  mov     rbx, rdx
0x140013deb  jnz     short loc_140013E0F
0x140013ded  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140013df3  test    eax, eax
0x140013df5  jnz     short loc_140013E0F
0x140013df7  mov     rcx, [rbp+57h+var_28]
0x140013dfb  xor     rcx, rsp; StackCookie
0x140013dfe  call    __security_check_cookie
0x140013e03  add     rsp, 0B0h
0x140013e0a  pop     rdi
0x140013e0b  pop     rbx
0x140013e0c  pop     rbp
0x140013e0d  retn
0x140013e0f  mov     [rsp+0C0h+arg_0], rsi
0x140013e17  mov     [rsp+0C0h+var_18], r14
0x140013e1f  mov     [rsp+0C0h+var_20], r15
0x140013e27  xor     r15d, r15d
0x140013e2a  mov     qword ptr [rbp+57h+RelatedActivityId.Data4], r15
0x140013e2e  test    r9, r9
0x140013e31  jnz     short loc_140013E7C
0x140013e33  test    rbx, rbx
0x140013e36  jnz     loc_140013F42
0x140013e3c  cmp     cs:g_AfdEtwTraceEnable, r15d
0x140013e43  jz      loc_140013F25
0x140013e49  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140013e4f  mov     qword ptr [rbp+57h+ActivityId.Data4], r15
0x140013e53  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x140013e57  test    eax, eax
0x140013e59  jz      loc_140013F25
0x140013e5f  lea     r8, [rbp+57h+ActivityId]
0x140013e63  mov     [rsp+0C0h+UserDataCount], 3
0x140013e6b  lea     rdx, ActivityStart
0x140013e72  call    EtwEx_tidActivityInfo
0x140013e77  jmp     loc_140013F25
0x140013e7c  cmp     cs:g_AfdEtwTraceEnable, r15d
0x140013e83  lea     r14, Microsoft_Windows_Networking_ProviderId
0x140013e8a  mov     qword ptr [rbp+57h+ActivityId.Data4], r15
0x140013e8e  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x140013e92  mov     qword ptr [rbp+57h+RelatedActivityId.Data1], r9
0x140013e96  jnz     loc_140014058
0x140013e9c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140013ea2  mov     rsi, 8000000000000001h
0x140013eac  test    eax, eax
0x140013eae  jz      short loc_140013F20
0x140013eb0  mov     rax, cs:ActivityTransfer
0x140013eb7  lea     r9, [rbp+57h+RelatedActivityId]; RelatedActivityId
0x140013ebb  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140013ec2  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x140013ec6  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x140013eca  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140013ece  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140013ed4  mov     [rbp+57h+var_90], 3
0x140013edb  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140013edf  test    eax, eax
0x140013ee1  jz      loc_1400140D4
0x140013ee7  lea     rax, [rbp+57h+var_90]
0x140013eeb  mov     [rbp+57h+var_68.Ptr], r14
0x140013eef  mov     [rbp+57h+var_58], rax
0x140013ef3  lea     rax, [rbp+57h+var_68]
0x140013ef7  mov     [rsp+0C0h+UserData], rax; UserData
0x140013efc  mov     [rsp+0C0h+UserDataCount], 2; UserDataCount
0x140013f04  mov     qword ptr [rbp+57h+var_68.Size], 10h
0x140013f0c  mov     [rbp+57h+var_50], 4
0x140013f14  call    cs:__imp_EtwWriteTransfer
0x140013f1b  nop     dword ptr [rax+rax+00h]
0x140013f20  test    rbx, rbx
0x140013f23  jnz     short loc_140013F53
0x140013f25  mov     r14, [rsp+0C0h+var_18]
0x140013f2d  mov     rsi, [rsp+0C0h+arg_0]
0x140013f35  mov     r15, [rsp+0C0h+var_20]
0x140013f3d  jmp     loc_140013DF7
0x140013f42  lea     r14, Microsoft_Windows_Networking_ProviderId
0x140013f49  mov     rsi, 8000000000000001h
0x140013f53  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140013f59  mov     qword ptr [rbp+57h+ActivityId.Data4], r15
0x140013f5d  mov     qword ptr [rbp+57h+ActivityId.Data1], rbx
0x140013f61  mov     qword ptr [rbp+57h+RelatedActivityId.Data4], r15
0x140013f65  mov     qword ptr [rbp+57h+RelatedActivityId.Data1], rdi
0x140013f69  test    eax, eax
0x140013f6b  jnz     short loc_140013FE3
0x140013f6d  cmp     cs:g_AfdEtwTraceEnable, r15d
0x140013f74  jz      short loc_140013F25
0x140013f76  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140013f7c  test    eax, eax
0x140013f7e  jz      short loc_140013F25
0x140013f80  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140013f86  lea     r8, [rbp+57h+RelatedActivityId]; ActivityId
0x140013f8a  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140013f91  lea     rdx, ActivityStop; EventDescriptor
0x140013f98  mov     [rbp+57h+var_90], 3
0x140013f9f  test    eax, eax
0x140013fa1  jz      loc_1400140E3
0x140013fa7  lea     rax, [rbp+57h+var_90]
0x140013fab  mov     [rbp+57h+var_68.Ptr], r14
0x140013faf  mov     [rbp+57h+var_58], rax
0x140013fb3  mov     r9d, 2; UserDataCount
0x140013fb9  lea     rax, [rbp+57h+var_68]
0x140013fbd  mov     qword ptr [rbp+57h+var_68.Size], 10h
0x140013fc5  mov     qword ptr [rsp+0C0h+UserDataCount], rax; UserData
0x140013fca  mov     [rbp+57h+var_50], 4
0x140013fd2  call    cs:__imp_EtwWrite
0x140013fd9  nop     dword ptr [rax+rax+00h]
0x140013fde  jmp     loc_140013F25
0x140013fe3  mov     rax, cs:ActivityTransfer
0x140013fea  lea     r9, [rbp+57h+RelatedActivityId]; RelatedActivityId
0x140013fee  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140013ff5  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x140013ff9  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x140013ffd  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140014001  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140014007  mov     [rbp+57h+var_90], 4
0x14001400e  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140014012  test    eax, eax
0x140014014  jz      loc_1400140C5
0x14001401a  lea     rax, [rbp+57h+var_90]
0x14001401e  mov     [rbp+57h+var_68.Ptr], r14
0x140014022  mov     [rbp+57h+var_58], rax
0x140014026  lea     rax, [rbp+57h+var_68]
0x14001402a  mov     [rsp+0C0h+UserData], rax; UserData
0x14001402f  mov     [rsp+0C0h+UserDataCount], 2; UserDataCount
0x140014037  mov     qword ptr [rbp+57h+var_68.Size], 10h
0x14001403f  mov     [rbp+57h+var_50], 4
0x140014047  call    cs:__imp_EtwWriteTransfer
0x14001404e  nop     dword ptr [rax+rax+00h]
0x140014053  jmp     loc_140013F6D
0x140014058  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001405e  test    eax, eax
0x140014060  jz      loc_140013E9C
0x140014066  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14001406c  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x140014070  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140014077  lea     rdx, ActivityStart; EventDescriptor
0x14001407e  mov     [rbp+57h+var_90], 3
0x140014085  test    eax, eax
0x140014087  jz      short loc_1400140F0
0x140014089  lea     rax, [rbp+57h+var_90]
0x14001408d  mov     qword ptr [rbp+57h+EventDescriptor.Id], r14
0x140014091  mov     [rbp+57h+var_38], rax
0x140014095  mov     r9d, 2; UserDataCount
0x14001409b  lea     rax, [rbp+57h+EventDescriptor]
0x14001409f  mov     [rbp+57h+EventDescriptor.Keyword], 10h
0x1400140a7  mov     qword ptr [rsp+0C0h+UserDataCount], rax; UserData
0x1400140ac  mov     [rbp+57h+var_30], 4
0x1400140b4  call    cs:__imp_EtwWrite
0x1400140bb  nop     dword ptr [rax+rax+00h]
0x1400140c0  jmp     loc_140013E9C
0x1400140c5  mov     [rsp+0C0h+UserData], r15
0x1400140ca  mov     [rsp+0C0h+UserDataCount], r15d
0x1400140cf  jmp     loc_140014047
0x1400140d4  mov     [rsp+0C0h+UserData], r15
0x1400140d9  mov     [rsp+0C0h+UserDataCount], r15d
0x1400140de  jmp     loc_140013F14
0x1400140e3  mov     qword ptr [rsp+0C0h+UserDataCount], r15
0x1400140e8  xor     r9d, r9d
0x1400140eb  jmp     loc_140013FD2
0x1400140f0  mov     qword ptr [rsp+0C0h+UserDataCount], r15
0x1400140f5  xor     r9d, r9d
0x1400140f8  jmp     short loc_1400140B4
```

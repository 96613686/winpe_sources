# CSMBHelperClass::TransferActivityID(void)

- ea: `0x180008b64`
- end: `0x180008c61`
- name: `?TransferActivityID@CSMBHelperClass@@SAJXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008440`
- `0x1800088e0`

## callees

- `0x180008b64`
- `0x18000fc30`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180008c2c`
- `ADVAPI32!EventWriteTransfer` at `0x180008c2c`
- `ADVAPI32!EventActivityIdControl` at `0x180008b8e`
- `ADVAPI32!EventActivityIdControl` at `0x180008b8e`

## pseudocode

```c
__int64 CSMBHelperClass::TransferActivityID(void)
{
  ULONG v0; // eax
  int v2; // [rsp+30h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-48h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-28h] BYREF
  int *v6; // [rsp+68h] [rbp-18h]
  __int64 v7; // [rsp+70h] [rbp-10h]

  ActivityId = 0;
  if ( EventActivityIdControl(1u, &ActivityId) )
    return 2147500037LL;
  if ( !Microsoft_Windows_Networking_CorrelationEnabled )
    return 0;
  *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
  v2 = 1;
  EventDescriptor.Keyword = 0x8000000000000001uLL;
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *(_QWORD *)&UserData.Size = 16;
    UserData.Ptr = (ULONGLONG)Microsoft_Windows_Networking_ProviderId;
    v6 = &v2;
    v7 = 4;
    v0 = EventWriteTransfer(0, &EventDescriptor, &ActivityId, &SMBHC_GUID_ACTIVITY_ID, 2u, &UserData);
  }
  else
  {
    v0 = EventWriteTransfer(0, &EventDescriptor, &ActivityId, &SMBHC_GUID_ACTIVITY_ID, 0, 0);
  }
  return v0 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180008b64  push    rbp
0x180008b66  mov     rbp, rsp
0x180008b69  sub     rsp, 80h
0x180008b70  mov     rax, cs:__security_cookie
0x180008b77  xor     rax, rsp
0x180008b7a  mov     [rbp+var_8], rax
0x180008b7e  xorps   xmm0, xmm0
0x180008b81  lea     rdx, [rbp+ActivityId]; ActivityId
0x180008b85  mov     ecx, 1; ControlCode
0x180008b8a  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180008b8e  call    cs:__imp_EventActivityIdControl
0x180008b94  test    eax, eax
0x180008b96  jnz     loc_180008C47
0x180008b9c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180008ba2  test    eax, eax
0x180008ba4  jz      loc_180008C43
0x180008baa  mov     rax, cs:ActivityTransfer
0x180008bb1  lea     r9, SMBHC_GUID_ACTIVITY_ID; RelatedActivityId
0x180008bb8  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x180008bbc  lea     r8, [rbp+ActivityId]; ActivityId
0x180008bc0  mov     rax, 8000000000000001h
0x180008bca  mov     [rbp+var_50], 1
0x180008bd1  mov     [rbp+EventDescriptor.Keyword], rax
0x180008bd5  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180008bd9  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180008bdf  xor     ecx, ecx; RegHandle
0x180008be1  test    eax, eax
0x180008be3  jz      short loc_180008C1B
0x180008be5  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180008bec  mov     [rbp+var_20], 10h
0x180008bf4  mov     [rbp+var_28], rax
0x180008bf8  lea     rax, [rbp+var_50]
0x180008bfc  mov     [rbp+var_18], rax
0x180008c00  lea     rax, [rbp+var_28]
0x180008c04  mov     [rsp+80h+UserData], rax
0x180008c09  mov     [rsp+80h+UserDataCount], 2
0x180008c11  mov     [rbp+var_10], 4
0x180008c19  jmp     short loc_180008C2C
0x180008c1b  mov     [rsp+80h+UserData], 0; UserData
0x180008c24  mov     [rsp+80h+UserDataCount], 0; UserDataCount
0x180008c2c  call    cs:__imp_EventWriteTransfer
0x180008c32  mov     ecx, eax
0x180008c34  xor     eax, eax
0x180008c36  sub     eax, ecx
0x180008c38  neg     eax
0x180008c3a  sbb     eax, eax
0x180008c3c  and     eax, 80004005h
0x180008c41  jmp     short loc_180008C4C
0x180008c43  xor     eax, eax
0x180008c45  jmp     short loc_180008C4C
0x180008c47  mov     eax, 80004005h
0x180008c4c  mov     rcx, [rbp+var_8]
0x180008c50  xor     rcx, rsp; StackCookie
0x180008c53  call    __security_check_cookie
0x180008c58  add     rsp, 80h
0x180008c5f  pop     rbp
0x180008c60  retn
```

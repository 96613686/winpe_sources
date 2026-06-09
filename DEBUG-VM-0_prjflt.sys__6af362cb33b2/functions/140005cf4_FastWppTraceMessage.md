# FastWppTraceMessage

- ea: `0x140005cf4`
- end: `0x140005e85`
- name: `FastWppTraceMessage`
- size: `401`
- prototype: ``
- caller_count: `59`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d008`
- `0x14000d128`
- `0x14000d26c`
- `0x14000d448`
- `0x14000d5e8`
- `0x14000d754`
- `0x14000d960`
- `0x14000dab0`
- `0x14000dc28`
- `0x14000de28`
- `0x14000e058`
- `0x14000e188`
- `0x14000e384`
- `0x14000e57c`
- `0x14000e7cc`
- `0x14000e9f4`
- `0x14000ec4c`
- `0x14000eda4`
- `0x14000ef78`
- `0x14000f0e8`
- `0x14000f2e4`
- `0x14000f4e4`
- `0x14000f714`
- `0x14000f984`
- `0x14000fc3c`
- `0x14000fdd8`
- `0x140010048`
- `0x140010154`
- `0x140010360`
- `0x140010594`
- `0x1400106ec`
- `0x1400108a4`
- `0x140010a70`
- `0x140010c3c`
- `0x140010e3c`
- `0x140010f1c`
- `0x14001104c`
- `0x140011158`
- `0x14001141c`
- `0x1400115e8`
- `0x1400117e8`
- `0x140011984`
- `0x140011b5c`
- `0x140011d2c`
- `0x140012058`
- `0x1400122d4`
- `0x14001249c`
- `0x140012870`
- `0x140012984`
- `0x140012a98`

## callees

- `0x140005c68`
- `0x140005cf4`
- `0x14000ba20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005e5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005e5d`
- `ntoskrnl!EtwWriteEx` at `0x140005e44`
- `ntoskrnl!EtwWriteEx` at `0x140005e44`
- `ntoskrnl!ExAllocatePool3` at `0x140005dd6`
- `ntoskrnl!ExAllocatePool3` at `0x140005dd6`

## pseudocode

```c
void FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  void *v3; // rbx
  __int64 Pool3; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v7; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v8[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  EventDescriptor = 0;
  UserData = 0;
  v7 = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v3 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE12(v7) = 0;
    DWORD2(v7) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    *(_QWORD *)&v7 = v8;
    FastWppPackEvent((__int64 *)va, v8, 256, (char *)&v7 + 8);
    if ( DWORD2(v7) > 0x100 )
    {
      Pool3 = ExAllocatePool3(64, DWORD2(v7), 1180127312, 0, 0);
      v3 = (void *)Pool3;
      if ( Pool3 )
      {
        *(_QWORD *)&v7 = Pool3;
        FastWppPackEvent((__int64 *)va, Pool3, DWORD2(v7), (char *)&v7 + 8);
      }
      else
      {
        DWORD2(v7) = 256;
      }
    }
    EtwWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v3 )
      ExFreePoolWithTag(v3, 0x46575050u);
  }
}

```

## disassembly

```asm
0x140005cf4  mov     [rsp-8+arg_10], r8
0x140005cf9  mov     [rsp-8+arg_18], r9
0x140005cfe  push    rbp
0x140005cff  push    rbx
0x140005d00  push    r15
0x140005d02  lea     rbp, [rsp-90h]
0x140005d0a  sub     rsp, 190h
0x140005d11  mov     rax, cs:__security_cookie
0x140005d18  xor     rax, rsp
0x140005d1b  mov     [rbp+0A0h+var_20], rax
0x140005d22  mov     eax, cs:FastWppInitState
0x140005d28  xorps   xmm1, xmm1
0x140005d2b  mov     [rsp+1A0h+var_160], 0
0x140005d34  xorps   xmm0, xmm0
0x140005d37  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x140005d3c  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x140005d41  movups  [rsp+1A0h+var_138], xmm1
0x140005d46  cmp     eax, 2
0x140005d49  jnz     loc_140005E69
0x140005d4f  movzx   eax, cx
0x140005d52  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x140005d57  shr     ax, 8
0x140005d5b  lea     r15, [rbp+0A0h+arg_18]
0x140005d62  mov     [rsp+1A0h+EventDescriptor.Level], al
0x140005d66  lea     r9, [rsp+1A0h+var_138+8]
0x140005d6b  xor     ebx, ebx
0x140005d6d  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x140005d72  mov     r8d, 100h
0x140005d78  mov     [rsp+1A0h+var_148.Size], 10h
0x140005d80  lea     rdx, [rbp+0A0h+var_120]
0x140005d84  mov     byte ptr [rsp+1A0h+var_138+0Ch], bl
0x140005d88  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140005d90  lea     eax, [rbx+1]
0x140005d93  shl     rax, cl
0x140005d96  mov     rcx, r15
0x140005d99  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x140005d9e  mov     rax, [rbp+0A0h+arg_10]
0x140005da5  mov     [rsp+1A0h+var_148.Ptr], rax
0x140005daa  lea     rax, [rbp+0A0h+var_120]
0x140005dae  mov     qword ptr [rsp+1A0h+var_138], rax
0x140005db3  call    FastWppPackEvent
0x140005db8  cmp     dword ptr [rsp+1A0h+var_138+8], 100h
0x140005dc0  jbe     short loc_140005E0E
0x140005dc2  mov     edx, dword ptr [rsp+1A0h+var_138+8]
0x140005dc6  lea     ecx, [rbx+40h]
0x140005dc9  xor     r9d, r9d
0x140005dcc  mov     dword ptr [rsp+1A0h+ActivityId], ebx
0x140005dd0  mov     r8d, 46575050h
0x140005dd6  call    cs:__imp_ExAllocatePool3
0x140005ddd  nop     dword ptr [rax+rax+00h]
0x140005de2  mov     rbx, rax
0x140005de5  test    rax, rax
0x140005de8  jz      short loc_140005E06
0x140005dea  mov     r8d, dword ptr [rsp+1A0h+var_138+8]
0x140005def  lea     r9, [rsp+1A0h+var_138+8]
0x140005df4  mov     rdx, rax
0x140005df7  mov     qword ptr [rsp+1A0h+var_138], rax
0x140005dfc  mov     rcx, r15
0x140005dff  call    FastWppPackEvent
0x140005e04  jmp     short loc_140005E0E
0x140005e06  mov     dword ptr [rsp+1A0h+var_138+8], 100h
0x140005e0e  mov     rcx, cs:FastWppRegHandle; RegHandle
0x140005e15  lea     rax, [rsp+1A0h+var_148]
0x140005e1a  mov     [rsp+1A0h+UserData], rax; UserData
0x140005e1f  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140005e24  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x140005e2c  xor     r9d, r9d; Flags
0x140005e2f  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x140005e38  xor     r8d, r8d; Filter
0x140005e3b  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x140005e44  call    cs:__imp_EtwWriteEx
0x140005e4b  nop     dword ptr [rax+rax+00h]
0x140005e50  test    rbx, rbx
0x140005e53  jz      short loc_140005E69
0x140005e55  mov     edx, 46575050h; Tag
0x140005e5a  mov     rcx, rbx; P
0x140005e5d  call    cs:__imp_ExFreePoolWithTag
0x140005e64  nop     dword ptr [rax+rax+00h]
0x140005e69  mov     rcx, [rbp+0A0h+var_20]
0x140005e70  xor     rcx, rsp; StackCookie
0x140005e73  call    __security_check_cookie
0x140005e78  add     rsp, 190h
0x140005e7f  pop     r15
0x140005e81  pop     rbx
0x140005e82  pop     rbp
0x140005e83  retn
```

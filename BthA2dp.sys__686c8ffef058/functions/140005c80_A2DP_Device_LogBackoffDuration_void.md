# A2DP_Device::LogBackoffDuration(void)

- ea: `0x140005c80`
- end: `0x140005e43`
- name: `?LogBackoffDuration@A2DP_Device@@AEAAXXZ`
- size: `451`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005380`

## callees

- `0x140005c80`
- `0x14005c7d0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140005cb0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140005cb0`
- `ntoskrnl!EtwWriteTransfer` at `0x140005e12`
- `ntoskrnl!EtwWriteTransfer` at `0x140005e12`

## pseudocode

```c
void __fastcall A2DP_Device::LogBackoffDuration(A2DP_Device *this)
{
  ULONGLONG UnbiasedInterruptTime; // rax
  __int64 v3; // r9
  _DWORD v4[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v5; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int64 v6; // [rsp+40h] [rbp-59h] BYREF
  __int64 v7; // [rsp+48h] [rbp-51h] BYREF
  __int64 v8; // [rsp+50h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-29h] BYREF
  char *v11; // [rsp+80h] [rbp-19h]
  int v12; // [rsp+88h] [rbp-11h]
  int v13; // [rsp+8Ch] [rbp-Dh]
  __int64 *v14; // [rsp+90h] [rbp-9h]
  __int64 v15; // [rsp+98h] [rbp-1h]
  __int64 *v16; // [rsp+A0h] [rbp+7h]
  __int64 v17; // [rsp+A8h] [rbp+Fh]
  unsigned __int64 *v18; // [rsp+B0h] [rbp+17h]
  __int64 v19; // [rsp+B8h] [rbp+1Fh]
  _DWORD *v20; // [rsp+C0h] [rbp+27h]
  __int64 v21; // [rsp+C8h] [rbp+2Fh]
  __int64 *v22; // [rsp+D0h] [rbp+37h]
  __int64 v23; // [rsp+D8h] [rbp+3Fh]

  if ( *((_BYTE *)this + 3368) )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v3 = *((_QWORD *)this + 420);
    if ( (unsigned int)dword_14006F0F8 > 5
      && (qword_14006F108 & 0x400000000000LL) != 0
      && (qword_14006F110 & 0x400000000000LL) == qword_14006F110 )
    {
      v5 = *((_QWORD *)this + 90);
      v4[0] = *((_DWORD *)this + 843);
      v7 = *((_QWORD *)this + 353);
      v22 = &v5;
      v20 = v4;
      v18 = &v6;
      v16 = &v7;
      v14 = &v8;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14006F100;
      v6 = (UnbiasedInterruptTime - v3) / 0x2710;
      v8 = 50333696;
      v23 = 8;
      v21 = 4;
      v19 = 8;
      v17 = 8;
      v15 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = (unsigned __int16)*off_14006F100;
      v11 = byte_140069A31;
      UserData.Reserved = 2;
      v12 = 135;
      v13 = 1;
      v4[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
    }
    *((_BYTE *)this + 3368) = 0;
  }
}

```

## disassembly

```asm
0x140005c80  mov     [rsp-8+arg_8], rbx
0x140005c85  push    rbp
0x140005c86  lea     rbp, [rsp-57h]
0x140005c8b  sub     rsp, 0F0h
0x140005c92  mov     rax, cs:__security_cookie
0x140005c99  xor     rax, rsp
0x140005c9c  mov     [rbp+57h+var_10], rax
0x140005ca0  cmp     byte ptr [rcx+0D28h], 0
0x140005ca7  mov     rbx, rcx
0x140005caa  jz      loc_140005E25
0x140005cb0  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140005cb7  nop     dword ptr [rax+rax+00h]
0x140005cbc  mov     edx, cs:dword_14006F0F8
0x140005cc2  mov     r8, rax
0x140005cc5  mov     r9, [rbx+0D20h]
0x140005ccc  cmp     edx, 5
0x140005ccf  jbe     loc_140005E1E
0x140005cd5  mov     rdx, cs:qword_14006F110
0x140005cdc  mov     r10, 400000000000h
0x140005ce6  mov     rcx, cs:qword_14006F108
0x140005ced  test    r10, rcx
0x140005cf0  jz      loc_140005E1E
0x140005cf6  mov     rcx, rdx
0x140005cf9  and     rcx, r10
0x140005cfc  cmp     rcx, rdx
0x140005cff  jnz     loc_140005E1E
0x140005d05  mov     rax, [rbx+2D0h]
0x140005d0c  lea     rcx, _TraceLoggingMetadata
0x140005d13  mov     [rbp+57h+var_B8], rax
0x140005d17  sub     r8, r9
0x140005d1a  mov     eax, [rbx+0D2Ch]
0x140005d20  xor     r9d, r9d; RelatedActivityId
0x140005d23  mov     [rbp+57h+var_C0], eax
0x140005d26  mov     rax, 346DC5D63886594Bh
0x140005d30  mul     r8
0x140005d33  mov     rax, [rbx+0B08h]
0x140005d3a  xor     r8d, r8d; ActivityId
0x140005d3d  mov     [rbp+57h+var_A8], rax
0x140005d41  lea     rax, [rbp+57h+var_B8]
0x140005d45  mov     [rbp+57h+var_20], rax
0x140005d49  lea     rax, [rbp+57h+var_C0]
0x140005d4d  mov     [rbp+57h+var_30], rax
0x140005d51  lea     rax, [rbp+57h+var_B0]
0x140005d55  mov     [rbp+57h+var_40], rax
0x140005d59  lea     rax, [rbp+57h+var_A8]
0x140005d5d  mov     [rbp+57h+var_50], rax
0x140005d61  lea     rax, [rbp+57h+var_A0]
0x140005d65  mov     [rbp+57h+var_60], rax
0x140005d69  movzx   eax, cs:word_140069A27
0x140005d70  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140005d73  mov     rax, cs:off_14006F100
0x140005d7a  mov     [rbp+57h+var_80.Ptr], rax
0x140005d7e  shr     rdx, 0Bh
0x140005d82  mov     [rbp+57h+var_B0], rdx
0x140005d86  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140005d8a  mov     [rbp+57h+var_A0], 3000800h
0x140005d92  mov     [rbp+57h+var_18], 8
0x140005d9a  mov     [rbp+57h+var_28], 4
0x140005da2  mov     [rbp+57h+var_38], 8
0x140005daa  mov     [rbp+57h+var_48], 8
0x140005db2  mov     [rbp+57h+var_58], 8
0x140005dba  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140005dc1  mov     [rbp+57h+EventDescriptor.Keyword], r10
0x140005dc5  movzx   eax, word ptr [rax]
0x140005dc8  mov     [rbp+57h+var_80.Size], eax
0x140005dcb  lea     rax, byte_140069A31
0x140005dd2  mov     [rbp+57h+var_70], rax
0x140005dd6  lea     rax, _TraceLoggingMetadataEnd
0x140005ddd  sub     eax, ecx
0x140005ddf  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x140005de6  mov     [rbp+57h+var_68], 87h
0x140005ded  mov     [rbp+57h+var_64], 1
0x140005df4  mov     [rbp+57h+var_BC], eax
0x140005df7  mov     eax, [rbp+57h+var_BC]
0x140005dfa  mov     rcx, cs:RegHandle; RegHandle
0x140005e01  lea     rax, [rbp+57h+var_80]
0x140005e05  mov     [rsp+0F0h+UserData], rax; UserData
0x140005e0a  mov     [rsp+0F0h+UserDataCount], 7; UserDataCount
0x140005e12  call    cs:__imp_EtwWriteTransfer
0x140005e19  nop     dword ptr [rax+rax+00h]
0x140005e1e  mov     byte ptr [rbx+0D28h], 0
0x140005e25  mov     rcx, [rbp+57h+var_10]
0x140005e29  xor     rcx, rsp; StackCookie
0x140005e2c  call    __security_check_cookie
0x140005e31  mov     rbx, [rsp+0F0h+arg_8]
0x140005e39  add     rsp, 0F0h
0x140005e40  pop     rbp
0x140005e41  retn
```

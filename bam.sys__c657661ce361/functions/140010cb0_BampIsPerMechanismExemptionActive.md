# BampIsPerMechanismExemptionActive

- ea: `0x140010cb0`
- end: `0x140010e11`
- name: `BampIsPerMechanismExemptionActive`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140010a30`

## callees

- `0x1400026d0`
- `0x140010cb0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140010de4`
- `ntoskrnl!EtwWriteTransfer` at `0x140010de4`

## pseudocode

```c
_BOOL8 __fastcall BampIsPerMechanismExemptionActive(__int64 a1, int a2, int *a3)
{
  int v3; // r10d
  __int64 v4; // r9
  bool v5; // bl
  __int64 v6; // rax
  int v7; // ecx
  bool v9; // [rsp+30h] [rbp-59h] BYREF
  int v10; // [rsp+34h] [rbp-55h] BYREF
  int v11; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  _DWORD v13[2]; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v16; // [rsp+70h] [rbp-19h]
  int v17; // [rsp+78h] [rbp-11h]
  int v18; // [rsp+7Ch] [rbp-Dh]
  int *v19; // [rsp+80h] [rbp-9h]
  __int64 v20; // [rsp+88h] [rbp-1h]
  int *v21; // [rsp+90h] [rbp+7h]
  __int64 v22; // [rsp+98h] [rbp+Fh]
  bool *v23; // [rsp+A0h] [rbp+17h]
  __int64 v24; // [rsp+A8h] [rbp+1Fh]
  int *v25; // [rsp+B0h] [rbp+27h]
  __int64 v26; // [rsp+B8h] [rbp+2Fh]
  _DWORD *v27; // [rsp+C0h] [rbp+37h]
  __int64 v28; // [rsp+C8h] [rbp+3Fh]

  v3 = *a3;
  v4 = a1 + 4LL * a2;
  v5 = (*a3 & *(_DWORD *)(v4 + 380)) != 0;
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v7 = *(_DWORD *)(v6 + 464);
    v19 = &v10;
    v21 = &v11;
    v23 = &v9;
    v25 = &v12;
    v13[0] = *(_DWORD *)(v4 + 380);
    v27 = v13;
    v10 = v7;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v11 = a2;
    v20 = 4;
    v22 = 4;
    v9 = v5;
    v24 = 1;
    v12 = v3;
    v26 = 4;
    v28 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v16 = &byte_140005597;
    UserData.Reserved = 2;
    v17 = 112;
    v18 = 1;
    v13[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
  }
  return v5;
}

```

## disassembly

```asm
0x140010cb0  mov     [rsp-8+arg_0], rbx
0x140010cb5  push    rbp
0x140010cb6  lea     rbp, [rsp-57h]
0x140010cbb  sub     rsp, 0E0h
0x140010cc2  mov     rax, cs:__security_cookie
0x140010cc9  xor     rax, rsp
0x140010ccc  mov     [rbp+57h+var_10], rax
0x140010cd0  mov     r10d, [r8]
0x140010cd3  movsxd  rax, edx
0x140010cd6  lea     r9, [rcx+rax*4]
0x140010cda  mov     eax, cs:dword_140007010
0x140010ce0  test    [r9+17Ch], r10d
0x140010ce7  setnz   bl
0x140010cea  cmp     eax, 4
0x140010ced  jbe     loc_140010DF0
0x140010cf3  mov     rax, [rcx+8]
0x140010cf7  xor     r8d, r8d; ActivityId
0x140010cfa  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140010d01  mov     ecx, [rax+1D0h]
0x140010d07  lea     rax, [rbp+57h+var_AC]
0x140010d0b  mov     [rbp+57h+var_60], rax
0x140010d0f  lea     rax, [rbp+57h+var_A8]
0x140010d13  mov     [rbp+57h+var_50], rax
0x140010d17  lea     rax, [rbp+57h+var_B0]
0x140010d1b  mov     [rbp+57h+var_40], rax
0x140010d1f  lea     rax, [rbp+57h+var_A4]
0x140010d23  mov     [rbp+57h+var_30], rax
0x140010d27  mov     eax, [r9+17Ch]
0x140010d2e  xor     r9d, r9d; RelatedActivityId
0x140010d31  mov     [rbp+57h+var_A0], eax
0x140010d34  lea     rax, [rbp+57h+var_A0]
0x140010d38  mov     [rbp+57h+var_20], rax
0x140010d3c  movzx   eax, cs:word_14000558D
0x140010d43  mov     [rbp+57h+var_AC], ecx
0x140010d46  xor     ecx, ecx
0x140010d48  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140010d4b  mov     rax, cs:off_140007018
0x140010d52  mov     [rbp+57h+EventDescriptor.Keyword], rcx
0x140010d56  lea     rcx, _TraceLoggingMetadataEnd
0x140010d5d  mov     [rbp+57h+var_80.Ptr], rax
0x140010d61  mov     [rbp+57h+var_A8], edx
0x140010d64  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140010d68  mov     [rbp+57h+var_58], 4
0x140010d70  mov     [rbp+57h+var_48], 4
0x140010d78  mov     [rbp+57h+var_B0], bl
0x140010d7b  mov     [rbp+57h+var_38], 1
0x140010d83  mov     [rbp+57h+var_A4], r10d
0x140010d87  mov     [rbp+57h+var_28], 4
0x140010d8f  mov     [rbp+57h+var_18], 4
0x140010d97  movzx   eax, word ptr [rax]
0x140010d9a  mov     [rbp+57h+var_80.Size], eax
0x140010d9d  lea     rax, byte_140005597
0x140010da4  mov     [rbp+57h+var_70], rax
0x140010da8  lea     rax, _TraceLoggingMetadata
0x140010daf  sub     ecx, eax
0x140010db1  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x140010db8  mov     [rbp+57h+var_68], 70h ; 'p'
0x140010dbf  lea     rax, [rbp+57h+var_80]
0x140010dc3  mov     [rbp+57h+var_64], 1
0x140010dca  mov     [rbp+57h+var_9C], ecx
0x140010dcd  mov     ecx, [rbp+57h+var_9C]
0x140010dd0  mov     rcx, cs:RegHandle; RegHandle
0x140010dd7  mov     [rsp+0E0h+UserData], rax; UserData
0x140010ddc  mov     [rsp+0E0h+UserDataCount], 7; UserDataCount
0x140010de4  call    cs:__imp_EtwWriteTransfer
0x140010deb  nop     dword ptr [rax+rax+00h]
0x140010df0  movzx   eax, bl
0x140010df3  mov     rcx, [rbp+57h+var_10]
0x140010df7  xor     rcx, rsp; StackCookie
0x140010dfa  call    __security_check_cookie
0x140010dff  mov     rbx, [rsp+0E0h+arg_0]
0x140010e07  add     rsp, 0E0h
0x140010e0e  pop     rbp
0x140010e0f  retn
```

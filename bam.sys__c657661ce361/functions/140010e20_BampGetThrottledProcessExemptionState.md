# BampGetThrottledProcessExemptionState

- ea: `0x140010e20`
- end: `0x140010fff`
- name: `BampGetThrottledProcessExemptionState`
- size: `479`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010a30`
- `0x140014180`

## callees

- `0x1400026d0`
- `0x140010e20`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140010fdb`
- `ntoskrnl!EtwWriteTransfer` at `0x140010fdb`

## pseudocode

```c
NTSTATUS __fastcall BampGetThrottledProcessExemptionState(__int64 a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v6; // ecx
  int v7; // ebx
  unsigned int v8; // r8d
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // ecx
  int v12; // eax
  int v13; // edx
  NTSTATUS result; // eax
  __int64 v15; // rax
  int v16; // ecx
  int v17; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-35h] BYREF
  _DWORD v19[2]; // [rsp+38h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  char *v22; // [rsp+60h] [rbp-9h]
  int v23; // [rsp+68h] [rbp-1h]
  int v24; // [rsp+6Ch] [rbp+3h]
  int *v25; // [rsp+70h] [rbp+7h]
  __int64 v26; // [rsp+78h] [rbp+Fh]
  unsigned int *v27; // [rsp+80h] [rbp+17h]
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  _DWORD *v29; // [rsp+90h] [rbp+27h]
  __int64 v30; // [rsp+98h] [rbp+2Fh]

  *a2 = 0;
  *a3 = 0;
  v6 = *(_DWORD *)(a1 + 304);
  v7 = *(_DWORD *)(a1 + 308);
  v8 = v6 | 1;
  v9 = *(_DWORD *)(a1 + 324);
  if ( (v6 & 0x10) == 0 )
    v8 = v6;
  if ( (v8 & 1) == 0 )
  {
    v8 = *(_DWORD *)(a1 + 328);
    if ( !v9 )
      v9 = *(_DWORD *)(a1 + 348);
  }
  v10 = 2;
  if ( v9 != 2 )
    v10 = 0;
  v11 = *a2 & 0xFFFFFFFD | v10;
  *a2 = v11;
  *a2 = v11 & 0xFFFFFFFE | ((*(_WORD *)(a1 + 276) & 1) == 0);
  if ( (v8 & 1) == 0 || (v13 = 2, (v8 & 6) == 0) )
    v13 = 0;
  v12 = *a3
      ^ ((unsigned __int8)*a3
       ^ (unsigned __int8)(8 * v7))
      & 8
      ^ ((unsigned __int8)(8 * v7)
       ^ *(_BYTE *)a3
       ^ ((unsigned __int8)*a3
        ^ (unsigned __int8)(8 * v7))
       & 8)
      & 0x10;
  *a3 = (4 * !(v8 & 1))
      | v13 & 0xFFFFFFFB
      | (v12 ^ ((unsigned __int8)v12 ^ (unsigned __int8)(v8 >> 1)) & 1) & 0xFFFFFFF9;
  result = dword_140007010;
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v15 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v16 = *(_DWORD *)(v15 + 464);
    v25 = &v17;
    v18 = *a2;
    v27 = &v18;
    v19[0] = *a3;
    v29 = v19;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v17 = v16;
    v26 = 4;
    v28 = 4;
    v30 = 4;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v22 = byte_140005613;
    UserData.Reserved = 2;
    v23 = 83;
    v24 = 1;
    v19[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140010e20  push    rbp
0x140010e22  push    rbx
0x140010e23  push    rdi
0x140010e24  lea     rbp, [rsp-47h]
0x140010e29  sub     rsp, 0B0h
0x140010e30  mov     rax, cs:__security_cookie
0x140010e37  xor     rax, rsp
0x140010e3a  mov     [rbp+57h+var_20], rax
0x140010e3e  xor     eax, eax
0x140010e40  mov     r9, rcx
0x140010e43  mov     [rdx], eax
0x140010e45  mov     r10, r8
0x140010e48  mov     [r8], eax
0x140010e4b  mov     r11, rdx
0x140010e4e  mov     ecx, [rcx+130h]
0x140010e54  mov     r8d, ecx
0x140010e57  mov     ebx, [r9+134h]
0x140010e5e  or      r8d, 1
0x140010e62  mov     edx, [r9+144h]
0x140010e69  test    cl, 10h
0x140010e6c  cmovz   r8d, ecx
0x140010e70  test    r8b, 1
0x140010e74  jnz     short loc_140010E88
0x140010e76  mov     r8d, [r9+148h]
0x140010e7d  test    edx, edx
0x140010e7f  jnz     short loc_140010E88
0x140010e81  mov     edx, [r9+15Ch]
0x140010e88  mov     eax, [r11]
0x140010e8b  xor     edi, edi
0x140010e8d  mov     ecx, 2
0x140010e92  cmp     edx, ecx
0x140010e94  cmovnz  ecx, edi
0x140010e97  and     eax, 0FFFFFFFDh
0x140010e9a  or      ecx, eax
0x140010e9c  mov     [r11], ecx
0x140010e9f  and     ecx, 0FFFFFFFEh
0x140010ea2  movzx   eax, word ptr [r9+114h]
0x140010eaa  not     ax
0x140010ead  and     eax, 1
0x140010eb0  or      eax, ecx
0x140010eb2  lea     ecx, ds:0[rbx*8]
0x140010eb9  mov     [r11], eax
0x140010ebc  mov     edx, ecx
0x140010ebe  mov     eax, [r10]
0x140010ec1  xor     edx, eax
0x140010ec3  and     edx, 8
0x140010ec6  xor     edx, eax
0x140010ec8  mov     eax, edx
0x140010eca  xor     eax, ecx
0x140010ecc  mov     ecx, r8d
0x140010ecf  shr     ecx, 1
0x140010ed1  and     eax, 10h
0x140010ed4  xor     eax, edx
0x140010ed6  xor     ecx, eax
0x140010ed8  and     ecx, 1
0x140010edb  xor     ecx, eax
0x140010edd  mov     eax, r8d
0x140010ee0  and     eax, 1
0x140010ee3  jz      short loc_140010EF0
0x140010ee5  mov     edx, 2
0x140010eea  test    r8b, 6
0x140010eee  jnz     short loc_140010EF2
0x140010ef0  mov     edx, edi
0x140010ef2  and     ecx, 0FFFFFFFDh
0x140010ef5  xor     eax, 1
0x140010ef8  or      ecx, edx
0x140010efa  shl     eax, 2
0x140010efd  and     ecx, 0FFFFFFFBh
0x140010f00  or      ecx, eax
0x140010f02  mov     [r10], ecx
0x140010f05  mov     eax, cs:dword_140007010
0x140010f0b  cmp     eax, 5
0x140010f0e  jbe     loc_140010FE7
0x140010f14  mov     rax, [r9+8]
0x140010f18  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140010f1c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140010f23  xor     r9d, r9d; RelatedActivityId
0x140010f26  mov     [rbp+57h+EventDescriptor.Keyword], rdi
0x140010f2a  xor     r8d, r8d; ActivityId
0x140010f2d  mov     ecx, [rax+1D0h]
0x140010f33  lea     rax, [rbp+57h+var_90]
0x140010f37  mov     [rbp+57h+var_50], rax
0x140010f3b  mov     eax, [r11]
0x140010f3e  mov     [rbp+57h+var_8C], eax
0x140010f41  lea     rax, [rbp+57h+var_8C]
0x140010f45  mov     [rbp+57h+var_40], rax
0x140010f49  mov     eax, [r10]
0x140010f4c  mov     [rbp+57h+var_88], eax
0x140010f4f  lea     rax, [rbp+57h+var_88]
0x140010f53  mov     [rbp+57h+var_30], rax
0x140010f57  movzx   eax, cs:word_140005609
0x140010f5e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140010f61  mov     rax, cs:off_140007018
0x140010f68  mov     [rbp+57h+var_70.Ptr], rax
0x140010f6c  mov     [rbp+57h+var_90], ecx
0x140010f6f  lea     rcx, _TraceLoggingMetadata
0x140010f76  mov     [rbp+57h+var_48], 4
0x140010f7e  mov     [rbp+57h+var_38], 4
0x140010f86  mov     [rbp+57h+var_28], 4
0x140010f8e  movzx   eax, word ptr [rax]
0x140010f91  mov     [rbp+57h+var_70.Size], eax
0x140010f94  lea     rax, byte_140005613
0x140010f9b  mov     [rbp+57h+var_60], rax
0x140010f9f  lea     rax, _TraceLoggingMetadataEnd
0x140010fa6  sub     eax, ecx
0x140010fa8  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140010faf  mov     [rbp+57h+var_58], 53h ; 'S'
0x140010fb6  mov     [rbp+57h+var_54], 1
0x140010fbd  mov     [rbp+57h+var_84], eax
0x140010fc0  mov     eax, [rbp+57h+var_84]
0x140010fc3  mov     rcx, cs:RegHandle; RegHandle
0x140010fca  lea     rax, [rbp+57h+var_70]
0x140010fce  mov     [rsp+0C0h+UserData], rax; UserData
0x140010fd3  mov     [rsp+0C0h+UserDataCount], 5; UserDataCount
0x140010fdb  call    cs:__imp_EtwWriteTransfer
0x140010fe2  nop     dword ptr [rax+rax+00h]
0x140010fe7  mov     rcx, [rbp+57h+var_20]
0x140010feb  xor     rcx, rsp; StackCookie
0x140010fee  call    __security_check_cookie
0x140010ff3  add     rsp, 0B0h
0x140010ffa  pop     rdi
0x140010ffb  pop     rbx
0x140010ffc  pop     rbp
0x140010ffd  retn
```

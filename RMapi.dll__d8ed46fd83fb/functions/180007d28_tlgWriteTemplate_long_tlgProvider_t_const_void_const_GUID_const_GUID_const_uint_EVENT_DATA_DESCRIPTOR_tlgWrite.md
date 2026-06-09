# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)

- ea: `0x180007d28`
- end: `0x180007ef9`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@53@Z`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020d50`

## callees

- `0x180007d28`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007ede`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007ede`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7,
        __int64 **a8,
        __int64 **a9,
        const wchar_t **a10)
{
  __int64 v10; // r8
  const wchar_t *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const wchar_t *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  const wchar_t *v23; // rcx
  int v24; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-81h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 *v28; // [rsp+60h] [rbp-59h]
  int v29; // [rsp+68h] [rbp-51h]
  int v30; // [rsp+6Ch] [rbp-4Dh]
  const wchar_t *v31; // [rsp+70h] [rbp-49h]
  int v32; // [rsp+78h] [rbp-41h]
  int v33; // [rsp+7Ch] [rbp-3Dh]
  __int64 v34; // [rsp+80h] [rbp-39h]
  __int64 v35; // [rsp+88h] [rbp-31h]
  const wchar_t *v36; // [rsp+90h] [rbp-29h]
  int v37; // [rsp+98h] [rbp-21h]
  int v38; // [rsp+9Ch] [rbp-1Dh]
  __int64 *v39; // [rsp+A0h] [rbp-19h]
  int v40; // [rsp+A8h] [rbp-11h]
  int v41; // [rsp+ACh] [rbp-Dh]
  __int64 *v42; // [rsp+B0h] [rbp-9h]
  int v43; // [rsp+B8h] [rbp-1h]
  int v44; // [rsp+BCh] [rbp+3h]
  const wchar_t *v45; // [rsp+C0h] [rbp+7h]
  int v46; // [rsp+C8h] [rbp+Fh]
  int v47; // [rsp+CCh] [rbp+13h]

  v10 = -1;
  v11 = *a10;
  if ( *a10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &byte_18002AE5D;
    v13 = 1;
  }
  v46 = v13;
  v45 = v11;
  v47 = 0;
  v14 = *a9;
  if ( *a9 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_18002AF20;
    v16 = 2;
  }
  v43 = v16;
  v42 = v14;
  v44 = 0;
  v17 = *a8;
  if ( *a8 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_18002AF20;
    v19 = 2;
  }
  v40 = v19;
  v39 = v17;
  v41 = 0;
  v20 = *a7;
  if ( *a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_BYTE *)v20 + v21) );
    v22 = v21 + 1;
  }
  else
  {
    v20 = &byte_18002AE5D;
    v22 = 1;
  }
  v37 = v22;
  v36 = v20;
  v38 = 0;
  v35 = 16;
  v34 = *a6;
  v23 = *a5;
  if ( *a5 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v23 + v10) );
    v24 = v10 + 1;
  }
  else
  {
    v23 = &byte_18002AE5D;
    v24 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v31 = v23;
  v32 = v24;
  v33 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v29 = *(unsigned __int16 *)(a2 + 11);
  v28 = a2 + 11;
  UserData.Reserved = 2;
  v30 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x180007d28  push    rbp
0x180007d2a  lea     rbp, [rsp-27h]
0x180007d2f  sub     rsp, 0E0h
0x180007d36  mov     rax, cs:__security_cookie
0x180007d3d  xor     rax, rsp
0x180007d40  mov     [rbp+27h+var_10], rax
0x180007d44  mov     rax, [rbp+27h+arg_48]
0x180007d48  lea     r10, byte_18002AE5D
0x180007d4f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007d53  xor     r9d, r9d; RelatedActivityId
0x180007d56  mov     r11d, 1
0x180007d5c  mov     rcx, [rax]
0x180007d5f  test    rcx, rcx
0x180007d62  jz      short loc_180007D74
0x180007d64  mov     rax, r8
0x180007d67  inc     rax
0x180007d6a  cmp     [rcx+rax], r9b
0x180007d6e  jnz     short loc_180007D67
0x180007d70  inc     eax
0x180007d72  jmp     short loc_180007D7A
0x180007d74  mov     rcx, r10
0x180007d77  mov     eax, r11d
0x180007d7a  mov     [rbp+27h+var_18], eax
0x180007d7d  mov     rax, [rbp+27h+arg_40]
0x180007d81  mov     [rbp+27h+var_20], rcx
0x180007d85  mov     [rbp+27h+var_14], r9d
0x180007d89  mov     rcx, [rax]
0x180007d8c  test    rcx, rcx
0x180007d8f  jz      short loc_180007DA7
0x180007d91  mov     rax, r8
0x180007d94  inc     rax
0x180007d97  cmp     [rcx+rax*2], r9w
0x180007d9c  jnz     short loc_180007D94
0x180007d9e  lea     eax, ds:2[rax*2]
0x180007da5  jmp     short loc_180007DB3
0x180007da7  lea     rcx, qword_18002AF20
0x180007dae  mov     eax, 2
0x180007db3  mov     [rbp+27h+var_28], eax
0x180007db6  mov     rax, [rbp+27h+arg_38]
0x180007dba  mov     [rbp+27h+var_30], rcx
0x180007dbe  mov     [rbp+27h+var_24], r9d
0x180007dc2  mov     rcx, [rax]
0x180007dc5  test    rcx, rcx
0x180007dc8  jz      short loc_180007DE0
0x180007dca  mov     rax, r8
0x180007dcd  inc     rax
0x180007dd0  cmp     [rcx+rax*2], r9w
0x180007dd5  jnz     short loc_180007DCD
0x180007dd7  lea     eax, ds:2[rax*2]
0x180007dde  jmp     short loc_180007DEC
0x180007de0  lea     rcx, qword_18002AF20
0x180007de7  mov     eax, 2
0x180007dec  mov     [rbp+27h+var_38], eax
0x180007def  mov     rax, [rbp+27h+arg_30]
0x180007df3  mov     [rbp+27h+var_40], rcx
0x180007df7  mov     [rbp+27h+var_34], r9d
0x180007dfb  mov     rcx, [rax]
0x180007dfe  test    rcx, rcx
0x180007e01  jz      short loc_180007E13
0x180007e03  mov     rax, r8
0x180007e06  inc     rax
0x180007e09  cmp     [rcx+rax], r9b
0x180007e0d  jnz     short loc_180007E06
0x180007e0f  inc     eax
0x180007e11  jmp     short loc_180007E19
0x180007e13  mov     rcx, r10
0x180007e16  mov     eax, r11d
0x180007e19  mov     [rbp+27h+var_48], eax
0x180007e1c  mov     rax, [rbp+27h+arg_28]
0x180007e20  mov     [rbp+27h+var_50], rcx
0x180007e24  mov     [rbp+27h+var_44], r9d
0x180007e28  mov     [rbp+27h+var_58], 10h
0x180007e30  mov     rcx, [rax]
0x180007e33  mov     rax, [rbp+27h+arg_20]
0x180007e37  mov     [rbp+27h+var_60], rcx
0x180007e3b  mov     rcx, [rax]
0x180007e3e  test    rcx, rcx
0x180007e41  jz      short loc_180007E51
0x180007e43  inc     r8
0x180007e46  cmp     [rcx+r8], r9b
0x180007e4a  jnz     short loc_180007E43
0x180007e4c  inc     r8d
0x180007e4f  jmp     short loc_180007E57
0x180007e51  mov     rcx, r10
0x180007e54  mov     r8d, r11d
0x180007e57  movzx   eax, byte ptr [rdx]
0x180007e5a  shl     eax, 18h
0x180007e5d  mov     dword ptr [rsp+0E0h+EventDescriptor.Id], eax
0x180007e61  movzx   eax, word ptr [rdx+1]
0x180007e65  mov     dword ptr [rbp+27h+EventDescriptor.Level], eax
0x180007e68  mov     rax, [rdx+3]
0x180007e6c  mov     [rbp+27h+EventDescriptor.Keyword], rax
0x180007e70  mov     rax, cs:off_180037058
0x180007e77  mov     [rbp+27h+var_90.Ptr], rax
0x180007e7b  mov     [rbp+27h+var_70], rcx
0x180007e7f  lea     rcx, [rdx+0Bh]
0x180007e83  mov     [rbp+27h+var_68], r8d
0x180007e87  lea     rdx, [rsp+0E0h+EventDescriptor]; EventDescriptor
0x180007e8c  mov     [rbp+27h+var_64], r9d
0x180007e90  xor     r8d, r8d; ActivityId
0x180007e93  movzx   eax, word ptr [rax]
0x180007e96  mov     [rbp+27h+var_90.Size], eax
0x180007e99  movzx   eax, word ptr [rcx]
0x180007e9c  mov     [rbp+27h+var_78], eax
0x180007e9f  lea     rax, _TraceLoggingMetadataEnd
0x180007ea6  mov     [rbp+27h+var_80], rcx
0x180007eaa  lea     rcx, _TraceLoggingMetadata
0x180007eb1  sub     eax, ecx
0x180007eb3  mov     dword ptr [rbp+27h+var_90.0Ch], 2
0x180007eba  mov     [rbp+27h+var_74], r11d
0x180007ebe  mov     [rsp+0E0h+var_B0], eax
0x180007ec2  mov     eax, [rsp+0E0h+var_B0]
0x180007ec6  mov     rcx, cs:RegHandle; RegHandle
0x180007ecd  lea     rax, [rbp+27h+var_90]
0x180007ed1  mov     [rsp+0E0h+UserData], rax; UserData
0x180007ed6  mov     [rsp+0E0h+UserDataCount], 8; UserDataCount
0x180007ede  call    cs:__imp_EventWriteTransfer
0x180007ee4  mov     rcx, [rbp+27h+var_10]
0x180007ee8  xor     rcx, rsp; StackCookie
0x180007eeb  call    __security_check_cookie
0x180007ef0  add     rsp, 0E0h
0x180007ef7  pop     rbp
0x180007ef8  retn
```

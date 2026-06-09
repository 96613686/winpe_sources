# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180006a2c`
- end: `0x180006b69`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `317`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c7e0`
- `0x18001df88`
- `0x18001f6c0`
- `0x1800222d0`
- `0x180025b66`
- `0x180026056`
- `0x1800260ef`
- `0x1800261a5`
- `0x18002623b`
- `0x1800268b2`
- `0x180026940`
- `0x180026ab4`
- `0x180026c57`
- `0x180026d00`

## callees

- `0x180006a2c`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006b4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006b4e`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7,
        __int64 a8)
{
  __int64 v8; // r8
  const wchar_t *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  const wchar_t *v12; // rcx
  int v13; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 *v17; // [rsp+60h] [rbp-29h]
  int v18; // [rsp+68h] [rbp-21h]
  int v19; // [rsp+6Ch] [rbp-1Dh]
  const wchar_t *v20; // [rsp+70h] [rbp-19h]
  int v21; // [rsp+78h] [rbp-11h]
  int v22; // [rsp+7Ch] [rbp-Dh]
  __int64 v23; // [rsp+80h] [rbp-9h]
  __int64 v24; // [rsp+88h] [rbp-1h]
  const wchar_t *v25; // [rsp+90h] [rbp+7h]
  int v26; // [rsp+98h] [rbp+Fh]
  int v27; // [rsp+9Ch] [rbp+13h]
  __int64 v28; // [rsp+A0h] [rbp+17h]
  __int64 v29; // [rsp+A8h] [rbp+1Fh]

  v28 = a8;
  v8 = -1;
  v29 = 4;
  v9 = *a7;
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v9 = &byte_18002AE5D;
    v11 = 1;
  }
  v26 = v11;
  v25 = v9;
  v27 = 0;
  v24 = 16;
  v23 = *a6;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v12 + v8) );
    v13 = v8 + 1;
  }
  else
  {
    v12 = &byte_18002AE5D;
    v13 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v20 = v12;
  v21 = v13;
  v22 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v18 = *(unsigned __int16 *)(a2 + 11);
  v17 = a2 + 11;
  UserData.Reserved = 2;
  v19 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
}

```

## disassembly

```asm
0x180006a2c  push    rbp
0x180006a2e  lea     rbp, [rsp-37h]
0x180006a33  sub     rsp, 0C0h
0x180006a3a  mov     rax, cs:__security_cookie
0x180006a41  xor     rax, rsp
0x180006a44  mov     [rbp+37h+var_10], rax
0x180006a48  mov     rax, [rbp+37h+arg_38]
0x180006a4c  xor     r9d, r9d; RelatedActivityId
0x180006a4f  mov     [rbp+37h+var_20], rax
0x180006a53  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006a57  mov     rax, [rbp+37h+arg_30]
0x180006a5b  mov     [rbp+37h+var_18], 4
0x180006a63  lea     r10d, [r9+1]
0x180006a67  mov     rcx, [rax]
0x180006a6a  test    rcx, rcx
0x180006a6d  jz      short loc_180006A7F
0x180006a6f  mov     rax, r8
0x180006a72  inc     rax
0x180006a75  cmp     [rcx+rax], r9b
0x180006a79  jnz     short loc_180006A72
0x180006a7b  inc     eax
0x180006a7d  jmp     short loc_180006A89
0x180006a7f  lea     rcx, byte_18002AE5D
0x180006a86  mov     eax, r10d
0x180006a89  mov     [rbp+37h+var_28], eax
0x180006a8c  mov     rax, [rbp+37h+arg_28]
0x180006a90  mov     [rbp+37h+var_30], rcx
0x180006a94  mov     [rbp+37h+var_24], r9d
0x180006a98  mov     [rbp+37h+var_38], 10h
0x180006aa0  mov     rcx, [rax]
0x180006aa3  mov     rax, [rbp+37h+arg_20]
0x180006aa7  mov     [rbp+37h+var_40], rcx
0x180006aab  mov     rcx, [rax]
0x180006aae  test    rcx, rcx
0x180006ab1  jz      short loc_180006AC1
0x180006ab3  inc     r8
0x180006ab6  cmp     [rcx+r8], r9b
0x180006aba  jnz     short loc_180006AB3
0x180006abc  inc     r8d
0x180006abf  jmp     short loc_180006ACB
0x180006ac1  lea     rcx, byte_18002AE5D
0x180006ac8  mov     r8d, r10d
0x180006acb  movzx   eax, byte ptr [rdx]
0x180006ace  shl     eax, 18h
0x180006ad1  mov     dword ptr [rbp+37h+EventDescriptor.Id], eax
0x180006ad4  movzx   eax, word ptr [rdx+1]
0x180006ad8  mov     dword ptr [rbp+37h+EventDescriptor.Level], eax
0x180006adb  mov     rax, [rdx+3]
0x180006adf  mov     [rbp+37h+EventDescriptor.Keyword], rax
0x180006ae3  mov     rax, cs:off_180037058
0x180006aea  mov     [rbp+37h+var_70.Ptr], rax
0x180006aee  mov     [rbp+37h+var_50], rcx
0x180006af2  lea     rcx, [rdx+0Bh]
0x180006af6  mov     [rbp+37h+var_48], r8d
0x180006afa  lea     rdx, [rbp+37h+EventDescriptor]; EventDescriptor
0x180006afe  mov     [rbp+37h+var_44], r9d
0x180006b02  xor     r8d, r8d; ActivityId
0x180006b05  movzx   eax, word ptr [rax]
0x180006b08  mov     [rbp+37h+var_70.Size], eax
0x180006b0b  movzx   eax, word ptr [rcx]
0x180006b0e  mov     [rbp+37h+var_58], eax
0x180006b11  lea     rax, _TraceLoggingMetadataEnd
0x180006b18  mov     [rbp+37h+var_60], rcx
0x180006b1c  lea     rcx, _TraceLoggingMetadata
0x180006b23  sub     eax, ecx
0x180006b25  mov     dword ptr [rbp+37h+var_70.0Ch], 2
0x180006b2c  mov     [rbp+37h+var_54], r10d
0x180006b30  mov     [rbp+37h+var_90], eax
0x180006b33  mov     eax, [rbp+37h+var_90]
0x180006b36  mov     rcx, cs:RegHandle; RegHandle
0x180006b3d  lea     rax, [rbp+37h+var_70]
0x180006b41  mov     [rsp+0C0h+UserData], rax; UserData
0x180006b46  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x180006b4e  call    cs:__imp_EventWriteTransfer
0x180006b54  mov     rcx, [rbp+37h+var_10]
0x180006b58  xor     rcx, rsp; StackCookie
0x180006b5b  call    __security_check_cookie
0x180006b60  add     rsp, 0C0h
0x180006b67  pop     rbp
0x180006b68  retn
```

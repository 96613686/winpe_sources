# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)

- ea: `0x180006200`
- end: `0x18000633d`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z`
- size: `317`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800135e0`
- `0x18001b8b8`
- `0x18001b968`
- `0x18001c23c`
- `0x18001d4b4`
- `0x18001d834`
- `0x18001df88`
- `0x18001f6c0`
- `0x1800201ac`
- `0x1800213d4`
- `0x180021d48`

## callees

- `0x180006200`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006304`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006304`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7)
{
  __int64 v7; // r8
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  const wchar_t *v11; // rcx
  int v12; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v16; // [rsp+60h] [rbp-11h]
  int v17; // [rsp+68h] [rbp-9h]
  int v18; // [rsp+6Ch] [rbp-5h]
  const wchar_t *v19; // [rsp+70h] [rbp-1h]
  int v20; // [rsp+78h] [rbp+7h]
  int v21; // [rsp+7Ch] [rbp+Bh]
  __int64 v22; // [rsp+80h] [rbp+Fh]
  __int64 v23; // [rsp+88h] [rbp+17h]
  const wchar_t *v24; // [rsp+90h] [rbp+1Fh]
  int v25; // [rsp+98h] [rbp+27h]
  int v26; // [rsp+9Ch] [rbp+2Bh]

  v7 = -1;
  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &byte_18002AE5D;
    v10 = 1;
  }
  v25 = v10;
  v24 = v8;
  v26 = 0;
  v23 = 16;
  v22 = *a6;
  v11 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_BYTE *)v11 + v7) );
    v12 = v7 + 1;
  }
  else
  {
    v11 = &byte_18002AE5D;
    v12 = 1;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180037058;
  v19 = v11;
  v20 = v12;
  v21 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v17 = *(unsigned __int16 *)(a2 + 11);
  v16 = a2 + 11;
  UserData.Reserved = 2;
  v18 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x180006200  push    rbp
0x180006202  lea     rbp, [rsp-3Fh]
0x180006207  sub     rsp, 0B0h
0x18000620e  mov     rax, cs:__security_cookie
0x180006215  xor     rax, rsp
0x180006218  mov     [rbp+3Fh+var_10], rax
0x18000621c  mov     rax, [rbp+3Fh+arg_30]
0x180006220  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006224  xor     r9d, r9d; RelatedActivityId
0x180006227  mov     r10d, 1
0x18000622d  mov     rcx, [rax]
0x180006230  test    rcx, rcx
0x180006233  jz      loc_18000631F
0x180006239  mov     rax, r8
0x18000623c  inc     rax
0x18000623f  cmp     [rcx+rax], r9b
0x180006243  jnz     short loc_18000623C
0x180006245  inc     eax
0x180006247  mov     [rbp+3Fh+var_18], eax
0x18000624a  mov     rax, [rbp+3Fh+arg_28]
0x18000624e  mov     [rbp+3Fh+var_20], rcx
0x180006252  mov     [rbp+3Fh+var_14], r9d
0x180006256  mov     [rbp+3Fh+var_28], 10h
0x18000625e  mov     rcx, [rax]
0x180006261  mov     rax, [rbp+3Fh+arg_20]
0x180006265  mov     [rbp+3Fh+var_30], rcx
0x180006269  mov     rcx, [rax]
0x18000626c  test    rcx, rcx
0x18000626f  jz      loc_18000632E
0x180006275  inc     r8
0x180006278  cmp     [rcx+r8], r9b
0x18000627c  jnz     short loc_180006275
0x18000627e  inc     r8d
0x180006281  movzx   eax, byte ptr [rdx]
0x180006284  shl     eax, 18h
0x180006287  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18000628a  movzx   eax, word ptr [rdx+1]
0x18000628e  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180006291  mov     rax, [rdx+3]
0x180006295  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180006299  mov     rax, cs:off_180037058
0x1800062a0  mov     [rbp+3Fh+var_60.Ptr], rax
0x1800062a4  mov     [rbp+3Fh+var_40], rcx
0x1800062a8  lea     rcx, [rdx+0Bh]
0x1800062ac  mov     [rbp+3Fh+var_38], r8d
0x1800062b0  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x1800062b4  mov     [rbp+3Fh+var_34], r9d
0x1800062b8  xor     r8d, r8d; ActivityId
0x1800062bb  movzx   eax, word ptr [rax]
0x1800062be  mov     [rbp+3Fh+var_60.Size], eax
0x1800062c1  movzx   eax, word ptr [rcx]
0x1800062c4  mov     [rbp+3Fh+var_48], eax
0x1800062c7  lea     rax, _TraceLoggingMetadataEnd
0x1800062ce  mov     [rbp+3Fh+var_50], rcx
0x1800062d2  lea     rcx, _TraceLoggingMetadata
0x1800062d9  sub     eax, ecx
0x1800062db  mov     dword ptr [rbp+3Fh+var_60.0Ch], 2
0x1800062e2  mov     [rbp+3Fh+var_44], r10d
0x1800062e6  mov     [rbp+3Fh+var_80], eax
0x1800062e9  mov     eax, [rbp+3Fh+var_80]
0x1800062ec  mov     rcx, cs:RegHandle; RegHandle
0x1800062f3  lea     rax, [rbp+3Fh+var_60]
0x1800062f7  mov     [rsp+0B0h+UserData], rax; UserData
0x1800062fc  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x180006304  call    cs:__imp_EventWriteTransfer
0x18000630a  mov     rcx, [rbp+3Fh+var_10]
0x18000630e  xor     rcx, rsp; StackCookie
0x180006311  call    __security_check_cookie
0x180006316  add     rsp, 0B0h
0x18000631d  pop     rbp
0x18000631e  retn
0x18000631f  lea     rcx, byte_18002AE5D
0x180006326  mov     eax, r10d
0x180006329  jmp     loc_180006247
0x18000632e  lea     rcx, byte_18002AE5D
0x180006335  mov     r8d, r10d
0x180006338  jmp     loc_180006281
```

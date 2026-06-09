# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800060b0`
- end: `0x1800061f7`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca54`

## callees

- `0x1800060b0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800061be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800061be`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 **a6,
        __int64 a7)
{
  __int64 v7; // rcx
  __int64 *v9; // r8
  __int64 v10; // rax
  int v11; // eax
  const wchar_t *v12; // rdx
  int v13; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v17; // [rsp+60h] [rbp-11h]
  int v18; // [rsp+68h] [rbp-9h]
  int v19; // [rsp+6Ch] [rbp-5h]
  const wchar_t *v20; // [rsp+70h] [rbp-1h]
  int v21; // [rsp+78h] [rbp+7h]
  int v22; // [rsp+7Ch] [rbp+Bh]
  __int64 *v23; // [rsp+80h] [rbp+Fh]
  int v24; // [rsp+88h] [rbp+17h]
  int v25; // [rsp+8Ch] [rbp+1Bh]
  __int64 v26; // [rsp+90h] [rbp+1Fh]
  __int64 v27; // [rsp+98h] [rbp+27h]

  v26 = a7;
  v7 = -1;
  v27 = 4;
  v9 = *a6;
  if ( *a6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &qword_18002AF20;
    v11 = 2;
  }
  v24 = v11;
  v23 = v9;
  v25 = 0;
  v12 = *a5;
  if ( *a5 )
  {
    do
      ++v7;
    while ( *((_BYTE *)v12 + v7) );
    v13 = v7 + 1;
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
  v21 = v13;
  v20 = v12;
  v22 = 0;
  UserData.Size = (unsigned __int16)*off_180037058;
  v18 = *(unsigned __int16 *)(a2 + 11);
  v17 = a2 + 11;
  v19 = 1;
  UserData.Reserved = 2;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x1800060b0  push    rbp
0x1800060b2  lea     rbp, [rsp-3Fh]
0x1800060b7  sub     rsp, 0B0h
0x1800060be  mov     rax, cs:__security_cookie
0x1800060c5  xor     rax, rsp
0x1800060c8  mov     [rbp+3Fh+var_10], rax
0x1800060cc  mov     rax, [rbp+3Fh+arg_30]
0x1800060d0  xor     r10d, r10d
0x1800060d3  mov     [rbp+3Fh+var_20], rax
0x1800060d7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800060db  mov     rax, [rbp+3Fh+arg_28]
0x1800060df  mov     r9, rdx
0x1800060e2  mov     [rbp+3Fh+var_18], 4
0x1800060ea  lea     r11d, [r10+2]
0x1800060ee  mov     r8, [rax]
0x1800060f1  test    r8, r8
0x1800060f4  jz      loc_1800061D9
0x1800060fa  mov     rax, rcx
0x1800060fd  inc     rax
0x180006100  cmp     [r8+rax*2], r10w
0x180006105  jnz     short loc_1800060FD
0x180006107  lea     eax, ds:2[rax*2]
0x18000610e  mov     [rbp+3Fh+var_28], eax
0x180006111  mov     rax, [rbp+3Fh+arg_20]
0x180006115  mov     [rbp+3Fh+var_30], r8
0x180006119  mov     r8d, 1
0x18000611f  mov     [rbp+3Fh+var_24], r10d
0x180006123  mov     rdx, [rax]
0x180006126  test    rdx, rdx
0x180006129  jz      loc_1800061E8
0x18000612f  inc     rcx
0x180006132  cmp     [rdx+rcx], r10b
0x180006136  jnz     short loc_18000612F
0x180006138  inc     ecx
0x18000613a  movzx   eax, byte ptr [r9]
0x18000613e  shl     eax, 18h
0x180006141  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x180006144  movzx   eax, word ptr [r9+1]
0x180006149  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18000614c  mov     rax, [r9+3]
0x180006150  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180006154  mov     rax, cs:off_180037058
0x18000615b  mov     [rbp+3Fh+var_60.Ptr], rax
0x18000615f  mov     [rbp+3Fh+var_38], ecx
0x180006162  lea     rcx, [r9+0Bh]
0x180006166  mov     [rbp+3Fh+var_40], rdx
0x18000616a  xor     r9d, r9d; RelatedActivityId
0x18000616d  mov     [rbp+3Fh+var_34], r10d
0x180006171  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x180006175  movzx   eax, word ptr [rax]
0x180006178  mov     [rbp+3Fh+var_60.Size], eax
0x18000617b  movzx   eax, word ptr [rcx]
0x18000617e  mov     [rbp+3Fh+var_48], eax
0x180006181  lea     rax, _TraceLoggingMetadataEnd
0x180006188  mov     [rbp+3Fh+var_50], rcx
0x18000618c  lea     rcx, _TraceLoggingMetadata
0x180006193  sub     eax, ecx
0x180006195  mov     [rbp+3Fh+var_44], r8d
0x180006199  mov     dword ptr [rbp+3Fh+var_60.0Ch], r11d
0x18000619d  xor     r8d, r8d; ActivityId
0x1800061a0  mov     [rbp+3Fh+var_80], eax
0x1800061a3  mov     eax, [rbp+3Fh+var_80]
0x1800061a6  mov     rcx, cs:RegHandle; RegHandle
0x1800061ad  lea     rax, [rbp+3Fh+var_60]
0x1800061b1  mov     [rsp+0B0h+UserData], rax; UserData
0x1800061b6  mov     [rsp+0B0h+UserDataCount], 5; UserDataCount
0x1800061be  call    cs:__imp_EventWriteTransfer
0x1800061c4  mov     rcx, [rbp+3Fh+var_10]
0x1800061c8  xor     rcx, rsp; StackCookie
0x1800061cb  call    __security_check_cookie
0x1800061d0  add     rsp, 0B0h
0x1800061d7  pop     rbp
0x1800061d8  retn
0x1800061d9  lea     r8, qword_18002AF20
0x1800061e0  mov     eax, r11d
0x1800061e3  jmp     loc_18000610E
0x1800061e8  lea     rdx, byte_18002AE5D
0x1800061ef  mov     ecx, r8d
0x1800061f2  jmp     loc_18000613A
```

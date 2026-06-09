# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x1800559cc`
- end: `0x180055abd`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800114c4`
- `0x18003d1f0`

## callees

- `0x1800559cc`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055a9b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055a9b`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int8 *v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+60h] [rbp-20h]
  int v14; // [rsp+64h] [rbp-1Ch]
  int *v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+70h] [rbp-10h]
  int v17; // [rsp+74h] [rbp-Ch]

  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_1800DB714;
    v8 = 2;
  }
  v16 = v8;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v15 = v6;
  v17 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v13 = *(unsigned __int16 *)(a2 + 11);
  v12 = a2 + 11;
  UserData.Reserved = 2;
  v14 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x1800559cc  push    rbp
0x1800559ce  mov     rbp, rsp
0x1800559d1  sub     rsp, 80h
0x1800559d8  mov     rax, cs:__security_cookie
0x1800559df  xor     rax, rsp
0x1800559e2  mov     [rbp+var_8], rax
0x1800559e6  mov     rax, [rbp+arg_20]
0x1800559ea  mov     r10, rcx
0x1800559ed  xor     r8d, r8d; ActivityId
0x1800559f0  mov     r9d, 2
0x1800559f6  mov     rcx, [rax]
0x1800559f9  test    rcx, rcx
0x1800559fc  jz      short loc_180055A15
0x1800559fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055a02  inc     rax
0x180055a05  cmp     [rcx+rax*2], r8w
0x180055a0a  jnz     short loc_180055A02
0x180055a0c  lea     eax, ds:2[rax*2]
0x180055a13  jmp     short loc_180055A1F
0x180055a15  lea     rcx, dword_1800DB714
0x180055a1c  mov     eax, r9d
0x180055a1f  mov     [rbp+var_10], eax
0x180055a22  movzx   eax, byte ptr [rdx]
0x180055a25  shl     eax, 18h
0x180055a28  mov     dword ptr [rbp+EventDescriptor.Id], eax
0x180055a2b  movzx   eax, word ptr [rdx+1]
0x180055a2f  mov     dword ptr [rbp+EventDescriptor.Level], eax
0x180055a32  mov     rax, [rdx+3]
0x180055a36  mov     [rbp+EventDescriptor.Keyword], rax
0x180055a3a  mov     rax, [r10+8]
0x180055a3e  mov     [rbp+var_38.Ptr], rax
0x180055a42  mov     [rbp+var_18], rcx
0x180055a46  lea     rcx, [rdx+0Bh]
0x180055a4a  mov     [rbp+var_C], r8d
0x180055a4e  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180055a52  movzx   eax, word ptr [rax]
0x180055a55  mov     [rbp+var_38.Size], eax
0x180055a58  movzx   eax, word ptr [rcx]
0x180055a5b  mov     [rbp+var_20], eax
0x180055a5e  lea     rax, _TraceLoggingMetadataEnd
0x180055a65  mov     [rbp+var_28], rcx
0x180055a69  lea     rcx, _TraceLoggingMetadata
0x180055a70  sub     eax, ecx
0x180055a72  mov     dword ptr [rbp+var_38.0Ch], r9d
0x180055a76  mov     [rbp+var_1C], 1
0x180055a7d  xor     r9d, r9d; RelatedActivityId
0x180055a80  mov     [rbp+var_50], eax
0x180055a83  mov     eax, [rbp+var_50]
0x180055a86  mov     rcx, [r10+20h]; RegHandle
0x180055a8a  lea     rax, [rbp+var_38]
0x180055a8e  mov     [rsp+80h+UserData], rax; UserData
0x180055a93  mov     [rsp+80h+UserDataCount], 3; UserDataCount
0x180055a9b  call    cs:__imp_EventWriteTransfer
0x180055aa2  nop     dword ptr [rax+rax+00h]
0x180055aa7  mov     rcx, [rbp+var_8]
0x180055aab  xor     rcx, rsp; StackCookie
0x180055aae  call    __security_check_cookie
0x180055ab3  add     rsp, 80h
0x180055aba  pop     rbp
0x180055abb  retn
```

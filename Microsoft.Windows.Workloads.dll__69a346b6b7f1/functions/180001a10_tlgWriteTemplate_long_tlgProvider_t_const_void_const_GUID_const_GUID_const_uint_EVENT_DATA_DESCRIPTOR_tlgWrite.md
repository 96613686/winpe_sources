# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001a10`
- end: `0x180001b90`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z`
- size: `384`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, const wchar_t **, __int64 *, const wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180023860`
- `0x180023c50`

## callees

- `0x180001a10`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001b72`
- `ADVAPI32!EventWriteTransfer` at `0x180001b72`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6,
        const wchar_t **a7)
{
  const wchar_t *v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // ecx
  const wchar_t *v14; // rdx
  int v15; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 *v19; // [rsp+60h] [rbp-58h]
  int v20; // [rsp+68h] [rbp-50h]
  int v21; // [rsp+6Ch] [rbp-4Ch]
  const wchar_t *v22; // [rsp+70h] [rbp-48h]
  int v23; // [rsp+78h] [rbp-40h]
  int v24; // [rsp+7Ch] [rbp-3Ch]
  __int64 v25; // [rsp+80h] [rbp-38h]
  __int64 v26; // [rsp+88h] [rbp-30h]
  const wchar_t *v27; // [rsp+90h] [rbp-28h]
  int v28; // [rsp+98h] [rbp-20h]
  int v29; // [rsp+9Ch] [rbp-1Ch]

  v9 = *a7;
  v10 = -1;
  if ( *a7 )
  {
    v11 = -1;
    do
      v12 = v9[++v11] == 0;
    while ( !v12 );
    v13 = 2 * v11 + 2;
  }
  else
  {
    v9 = &Src;
    v13 = 2;
  }
  v28 = v13;
  v27 = v9;
  v29 = 0;
  v26 = 16;
  v25 = *a6;
  v14 = *a5;
  if ( *a5 )
  {
    do
      v12 = v14[++v10] == 0;
    while ( !v12 );
    v15 = 2 * v10 + 2;
  }
  else
  {
    v14 = &Src;
    v15 = 2;
  }
  v23 = v15;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v22 = v14;
  v24 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v20 = *(unsigned __int16 *)(a2 + 11);
  v19 = a2 + 11;
  UserData.Reserved = 2;
  v21 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x180001a10  sub     rsp, 0B8h
0x180001a17  mov     rax, cs:__security_cookie
0x180001a1e  xor     rax, rsp
0x180001a21  mov     [rsp+0B8h+var_18], rax
0x180001a29  mov     rax, [rsp+0B8h+arg_30]
0x180001a31  mov     r9, rdx
0x180001a34  mov     r10, rcx
0x180001a37  mov     r8, [rax]
0x180001a3a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001a41  test    r8, r8
0x180001a44  jz      short loc_180001A66
0x180001a46  mov     rcx, rax
0x180001a49  nop     dword ptr [rax+00000000h]
0x180001a50  cmp     word ptr [r8+rcx*2+2], 0
0x180001a57  lea     rcx, [rcx+1]
0x180001a5b  jnz     short loc_180001A50
0x180001a5d  lea     ecx, ds:2[rcx*2]
0x180001a64  jmp     short loc_180001A72
0x180001a66  lea     r8, Src
0x180001a6d  mov     ecx, 2
0x180001a72  mov     [rsp+0B8h+var_20], ecx
0x180001a79  mov     rcx, [rsp+0B8h+arg_28]
0x180001a81  mov     [rsp+0B8h+var_28], r8
0x180001a89  xor     r8d, r8d; ActivityId
0x180001a8c  mov     [rsp+0B8h+var_1C], r8d
0x180001a94  mov     [rsp+0B8h+var_30], 10h
0x180001aa0  mov     rdx, [rcx]
0x180001aa3  mov     rcx, [rsp+0B8h+arg_20]
0x180001aab  mov     [rsp+0B8h+var_38], rdx
0x180001ab3  mov     rdx, [rcx]
0x180001ab6  test    rdx, rdx
0x180001ab9  jz      short loc_180001AD5
0x180001abb  nop     dword ptr [rax+rax+00h]
0x180001ac0  cmp     [rdx+rax*2+2], r8w
0x180001ac6  lea     rax, [rax+1]
0x180001aca  jnz     short loc_180001AC0
0x180001acc  lea     eax, ds:2[rax*2]
0x180001ad3  jmp     short loc_180001AE1
0x180001ad5  lea     rdx, Src
0x180001adc  mov     eax, 2
0x180001ae1  mov     [rsp+0B8h+var_40], eax
0x180001ae5  lea     rcx, [r9+0Bh]
0x180001ae9  movzx   eax, byte ptr [r9]
0x180001aed  shl     eax, 18h
0x180001af0  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], eax
0x180001af4  movzx   eax, word ptr [r9+1]
0x180001af9  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x180001afd  mov     rax, [r9+3]
0x180001b01  xor     r9d, r9d; RelatedActivityId
0x180001b04  mov     [rsp+0B8h+EventDescriptor.Keyword], rax
0x180001b09  mov     rax, [r10+8]
0x180001b0d  mov     [rsp+0B8h+var_68.Ptr], rax
0x180001b12  mov     [rsp+0B8h+var_48], rdx
0x180001b17  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x180001b1c  mov     [rsp+0B8h+var_3C], r8d
0x180001b21  movzx   eax, word ptr [rax]
0x180001b24  mov     [rsp+0B8h+var_68.Size], eax
0x180001b28  movzx   eax, word ptr [rcx]
0x180001b2b  mov     [rsp+0B8h+var_50], eax
0x180001b2f  lea     rax, _TraceLoggingMetadataEnd
0x180001b36  mov     [rsp+0B8h+var_58], rcx
0x180001b3b  lea     rcx, _TraceLoggingMetadata
0x180001b42  sub     eax, ecx
0x180001b44  mov     dword ptr [rsp+0B8h+var_68.0Ch], 2
0x180001b4c  mov     [rsp+0B8h+var_4C], 1
0x180001b54  mov     [rsp+0B8h+var_88], eax
0x180001b58  mov     eax, [rsp+0B8h+var_88]
0x180001b5c  mov     rcx, [r10+20h]; RegHandle
0x180001b60  lea     rax, [rsp+0B8h+var_68]
0x180001b65  mov     [rsp+0B8h+UserData], rax; UserData
0x180001b6a  mov     [rsp+0B8h+UserDataCount], 5; UserDataCount
0x180001b72  call    cs:__imp_EventWriteTransfer
0x180001b78  mov     rcx, [rsp+0B8h+var_18]
0x180001b80  xor     rcx, rsp; StackCookie
0x180001b83  call    __security_check_cookie
0x180001b88  add     rsp, 0B8h
0x180001b8f  retn
```

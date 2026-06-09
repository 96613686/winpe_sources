# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByRef<16> const &)

- ea: `0x1800018f0`
- end: `0x180001a0e`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `286`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, const wchar_t **, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800229c0`
- `0x180023860`

## callees

- `0x1800018f0`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800019f0`
- `ADVAPI32!EventWriteTransfer` at `0x1800019f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const wchar_t **a5,
        __int64 *a6)
{
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  int v10; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-48h]
  int v15; // [rsp+68h] [rbp-40h]
  int v16; // [rsp+6Ch] [rbp-3Ch]
  const wchar_t *v17; // [rsp+70h] [rbp-38h]
  int v18; // [rsp+78h] [rbp-30h]
  int v19; // [rsp+7Ch] [rbp-2Ch]
  __int64 v20; // [rsp+80h] [rbp-28h]
  __int64 v21; // [rsp+88h] [rbp-20h]

  v21 = 16;
  v20 = *a6;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    while ( v7[++v8] != 0 )
      ;
    v10 = 2 * v8 + 2;
  }
  else
  {
    v7 = &Src;
    v10 = 2;
  }
  v18 = v10;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v17 = v7;
  v19 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  UserData.Reserved = 2;
  v16 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
}

```

## disassembly

```asm
0x1800018f0  mov     r11, rsp
0x1800018f3  sub     rsp, 0A8h
0x1800018fa  mov     rax, cs:__security_cookie
0x180001901  xor     rax, rsp
0x180001904  mov     [rsp+0A8h+var_18], rax
0x18000190c  mov     rax, [rsp+0A8h+arg_28]
0x180001914  mov     r10, rcx
0x180001917  xor     r8d, r8d; ActivityId
0x18000191a  mov     qword ptr [r11-20h], 10h
0x180001922  mov     rcx, [rax]
0x180001925  mov     rax, [rsp+0A8h+arg_20]
0x18000192d  mov     [r11-28h], rcx
0x180001931  mov     rcx, [rax]
0x180001934  test    rcx, rcx
0x180001937  jz      short loc_180001955
0x180001939  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001940  cmp     [rcx+rax*2+2], r8w
0x180001946  lea     rax, [rax+1]
0x18000194a  jnz     short loc_180001940
0x18000194c  lea     eax, ds:2[rax*2]
0x180001953  jmp     short loc_180001961
0x180001955  lea     rcx, Src
0x18000195c  mov     eax, 2
0x180001961  mov     [rsp+0A8h+var_30], eax
0x180001965  xor     r9d, r9d; RelatedActivityId
0x180001968  movzx   eax, byte ptr [rdx]
0x18000196b  shl     eax, 18h
0x18000196e  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], eax
0x180001972  movzx   eax, word ptr [rdx+1]
0x180001976  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x18000197a  mov     rax, [rdx+3]
0x18000197e  mov     [rsp+0A8h+EventDescriptor.Keyword], rax
0x180001983  mov     rax, [r10+8]
0x180001987  mov     [rsp+0A8h+var_58.Ptr], rax
0x18000198c  mov     [rsp+0A8h+var_38], rcx
0x180001991  lea     rcx, [rdx+0Bh]
0x180001995  mov     [rsp+0A8h+var_2C], r8d
0x18000199a  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18000199f  movzx   eax, word ptr [rax]
0x1800019a2  mov     [rsp+0A8h+var_58.Size], eax
0x1800019a6  movzx   eax, word ptr [rcx]
0x1800019a9  mov     [rsp+0A8h+var_40], eax
0x1800019ad  lea     rax, _TraceLoggingMetadataEnd
0x1800019b4  mov     [rsp+0A8h+var_48], rcx
0x1800019b9  lea     rcx, _TraceLoggingMetadata
0x1800019c0  sub     eax, ecx
0x1800019c2  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x1800019ca  mov     [rsp+0A8h+var_3C], 1
0x1800019d2  mov     [rsp+0A8h+var_78], eax
0x1800019d6  mov     eax, [rsp+0A8h+var_78]
0x1800019da  mov     rcx, [r10+20h]; RegHandle
0x1800019de  lea     rax, [rsp+0A8h+var_58]
0x1800019e3  mov     [rsp+0A8h+UserData], rax; UserData
0x1800019e8  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x1800019f0  call    cs:__imp_EventWriteTransfer
0x1800019f6  mov     rcx, [rsp+0A8h+var_18]
0x1800019fe  xor     rcx, rsp; StackCookie
0x180001a01  call    __security_check_cookie
0x180001a06  add     rsp, 0A8h
0x180001a0d  retn
```

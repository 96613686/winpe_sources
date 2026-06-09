# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001000`
- end: `0x18000111e`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `286`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64 **, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180060020`
- `0x18006019c`
- `0x180060320`
- `0x180060760`
- `0x1800608dc`
- `0x180060a50`
- `0x180060bdc`
- `0x180060f6c`
- `0x180062600`
- `0x180062770`
- `0x1800628ec`
- `0x180062ef0`
- `0x180063060`

## callees

- `0x180001000`
- `0x18004c070`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001100`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001100`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v10; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v14; // [rsp+60h] [rbp-48h]
  int v15; // [rsp+68h] [rbp-40h]
  int v16; // [rsp+6Ch] [rbp-3Ch]
  __int64 *v17; // [rsp+70h] [rbp-38h]
  int v18; // [rsp+78h] [rbp-30h]
  int v19; // [rsp+7Ch] [rbp-2Ch]
  __int64 v20; // [rsp+80h] [rbp-28h]
  __int64 v21; // [rsp+88h] [rbp-20h]

  v20 = a6;
  v21 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    while ( *((_WORD *)v7 + ++v8) != 0 )
      ;
    v10 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_18006D0D8;
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
0x180001000  mov     r11, rsp
0x180001003  sub     rsp, 0A8h
0x18000100a  mov     rax, cs:__security_cookie
0x180001011  xor     rax, rsp
0x180001014  mov     [rsp+0A8h+var_18], rax
0x18000101c  mov     rax, [rsp+0A8h+arg_28]
0x180001024  mov     r10, rcx
0x180001027  mov     [r11-28h], rax
0x18000102b  xor     r8d, r8d; ActivityId
0x18000102e  mov     rax, [rsp+0A8h+arg_20]
0x180001036  mov     qword ptr [r11-20h], 4
0x18000103e  mov     rcx, [rax]
0x180001041  test    rcx, rcx
0x180001044  jz      short loc_180001065
0x180001046  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000104d  nop     dword ptr [rax]
0x180001050  cmp     [rcx+rax*2+2], r8w
0x180001056  lea     rax, [rax+1]
0x18000105a  jnz     short loc_180001050
0x18000105c  lea     eax, ds:2[rax*2]
0x180001063  jmp     short loc_180001071
0x180001065  lea     rcx, qword_18006D0D8
0x18000106c  mov     eax, 2
0x180001071  mov     [rsp+0A8h+var_30], eax
0x180001075  xor     r9d, r9d; RelatedActivityId
0x180001078  movzx   eax, byte ptr [rdx]
0x18000107b  shl     eax, 18h
0x18000107e  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], eax
0x180001082  movzx   eax, word ptr [rdx+1]
0x180001086  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x18000108a  mov     rax, [rdx+3]
0x18000108e  mov     [rsp+0A8h+EventDescriptor.Keyword], rax
0x180001093  mov     rax, [r10+8]
0x180001097  mov     [rsp+0A8h+var_58.Ptr], rax
0x18000109c  mov     [rsp+0A8h+var_38], rcx
0x1800010a1  lea     rcx, [rdx+0Bh]
0x1800010a5  mov     [rsp+0A8h+var_2C], r8d
0x1800010aa  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x1800010af  movzx   eax, word ptr [rax]
0x1800010b2  mov     [rsp+0A8h+var_58.Size], eax
0x1800010b6  movzx   eax, word ptr [rcx]
0x1800010b9  mov     [rsp+0A8h+var_40], eax
0x1800010bd  lea     rax, _TraceLoggingMetadataEnd
0x1800010c4  mov     [rsp+0A8h+var_48], rcx
0x1800010c9  lea     rcx, _TraceLoggingMetadata
0x1800010d0  sub     eax, ecx
0x1800010d2  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x1800010da  mov     [rsp+0A8h+var_3C], 1
0x1800010e2  mov     [rsp+0A8h+var_78], eax
0x1800010e6  mov     eax, [rsp+0A8h+var_78]
0x1800010ea  mov     rcx, [r10+20h]; RegHandle
0x1800010ee  lea     rax, [rsp+0A8h+var_58]
0x1800010f3  mov     [rsp+0A8h+UserData], rax; UserData
0x1800010f8  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x180001100  call    cs:__imp_EventWriteTransfer
0x180001106  mov     rcx, [rsp+0A8h+var_18]
0x18000110e  xor     rcx, rsp; StackCookie
0x180001111  call    __security_check_cookie
0x180001116  add     rsp, 0A8h
0x18000111d  retn
```

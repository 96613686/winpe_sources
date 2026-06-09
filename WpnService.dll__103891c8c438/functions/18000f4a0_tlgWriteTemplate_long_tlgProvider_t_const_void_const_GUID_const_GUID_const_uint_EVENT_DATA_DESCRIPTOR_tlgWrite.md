# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000f4a0`
- end: `0x18000f592`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `242`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008210`

## callees

- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f574`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f574`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // eax
  EVENT_DESCRIPTOR v9; // [rsp+38h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 *v11; // [rsp+60h] [rbp-58h]
  int v12; // [rsp+68h] [rbp-50h]
  int v13; // [rsp+6Ch] [rbp-4Ch]
  __int64 v14; // [rsp+70h] [rbp-48h]
  __int64 v15; // [rsp+78h] [rbp-40h]
  __int64 v16; // [rsp+80h] [rbp-38h]
  __int64 v17; // [rsp+88h] [rbp-30h]
  __int64 v18; // [rsp+90h] [rbp-28h]
  __int64 v19; // [rsp+98h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v14 = a5;
  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v9.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v19 = 8;
  v17 = 4;
  v15 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v7 = *(unsigned __int16 *)(a2 + 11);
  UserData.Reserved = 2;
  v11 = a2 + 11;
  v12 = v7;
  v13 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v9, a3, a4, 5u, &UserData);
}

```

## disassembly

```asm
0x18000f4a0  mov     r11, rsp
0x18000f4a3  sub     rsp, 0B8h
0x18000f4aa  mov     rax, cs:__security_cookie
0x18000f4b1  xor     rax, rsp
0x18000f4b4  mov     [rsp+0B8h+var_18], rax
0x18000f4bc  mov     rax, [rsp+0B8h+arg_30]
0x18000f4c4  mov     r10, rcx
0x18000f4c7  mov     [r11-28h], rax
0x18000f4cb  lea     rcx, [rdx+0Bh]
0x18000f4cf  mov     rax, [rsp+0B8h+arg_28]
0x18000f4d7  mov     [r11-38h], rax
0x18000f4db  mov     rax, [rsp+0B8h+arg_20]
0x18000f4e3  mov     [r11-48h], rax
0x18000f4e7  movzx   eax, byte ptr [rdx]
0x18000f4ea  shl     eax, 18h
0x18000f4ed  mov     [rsp+0B8h+var_80], eax
0x18000f4f1  movzx   eax, word ptr [rdx+1]
0x18000f4f5  mov     [rsp+0B8h+var_7C], eax
0x18000f4f9  mov     rax, [rdx+3]
0x18000f4fd  lea     rdx, [r11-80h]; EventDescriptor
0x18000f501  mov     [r11-78h], rax
0x18000f505  mov     rax, [r10+8]
0x18000f509  mov     [r11-68h], rax
0x18000f50d  mov     qword ptr [r11-20h], 8
0x18000f515  mov     qword ptr [r11-30h], 4
0x18000f51d  mov     qword ptr [r11-40h], 8
0x18000f525  movzx   eax, word ptr [rax]
0x18000f528  mov     [rsp+0B8h+var_60], eax
0x18000f52c  movzx   eax, word ptr [rcx]
0x18000f52f  mov     [rsp+0B8h+var_5C], 2
0x18000f537  mov     [r11-58h], rcx
0x18000f53b  lea     rcx, _TraceLoggingMetadata
0x18000f542  mov     [rsp+0B8h+var_50], eax
0x18000f546  lea     rax, _TraceLoggingMetadataEnd
0x18000f54d  sub     eax, ecx
0x18000f54f  mov     [rsp+0B8h+var_4C], 1
0x18000f557  mov     [rsp+0B8h+var_88], eax
0x18000f55b  mov     eax, [rsp+0B8h+var_88]
0x18000f55f  mov     rcx, [r10+20h]; RegHandle
0x18000f563  lea     rax, [r11-68h]
0x18000f567  mov     [rsp+0B8h+UserData], rax; UserData
0x18000f56c  mov     [rsp+0B8h+UserDataCount], 5; UserDataCount
0x18000f574  call    cs:__imp_EventWriteTransfer
0x18000f57a  mov     rcx, [rsp+0B8h+var_18]
0x18000f582  xor     rcx, rsp; StackCookie
0x18000f585  call    __security_check_cookie
0x18000f58a  add     rsp, 0B8h
0x18000f591  retn
```

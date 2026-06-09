# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000f2f0`
- end: `0x18000f3e2`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `242`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ac4`
- `0x18000cd88`
- `0x180018fa0`
- `0x180019d80`
- `0x180019fc0`
- `0x18001a200`
- `0x18001a440`
- `0x18001a680`
- `0x18001a8c0`
- `0x18001ab00`
- `0x18001ad40`
- `0x18001c050`
- `0x18001c650`
- `0x18001c890`
- `0x18001cad0`
- `0x18001cd10`
- `0x18001d7b0`
- `0x18001d9f0`
- `0x18001ece0`
- `0x180020c44`
- `0x180023efc`
- `0x18002c760`
- `0x18002c990`
- `0x18002d7e0`
- `0x18002da20`
- `0x18002e9e4`
- `0x18002eb48`
- `0x18002ebf0`
- `0x18002ee30`
- `0x18002f070`
- `0x18002f2b0`
- `0x180030620`
- `0x180030850`
- `0x180030a90`
- `0x180030cd0`
- `0x180030f10`
- `0x180032920`
- `0x180033880`
- `0x180033ac0`
- `0x180033d00`

## callees

- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f3c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f3c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
  v19 = 4;
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
0x18000f2f0  mov     r11, rsp
0x18000f2f3  sub     rsp, 0B8h
0x18000f2fa  mov     rax, cs:__security_cookie
0x18000f301  xor     rax, rsp
0x18000f304  mov     [rsp+0B8h+var_18], rax
0x18000f30c  mov     rax, [rsp+0B8h+arg_30]
0x18000f314  mov     r10, rcx
0x18000f317  mov     [r11-28h], rax
0x18000f31b  lea     rcx, [rdx+0Bh]
0x18000f31f  mov     rax, [rsp+0B8h+arg_28]
0x18000f327  mov     [r11-38h], rax
0x18000f32b  mov     rax, [rsp+0B8h+arg_20]
0x18000f333  mov     [r11-48h], rax
0x18000f337  movzx   eax, byte ptr [rdx]
0x18000f33a  shl     eax, 18h
0x18000f33d  mov     [rsp+0B8h+var_80], eax
0x18000f341  movzx   eax, word ptr [rdx+1]
0x18000f345  mov     [rsp+0B8h+var_7C], eax
0x18000f349  mov     rax, [rdx+3]
0x18000f34d  lea     rdx, [r11-80h]; EventDescriptor
0x18000f351  mov     [r11-78h], rax
0x18000f355  mov     rax, [r10+8]
0x18000f359  mov     [r11-68h], rax
0x18000f35d  mov     qword ptr [r11-20h], 4
0x18000f365  mov     qword ptr [r11-30h], 4
0x18000f36d  mov     qword ptr [r11-40h], 8
0x18000f375  movzx   eax, word ptr [rax]
0x18000f378  mov     [rsp+0B8h+var_60], eax
0x18000f37c  movzx   eax, word ptr [rcx]
0x18000f37f  mov     [rsp+0B8h+var_5C], 2
0x18000f387  mov     [r11-58h], rcx
0x18000f38b  lea     rcx, _TraceLoggingMetadata
0x18000f392  mov     [rsp+0B8h+var_50], eax
0x18000f396  lea     rax, _TraceLoggingMetadataEnd
0x18000f39d  sub     eax, ecx
0x18000f39f  mov     [rsp+0B8h+var_4C], 1
0x18000f3a7  mov     [rsp+0B8h+var_88], eax
0x18000f3ab  mov     eax, [rsp+0B8h+var_88]
0x18000f3af  mov     rcx, [r10+20h]; RegHandle
0x18000f3b3  lea     rax, [r11-68h]
0x18000f3b7  mov     [rsp+0B8h+UserData], rax; UserData
0x18000f3bc  mov     [rsp+0B8h+UserDataCount], 5; UserDataCount
0x18000f3c4  call    cs:__imp_EventWriteTransfer
0x18000f3ca  mov     rcx, [rsp+0B8h+var_18]
0x18000f3d2  xor     rcx, rsp; StackCookie
0x18000f3d5  call    __security_check_cookie
0x18000f3da  add     rsp, 0B8h
0x18000f3e1  retn
```

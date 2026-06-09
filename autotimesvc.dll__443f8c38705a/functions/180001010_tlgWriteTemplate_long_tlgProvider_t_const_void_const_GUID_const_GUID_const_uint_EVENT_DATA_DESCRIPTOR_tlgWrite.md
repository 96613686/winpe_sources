# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x180001010`
- end: `0x18000104c`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c64`
- `0x1800061ac`
- `0x180006350`
- `0x180006598`
- `0x180007220`
- `0x180007534`
- `0x180007a5c`
- `0x1800084c4`
- `0x180008798`
- `0x18000891c`
- `0x1800096b0`
- `0x1800098d4`
- `0x180009bb8`
- `0x180009d88`
- `0x18000b118`
- `0x18000b264`
- `0x18000c900`
- `0x18000d178`
- `0x18000d330`
- `0x18000fca0`
- `0x18001020c`
- `0x1800102c4`
- `0x180010578`
- `0x180010800`
- `0x180010ac0`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 68h
0x180001014  mov     rax, cs:__security_cookie
0x18000101b  xor     rax, rsp
0x18000101e  mov     [rsp+68h+var_18], rax
0x180001023  lea     rax, [rsp+68h+var_38]
0x180001028  mov     [rsp+68h+var_40], rax
0x18000102d  mov     [rsp+68h+var_48], 2
0x180001035  call    _tlgWriteTransfer_EventWriteTransfer
0x18000103a  mov     rcx, [rsp+68h+var_18]
0x18000103f  xor     rcx, rsp; StackCookie
0x180001042  call    __security_check_cookie
0x180001047  add     rsp, 68h
0x18000104b  retn
```

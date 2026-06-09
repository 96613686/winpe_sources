# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180001220`
- end: `0x18000127f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `95`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a8588`
- `0x1800a8df0`
- `0x1800aa7f0`
- `0x1800aafe0`
- `0x1800ab5b0`
- `0x1800acd7c`

## callees

- `0x18000117c`
- `0x180002a00`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]

  v7 = a5;
  v8 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800E50F0, a2, 0, 0, 3u, &v6);
}

```

## disassembly

```asm
0x180001220  mov     r11, rsp
0x180001223  sub     rsp, 78h
0x180001227  mov     rax, cs:__security_cookie
0x18000122e  xor     rax, rsp
0x180001231  mov     [rsp+78h+var_18], rax
0x180001236  mov     rax, [rsp+78h+arg_20]
0x18000123e  lea     rcx, dword_1800E50F0
0x180001245  mov     [r11-28h], rax
0x180001249  xor     r9d, r9d
0x18000124c  lea     rax, [r11-48h]
0x180001250  mov     qword ptr [r11-20h], 8
0x180001258  mov     [r11-50h], rax
0x18000125c  xor     r8d, r8d
0x18000125f  mov     [rsp+78h+var_58], 3
0x180001267  call    _tlgWriteTransfer_EventWriteTransfer
0x18000126c  mov     rcx, [rsp+78h+var_18]
0x180001271  xor     rcx, rsp; StackCookie
0x180001274  call    __security_check_cookie
0x180001279  add     rsp, 78h
0x18000127d  retn
```

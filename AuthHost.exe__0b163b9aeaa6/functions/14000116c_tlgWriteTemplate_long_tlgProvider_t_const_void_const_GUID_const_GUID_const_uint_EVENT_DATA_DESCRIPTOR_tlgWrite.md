# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000116c`
- end: `0x1400011dd`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004160`

## callees

- `0x140001218`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h]
  __int64 v9; // [rsp+58h] [rbp-30h]
  __int64 v10; // [rsp+60h] [rbp-28h]
  __int64 v11; // [rsp+68h] [rbp-20h]

  v10 = a6;
  v8 = a5;
  v11 = 4;
  v9 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14001D000, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x14000116c  mov     r11, rsp
0x14000116f  sub     rsp, 88h
0x140001176  mov     rax, cs:__security_cookie
0x14000117d  xor     rax, rsp
0x140001180  mov     [rsp+88h+var_18], rax
0x140001185  mov     rax, [rsp+88h+arg_28]
0x14000118d  mov     ecx, 4
0x140001192  mov     [r11-28h], rax
0x140001196  xor     r9d, r9d
0x140001199  mov     rax, [rsp+88h+arg_20]
0x1400011a1  xor     r8d, r8d
0x1400011a4  mov     [r11-38h], rax
0x1400011a8  lea     rax, [r11-58h]
0x1400011ac  mov     [r11-60h], rax
0x1400011b0  mov     [rsp+88h+var_68], ecx
0x1400011b4  mov     [r11-20h], rcx
0x1400011b8  mov     [r11-30h], rcx
0x1400011bc  lea     rcx, dword_14001D000
0x1400011c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400011c8  mov     rcx, [rsp+88h+var_18]
0x1400011cd  xor     rcx, rsp; StackCookie
0x1400011d0  call    __security_check_cookie
0x1400011d5  add     rsp, 88h
0x1400011dc  retn
```

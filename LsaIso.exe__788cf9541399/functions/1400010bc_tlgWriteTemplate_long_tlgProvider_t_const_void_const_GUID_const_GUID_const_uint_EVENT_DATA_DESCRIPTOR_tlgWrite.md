# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x1400010bc`
- end: `0x140001113`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400064a0`
- `0x14000685c`
- `0x140014d6c`

## callees

- `0x140001bc0`
- `0x140038d10`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
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
  v8 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 3u, &v6);
}

```

## disassembly

```asm
0x1400010bc  mov     r11, rsp
0x1400010bf  sub     rsp, 78h
0x1400010c3  mov     rax, cs:__security_cookie
0x1400010ca  xor     rax, rsp
0x1400010cd  mov     [rsp+78h+var_18], rax
0x1400010d2  mov     rax, [rsp+78h+arg_20]
0x1400010da  xor     r9d, r9d
0x1400010dd  mov     [r11-28h], rax
0x1400010e1  xor     r8d, r8d
0x1400010e4  lea     rax, [r11-48h]
0x1400010e8  mov     qword ptr [r11-20h], 4
0x1400010f0  mov     [r11-50h], rax
0x1400010f4  mov     [rsp+78h+var_58], 3
0x1400010fc  call    _tlgWriteTransfer_EventWriteTransfer
0x140001101  mov     rcx, [rsp+78h+var_18]
0x140001106  xor     rcx, rsp; StackCookie
0x140001109  call    __security_check_cookie
0x14000110e  add     rsp, 78h
0x140001112  retn
```

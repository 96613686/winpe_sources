# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001090`
- end: `0x180001102`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `114`
- prototype: ``
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x180006de0`
- `0x180007030`
- `0x1800075c0`
- `0x180007850`
- `0x180007bb0`
- `0x180007d00`
- `0x180007e30`
- `0x180008270`
- `0x180008580`
- `0x180008840`
- `0x1800089b0`
- `0x180008c10`
- `0x180008cc0`
- `0x180008d90`
- `0x180008ff0`
- `0x1800091b0`
- `0x180009620`
- `0x1800097e0`
- `0x1800099a0`
- `0x180009ca0`
- `0x18000a320`
- `0x18000a570`
- `0x18000abc0`
- `0x18000ad70`
- `0x18000c210`
- `0x18000c4a0`
- `0x18000c7b0`
- `0x18000c980`
- `0x18000ce20`
- `0x18000d4f0`
- `0x18000e1fc`
- `0x18000e314`
- `0x18000e3f4`
- `0x18000ed10`
- `0x18000ed88`
- `0x18000ee84`
- `0x18000ff68`
- `0x180011fe0`
- `0x18001209c`
- `0x1800122f4`
- `0x180012374`
- `0x1800129e4`
- `0x180012a88`

## callees

- `0x180001108`
- `0x180001b90`

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
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x180001090  mov     r11, rsp
0x180001093  sub     rsp, 88h
0x18000109a  mov     rax, cs:__security_cookie
0x1800010a1  xor     rax, rsp
0x1800010a4  mov     [rsp+88h+var_18], rax
0x1800010a9  mov     rax, [rsp+88h+arg_28]
0x1800010b1  mov     ecx, 4
0x1800010b6  mov     [r11-28h], rax
0x1800010ba  xor     r9d, r9d
0x1800010bd  mov     rax, [rsp+88h+arg_20]
0x1800010c5  xor     r8d, r8d
0x1800010c8  mov     [r11-38h], rax
0x1800010cc  lea     rax, [r11-58h]
0x1800010d0  mov     [r11-60h], rax
0x1800010d4  mov     [rsp+88h+var_68], ecx
0x1800010d8  mov     [r11-20h], rcx
0x1800010dc  mov     [r11-30h], rcx
0x1800010e0  lea     rcx, dword_18004AE90
0x1800010e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010ec  mov     rcx, [rsp+88h+var_18]
0x1800010f1  xor     rcx, rsp; StackCookie
0x1800010f4  call    __security_check_cookie
0x1800010f9  add     rsp, 88h
0x180001100  retn
```

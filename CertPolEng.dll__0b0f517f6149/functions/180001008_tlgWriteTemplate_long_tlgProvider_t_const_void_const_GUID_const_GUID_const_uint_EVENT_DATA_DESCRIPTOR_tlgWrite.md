# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)

- ea: `0x180001008`
- end: `0x180001062`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800171f0`
- `0x18001725c`

## callees

- `0x180007e00`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[5] = 16;
  v6[4] = *a5;
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 3, (__int64)v6);
}

```

## disassembly

```asm
0x180001008  mov     r11, rsp
0x18000100b  sub     rsp, 78h
0x18000100f  mov     rax, cs:__security_cookie
0x180001016  xor     rax, rsp
0x180001019  mov     [rsp+78h+var_18], rax
0x18000101e  mov     rax, [rsp+78h+arg_20]
0x180001026  xor     r9d, r9d
0x180001029  mov     qword ptr [r11-20h], 10h
0x180001031  mov     r8, [rax]
0x180001034  lea     rax, [r11-48h]
0x180001038  mov     [r11-28h], r8
0x18000103c  xor     r8d, r8d
0x18000103f  mov     [r11-50h], rax
0x180001043  mov     [rsp+78h+var_58], 3
0x18000104b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180001050  mov     rcx, [rsp+78h+var_18]
0x180001055  xor     rcx, rsp; StackCookie
0x180001058  call    __security_check_cookie
0x18000105d  add     rsp, 78h
0x180001061  retn
```

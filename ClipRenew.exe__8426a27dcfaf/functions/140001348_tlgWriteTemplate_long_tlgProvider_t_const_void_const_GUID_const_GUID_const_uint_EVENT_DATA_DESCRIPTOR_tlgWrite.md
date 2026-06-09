# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001348`
- end: `0x1400013bd`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x140001498`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD v7[8]; // [rsp+30h] [rbp-58h] BYREF

  v7[6] = a6;
  v7[4] = a5;
  v7[5] = 4;
  v7[7] = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140019000, a2, 0, 0, 4, v7);
}

```

## disassembly

```asm
0x140001348  mov     r11, rsp
0x14000134b  sub     rsp, 88h
0x140001352  mov     rax, cs:__security_cookie
0x140001359  xor     rax, rsp
0x14000135c  mov     [rsp+88h+var_18], rax
0x140001361  mov     rax, [rsp+88h+arg_28]
0x140001369  mov     ecx, 4
0x14000136e  mov     [r11-28h], rax
0x140001372  xor     r9d, r9d
0x140001375  mov     rax, [rsp+88h+arg_20]
0x14000137d  xor     r8d, r8d
0x140001380  mov     [r11-38h], rax
0x140001384  lea     rax, [r11-58h]
0x140001388  mov     [r11-60h], rax
0x14000138c  mov     [rsp+88h+var_68], ecx
0x140001390  mov     [r11-30h], rcx
0x140001394  lea     rcx, dword_140019000
0x14000139b  mov     qword ptr [r11-20h], 8
0x1400013a3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013a8  mov     rcx, [rsp+88h+var_18]
0x1400013ad  xor     rcx, rsp; StackCookie
0x1400013b0  call    __security_check_cookie
0x1400013b5  add     rsp, 88h
0x1400013bc  retn
```

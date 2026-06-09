# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001394`
- end: `0x180001409`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800078a0`
- `0x180007b4c`
- `0x180008e54`

## callees

- `0x18000108c`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        int a2,
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
  v9 = 4;
  v11 = 8;
  return tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x180001394  mov     r11, rsp
0x180001397  sub     rsp, 88h
0x18000139e  mov     rax, cs:__security_cookie
0x1800013a5  xor     rax, rsp
0x1800013a8  mov     [rsp+88h+var_18], rax
0x1800013ad  mov     rax, [rsp+88h+arg_28]
0x1800013b5  mov     ecx, 4
0x1800013ba  mov     [r11-28h], rax
0x1800013be  xor     r9d, r9d; int
0x1800013c1  mov     rax, [rsp+88h+arg_20]
0x1800013c9  xor     r8d, r8d; int
0x1800013cc  mov     [r11-38h], rax
0x1800013d0  lea     rax, [r11-58h]
0x1800013d4  mov     [r11-60h], rax
0x1800013d8  mov     [rsp+88h+var_68], ecx; ULONG
0x1800013dc  mov     [r11-30h], rcx
0x1800013e0  lea     rcx, dword_180013018; int
0x1800013e7  mov     qword ptr [r11-20h], 8
0x1800013ef  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013f4  mov     rcx, [rsp+88h+var_18]
0x1800013f9  xor     rcx, rsp; StackCookie
0x1800013fc  call    __security_check_cookie
0x180001401  add     rsp, 88h
0x180001408  retn
```

# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)

- ea: `0x1800013ac`
- end: `0x180001421`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b86c`
- `0x18000d330`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x1800013ac  mov     r11, rsp
0x1800013af  sub     rsp, 88h
0x1800013b6  mov     rax, cs:__security_cookie
0x1800013bd  xor     rax, rsp
0x1800013c0  mov     [rsp+88h+var_18], rax
0x1800013c5  mov     rax, [rsp+88h+arg_28]
0x1800013cd  mov     ecx, 4
0x1800013d2  mov     [r11-28h], rax
0x1800013d6  xor     r9d, r9d
0x1800013d9  mov     rax, [rsp+88h+arg_20]
0x1800013e1  xor     r8d, r8d
0x1800013e4  mov     [r11-38h], rax
0x1800013e8  lea     rax, [r11-58h]
0x1800013ec  mov     [r11-60h], rax
0x1800013f0  mov     [rsp+88h+var_68], ecx
0x1800013f4  mov     [r11-30h], rcx
0x1800013f8  lea     rcx, dword_18001C010
0x1800013ff  mov     qword ptr [r11-20h], 1
0x180001407  call    _tlgWriteTransfer_EventWriteTransfer
0x18000140c  mov     rcx, [rsp+88h+var_18]
0x180001411  xor     rcx, rsp; StackCookie
0x180001414  call    __security_check_cookie
0x180001419  add     rsp, 88h
0x180001420  retn
```

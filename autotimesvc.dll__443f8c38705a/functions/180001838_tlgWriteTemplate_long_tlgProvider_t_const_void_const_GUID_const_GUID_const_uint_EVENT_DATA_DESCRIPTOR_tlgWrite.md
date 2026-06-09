# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001838`
- end: `0x1800018ad`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000caf0`
- `0x18000cc10`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001838  mov     r11, rsp
0x18000183b  sub     rsp, 88h
0x180001842  mov     rax, cs:__security_cookie
0x180001849  xor     rax, rsp
0x18000184c  mov     [rsp+88h+var_18], rax
0x180001851  mov     rax, [rsp+88h+arg_28]
0x180001859  mov     ecx, 4
0x18000185e  mov     [r11-28h], rax
0x180001862  xor     r9d, r9d
0x180001865  mov     rax, [rsp+88h+arg_20]
0x18000186d  xor     r8d, r8d
0x180001870  mov     [r11-38h], rax
0x180001874  lea     rax, [r11-58h]
0x180001878  mov     [r11-60h], rax
0x18000187c  mov     [rsp+88h+var_68], ecx
0x180001880  mov     [r11-20h], rcx
0x180001884  lea     rcx, dword_18001C010
0x18000188b  mov     qword ptr [r11-30h], 8
0x180001893  call    _tlgWriteTransfer_EventWriteTransfer
0x180001898  mov     rcx, [rsp+88h+var_18]
0x18000189d  xor     rcx, rsp; StackCookie
0x1800018a0  call    __security_check_cookie
0x1800018a5  add     rsp, 88h
0x1800018ac  retn
```

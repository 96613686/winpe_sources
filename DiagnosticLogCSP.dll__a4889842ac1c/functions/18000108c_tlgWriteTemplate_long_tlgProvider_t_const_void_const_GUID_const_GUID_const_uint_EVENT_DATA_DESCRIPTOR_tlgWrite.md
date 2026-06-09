# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000108c`
- end: `0x1800010fd`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d20`
- `0x180006f60`
- `0x180007460`
- `0x1800076d0`
- `0x180007a30`
- `0x180007b80`
- `0x180007ca0`
- `0x180008080`
- `0x180008380`
- `0x180008640`
- `0x1800087b0`
- `0x180008a10`
- `0x180008ac0`
- `0x180008b90`
- `0x180008dc0`
- `0x180008f70`
- `0x1800093a0`
- `0x180009560`
- `0x180009710`
- `0x180009a10`
- `0x18000a010`
- `0x18000a250`
- `0x18000a890`
- `0x18000aa40`
- `0x18000bcc0`
- `0x18000bf50`
- `0x18000c260`
- `0x18000c410`
- `0x18000c870`
- `0x18000ced0`
- `0x18000db34`
- `0x18000dc40`
- `0x18000dd1c`
- `0x18000e5f0`
- `0x18000e664`
- `0x18000e758`
- `0x18000f798`
- `0x1800116a4`
- `0x180011760`
- `0x180011980`
- `0x1800119fc`
- `0x18001202c`
- `0x1800120cc`

## callees

- `0x180001104`
- `0x180001b60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
  v7[7] = 4;
  v7[5] = 4;
  return ((__int64 (__fastcall *)(int *, __int64, _QWORD, _QWORD, int, _QWORD *))tlgWriteTransfer_EventWriteTransfer)(
           &dword_180048E90,
           a2,
           0,
           0,
           4,
           v7);
}

```

## disassembly

```asm
0x18000108c  mov     r11, rsp
0x18000108f  sub     rsp, 88h
0x180001096  mov     rax, cs:__security_cookie
0x18000109d  xor     rax, rsp
0x1800010a0  mov     [rsp+88h+var_18], rax
0x1800010a5  mov     rax, [rsp+88h+arg_28]
0x1800010ad  mov     ecx, 4
0x1800010b2  mov     [r11-28h], rax
0x1800010b6  xor     r9d, r9d
0x1800010b9  mov     rax, [rsp+88h+arg_20]
0x1800010c1  xor     r8d, r8d
0x1800010c4  mov     [r11-38h], rax
0x1800010c8  lea     rax, [r11-58h]
0x1800010cc  mov     [r11-60h], rax
0x1800010d0  mov     [rsp+88h+var_68], ecx
0x1800010d4  mov     [r11-20h], rcx
0x1800010d8  mov     [r11-30h], rcx
0x1800010dc  lea     rcx, dword_180048E90
0x1800010e3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010e8  mov     rcx, [rsp+88h+var_18]
0x1800010ed  xor     rcx, rsp; StackCookie
0x1800010f0  call    __security_check_cookie
0x1800010f5  add     rsp, 88h
0x1800010fc  retn
```

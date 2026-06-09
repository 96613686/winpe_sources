# ?add@?Q?$IObservableMap@PE$AAVString@Platform@@PE$AAV12@@Collections@Foundation@Windows@@MapChanged@?$Map@PE$AAVString@Platform@@PE$AAV12@U?$less@PE$AAVString@Platform@@@std@@$00$00@2Platform@@UE$AAA?AVEventRegistrationToken@34@PE$AAV?$MapChangedEventHandler@PE$AAVString@Platform@@PE$AAV12@@234@@Z

- ea: `0x1800b3690`
- end: `0x1800b36b7`
- name: `?add@?Q?$IObservableMap@PE$AAVString@Platform@@PE$AAV12@@Collections@Foundation@Windows@@MapChanged@?$Map@PE$AAVString@Platform@@PE$AAV12@U?$less@PE$AAVString@Platform@@@std@@$00$00@2Platform@@UE$AAA?AVEventRegistrationToken@34@PE$AAV?$MapChangedEventHandler@PE$AAVString@Platform@@PE$AAV12@@234@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b36a5`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b36a5`

## pseudocode

```c
_QWORD *__fastcall _add__Q__IObservableMap_PE_AAVString_Platform__PE_AAV12__Collections_Foundation_Windows__MapChanged___Map_PE_AAVString_Platform__PE_AAV12_U__less_PE_AAVString_Platform___std___00_00_2Platform__UE_AAA_AVEventRegistrationToken_34_PE_AAV__MapChangedEventHandler_PE_AAVString_Platform__PE_AAV12__234__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *(_BYTE *)(a1 + 88) = 1;
  *a2 = Platform::Details::EventSourceAdd(a1 + 96, a1 + 120, a3);
  return a2;
}

```

## disassembly

```asm
0x1800b3690  push    rbx
0x1800b3692  sub     rsp, 20h
0x1800b3696  mov     rbx, rdx
0x1800b3699  mov     byte ptr [rcx+58h], 1
0x1800b369d  lea     rdx, [rcx+78h]
0x1800b36a1  add     rcx, 60h ; '`'
0x1800b36a5  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x1800b36ab  mov     [rbx], rax
0x1800b36ae  mov     rax, rbx
0x1800b36b1  add     rsp, 20h
0x1800b36b5  pop     rbx
0x1800b36b6  retn
```

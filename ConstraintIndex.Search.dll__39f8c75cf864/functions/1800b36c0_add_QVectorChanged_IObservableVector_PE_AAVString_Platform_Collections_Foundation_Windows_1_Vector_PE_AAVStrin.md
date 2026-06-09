# ?add@?QVectorChanged@?$IObservableVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@1?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@3Platform@@UE$AAA?AVEventRegistrationToken@45@PE$AAV?$VectorChangedEventHandler@PE$AAVString@Platform@@@345@@Z

- ea: `0x1800b36c0`
- end: `0x1800b36ea`
- name: `?add@?QVectorChanged@?$IObservableVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@1?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@3Platform@@UE$AAA?AVEventRegistrationToken@45@PE$AAV?$VectorChangedEventHandler@PE$AAVString@Platform@@@345@@Z`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b36d8`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b36d8`

## pseudocode

```c
_QWORD *__fastcall _add__QVectorChanged___IObservableVector_PE_AAVString_Platform___Collections_Foundation_Windows__1__Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_3Platform__UE_AAA_AVEventRegistrationToken_45_PE_AAV__VectorChangedEventHandler_PE_AAVString_Platform___345__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *(_BYTE *)(a1 + 112) = 1;
  *a2 = Platform::Details::EventSourceAdd(a1 + 120, a1 + 152, a3);
  return a2;
}

```

## disassembly

```asm
0x1800b36c0  push    rbx
0x1800b36c2  sub     rsp, 20h
0x1800b36c6  mov     rbx, rdx
0x1800b36c9  mov     byte ptr [rcx+70h], 1
0x1800b36cd  lea     rdx, [rcx+98h]
0x1800b36d4  add     rcx, 78h ; 'x'
0x1800b36d8  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x1800b36de  mov     [rbx], rax
0x1800b36e1  mov     rax, rbx
0x1800b36e4  add     rsp, 20h
0x1800b36e8  pop     rbx
0x1800b36e9  retn
```

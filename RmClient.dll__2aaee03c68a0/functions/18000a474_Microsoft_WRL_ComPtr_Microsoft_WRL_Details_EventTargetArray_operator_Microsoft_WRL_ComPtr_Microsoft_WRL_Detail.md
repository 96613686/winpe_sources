# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)

- ea: `0x18000a474`
- end: `0x18000a4ac`
- name: `??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z`
- size: `56`
- prototype: `__int64 *__fastcall(__int64 *, char *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001500`
- `0x1800018f0`
- `0x180018ca0`
- `0x180018e18`

## callees

- `0x18000a474`
- `0x18000a640`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(__int64 *a1, char *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  char v6; // [rsp+20h] [rbp-18h] BYREF

  v3 = 0;
  if ( &v6 != a2 )
  {
    v3 = *(_QWORD *)a2;
    *(_QWORD *)a2 = 0;
  }
  v4 = *a1;
  *a1 = v3;
  if ( v4 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  return a1;
}

```

## disassembly

```asm
0x18000a474  push    rbx
0x18000a476  sub     rsp, 30h
0x18000a47a  mov     rbx, rcx
0x18000a47d  xor     eax, eax
0x18000a47f  lea     rcx, [rsp+38h+var_18]
0x18000a484  cmp     rcx, rdx
0x18000a487  jz      short loc_18000A493
0x18000a489  mov     rax, [rdx]
0x18000a48c  mov     qword ptr [rdx], 0
0x18000a493  mov     rcx, [rbx]
0x18000a496  mov     [rbx], rax
0x18000a499  test    rcx, rcx
0x18000a49c  jz      short loc_18000A4A3
0x18000a49e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000a4a3  mov     rax, rbx
0x18000a4a6  add     rsp, 30h
0x18000a4aa  pop     rbx
0x18000a4ab  retn
```

# CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(void)

- ea: `0x18000bc80`
- end: `0x18000bcae`
- name: `??1?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a4a0`
- `0x18001a620`
- `0x18001a652`
- `0x18001aaaa`
- `0x18001aabc`
- `0x18001aace`

## callees

- `0x18000bc80`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (**v2)(v2, 1);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc80  push    rbx
0x18000bc82  sub     rsp, 20h
0x18000bc86  mov     rbx, rcx
0x18000bc89  mov     rcx, [rcx]
0x18000bc8c  test    rcx, rcx
0x18000bc8f  jz      short loc_18000BCA8
0x18000bc91  mov     rax, [rcx]
0x18000bc94  mov     edx, 1
0x18000bc99  mov     rax, [rax]
0x18000bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca1  mov     qword ptr [rbx], 0
0x18000bca8  add     rsp, 20h
0x18000bcac  pop     rbx
0x18000bcad  retn
```

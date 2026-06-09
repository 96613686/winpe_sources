# OERTCreateInstance

- ea: `0x180006040`
- end: `0x1800060ac`
- name: `OERTCreateInstance`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006010`
- `0x180006040`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall OERTCreateInstance(const IID *a1, __int64 a2, __int64 a3)
{
  HRESULT ClassObject; // eax
  LPVOID v6; // rbx
  unsigned int v7; // edi
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  ppv = 0;
  ClassObject = DllGetClassObject(a1, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
  v6 = ppv;
  v7 = ClassObject;
  if ( ClassObject >= 0 )
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 0, a2, a3);
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x180006040  push    rbx
0x180006042  push    rbp
0x180006043  push    rsi
0x180006044  push    rdi
0x180006045  sub     rsp, 38h
0x180006049  mov     rsi, r8
0x18000604c  mov     [rsp+58h+ppv], 0
0x180006055  mov     rbp, rdx
0x180006058  lea     r8, [rsp+58h+ppv]; ppv
0x18000605d  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180006064  call    DllGetClassObject
0x180006069  mov     rbx, [rsp+58h+ppv]
0x18000606e  mov     edi, eax
0x180006070  test    eax, eax
0x180006072  js      short loc_18000608D
0x180006074  mov     rax, [rbx]
0x180006077  mov     r9, rsi
0x18000607a  mov     r8, rbp
0x18000607d  xor     edx, edx
0x18000607f  mov     rcx, rbx
0x180006082  mov     rax, [rax+18h]
0x180006086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608b  mov     edi, eax
0x18000608d  test    rbx, rbx
0x180006090  jz      short loc_1800060A1
0x180006092  mov     rax, [rbx]
0x180006095  mov     rcx, rbx
0x180006098  mov     rax, [rax+10h]
0x18000609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a1  mov     eax, edi
0x1800060a3  add     rsp, 38h
0x1800060a7  pop     rdi
0x1800060a8  pop     rsi
0x1800060a9  pop     rbp
0x1800060aa  pop     rbx
0x1800060ab  retn
```

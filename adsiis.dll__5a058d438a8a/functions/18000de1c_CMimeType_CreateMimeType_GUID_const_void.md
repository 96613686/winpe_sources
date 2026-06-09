# CMimeType::CreateMimeType(_GUID const &,void * *)

- ea: `0x18000de1c`
- end: `0x18000de8c`
- name: `?CreateMimeType@CMimeType@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db90`
- `0x180018518`

## callees

- `0x18000dc44`
- `0x18000dc6c`
- `0x18000de1c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CMimeType::CreateMimeType(const struct _GUID *a1, void **a2)
{
  int v4; // eax
  unsigned int v5; // edx
  CMimeType *v6; // rbx
  int v7; // edi
  CMimeType *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CMimeType::AllocateMimeTypeObject(&v9);
  v6 = v9;
  v7 = v4;
  if ( v4 < 0 || (v7 = (**(__int64 (__fastcall ***)(CMimeType *, const struct _GUID *, void **))v9)(v9, a1, a2), v7 < 0) )
  {
    if ( v6 )
      CMimeType::`scalar deleting destructor'(v6, v5);
  }
  else
  {
    (*(void (__fastcall **)(CMimeType *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000de1c  push    rbx
0x18000de1e  push    rbp
0x18000de1f  push    rsi
0x18000de20  push    rdi
0x18000de21  sub     rsp, 28h
0x18000de25  mov     rbp, rcx
0x18000de28  mov     [rsp+48h+arg_10], 0
0x18000de31  lea     rcx, [rsp+48h+arg_10]; struct CMimeType **
0x18000de36  mov     rsi, rdx
0x18000de39  call    ?AllocateMimeTypeObject@CMimeType@@SAJPEAPEAV1@@Z; CMimeType::AllocateMimeTypeObject(CMimeType * *)
0x18000de3e  mov     rbx, [rsp+48h+arg_10]
0x18000de43  mov     edi, eax
0x18000de45  test    eax, eax
0x18000de47  js      short loc_18000DE74
0x18000de49  mov     rax, [rbx]
0x18000de4c  mov     r8, rsi
0x18000de4f  mov     rdx, rbp
0x18000de52  mov     rcx, rbx
0x18000de55  mov     rax, [rax]
0x18000de58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de5d  mov     edi, eax
0x18000de5f  test    eax, eax
0x18000de61  js      short loc_18000DE74
0x18000de63  mov     rax, [rbx]
0x18000de66  mov     rcx, rbx
0x18000de69  mov     rax, [rax+10h]
0x18000de6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de72  jmp     short loc_18000DE81
0x18000de74  test    rbx, rbx
0x18000de77  jz      short loc_18000DE81
0x18000de79  mov     rcx, rbx; this
0x18000de7c  call    ??_GCMimeType@@QEAAPEAXI@Z; CMimeType::`scalar deleting destructor'(uint)
0x18000de81  mov     eax, edi
0x18000de83  add     rsp, 28h
0x18000de87  pop     rdi
0x18000de88  pop     rsi
0x18000de89  pop     rbp
0x18000de8a  pop     rbx
0x18000de8b  retn
```

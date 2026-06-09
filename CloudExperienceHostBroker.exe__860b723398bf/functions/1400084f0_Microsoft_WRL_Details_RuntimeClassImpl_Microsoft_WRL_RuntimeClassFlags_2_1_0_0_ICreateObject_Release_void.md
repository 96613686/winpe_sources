# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)

- ea: `0x1400084f0`
- end: `0x14000853f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006680`

## callees

- `0x1400084f0`
- `0x140008960`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 12), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x1400084f0  push    rbx
0x1400084f2  sub     rsp, 20h
0x1400084f6  mov     r10, rcx
0x1400084f9  add     rcx, 0Ch; this
0x1400084fd  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x140008502  mov     ebx, eax
0x140008504  test    eax, eax
0x140008506  jnz     short loc_140008537
0x140008508  test    r10, r10
0x14000850b  jz      short loc_14000851F
0x14000850d  mov     rdx, [r10]
0x140008510  mov     rcx, r10
0x140008513  mov     rax, [rdx+20h]
0x140008517  lea     edx, [rbx+1]
0x14000851a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000851f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140008526  test    rcx, rcx
0x140008529  jz      short loc_140008537
0x14000852b  mov     rax, [rcx]
0x14000852e  mov     rax, [rax+10h]
0x140008532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008537  mov     eax, ebx
0x140008539  add     rsp, 20h
0x14000853d  pop     rbx
0x14000853e  retn
```

# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::Attach(Microsoft::WRL::Details::EventTargetArray *)

- ea: `0x180010918`
- end: `0x180010945`
- name: `?Attach@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAXPEAVEventTargetArray@Details@23@@Z`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013594`

## callees

- `0x18000a640`
- `0x180010918`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::Attach(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax

  if ( *a1 )
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180010918  mov     [rsp+arg_0], rbx
0x18001091d  push    rdi
0x18001091e  sub     rsp, 20h
0x180010922  mov     rbx, rcx
0x180010925  mov     rdi, rdx
0x180010928  mov     rcx, [rcx]
0x18001092b  test    rcx, rcx
0x18001092e  jnz     short loc_18001093E
0x180010930  mov     [rbx], rdi
0x180010933  mov     rbx, [rsp+28h+arg_0]
0x180010938  add     rsp, 20h
0x18001093c  pop     rdi
0x18001093d  retn
0x18001093e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180010943  jmp     short loc_180010930
```

# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>(void)

- ea: `0x180004120`
- end: `0x180004164`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `68`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005150`

## callees

- `0x180004120`
- `0x180006010`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IInspectable>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 64);
  if ( v2 < 0 )
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v2);
  v3 = *(_QWORD *)(a1 + 32);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180004120  push    rbx
0x180004122  sub     rsp, 20h
0x180004126  mov     rbx, rcx
0x180004129  mov     rcx, [rcx+40h]
0x18000412d  test    rcx, rcx
0x180004130  js      short loc_18000415A
0x180004132  mov     rcx, [rbx+20h]
0x180004136  test    rcx, rcx
0x180004139  jz      short loc_180004154
0x18000413b  mov     qword ptr [rbx+20h], 0
0x180004143  mov     rax, [rcx]
0x180004146  mov     rax, [rax+10h]
0x18000414a  add     rsp, 20h
0x18000414e  pop     rbx
0x18000414f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004154  add     rsp, 20h
0x180004158  pop     rbx
0x180004159  retn
0x18000415a  add     rcx, rcx
0x18000415d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180004162  jmp     short loc_180004132
```

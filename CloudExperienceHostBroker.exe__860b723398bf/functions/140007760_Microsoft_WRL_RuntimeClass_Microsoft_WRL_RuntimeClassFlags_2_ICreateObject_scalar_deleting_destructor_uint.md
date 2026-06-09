# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`scalar deleting destructor'(uint)

- ea: `0x140007760`
- end: `0x140007784`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICreateObject@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `36`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140007760`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007775`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007775`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140007760  push    rbx
0x140007762  sub     rsp, 20h
0x140007766  mov     dword ptr [rcx+0Ch], 0C0000001h
0x14000776d  mov     rbx, rcx
0x140007770  test    dl, 1
0x140007773  jz      short loc_14000777B
0x140007775  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000777b  mov     rax, rbx
0x14000777e  add     rsp, 20h
0x140007782  pop     rbx
0x140007783  retn
```

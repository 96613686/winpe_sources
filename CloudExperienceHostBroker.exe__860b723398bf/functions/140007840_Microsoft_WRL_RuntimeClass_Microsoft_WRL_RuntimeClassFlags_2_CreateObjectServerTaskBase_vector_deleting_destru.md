# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vector deleting destructor'(uint)

- ea: `0x140007840`
- end: `0x140007877`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCreateObjectServerTaskBase@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `55`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140007544`
- `0x140007840`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007863`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007863`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CreateObjectServerTaskBase>::`vector deleting destructor'(
        __int64 a1,
        void *a2)
{
  char v2; // bl

  v2 = (char)a2;
  *(_DWORD *)(a1 + 108) = -1073741823;
  CreateObjectServerTaskBase::~CreateObjectServerTaskBase((wil::details **)a1, a2);
  if ( (v2 & 1) != 0 )
    operator delete((void *)a1);
  return a1;
}

```

## disassembly

```asm
0x140007840  mov     [rsp+arg_0], rbx
0x140007845  push    rdi
0x140007846  sub     rsp, 20h
0x14000784a  mov     ebx, edx
0x14000784c  mov     dword ptr [rcx+6Ch], 0C0000001h
0x140007853  mov     rdi, rcx
0x140007856  call    ??1CreateObjectServerTaskBase@@QEAA@XZ; CreateObjectServerTaskBase::~CreateObjectServerTaskBase(void)
0x14000785b  test    bl, 1
0x14000785e  jz      short loc_140007869
0x140007860  mov     rcx, rdi
0x140007863  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007869  mov     rbx, [rsp+28h+arg_0]
0x14000786e  mov     rax, rdi
0x140007871  add     rsp, 20h
0x140007875  pop     rdi
0x140007876  retn
```

# ATL::CComObject<ReceiveTextMessageTask>::`scalar deleting destructor'(uint)

- ea: `0x180007bb0`
- end: `0x180007c07`
- name: `??_G?$CComObject@VReceiveTextMessageTask@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `ReceiveTextMessageTask *__fastcall(ReceiveTextMessageTask *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180007ae4`
- `0x180007bb0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007bf3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007bf3`

## pseudocode

```c
ReceiveTextMessageTask *__fastcall ATL::CComObject<ReceiveTextMessageTask>::`scalar deleting destructor'(
        ReceiveTextMessageTask *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<ReceiveTextMessageTask>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ReceiveTextMessageTask::~ReceiveTextMessageTask(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007bb0  mov     [rsp+arg_0], rbx
0x180007bb5  push    rdi
0x180007bb6  sub     rsp, 20h
0x180007bba  mov     dword ptr [rcx+8], 0C0000001h
0x180007bc1  lea     rax, ??_7?$CComObject@VReceiveTextMessageTask@@@ATL@@6B@; const ATL::CComObject<ReceiveTextMessageTask>::`vftable'
0x180007bc8  mov     [rcx], rax
0x180007bcb  mov     rdi, rcx
0x180007bce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007bd5  mov     ebx, edx
0x180007bd7  mov     rax, [rcx]
0x180007bda  mov     rax, [rax+10h]
0x180007bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be3  mov     rcx, rdi; this
0x180007be6  call    ??1ReceiveTextMessageTask@@MEAA@XZ; ReceiveTextMessageTask::~ReceiveTextMessageTask(void)
0x180007beb  test    bl, 1
0x180007bee  jz      short loc_180007BF9
0x180007bf0  mov     rcx, rdi
0x180007bf3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007bf9  mov     rbx, [rsp+28h+arg_0]
0x180007bfe  mov     rax, rdi
0x180007c01  add     rsp, 20h
0x180007c05  pop     rdi
0x180007c06  retn
```

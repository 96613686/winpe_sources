# ATL::CComObject<sandbox::SandboxFactory>::`scalar deleting destructor'(uint)

- ea: `0x140005aa0`
- end: `0x140005afd`
- name: `??_G?$CComObject@VSandboxFactory@sandbox@@@ATL@@UEAAPEAXI@Z`
- size: `93`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001f64`
- `0x140005aa0`
- `0x140008010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<sandbox::SandboxFactory>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<sandbox::SandboxFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)Block = &sandbox::SandboxFactory::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140005aa0  mov     [rsp+arg_0], rbx
0x140005aa5  push    rdi
0x140005aa6  sub     rsp, 20h
0x140005aaa  mov     dword ptr [rcx+8], 0C0000001h
0x140005ab1  lea     rax, ??_7?$CComObject@VSandboxFactory@sandbox@@@ATL@@6B@; const ATL::CComObject<sandbox::SandboxFactory>::`vftable'
0x140005ab8  mov     [rcx], rax
0x140005abb  mov     rdi, rcx
0x140005abe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005ac5  mov     ebx, edx
0x140005ac7  mov     rax, [rcx]
0x140005aca  mov     rax, [rax+10h]
0x140005ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ad3  lea     rax, ??_7SandboxFactory@sandbox@@6B@; const sandbox::SandboxFactory::`vftable'
0x140005ada  mov     [rdi], rax
0x140005add  test    bl, 1
0x140005ae0  jz      short loc_140005AEF
0x140005ae2  mov     edx, 20h ; ' '
0x140005ae7  mov     rcx, rdi; Block
0x140005aea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005aef  mov     rbx, [rsp+28h+arg_0]
0x140005af4  mov     rax, rdi
0x140005af7  add     rsp, 20h
0x140005afb  pop     rdi
0x140005afc  retn
```

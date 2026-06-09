# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180024730`
- end: `0x180024796`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180024730`
- `0x180024798`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *Block,
        char a2)
{
  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
  *((_DWORD *)Block + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180024730  mov     [rsp+arg_0], rcx
0x180024735  push    rdi
0x180024736  sub     rsp, 30h
0x18002473a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180024743  mov     [rsp+38h+arg_8], rbx
0x180024748  mov     ebx, edx
0x18002474a  mov     rdi, rcx
0x18002474d  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180024754  mov     [rcx], rax
0x180024757  mov     dword ptr [rcx+18h], 0C0000001h
0x18002475e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180024765  mov     rax, [rcx]
0x180024768  mov     rax, [rax+10h]
0x18002476c  call    cs:__guard_dispatch_icall_fptr
0x180024772  nop
0x180024773  mov     rcx, rdi; this
0x180024776  call    ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
0x18002477b  test    bl, 1
0x18002477e  jz      short loc_180024788
0x180024780  mov     rcx, rdi; Block
0x180024783  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024788  mov     rax, rdi
0x18002478b  mov     rbx, [rsp+38h+arg_8]
0x180024790  add     rsp, 30h
0x180024794  pop     rdi
0x180024795  retn
```

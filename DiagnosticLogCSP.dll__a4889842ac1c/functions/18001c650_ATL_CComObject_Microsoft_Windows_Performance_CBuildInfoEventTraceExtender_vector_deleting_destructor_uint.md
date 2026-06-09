# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18001c650`
- end: `0x18001c6d1`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18001c650`
- `0x180037010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
  a1[6] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)a1 + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)a1 + 1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001c650  mov     [rsp+arg_0], rbx
0x18001c655  push    rdi
0x18001c656  sub     rsp, 20h
0x18001c65a  mov     edi, edx
0x18001c65c  mov     rbx, rcx
0x18001c65f  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18001c666  mov     [rcx], rax
0x18001c669  mov     dword ptr [rcx+18h], 0C0000001h
0x18001c670  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001c677  mov     rax, [rcx]
0x18001c67a  mov     rax, [rax+10h]
0x18001c67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c683  nop
0x18001c684  mov     rcx, [rbx+10h]
0x18001c688  test    rcx, rcx
0x18001c68b  jz      short loc_18001C69A
0x18001c68d  mov     rax, [rcx]
0x18001c690  mov     rax, [rax+10h]
0x18001c694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c699  nop
0x18001c69a  mov     rcx, [rbx+8]
0x18001c69e  test    rcx, rcx
0x18001c6a1  jz      short loc_18001C6B0
0x18001c6a3  mov     rax, [rcx]
0x18001c6a6  mov     rax, [rax+10h]
0x18001c6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6af  nop
0x18001c6b0  test    dil, 1
0x18001c6b4  jz      short loc_18001C6C3
0x18001c6b6  mov     edx, 20h ; ' '; unsigned __int64
0x18001c6bb  mov     rcx, rbx; void *
0x18001c6be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c6c3  mov     rax, rbx
0x18001c6c6  mov     rbx, [rsp+28h+arg_0]
0x18001c6cb  add     rsp, 20h
0x18001c6cf  pop     rdi
0x18001c6d0  retn
```

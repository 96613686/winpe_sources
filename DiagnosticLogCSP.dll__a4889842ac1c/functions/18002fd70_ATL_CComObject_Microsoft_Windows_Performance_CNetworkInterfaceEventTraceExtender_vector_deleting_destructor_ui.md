# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18002fd70`
- end: `0x18002fdf1`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18002fd70`
- `0x180037010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
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
0x18002fd70  mov     [rsp+arg_0], rbx
0x18002fd75  push    rdi
0x18002fd76  sub     rsp, 20h
0x18002fd7a  mov     edi, edx
0x18002fd7c  mov     rbx, rcx
0x18002fd7f  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18002fd86  mov     [rcx], rax
0x18002fd89  mov     dword ptr [rcx+18h], 0C0000001h
0x18002fd90  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002fd97  mov     rax, [rcx]
0x18002fd9a  mov     rax, [rax+10h]
0x18002fd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fda3  nop
0x18002fda4  mov     rcx, [rbx+10h]
0x18002fda8  test    rcx, rcx
0x18002fdab  jz      short loc_18002FDBA
0x18002fdad  mov     rax, [rcx]
0x18002fdb0  mov     rax, [rax+10h]
0x18002fdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb9  nop
0x18002fdba  mov     rcx, [rbx+8]
0x18002fdbe  test    rcx, rcx
0x18002fdc1  jz      short loc_18002FDD0
0x18002fdc3  mov     rax, [rcx]
0x18002fdc6  mov     rax, [rax+10h]
0x18002fdca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdcf  nop
0x18002fdd0  test    dil, 1
0x18002fdd4  jz      short loc_18002FDE3
0x18002fdd6  mov     edx, 20h ; ' '; unsigned __int64
0x18002fddb  mov     rcx, rbx; void *
0x18002fdde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fde3  mov     rax, rbx
0x18002fde6  mov     rbx, [rsp+28h+arg_0]
0x18002fdeb  add     rsp, 20h
0x18002fdef  pop     rdi
0x18002fdf0  retn
```

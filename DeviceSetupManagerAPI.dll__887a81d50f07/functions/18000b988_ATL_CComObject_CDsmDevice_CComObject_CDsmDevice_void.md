# ATL::CComObject<CDsmDevice>::~CComObject<CDsmDevice>(void)

- ea: `0x18000b988`
- end: `0x18000b9f5`
- name: `??1?$CComObject@VCDsmDevice@@@ATL@@UEAA@XZ`
- size: `109`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ba40`

## callees

- `0x18000b988`
- `0x18000ba80`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bf`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDsmDevice>::~CComObject<CDsmDevice>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 result; // rax
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CDsmDevice>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  CDsmDevice::Close((CDsmDevice *)a1);
  v2 = *(void **)(a1 + 72);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)(a1 + 80);
  if ( v3 )
    CloseHandle(v3);
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return result;
}

```

## disassembly

```asm
0x18000b988  push    rbx
0x18000b98a  sub     rsp, 20h
0x18000b98e  mov     rbx, rcx
0x18000b991  lea     rax, ??_7?$CComObject@VCDsmDevice@@@ATL@@6B@; const ATL::CComObject<CDsmDevice>::`vftable'
0x18000b998  mov     [rcx], rax
0x18000b99b  mov     dword ptr [rcx+8], 0C0000001h
0x18000b9a2  call    ?Close@CDsmDevice@@UEAAJXZ; CDsmDevice::Close(void)
0x18000b9a7  mov     rcx, [rbx+48h]; hObject
0x18000b9ab  test    rcx, rcx
0x18000b9ae  jz      short loc_18000B9B6
0x18000b9b0  call    cs:__imp_CloseHandle
0x18000b9b6  mov     rcx, [rbx+50h]; hObject
0x18000b9ba  test    rcx, rcx
0x18000b9bd  jz      short loc_18000B9C5
0x18000b9bf  call    cs:__imp_CloseHandle
0x18000b9c5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b9cc  mov     rax, [rcx]
0x18000b9cf  mov     rax, [rax+10h]
0x18000b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d8  nop
0x18000b9d9  mov     rcx, [rbx+18h]
0x18000b9dd  test    rcx, rcx
0x18000b9e0  jz      short loc_18000B9EF
0x18000b9e2  mov     rax, [rcx]
0x18000b9e5  mov     rax, [rax+10h]
0x18000b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ee  nop
0x18000b9ef  add     rsp, 20h
0x18000b9f3  pop     rbx
0x18000b9f4  retn
```

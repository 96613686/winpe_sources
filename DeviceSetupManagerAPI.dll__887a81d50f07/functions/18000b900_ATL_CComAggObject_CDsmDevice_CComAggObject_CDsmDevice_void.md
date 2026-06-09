# ATL::CComAggObject<CDsmDevice>::~CComAggObject<CDsmDevice>(void)

- ea: `0x18000b900`
- end: `0x18000b982`
- name: `??1?$CComAggObject@VCDsmDevice@@@ATL@@UEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ba00`

## callees

- `0x18000b900`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b947`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDsmDevice>::~CComAggObject<CDsmDevice>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 result; // rax
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComAggObject<CDsmDevice>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 64LL))(a1 + 16);
  v2 = *(void **)(a1 + 88);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)(a1 + 96);
  if ( v3 )
    CloseHandle(v3);
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v5 = *(_QWORD *)(a1 + 40);
  if ( v5 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return result;
}

```

## disassembly

```asm
0x18000b900  mov     [rsp+arg_0], rbx
0x18000b905  push    rdi
0x18000b906  sub     rsp, 20h
0x18000b90a  mov     rdi, rcx
0x18000b90d  lea     rax, ??_7?$CComAggObject@VCDsmDevice@@@ATL@@6B@; const ATL::CComAggObject<CDsmDevice>::`vftable'
0x18000b914  mov     [rcx], rax
0x18000b917  mov     dword ptr [rcx+8], 0C0000001h
0x18000b91e  mov     rax, [rcx+10h]
0x18000b922  add     rcx, 10h
0x18000b926  mov     rax, [rax+40h]
0x18000b92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92f  mov     rcx, [rdi+58h]; hObject
0x18000b933  test    rcx, rcx
0x18000b936  jz      short loc_18000B93E
0x18000b938  call    cs:__imp_CloseHandle
0x18000b93e  mov     rcx, [rdi+60h]; hObject
0x18000b942  test    rcx, rcx
0x18000b945  jz      short loc_18000B94D
0x18000b947  call    cs:__imp_CloseHandle
0x18000b94d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b954  mov     rax, [rcx]
0x18000b957  mov     rax, [rax+10h]
0x18000b95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b960  nop
0x18000b961  mov     rcx, [rdi+28h]
0x18000b965  test    rcx, rcx
0x18000b968  jz      short loc_18000B977
0x18000b96a  mov     rax, [rcx]
0x18000b96d  mov     rax, [rax+10h]
0x18000b971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b976  nop
0x18000b977  mov     rbx, [rsp+28h+arg_0]
0x18000b97c  add     rsp, 20h
0x18000b980  pop     rdi
0x18000b981  retn
```

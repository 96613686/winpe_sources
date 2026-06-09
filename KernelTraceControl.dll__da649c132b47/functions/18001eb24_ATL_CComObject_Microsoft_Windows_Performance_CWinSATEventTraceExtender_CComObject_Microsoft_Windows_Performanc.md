# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(void)

- ea: `0x18001eb24`
- end: `0x18001ebbf`
- name: `??1?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ebc0`

## callees

- `0x18001eb24`
- `0x180027910`

## import_xrefs

- `msvcrt!free` at `0x18001eb64`
- `msvcrt!free` at `0x18001eb73`
- `msvcrt!free` at `0x18001eb82`
- `msvcrt!free` at `0x18001eb64`
- `msvcrt!free` at `0x18001eb73`
- `msvcrt!free` at `0x18001eb82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  free(*(void **)(a1 + 88));
  *(_QWORD *)(a1 + 88) = 0;
  free(*(void **)(a1 + 72));
  *(_QWORD *)(a1 + 72) = 0;
  free(*(void **)(a1 + 56));
  *(_QWORD *)(a1 + 56) = 0;
  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x18001eb24  mov     [rsp+arg_0], rcx
0x18001eb29  push    rbx
0x18001eb2a  sub     rsp, 30h
0x18001eb2e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001eb37  mov     rbx, rcx
0x18001eb3a  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18001eb41  mov     [rcx], rax
0x18001eb44  mov     dword ptr [rcx+18h], 0C0000001h
0x18001eb4b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001eb52  mov     rax, [rcx]
0x18001eb55  mov     rax, [rax+10h]
0x18001eb59  call    cs:__guard_dispatch_icall_fptr
0x18001eb5f  nop
0x18001eb60  mov     rcx, [rbx+58h]; Block
0x18001eb64  call    cs:__imp_free
0x18001eb6a  and     qword ptr [rbx+58h], 0
0x18001eb6f  mov     rcx, [rbx+48h]; Block
0x18001eb73  call    cs:__imp_free
0x18001eb79  and     qword ptr [rbx+48h], 0
0x18001eb7e  mov     rcx, [rbx+38h]; Block
0x18001eb82  call    cs:__imp_free
0x18001eb88  and     qword ptr [rbx+38h], 0
0x18001eb8d  mov     rcx, [rbx+10h]
0x18001eb91  test    rcx, rcx
0x18001eb94  jz      short loc_18001EBA3
0x18001eb96  mov     rax, [rcx]
0x18001eb99  mov     rax, [rax+10h]
0x18001eb9d  call    cs:__guard_dispatch_icall_fptr
0x18001eba3  mov     rcx, [rbx+8]
0x18001eba7  test    rcx, rcx
0x18001ebaa  jz      short loc_18001EBB9
0x18001ebac  mov     rax, [rcx]
0x18001ebaf  mov     rax, [rax+10h]
0x18001ebb3  call    cs:__guard_dispatch_icall_fptr
0x18001ebb9  add     rsp, 30h
0x18001ebbd  pop     rbx
0x18001ebbe  retn
```

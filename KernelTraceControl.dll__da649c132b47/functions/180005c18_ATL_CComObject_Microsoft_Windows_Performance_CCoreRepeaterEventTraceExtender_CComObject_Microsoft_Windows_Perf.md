# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)

- ea: `0x180005c18`
- end: `0x180005c86`
- name: `??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d90`

## callees

- `0x180005c18`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return result;
}

```

## disassembly

```asm
0x180005c18  mov     [rsp+arg_0], rcx
0x180005c1d  push    rbx
0x180005c1e  sub     rsp, 30h
0x180005c22  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005c2b  mov     rbx, rcx
0x180005c2e  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180005c35  mov     [rcx], rax
0x180005c38  mov     dword ptr [rcx+18h], 0C0000001h
0x180005c3f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c46  mov     rax, [rcx]
0x180005c49  mov     rax, [rax+10h]
0x180005c4d  call    cs:__guard_dispatch_icall_fptr
0x180005c53  nop
0x180005c54  mov     rcx, [rbx+10h]
0x180005c58  test    rcx, rcx
0x180005c5b  jz      short loc_180005C6A
0x180005c5d  mov     rax, [rcx]
0x180005c60  mov     rax, [rax+10h]
0x180005c64  call    cs:__guard_dispatch_icall_fptr
0x180005c6a  mov     rcx, [rbx+8]
0x180005c6e  test    rcx, rcx
0x180005c71  jz      short loc_180005C80
0x180005c73  mov     rax, [rcx]
0x180005c76  mov     rax, [rax+10h]
0x180005c7a  call    cs:__guard_dispatch_icall_fptr
0x180005c80  add     rsp, 30h
0x180005c84  pop     rbx
0x180005c85  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)

- ea: `0x180005c88`
- end: `0x180005cf6`
- name: `??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180005c88`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x180005c88  mov     [rsp+arg_0], rcx
0x180005c8d  push    rbx
0x180005c8e  sub     rsp, 30h
0x180005c92  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005c9b  mov     rbx, rcx
0x180005c9e  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180005ca5  mov     [rcx], rax
0x180005ca8  mov     dword ptr [rcx+18h], 0C0000001h
0x180005caf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005cb6  mov     rax, [rcx]
0x180005cb9  mov     rax, [rax+10h]
0x180005cbd  call    cs:__guard_dispatch_icall_fptr
0x180005cc3  nop
0x180005cc4  mov     rcx, [rbx+10h]
0x180005cc8  test    rcx, rcx
0x180005ccb  jz      short loc_180005CDA
0x180005ccd  mov     rax, [rcx]
0x180005cd0  mov     rax, [rax+10h]
0x180005cd4  call    cs:__guard_dispatch_icall_fptr
0x180005cda  mov     rcx, [rbx+8]
0x180005cde  test    rcx, rcx
0x180005ce1  jz      short loc_180005CF0
0x180005ce3  mov     rax, [rcx]
0x180005ce6  mov     rax, [rax+10h]
0x180005cea  call    cs:__guard_dispatch_icall_fptr
0x180005cf0  add     rsp, 30h
0x180005cf4  pop     rbx
0x180005cf5  retn
```

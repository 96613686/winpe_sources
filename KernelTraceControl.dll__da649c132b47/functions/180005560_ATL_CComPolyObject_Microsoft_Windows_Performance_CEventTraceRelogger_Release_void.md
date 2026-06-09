# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(void)

- ea: `0x180005560`
- end: `0x1800055c5`
- name: `?Release@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005560`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(_DWORD *a1)
{
  bool v1; // zf
  unsigned int v3; // edi

  v1 = a1[2]-- == 1;
  v3 = a1[2];
  if ( v1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005560  mov     [rsp+arg_0], rbx
0x180005565  push    rdi
0x180005566  sub     rsp, 20h
0x18000556a  sub     dword ptr [rcx+8], 1
0x18000556e  mov     rbx, rcx
0x180005571  mov     edi, [rcx+8]
0x180005574  jnz     short loc_1800055B8
0x180005576  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000557d  mov     rax, [rcx]
0x180005580  mov     rax, [rax+8]
0x180005584  call    cs:__guard_dispatch_icall_fptr
0x18000558a  test    rbx, rbx
0x18000558d  jz      short loc_1800055A4
0x18000558f  mov     rax, [rbx]
0x180005592  mov     edx, 1
0x180005597  mov     rcx, rbx
0x18000559a  mov     rax, [rax+18h]
0x18000559e  call    cs:__guard_dispatch_icall_fptr
0x1800055a4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800055ab  mov     rdx, [rcx]
0x1800055ae  mov     rax, [rdx+10h]
0x1800055b2  call    cs:__guard_dispatch_icall_fptr
0x1800055b8  mov     eax, edi
0x1800055ba  mov     rbx, [rsp+28h+arg_0]
0x1800055bf  add     rsp, 20h
0x1800055c3  pop     rdi
0x1800055c4  retn
```

# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180001ad0`
- end: `0x180001b19`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001ad0`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(_DWORD *a1)
{
  bool v1; // zf
  unsigned int v2; // ebx

  v1 = a1[2]-- == 1;
  v2 = a1[2];
  if ( v1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  }
  else if ( v2 == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180001ad0  push    rbx
0x180001ad2  sub     rsp, 20h
0x180001ad6  sub     dword ptr [rcx+8], 1
0x180001ada  mov     ebx, [rcx+8]
0x180001add  jnz     short loc_180001AF8
0x180001adf  test    rcx, rcx
0x180001ae2  jz      short loc_180001B11
0x180001ae4  mov     rax, [rcx]
0x180001ae7  mov     edx, 1
0x180001aec  mov     rax, [rax+28h]
0x180001af0  call    cs:__guard_dispatch_icall_fptr
0x180001af6  jmp     short loc_180001B11
0x180001af8  cmp     ebx, 1
0x180001afb  jnz     short loc_180001B11
0x180001afd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001b04  mov     rdx, [rcx]
0x180001b07  mov     rax, [rdx+10h]
0x180001b0b  call    cs:__guard_dispatch_icall_fptr
0x180001b11  mov     eax, ebx
0x180001b13  add     rsp, 20h
0x180001b17  pop     rbx
0x180001b18  retn
```

# ATL::CComObject<CVsShellExtHandler>::Release(void)

- ea: `0x180003210`
- end: `0x180003263`
- name: `?Release@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `83`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800034d0`
- `0x180003510`

## callees

- `0x180003210`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::Release(_DWORD *a1)
{
  bool v2; // zf
  unsigned int v3; // edi

  v2 = a1[6]-- == 1;
  v3 = a1[6];
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180003210  mov     [rsp+arg_0], rbx
0x180003215  push    rdi
0x180003216  sub     rsp, 20h
0x18000321a  mov     rbx, rcx
0x18000321d  sub     dword ptr [rcx+18h], 1
0x180003221  mov     edi, [rcx+18h]
0x180003224  jnz     short loc_180003256
0x180003226  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000322d  mov     rax, [rcx]
0x180003230  call    qword ptr [rax+8]
0x180003233  test    rbx, rbx
0x180003236  jz      short loc_180003248
0x180003238  mov     r8, [rbx]
0x18000323b  mov     edx, 1
0x180003240  mov     rcx, rbx
0x180003243  call    qword ptr [r8+48h]
0x180003247  nop
0x180003248  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000324f  mov     rdx, [rcx]
0x180003252  call    qword ptr [rdx+10h]
0x180003255  nop
0x180003256  mov     eax, edi
0x180003258  mov     rbx, [rsp+28h+arg_0]
0x18000325d  add     rsp, 20h
0x180003261  pop     rdi
0x180003262  retn
```

# CEnumSubCommands::Reset(void)

- ea: `0x180006570`
- end: `0x1800065ac`
- name: `?Reset@CEnumSubCommands@@UEAAJXZ`
- size: `60`
- prototype: `__int64 __fastcall(CEnumSubCommands *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006570`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Reset(CEnumSubCommands *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 6) = 0;
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 4) = 0;
  }
  *((_DWORD *)this + 10) = 0;
  return 0;
}

```

## disassembly

```asm
0x180006570  push    rbx
0x180006572  sub     rsp, 20h
0x180006576  mov     rbx, rcx
0x180006579  mov     dword ptr [rcx+18h], 0
0x180006580  mov     rcx, [rcx+20h]
0x180006584  test    rcx, rcx
0x180006587  jz      short loc_18000659D
0x180006589  mov     rax, [rcx]
0x18000658c  mov     rax, [rax+10h]
0x180006590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006595  mov     qword ptr [rbx+20h], 0
0x18000659d  mov     dword ptr [rbx+28h], 0
0x1800065a4  xor     eax, eax
0x1800065a6  add     rsp, 20h
0x1800065aa  pop     rbx
0x1800065ab  retn
```

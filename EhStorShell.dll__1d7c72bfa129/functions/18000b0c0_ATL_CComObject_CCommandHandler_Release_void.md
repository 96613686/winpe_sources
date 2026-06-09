# ATL::CComObject<CCommandHandler>::Release(void)

- ea: `0x18000b0c0`
- end: `0x18000b12a`
- name: `?Release@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b130`
- `0x18000b140`
- `0x18000b150`

## callees

- `0x180003ca0`
- `0x18000b0c0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[8];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[8] = v3;
    if ( !v3 )
    {
      ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v5);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b0c0  mov     [rsp+arg_8], rbx
0x18000b0c5  push    rdi
0x18000b0c6  sub     rsp, 20h
0x18000b0ca  mov     edi, [rcx+20h]
0x18000b0cd  mov     rbx, rcx
0x18000b0d0  cmp     edi, 7FFFFFFFh
0x18000b0d6  jnz     short loc_18000B0DF
0x18000b0d8  mov     edi, 7FFFFFFEh
0x18000b0dd  jmp     short loc_18000B11D
0x18000b0df  sub     edi, 1
0x18000b0e2  mov     [rcx+20h], edi
0x18000b0e5  jnz     short loc_18000B11D
0x18000b0e7  lea     rcx, [rsp+28h+arg_0]; this
0x18000b0ec  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000b0f1  test    rbx, rbx
0x18000b0f4  jz      short loc_18000B10A
0x18000b0f6  mov     rax, [rbx]
0x18000b0f9  mov     edx, 1
0x18000b0fe  mov     rcx, rbx
0x18000b101  mov     rax, [rax+28h]
0x18000b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b111  mov     rdx, [rcx]
0x18000b114  mov     rax, [rdx+10h]
0x18000b118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11d  mov     rbx, [rsp+28h+arg_8]
0x18000b122  mov     eax, edi
0x18000b124  add     rsp, 20h
0x18000b128  pop     rdi
0x18000b129  retn
```

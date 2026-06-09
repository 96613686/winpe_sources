# ATL::CComObject<CAutoplayHandler>::Release(void)

- ea: `0x180009010`
- end: `0x18000907a`
- name: `?Release@?$CComObject@VCAutoplayHandler@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ca0`
- `0x180009010`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAutoplayHandler>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v5);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180009010  mov     [rsp+arg_8], rbx
0x180009015  push    rdi
0x180009016  sub     rsp, 20h
0x18000901a  mov     edi, [rcx+8]
0x18000901d  mov     rbx, rcx
0x180009020  cmp     edi, 7FFFFFFFh
0x180009026  jnz     short loc_18000902F
0x180009028  mov     edi, 7FFFFFFEh
0x18000902d  jmp     short loc_18000906D
0x18000902f  sub     edi, 1
0x180009032  mov     [rcx+8], edi
0x180009035  jnz     short loc_18000906D
0x180009037  lea     rcx, [rsp+28h+arg_0]; this
0x18000903c  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180009041  test    rbx, rbx
0x180009044  jz      short loc_18000905A
0x180009046  mov     rax, [rbx]
0x180009049  mov     edx, 1
0x18000904e  mov     rcx, rbx
0x180009051  mov     rax, [rax+30h]
0x180009055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000905a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009061  mov     rdx, [rcx]
0x180009064  mov     rax, [rdx+10h]
0x180009068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906d  mov     rbx, [rsp+28h+arg_8]
0x180009072  mov     eax, edi
0x180009074  add     rsp, 20h
0x180009078  pop     rdi
0x180009079  retn
```

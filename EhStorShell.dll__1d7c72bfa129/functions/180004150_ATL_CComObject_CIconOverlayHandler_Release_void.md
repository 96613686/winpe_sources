# ATL::CComObject<CIconOverlayHandler>::Release(void)

- ea: `0x180004150`
- end: `0x1800041bc`
- name: `?Release@?$CComObject@VCIconOverlayHandler@@@ATL@@UEAAKXZ`
- size: `108`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ca0`
- `0x180004150`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIconOverlayHandler>::Release(_DWORD *a1)
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
0x180004150  mov     [rsp+arg_8], rbx
0x180004155  push    rdi
0x180004156  sub     rsp, 20h
0x18000415a  mov     edi, [rcx+8]
0x18000415d  mov     rbx, rcx
0x180004160  cmp     edi, 7FFFFFFFh
0x180004166  jz      short loc_18000417D
0x180004168  sub     edi, 1
0x18000416b  mov     [rcx+8], edi
0x18000416e  jz      short loc_180004184
0x180004170  mov     rbx, [rsp+28h+arg_8]
0x180004175  mov     eax, edi
0x180004177  add     rsp, 20h
0x18000417b  pop     rdi
0x18000417c  retn
0x18000417d  mov     edi, 7FFFFFFEh
0x180004182  jmp     short loc_180004170
0x180004184  lea     rcx, [rsp+28h+arg_0]; this
0x180004189  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000418e  test    rbx, rbx
0x180004191  jz      short loc_1800041A7
0x180004193  mov     rax, [rbx]
0x180004196  mov     edx, 1
0x18000419b  mov     rcx, rbx
0x18000419e  mov     rax, [rax+30h]
0x1800041a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800041ae  mov     rdx, [rcx]
0x1800041b1  mov     rax, [rdx+10h]
0x1800041b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ba  jmp     short loc_180004170
```

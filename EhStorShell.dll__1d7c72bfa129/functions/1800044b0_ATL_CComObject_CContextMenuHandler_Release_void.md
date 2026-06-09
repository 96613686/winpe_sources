# ATL::CComObject<CContextMenuHandler>::Release(void)

- ea: `0x1800044b0`
- end: `0x18000451a`
- name: `?Release@?$CComObject@VCContextMenuHandler@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009080`

## callees

- `0x180003ca0`
- `0x1800044b0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[4];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[4] = v3;
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
0x1800044b0  mov     [rsp+arg_8], rbx
0x1800044b5  push    rdi
0x1800044b6  sub     rsp, 20h
0x1800044ba  mov     edi, [rcx+10h]
0x1800044bd  mov     rbx, rcx
0x1800044c0  cmp     edi, 7FFFFFFFh
0x1800044c6  jnz     short loc_1800044CF
0x1800044c8  mov     edi, 7FFFFFFEh
0x1800044cd  jmp     short loc_18000450D
0x1800044cf  sub     edi, 1
0x1800044d2  mov     [rcx+10h], edi
0x1800044d5  jnz     short loc_18000450D
0x1800044d7  lea     rcx, [rsp+28h+arg_0]; this
0x1800044dc  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x1800044e1  test    rbx, rbx
0x1800044e4  jz      short loc_1800044FA
0x1800044e6  mov     rax, [rbx]
0x1800044e9  mov     edx, 1
0x1800044ee  mov     rcx, rbx
0x1800044f1  mov     rax, [rax+30h]
0x1800044f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fa  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004501  mov     rdx, [rcx]
0x180004504  mov     rax, [rdx+10h]
0x180004508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450d  mov     rbx, [rsp+28h+arg_8]
0x180004512  mov     eax, edi
0x180004514  add     rsp, 20h
0x180004518  pop     rdi
0x180004519  retn
```

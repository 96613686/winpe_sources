# ATL::CComObject<CAxInstaller>::Release(void)

- ea: `0x18000ee90`
- end: `0x18000eeed`
- name: `?Release@?$CComObject@VCAxInstaller@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ef00`

## callees

- `0x180008030`
- `0x18000ee90`
- `0x18000f460`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAxInstaller>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 4);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ee90  mov     [rsp+arg_8], rbx
0x18000ee95  push    rdi
0x18000ee96  sub     rsp, 20h
0x18000ee9a  mov     rbx, rcx
0x18000ee9d  add     rcx, 10h; volatile int *
0x18000eea1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000eea6  mov     edi, eax
0x18000eea8  test    eax, eax
0x18000eeaa  jnz     short loc_18000EEE0
0x18000eeac  lea     rcx, [rsp+28h+arg_0]; this
0x18000eeb1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000eeb6  test    rbx, rbx
0x18000eeb9  jz      short loc_18000EECD
0x18000eebb  mov     rdx, [rbx]
0x18000eebe  mov     rcx, rbx
0x18000eec1  mov     rax, [rdx+30h]
0x18000eec5  lea     edx, [rdi+1]
0x18000eec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eecd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000eed4  mov     rax, [rcx]
0x18000eed7  mov     rax, [rax+10h]
0x18000eedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee0  mov     rbx, [rsp+28h+arg_8]
0x18000eee5  mov     eax, edi
0x18000eee7  add     rsp, 20h
0x18000eeeb  pop     rdi
0x18000eeec  retn
```

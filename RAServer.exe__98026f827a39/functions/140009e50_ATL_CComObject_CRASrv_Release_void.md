# ATL::CComObject<CRASrv>::Release(void)

- ea: `0x140009e50`
- end: `0x140009ead`
- name: `?Release@?$CComObject@VCRASrv@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009ec0`

## callees

- `0x140003058`
- `0x140009e50`
- `0x14000a230`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRASrv>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 4);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x140009e50  mov     [rsp+arg_8], rbx
0x140009e55  push    rdi
0x140009e56  sub     rsp, 20h
0x140009e5a  mov     rbx, rcx
0x140009e5d  add     rcx, 10h; volatile int *
0x140009e61  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140009e66  mov     edi, eax
0x140009e68  test    eax, eax
0x140009e6a  jnz     short loc_140009EA0
0x140009e6c  lea     rcx, [rsp+28h+arg_0]; this
0x140009e71  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x140009e76  test    rbx, rbx
0x140009e79  jz      short loc_140009E8D
0x140009e7b  mov     rdx, [rbx]
0x140009e7e  mov     rcx, rbx
0x140009e81  mov     rax, [rdx+48h]
0x140009e85  lea     edx, [rdi+1]
0x140009e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e8d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009e94  mov     rax, [rcx]
0x140009e97  mov     rax, [rax+10h]
0x140009e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ea0  mov     rbx, [rsp+28h+arg_8]
0x140009ea5  mov     eax, edi
0x140009ea7  add     rsp, 20h
0x140009eab  pop     rdi
0x140009eac  retn
```

# ATL::CComObject<CRemoteAssistance>::Release(void)

- ea: `0x140009ed0`
- end: `0x140009f2d`
- name: `?Release@?$CComObject@VCRemoteAssistance@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009f40`

## callees

- `0x140003058`
- `0x140009ed0`
- `0x14000a230`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoteAssistance>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 4);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x140009ed0  mov     [rsp+arg_8], rbx
0x140009ed5  push    rdi
0x140009ed6  sub     rsp, 20h
0x140009eda  mov     rbx, rcx
0x140009edd  add     rcx, 10h; volatile int *
0x140009ee1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140009ee6  mov     edi, eax
0x140009ee8  test    eax, eax
0x140009eea  jnz     short loc_140009F20
0x140009eec  lea     rcx, [rsp+28h+arg_0]; this
0x140009ef1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x140009ef6  test    rbx, rbx
0x140009ef9  jz      short loc_140009F0D
0x140009efb  mov     rdx, [rbx]
0x140009efe  mov     rcx, rbx
0x140009f01  mov     rax, [rdx+20h]
0x140009f05  lea     edx, [rdi+1]
0x140009f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f0d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009f14  mov     rax, [rcx]
0x140009f17  mov     rax, [rax+10h]
0x140009f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f20  mov     rbx, [rsp+28h+arg_8]
0x140009f25  mov     eax, edi
0x140009f27  add     rsp, 20h
0x140009f2b  pop     rdi
0x140009f2c  retn
```

# ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::Release(void)

- ea: `0x180008640`
- end: `0x1800086c1`
- name: `?Release@?$CComObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008640`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180008640  mov     [rsp+arg_0], rbx
0x180008645  push    rdi
0x180008646  sub     rsp, 20h
0x18000864a  mov     r8d, [rcx+8]
0x18000864e  mov     rbx, rcx
0x180008651  mov     ecx, 7FFFFFFFh
0x180008656  jmp     short loc_18000866A
0x180008658  lea     edx, [r8-1]
0x18000865c  mov     eax, r8d
0x18000865f  lock cmpxchg [rbx+8], edx
0x180008664  jz      short loc_18000866F
0x180008666  mov     r8d, [rbx+8]
0x18000866a  cmp     r8d, ecx
0x18000866d  jnz     short loc_180008658
0x18000866f  lea     edi, [r8-1]
0x180008673  test    edi, edi
0x180008675  jnz     short loc_1800086B4
0x180008677  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000867e  mov     rax, [rcx]
0x180008681  mov     rax, [rax+8]
0x180008685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868a  test    rbx, rbx
0x18000868d  jz      short loc_1800086A1
0x18000868f  mov     rax, [rbx]
0x180008692  lea     edx, [rdi+1]
0x180008695  mov     rcx, rbx
0x180008698  mov     rax, [rax+20h]
0x18000869c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800086a8  mov     rdx, [rcx]
0x1800086ab  mov     rax, [rdx+10h]
0x1800086af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b4  mov     rbx, [rsp+28h+arg_0]
0x1800086b9  mov     eax, edi
0x1800086bb  add     rsp, 20h
0x1800086bf  pop     rdi
0x1800086c0  retn
```

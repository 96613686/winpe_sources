# ATL::CComObject<CMidi2VirtualMidiTransport>::Release(void)

- ea: `0x180009350`
- end: `0x1800093d1`
- name: `?Release@?$CComObject@VCMidi2VirtualMidiTransport@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009350`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2VirtualMidiTransport>::Release(volatile signed __int32 *a1)
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
0x180009350  mov     [rsp+arg_0], rbx
0x180009355  push    rdi
0x180009356  sub     rsp, 20h
0x18000935a  mov     r8d, [rcx+8]
0x18000935e  mov     rbx, rcx
0x180009361  mov     ecx, 7FFFFFFFh
0x180009366  jmp     short loc_18000937A
0x180009368  lea     edx, [r8-1]
0x18000936c  mov     eax, r8d
0x18000936f  lock cmpxchg [rbx+8], edx
0x180009374  jz      short loc_18000937F
0x180009376  mov     r8d, [rbx+8]
0x18000937a  cmp     r8d, ecx
0x18000937d  jnz     short loc_180009368
0x18000937f  lea     edi, [r8-1]
0x180009383  test    edi, edi
0x180009385  jnz     short loc_1800093C4
0x180009387  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000938e  mov     rax, [rcx]
0x180009391  mov     rax, [rax+8]
0x180009395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000939a  test    rbx, rbx
0x18000939d  jz      short loc_1800093B1
0x18000939f  mov     rax, [rbx]
0x1800093a2  lea     edx, [rdi+1]
0x1800093a5  mov     rcx, rbx
0x1800093a8  mov     rax, [rax+20h]
0x1800093ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800093b8  mov     rdx, [rcx]
0x1800093bb  mov     rax, [rdx+10h]
0x1800093bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c4  mov     rbx, [rsp+28h+arg_0]
0x1800093c9  mov     eax, edi
0x1800093cb  add     rsp, 20h
0x1800093cf  pop     rdi
0x1800093d0  retn
```

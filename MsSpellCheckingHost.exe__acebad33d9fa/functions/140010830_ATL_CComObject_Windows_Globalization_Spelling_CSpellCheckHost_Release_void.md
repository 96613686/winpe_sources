# ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::Release(void)

- ea: `0x140010830`
- end: `0x1400108b1`
- name: `?Release@?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140010830`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::Release(
        volatile signed __int32 *a1)
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
0x140010830  mov     [rsp+arg_0], rbx
0x140010835  push    rdi
0x140010836  sub     rsp, 20h
0x14001083a  mov     r8d, [rcx+8]
0x14001083e  mov     rbx, rcx
0x140010841  mov     ecx, 7FFFFFFFh
0x140010846  jmp     short loc_14001085A
0x140010848  lea     edx, [r8-1]
0x14001084c  mov     eax, r8d
0x14001084f  lock cmpxchg [rbx+8], edx
0x140010854  jz      short loc_14001085F
0x140010856  mov     r8d, [rbx+8]
0x14001085a  cmp     r8d, ecx
0x14001085d  jnz     short loc_140010848
0x14001085f  lea     edi, [r8-1]
0x140010863  test    edi, edi
0x140010865  jnz     short loc_1400108A4
0x140010867  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14001086e  mov     rax, [rcx]
0x140010871  mov     rax, [rax+8]
0x140010875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001087a  test    rbx, rbx
0x14001087d  jz      short loc_140010891
0x14001087f  mov     rax, [rbx]
0x140010882  lea     edx, [rdi+1]
0x140010885  mov     rcx, rbx
0x140010888  mov     rax, [rax+20h]
0x14001088c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010891  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140010898  mov     rdx, [rcx]
0x14001089b  mov     rax, [rdx+10h]
0x14001089f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108a4  mov     rbx, [rsp+28h+arg_0]
0x1400108a9  mov     eax, edi
0x1400108ab  add     rsp, 20h
0x1400108af  pop     rdi
0x1400108b0  retn
```

# ATL::CComCreator<ATL::CComAggObject<CDsmControl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a134`
- end: `0x18000a21a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDsmControl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a120`

## callees

- `0x18000137c`
- `0x18000a134`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDsmControl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x20u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDsmControl>::`vftable';
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CDsmControl>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v10;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000a134  mov     [rsp+arg_10], r8
0x18000a139  mov     [rsp+arg_8], rdx
0x18000a13e  push    rbx
0x18000a13f  push    rsi
0x18000a140  push    rdi
0x18000a141  push    r14
0x18000a143  push    r15
0x18000a145  sub     rsp, 30h
0x18000a149  mov     rsi, r8
0x18000a14c  mov     r14, rdx
0x18000a14f  mov     r15, rcx
0x18000a152  test    r8, r8
0x18000a155  jnz     short loc_18000A161
0x18000a157  mov     eax, 80004003h
0x18000a15c  jmp     loc_18000A20E
0x18000a161  mov     qword ptr [r8], 0
0x18000a168  mov     edi, 8007000Eh
0x18000a16d  mov     [rsp+58h+arg_18], edi
0x18000a171  mov     [rsp+58h+var_38], 0
0x18000a17a  mov     ecx, 20h ; ' '; Size
0x18000a17f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a184  mov     rbx, rax
0x18000a187  test    rbx, rbx
0x18000a18a  jz      short loc_18000A1BF
0x18000a18c  mov     dword ptr [rax+8], 0
0x18000a193  lea     rax, ??_7?$CComAggObject@VCDsmControl@@@ATL@@6B@; const ATL::CComAggObject<CDsmControl>::`vftable'
0x18000a19a  mov     [rbx], rax
0x18000a19d  lea     rax, ??_7?$CComContainedObject@VCDsmControl@@@ATL@@6B@; const ATL::CComContainedObject<CDsmControl>::`vftable'
0x18000a1a4  mov     [rbx+10h], rax
0x18000a1a8  mov     [rbx+18h], r15
0x18000a1ac  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a1b3  mov     rax, [rcx]
0x18000a1b6  mov     rax, [rax+8]
0x18000a1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1bf  mov     [rsp+58h+var_38], rbx
0x18000a1c4  jmp     short loc_18000A1D9
0x18000a1c6  mov     rsi, [rsp+58h+arg_10]
0x18000a1cb  mov     r14, [rsp+58h+arg_8]
0x18000a1d0  mov     edi, [rsp+58h+arg_18]
0x18000a1d4  mov     rbx, [rsp+58h+var_38]
0x18000a1d9  test    rbx, rbx
0x18000a1dc  jz      short loc_18000A20C
0x18000a1de  mov     rax, [rbx]
0x18000a1e1  mov     r8, rsi
0x18000a1e4  mov     rdx, r14
0x18000a1e7  mov     rcx, rbx
0x18000a1ea  mov     rax, [rax]
0x18000a1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f2  mov     edi, eax
0x18000a1f4  test    eax, eax
0x18000a1f6  jz      short loc_18000A20C
0x18000a1f8  mov     rdx, [rbx]
0x18000a1fb  mov     rax, [rdx+18h]
0x18000a1ff  mov     edx, 1
0x18000a204  mov     rcx, rbx
0x18000a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20c  mov     eax, edi
0x18000a20e  add     rsp, 30h
0x18000a212  pop     r15
0x18000a214  pop     r14
0x18000a216  pop     rdi
0x18000a217  pop     rsi
0x18000a218  pop     rbx
0x18000a219  retn
```

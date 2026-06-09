# ATL::CComCreator<ATL::CComObject<CDsmControl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a220`
- end: `0x18000a314`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDsmControl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a120`

## callees

- `0x18000137c`
- `0x18000a220`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDsmControl>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // ecx
  _DWORD *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x10u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CDsmControl>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = v8[2];
    if ( v9 != 0x7FFFFFFF )
    {
      v8[2] = v9 + 1;
      if ( v9 != 2147483646 )
        v8[2] = v9;
    }
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 136LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a220  mov     [rsp+arg_10], r8
0x18000a225  mov     [rsp+arg_8], rdx
0x18000a22a  mov     [rsp+arg_0], rcx
0x18000a22f  push    rbx
0x18000a230  push    rsi
0x18000a231  push    rdi
0x18000a232  push    r14
0x18000a234  sub     rsp, 28h
0x18000a238  mov     rsi, r8
0x18000a23b  mov     r14, rdx
0x18000a23e  test    r8, r8
0x18000a241  jnz     short loc_18000A24D
0x18000a243  mov     eax, 80004003h
0x18000a248  jmp     loc_18000A30A
0x18000a24d  mov     qword ptr [r8], 0
0x18000a254  mov     edi, 8007000Eh
0x18000a259  mov     dword ptr [rsp+48h+arg_0], edi
0x18000a25d  mov     [rsp+48h+arg_18], 0
0x18000a266  mov     ecx, 10h; Size
0x18000a26b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a270  mov     rbx, rax
0x18000a273  test    rbx, rbx
0x18000a276  jz      short loc_18000A29C
0x18000a278  mov     dword ptr [rax+8], 0
0x18000a27f  lea     rax, ??_7?$CComObject@VCDsmControl@@@ATL@@6B@; const ATL::CComObject<CDsmControl>::`vftable'
0x18000a286  mov     [rbx], rax
0x18000a289  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a290  mov     rax, [rcx]
0x18000a293  mov     rax, [rax+8]
0x18000a297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29c  mov     [rsp+48h+arg_18], rbx
0x18000a2a1  jmp     short loc_18000A2B6
0x18000a2a3  mov     rsi, [rsp+48h+arg_10]
0x18000a2a8  mov     r14, [rsp+48h+arg_8]
0x18000a2ad  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000a2b1  mov     rbx, [rsp+48h+arg_18]
0x18000a2b6  test    rbx, rbx
0x18000a2b9  jz      short loc_18000A308
0x18000a2bb  mov     ecx, [rbx+8]
0x18000a2be  cmp     ecx, 7FFFFFFFh
0x18000a2c4  jz      short loc_18000A2D7
0x18000a2c6  lea     eax, [rcx+1]
0x18000a2c9  mov     [rbx+8], eax
0x18000a2cc  cmp     ecx, 7FFFFFFEh
0x18000a2d2  jz      short loc_18000A2D7
0x18000a2d4  mov     [rbx+8], ecx
0x18000a2d7  mov     rax, [rbx]
0x18000a2da  mov     r8, rsi
0x18000a2dd  mov     rdx, r14
0x18000a2e0  mov     rcx, rbx
0x18000a2e3  mov     rax, [rax]
0x18000a2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2eb  mov     edi, eax
0x18000a2ed  test    eax, eax
0x18000a2ef  jz      short loc_18000A308
0x18000a2f1  mov     rdx, [rbx]
0x18000a2f4  mov     rax, [rdx+88h]
0x18000a2fb  mov     edx, 1
0x18000a300  mov     rcx, rbx
0x18000a303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a308  mov     eax, edi
0x18000a30a  add     rsp, 28h
0x18000a30e  pop     r14
0x18000a310  pop     rdi
0x18000a311  pop     rsi
0x18000a312  pop     rbx
0x18000a313  retn
```

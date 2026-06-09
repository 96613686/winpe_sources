# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x180004ab0`
- end: `0x180004c09`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004740`

## callees

- `0x1800018a0`
- `0x180004ab0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(
        char *a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned int v5; // r14d
  char *v6; // rbx
  char *v7; // rcx
  int v8; // eax
  int v9; // eax
  char *v11; // [rsp+68h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  try
  {
    *a2 = 0;
    v5 = -2147024882;
    v6 = (char *)operator new(0xC0u);
    *((_DWORD *)v6 + 2) = 0;
    *(_QWORD *)v6 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
    v7 = v6;
    if ( a1 )
      v7 = a1;
    *((_DWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 6) = 0;
    *((_QWORD *)v6 + 7) = 0;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_DWORD *)v6 + 24) = 0;
    *((_DWORD *)v6 + 26) = 0;
    *((_DWORD *)v6 + 27) = 2;
    *((_DWORD *)v6 + 28) = 50;
    *(_QWORD *)(v6 + 116) = 10;
    *((_WORD *)v6 + 62) = 256;
    *((_DWORD *)v6 + 32) = 0;
    *((_DWORD *)v6 + 33) = 7;
    *((_DWORD *)v6 + 34) = -1;
    *((_QWORD *)v6 + 18) = 0;
    *((_QWORD *)v6 + 19) = 0;
    v6[160] = 0;
    *((_DWORD *)v6 + 41) = 0;
    *((_DWORD *)v6 + 42) = -1;
    *((_QWORD *)v6 + 22) = 0;
    *((_QWORD *)v6 + 23) = 0;
    *((_QWORD *)v6 + 2) = &ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
    *((_QWORD *)v6 + 3) = v7;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v11 = v6;
  }
  catch ( ... )
  {
    v2 = a2;
    v5 = -2147024882;
    v6 = v11;
  }
  if ( v6 )
  {
    v8 = *((_DWORD *)v6 + 2);
    if ( v8 != 0x7FFFFFFF )
    {
      v9 = v8 + 1;
      *((_DWORD *)v6 + 2) = v9;
      if ( v9 != 0x7FFFFFFF )
        *((_DWORD *)v6 + 2) = v9 - 1;
    }
    v5 = 0;
  }
  *v2 = v6;
  return v5;
}

```

## disassembly

```asm
0x180004ab0  mov     [rsp+arg_8], rdx
0x180004ab5  push    rbx
0x180004ab6  push    rsi
0x180004ab7  push    rdi
0x180004ab8  push    r14
0x180004aba  push    r15
0x180004abc  sub     rsp, 20h
0x180004ac0  mov     rsi, rdx
0x180004ac3  mov     r15, rcx
0x180004ac6  xor     edi, edi
0x180004ac8  test    rdx, rdx
0x180004acb  jnz     short loc_180004AD7
0x180004acd  mov     eax, 80004003h
0x180004ad2  jmp     loc_180004BFD
0x180004ad7  mov     [rdx], rdi
0x180004ada  mov     r14d, 8007000Eh
0x180004ae0  mov     [rsp+48h+arg_10], r14d
0x180004ae5  mov     [rsp+48h+arg_18], rdi
0x180004aea  mov     ecx, 0C0h; Size
0x180004aef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004af4  mov     rbx, rax
0x180004af7  mov     [rax+8], edi
0x180004afa  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180004b01  mov     [rbx], rax
0x180004b04  mov     rcx, rbx
0x180004b07  test    r15, r15
0x180004b0a  cmovnz  rcx, r15
0x180004b0e  mov     [rbx+20h], edi
0x180004b11  mov     [rbx+28h], rdi
0x180004b15  mov     [rbx+30h], rdi
0x180004b19  mov     [rbx+38h], rdi
0x180004b1d  mov     [rbx+40h], rdi
0x180004b21  xor     eax, eax
0x180004b23  mov     [rbx+48h], rax
0x180004b27  mov     [rbx+50h], rdi
0x180004b2b  mov     [rbx+58h], rdi
0x180004b2f  mov     [rbx+60h], edi
0x180004b32  mov     [rbx+68h], edi
0x180004b35  mov     dword ptr [rbx+6Ch], 2
0x180004b3c  mov     dword ptr [rbx+70h], 32h ; '2'
0x180004b43  mov     qword ptr [rbx+74h], 0Ah
0x180004b4b  mov     word ptr [rbx+7Ch], 100h
0x180004b51  mov     [rbx+80h], edi
0x180004b57  mov     dword ptr [rbx+84h], 7
0x180004b61  or      eax, 0FFFFFFFFh
0x180004b64  mov     [rbx+88h], eax
0x180004b6a  mov     [rbx+90h], rdi
0x180004b71  mov     [rbx+98h], rdi
0x180004b78  mov     [rbx+0A0h], dil
0x180004b7f  mov     [rbx+0A4h], edi
0x180004b85  mov     [rbx+0A8h], eax
0x180004b8b  xor     eax, eax
0x180004b8d  mov     [rbx+0B0h], rax
0x180004b94  mov     [rbx+0B8h], rdi
0x180004b9b  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180004ba2  mov     [rbx+10h], rax
0x180004ba6  mov     [rbx+18h], rcx
0x180004baa  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004bb1  mov     rax, [rcx]
0x180004bb4  mov     rax, [rax+8]
0x180004bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbd  mov     [rsp+48h+arg_18], rbx
0x180004bc2  jmp     short loc_180004BD5
0x180004bc4  xor     edi, edi
0x180004bc6  mov     rsi, [rsp+48h+arg_8]
0x180004bcb  mov     r14d, [rsp+48h+arg_10]
0x180004bd0  mov     rbx, [rsp+48h+arg_18]
0x180004bd5  test    rbx, rbx
0x180004bd8  jz      short loc_180004BF7
0x180004bda  mov     eax, [rbx+8]
0x180004bdd  mov     ecx, 7FFFFFFFh
0x180004be2  cmp     eax, ecx
0x180004be4  jz      short loc_180004BF4
0x180004be6  inc     eax
0x180004be8  mov     [rbx+8], eax
0x180004beb  cmp     eax, ecx
0x180004bed  jz      short loc_180004BF4
0x180004bef  dec     eax
0x180004bf1  mov     [rbx+8], eax
0x180004bf4  mov     r14d, edi
0x180004bf7  mov     [rsi], rbx
0x180004bfa  mov     eax, r14d
0x180004bfd  add     rsp, 20h
0x180004c01  pop     r15
0x180004c03  pop     r14
0x180004c05  pop     rdi
0x180004c06  pop     rsi
0x180004c07  pop     rbx
0x180004c08  retn
```

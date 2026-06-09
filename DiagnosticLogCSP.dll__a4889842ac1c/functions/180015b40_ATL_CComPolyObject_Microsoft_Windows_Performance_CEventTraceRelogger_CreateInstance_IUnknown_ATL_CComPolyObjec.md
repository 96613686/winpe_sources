# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x180015b40`
- end: `0x180015c99`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `345`
- prototype: `__int64 __fastcall(char *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800157d0`

## callees

- `0x180001b84`
- `0x180015b40`
- `0x180037010`

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
0x180015b40  mov     [rsp+arg_8], rdx
0x180015b45  push    rbx
0x180015b46  push    rsi
0x180015b47  push    rdi
0x180015b48  push    r14
0x180015b4a  push    r15
0x180015b4c  sub     rsp, 20h
0x180015b50  mov     rsi, rdx
0x180015b53  mov     r15, rcx
0x180015b56  xor     edi, edi
0x180015b58  test    rdx, rdx
0x180015b5b  jnz     short loc_180015B67
0x180015b5d  mov     eax, 80004003h
0x180015b62  jmp     loc_180015C8D
0x180015b67  mov     [rdx], rdi
0x180015b6a  mov     r14d, 8007000Eh
0x180015b70  mov     [rsp+48h+arg_10], r14d
0x180015b75  mov     [rsp+48h+arg_18], rdi
0x180015b7a  mov     ecx, 0C0h; Size
0x180015b7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015b84  mov     rbx, rax
0x180015b87  mov     [rax+8], edi
0x180015b8a  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180015b91  mov     [rbx], rax
0x180015b94  mov     rcx, rbx
0x180015b97  test    r15, r15
0x180015b9a  cmovnz  rcx, r15
0x180015b9e  mov     [rbx+20h], edi
0x180015ba1  mov     [rbx+28h], rdi
0x180015ba5  mov     [rbx+30h], rdi
0x180015ba9  mov     [rbx+38h], rdi
0x180015bad  mov     [rbx+40h], rdi
0x180015bb1  xor     eax, eax
0x180015bb3  mov     [rbx+48h], rax
0x180015bb7  mov     [rbx+50h], rdi
0x180015bbb  mov     [rbx+58h], rdi
0x180015bbf  mov     [rbx+60h], edi
0x180015bc2  mov     [rbx+68h], edi
0x180015bc5  mov     dword ptr [rbx+6Ch], 2
0x180015bcc  mov     dword ptr [rbx+70h], 32h ; '2'
0x180015bd3  mov     qword ptr [rbx+74h], 0Ah
0x180015bdb  mov     word ptr [rbx+7Ch], 100h
0x180015be1  mov     [rbx+80h], edi
0x180015be7  mov     dword ptr [rbx+84h], 7
0x180015bf1  or      eax, 0FFFFFFFFh
0x180015bf4  mov     [rbx+88h], eax
0x180015bfa  mov     [rbx+90h], rdi
0x180015c01  mov     [rbx+98h], rdi
0x180015c08  mov     [rbx+0A0h], dil
0x180015c0f  mov     [rbx+0A4h], edi
0x180015c15  mov     [rbx+0A8h], eax
0x180015c1b  xor     eax, eax
0x180015c1d  mov     [rbx+0B0h], rax
0x180015c24  mov     [rbx+0B8h], rdi
0x180015c2b  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180015c32  mov     [rbx+10h], rax
0x180015c36  mov     [rbx+18h], rcx
0x180015c3a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015c41  mov     rax, [rcx]
0x180015c44  mov     rax, [rax+8]
0x180015c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c4d  mov     [rsp+48h+arg_18], rbx
0x180015c52  jmp     short loc_180015C65
0x180015c54  xor     edi, edi
0x180015c56  mov     rsi, [rsp+48h+arg_8]
0x180015c5b  mov     r14d, [rsp+48h+arg_10]
0x180015c60  mov     rbx, [rsp+48h+arg_18]
0x180015c65  test    rbx, rbx
0x180015c68  jz      short loc_180015C87
0x180015c6a  mov     eax, [rbx+8]
0x180015c6d  mov     ecx, 7FFFFFFFh
0x180015c72  cmp     eax, ecx
0x180015c74  jz      short loc_180015C84
0x180015c76  inc     eax
0x180015c78  mov     [rbx+8], eax
0x180015c7b  cmp     eax, ecx
0x180015c7d  jz      short loc_180015C84
0x180015c7f  dec     eax
0x180015c81  mov     [rbx+8], eax
0x180015c84  mov     r14d, edi
0x180015c87  mov     [rsi], rbx
0x180015c8a  mov     eax, r14d
0x180015c8d  add     rsp, 20h
0x180015c91  pop     r15
0x180015c93  pop     r14
0x180015c95  pop     rdi
0x180015c96  pop     rsi
0x180015c97  pop     rbx
0x180015c98  retn
```

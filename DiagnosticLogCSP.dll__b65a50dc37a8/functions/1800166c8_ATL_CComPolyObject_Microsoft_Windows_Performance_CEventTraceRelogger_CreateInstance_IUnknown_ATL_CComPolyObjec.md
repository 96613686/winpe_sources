# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x1800166c8`
- end: `0x180016822`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016350`

## callees

- `0x180001bb4`
- `0x1800166c8`
- `0x180039010`

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
0x1800166c8  mov     [rsp+arg_8], rdx
0x1800166cd  push    rbx
0x1800166ce  push    rsi
0x1800166cf  push    rdi
0x1800166d0  push    r14
0x1800166d2  push    r15
0x1800166d4  sub     rsp, 20h
0x1800166d8  mov     rsi, rdx
0x1800166db  mov     r15, rcx
0x1800166de  xor     edi, edi
0x1800166e0  test    rdx, rdx
0x1800166e3  jnz     short loc_1800166EF
0x1800166e5  mov     eax, 80004003h
0x1800166ea  jmp     loc_180016815
0x1800166ef  mov     [rdx], rdi
0x1800166f2  mov     r14d, 8007000Eh
0x1800166f8  mov     [rsp+48h+arg_10], r14d
0x1800166fd  mov     [rsp+48h+arg_18], rdi
0x180016702  mov     ecx, 0C0h; Size
0x180016707  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001670c  mov     rbx, rax
0x18001670f  mov     [rax+8], edi
0x180016712  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180016719  mov     [rbx], rax
0x18001671c  mov     rcx, rbx
0x18001671f  test    r15, r15
0x180016722  cmovnz  rcx, r15
0x180016726  mov     [rbx+20h], edi
0x180016729  mov     [rbx+28h], rdi
0x18001672d  mov     [rbx+30h], rdi
0x180016731  mov     [rbx+38h], rdi
0x180016735  mov     [rbx+40h], rdi
0x180016739  xor     eax, eax
0x18001673b  mov     [rbx+48h], rax
0x18001673f  mov     [rbx+50h], rdi
0x180016743  mov     [rbx+58h], rdi
0x180016747  mov     [rbx+60h], edi
0x18001674a  mov     [rbx+68h], edi
0x18001674d  mov     dword ptr [rbx+6Ch], 2
0x180016754  mov     dword ptr [rbx+70h], 32h ; '2'
0x18001675b  mov     qword ptr [rbx+74h], 0Ah
0x180016763  mov     word ptr [rbx+7Ch], 100h
0x180016769  mov     [rbx+80h], edi
0x18001676f  mov     dword ptr [rbx+84h], 7
0x180016779  or      eax, 0FFFFFFFFh
0x18001677c  mov     [rbx+88h], eax
0x180016782  mov     [rbx+90h], rdi
0x180016789  mov     [rbx+98h], rdi
0x180016790  mov     [rbx+0A0h], dil
0x180016797  mov     [rbx+0A4h], edi
0x18001679d  mov     [rbx+0A8h], eax
0x1800167a3  xor     eax, eax
0x1800167a5  mov     [rbx+0B0h], rax
0x1800167ac  mov     [rbx+0B8h], rdi
0x1800167b3  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x1800167ba  mov     [rbx+10h], rax
0x1800167be  mov     [rbx+18h], rcx
0x1800167c2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800167c9  mov     rax, [rcx]
0x1800167cc  mov     rax, [rax+8]
0x1800167d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d5  mov     [rsp+48h+arg_18], rbx
0x1800167da  jmp     short loc_1800167ED
0x1800167dc  xor     edi, edi
0x1800167de  mov     rsi, [rsp+48h+arg_8]
0x1800167e3  mov     r14d, [rsp+48h+arg_10]
0x1800167e8  mov     rbx, [rsp+48h+arg_18]
0x1800167ed  test    rbx, rbx
0x1800167f0  jz      short loc_18001680F
0x1800167f2  mov     eax, [rbx+8]
0x1800167f5  mov     ecx, 7FFFFFFFh
0x1800167fa  cmp     eax, ecx
0x1800167fc  jz      short loc_18001680C
0x1800167fe  inc     eax
0x180016800  mov     [rbx+8], eax
0x180016803  cmp     eax, ecx
0x180016805  jz      short loc_18001680C
0x180016807  dec     eax
0x180016809  mov     [rbx+8], eax
0x18001680c  mov     r14d, edi
0x18001680f  mov     [rsi], rbx
0x180016812  mov     eax, r14d
0x180016815  add     rsp, 20h
0x180016819  pop     r15
0x18001681b  pop     r14
0x18001681d  pop     rdi
0x18001681e  pop     rsi
0x18001681f  pop     rbx
0x180016820  retn
```

# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x180005384`
- end: `0x1800054e7`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800043a0`

## callees

- `0x180005384`
- `0x18002687c`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(
        char *a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned int v5; // r14d
  char *v6; // rax
  char *v7; // rbx
  char *v9; // [rsp+78h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = -2147024882;
  try
  {
    v6 = (char *)operator new(0xC0u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = 0;
      *(_QWORD *)v6 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
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
      if ( a1 )
        v6 = a1;
      *((_QWORD *)v7 + 3) = v6;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v7 = 0;
    }
    v9 = v7;
  }
  catch ( ... )
  {
    v2 = a2;
    v5 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    ++*((_DWORD *)v7 + 2);
    --*((_DWORD *)v7 + 2);
    v5 = 0;
  }
  *v2 = v7;
  return v5;
}

```

## disassembly

```asm
0x180005384  mov     [rsp+arg_8], rdx
0x180005389  push    rbx
0x18000538a  push    rsi
0x18000538b  push    rdi
0x18000538c  push    r14
0x18000538e  push    r15
0x180005390  sub     rsp, 30h
0x180005394  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000539d  mov     rsi, rdx
0x1800053a0  mov     r15, rcx
0x1800053a3  xor     edi, edi
0x1800053a5  test    rdx, rdx
0x1800053a8  jnz     short loc_1800053B4
0x1800053aa  mov     eax, 80004003h
0x1800053af  jmp     loc_1800054DB
0x1800053b4  mov     [rdx], rdi
0x1800053b7  mov     r14d, 8007000Eh
0x1800053bd  mov     [rsp+58h+arg_10], r14d
0x1800053c2  mov     [rsp+58h+arg_18], rdi
0x1800053c7  mov     ecx, 0C0h; Size
0x1800053cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800053d1  mov     rbx, rax
0x1800053d4  mov     [rsp+58h+var_30], rax
0x1800053d9  test    rax, rax
0x1800053dc  jz      loc_1800054AC
0x1800053e2  mov     [rax+8], edi
0x1800053e5  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x1800053ec  mov     [rbx], rax
0x1800053ef  mov     [rbx+20h], edi
0x1800053f2  mov     [rbx+28h], rdi
0x1800053f6  mov     [rbx+30h], rdi
0x1800053fa  mov     [rbx+38h], rdi
0x1800053fe  mov     [rbx+40h], rdi
0x180005402  xor     eax, eax
0x180005404  mov     [rbx+48h], rax
0x180005408  mov     [rbx+50h], rdi
0x18000540c  mov     [rbx+58h], rdi
0x180005410  mov     [rbx+60h], edi
0x180005413  mov     [rbx+68h], edi
0x180005416  mov     dword ptr [rbx+6Ch], 2
0x18000541d  mov     dword ptr [rbx+70h], 32h ; '2'
0x180005424  mov     qword ptr [rbx+74h], 0Ah
0x18000542c  mov     word ptr [rbx+7Ch], 100h
0x180005432  mov     [rbx+80h], edi
0x180005438  mov     dword ptr [rbx+84h], 7
0x180005442  or      eax, 0FFFFFFFFh
0x180005445  mov     [rbx+88h], eax
0x18000544b  mov     [rbx+90h], rdi
0x180005452  mov     [rbx+98h], rdi
0x180005459  mov     [rbx+0A0h], dil
0x180005460  mov     [rbx+0A4h], edi
0x180005466  mov     [rbx+0A8h], eax
0x18000546c  xor     eax, eax
0x18000546e  mov     [rbx+0B0h], rax
0x180005475  mov     [rbx+0B8h], rdi
0x18000547c  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180005483  mov     [rbx+10h], rax
0x180005487  mov     rax, rbx
0x18000548a  test    r15, r15
0x18000548d  cmovnz  rax, r15
0x180005491  mov     [rbx+18h], rax
0x180005495  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000549c  mov     rax, [rcx]
0x18000549f  mov     rax, [rax+8]
0x1800054a3  call    cs:__guard_dispatch_icall_fptr
0x1800054a9  nop
0x1800054aa  jmp     short loc_1800054AF
0x1800054ac  mov     rbx, rdi
0x1800054af  mov     [rsp+58h+arg_18], rbx
0x1800054b4  jmp     short loc_1800054C7
0x1800054b6  xor     edi, edi
0x1800054b8  mov     rsi, [rsp+58h+arg_8]
0x1800054bd  mov     r14d, [rsp+58h+arg_10]
0x1800054c2  mov     rbx, [rsp+58h+arg_18]
0x1800054c7  test    rbx, rbx
0x1800054ca  jz      short loc_1800054D5
0x1800054cc  inc     dword ptr [rbx+8]
0x1800054cf  dec     dword ptr [rbx+8]
0x1800054d2  mov     r14d, edi
0x1800054d5  mov     [rsi], rbx
0x1800054d8  mov     eax, r14d
0x1800054db  add     rsp, 30h
0x1800054df  pop     r15
0x1800054e1  pop     r14
0x1800054e3  pop     rdi
0x1800054e4  pop     rsi
0x1800054e5  pop     rbx
0x1800054e6  retn
```

# ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::CreateInstance(ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory> * *)

- ea: `0x14001056c`
- end: `0x140010610`
- name: `?CreateInstance@?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@SAJPEAPEAV12@@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010690`

## callees

- `0x1400014fc`
- `0x14001056c`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v3; // r14d
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  _DWORD *v7; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x28u);
    v5 = v4;
    if ( v4 )
    {
      v4[2] = 0;
      *((_QWORD *)v4 + 4) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v7 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
    v3 = 0;
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x14001056c  mov     [rsp+arg_18], rbx
0x140010571  mov     [rsp+arg_0], rcx
0x140010576  push    rsi
0x140010577  push    rdi
0x140010578  push    r14
0x14001057a  sub     rsp, 20h
0x14001057e  mov     rsi, rcx
0x140010581  xor     ebx, ebx
0x140010583  test    rcx, rcx
0x140010586  jnz     short loc_14001058F
0x140010588  mov     eax, 80004003h
0x14001058d  jmp     short loc_140010602
0x14001058f  mov     [rcx], rbx
0x140010592  mov     r14d, 8007000Eh
0x140010598  mov     [rsp+38h+arg_8], r14d
0x14001059d  mov     [rsp+38h+arg_10], rbx
0x1400105a2  mov     ecx, 28h ; '('; Size
0x1400105a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400105ac  mov     rdi, rax
0x1400105af  test    rax, rax
0x1400105b2  jz      short loc_1400105DA
0x1400105b4  mov     [rax+8], ebx
0x1400105b7  mov     [rax+20h], rbx
0x1400105bb  lea     rax, ??_7?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`vftable'
0x1400105c2  mov     [rdi], rax
0x1400105c5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400105cc  mov     rax, [rcx]
0x1400105cf  mov     rax, [rax+8]
0x1400105d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105d8  jmp     short loc_1400105DD
0x1400105da  mov     rdi, rbx
0x1400105dd  mov     [rsp+38h+arg_10], rdi
0x1400105e2  jmp     short loc_1400105F5
0x1400105e4  xor     ebx, ebx
0x1400105e6  mov     rsi, [rsp+38h+arg_0]
0x1400105eb  mov     r14d, [rsp+38h+arg_8]
0x1400105f0  mov     rdi, [rsp+38h+arg_10]
0x1400105f5  test    rdi, rdi
0x1400105f8  cmovnz  r14d, ebx
0x1400105fc  mov     [rsi], rdi
0x1400105ff  mov     eax, r14d
0x140010602  mov     rbx, [rsp+38h+arg_18]
0x140010607  add     rsp, 20h
0x14001060b  pop     r14
0x14001060d  pop     rdi
0x14001060e  pop     rsi
0x14001060f  retn
```

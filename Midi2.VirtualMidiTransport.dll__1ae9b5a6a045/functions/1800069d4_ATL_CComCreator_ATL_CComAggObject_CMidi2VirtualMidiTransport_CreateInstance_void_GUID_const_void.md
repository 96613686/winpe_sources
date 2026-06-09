# ATL::CComCreator<ATL::CComAggObject<CMidi2VirtualMidiTransport>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800069d4`
- end: `0x180006adc`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800069c0`

## callees

- `0x180003940`
- `0x1800069d4`
- `0x180007aa8`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2VirtualMidiTransport>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v7; // rbx
  int v8; // edi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x58u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2VirtualMidiTransport>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
    if ( v8 < 0 || (v7[80] = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800069d4  mov     [rsp+arg_10], r8
0x1800069d9  mov     [rsp+arg_8], rdx
0x1800069de  push    rbx
0x1800069df  push    rsi
0x1800069e0  push    rdi
0x1800069e1  push    r14
0x1800069e3  push    r15
0x1800069e5  sub     rsp, 30h
0x1800069e9  mov     rsi, r8
0x1800069ec  mov     r14, rdx
0x1800069ef  mov     r15, rcx
0x1800069f2  test    r8, r8
0x1800069f5  jnz     short loc_180006A01
0x1800069f7  mov     eax, 80004003h
0x1800069fc  jmp     loc_180006AD0
0x180006a01  mov     qword ptr [r8], 0
0x180006a08  mov     edi, 8007000Eh
0x180006a0d  mov     [rsp+58h+arg_18], edi
0x180006a11  mov     [rsp+58h+var_38], 0
0x180006a1a  mov     ecx, 58h ; 'X'; Size
0x180006a1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a24  mov     rbx, rax
0x180006a27  mov     dword ptr [rax+8], 0
0x180006a2e  lea     rax, ??_7?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vftable'
0x180006a35  mov     [rbx], rax
0x180006a38  xorps   xmm0, xmm0
0x180006a3b  xor     eax, eax
0x180006a3d  movups  xmmword ptr [rbx+28h], xmm0
0x180006a41  movups  xmmword ptr [rbx+38h], xmm0
0x180006a45  mov     [rbx+48h], rax
0x180006a49  mov     [rbx+50h], al
0x180006a4c  lea     rax, ??_7?$CComContainedObject@VCMidi2VirtualMidiTransport@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2VirtualMidiTransport>::`vftable'
0x180006a53  mov     [rbx+18h], rax
0x180006a57  mov     [rbx+20h], r15
0x180006a5b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006a62  mov     rax, [rcx]
0x180006a65  mov     rax, [rax+8]
0x180006a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6e  mov     [rsp+58h+var_38], rbx
0x180006a73  jmp     short loc_180006A88
0x180006a75  mov     rsi, [rsp+58h+arg_10]
0x180006a7a  mov     r14, [rsp+58h+arg_8]
0x180006a7f  mov     edi, [rsp+58h+arg_18]
0x180006a83  mov     rbx, [rsp+58h+var_38]
0x180006a88  test    rbx, rbx
0x180006a8b  jz      short loc_180006ACE
0x180006a8d  lea     rcx, [rbx+28h]; this
0x180006a91  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006a96  mov     edi, eax
0x180006a98  test    eax, eax
0x180006a9a  js      short loc_180006ABA
0x180006a9c  mov     byte ptr [rbx+50h], 1
0x180006aa0  mov     rax, [rbx]
0x180006aa3  mov     r8, rsi
0x180006aa6  mov     rdx, r14
0x180006aa9  mov     rcx, rbx
0x180006aac  mov     rax, [rax]
0x180006aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab4  mov     edi, eax
0x180006ab6  test    eax, eax
0x180006ab8  jz      short loc_180006ACE
0x180006aba  mov     rax, [rbx]
0x180006abd  mov     edx, 1
0x180006ac2  mov     rcx, rbx
0x180006ac5  mov     rax, [rax+18h]
0x180006ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ace  mov     eax, edi
0x180006ad0  add     rsp, 30h
0x180006ad4  pop     r15
0x180006ad6  pop     r14
0x180006ad8  pop     rdi
0x180006ad9  pop     rsi
0x180006ada  pop     rbx
0x180006adb  retn
```

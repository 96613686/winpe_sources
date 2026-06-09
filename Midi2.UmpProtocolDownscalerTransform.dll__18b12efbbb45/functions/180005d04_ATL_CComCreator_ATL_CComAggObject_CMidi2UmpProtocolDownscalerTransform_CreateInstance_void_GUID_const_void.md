# ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005d04`
- end: `0x180005e0c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005cf0`

## callees

- `0x180002ec0`
- `0x180005d04`
- `0x180006dd8`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>>::CreateInstance(
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
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::`vftable';
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
0x180005d04  mov     [rsp+arg_10], r8
0x180005d09  mov     [rsp+arg_8], rdx
0x180005d0e  push    rbx
0x180005d0f  push    rsi
0x180005d10  push    rdi
0x180005d11  push    r14
0x180005d13  push    r15
0x180005d15  sub     rsp, 30h
0x180005d19  mov     rsi, r8
0x180005d1c  mov     r14, rdx
0x180005d1f  mov     r15, rcx
0x180005d22  test    r8, r8
0x180005d25  jnz     short loc_180005D31
0x180005d27  mov     eax, 80004003h
0x180005d2c  jmp     loc_180005E00
0x180005d31  mov     qword ptr [r8], 0
0x180005d38  mov     edi, 8007000Eh
0x180005d3d  mov     [rsp+58h+arg_18], edi
0x180005d41  mov     [rsp+58h+var_38], 0
0x180005d4a  mov     ecx, 58h ; 'X'; Size
0x180005d4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d54  mov     rbx, rax
0x180005d57  mov     dword ptr [rax+8], 0
0x180005d5e  lea     rax, ??_7?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vftable'
0x180005d65  mov     [rbx], rax
0x180005d68  xorps   xmm0, xmm0
0x180005d6b  xor     eax, eax
0x180005d6d  movups  xmmword ptr [rbx+28h], xmm0
0x180005d71  movups  xmmword ptr [rbx+38h], xmm0
0x180005d75  mov     [rbx+48h], rax
0x180005d79  mov     [rbx+50h], al
0x180005d7c  lea     rax, ??_7?$CComContainedObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::`vftable'
0x180005d83  mov     [rbx+18h], rax
0x180005d87  mov     [rbx+20h], r15
0x180005d8b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d92  mov     rax, [rcx]
0x180005d95  mov     rax, [rax+8]
0x180005d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9e  mov     [rsp+58h+var_38], rbx
0x180005da3  jmp     short loc_180005DB8
0x180005da5  mov     rsi, [rsp+58h+arg_10]
0x180005daa  mov     r14, [rsp+58h+arg_8]
0x180005daf  mov     edi, [rsp+58h+arg_18]
0x180005db3  mov     rbx, [rsp+58h+var_38]
0x180005db8  test    rbx, rbx
0x180005dbb  jz      short loc_180005DFE
0x180005dbd  lea     rcx, [rbx+28h]; this
0x180005dc1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005dc6  mov     edi, eax
0x180005dc8  test    eax, eax
0x180005dca  js      short loc_180005DEA
0x180005dcc  mov     byte ptr [rbx+50h], 1
0x180005dd0  mov     rax, [rbx]
0x180005dd3  mov     r8, rsi
0x180005dd6  mov     rdx, r14
0x180005dd9  mov     rcx, rbx
0x180005ddc  mov     rax, [rax]
0x180005ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de4  mov     edi, eax
0x180005de6  test    eax, eax
0x180005de8  jz      short loc_180005DFE
0x180005dea  mov     rax, [rbx]
0x180005ded  mov     edx, 1
0x180005df2  mov     rcx, rbx
0x180005df5  mov     rax, [rax+18h]
0x180005df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfe  mov     eax, edi
0x180005e00  add     rsp, 30h
0x180005e04  pop     r15
0x180005e06  pop     r14
0x180005e08  pop     rdi
0x180005e09  pop     rsi
0x180005e0a  pop     rbx
0x180005e0b  retn
```

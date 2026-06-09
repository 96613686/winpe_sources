# CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002590`
- end: `0x18000265e`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001430`
- `0x180002590`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x38u);
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &CTempSignedLicenseExchangeTaskHandler::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CTempSignedLicenseExchangeTaskHandler::`vftable')(
             v7,
             a3,
             a4);
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180002590  mov     [rsp+arg_0], rbx
0x180002595  mov     [rsp+arg_8], rsi
0x18000259a  push    rdi
0x18000259b  sub     rsp, 20h
0x18000259f  mov     rdi, r9
0x1800025a2  mov     rsi, r8
0x1800025a5  test    r9, r9
0x1800025a8  jnz     short loc_1800025B4
0x1800025aa  mov     edi, 80070057h
0x1800025af  jmp     loc_18000264C
0x1800025b4  mov     qword ptr [r9], 0
0x1800025bb  test    rdx, rdx
0x1800025be  jz      short loc_1800025CA
0x1800025c0  mov     edi, 80040110h
0x1800025c5  jmp     loc_18000264C
0x1800025ca  mov     ecx, 38h ; '8'; Size
0x1800025cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025d4  mov     ecx, 1
0x1800025d9  mov     [rsp+28h+arg_18], rax
0x1800025de  mov     rbx, rax
0x1800025e1  mov     qword ptr [rax+8], 0
0x1800025e9  mov     dword ptr [rax+10h], 0
0x1800025f0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800025f8  mov     [rax+20h], ecx
0x1800025fb  mov     dword ptr [rax+24h], 0
0x180002602  mov     qword ptr [rax+28h], 0
0x18000260a  mov     qword ptr [rax+30h], 0
0x180002612  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002619  lea     rax, ??_7CTempSignedLicenseExchangeTaskHandler@@6B@; const CTempSignedLicenseExchangeTaskHandler::`vftable'
0x180002620  mov     r8, rdi
0x180002623  mov     [rbx], rax
0x180002626  mov     rdx, rsi
0x180002629  mov     [rbx+10h], ecx
0x18000262c  mov     rcx, rbx
0x18000262f  mov     rax, cs:??_7CTempSignedLicenseExchangeTaskHandler@@6B@; const CTempSignedLicenseExchangeTaskHandler::`vftable'
0x180002636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263b  mov     edi, eax
0x18000263d  mov     rcx, [rbx]
0x180002640  mov     rax, [rcx+10h]
0x180002644  mov     rcx, rbx
0x180002647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264c  mov     rbx, [rsp+28h+arg_0]
0x180002651  mov     eax, edi
0x180002653  mov     rsi, [rsp+28h+arg_8]
0x180002658  add     rsp, 20h
0x18000265c  pop     rdi
0x18000265d  retn
```

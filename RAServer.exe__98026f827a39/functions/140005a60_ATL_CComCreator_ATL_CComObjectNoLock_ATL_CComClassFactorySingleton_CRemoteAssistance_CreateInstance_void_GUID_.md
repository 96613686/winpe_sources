# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005a60`
- end: `0x140005b5e`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400012d4`
- `0x140003f00`
- `0x140005a60`
- `0x140007304`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  __int64 v5; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  int v11; // ecx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x58u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      v8[6] = 0;
      *((_BYTE *)v8 + 56) = 0;
      *((_DWORD *)v8 + 18) = 0;
      v8[10] = 0;
      *v8 = &ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`vftable';
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v9[8] = v5;
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 2));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x140005a60  mov     [rsp+arg_10], r8
0x140005a65  mov     [rsp+arg_8], rdx
0x140005a6a  mov     [rsp+arg_0], rcx
0x140005a6f  push    rbx
0x140005a70  push    rsi
0x140005a71  push    r12
0x140005a73  push    r14
0x140005a75  push    r15
0x140005a77  sub     rsp, 30h
0x140005a7b  mov     r14, r8
0x140005a7e  mov     r12, rdx
0x140005a81  mov     r15, rcx
0x140005a84  test    r8, r8
0x140005a87  jnz     short loc_140005A93
0x140005a89  mov     eax, 80004003h
0x140005a8e  jmp     loc_140005B51
0x140005a93  mov     qword ptr [r8], 0
0x140005a9a  mov     esi, 8007000Eh
0x140005a9f  mov     [rsp+58h+arg_18], esi
0x140005aa3  mov     [rsp+58h+var_38], 0
0x140005aac  mov     ecx, 58h ; 'X'; Size
0x140005ab1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005ab6  mov     rbx, rax
0x140005ab9  test    rbx, rbx
0x140005abc  jz      short loc_140005AEA
0x140005abe  mov     dword ptr [rax+8], 0
0x140005ac5  xorps   xmm0, xmm0
0x140005ac8  xor     eax, eax
0x140005aca  movups  xmmword ptr [rbx+10h], xmm0
0x140005ace  movups  xmmword ptr [rbx+20h], xmm0
0x140005ad2  mov     [rbx+30h], rax
0x140005ad6  mov     [rbx+38h], al
0x140005ad9  mov     [rbx+48h], eax
0x140005adc  mov     [rbx+50h], rax
0x140005ae0  lea     rax, ??_7?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`vftable'
0x140005ae7  mov     [rbx], rax
0x140005aea  mov     [rsp+58h+var_38], rbx
0x140005aef  jmp     short loc_140005B09
0x140005af1  mov     r14, [rsp+58h+arg_10]
0x140005af6  mov     r12, [rsp+58h+arg_8]
0x140005afb  mov     r15, [rsp+58h+arg_0]
0x140005b00  mov     esi, [rsp+58h+arg_18]
0x140005b04  mov     rbx, [rsp+58h+var_38]
0x140005b09  test    rbx, rbx
0x140005b0c  jz      short loc_140005B4F
0x140005b0e  mov     [rbx+40h], r15
0x140005b12  lea     rcx, [rbx+10h]; this
0x140005b16  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140005b1b  xor     ecx, ecx
0x140005b1d  test    eax, eax
0x140005b1f  cmovs   ecx, eax
0x140005b22  xor     esi, esi
0x140005b24  test    ecx, ecx
0x140005b26  cmovs   esi, ecx
0x140005b29  test    esi, esi
0x140005b2b  jnz     short loc_140005B47
0x140005b2d  mov     rax, [rbx]
0x140005b30  mov     r8, r14
0x140005b33  mov     rdx, r12
0x140005b36  mov     rcx, rbx
0x140005b39  mov     rax, [rax]
0x140005b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b41  mov     esi, eax
0x140005b43  test    eax, eax
0x140005b45  jz      short loc_140005B4F
0x140005b47  mov     rcx, rbx
0x140005b4a  call    ??_G?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`scalar deleting destructor'(uint)
0x140005b4f  mov     eax, esi
0x140005b51  add     rsp, 30h
0x140005b55  pop     r15
0x140005b57  pop     r14
0x140005b59  pop     r12
0x140005b5b  pop     rsi
0x140005b5c  pop     rbx
0x140005b5d  retn
```

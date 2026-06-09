# ATL::CComObjectCached<CRemoteAssistance>::CreateInstance(ATL::CComObjectCached<CRemoteAssistance> * *)

- ea: `0x140005c6c`
- end: `0x140005d3c`
- name: `?CreateInstance@?$CComObjectCached@VCRemoteAssistance@@@ATL@@SAJPEAPEAV12@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CRemoteAssistance **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400052e0`

## callees

- `0x1400012d4`
- `0x140002fec`
- `0x140003ed8`
- `0x140005c6c`
- `0x140007304`
- `0x14000a230`
- `0x14000a258`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CRemoteAssistance>::CreateInstance(CRemoteAssistance **a1)
{
  CRemoteAssistance **v1; // r14
  unsigned int v3; // esi
  CRemoteAssistance *v4; // rax
  CRemoteAssistance *v5; // rdi
  int v6; // eax
  int v7; // edx
  CRemoteAssistance *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (CRemoteAssistance *)operator new(0x78u);
    v5 = v4;
    if ( v4 )
    {
      CRemoteAssistance::CRemoteAssistance(v4);
      *(_QWORD *)v5 = &ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v5 + 1) = &ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v5 + 4);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((CRemoteAssistance *)((char *)v5 + 24));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v5 + 4);
    if ( v3 )
    {
      ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(v5);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x140005c6c  mov     [rsp+arg_18], rbx
0x140005c71  mov     [rsp+arg_0], rcx
0x140005c76  push    rsi
0x140005c77  push    rdi
0x140005c78  push    r14
0x140005c7a  sub     rsp, 20h
0x140005c7e  mov     r14, rcx
0x140005c81  test    rcx, rcx
0x140005c84  jnz     short loc_140005C90
0x140005c86  mov     eax, 80004003h
0x140005c8b  jmp     loc_140005D2E
0x140005c90  mov     qword ptr [rcx], 0
0x140005c97  mov     esi, 8007000Eh
0x140005c9c  mov     [rsp+38h+arg_8], esi
0x140005ca0  mov     [rsp+38h+arg_10], 0
0x140005ca9  mov     ecx, 78h ; 'x'; Size
0x140005cae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005cb3  mov     rdi, rax
0x140005cb6  test    rdi, rdi
0x140005cb9  jz      short loc_140005CD8
0x140005cbb  mov     rcx, rax; this
0x140005cbe  call    ??0CRemoteAssistance@@QEAA@XZ; CRemoteAssistance::CRemoteAssistance(void)
0x140005cc3  lea     rax, ??_7?$CComObjectCached@VCRemoteAssistance@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'}
0x140005cca  mov     [rdi], rax
0x140005ccd  lea     rax, ??_7?$CComObjectCached@VCRemoteAssistance@@@ATL@@6B?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x140005cd4  mov     [rdi+8], rax
0x140005cd8  mov     [rsp+38h+arg_10], rdi
0x140005cdd  jmp     short loc_140005CED
0x140005cdf  mov     r14, [rsp+38h+arg_0]
0x140005ce4  mov     esi, [rsp+38h+arg_8]
0x140005ce8  mov     rdi, [rsp+38h+arg_10]
0x140005ced  test    rdi, rdi
0x140005cf0  jz      short loc_140005D29
0x140005cf2  lea     rcx, [rdi+10h]; volatile int *
0x140005cf6  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x140005cfb  lea     rcx, [rdi+18h]; this
0x140005cff  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140005d04  xor     edx, edx
0x140005d06  test    eax, eax
0x140005d08  cmovs   edx, eax
0x140005d0b  xor     esi, esi
0x140005d0d  test    edx, edx
0x140005d0f  cmovs   esi, edx
0x140005d12  lea     rcx, [rdi+10h]; volatile int *
0x140005d16  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140005d1b  test    esi, esi
0x140005d1d  jz      short loc_140005D29
0x140005d1f  mov     rcx, rdi
0x140005d22  call    ??_G?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<CRemoteAssistance>::`scalar deleting destructor'(uint)
0x140005d27  xor     edi, edi
0x140005d29  mov     [r14], rdi
0x140005d2c  mov     eax, esi
0x140005d2e  mov     rbx, [rsp+38h+arg_18]
0x140005d33  add     rsp, 20h
0x140005d37  pop     r14
0x140005d39  pop     rdi
0x140005d3a  pop     rsi
0x140005d3b  retn
```

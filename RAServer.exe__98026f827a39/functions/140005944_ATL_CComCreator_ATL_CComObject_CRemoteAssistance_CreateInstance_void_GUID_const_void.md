# ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005944`
- end: `0x140005a56`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRemoteAssistance@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005460`

## callees

- `0x1400012d4`
- `0x140002fec`
- `0x140005944`
- `0x140007304`
- `0x14000a230`
- `0x14000a258`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRemoteAssistance>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  CRemoteAssistance *v7; // rax
  CRemoteAssistance *v8; // rdi
  int v9; // eax
  int v10; // edx
  CRemoteAssistance *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CRemoteAssistance *)operator new(0x78u);
    v8 = v7;
    if ( v7 )
    {
      CRemoteAssistance::CRemoteAssistance(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CRemoteAssistance *)((char *)v8 + 24));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CRemoteAssistance *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CRemoteAssistance *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x140005944  mov     [rsp+arg_10], r8
0x140005949  mov     [rsp+arg_8], rdx
0x14000594e  mov     [rsp+arg_0], rcx
0x140005953  push    rbx
0x140005954  push    rsi
0x140005955  push    rdi
0x140005956  push    r14
0x140005958  push    r15
0x14000595a  sub     rsp, 20h
0x14000595e  mov     r14, r8
0x140005961  mov     r15, rdx
0x140005964  test    r8, r8
0x140005967  jnz     short loc_140005973
0x140005969  mov     eax, 80004003h
0x14000596e  jmp     loc_140005A4A
0x140005973  mov     qword ptr [r8], 0
0x14000597a  mov     esi, 8007000Eh
0x14000597f  mov     dword ptr [rsp+48h+arg_0], esi
0x140005983  mov     [rsp+48h+arg_18], 0
0x14000598c  mov     ecx, 78h ; 'x'; Size
0x140005991  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005996  mov     rdi, rax
0x140005999  test    rdi, rdi
0x14000599c  jz      short loc_1400059CE
0x14000599e  mov     rcx, rax; this
0x1400059a1  call    ??0CRemoteAssistance@@QEAA@XZ; CRemoteAssistance::CRemoteAssistance(void)
0x1400059a6  lea     rax, ??_7?$CComObject@VCRemoteAssistance@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'}
0x1400059ad  mov     [rdi], rax
0x1400059b0  lea     rax, ??_7?$CComObject@VCRemoteAssistance@@@ATL@@6B?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x1400059b7  mov     [rdi+8], rax
0x1400059bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400059c2  mov     rax, [rcx]
0x1400059c5  mov     rax, [rax+8]
0x1400059c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059ce  mov     [rsp+48h+arg_18], rdi
0x1400059d3  jmp     short loc_1400059E8
0x1400059d5  mov     r14, [rsp+48h+arg_10]
0x1400059da  mov     r15, [rsp+48h+arg_8]
0x1400059df  mov     esi, dword ptr [rsp+48h+arg_0]
0x1400059e3  mov     rdi, [rsp+48h+arg_18]
0x1400059e8  test    rdi, rdi
0x1400059eb  jz      short loc_140005A48
0x1400059ed  lea     rcx, [rdi+10h]; volatile int *
0x1400059f1  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1400059f6  lea     rcx, [rdi+18h]; this
0x1400059fa  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1400059ff  xor     edx, edx
0x140005a01  test    eax, eax
0x140005a03  cmovs   edx, eax
0x140005a06  xor     esi, esi
0x140005a08  test    edx, edx
0x140005a0a  cmovs   esi, edx
0x140005a0d  lea     rcx, [rdi+10h]; volatile int *
0x140005a11  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x140005a16  test    esi, esi
0x140005a18  jnz     short loc_140005A34
0x140005a1a  mov     rax, [rdi]
0x140005a1d  mov     r8, r14
0x140005a20  mov     rdx, r15
0x140005a23  mov     rcx, rdi
0x140005a26  mov     rax, [rax]
0x140005a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a2e  mov     esi, eax
0x140005a30  test    eax, eax
0x140005a32  jz      short loc_140005A48
0x140005a34  mov     rdx, [rdi]
0x140005a37  mov     rax, [rdx+20h]
0x140005a3b  mov     edx, 1
0x140005a40  mov     rcx, rdi
0x140005a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a48  mov     eax, esi
0x140005a4a  add     rsp, 20h
0x140005a4e  pop     r15
0x140005a50  pop     r14
0x140005a52  pop     rdi
0x140005a53  pop     rsi
0x140005a54  pop     rbx
0x140005a55  retn
```

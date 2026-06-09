# ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008718`
- end: `0x18000886f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCAutoplayHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800086f0`

## callees

- `0x1800031e0`
- `0x18000684c`
- `0x180006b8c`
- `0x180008718`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CAutoplayHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // edi
  _DWORD *v7; // rax
  __int64 v8; // r9
  _DWORD *v9; // rbx
  _DWORD *v10; // rdi
  __int64 v11; // r9
  _DWORD *v14; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x10u);
    v9 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, v8);
      *(_QWORD *)v9 = &ATL::CComObject<CAutoplayHandler>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v14 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v9 = v14;
  }
  if ( v9 )
  {
    v10 = v9 + 2;
    ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(v9 + 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, v11);
    if ( *v10 != 0x7FFFFFFF )
      --*v10;
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 48LL))(v9, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180008718  mov     [rsp+arg_10], r8
0x18000871d  mov     [rsp+arg_8], rdx
0x180008722  mov     [rsp+arg_0], rcx
0x180008727  push    rbx
0x180008728  push    rsi
0x180008729  push    rdi
0x18000872a  push    r14
0x18000872c  push    r15
0x18000872e  sub     rsp, 20h
0x180008732  mov     rsi, r8
0x180008735  mov     r15, rdx
0x180008738  test    r8, r8
0x18000873b  jnz     short loc_180008747
0x18000873d  mov     eax, 80004003h
0x180008742  jmp     loc_180008863
0x180008747  mov     qword ptr [r8], 0
0x18000874e  mov     edi, 8007000Eh
0x180008753  mov     dword ptr [rsp+48h+arg_0], edi
0x180008757  mov     [rsp+48h+arg_18], 0
0x180008760  mov     ecx, 10h; Size
0x180008765  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000876a  mov     rbx, rax
0x18000876d  test    rbx, rbx
0x180008770  jz      short loc_1800087C6
0x180008772  mov     dword ptr [rax+8], 0
0x180008779  lea     r14, WPP_GLOBAL_Control
0x180008780  mov     rcx, cs:WPP_GLOBAL_Control
0x180008787  cmp     rcx, r14
0x18000878a  jz      short loc_1800087A7
0x18000878c  test    byte ptr [rcx+1Ch], 20h
0x180008790  jz      short loc_1800087A7
0x180008792  mov     edx, 0Ah
0x180008797  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x18000879e  mov     rcx, [rcx+10h]
0x1800087a2  call    WPP_SF_
0x1800087a7  lea     rax, ??_7?$CComObject@VCAutoplayHandler@@@ATL@@6B@; const ATL::CComObject<CAutoplayHandler>::`vftable'
0x1800087ae  mov     [rbx], rax
0x1800087b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800087b8  mov     rax, [rcx]
0x1800087bb  mov     rax, [rax+8]
0x1800087bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c4  jmp     short loc_1800087CD
0x1800087c6  lea     r14, WPP_GLOBAL_Control
0x1800087cd  mov     [rsp+48h+arg_18], rbx
0x1800087d2  jmp     short loc_1800087EE
0x1800087d4  lea     r14, WPP_GLOBAL_Control
0x1800087db  mov     rsi, [rsp+48h+arg_10]
0x1800087e0  mov     r15, [rsp+48h+arg_8]
0x1800087e5  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800087e9  mov     rbx, [rsp+48h+arg_18]
0x1800087ee  test    rbx, rbx
0x1800087f1  jz      short loc_180008861
0x1800087f3  lea     rdi, [rbx+8]
0x1800087f7  mov     rcx, rdi
0x1800087fa  call    ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
0x1800087ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008806  cmp     rcx, r14
0x180008809  jz      short loc_180008826
0x18000880b  test    byte ptr [rcx+1Ch], 20h
0x18000880f  jz      short loc_180008826
0x180008811  mov     edx, 0Bh
0x180008816  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x18000881d  mov     rcx, [rcx+10h]
0x180008821  call    WPP_SF_
0x180008826  mov     eax, [rdi]
0x180008828  cmp     eax, 7FFFFFFFh
0x18000882d  jz      short loc_180008833
0x18000882f  dec     eax
0x180008831  mov     [rdi], eax
0x180008833  mov     rax, [rbx]
0x180008836  mov     r8, rsi
0x180008839  mov     rdx, r15
0x18000883c  mov     rcx, rbx
0x18000883f  mov     rax, [rax]
0x180008842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008847  mov     edi, eax
0x180008849  test    eax, eax
0x18000884b  jz      short loc_180008861
0x18000884d  mov     rdx, [rbx]
0x180008850  mov     rax, [rdx+30h]
0x180008854  mov     edx, 1
0x180008859  mov     rcx, rbx
0x18000885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008861  mov     eax, edi
0x180008863  add     rsp, 20h
0x180008867  pop     r15
0x180008869  pop     r14
0x18000886b  pop     rdi
0x18000886c  pop     rsi
0x18000886d  pop     rbx
0x18000886e  retn
```

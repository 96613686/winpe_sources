# ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002f5c`
- end: `0x180003074`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCVsShellExtHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d80`

## callees

- `0x180002f5c`
- `0x1800032b0`
- `0x180007db0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CVsShellExtHandler>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  void *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64, _QWORD *); // rbx
  __int64 (__fastcall *v10)(_QWORD, __int64, _QWORD *); // r9
  unsigned int Interface; // eax
  __int64 (__fastcall ***v12)(_QWORD, __int64, _QWORD *); // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  try
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CVsShellExtHandler>::`vftable';
      *((_BYTE *)v8 + 48) = 0;
      *((_DWORD *)v8 + 13) = -1;
      *((_QWORD *)v8 + 7) = 0;
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'};
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'};
      *((_QWORD *)v8 + 4) = &ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'};
      *((_QWORD *)v8 + 5) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = **v9;
    if ( (char *)v10 == (char *)ATL::CComAggObject<CVsShellExtHandler>::QueryInterface )
      Interface = ATL::CComAggObject<CVsShellExtHandler>::QueryInterface(v9, v4, v3);
    else
      Interface = v10(v9, v4, v3);
    v7 = Interface;
    if ( Interface )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *), __int64))(*v9)[3])(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180002f5c  mov     [rsp+arg_10], r8
0x180002f61  mov     [rsp+arg_8], rdx
0x180002f66  push    rbx
0x180002f67  push    rsi
0x180002f68  push    r12
0x180002f6a  push    r14
0x180002f6c  push    r15
0x180002f6e  sub     rsp, 30h
0x180002f72  mov     r14, r8
0x180002f75  mov     r15, rdx
0x180002f78  mov     r12, rcx
0x180002f7b  test    r8, r8
0x180002f7e  jnz     short loc_180002F8A
0x180002f80  mov     eax, 80004003h
0x180002f85  jmp     loc_180003067
0x180002f8a  and     qword ptr [r8], 0
0x180002f8e  mov     esi, 8007000Eh
0x180002f93  mov     [rsp+58h+arg_18], esi
0x180002f97  and     [rsp+58h+var_38], 0
0x180002f9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002fa4  mov     ecx, 40h ; '@'; unsigned __int64
0x180002fa9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002fae  mov     rbx, rax
0x180002fb1  mov     [rsp+58h+var_30], rax
0x180002fb6  test    rax, rax
0x180002fb9  jz      short loc_18000300B
0x180002fbb  and     dword ptr [rax+8], 0
0x180002fbf  lea     rax, ??_7?$CComAggObject@VCVsShellExtHandler@@@ATL@@6B@; const ATL::CComAggObject<CVsShellExtHandler>::`vftable'
0x180002fc6  mov     [rbx], rax
0x180002fc9  mov     byte ptr [rbx+30h], 0
0x180002fcd  or      dword ptr [rbx+34h], 0FFFFFFFFh
0x180002fd1  and     qword ptr [rbx+38h], 0
0x180002fd6  lea     rax, ??_7?$CComContainedObject@VCVsShellExtHandler@@@ATL@@6BIPersistFile@@@; const ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'}
0x180002fdd  mov     [rbx+10h], rax
0x180002fe1  lea     rax, ??_7?$CComContainedObject@VCVsShellExtHandler@@@ATL@@6BIExtractIconW@@@; const ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'}
0x180002fe8  mov     [rbx+18h], rax
0x180002fec  lea     rax, ??_7?$CComContainedObject@VCVsShellExtHandler@@@ATL@@6BIPropertySetStorage@@@; const ATL::CComContainedObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'}
0x180002ff3  mov     [rbx+20h], rax
0x180002ff7  mov     [rbx+28h], r12
0x180002ffb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003002  mov     rax, [rcx]
0x180003005  call    qword ptr [rax+8]
0x180003008  nop
0x180003009  jmp     short loc_18000300D
0x18000300b  xor     ebx, ebx
0x18000300d  mov     [rsp+58h+var_38], rbx
0x180003012  jmp     short loc_180003027
0x180003014  mov     r14, [rsp+58h+arg_10]
0x180003019  mov     r15, [rsp+58h+arg_8]
0x18000301e  mov     esi, [rsp+58h+arg_18]
0x180003022  mov     rbx, [rsp+58h+var_38]
0x180003027  test    rbx, rbx
0x18000302a  jz      short loc_180003065
0x18000302c  mov     rax, [rbx]
0x18000302f  mov     r9, [rax]
0x180003032  lea     rax, ?QueryInterface@?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)
0x180003039  mov     r8, r14
0x18000303c  mov     rdx, r15
0x18000303f  mov     rcx, rbx
0x180003042  cmp     r9, rax
0x180003045  jnz     short loc_18000304E
0x180003047  call    ?QueryInterface@?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)
0x18000304c  jmp     short loc_180003051
0x18000304e  call    r9
0x180003051  mov     esi, eax
0x180003053  test    eax, eax
0x180003055  jz      short loc_180003065
0x180003057  mov     rax, [rbx]
0x18000305a  mov     edx, 1
0x18000305f  mov     rcx, rbx
0x180003062  call    qword ptr [rax+18h]
0x180003065  mov     eax, esi
0x180003067  add     rsp, 30h
0x18000306b  pop     r15
0x18000306d  pop     r14
0x18000306f  pop     r12
0x180003071  pop     rsi
0x180003072  pop     rbx
0x180003073  retn
```

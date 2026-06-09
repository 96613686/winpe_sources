# ATL::CComCreator<ATL::CComAggObject<CDfsShell>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004444`
- end: `0x18000454a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDfsShell@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004410`

## callees

- `0x180001164`
- `0x1800028e4`
- `0x180004444`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDfsShell>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  _QWORD *v10; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x150u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CDfsShell>::`vftable';
      CDfsShell::CDfsShell((CDfsShell *)(v8 + 2));
      v9[2] = &ATL::CComContainedObject<CDfsShell>::`vftable'{for `IShellExtInit'};
      v9[3] = &ATL::CComContainedObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'};
      v9[4] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v10;
  }
  if ( v9 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3);
    if ( v7 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180004444  mov     [rsp+arg_0], rbx
0x180004449  mov     [rsp+arg_10], r8
0x18000444e  mov     [rsp+arg_8], rdx
0x180004453  push    rsi
0x180004454  push    rdi
0x180004455  push    r12
0x180004457  push    r14
0x180004459  push    r15
0x18000445b  sub     rsp, 30h
0x18000445f  mov     r14, r8
0x180004462  mov     r15, rdx
0x180004465  mov     r12, rcx
0x180004468  test    r8, r8
0x18000446b  jnz     short loc_180004477
0x18000446d  mov     eax, 80004003h
0x180004472  jmp     loc_180004538
0x180004477  mov     qword ptr [r8], 0
0x18000447e  mov     esi, 8007000Eh
0x180004483  mov     [rsp+58h+arg_18], esi
0x180004487  mov     [rsp+58h+var_38], 0
0x180004490  mov     ecx, 150h; Size
0x180004495  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000449a  mov     rdi, rax
0x18000449d  test    rdi, rdi
0x1800044a0  jz      short loc_1800044E9
0x1800044a2  mov     dword ptr [rax+8], 0
0x1800044a9  lea     rax, ??_7?$CComAggObject@VCDfsShell@@@ATL@@6B@; const ATL::CComAggObject<CDfsShell>::`vftable'
0x1800044b0  mov     [rdi], rax
0x1800044b3  lea     rcx, [rdi+10h]; this
0x1800044b7  call    ??0CDfsShell@@QEAA@XZ; CDfsShell::CDfsShell(void)
0x1800044bc  lea     rax, ??_7?$CComContainedObject@VCDfsShell@@@ATL@@6BIShellExtInit@@@; const ATL::CComContainedObject<CDfsShell>::`vftable'{for `IShellExtInit'}
0x1800044c3  mov     [rdi+10h], rax
0x1800044c7  lea     rax, ??_7?$CComContainedObject@VCDfsShell@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComContainedObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'}
0x1800044ce  mov     [rdi+18h], rax
0x1800044d2  mov     [rdi+20h], r12
0x1800044d6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800044dd  mov     rax, [rcx]
0x1800044e0  mov     rax, [rax+8]
0x1800044e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e9  mov     [rsp+58h+var_38], rdi
0x1800044ee  jmp     short loc_180004503
0x1800044f0  mov     r14, [rsp+58h+arg_10]
0x1800044f5  mov     r15, [rsp+58h+arg_8]
0x1800044fa  mov     esi, [rsp+58h+arg_18]
0x1800044fe  mov     rdi, [rsp+58h+var_38]
0x180004503  test    rdi, rdi
0x180004506  jz      short loc_180004536
0x180004508  mov     rax, [rdi]
0x18000450b  mov     r8, r14
0x18000450e  mov     rdx, r15
0x180004511  mov     rcx, rdi
0x180004514  mov     rax, [rax]
0x180004517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451c  mov     esi, eax
0x18000451e  test    eax, eax
0x180004520  jz      short loc_180004536
0x180004522  mov     rdx, [rdi]
0x180004525  mov     rax, [rdx+18h]
0x180004529  mov     edx, 1
0x18000452e  mov     rcx, rdi
0x180004531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004536  mov     eax, esi
0x180004538  mov     rbx, [rsp+58h+arg_0]
0x18000453d  add     rsp, 30h
0x180004541  pop     r15
0x180004543  pop     r14
0x180004545  pop     r12
0x180004547  pop     rdi
0x180004548  pop     rsi
0x180004549  retn
```

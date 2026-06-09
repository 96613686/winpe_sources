# ATL::CComCreator<ATL::CComObject<CIMOfferRA>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1400055b8`
- end: `0x1400056db`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIMOfferRA@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400053e0`

## callees

- `0x1400012d4`
- `0x1400055b8`
- `0x140011460`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIMOfferRA>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  __int64 *v7; // rax
  __int64 *v8; // rbx
  int v9; // ecx
  __int64 *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (__int64 *)operator new(0x38u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      v7[3] = 0;
      v7[4] = 0;
      v7[6] = 0;
      ATL::CComPtr<IRendezvousSession>::operator=(v7 + 3);
      v8[2] = 0;
      v8[5] = 0;
      *v8 = (__int64)&ATL::CComObject<CIMOfferRA>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    v9 = *((_DWORD *)v8 + 2);
    if ( v9 != 0x7FFFFFFF )
    {
      *((_DWORD *)v8 + 2) = v9 + 1;
      if ( v9 != 2147483646 )
        *((_DWORD *)v8 + 2) = v9;
    }
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))*v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(__int64 *, __int64))(*v8 + 80))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1400055b8  mov     [rsp+arg_10], r8
0x1400055bd  mov     [rsp+arg_8], rdx
0x1400055c2  mov     [rsp+arg_0], rcx
0x1400055c7  push    rbx
0x1400055c8  push    rsi
0x1400055c9  push    r14
0x1400055cb  push    r15
0x1400055cd  sub     rsp, 28h
0x1400055d1  mov     r14, r8
0x1400055d4  mov     r15, rdx
0x1400055d7  test    r8, r8
0x1400055da  jnz     short loc_1400055E6
0x1400055dc  mov     eax, 80004003h
0x1400055e1  jmp     loc_1400056D0
0x1400055e6  mov     qword ptr [r8], 0
0x1400055ed  mov     esi, 8007000Eh
0x1400055f2  mov     dword ptr [rsp+48h+arg_0], esi
0x1400055f6  mov     [rsp+48h+arg_18], 0
0x1400055ff  mov     ecx, 38h ; '8'; Size
0x140005604  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005609  mov     rbx, rax
0x14000560c  test    rbx, rbx
0x14000560f  jz      short loc_140005665
0x140005611  mov     dword ptr [rax+8], 0
0x140005618  lea     rcx, [rax+18h]
0x14000561c  mov     qword ptr [rcx], 0
0x140005623  mov     qword ptr [rax+20h], 0
0x14000562b  mov     qword ptr [rax+30h], 0
0x140005633  call    ??4?$CComPtr@UIRendezvousSession@@@ATL@@QEAAPEAUIRendezvousSession@@PEAU2@@Z; ATL::CComPtr<IRendezvousSession>::operator=(IRendezvousSession *)
0x140005638  mov     qword ptr [rbx+10h], 0
0x140005640  mov     qword ptr [rbx+28h], 0
0x140005648  lea     rax, ??_7?$CComObject@VCIMOfferRA@@@ATL@@6B@; const ATL::CComObject<CIMOfferRA>::`vftable'
0x14000564f  mov     [rbx], rax
0x140005652  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005659  mov     rax, [rcx]
0x14000565c  mov     rax, [rax+8]
0x140005660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005665  mov     [rsp+48h+arg_18], rbx
0x14000566a  jmp     short loc_14000567F
0x14000566c  mov     r14, [rsp+48h+arg_10]
0x140005671  mov     r15, [rsp+48h+arg_8]
0x140005676  mov     esi, dword ptr [rsp+48h+arg_0]
0x14000567a  mov     rbx, [rsp+48h+arg_18]
0x14000567f  test    rbx, rbx
0x140005682  jz      short loc_1400056CE
0x140005684  mov     ecx, [rbx+8]
0x140005687  cmp     ecx, 7FFFFFFFh
0x14000568d  jz      short loc_1400056A0
0x14000568f  lea     eax, [rcx+1]
0x140005692  mov     [rbx+8], eax
0x140005695  cmp     ecx, 7FFFFFFEh
0x14000569b  jz      short loc_1400056A0
0x14000569d  mov     [rbx+8], ecx
0x1400056a0  mov     rax, [rbx]
0x1400056a3  mov     r8, r14
0x1400056a6  mov     rdx, r15
0x1400056a9  mov     rcx, rbx
0x1400056ac  mov     rax, [rax]
0x1400056af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056b4  mov     esi, eax
0x1400056b6  test    eax, eax
0x1400056b8  jz      short loc_1400056CE
0x1400056ba  mov     rdx, [rbx]
0x1400056bd  mov     rax, [rdx+50h]
0x1400056c1  mov     edx, 1
0x1400056c6  mov     rcx, rbx
0x1400056c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056ce  mov     eax, esi
0x1400056d0  add     rsp, 28h
0x1400056d4  pop     r15
0x1400056d6  pop     r14
0x1400056d8  pop     rsi
0x1400056d9  pop     rbx
0x1400056da  retn
```

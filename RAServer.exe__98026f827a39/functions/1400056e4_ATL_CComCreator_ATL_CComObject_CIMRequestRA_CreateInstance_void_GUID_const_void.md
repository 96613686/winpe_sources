# ATL::CComCreator<ATL::CComObject<CIMRequestRA>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1400056e4`
- end: `0x14000580f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIMRequestRA@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005410`

## callees

- `0x1400012d4`
- `0x1400056e4`
- `0x140011460`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIMRequestRA>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
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
    v7 = (__int64 *)operator new(0x40u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      v7[3] = 0;
      v7[4] = 0;
      v7[7] = 0;
      ATL::CComPtr<IRendezvousSession>::operator=(v7 + 3);
      v8[2] = 0;
      v8[5] = 0;
      v8[6] = 0;
      *v8 = (__int64)&ATL::CComObject<CIMRequestRA>::`vftable';
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
0x1400056e4  mov     [rsp+arg_10], r8
0x1400056e9  mov     [rsp+arg_8], rdx
0x1400056ee  mov     [rsp+arg_0], rcx
0x1400056f3  push    rbx
0x1400056f4  push    rsi
0x1400056f5  push    r14
0x1400056f7  push    r15
0x1400056f9  sub     rsp, 28h
0x1400056fd  mov     r14, r8
0x140005700  mov     r15, rdx
0x140005703  test    r8, r8
0x140005706  jnz     short loc_140005712
0x140005708  mov     eax, 80004003h
0x14000570d  jmp     loc_140005804
0x140005712  mov     qword ptr [r8], 0
0x140005719  mov     esi, 8007000Eh
0x14000571e  mov     dword ptr [rsp+48h+arg_0], esi
0x140005722  mov     [rsp+48h+arg_18], 0
0x14000572b  mov     ecx, 40h ; '@'; Size
0x140005730  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005735  mov     rbx, rax
0x140005738  test    rbx, rbx
0x14000573b  jz      short loc_140005799
0x14000573d  mov     dword ptr [rax+8], 0
0x140005744  lea     rcx, [rax+18h]
0x140005748  mov     qword ptr [rcx], 0
0x14000574f  mov     qword ptr [rax+20h], 0
0x140005757  mov     qword ptr [rax+38h], 0
0x14000575f  call    ??4?$CComPtr@UIRendezvousSession@@@ATL@@QEAAPEAUIRendezvousSession@@PEAU2@@Z; ATL::CComPtr<IRendezvousSession>::operator=(IRendezvousSession *)
0x140005764  mov     qword ptr [rbx+10h], 0
0x14000576c  mov     qword ptr [rbx+28h], 0
0x140005774  mov     qword ptr [rbx+30h], 0
0x14000577c  lea     rax, ??_7?$CComObject@VCIMRequestRA@@@ATL@@6B@; const ATL::CComObject<CIMRequestRA>::`vftable'
0x140005783  mov     [rbx], rax
0x140005786  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000578d  mov     rax, [rcx]
0x140005790  mov     rax, [rax+8]
0x140005794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005799  mov     [rsp+48h+arg_18], rbx
0x14000579e  jmp     short loc_1400057B3
0x1400057a0  mov     r14, [rsp+48h+arg_10]
0x1400057a5  mov     r15, [rsp+48h+arg_8]
0x1400057aa  mov     esi, dword ptr [rsp+48h+arg_0]
0x1400057ae  mov     rbx, [rsp+48h+arg_18]
0x1400057b3  test    rbx, rbx
0x1400057b6  jz      short loc_140005802
0x1400057b8  mov     ecx, [rbx+8]
0x1400057bb  cmp     ecx, 7FFFFFFFh
0x1400057c1  jz      short loc_1400057D4
0x1400057c3  lea     eax, [rcx+1]
0x1400057c6  mov     [rbx+8], eax
0x1400057c9  cmp     ecx, 7FFFFFFEh
0x1400057cf  jz      short loc_1400057D4
0x1400057d1  mov     [rbx+8], ecx
0x1400057d4  mov     rax, [rbx]
0x1400057d7  mov     r8, r14
0x1400057da  mov     rdx, r15
0x1400057dd  mov     rcx, rbx
0x1400057e0  mov     rax, [rax]
0x1400057e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057e8  mov     esi, eax
0x1400057ea  test    eax, eax
0x1400057ec  jz      short loc_140005802
0x1400057ee  mov     rdx, [rbx]
0x1400057f1  mov     rax, [rdx+50h]
0x1400057f5  mov     edx, 1
0x1400057fa  mov     rcx, rbx
0x1400057fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005802  mov     eax, esi
0x140005804  add     rsp, 28h
0x140005808  pop     r15
0x14000580a  pop     r14
0x14000580c  pop     rsi
0x14000580d  pop     rbx
0x14000580e  retn
```

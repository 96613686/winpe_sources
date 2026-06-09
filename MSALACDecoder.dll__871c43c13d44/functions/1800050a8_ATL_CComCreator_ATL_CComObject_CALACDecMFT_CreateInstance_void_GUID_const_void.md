# ATL::CComCreator<ATL::CComObject<CALACDecMFT>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800050a8`
- end: `0x18000519e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCALACDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004f70`

## callees

- `0x180001104`
- `0x180001ec4`
- `0x1800050a8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CALACDecMFT>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CALACDecMFT *v7; // rax
  CALACDecMFT *v8; // rbx
  int v9; // eax
  CALACDecMFT *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CALACDecMFT *)operator new(0xD8u);
    v8 = v7;
    if ( v7 )
    {
      CALACDecMFT::CALACDecMFT(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CALACDecMFT>::`vftable';
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v9 = (*(__int64 (__fastcall **)(CALACDecMFT *))(*(_QWORD *)v8 + 376LL))(v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CALACDecMFT *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CALACDecMFT *, __int64))(*(_QWORD *)v8 + 368LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800050a8  mov     [rsp+arg_10], r8
0x1800050ad  mov     [rsp+arg_8], rdx
0x1800050b2  mov     [rsp+arg_0], rcx
0x1800050b7  push    rbx
0x1800050b8  push    rsi
0x1800050b9  push    rdi
0x1800050ba  push    r14
0x1800050bc  sub     rsp, 28h
0x1800050c0  mov     rsi, r8
0x1800050c3  mov     r14, rdx
0x1800050c6  test    r8, r8
0x1800050c9  jnz     short loc_1800050D5
0x1800050cb  mov     eax, 80004003h
0x1800050d0  jmp     loc_180005194
0x1800050d5  mov     qword ptr [r8], 0
0x1800050dc  mov     edi, 8007000Eh
0x1800050e1  mov     dword ptr [rsp+48h+arg_0], edi
0x1800050e5  mov     [rsp+48h+arg_18], 0
0x1800050ee  mov     ecx, 0D8h; Size
0x1800050f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050f8  mov     rbx, rax
0x1800050fb  test    rbx, rbx
0x1800050fe  jz      short loc_180005125
0x180005100  mov     rcx, rax; this
0x180005103  call    ??0CALACDecMFT@@QEAA@XZ; CALACDecMFT::CALACDecMFT(void)
0x180005108  lea     rax, ??_7?$CComObject@VCALACDecMFT@@@ATL@@6B@; const ATL::CComObject<CALACDecMFT>::`vftable'
0x18000510f  mov     [rbx], rax
0x180005112  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005119  mov     rax, [rcx]
0x18000511c  mov     rax, [rax+8]
0x180005120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005125  mov     [rsp+48h+arg_18], rbx
0x18000512a  jmp     short loc_18000513F
0x18000512c  mov     rsi, [rsp+48h+arg_10]
0x180005131  mov     r14, [rsp+48h+arg_8]
0x180005136  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000513a  mov     rbx, [rsp+48h+arg_18]
0x18000513f  test    rbx, rbx
0x180005142  jz      short loc_180005192
0x180005144  mov     rax, [rbx]
0x180005147  mov     rcx, rbx
0x18000514a  mov     rax, [rax+178h]
0x180005151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005156  xor     edi, edi
0x180005158  test    eax, eax
0x18000515a  cmovs   edi, eax
0x18000515d  test    edi, edi
0x18000515f  jnz     short loc_18000517B
0x180005161  mov     rax, [rbx]
0x180005164  mov     r8, rsi
0x180005167  mov     rdx, r14
0x18000516a  mov     rcx, rbx
0x18000516d  mov     rax, [rax]
0x180005170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005175  mov     edi, eax
0x180005177  test    eax, eax
0x180005179  jz      short loc_180005192
0x18000517b  mov     rdx, [rbx]
0x18000517e  mov     rax, [rdx+170h]
0x180005185  mov     edx, 1
0x18000518a  mov     rcx, rbx
0x18000518d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005192  mov     eax, edi
0x180005194  add     rsp, 28h
0x180005198  pop     r14
0x18000519a  pop     rdi
0x18000519b  pop     rsi
0x18000519c  pop     rbx
0x18000519d  retn
```

# ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004b24`
- end: `0x180004c2c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x180001f40`
- `0x180004b24`
- `0x180005bf8`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2UMP2BSTransform>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v7; // rbx
  int v8; // edi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x58u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2UMP2BSTransform>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2UMP2BSTransform>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
    if ( v8 < 0 || (v7[80] = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004b24  mov     [rsp+arg_10], r8
0x180004b29  mov     [rsp+arg_8], rdx
0x180004b2e  push    rbx
0x180004b2f  push    rsi
0x180004b30  push    rdi
0x180004b31  push    r14
0x180004b33  push    r15
0x180004b35  sub     rsp, 30h
0x180004b39  mov     rsi, r8
0x180004b3c  mov     r14, rdx
0x180004b3f  mov     r15, rcx
0x180004b42  test    r8, r8
0x180004b45  jnz     short loc_180004B51
0x180004b47  mov     eax, 80004003h
0x180004b4c  jmp     loc_180004C20
0x180004b51  mov     qword ptr [r8], 0
0x180004b58  mov     edi, 8007000Eh
0x180004b5d  mov     [rsp+58h+arg_18], edi
0x180004b61  mov     [rsp+58h+var_38], 0
0x180004b6a  mov     ecx, 58h ; 'X'; Size
0x180004b6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b74  mov     rbx, rax
0x180004b77  mov     dword ptr [rax+8], 0
0x180004b7e  lea     rax, ??_7?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2UMP2BSTransform>::`vftable'
0x180004b85  mov     [rbx], rax
0x180004b88  xorps   xmm0, xmm0
0x180004b8b  xor     eax, eax
0x180004b8d  movups  xmmword ptr [rbx+28h], xmm0
0x180004b91  movups  xmmword ptr [rbx+38h], xmm0
0x180004b95  mov     [rbx+48h], rax
0x180004b99  mov     [rbx+50h], al
0x180004b9c  lea     rax, ??_7?$CComContainedObject@VCMidi2UMP2BSTransform@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2UMP2BSTransform>::`vftable'
0x180004ba3  mov     [rbx+18h], rax
0x180004ba7  mov     [rbx+20h], r15
0x180004bab  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004bb2  mov     rax, [rcx]
0x180004bb5  mov     rax, [rax+8]
0x180004bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbe  mov     [rsp+58h+var_38], rbx
0x180004bc3  jmp     short loc_180004BD8
0x180004bc5  mov     rsi, [rsp+58h+arg_10]
0x180004bca  mov     r14, [rsp+58h+arg_8]
0x180004bcf  mov     edi, [rsp+58h+arg_18]
0x180004bd3  mov     rbx, [rsp+58h+var_38]
0x180004bd8  test    rbx, rbx
0x180004bdb  jz      short loc_180004C1E
0x180004bdd  lea     rcx, [rbx+28h]; this
0x180004be1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004be6  mov     edi, eax
0x180004be8  test    eax, eax
0x180004bea  js      short loc_180004C0A
0x180004bec  mov     byte ptr [rbx+50h], 1
0x180004bf0  mov     rax, [rbx]
0x180004bf3  mov     r8, rsi
0x180004bf6  mov     rdx, r14
0x180004bf9  mov     rcx, rbx
0x180004bfc  mov     rax, [rax]
0x180004bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c04  mov     edi, eax
0x180004c06  test    eax, eax
0x180004c08  jz      short loc_180004C1E
0x180004c0a  mov     rax, [rbx]
0x180004c0d  mov     edx, 1
0x180004c12  mov     rcx, rbx
0x180004c15  mov     rax, [rax+18h]
0x180004c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1e  mov     eax, edi
0x180004c20  add     rsp, 30h
0x180004c24  pop     r15
0x180004c26  pop     r14
0x180004c28  pop     rdi
0x180004c29  pop     rsi
0x180004c2a  pop     rbx
0x180004c2b  retn
```

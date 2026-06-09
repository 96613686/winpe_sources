# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002310`
- end: `0x180002413`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002310`
- `0x180002920`
- `0x18000d1a8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002354`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002354`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 (__fastcall **a1)(_QWORD, __int64, _QWORD *),
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  HLOCAL v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = LocalAlloc(0x40u, 0x48u);
  v8 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v8[8] = a1;
    v9 = ATL::CComSafeDeleteCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 2));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**v8)(v8, a2, a3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x180002310  mov     [rsp+arg_10], r8
0x180002315  mov     [rsp+arg_8], rdx
0x18000231a  mov     [rsp+arg_0], rcx
0x18000231f  push    rbx
0x180002320  push    rsi
0x180002321  push    rdi
0x180002322  push    r14
0x180002324  push    r15
0x180002326  sub     rsp, 30h
0x18000232a  mov     rsi, r8
0x18000232d  mov     r15, rdx
0x180002330  mov     r14, rcx
0x180002333  test    r8, r8
0x180002336  jz      loc_1800023E8
0x18000233c  mov     qword ptr [r8], 0
0x180002343  mov     edi, 8007000Eh
0x180002348  mov     [rsp+58h+arg_18], edi
0x18000234c  mov     edx, 48h ; 'H'; uBytes
0x180002351  lea     ecx, [rdx-8]; uFlags
0x180002354  call    cs:__imp_LocalAlloc
0x18000235b  nop     dword ptr [rax+rax+00h]
0x180002360  mov     rbx, rax
0x180002363  mov     [rsp+58h+var_38], rax
0x180002368  test    rax, rax
0x18000236b  jz      short loc_1800023E4
0x18000236d  mov     dword ptr [rax+8], 0
0x180002374  xorps   xmm0, xmm0
0x180002377  xor     eax, eax
0x180002379  movups  xmmword ptr [rbx+10h], xmm0
0x18000237d  movups  xmmword ptr [rbx+20h], xmm0
0x180002381  mov     [rbx+30h], rax
0x180002385  mov     [rbx+38h], al
0x180002388  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000238f  mov     [rbx], rax
0x180002392  mov     [rsp+58h+var_38], rbx
0x180002397  test    rbx, rbx
0x18000239a  jz      short loc_1800023D5
0x18000239c  mov     [rbx+40h], r14
0x1800023a0  lea     rcx, [rbx+10h]; this
0x1800023a4  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800023a9  xor     ecx, ecx
0x1800023ab  test    eax, eax
0x1800023ad  cmovs   ecx, eax
0x1800023b0  xor     edi, edi
0x1800023b2  test    ecx, ecx
0x1800023b4  cmovs   edi, ecx
0x1800023b7  test    edi, edi
0x1800023b9  jnz     short loc_180002409
0x1800023bb  mov     rax, [rbx]
0x1800023be  mov     r8, rsi
0x1800023c1  mov     rdx, r15
0x1800023c4  mov     rcx, rbx
0x1800023c7  mov     rax, [rax]
0x1800023ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023cf  mov     edi, eax
0x1800023d1  test    eax, eax
0x1800023d3  jnz     short loc_180002409
0x1800023d5  mov     eax, edi
0x1800023d7  add     rsp, 30h
0x1800023db  pop     r15
0x1800023dd  pop     r14
0x1800023df  pop     rdi
0x1800023e0  pop     rsi
0x1800023e1  pop     rbx
0x1800023e2  retn
0x1800023e4  xor     ebx, ebx
0x1800023e6  jmp     short loc_180002392
0x1800023e8  mov     eax, 80004003h
0x1800023ed  jmp     short loc_1800023D7
0x1800023ef  mov     rsi, [rsp+58h+arg_10]
0x1800023f4  mov     r15, [rsp+58h+arg_8]
0x1800023f9  mov     r14, [rsp+58h+arg_0]
0x1800023fe  mov     edi, [rsp+58h+arg_18]
0x180002402  mov     rbx, [rsp+58h+var_38]
0x180002407  jmp     short loc_180002397
0x180002409  mov     rcx, rbx; hMem
0x18000240c  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x180002411  jmp     short loc_1800023D5
```

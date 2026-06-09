# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800051b0`
- end: `0x1800052da`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001104`
- `0x180001574`
- `0x1800051b0`
- `0x1800054ac`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052b6`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_10], r8
0x1800051b5  mov     [rsp+arg_8], rdx
0x1800051ba  mov     [rsp+arg_0], rcx
0x1800051bf  push    rbx
0x1800051c0  push    rsi
0x1800051c1  push    r12
0x1800051c3  push    r13
0x1800051c5  push    r14
0x1800051c7  push    r15
0x1800051c9  sub     rsp, 38h
0x1800051cd  mov     r15, r8
0x1800051d0  mov     r12, rdx
0x1800051d3  mov     r14, rcx
0x1800051d6  test    r8, r8
0x1800051d9  jnz     short loc_1800051E5
0x1800051db  mov     eax, 80004003h
0x1800051e0  jmp     loc_1800052CB
0x1800051e5  mov     qword ptr [r8], 0
0x1800051ec  mov     esi, 8007000Eh
0x1800051f1  mov     [rsp+68h+arg_18], esi
0x1800051f8  mov     [rsp+68h+var_48], 0
0x180005201  mov     ecx, 48h ; 'H'; Size
0x180005206  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000520b  mov     rbx, rax
0x18000520e  test    rbx, rbx
0x180005211  jz      short loc_180005238
0x180005213  mov     dword ptr [rax+8], 0
0x18000521a  xorps   xmm0, xmm0
0x18000521d  xor     eax, eax
0x18000521f  movups  xmmword ptr [rbx+10h], xmm0
0x180005223  movups  xmmword ptr [rbx+20h], xmm0
0x180005227  mov     [rbx+30h], rax
0x18000522b  mov     [rbx+38h], al
0x18000522e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180005235  mov     [rbx], rax
0x180005238  mov     [rsp+68h+var_48], rbx
0x18000523d  jmp     short loc_18000525D
0x18000523f  mov     r15, [rsp+68h+arg_10]
0x180005247  mov     r12, [rsp+68h+arg_8]
0x18000524c  mov     r14, [rsp+68h+arg_0]
0x180005251  mov     esi, [rsp+68h+arg_18]
0x180005258  mov     rbx, [rsp+68h+var_48]
0x18000525d  test    rbx, rbx
0x180005260  jz      short loc_1800052C9
0x180005262  mov     [rbx+40h], r14
0x180005266  lea     rcx, [rbx+10h]; this
0x18000526a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000526f  mov     esi, eax
0x180005271  lea     r14, [rbx+38h]
0x180005275  test    eax, eax
0x180005277  js      short loc_180005297
0x180005279  mov     byte ptr [r14], 1
0x18000527d  mov     rax, [rbx]
0x180005280  mov     r8, r15
0x180005283  mov     rdx, r12
0x180005286  mov     rcx, rbx
0x180005289  mov     rax, [rax]
0x18000528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005291  mov     esi, eax
0x180005293  test    eax, eax
0x180005295  jz      short loc_1800052C9
0x180005297  mov     dword ptr [rbx+8], 0C0000001h
0x18000529e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800052a5  mov     [rbx], rax
0x1800052a8  cmp     byte ptr [r14], 0
0x1800052ac  jz      short loc_1800052BC
0x1800052ae  mov     byte ptr [r14], 0
0x1800052b2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800052b6  call    cs:__imp_DeleteCriticalSection
0x1800052bc  mov     edx, 48h ; 'H'
0x1800052c1  mov     rcx, rbx; Block
0x1800052c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800052c9  mov     eax, esi
0x1800052cb  add     rsp, 38h
0x1800052cf  pop     r15
0x1800052d1  pop     r14
0x1800052d3  pop     r13
0x1800052d5  pop     r12
0x1800052d7  pop     rsi
0x1800052d8  pop     rbx
0x1800052d9  retn
```

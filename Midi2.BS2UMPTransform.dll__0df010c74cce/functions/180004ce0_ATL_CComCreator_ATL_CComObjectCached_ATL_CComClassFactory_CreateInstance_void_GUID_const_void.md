# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004ce0`
- end: `0x180004df4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e84`
- `0x180001eb0`
- `0x180004ce0`
- `0x180005b68`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004dd2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004dd2`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  __int64 v5; // r15
  _BYTE *v7; // rbx
  int v8; // esi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      *((_DWORD *)v7 + 2) = -1073741823;
      *(_QWORD *)v7 = &ATL::CComClassFactory::`vftable';
      if ( v7[56] )
      {
        v7[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      }
      operator delete(v7);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004ce0  mov     [rsp+arg_10], r8
0x180004ce5  mov     [rsp+arg_8], rdx
0x180004cea  mov     [rsp+arg_0], rcx
0x180004cef  push    rbx
0x180004cf0  push    rsi
0x180004cf1  push    r12
0x180004cf3  push    r14
0x180004cf5  push    r15
0x180004cf7  sub     rsp, 30h
0x180004cfb  mov     r14, r8
0x180004cfe  mov     r12, rdx
0x180004d01  mov     r15, rcx
0x180004d04  test    r8, r8
0x180004d07  jnz     short loc_180004D13
0x180004d09  mov     eax, 80004003h
0x180004d0e  jmp     loc_180004DE7
0x180004d13  mov     qword ptr [r8], 0
0x180004d1a  mov     esi, 8007000Eh
0x180004d1f  mov     [rsp+58h+arg_18], esi
0x180004d23  mov     [rsp+58h+var_38], 0
0x180004d2c  mov     ecx, 48h ; 'H'; Size
0x180004d31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d36  mov     rbx, rax
0x180004d39  mov     dword ptr [rax+8], 0
0x180004d40  xorps   xmm0, xmm0
0x180004d43  xor     eax, eax
0x180004d45  movups  xmmword ptr [rbx+10h], xmm0
0x180004d49  movups  xmmword ptr [rbx+20h], xmm0
0x180004d4d  mov     [rbx+30h], rax
0x180004d51  mov     [rbx+38h], al
0x180004d54  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004d5b  mov     [rbx], rax
0x180004d5e  mov     [rsp+58h+var_38], rbx
0x180004d63  jmp     short loc_180004D7D
0x180004d65  mov     r14, [rsp+58h+arg_10]
0x180004d6a  mov     r12, [rsp+58h+arg_8]
0x180004d6f  mov     r15, [rsp+58h+arg_0]
0x180004d74  mov     esi, [rsp+58h+arg_18]
0x180004d78  mov     rbx, [rsp+58h+var_38]
0x180004d7d  test    rbx, rbx
0x180004d80  jz      short loc_180004DE5
0x180004d82  mov     [rbx+40h], r15
0x180004d86  lea     rcx, [rbx+10h]; this
0x180004d8a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004d8f  mov     esi, eax
0x180004d91  test    eax, eax
0x180004d93  js      short loc_180004DB3
0x180004d95  mov     byte ptr [rbx+38h], 1
0x180004d99  mov     rax, [rbx]
0x180004d9c  mov     r8, r14
0x180004d9f  mov     rdx, r12
0x180004da2  mov     rcx, rbx
0x180004da5  mov     rax, [rax]
0x180004da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dad  mov     esi, eax
0x180004daf  test    eax, eax
0x180004db1  jz      short loc_180004DE5
0x180004db3  mov     dword ptr [rbx+8], 0C0000001h
0x180004dba  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004dc1  mov     [rbx], rax
0x180004dc4  cmp     byte ptr [rbx+38h], 0
0x180004dc8  jz      short loc_180004DD8
0x180004dca  mov     byte ptr [rbx+38h], 0
0x180004dce  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004dd2  call    cs:__imp_DeleteCriticalSection
0x180004dd8  mov     edx, 48h ; 'H'
0x180004ddd  mov     rcx, rbx; Block
0x180004de0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004de5  mov     eax, esi
0x180004de7  add     rsp, 30h
0x180004deb  pop     r15
0x180004ded  pop     r14
0x180004def  pop     r12
0x180004df1  pop     rsi
0x180004df2  pop     rbx
0x180004df3  retn
```

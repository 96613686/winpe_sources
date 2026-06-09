# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005f50`
- end: `0x180006064`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x180002ec0`
- `0x180005f50`
- `0x180006dd8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006042`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006042`

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
0x180005f50  mov     [rsp+arg_10], r8
0x180005f55  mov     [rsp+arg_8], rdx
0x180005f5a  mov     [rsp+arg_0], rcx
0x180005f5f  push    rbx
0x180005f60  push    rsi
0x180005f61  push    r12
0x180005f63  push    r14
0x180005f65  push    r15
0x180005f67  sub     rsp, 30h
0x180005f6b  mov     r14, r8
0x180005f6e  mov     r12, rdx
0x180005f71  mov     r15, rcx
0x180005f74  test    r8, r8
0x180005f77  jnz     short loc_180005F83
0x180005f79  mov     eax, 80004003h
0x180005f7e  jmp     loc_180006057
0x180005f83  mov     qword ptr [r8], 0
0x180005f8a  mov     esi, 8007000Eh
0x180005f8f  mov     [rsp+58h+arg_18], esi
0x180005f93  mov     [rsp+58h+var_38], 0
0x180005f9c  mov     ecx, 48h ; 'H'; Size
0x180005fa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fa6  mov     rbx, rax
0x180005fa9  mov     dword ptr [rax+8], 0
0x180005fb0  xorps   xmm0, xmm0
0x180005fb3  xor     eax, eax
0x180005fb5  movups  xmmword ptr [rbx+10h], xmm0
0x180005fb9  movups  xmmword ptr [rbx+20h], xmm0
0x180005fbd  mov     [rbx+30h], rax
0x180005fc1  mov     [rbx+38h], al
0x180005fc4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180005fcb  mov     [rbx], rax
0x180005fce  mov     [rsp+58h+var_38], rbx
0x180005fd3  jmp     short loc_180005FED
0x180005fd5  mov     r14, [rsp+58h+arg_10]
0x180005fda  mov     r12, [rsp+58h+arg_8]
0x180005fdf  mov     r15, [rsp+58h+arg_0]
0x180005fe4  mov     esi, [rsp+58h+arg_18]
0x180005fe8  mov     rbx, [rsp+58h+var_38]
0x180005fed  test    rbx, rbx
0x180005ff0  jz      short loc_180006055
0x180005ff2  mov     [rbx+40h], r15
0x180005ff6  lea     rcx, [rbx+10h]; this
0x180005ffa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005fff  mov     esi, eax
0x180006001  test    eax, eax
0x180006003  js      short loc_180006023
0x180006005  mov     byte ptr [rbx+38h], 1
0x180006009  mov     rax, [rbx]
0x18000600c  mov     r8, r14
0x18000600f  mov     rdx, r12
0x180006012  mov     rcx, rbx
0x180006015  mov     rax, [rax]
0x180006018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601d  mov     esi, eax
0x18000601f  test    eax, eax
0x180006021  jz      short loc_180006055
0x180006023  mov     dword ptr [rbx+8], 0C0000001h
0x18000602a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006031  mov     [rbx], rax
0x180006034  cmp     byte ptr [rbx+38h], 0
0x180006038  jz      short loc_180006048
0x18000603a  mov     byte ptr [rbx+38h], 0
0x18000603e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006042  call    cs:__imp_DeleteCriticalSection
0x180006048  mov     edx, 48h ; 'H'
0x18000604d  mov     rcx, rbx; Block
0x180006050  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006055  mov     eax, esi
0x180006057  add     rsp, 30h
0x18000605b  pop     r15
0x18000605d  pop     r14
0x18000605f  pop     r12
0x180006061  pop     rsi
0x180006062  pop     rbx
0x180006063  retn
```

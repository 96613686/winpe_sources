# ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004a94`
- end: `0x180004b9c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004a80`

## callees

- `0x180001eb0`
- `0x180004a94`
- `0x180005b68`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2BS2UMPTransform>>::CreateInstance(
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
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2BS2UMPTransform>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2BS2UMPTransform>::`vftable';
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
0x180004a94  mov     [rsp+arg_10], r8
0x180004a99  mov     [rsp+arg_8], rdx
0x180004a9e  push    rbx
0x180004a9f  push    rsi
0x180004aa0  push    rdi
0x180004aa1  push    r14
0x180004aa3  push    r15
0x180004aa5  sub     rsp, 30h
0x180004aa9  mov     rsi, r8
0x180004aac  mov     r14, rdx
0x180004aaf  mov     r15, rcx
0x180004ab2  test    r8, r8
0x180004ab5  jnz     short loc_180004AC1
0x180004ab7  mov     eax, 80004003h
0x180004abc  jmp     loc_180004B90
0x180004ac1  mov     qword ptr [r8], 0
0x180004ac8  mov     edi, 8007000Eh
0x180004acd  mov     [rsp+58h+arg_18], edi
0x180004ad1  mov     [rsp+58h+var_38], 0
0x180004ada  mov     ecx, 58h ; 'X'; Size
0x180004adf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ae4  mov     rbx, rax
0x180004ae7  mov     dword ptr [rax+8], 0
0x180004aee  lea     rax, ??_7?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2BS2UMPTransform>::`vftable'
0x180004af5  mov     [rbx], rax
0x180004af8  xorps   xmm0, xmm0
0x180004afb  xor     eax, eax
0x180004afd  movups  xmmword ptr [rbx+28h], xmm0
0x180004b01  movups  xmmword ptr [rbx+38h], xmm0
0x180004b05  mov     [rbx+48h], rax
0x180004b09  mov     [rbx+50h], al
0x180004b0c  lea     rax, ??_7?$CComContainedObject@VCMidi2BS2UMPTransform@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2BS2UMPTransform>::`vftable'
0x180004b13  mov     [rbx+18h], rax
0x180004b17  mov     [rbx+20h], r15
0x180004b1b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b22  mov     rax, [rcx]
0x180004b25  mov     rax, [rax+8]
0x180004b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2e  mov     [rsp+58h+var_38], rbx
0x180004b33  jmp     short loc_180004B48
0x180004b35  mov     rsi, [rsp+58h+arg_10]
0x180004b3a  mov     r14, [rsp+58h+arg_8]
0x180004b3f  mov     edi, [rsp+58h+arg_18]
0x180004b43  mov     rbx, [rsp+58h+var_38]
0x180004b48  test    rbx, rbx
0x180004b4b  jz      short loc_180004B8E
0x180004b4d  lea     rcx, [rbx+28h]; this
0x180004b51  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004b56  mov     edi, eax
0x180004b58  test    eax, eax
0x180004b5a  js      short loc_180004B7A
0x180004b5c  mov     byte ptr [rbx+50h], 1
0x180004b60  mov     rax, [rbx]
0x180004b63  mov     r8, rsi
0x180004b66  mov     rdx, r14
0x180004b69  mov     rcx, rbx
0x180004b6c  mov     rax, [rax]
0x180004b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b74  mov     edi, eax
0x180004b76  test    eax, eax
0x180004b78  jz      short loc_180004B8E
0x180004b7a  mov     rax, [rbx]
0x180004b7d  mov     edx, 1
0x180004b82  mov     rcx, rbx
0x180004b85  mov     rax, [rax+18h]
0x180004b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8e  mov     eax, edi
0x180004b90  add     rsp, 30h
0x180004b94  pop     r15
0x180004b96  pop     r14
0x180004b98  pop     rdi
0x180004b99  pop     rsi
0x180004b9a  pop     rbx
0x180004b9b  retn
```

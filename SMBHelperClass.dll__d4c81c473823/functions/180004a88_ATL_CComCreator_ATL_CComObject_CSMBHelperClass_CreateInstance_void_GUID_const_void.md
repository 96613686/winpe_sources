# ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004a88`
- end: `0x180004bd8`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCSMBHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004a60`

## callees

- `0x18000123c`
- `0x180002974`
- `0x180004a88`
- `0x1800058dc`
- `0x180012010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CSMBHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CSMBHelperClass *v7; // rax
  CSMBHelperClass *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  CSMBHelperClass *v15; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CSMBHelperClass *)operator new(0x130u);
    v8 = v7;
    if ( v7 )
    {
      CSMBHelperClass::CSMBHelperClass(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelperInfo'};
      *((_QWORD *)v8 + 7) = &ATL::CComObject<CSMBHelperClass>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = *((_DWORD *)v8 + 16);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 16, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((CSMBHelperClass *)((char *)v8 + 72));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 112) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *((_DWORD *)v8 + 16);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 16, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CSMBHelperClass *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CSMBHelperClass *, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004a88  mov     [rsp+arg_10], r8
0x180004a8d  mov     [rsp+arg_8], rdx
0x180004a92  mov     [rsp+arg_0], rcx
0x180004a97  push    rbx
0x180004a98  push    rsi
0x180004a99  push    rdi
0x180004a9a  push    r14
0x180004a9c  push    r15
0x180004a9e  sub     rsp, 30h
0x180004aa2  mov     rsi, r8
0x180004aa5  mov     r14, rdx
0x180004aa8  test    r8, r8
0x180004aab  jnz     short loc_180004AB7
0x180004aad  mov     eax, 80004003h
0x180004ab2  jmp     loc_180004BCC
0x180004ab7  mov     qword ptr [r8], 0
0x180004abe  mov     edi, 8007000Eh
0x180004ac3  mov     dword ptr [rsp+58h+arg_0], edi
0x180004ac7  mov     [rsp+58h+arg_18], 0
0x180004ad0  mov     ecx, 130h; Size
0x180004ad5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ada  mov     rbx, rax
0x180004add  mov     [rsp+58h+var_38], rax
0x180004ae2  test    rbx, rbx
0x180004ae5  jz      short loc_180004B23
0x180004ae7  mov     rcx, rax; this
0x180004aea  call    ??0CSMBHelperClass@@QEAA@XZ; CSMBHelperClass::CSMBHelperClass(void)
0x180004aef  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelper'}
0x180004af6  mov     [rbx], rax
0x180004af9  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180004b00  mov     [rbx+8], rax
0x180004b04  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6B@; const ATL::CComObject<CSMBHelperClass>::`vftable'
0x180004b0b  mov     [rbx+38h], rax
0x180004b0f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b16  mov     rax, [rcx]
0x180004b19  mov     rax, [rax+8]
0x180004b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b22  nop
0x180004b23  mov     [rsp+58h+arg_18], rbx
0x180004b28  jmp     short loc_180004B3D
0x180004b2a  mov     rsi, [rsp+58h+arg_10]
0x180004b2f  mov     r14, [rsp+58h+arg_8]
0x180004b34  mov     edi, dword ptr [rsp+58h+arg_0]
0x180004b38  mov     rbx, [rsp+58h+arg_18]
0x180004b3d  test    rbx, rbx
0x180004b40  jz      loc_180004BCA
0x180004b46  mov     r15d, 7FFFFFFFh
0x180004b4c  jmp     short loc_180004B58
0x180004b4e  lea     ecx, [rax+1]
0x180004b51  lock cmpxchg [rbx+40h], ecx
0x180004b56  jz      short loc_180004B60
0x180004b58  mov     eax, [rbx+40h]
0x180004b5b  cmp     eax, r15d
0x180004b5e  jnz     short loc_180004B4E
0x180004b60  lea     rcx, [rbx+48h]; this
0x180004b64  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004b69  mov     ecx, eax
0x180004b6b  test    eax, eax
0x180004b6d  js      short loc_180004B73
0x180004b6f  mov     byte ptr [rbx+70h], 1
0x180004b73  xor     eax, eax
0x180004b75  test    ecx, ecx
0x180004b77  cmovs   eax, ecx
0x180004b7a  xor     edi, edi
0x180004b7c  test    eax, eax
0x180004b7e  cmovs   edi, eax
0x180004b81  jmp     short loc_180004B8D
0x180004b83  lea     ecx, [rax-1]
0x180004b86  lock cmpxchg [rbx+40h], ecx
0x180004b8b  jz      short loc_180004B95
0x180004b8d  mov     eax, [rbx+40h]
0x180004b90  cmp     eax, r15d
0x180004b93  jnz     short loc_180004B83
0x180004b95  test    edi, edi
0x180004b97  jnz     short loc_180004BB3
0x180004b99  mov     rax, [rbx]
0x180004b9c  mov     r8, rsi
0x180004b9f  mov     rdx, r14
0x180004ba2  mov     rcx, rbx
0x180004ba5  mov     rax, [rax]
0x180004ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bad  mov     edi, eax
0x180004baf  test    eax, eax
0x180004bb1  jz      short loc_180004BCA
0x180004bb3  mov     r8, [rbx]
0x180004bb6  mov     edx, 1
0x180004bbb  mov     rcx, rbx
0x180004bbe  mov     rax, [r8+0A8h]
0x180004bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bca  mov     eax, edi
0x180004bcc  add     rsp, 30h
0x180004bd0  pop     r15
0x180004bd2  pop     r14
0x180004bd4  pop     rdi
0x180004bd5  pop     rsi
0x180004bd6  pop     rbx
0x180004bd7  retn
```

# ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)

- ea: `0x180003a70`
- end: `0x180003bd3`
- name: `?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z`
- size: `355`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002500`
- `0x1800035f0`
- `0x180004490`
- `0x180016400`
- `0x180016718`

## callees

- `0x180003a70`
- `0x180006230`
- `0x18000f088`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUser>::CreateInstance(_QWORD *a1)
{
  unsigned int v2; // r14d
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  signed __int32 i; // eax
  int v6; // eax
  signed __int32 j; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v2 = -2147024882;
  v3 = operator new(0x68u);
  v4 = v3;
  if ( v3 )
  {
    v3[2] = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_BYTE *)v3 + 56) = 0;
    *((_QWORD *)v3 + 12) = 0;
    *(_QWORD *)v3 = &ATL::CComObject<CConnectedUser>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v4 = 0;
  }
  if ( v4 )
  {
    for ( i = v4[2]; i != 0x7FFFFFFF; i = v4[2] )
    {
      if ( i == _InterlockedCompareExchange(v4 + 2, i + 1, i) )
        break;
    }
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 4));
    if ( v6 >= 0 )
    {
      *((_BYTE *)v4 + 56) = 1;
      *((_QWORD *)v4 + 11) = 0;
      *(GUID *)(v4 + 17) = GUID_NULL;
      v6 = 0;
    }
    v2 = 0;
    if ( v6 < 0 )
      v2 = v6;
    for ( j = v4[2]; j != 0x7FFFFFFF; j = v4[2] )
    {
      if ( j == _InterlockedCompareExchange(v4 + 2, j - 1, j) )
        break;
    }
    if ( v2 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 48LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      v2 = 0;
    }
  }
  *a1 = v4;
  return v2;
}

```

## disassembly

```asm
0x180003a70  mov     [rsp+arg_18], rbx
0x180003a75  mov     [rsp+arg_0], rcx
0x180003a7a  push    rsi
0x180003a7b  push    rdi
0x180003a7c  push    r14
0x180003a7e  sub     rsp, 20h
0x180003a82  mov     rdi, rcx
0x180003a85  test    rcx, rcx
0x180003a88  jz      loc_180003B56
0x180003a8e  xor     esi, esi
0x180003a90  mov     [rcx], rsi
0x180003a93  mov     r14d, 8007000Eh
0x180003a99  mov     [rsp+38h+arg_8], r14d
0x180003a9e  mov     [rsp+38h+arg_10], rsi
0x180003aa3  mov     ecx, 68h ; 'h'; Size
0x180003aa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003aad  mov     rbx, rax
0x180003ab0  test    rax, rax
0x180003ab3  jz      loc_180003B69
0x180003ab9  mov     [rax+8], esi
0x180003abc  xorps   xmm0, xmm0
0x180003abf  xor     eax, eax
0x180003ac1  movups  xmmword ptr [rbx+10h], xmm0
0x180003ac5  movups  xmmword ptr [rbx+20h], xmm0
0x180003ac9  mov     [rbx+30h], rax
0x180003acd  mov     [rbx+38h], al
0x180003ad0  mov     [rbx+60h], rsi
0x180003ad4  lea     rax, ??_7?$CComObject@VCConnectedUser@@@ATL@@6B@; const ATL::CComObject<CConnectedUser>::`vftable'
0x180003adb  mov     [rbx], rax
0x180003ade  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003ae5  mov     rax, [rcx]
0x180003ae8  mov     rax, [rax+8]
0x180003aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af1  mov     [rsp+38h+arg_10], rbx
0x180003af6  test    rbx, rbx
0x180003af9  jz      short loc_180003B42
0x180003afb  mov     eax, [rbx+8]
0x180003afe  cmp     eax, 7FFFFFFFh
0x180003b03  jnz     short loc_180003B84
0x180003b05  lea     rcx, [rbx+10h]; this
0x180003b09  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003b0e  test    eax, eax
0x180003b10  js      short loc_180003B27
0x180003b12  mov     byte ptr [rbx+38h], 1
0x180003b16  mov     [rbx+58h], rsi
0x180003b1a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003b21  movups  xmmword ptr [rbx+44h], xmm0
0x180003b25  mov     eax, esi
0x180003b27  mov     r14d, esi
0x180003b2a  test    eax, eax
0x180003b2c  cmovs   r14d, eax
0x180003b30  mov     eax, [rbx+8]
0x180003b33  cmp     eax, 7FFFFFFFh
0x180003b38  jnz     short loc_180003BA1
0x180003b3a  test    r14d, r14d
0x180003b3d  jnz     short loc_180003BB7
0x180003b3f  mov     r14d, esi
0x180003b42  mov     [rdi], rbx
0x180003b45  mov     eax, r14d
0x180003b48  mov     rbx, [rsp+38h+arg_18]
0x180003b4d  add     rsp, 20h
0x180003b51  pop     r14
0x180003b53  pop     rdi
0x180003b54  pop     rsi
0x180003b55  retn
0x180003b56  mov     eax, 80004003h
0x180003b5b  mov     rbx, [rsp+38h+arg_18]
0x180003b60  add     rsp, 20h
0x180003b64  pop     r14
0x180003b66  pop     rdi
0x180003b67  pop     rsi
0x180003b68  retn
0x180003b69  mov     rbx, rsi
0x180003b6c  jmp     short loc_180003AF1
0x180003b6e  xor     esi, esi
0x180003b70  mov     rdi, [rsp+38h+arg_0]
0x180003b75  mov     r14d, [rsp+38h+arg_8]
0x180003b7a  mov     rbx, [rsp+38h+arg_10]
0x180003b7f  jmp     loc_180003AF6
0x180003b84  lea     ecx, [rax+1]
0x180003b87  lock cmpxchg [rbx+8], ecx
0x180003b8c  jz      loc_180003B05
0x180003b92  mov     eax, [rbx+8]
0x180003b95  cmp     eax, 7FFFFFFFh
0x180003b9a  jnz     short loc_180003B84
0x180003b9c  jmp     loc_180003B05
0x180003ba1  lea     ecx, [rax-1]
0x180003ba4  lock cmpxchg [rbx+8], ecx
0x180003ba9  jz      short loc_180003B3A
0x180003bab  mov     eax, [rbx+8]
0x180003bae  cmp     eax, 7FFFFFFFh
0x180003bb3  jnz     short loc_180003BA1
0x180003bb5  jmp     short loc_180003B3A
0x180003bb7  mov     rax, [rbx]
0x180003bba  mov     edx, 1
0x180003bbf  mov     rcx, rbx
0x180003bc2  mov     rax, [rax+30h]
0x180003bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcb  mov     rbx, rsi
0x180003bce  jmp     loc_180003B42
```

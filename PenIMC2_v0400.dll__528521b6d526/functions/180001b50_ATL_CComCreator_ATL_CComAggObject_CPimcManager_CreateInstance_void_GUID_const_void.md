# ATL::CComCreator<ATL::CComAggObject<CPimcManager>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001b50`
- end: `0x180001cab`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPimcManager@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001970`

## callees

- `0x180001b50`
- `0x180001fd0`
- `0x18000a444`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPimcManager>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  void *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64, _QWORD *); // rdi
  int v10; // eax
  __int64 (__fastcall *v11)(_QWORD, __int64, _QWORD *); // rax
  unsigned int Interface; // eax
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  try
  {
    v8 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CPimcManager>::`vftable';
      *((_DWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_DWORD *)v8 + 14) = 0;
      *((_BYTE *)v8 + 72) = 0;
      *((_DWORD *)v8 + 19) &= ~1u;
      *((_QWORD *)v8 + 10) = 0;
      *((_BYTE *)v8 + 100) = 0;
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CPimcManager>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = CPimcManager::FinalConstruct((CPimcManager *)(v9 + 2));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7
      || ((v11 = **v9, (char *)v11 != (char *)ATL::CComAggObject<CPimcManager>::QueryInterface)
        ? (Interface = v11(v9, v4, v3))
        : (Interface = ATL::CComAggObject<CPimcManager>::QueryInterface(v9, v4, v3)),
          (v7 = Interface) != 0) )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *), __int64))(*v9)[3])(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180001b50  mov     [rsp+arg_10], r8
0x180001b55  mov     [rsp+arg_8], rdx
0x180001b5a  push    rsi
0x180001b5b  push    rdi
0x180001b5c  push    r12
0x180001b5e  push    r14
0x180001b60  push    r15
0x180001b62  sub     rsp, 40h
0x180001b66  mov     r14, r8
0x180001b69  mov     r15, rdx
0x180001b6c  mov     r12, rcx
0x180001b6f  test    r8, r8
0x180001b72  jnz     short loc_180001B7E
0x180001b74  mov     eax, 80004003h
0x180001b79  jmp     loc_180001C9E
0x180001b7e  and     qword ptr [r8], 0
0x180001b82  mov     esi, 8007000Eh
0x180001b87  mov     [rsp+68h+arg_18], esi
0x180001b8e  and     [rsp+68h+var_48], 0
0x180001b94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001b9b  mov     ecx, 68h ; 'h'; unsigned __int64
0x180001ba0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001ba5  mov     rdi, rax
0x180001ba8  mov     [rsp+68h+var_40], rax
0x180001bad  test    rax, rax
0x180001bb0  jz      short loc_180001C1E
0x180001bb2  and     dword ptr [rax+8], 0
0x180001bb6  lea     rax, ??_7?$CComAggObject@VCPimcManager@@@ATL@@6B@; const ATL::CComAggObject<CPimcManager>::`vftable'
0x180001bbd  mov     [rdi], rax
0x180001bc0  lea     rcx, [rdi+10h]
0x180001bc4  mov     [rsp+68h+var_38], rcx
0x180001bc9  and     dword ptr [rcx+8], 0
0x180001bcd  and     qword ptr [rcx+10h], 0
0x180001bd2  and     qword ptr [rcx+18h], 0
0x180001bd7  lea     rax, [rcx+20h]
0x180001bdb  mov     [rsp+68h+var_30], rax
0x180001be0  and     qword ptr [rax], 0
0x180001be4  and     dword ptr [rcx+28h], 0
0x180001be8  mov     byte ptr [rcx+38h], 0
0x180001bec  and     dword ptr [rcx+3Ch], 0FFFFFFFEh
0x180001bf0  and     qword ptr [rcx+40h], 0
0x180001bf5  mov     byte ptr [rcx+54h], 0
0x180001bf9  lea     rax, ??_7?$CComContainedObject@VCPimcManager@@@ATL@@6B@; const ATL::CComContainedObject<CPimcManager>::`vftable'
0x180001c00  mov     [rcx], rax
0x180001c03  mov     [rcx+8], r12
0x180001c07  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001c0e  mov     rax, [rcx]
0x180001c11  mov     rax, [rax+8]
0x180001c15  call    cs:__guard_dispatch_icall_fptr
0x180001c1b  nop
0x180001c1c  jmp     short loc_180001C20
0x180001c1e  xor     edi, edi
0x180001c20  mov     [rsp+68h+var_48], rdi
0x180001c25  jmp     short loc_180001C40
0x180001c27  mov     r14, [rsp+68h+arg_10]
0x180001c2f  mov     r15, [rsp+68h+arg_8]
0x180001c34  mov     esi, [rsp+68h+arg_18]
0x180001c3b  mov     rdi, [rsp+68h+var_48]
0x180001c40  test    rdi, rdi
0x180001c43  jz      short loc_180001C9C
0x180001c45  lea     rcx, [rdi+10h]; this
0x180001c49  call    ?FinalConstruct@CPimcManager@@QEAAJXZ; CPimcManager::FinalConstruct(void)
0x180001c4e  xor     esi, esi
0x180001c50  test    eax, eax
0x180001c52  cmovs   esi, eax
0x180001c55  test    esi, esi
0x180001c57  jnz     short loc_180001C87
0x180001c59  mov     rax, [rdi]
0x180001c5c  mov     rax, [rax]
0x180001c5f  lea     rcx, ?QueryInterface@?$CComAggObject@VCPimcManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CPimcManager>::QueryInterface(_GUID const &,void * *)
0x180001c66  mov     r8, r14
0x180001c69  mov     rdx, r15
0x180001c6c  cmp     rax, rcx
0x180001c6f  mov     rcx, rdi
0x180001c72  jnz     short loc_180001C7B
0x180001c74  call    ?QueryInterface@?$CComAggObject@VCPimcManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CPimcManager>::QueryInterface(_GUID const &,void * *)
0x180001c79  jmp     short loc_180001C81
0x180001c7b  call    cs:__guard_dispatch_icall_fptr
0x180001c81  mov     esi, eax
0x180001c83  test    eax, eax
0x180001c85  jz      short loc_180001C9C
0x180001c87  mov     rax, [rdi]
0x180001c8a  mov     edx, 1
0x180001c8f  mov     rcx, rdi
0x180001c92  mov     rax, [rax+18h]
0x180001c96  call    cs:__guard_dispatch_icall_fptr
0x180001c9c  mov     eax, esi
0x180001c9e  add     rsp, 40h
0x180001ca2  pop     r15
0x180001ca4  pop     r14
0x180001ca6  pop     r12
0x180001ca8  pop     rdi
0x180001ca9  pop     rsi
0x180001caa  retn
```

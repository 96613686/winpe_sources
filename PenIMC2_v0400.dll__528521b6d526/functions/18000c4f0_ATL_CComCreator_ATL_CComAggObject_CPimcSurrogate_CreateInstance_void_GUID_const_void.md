# ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000c4f0`
- end: `0x18000c5f7`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPimcSurrogate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c4e0`

## callees

- `0x18000c4f0`
- `0x18000c790`
- `0x18000d438`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPimcSurrogate>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  void *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64, _QWORD *); // rbx
  __int64 (__fastcall *v10)(_QWORD, __int64, _QWORD *); // rax
  unsigned int Interface; // eax
  __int64 (__fastcall ***v12)(_QWORD, __int64, _QWORD *); // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  try
  {
    v8 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CPimcSurrogate>::`vftable';
      *((_DWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CPimcSurrogate>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = **v9;
    if ( (char *)v10 == (char *)ATL::CComAggObject<CPimcSurrogate>::QueryInterface )
      Interface = ATL::CComAggObject<CPimcSurrogate>::QueryInterface(v9, v4, v3);
    else
      Interface = v10(v9, v4, v3);
    v7 = Interface;
    if ( Interface )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *), __int64))(*v9)[3])(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000c4f0  mov     [rsp+arg_10], r8
0x18000c4f5  mov     [rsp+arg_8], rdx
0x18000c4fa  push    rbx
0x18000c4fb  push    rsi
0x18000c4fc  push    rdi
0x18000c4fd  push    r14
0x18000c4ff  push    r15
0x18000c501  sub     rsp, 30h
0x18000c505  mov     rsi, r8
0x18000c508  mov     r14, rdx
0x18000c50b  mov     r15, rcx
0x18000c50e  test    r8, r8
0x18000c511  jnz     short loc_18000C51D
0x18000c513  mov     eax, 80004003h
0x18000c518  jmp     loc_18000C5EB
0x18000c51d  and     qword ptr [r8], 0
0x18000c521  mov     edi, 8007000Eh
0x18000c526  mov     [rsp+58h+arg_18], edi
0x18000c52a  and     [rsp+58h+var_38], 0
0x18000c530  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c537  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c53c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c541  mov     rbx, rax
0x18000c544  mov     [rsp+58h+var_30], rax
0x18000c549  test    rax, rax
0x18000c54c  jz      short loc_18000C585
0x18000c54e  and     dword ptr [rax+8], 0
0x18000c552  lea     rax, ??_7?$CComAggObject@VCPimcSurrogate@@@ATL@@6B@; const ATL::CComAggObject<CPimcSurrogate>::`vftable'
0x18000c559  mov     [rbx], rax
0x18000c55c  and     dword ptr [rbx+18h], 0
0x18000c560  lea     rax, ??_7?$CComContainedObject@VCPimcSurrogate@@@ATL@@6B@; const ATL::CComContainedObject<CPimcSurrogate>::`vftable'
0x18000c567  mov     [rbx+10h], rax
0x18000c56b  mov     [rbx+18h], r15
0x18000c56f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c576  mov     rax, [rcx]
0x18000c579  mov     rax, [rax+8]
0x18000c57d  call    cs:__guard_dispatch_icall_fptr
0x18000c583  jmp     short loc_18000C587
0x18000c585  xor     ebx, ebx
0x18000c587  mov     [rsp+58h+var_38], rbx
0x18000c58c  jmp     short loc_18000C5A1
0x18000c58e  mov     rsi, [rsp+58h+arg_10]
0x18000c593  mov     r14, [rsp+58h+arg_8]
0x18000c598  mov     edi, [rsp+58h+arg_18]
0x18000c59c  mov     rbx, [rsp+58h+var_38]
0x18000c5a1  test    rbx, rbx
0x18000c5a4  jz      short loc_18000C5E9
0x18000c5a6  mov     rax, [rbx]
0x18000c5a9  mov     rax, [rax]
0x18000c5ac  lea     rcx, ?QueryInterface@?$CComAggObject@VCPimcSurrogate@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CPimcSurrogate>::QueryInterface(_GUID const &,void * *)
0x18000c5b3  mov     r8, rsi
0x18000c5b6  mov     rdx, r14
0x18000c5b9  cmp     rax, rcx
0x18000c5bc  mov     rcx, rbx
0x18000c5bf  jnz     short loc_18000C5C8
0x18000c5c1  call    ?QueryInterface@?$CComAggObject@VCPimcSurrogate@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComAggObject<CPimcSurrogate>::QueryInterface(_GUID const &,void * *)
0x18000c5c6  jmp     short loc_18000C5CE
0x18000c5c8  call    cs:__guard_dispatch_icall_fptr
0x18000c5ce  mov     edi, eax
0x18000c5d0  test    eax, eax
0x18000c5d2  jz      short loc_18000C5E9
0x18000c5d4  mov     rax, [rbx]
0x18000c5d7  mov     edx, 1
0x18000c5dc  mov     rcx, rbx
0x18000c5df  mov     rax, [rax+18h]
0x18000c5e3  call    cs:__guard_dispatch_icall_fptr
0x18000c5e9  mov     eax, edi
0x18000c5eb  add     rsp, 30h
0x18000c5ef  pop     r15
0x18000c5f1  pop     r14
0x18000c5f3  pop     rdi
0x18000c5f4  pop     rsi
0x18000c5f5  pop     rbx
0x18000c5f6  retn
```

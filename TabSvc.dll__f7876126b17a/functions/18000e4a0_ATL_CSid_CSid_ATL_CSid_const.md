# ATL::CSid::CSid(ATL::CSid const &)

- ea: `0x18000e4a0`
- end: `0x18000e6e7`
- name: `??0CSid@ATL@@QEAA@AEBV01@@Z`
- size: `583`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dff0`

## callees

- `0x18000e4a0`
- `0x180017f50`
- `0x180019e00`
- `0x18001a5e0`
- `0x18002d55c`
- `0x180031010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e5ca`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e5ca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e5ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e5ba`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e5a8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e5a8`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this, const struct ATL::CSid *a2)
{
  char *v4; // rbp
  char *v5; // rbx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, __int64); // rax
  char *v7; // rbp
  char *v8; // rbx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, __int64); // rax
  char *v10; // rbp
  char *v11; // rbx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, __int64); // rax
  DWORD LengthSid; // eax
  _DWORD *v15; // r14
  __int64 v16; // rax
  _DWORD *v17; // r14
  __int64 v18; // rax
  _DWORD *v19; // r14
  __int64 v20; // rax
  int Error; // eax

  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_BYTE *)this + 76) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  v4 = (char *)*((_QWORD *)a2 + 11);
  v5 = v4 - 24;
  v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3)
                                                                                            + 32LL))(*((_QWORD *)v4 - 3));
  if ( *((int *)v4 - 2) >= 0 && v6 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v5 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v5 + 4);
  }
  else
  {
    v15 = v5 + 8;
    v16 = (**v6)(v6, *((unsigned int *)v5 + 2), 2);
    v5 = (char *)v16;
    if ( !v16 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v16 + 8) = *v15;
    memcpy_s((void *const)(v16 + 24), 2LL * (*v15 + 1), v4, 2LL * (*v15 + 1));
  }
  *((_QWORD *)this + 11) = v5 + 24;
  v7 = (char *)*((_QWORD *)a2 + 12);
  v8 = v7 - 24;
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3)
                                                                                            + 32LL))(*((_QWORD *)v7 - 3));
  if ( *((int *)v7 - 2) >= 0 && v9 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v8 + 4);
  }
  else
  {
    v17 = v8 + 8;
    v18 = (**v9)(v9, *((unsigned int *)v8 + 2), 2);
    v8 = (char *)v18;
    if ( !v18 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v18 + 8) = *v17;
    memcpy_s((void *const)(v18 + 24), 2LL * (*v17 + 1), v7, 2LL * (*v17 + 1));
  }
  *((_QWORD *)this + 12) = v8 + 24;
  v10 = (char *)*((_QWORD *)a2 + 13);
  v11 = v10 - 24;
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3)
                                                                                             + 32LL))(*((_QWORD *)v10 - 3));
  if ( *((int *)v10 - 2) >= 0 && v12 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v11 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v11 + 4);
  }
  else
  {
    v19 = v11 + 8;
    v20 = (**v12)(v12, *((unsigned int *)v11 + 2), 2);
    v11 = (char *)v20;
    if ( !v20 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v20 + 8) = *v19;
    memcpy_s((void *const)(v20 + 24), 2LL * (*v19 + 1), v10, 2LL * (*v19 + 1));
  }
  *((_QWORD *)this + 13) = v11 + 24;
  *((_QWORD *)this + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    if ( !IsValidSid((char *)a2 + 8) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid((char *)a2 + 8);
    if ( !CopySid(LengthSid, (char *)this + 8, (char *)a2 + 8) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000e4a0  mov     [rsp+arg_8], rbx
0x18000e4a5  mov     [rsp+arg_10], rbp
0x18000e4aa  mov     [rsp+arg_0], rcx
0x18000e4af  push    rsi
0x18000e4b0  push    rdi
0x18000e4b1  push    r14
0x18000e4b3  sub     rsp, 20h
0x18000e4b7  mov     rsi, rdx
0x18000e4ba  mov     rdi, rcx
0x18000e4bd  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000e4c4  mov     [rcx], rax
0x18000e4c7  movzx   eax, byte ptr [rdx+4Ch]
0x18000e4cb  mov     [rcx+4Ch], al
0x18000e4ce  mov     eax, [rdx+50h]
0x18000e4d1  mov     [rcx+50h], eax
0x18000e4d4  mov     rbp, [rdx+58h]
0x18000e4d8  lea     rbx, [rbp-18h]
0x18000e4dc  mov     rcx, [rbx]
0x18000e4df  mov     rax, [rcx]
0x18000e4e2  mov     rax, [rax+20h]
0x18000e4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4eb  mov     rcx, rax
0x18000e4ee  cmp     dword ptr [rbx+10h], 0
0x18000e4f2  jl      loc_18000E5EE
0x18000e4f8  cmp     rax, [rbx]
0x18000e4fb  jnz     loc_18000E5EE
0x18000e501  lock inc dword ptr [rbx+10h]
0x18000e505  lea     rax, [rbx+18h]
0x18000e509  mov     [rdi+58h], rax
0x18000e50d  mov     rbp, [rsi+60h]
0x18000e511  lea     rbx, [rbp-18h]
0x18000e515  mov     rcx, [rbx]
0x18000e518  mov     rax, [rcx]
0x18000e51b  mov     rax, [rax+20h]
0x18000e51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e524  mov     rcx, rax
0x18000e527  cmp     dword ptr [rbx+10h], 0
0x18000e52b  jl      loc_18000E639
0x18000e531  cmp     rax, [rbx]
0x18000e534  jnz     loc_18000E639
0x18000e53a  lock inc dword ptr [rbx+10h]
0x18000e53e  lea     rax, [rbx+18h]
0x18000e542  mov     [rdi+60h], rax
0x18000e546  mov     rbp, [rsi+68h]
0x18000e54a  lea     rbx, [rbp-18h]
0x18000e54e  mov     rcx, [rbx]
0x18000e551  mov     rax, [rcx]
0x18000e554  mov     rax, [rax+20h]
0x18000e558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e55d  mov     rcx, rax
0x18000e560  cmp     dword ptr [rbx+10h], 0
0x18000e564  jl      loc_18000E684
0x18000e56a  cmp     rax, [rbx]
0x18000e56d  jnz     loc_18000E684
0x18000e573  lock inc dword ptr [rbx+10h]
0x18000e577  add     rbx, 18h
0x18000e57b  mov     [rdi+68h], rbx
0x18000e57f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e586  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e58d  mov     rax, [rax+18h]
0x18000e591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e596  add     rax, 18h
0x18000e59a  mov     [rdi+70h], rax
0x18000e59e  cmp     byte ptr [rsi+4Ch], 0
0x18000e5a2  jz      short loc_18000E5D8
0x18000e5a4  lea     rcx, [rsi+8]; pSid
0x18000e5a8  call    cs:__imp_IsValidSid
0x18000e5ae  test    eax, eax
0x18000e5b0  jz      loc_18000E6CF
0x18000e5b6  lea     rcx, [rsi+8]; pSid
0x18000e5ba  call    cs:__imp_GetLengthSid
0x18000e5c0  lea     rdx, [rdi+8]; pDestinationSid
0x18000e5c4  lea     r8, [rsi+8]; pSourceSid
0x18000e5c8  mov     ecx, eax; nDestinationSidLength
0x18000e5ca  call    cs:__imp_CopySid
0x18000e5d0  test    eax, eax
0x18000e5d2  jz      loc_18000E6DA
0x18000e5d8  mov     rax, rdi
0x18000e5db  mov     rbx, [rsp+38h+arg_8]
0x18000e5e0  mov     rbp, [rsp+38h+arg_10]
0x18000e5e5  add     rsp, 20h
0x18000e5e9  pop     r14
0x18000e5eb  pop     rdi
0x18000e5ec  pop     rsi
0x18000e5ed  retn
0x18000e5ee  lea     r14, [rbx+8]
0x18000e5f2  mov     rax, [rax]
0x18000e5f5  mov     r8d, 2
0x18000e5fb  mov     edx, [r14]
0x18000e5fe  mov     rax, [rax]
0x18000e601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e606  mov     rbx, rax
0x18000e609  test    rax, rax
0x18000e60c  jnz     short loc_18000E614
0x18000e60e  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e614  mov     eax, [r14]
0x18000e617  mov     [rbx+8], eax
0x18000e61a  mov     eax, [r14]
0x18000e61d  inc     eax
0x18000e61f  movsxd  rdx, eax
0x18000e622  add     rdx, rdx; DestinationSize
0x18000e625  lea     rcx, [rbx+18h]; Destination
0x18000e629  mov     r9, rdx; SourceSize
0x18000e62c  mov     r8, rbp; Source
0x18000e62f  call    memcpy_s
0x18000e634  jmp     loc_18000E505
0x18000e639  lea     r14, [rbx+8]
0x18000e63d  mov     rax, [rax]
0x18000e640  mov     r8d, 2
0x18000e646  mov     edx, [r14]
0x18000e649  mov     rax, [rax]
0x18000e64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e651  mov     rbx, rax
0x18000e654  test    rax, rax
0x18000e657  jnz     short loc_18000E65F
0x18000e659  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e65f  mov     eax, [r14]
0x18000e662  mov     [rbx+8], eax
0x18000e665  mov     eax, [r14]
0x18000e668  inc     eax
0x18000e66a  movsxd  rdx, eax
0x18000e66d  add     rdx, rdx; DestinationSize
0x18000e670  lea     rcx, [rbx+18h]; Destination
0x18000e674  mov     r9, rdx; SourceSize
0x18000e677  mov     r8, rbp; Source
0x18000e67a  call    memcpy_s
0x18000e67f  jmp     loc_18000E53E
0x18000e684  lea     r14, [rbx+8]
0x18000e688  mov     rax, [rax]
0x18000e68b  mov     r8d, 2
0x18000e691  mov     edx, [r14]
0x18000e694  mov     rax, [rax]
0x18000e697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e69c  mov     rbx, rax
0x18000e69f  test    rax, rax
0x18000e6a2  jnz     short loc_18000E6AA
0x18000e6a4  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e6aa  mov     eax, [r14]
0x18000e6ad  mov     [rbx+8], eax
0x18000e6b0  mov     eax, [r14]
0x18000e6b3  inc     eax
0x18000e6b5  movsxd  rdx, eax
0x18000e6b8  add     rdx, rdx; DestinationSize
0x18000e6bb  lea     rcx, [rbx+18h]; Destination
0x18000e6bf  mov     r9, rdx; SourceSize
0x18000e6c2  mov     r8, rbp; Source
0x18000e6c5  call    memcpy_s
0x18000e6ca  jmp     loc_18000E577
0x18000e6cf  mov     ecx, 80070057h; int
0x18000e6d4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e6da  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000e6df  mov     ecx, eax; int
0x18000e6e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

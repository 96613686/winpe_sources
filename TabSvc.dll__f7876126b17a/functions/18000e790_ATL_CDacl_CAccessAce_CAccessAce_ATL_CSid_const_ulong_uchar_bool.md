# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x18000e790`
- end: `0x18000ea27`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `663`
- prototype: `ATL::CDacl::CAccessAce *__fastcall(ATL::CDacl::CAccessAce *this, const struct ATL::CSid *, int, char, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002bca0`
- `0x18002c264`

## callees

- `0x18000e790`
- `0x180017f50`
- `0x180019e00`
- `0x18001a5e0`
- `0x18002d55c`
- `0x180031010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e8d2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e8d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e8c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e8c2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e8b0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e8b0`

## pseudocode

```c
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::CAccessAce(
        ATL::CDacl::CAccessAce *this,
        const struct ATL::CSid *a2,
        int a3,
        char a4,
        bool a5)
{
  _QWORD *v9; // rsi
  char *v10; // r14
  char *v11; // rdi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, __int64); // rax
  char *v13; // r14
  char *v14; // rdi
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, __int64); // rax
  char *v16; // r14
  char *v17; // rdi
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, __int64); // rax
  DWORD LengthSid; // eax
  _DWORD *v21; // r13
  __int64 v22; // rax
  _DWORD *v23; // r13
  __int64 v24; // rax
  _DWORD *v25; // r13
  __int64 v26; // rax
  int Error; // eax

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v9 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &ATL::CSid::`vftable';
  *((_BYTE *)this + 84) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 20);
  v10 = (char *)*((_QWORD *)a2 + 11);
  v11 = v10 - 24;
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3)
                                                                                             + 32LL))(*((_QWORD *)v10 - 3));
  if ( *((int *)v10 - 2) >= 0 && v12 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v11 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v11 + 4);
  }
  else
  {
    v21 = v11 + 8;
    v22 = (**v12)(v12, *((unsigned int *)v11 + 2), 2);
    v11 = (char *)v22;
    if ( !v22 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v22 + 8) = *v21;
    memcpy_s((void *const)(v22 + 24), 2LL * (*v21 + 1), v10, 2LL * (*v21 + 1));
  }
  v9[11] = v11 + 24;
  v13 = (char *)*((_QWORD *)a2 + 12);
  v14 = v13 - 24;
  v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3)
                                                                                             + 32LL))(*((_QWORD *)v13 - 3));
  if ( *((int *)v13 - 2) >= 0 && v15 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v14 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v14 + 4);
  }
  else
  {
    v23 = v14 + 8;
    v24 = (**v15)(v15, *((unsigned int *)v14 + 2), 2);
    v14 = (char *)v24;
    if ( !v24 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v24 + 8) = *v23;
    memcpy_s((void *const)(v24 + 24), 2LL * (*v23 + 1), v13, 2LL * (*v23 + 1));
  }
  v9[12] = v14 + 24;
  v16 = (char *)*((_QWORD *)a2 + 13);
  v17 = v16 - 24;
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3)
                                                                                             + 32LL))(*((_QWORD *)v16 - 3));
  if ( *((int *)v16 - 2) >= 0 && v18 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v17 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v17 + 4);
  }
  else
  {
    v25 = v17 + 8;
    v26 = (**v18)(v18, *((unsigned int *)v17 + 2), 2);
    v17 = (char *)v26;
    if ( !v26 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v26 + 8) = *v25;
    memcpy_s((void *const)(v26 + 24), 2LL * (*v25 + 1), v16, 2LL * (*v25 + 1));
  }
  v9[13] = v17 + 24;
  v9[14] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *((_BYTE *)a2 + 76) )
  {
    if ( !IsValidSid((char *)a2 + 8) )
      ATL::AtlThrowImpl(-2147024809);
    LengthSid = GetLengthSid((char *)a2 + 8);
    if ( !CopySid(LengthSid, v9 + 1, (char *)a2 + 8) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::AtlThrowImpl(Error);
    }
  }
  *((_DWORD *)this + 32) = a3;
  *((_BYTE *)this + 132) = a4;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)this = &ATL::CDacl::CAccessAce::`vftable';
  *((_BYTE *)this + 144) = a5;
  return this;
}

```

## disassembly

```asm
0x18000e790  mov     [rsp+arg_0], rcx
0x18000e795  push    rbx
0x18000e796  push    rbp
0x18000e797  push    rsi
0x18000e798  push    rdi
0x18000e799  push    r12
0x18000e79b  push    r13
0x18000e79d  push    r14
0x18000e79f  push    r15
0x18000e7a1  sub     rsp, 28h
0x18000e7a5  movzx   r15d, r9b
0x18000e7a9  mov     r12d, r8d
0x18000e7ac  mov     rbp, rdx
0x18000e7af  mov     rbx, rcx
0x18000e7b2  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x18000e7b9  mov     [rcx], rax
0x18000e7bc  lea     rsi, [rcx+8]
0x18000e7c0  mov     [rsp+68h+arg_0], rsi
0x18000e7c5  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000e7cc  mov     [rsi], rax
0x18000e7cf  movzx   eax, byte ptr [rdx+4Ch]
0x18000e7d3  mov     [rsi+4Ch], al
0x18000e7d6  mov     eax, [rdx+50h]
0x18000e7d9  mov     [rsi+50h], eax
0x18000e7dc  mov     r14, [rdx+58h]
0x18000e7e0  lea     rdi, [r14-18h]
0x18000e7e4  mov     rcx, [rdi]
0x18000e7e7  mov     rax, [rcx]
0x18000e7ea  mov     rax, [rax+20h]
0x18000e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f3  mov     rcx, rax
0x18000e7f6  cmp     dword ptr [rdi+10h], 0
0x18000e7fa  jl      loc_18000E925
0x18000e800  cmp     rax, [rdi]
0x18000e803  jnz     loc_18000E925
0x18000e809  lock inc dword ptr [rdi+10h]
0x18000e80d  lea     rax, [rdi+18h]
0x18000e811  mov     [rsi+58h], rax
0x18000e815  mov     r14, [rbp+60h]
0x18000e819  lea     rdi, [r14-18h]
0x18000e81d  mov     rcx, [rdi]
0x18000e820  mov     rax, [rcx]
0x18000e823  mov     rax, [rax+20h]
0x18000e827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e82c  mov     rcx, rax
0x18000e82f  cmp     dword ptr [rdi+10h], 0
0x18000e833  jl      loc_18000E973
0x18000e839  cmp     rax, [rdi]
0x18000e83c  jnz     loc_18000E973
0x18000e842  lock inc dword ptr [rdi+10h]
0x18000e846  lea     rax, [rdi+18h]
0x18000e84a  mov     [rsi+60h], rax
0x18000e84e  mov     r14, [rbp+68h]
0x18000e852  lea     rdi, [r14-18h]
0x18000e856  mov     rcx, [rdi]
0x18000e859  mov     rax, [rcx]
0x18000e85c  mov     rax, [rax+20h]
0x18000e860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e865  mov     rcx, rax
0x18000e868  cmp     dword ptr [rdi+10h], 0
0x18000e86c  jl      loc_18000E9C1
0x18000e872  cmp     rax, [rdi]
0x18000e875  jnz     loc_18000E9C1
0x18000e87b  lock inc dword ptr [rdi+10h]
0x18000e87f  lea     rax, [rdi+18h]
0x18000e883  mov     [rsi+68h], rax
0x18000e887  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e88e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e895  mov     rax, [rax+18h]
0x18000e899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e89e  add     rax, 18h
0x18000e8a2  mov     [rsi+70h], rax
0x18000e8a6  cmp     byte ptr [rbp+4Ch], 0
0x18000e8aa  jz      short loc_18000E8E0
0x18000e8ac  lea     rcx, [rbp+8]; pSid
0x18000e8b0  call    cs:__imp_IsValidSid
0x18000e8b6  test    eax, eax
0x18000e8b8  jz      loc_18000EA0F
0x18000e8be  lea     rcx, [rbp+8]; pSid
0x18000e8c2  call    cs:__imp_GetLengthSid
0x18000e8c8  lea     rdx, [rsi+8]; pDestinationSid
0x18000e8cc  lea     r8, [rbp+8]; pSourceSid
0x18000e8d0  mov     ecx, eax; nDestinationSidLength
0x18000e8d2  call    cs:__imp_CopySid
0x18000e8d8  test    eax, eax
0x18000e8da  jz      loc_18000EA1A
0x18000e8e0  mov     [rbx+80h], r12d
0x18000e8e7  mov     [rbx+84h], r15b
0x18000e8ee  mov     qword ptr [rbx+88h], 0
0x18000e8f9  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x18000e900  mov     [rbx], rax
0x18000e903  movzx   eax, [rsp+68h+arg_20]
0x18000e90b  mov     [rbx+90h], al
0x18000e911  mov     rax, rbx
0x18000e914  add     rsp, 28h
0x18000e918  pop     r15
0x18000e91a  pop     r14
0x18000e91c  pop     r13
0x18000e91e  pop     r12
0x18000e920  pop     rdi
0x18000e921  pop     rsi
0x18000e922  pop     rbp
0x18000e923  pop     rbx
0x18000e924  retn
0x18000e925  lea     r13, [rdi+8]
0x18000e929  mov     rax, [rax]
0x18000e92c  mov     r8d, 2
0x18000e932  mov     edx, [r13+0]
0x18000e936  mov     rax, [rax]
0x18000e939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93e  mov     rdi, rax
0x18000e941  test    rax, rax
0x18000e944  jnz     short loc_18000E94C
0x18000e946  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e94c  mov     eax, [r13+0]
0x18000e950  mov     [rdi+8], eax
0x18000e953  mov     eax, [r13+0]
0x18000e957  inc     eax
0x18000e959  movsxd  rdx, eax
0x18000e95c  add     rdx, rdx; DestinationSize
0x18000e95f  lea     rcx, [rdi+18h]; Destination
0x18000e963  mov     r9, rdx; SourceSize
0x18000e966  mov     r8, r14; Source
0x18000e969  call    memcpy_s
0x18000e96e  jmp     loc_18000E80D
0x18000e973  lea     r13, [rdi+8]
0x18000e977  mov     rax, [rax]
0x18000e97a  mov     r8d, 2
0x18000e980  mov     edx, [r13+0]
0x18000e984  mov     rax, [rax]
0x18000e987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e98c  mov     rdi, rax
0x18000e98f  test    rax, rax
0x18000e992  jnz     short loc_18000E99A
0x18000e994  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e99a  mov     eax, [r13+0]
0x18000e99e  mov     [rdi+8], eax
0x18000e9a1  mov     eax, [r13+0]
0x18000e9a5  inc     eax
0x18000e9a7  movsxd  rdx, eax
0x18000e9aa  add     rdx, rdx; DestinationSize
0x18000e9ad  lea     rcx, [rdi+18h]; Destination
0x18000e9b1  mov     r9, rdx; SourceSize
0x18000e9b4  mov     r8, r14; Source
0x18000e9b7  call    memcpy_s
0x18000e9bc  jmp     loc_18000E846
0x18000e9c1  lea     r13, [rdi+8]
0x18000e9c5  mov     rax, [rax]
0x18000e9c8  mov     r8d, 2
0x18000e9ce  mov     edx, [r13+0]
0x18000e9d2  mov     rax, [rax]
0x18000e9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9da  mov     rdi, rax
0x18000e9dd  test    rax, rax
0x18000e9e0  jnz     short loc_18000E9E8
0x18000e9e2  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x18000e9e8  mov     eax, [r13+0]
0x18000e9ec  mov     [rdi+8], eax
0x18000e9ef  mov     eax, [r13+0]
0x18000e9f3  inc     eax
0x18000e9f5  movsxd  rdx, eax
0x18000e9f8  add     rdx, rdx; DestinationSize
0x18000e9fb  lea     rcx, [rdi+18h]; Destination
0x18000e9ff  mov     r9, rdx; SourceSize
0x18000ea02  mov     r8, r14; Source
0x18000ea05  call    memcpy_s
0x18000ea0a  jmp     loc_18000E87F
0x18000ea0f  mov     ecx, 80070057h; int
0x18000ea14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ea1a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ea1f  mov     ecx, eax; int
0x18000ea21  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

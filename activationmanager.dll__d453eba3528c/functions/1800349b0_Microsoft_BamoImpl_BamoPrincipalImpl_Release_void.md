# Microsoft::BamoImpl::BamoPrincipalImpl::Release(void)

- ea: `0x1800349b0`
- end: `0x180034b31`
- name: `?Release@BamoPrincipalImpl@BamoImpl@Microsoft@@UEAAKXZ`
- size: `385`
- prototype: `unsigned int __fastcall(Microsoft::BamoImpl::BamoPrincipalImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800349b0`
- `0x18004498c`
- `0x18008b9d8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800349d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800349fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800349d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800349fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::BamoPrincipalImpl::Release(Microsoft::BamoImpl::BamoPrincipalImpl *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rbp
  const char *v5; // r9
  signed __int32 v6; // edi
  bool v7; // sf
  unsigned __int32 v8; // edi
  bool v9; // bp
  __int64 v10; // r14
  const char *v11; // r9
  signed __int32 v12; // edx
  signed __int32 v13; // edx
  __int64 v15; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_QWORD *)this + 2);
  v3 = 0;
  v4 = *(_QWORD *)(v2 + 32);
  if ( *(_DWORD *)(v4 + 184) != GetCurrentThreadId() )
  {
    v3 = v2;
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 16) + 24LL))(*(_QWORD *)(v4 + 16));
    *(_DWORD *)(v4 + 184) = GetCurrentThreadId();
  }
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
  v7 = v6 - 1 < 0;
  v8 = v6 - 1;
  if ( v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x33,
      (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
      v5);
  v9 = 0;
  if ( !v8 )
  {
    (*(void (__fastcall **)(Microsoft::BamoImpl::BamoPrincipalImpl *))(*(_QWORD *)this + 24LL))(this);
    v9 = Microsoft::BamoImpl::BamoPrincipalImpl::TryDisposeAndNotifyRemoteProxies(this);
  }
  if ( v3 )
  {
    v10 = *(_QWORD *)(v3 + 32);
    if ( *(_DWORD *)(v10 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v11);
    *(_DWORD *)(v10 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 16) + 32LL))(*(_QWORD *)(v10 + 16));
  }
  if ( v3 )
  {
    v12 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 8), 0xFFFFFFFF);
    v7 = v12 - 1 < 0;
    v13 = v12 - 1;
    if ( v7 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v5);
    if ( !v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  }
  if ( v9 )
  {
    v15 = (*(__int64 (__fastcall **)(Microsoft::BamoImpl::BamoPrincipalImpl *))(*(_QWORD *)this + 56LL))(this);
    if ( v15 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 24LL))(v15, 1);
  }
  return v8;
}

```

## disassembly

```asm
0x1800349b0  mov     [rsp+arg_8], rbx
0x1800349b5  mov     [rsp+arg_10], rbp
0x1800349ba  push    rsi
0x1800349bb  push    rdi
0x1800349bc  push    r14
0x1800349be  sub     rsp, 20h
0x1800349c2  mov     rsi, rcx
0x1800349c5  mov     rdi, [rcx+10h]
0x1800349c9  xor     ebx, ebx
0x1800349cb  mov     [rsp+38h+arg_0], rbx
0x1800349d0  mov     rbp, [rdi+20h]
0x1800349d4  call    cs:__imp_GetCurrentThreadId
0x1800349da  cmp     [rbp+0B8h], eax
0x1800349e0  jz      short loc_180034A0A
0x1800349e2  mov     rbx, rdi
0x1800349e5  mov     [rsp+38h+arg_0], rbx
0x1800349ea  lock inc dword ptr [rdi+8]
0x1800349ee  mov     rcx, [rbp+10h]
0x1800349f2  mov     rax, [rcx]
0x1800349f5  mov     rax, [rax+18h]
0x1800349f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349fe  call    cs:__imp_GetCurrentThreadId
0x180034a04  mov     [rbp+0B8h], eax
0x180034a0a  or      edi, 0FFFFFFFFh
0x180034a0d  lock xadd [rsi+8], edi
0x180034a12  add     edi, 0FFFFFFFFh
0x180034a15  sets    al
0x180034a18  mov     rcx, [rsp+38h]; this
0x180034a1d  test    al, al
0x180034a1f  jnz     loc_180034ACE
0x180034a25  xor     bpl, bpl
0x180034a28  test    edi, edi
0x180034a2a  jnz     short loc_180034A46
0x180034a2c  mov     rax, [rsi]
0x180034a2f  mov     rcx, rsi
0x180034a32  mov     rax, [rax+18h]
0x180034a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a3b  mov     rcx, rsi; this
0x180034a3e  call    ?TryDisposeAndNotifyRemoteProxies@BamoPrincipalImpl@BamoImpl@Microsoft@@AEAA_NXZ; Microsoft::BamoImpl::BamoPrincipalImpl::TryDisposeAndNotifyRemoteProxies(void)
0x180034a43  mov     bpl, al
0x180034a46  test    rbx, rbx
0x180034a49  jz      short loc_180034A84
0x180034a4b  mov     r14, [rbx+20h]
0x180034a4f  call    cs:__imp_GetCurrentThreadId
0x180034a55  cmp     [r14+0B8h], eax
0x180034a5c  setnz   dl
0x180034a5f  mov     rcx, [rsp+38h]; this
0x180034a64  test    dl, dl
0x180034a66  jnz     short loc_180034AE0
0x180034a68  mov     dword ptr [r14+0B8h], 0
0x180034a73  mov     rcx, [r14+10h]
0x180034a77  mov     rax, [rcx]
0x180034a7a  mov     rax, [rax+20h]
0x180034a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a83  nop
0x180034a84  test    rbx, rbx
0x180034a87  jz      short loc_180034AB4
0x180034a89  or      edx, 0FFFFFFFFh
0x180034a8c  lock xadd [rbx+8], edx
0x180034a91  add     edx, 0FFFFFFFFh
0x180034a94  sets    al
0x180034a97  mov     rcx, [rsp+38h]; this
0x180034a9c  test    al, al
0x180034a9e  jnz     short loc_180034AF2
0x180034aa0  test    edx, edx
0x180034aa2  jnz     short loc_180034AB4
0x180034aa4  mov     rax, [rbx]
0x180034aa7  mov     rcx, rbx
0x180034aaa  mov     rax, [rax+18h]
0x180034aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ab3  nop
0x180034ab4  test    bpl, bpl
0x180034ab7  jnz     short loc_180034B04
0x180034ab9  mov     eax, edi
0x180034abb  mov     rbx, [rsp+38h+arg_8]
0x180034ac0  mov     rbp, [rsp+38h+arg_10]
0x180034ac5  add     rsp, 20h
0x180034ac9  pop     r14
0x180034acb  pop     rdi
0x180034acc  pop     rsi
0x180034acd  retn
0x180034ace  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x180034ad5  mov     edx, 33h ; '3'; void *
0x180034ada  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034ae0  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x180034ae7  mov     edx, 9A3h; void *
0x180034aec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034af2  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x180034af9  mov     edx, 33h ; '3'; void *
0x180034afe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034b04  mov     rax, [rsi]
0x180034b07  mov     rcx, rsi
0x180034b0a  mov     rax, [rax+38h]
0x180034b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b13  mov     r8, rax
0x180034b16  test    rax, rax
0x180034b19  jz      short loc_180034AB9
0x180034b1b  mov     rcx, [rax]
0x180034b1e  mov     rax, [rcx+18h]
0x180034b22  mov     edx, 1
0x180034b27  mov     rcx, r8
0x180034b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b2f  jmp     short loc_180034AB9
```

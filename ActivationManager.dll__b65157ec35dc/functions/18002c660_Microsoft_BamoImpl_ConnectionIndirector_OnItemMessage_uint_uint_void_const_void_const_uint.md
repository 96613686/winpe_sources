# Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(uint,uint,void const *,void const *,uint)

- ea: `0x18002c660`
- end: `0x18002c809`
- name: `?OnItemMessage@ConnectionIndirector@BamoImpl@Microsoft@@UEAAJIIPEBX0I@Z`
- size: `425`
- prototype: `__int64 __fastcall(Microsoft::BamoImpl::ConnectionIndirector *__hidden this, unsigned int, unsigned int, const void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18002c660`
- `0x18004498c`
- `0x180050088`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c68c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c68c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c721`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(
        Microsoft::BamoImpl::ConnectionIndirector *this,
        int a2,
        int a3,
        const void *a4,
        const void *a5,
        unsigned int a6)
{
  char *v10; // rbx
  __int64 v11; // rbp
  const char *v12; // r9
  __int64 v13; // rdi
  _DWORD *i; // rax
  unsigned int v15; // esi
  __int64 v16; // rdi
  const char *v17; // r9
  signed __int32 v18; // eax
  bool v19; // sf
  signed __int32 v20; // eax
  int v22; // eax
  int v23; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v10 = 0;
  v11 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v11 + 184) != GetCurrentThreadId() )
  {
    v10 = (char *)this - 16;
    _InterlockedIncrement((volatile signed __int32 *)this - 2);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 16) + 24LL))(*(_QWORD *)(v11 + 16));
    *(_DWORD *)(v11 + 184) = GetCurrentThreadId();
  }
  v13 = *((_QWORD *)this + 2);
  if ( *(_QWORD *)(v13 + 64) )
  {
    for ( i = *(_DWORD **)(v13 + 192); i != *(_DWORD **)(v13 + 200); ++i )
    {
      if ( *i == a3 )
        goto LABEL_18;
    }
    if ( a4 )
    {
      *(_DWORD *)(v13 + 32) = a2;
      v15 = (*(__int64 (__fastcall **)(const void *, const void *, _QWORD))(*(_QWORD *)a4 + 32LL))(a4, a5, a6);
      *(_DWORD *)(v13 + 32) = 0;
    }
    else
    {
      v22 = Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(
              *((Microsoft::BamoImpl::BaseBamoConnectionImpl **)this + 2),
              -2018375668,
              0);
      v15 = v22;
      if ( v22 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76E,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
          (const char *)(unsigned int)v22,
          v23);
    }
  }
  else
  {
LABEL_18:
    v15 = 0;
  }
  if ( v10 )
  {
    v16 = *((_QWORD *)v10 + 4);
    if ( *(_DWORD *)(v16 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v17);
    *(_DWORD *)(v16 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 16) + 32LL))(*(_QWORD *)(v16 + 16));
  }
  if ( v10 )
  {
    v18 = _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF);
    v19 = v18 - 1 < 0;
    v20 = v18 - 1;
    if ( v19 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v12);
    if ( !v20 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 24LL))(v10);
  }
  return v15;
}

```

## disassembly

```asm
0x18002c660  push    rbx
0x18002c662  push    rbp
0x18002c663  push    rsi
0x18002c664  push    rdi
0x18002c665  push    r12
0x18002c667  push    r13
0x18002c669  push    r14
0x18002c66b  push    r15
0x18002c66d  sub     rsp, 28h
0x18002c671  mov     r14, r9
0x18002c674  mov     r12d, r8d
0x18002c677  mov     r15d, edx
0x18002c67a  mov     rsi, rcx
0x18002c67d  xor     r13d, r13d
0x18002c680  mov     ebx, r13d
0x18002c683  mov     [rsp+68h+arg_0], rbx
0x18002c688  mov     rbp, [rcx+10h]
0x18002c68c  call    cs:__imp_GetCurrentThreadId
0x18002c692  cmp     [rbp+0B8h], eax
0x18002c698  jz      short loc_18002C6C3
0x18002c69a  lea     rbx, [rsi-10h]
0x18002c69e  mov     [rsp+68h+arg_0], rbx
0x18002c6a3  lock inc dword ptr [rsi-8]
0x18002c6a7  mov     rcx, [rbp+10h]
0x18002c6ab  mov     rax, [rcx]
0x18002c6ae  mov     rax, [rax+18h]
0x18002c6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6b7  call    cs:__imp_GetCurrentThreadId
0x18002c6bd  mov     [rbp+0B8h], eax
0x18002c6c3  mov     rdi, [rsi+10h]
0x18002c6c7  cmp     qword ptr [rdi+40h], 0
0x18002c6cc  jz      loc_18002C7BA
0x18002c6d2  mov     rax, [rdi+0C0h]
0x18002c6d9  cmp     rax, [rdi+0C8h]
0x18002c6e0  jnz     loc_18002C7C2
0x18002c6e6  test    r14, r14
0x18002c6e9  jz      loc_18002C7D0
0x18002c6ef  mov     [rdi+20h], r15d
0x18002c6f3  mov     rax, [r14]
0x18002c6f6  mov     r8d, [rsp+68h+arg_28]
0x18002c6fe  mov     rdx, [rsp+68h+arg_20]
0x18002c706  mov     rcx, r14
0x18002c709  mov     rax, [rax+20h]
0x18002c70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c712  mov     esi, eax
0x18002c714  mov     [rdi+20h], r13d
0x18002c718  test    rbx, rbx
0x18002c71b  jz      short loc_18002C751
0x18002c71d  mov     rdi, [rbx+20h]
0x18002c721  call    cs:__imp_GetCurrentThreadId
0x18002c727  cmp     [rdi+0B8h], eax
0x18002c72d  setnz   al
0x18002c730  mov     rcx, [rsp+68h]; this
0x18002c735  test    al, al
0x18002c737  jnz     short loc_18002C796
0x18002c739  mov     [rdi+0B8h], r13d
0x18002c740  mov     rcx, [rdi+10h]
0x18002c744  mov     rax, [rcx]
0x18002c747  mov     rax, [rax+20h]
0x18002c74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c750  nop
0x18002c751  test    rbx, rbx
0x18002c754  jz      short loc_18002C783
0x18002c756  mov     eax, 0FFFFFFFFh
0x18002c75b  lock xadd [rbx+8], eax
0x18002c760  add     eax, 0FFFFFFFFh
0x18002c763  sets    dl
0x18002c766  mov     rcx, [rsp+68h]; this
0x18002c76b  test    dl, dl
0x18002c76d  jnz     short loc_18002C7A8
0x18002c76f  test    eax, eax
0x18002c771  jnz     short loc_18002C783
0x18002c773  mov     rcx, [rbx]
0x18002c776  mov     rax, [rcx+18h]
0x18002c77a  mov     rcx, rbx
0x18002c77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c782  nop
0x18002c783  mov     eax, esi
0x18002c785  add     rsp, 28h
0x18002c789  pop     r15
0x18002c78b  pop     r14
0x18002c78d  pop     r13
0x18002c78f  pop     r12
0x18002c791  pop     rdi
0x18002c792  pop     rsi
0x18002c793  pop     rbp
0x18002c794  pop     rbx
0x18002c795  retn
0x18002c796  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18002c79d  mov     edx, 9A3h; void *
0x18002c7a2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002c7a8  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18002c7af  mov     edx, 33h ; '3'; void *
0x18002c7b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002c7ba  mov     esi, r13d
0x18002c7bd  jmp     loc_18002C718
0x18002c7c2  cmp     [rax], r12d
0x18002c7c5  jz      short loc_18002C7BA
0x18002c7c7  add     rax, 4
0x18002c7cb  jmp     loc_18002C6D9
0x18002c7d0  xor     r8d, r8d; unsigned int
0x18002c7d3  mov     edx, 87B2080Ch; int
0x18002c7d8  mov     rcx, rdi; this
0x18002c7db  call    ?TrackError@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEAAJJI@Z; Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(long,uint)
0x18002c7e0  mov     esi, eax
0x18002c7e2  test    eax, eax
0x18002c7e4  jns     loc_18002C718
0x18002c7ea  mov     rcx, [rsp+68h]; this
0x18002c7ef  mov     r9d, eax; char *
0x18002c7f2  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18002c7f9  mov     edx, 76Eh; void *
0x18002c7fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c803  jmp     loc_18002C718
```

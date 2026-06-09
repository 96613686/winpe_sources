# PWGRCore::CPWGRStreamWriter::StartDocW(IStream *,uint,_DOC_SETTINGS)

- ea: `0x18000a550`
- end: `0x18000a684`
- name: `?StartDocW@CPWGRStreamWriter@PWGRCore@@UEAAJPEAUIStream@@IU_DOC_SETTINGS@@@Z`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001760`
- `0x18000200c`
- `0x180009c90`
- `0x18000a550`
- `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PWGRCore::CPWGRStreamWriter::StartDocW(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  int v12; // [rsp+30h] [rbp-48h] BYREF
  void *v13; // [rsp+38h] [rbp-40h]
  char v14[8]; // [rsp+40h] [rbp-38h] BYREF

  if ( *(_QWORD *)(a1 + 16) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v8 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = a2;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *(_DWORD *)(a1 + 24) = a3;
  *(_OWORD *)(a1 + 28) = *(_OWORD *)a4;
  *(_QWORD *)(a1 + 44) = *(_QWORD *)(a4 + 16);
  v13 = operator new(0x70u);
  v9 = std::_Ref_count_obj2<PWGRCore::CPWGRBitmapEncoder>::_Ref_count_obj2<PWGRCore::CPWGRBitmapEncoder>(v13, a1 + 24);
  *(_QWORD *)(a1 + 56) = v9 + 16;
  v10 = *(volatile signed __int32 **)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v9;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  PWGRCore::CPWGRBitmapWrapper::_hLoggingProvider = (const struct _tlgProvider_t *const)&qword_180017000;
  v12 = 0;
  strcpy(v14, "RaS2");
  return (*(__int64 (__fastcall **)(_QWORD, char *, __int64, int *))(**(_QWORD **)(a1 + 16) + 32LL))(
           *(_QWORD *)(a1 + 16),
           v14,
           4,
           &v12);
}

```

## disassembly

```asm
0x18000a550  push    rbx
0x18000a552  push    rbp
0x18000a553  push    rsi
0x18000a554  push    rdi
0x18000a555  sub     rsp, 58h
0x18000a559  mov     rax, cs:__security_cookie
0x18000a560  xor     rax, rsp
0x18000a563  mov     [rsp+78h+var_30], rax
0x18000a568  mov     rsi, r9
0x18000a56b  mov     ebp, r8d
0x18000a56e  mov     rbx, rdx
0x18000a571  mov     rdi, rcx
0x18000a574  cmp     [rcx+10h], rdx
0x18000a578  jz      short loc_18000A5A9
0x18000a57a  test    rdx, rdx
0x18000a57d  jz      short loc_18000A58F
0x18000a57f  mov     rax, [rdx]
0x18000a582  mov     rcx, rdx
0x18000a585  mov     rax, [rax+8]
0x18000a589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58e  nop
0x18000a58f  mov     rcx, [rdi+10h]
0x18000a593  mov     [rdi+10h], rbx
0x18000a597  test    rcx, rcx
0x18000a59a  jz      short loc_18000A5A9
0x18000a59c  mov     rax, [rcx]
0x18000a59f  mov     rax, [rax+10h]
0x18000a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a8  nop
0x18000a5a9  mov     [rdi+18h], ebp
0x18000a5ac  movups  xmm0, xmmword ptr [rsi]
0x18000a5af  movups  xmmword ptr [rdi+1Ch], xmm0
0x18000a5b3  movsd   xmm1, qword ptr [rsi+10h]
0x18000a5b8  movsd   qword ptr [rdi+2Ch], xmm1
0x18000a5bd  mov     ecx, 70h ; 'p'; Size
0x18000a5c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5c7  mov     [rsp+78h+var_40], rax
0x18000a5cc  lea     rdx, [rdi+18h]
0x18000a5d0  mov     rcx, rax
0x18000a5d3  call    ??$?0AEAI@?$_Ref_count_obj2@VCPWGRBitmapEncoder@PWGRCore@@@std@@QEAA@AEAI@Z; std::_Ref_count_obj2<PWGRCore::CPWGRBitmapEncoder>::_Ref_count_obj2<PWGRCore::CPWGRBitmapEncoder>(uint &)
0x18000a5d8  nop
0x18000a5d9  lea     rcx, [rax+10h]
0x18000a5dd  mov     [rdi+38h], rcx
0x18000a5e1  mov     rbx, [rdi+40h]
0x18000a5e5  mov     [rdi+40h], rax
0x18000a5e9  test    rbx, rbx
0x18000a5ec  jz      short loc_18000A624
0x18000a5ee  or      esi, 0FFFFFFFFh
0x18000a5f1  mov     eax, esi
0x18000a5f3  lock xadd [rbx+8], eax
0x18000a5f8  add     eax, esi
0x18000a5fa  jnz     short loc_18000A624
0x18000a5fc  mov     rax, [rbx]
0x18000a5ff  mov     rcx, rbx
0x18000a602  mov     rax, [rax]
0x18000a605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60a  mov     eax, esi
0x18000a60c  lock xadd [rbx+0Ch], eax
0x18000a611  add     eax, esi
0x18000a613  jnz     short loc_18000A624
0x18000a615  mov     rax, [rbx]
0x18000a618  mov     rcx, rbx
0x18000a61b  mov     rax, [rax+8]
0x18000a61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a624  lea     rax, qword_180017000
0x18000a62b  mov     cs:?_hLoggingProvider@CPWGRBitmapWrapper@PWGRCore@@0PEBU_tlgProvider_t@@EB, rax; _tlgProvider_t const * const PWGRCore::CPWGRBitmapWrapper::_hLoggingProvider
0x18000a632  mov     [rsp+78h+var_48], 0
0x18000a63a  mov     eax, dword ptr cs:aRas2; "RaS2"
0x18000a640  mov     dword ptr [rsp+78h+var_38], eax
0x18000a644  mov     al, byte ptr cs:aRas2+4; ""
0x18000a64a  mov     [rsp+78h+var_38+4], al
0x18000a64e  mov     rcx, [rdi+10h]
0x18000a652  mov     rax, [rcx]
0x18000a655  lea     r9, [rsp+78h+var_48]
0x18000a65a  mov     r8d, 4
0x18000a660  lea     rdx, [rsp+78h+var_38]
0x18000a665  mov     rax, [rax+20h]
0x18000a669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a66e  mov     rcx, [rsp+78h+var_30]
0x18000a673  xor     rcx, rsp; StackCookie
0x18000a676  call    __security_check_cookie
0x18000a67b  add     rsp, 58h
0x18000a67f  pop     rdi
0x18000a680  pop     rsi
0x18000a681  pop     rbp
0x18000a682  pop     rbx
0x18000a683  retn
```

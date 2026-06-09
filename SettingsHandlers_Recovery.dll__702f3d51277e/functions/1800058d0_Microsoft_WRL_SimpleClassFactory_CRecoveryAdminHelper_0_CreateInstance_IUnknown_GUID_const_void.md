# Microsoft::WRL::SimpleClassFactory<CRecoveryAdminHelper,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800058d0`
- end: `0x1800059c7`
- name: `?CreateInstance@?$SimpleClassFactory@VCRecoveryAdminHelper@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002380`
- `0x1800058d0`
- `0x18000dcec`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800058f4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800058f4`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CRecoveryAdminHelper,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  CRecoveryAdminHelper *v7; // rax
  int v8; // edi
  CRecoveryAdminHelper *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return v6;
  }
  v13 = 0;
  v7 = (CRecoveryAdminHelper *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    v9 = CRecoveryAdminHelper::CRecoveryAdminHelper(v7);
    v8 = (**(__int64 (__fastcall ***)(CRecoveryAdminHelper *, GUID *, _QWORD))v9)(
           v9,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(CRecoveryAdminHelper *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v8 >= 0 )
    {
      v6 = (**v13)(v13, a3, a4);
      v12 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v12)[2])(v12);
      }
      return v6;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800058d0  push    rbx
0x1800058d2  push    rbp
0x1800058d3  push    rsi
0x1800058d4  push    rdi
0x1800058d5  sub     rsp, 28h
0x1800058d9  mov     rsi, r9
0x1800058dc  mov     rbp, r8
0x1800058df  mov     qword ptr [r9], 0
0x1800058e6  test    rdx, rdx
0x1800058e9  jz      short loc_1800058FF
0x1800058eb  xor     edx, edx
0x1800058ed  mov     ebx, 80040110h
0x1800058f2  mov     ecx, ebx
0x1800058f4  call    cs:__imp_RoOriginateError
0x1800058fa  jmp     loc_1800059BC
0x1800058ff  mov     [rsp+48h+arg_8], 0
0x180005908  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000590f  mov     ecx, 18h; unsigned __int64
0x180005914  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005919  test    rax, rax
0x18000591c  jnz     short loc_180005925
0x18000591e  mov     edi, 8007000Eh
0x180005923  jmp     short loc_180005960
0x180005925  mov     rcx, rax; this
0x180005928  call    ??0CRecoveryAdminHelper@@QEAA@XZ; CRecoveryAdminHelper::CRecoveryAdminHelper(void)
0x18000592d  mov     rbx, rax
0x180005930  mov     rcx, [rax]
0x180005933  mov     rax, [rcx]
0x180005936  lea     r8, [rsp+48h+arg_8]
0x18000593b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005942  mov     rcx, rbx
0x180005945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594a  mov     edi, eax
0x18000594c  mov     rax, [rbx]
0x18000594f  mov     rcx, rbx
0x180005952  mov     rax, [rax+10h]
0x180005956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595b  nop
0x18000595c  test    edi, edi
0x18000595e  jns     short loc_180005984
0x180005960  mov     rcx, [rsp+48h+arg_8]
0x180005965  test    rcx, rcx
0x180005968  jz      short loc_180005980
0x18000596a  mov     [rsp+48h+arg_8], 0
0x180005973  mov     rdx, [rcx]
0x180005976  mov     rax, [rdx+10h]
0x18000597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597f  nop
0x180005980  mov     eax, edi
0x180005982  jmp     short loc_1800059BE
0x180005984  mov     rcx, [rsp+48h+arg_8]
0x180005989  mov     rax, [rcx]
0x18000598c  mov     r8, rsi
0x18000598f  mov     rdx, rbp
0x180005992  mov     rax, [rax]
0x180005995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599a  mov     ebx, eax
0x18000599c  mov     rcx, [rsp+48h+arg_8]
0x1800059a1  test    rcx, rcx
0x1800059a4  jz      short loc_1800059BC
0x1800059a6  mov     [rsp+48h+arg_8], 0
0x1800059af  mov     rdx, [rcx]
0x1800059b2  mov     rax, [rdx+10h]
0x1800059b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059bb  nop
0x1800059bc  mov     eax, ebx
0x1800059be  add     rsp, 28h
0x1800059c2  pop     rdi
0x1800059c3  pop     rsi
0x1800059c4  pop     rbp
0x1800059c5  pop     rbx
0x1800059c6  retn
```

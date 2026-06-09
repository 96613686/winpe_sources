# KerberosCryptoPolicy::GetEncryptionTypes(Kerb3961::KeyUsage)

- ea: `0x18000c598`
- end: `0x18000c709`
- name: `?GetEncryptionTypes@KerberosCryptoPolicy@@QEBA?AV?$unique_ptr@V?$vector@KV?$allocator@K@utl@@@utl@@U?$default_delete@V?$vector@KV?$allocator@K@utl@@@utl@@@2@@utl@@W4KeyUsage@Kerb3961@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000a0fc`

## callees

- `0x1800019e0`
- `0x180001a00`
- `0x1800021d0`
- `0x180002238`
- `0x180002350`
- `0x18000c468`
- `0x18000c598`
- `0x18000d010`

## pseudocode

```c
void ***__fastcall KerberosCryptoPolicy::GetEncryptionTypes(_QWORD *a1, void ***a2, __int64 a3)
{
  void **v6; // rax
  void **v7; // rbx
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64 *, __int64, _QWORD *, __int128 *); // r15
  __int64 v10; // rax
  __int128 *v11; // rax
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rdx
  void *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-58h] BYREF
  void *v18; // [rsp+38h] [rbp-50h]
  int v19; // [rsp+40h] [rbp-48h]

  v6 = (void **)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *v6 = (void *)-1LL;
    v6[1] = (void *)-1LL;
    v6[2] = (void *)-1LL;
    v8 = *a1;
    v9 = *(void (__fastcall **)(__int64, __int64 *, __int64, _QWORD *, __int128 *))(*(_QWORD *)*a1 + 168LL);
    if ( __TSS0__1__GetSecondPartner_KerberosCryptoPolicy__AEBAAEBUCipherPartnerHandle_Kerb3961__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetSecondPartner_KerberosCryptoPolicy__AEBAAEBUCipherPartnerHandle_Kerb3961__XZ_4HA);
      if ( __TSS0__1__GetSecondPartner_KerberosCryptoPolicy__AEBAAEBUCipherPartnerHandle_Kerb3961__XZ_4HA == -1 )
      {
        `KerberosCryptoPolicy::GetSecondPartner'::`2'::none = 0;
        atexit(`KerberosCryptoPolicy::GetSecondPartner'::`2'::`dynamic atexit destructor for 'none'');
        Init_thread_footer(&__TSS0__1__GetSecondPartner_KerberosCryptoPolicy__AEBAAEBUCipherPartnerHandle_Kerb3961__XZ_4HA);
      }
    }
    v10 = a1[6];
    if ( v10 )
      v11 = (__int128 *)(v10 + 16);
    else
      v11 = &`KerberosCryptoPolicy::GetSecondPartner'::`2'::none;
    v9(v8, &v17, a3, a1 + 2, v11);
    if ( v19 >= 0
      && (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::assign<unsigned int const *,void>(
                            v7,
                            v18,
                            (char *)v18 + 4 * v17) )
    {
      v15 = v18;
      v14 = 4;
      *a2 = v7;
    }
    else
    {
      v12 = v18;
      *a2 = 0;
      operator delete(v12, (const struct std::nothrow_t *)4);
      v13 = *v7;
      if ( *v7 != (void *)-1LL )
      {
        v7[1] = v13;
        operator delete(v13, (const struct std::nothrow_t *)std::nothrow);
      }
      v14 = 24;
      v15 = v7;
    }
    operator delete(v15, (const struct std::nothrow_t *)v14);
  }
  else
  {
    *a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c598  push    rbx
0x18000c59a  push    rbp
0x18000c59b  push    rsi
0x18000c59c  push    rdi
0x18000c59d  push    r13
0x18000c59f  push    r14
0x18000c5a1  push    r15
0x18000c5a3  sub     rsp, 50h
0x18000c5a7  mov     rdi, rdx
0x18000c5aa  mov     rsi, rcx
0x18000c5ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c5b4  mov     ecx, 18h; unsigned __int64
0x18000c5b9  mov     rbp, r8
0x18000c5bc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c5c1  mov     rbx, rax
0x18000c5c4  test    rax, rax
0x18000c5c7  jz      loc_18000C6AF
0x18000c5cd  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000c5d1  mov     edx, 4
0x18000c5d6  mov     [rax], r13
0x18000c5d9  mov     [rax+8], r13
0x18000c5dd  mov     [rax+10h], r13
0x18000c5e1  mov     r14, [rsi]
0x18000c5e4  mov     eax, cs:_tls_index
0x18000c5ea  mov     rcx, [r14]
0x18000c5ed  mov     r15, [rcx+0A8h]
0x18000c5f4  mov     rcx, gs:58h
0x18000c5fd  mov     rax, [rcx+rax*8]
0x18000c601  mov     eax, [rdx+rax]
0x18000c604  cmp     cs:?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA, eax
0x18000c60a  jg      loc_18000C6C8
0x18000c610  mov     rax, [rsi+30h]
0x18000c614  test    rax, rax
0x18000c617  jz      short loc_18000C61F
0x18000c619  add     rax, 10h
0x18000c61d  jmp     short loc_18000C626
0x18000c61f  lea     rax, ?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x18000c626  mov     [rsp+88h+var_68], rax
0x18000c62b  lea     r9, [rsi+10h]
0x18000c62f  mov     rax, r15
0x18000c632  lea     rdx, [rsp+88h+var_58]
0x18000c637  mov     r8, rbp
0x18000c63a  mov     rcx, r14
0x18000c63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c642  cmp     [rsp+88h+var_48], 0
0x18000c647  jl      short loc_18000C663
0x18000c649  mov     rdx, [rsp+88h+var_50]
0x18000c64e  mov     rcx, rbx
0x18000c651  mov     rax, [rsp+88h+var_58]
0x18000c656  lea     r8, [rdx+rax*4]
0x18000c65a  call    ??$assign@PEBIX@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_NPEBI0@Z; utl::vector<ulong,utl::allocator<ulong>>::assign<uint const *,void>(uint const *,uint const *)
0x18000c65f  test    al, al
0x18000c661  jnz     short loc_18000C6A0
0x18000c663  mov     rcx, [rsp+88h+var_50]; void *
0x18000c668  mov     edx, 4; struct std::nothrow_t *
0x18000c66d  mov     qword ptr [rdi], 0
0x18000c674  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c679  mov     rcx, [rbx]; void *
0x18000c67c  cmp     rcx, r13
0x18000c67f  jz      short loc_18000C691
0x18000c681  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c688  mov     [rbx+8], rcx
0x18000c68c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c691  mov     edx, 18h; struct std::nothrow_t *
0x18000c696  mov     rcx, rbx; void *
0x18000c699  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c69e  jmp     short loc_18000C6B6
0x18000c6a0  mov     rcx, [rsp+88h+var_50]
0x18000c6a5  mov     edx, 4
0x18000c6aa  mov     [rdi], rbx
0x18000c6ad  jmp     short loc_18000C699
0x18000c6af  mov     qword ptr [rdi], 0
0x18000c6b6  mov     rax, rdi
0x18000c6b9  add     rsp, 50h
0x18000c6bd  pop     r15
0x18000c6bf  pop     r14
0x18000c6c1  pop     r13
0x18000c6c3  pop     rdi
0x18000c6c4  pop     rsi
0x18000c6c5  pop     rbp
0x18000c6c6  pop     rbx
0x18000c6c7  retn
0x18000c6c8  lea     rcx, ?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA
0x18000c6cf  call    _Init_thread_header
0x18000c6d4  cmp     cs:?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA, r13d
0x18000c6db  jnz     loc_18000C610
0x18000c6e1  xorps   xmm0, xmm0
0x18000c6e4  lea     rcx, ??__Fnone@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@YAXXZ; void (__cdecl *)()
0x18000c6eb  movdqu  cs:?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A, xmm0; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x18000c6f3  call    atexit
0x18000c6f8  lea     rcx, ?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA
0x18000c6ff  call    _Init_thread_footer
0x18000c704  jmp     loc_18000C610
```

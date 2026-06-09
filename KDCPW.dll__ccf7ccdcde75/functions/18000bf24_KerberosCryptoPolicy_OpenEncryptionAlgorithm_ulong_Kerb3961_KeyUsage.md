# KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x18000bf24`
- end: `0x18000c02e`
- name: `?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0fc`

## callees

- `0x1800019e0`
- `0x1800021d0`
- `0x180002238`
- `0x18000bf24`
- `0x18000c034`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::OpenEncryptionAlgorithm(_BYTE *a1, unsigned int a2, __int64 a3)
{
  bool v6; // al
  _QWORD *v7; // rdi
  __int64 v8; // r10
  __int64 *v9; // rax
  __int64 (__fastcall *v10)(_QWORD *, _BYTE *, _QWORD, __int64, _BYTE *, __int128 *); // r14
  __int64 v11; // rax
  __int128 *v12; // rax
  __int64 v13; // rdi
  _BYTE v15[56]; // [rsp+40h] [rbp-38h] BYREF

  v6 = KerberosCryptoPolicy::isolatedMode || a1[8];
  v7 = *(_QWORD **)a1;
  v8 = **(_QWORD **)a1;
  if ( v6 )
  {
    v9 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, __int64))(v8 + 120))(*(_QWORD *)a1, v15, a2, a3);
  }
  else
  {
    v10 = *(__int64 (__fastcall **)(_QWORD *, _BYTE *, _QWORD, __int64, _BYTE *, __int128 *))(v8 + 104);
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
    v11 = *((_QWORD *)a1 + 6);
    if ( v11 )
      v12 = (__int128 *)(v11 + 16);
    else
      v12 = &`KerberosCryptoPolicy::GetSecondPartner'::`2'::none;
    v9 = (__int64 *)v10(v7, v15, a2, a3, a1 + 16, v12);
  }
  v13 = *v9;
  if ( !*v9 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, a3);
  return v13;
}

```

## disassembly

```asm
0x18000bf24  push    rbx
0x18000bf26  push    rbp
0x18000bf27  push    rsi
0x18000bf28  push    rdi
0x18000bf29  push    r14
0x18000bf2b  sub     rsp, 50h
0x18000bf2f  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x18000bf36  mov     rsi, r8
0x18000bf39  mov     ebp, edx
0x18000bf3b  mov     rbx, rcx
0x18000bf3e  jnz     short loc_18000BF4A
0x18000bf40  cmp     byte ptr [rcx+8], 0
0x18000bf44  jnz     short loc_18000BF4A
0x18000bf46  xor     al, al
0x18000bf48  jmp     short loc_18000BF4C
0x18000bf4a  mov     al, 1
0x18000bf4c  mov     rdi, [rcx]
0x18000bf4f  mov     r10, [rdi]
0x18000bf52  test    al, al
0x18000bf54  jz      short loc_18000BF6F
0x18000bf56  mov     rax, [r10+78h]
0x18000bf5a  lea     rdx, [rsp+78h+var_38]
0x18000bf5f  mov     r9, rsi
0x18000bf62  mov     r8d, ebp
0x18000bf65  mov     rcx, rdi
0x18000bf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf6d  jmp     short loc_18000BFD0
0x18000bf6f  mov     ecx, cs:_tls_index
0x18000bf75  mov     rax, gs:58h
0x18000bf7e  mov     r14, [r10+68h]
0x18000bf82  mov     edx, 4
0x18000bf87  mov     rax, [rax+rcx*8]
0x18000bf8b  mov     eax, [rdx+rax]
0x18000bf8e  cmp     cs:?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA, eax
0x18000bf94  jg      short loc_18000BFF1
0x18000bf96  mov     rax, [rbx+30h]
0x18000bf9a  test    rax, rax
0x18000bf9d  jz      short loc_18000BFA5
0x18000bf9f  add     rax, 10h
0x18000bfa3  jmp     short loc_18000BFAC
0x18000bfa5  lea     rax, ?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x18000bfac  mov     [rsp+78h+var_50], rax
0x18000bfb1  lea     rcx, [rbx+10h]
0x18000bfb5  mov     [rsp+78h+var_58], rcx
0x18000bfba  lea     rdx, [rsp+78h+var_38]
0x18000bfbf  mov     rcx, rdi
0x18000bfc2  mov     r9, rsi
0x18000bfc5  mov     r8d, ebp
0x18000bfc8  mov     rax, r14
0x18000bfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd0  mov     rdi, [rax]
0x18000bfd3  test    rdi, rdi
0x18000bfd6  jnz     short loc_18000BFE3
0x18000bfd8  mov     rdx, rsi
0x18000bfdb  mov     rcx, rbx
0x18000bfde  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x18000bfe3  mov     rax, rdi
0x18000bfe6  add     rsp, 50h
0x18000bfea  pop     r14
0x18000bfec  pop     rdi
0x18000bfed  pop     rsi
0x18000bfee  pop     rbp
0x18000bfef  pop     rbx
0x18000bff0  retn
0x18000bff1  lea     rcx, ?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA
0x18000bff8  call    _Init_thread_header
0x18000bffd  cmp     cs:?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA, 0FFFFFFFFh
0x18000c004  jnz     short loc_18000BF96
0x18000c006  xorps   xmm0, xmm0
0x18000c009  lea     rcx, ??__Fnone@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@YAXXZ; void (__cdecl *)()
0x18000c010  movdqu  cs:?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A, xmm0; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x18000c018  call    atexit
0x18000c01d  lea     rcx, ?$TSS0@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4HA
0x18000c024  call    _Init_thread_footer
0x18000c029  jmp     loc_18000BF96
```

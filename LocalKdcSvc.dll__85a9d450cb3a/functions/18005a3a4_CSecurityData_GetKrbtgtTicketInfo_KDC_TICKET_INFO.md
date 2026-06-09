# CSecurityData::GetKrbtgtTicketInfo(_KDC_TICKET_INFO *)

- ea: `0x18005a3a4`
- end: `0x18005a5f4`
- name: `?GetKrbtgtTicketInfo@CSecurityData@@QEAAJPEAU_KDC_TICKET_INFO@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CSecurityData *__hidden this, struct _KDC_TICKET_INFO *)`
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016148`
- `0x18001db14`
- `0x180021eb4`
- `0x18002dd48`
- `0x1800428c4`
- `0x18004364c`
- `0x180047f90`
- `0x18004b8a0`
- `0x18004e710`
- `0x180055744`
- `0x180060c24`
- `0x18006c8c8`

## callees

- `0x180003908`
- `0x18000ab40`
- `0x18000e9a4`
- `0x180020fa8`
- `0x1800210a8`
- `0x18005a3a4`
- `0x18005c2a4`
- `0x18005fc6c`
- `0x18007c4d4`
- `0x180081bec`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18005a456`
- `ntdll!RtlAcquireResourceShared` at `0x18005a456`
- `ntdll!RtlReleaseResource` at `0x18005a5c4`
- `ntdll!RtlReleaseResource` at `0x18005a5c4`

## pseudocode

```c
__int64 __fastcall CSecurityData::GetKrbtgtTicketInfo(CSecurityData *this, struct _KDC_TICKET_INFO *a2)
{
  unsigned int v3; // ebx
  unsigned __int8 v4; // r8
  unsigned __int8 v5; // r9
  unsigned __int8 v6; // r9
  struct _UNICODE_STRING v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  int v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+5Ch] [rbp-A4h]
  struct _KERB_STORED_CREDENTIAL *v12[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+71h] [rbp-8Fh]
  __int16 v14; // [rsp+75h] [rbp-8Bh]
  char v15; // [rsp+77h] [rbp-89h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  __int16 v17; // [rsp+89h] [rbp-77h]
  char v18; // [rsp+8Bh] [rbp-75h]
  int v19; // [rsp+94h] [rbp-6Ch]
  __int64 v20; // [rsp+98h] [rbp-68h]
  __int128 v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-40h]
  _BYTE v24[60]; // [rsp+D0h] [rbp-30h] BYREF
  int v25; // [rsp+10Ch] [rbp+Ch]
  int v26; // [rsp+121h] [rbp+21h]
  __int16 v27; // [rsp+125h] [rbp+25h]
  char v28; // [rsp+127h] [rbp+27h]
  __int16 v29; // [rsp+139h] [rbp+39h]
  char v30; // [rsp+13Bh] [rbp+3Bh]
  int v31; // [rsp+144h] [rbp+44h]
  __int128 v32; // [rsp+168h] [rbp+68h] BYREF
  __int64 v33; // [rsp+178h] [rbp+78h]
  void *v34; // [rsp+180h] [rbp+80h]
  struct _UNICODE_STRING *v35; // [rsp+188h] [rbp+88h]
  char v36; // [rsp+190h] [rbp+90h]
  unsigned int v37; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 *v38; // [rsp+1D0h] [rbp+D0h] BYREF

  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(&v8, 0, 0x98u);
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v24, 0, 0x98u);
  v32 = 0;
  v33 = 0;
  _KDC_TICKET_INFO::operator=(a2, v24);
  std::vector<unsigned int>::_Tidy((__int64)&v32);
  RtlAcquireResourceShared(&Resource, 1u);
  v34 = &SecData;
  v35 = &v8;
  v36 = 1;
  KerberosCryptoPolicy::Create(&v38);
  if ( !v38 )
    goto LABEL_8;
  if ( !(_BYTE)word_1800B2F08 )
  {
    v3 = 7;
    goto LABEL_9;
  }
  _KDC_TICKET_INFO::operator=(&v8, &stru_1800B2E58);
  *(_OWORD *)v12 = 0;
  v16 = 0;
  v8.Buffer = 0;
  v9 = 0;
  v20 = 0;
  v21 = 0;
  v10 = 502;
  if ( (int)KerbDuplicateStringEx(&v8, &stru_1800B2E58, v4) < 0 )
  {
LABEL_8:
    v3 = 60;
    goto LABEL_9;
  }
  v3 = KdcDuplicateCredentials(v12, &v37, qword_1800B2E98, v5);
  if ( !v3 )
  {
    v3 = KdcDuplicateCredentials(&v12[1], &v37, qword_1800B2EA0, v6);
    if ( !v3 )
    {
      _KDC_TICKET_INFO::operator=(a2, &v8);
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      memset_0(v24, 0, 0x98u);
      v32 = 0;
      v33 = 0;
      _KDC_TICKET_INFO::operator=(&v8, v24);
      std::vector<unsigned int>::_Tidy((__int64)&v32);
    }
  }
LABEL_9:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v38);
  RtlReleaseResource(&Resource);
  FreeTicketInfo((struct _KDC_TICKET_INFO *)&v8);
  std::vector<unsigned int>::_Tidy((__int64)&v22);
  return v3;
}

```

## disassembly

```asm
0x18005a3a4  mov     [rsp-8+arg_8], rbx
0x18005a3a9  push    rbp
0x18005a3aa  push    rdi
0x18005a3ab  push    r14
0x18005a3ad  lea     rbp, [rsp-0A0h]
0x18005a3b5  sub     rsp, 1A0h
0x18005a3bc  mov     rdi, rdx
0x18005a3bf  xor     eax, eax
0x18005a3c1  mov     [rsp+1B0h+var_154], eax
0x18005a3c5  mov     [rsp+1B0h+var_13F], eax
0x18005a3c9  mov     [rsp+1B0h+var_13B], ax
0x18005a3ce  mov     [rsp+1B0h+var_139], al
0x18005a3d2  mov     [rbp+0B0h+var_127], ax
0x18005a3d6  mov     [rbp+0B0h+var_125], al
0x18005a3d9  mov     [rbp+0B0h+var_11C], eax
0x18005a3dc  mov     r14d, 98h
0x18005a3e2  mov     r8d, r14d; Size
0x18005a3e5  xor     edx, edx; Val
0x18005a3e7  lea     rcx, [rsp+1B0h+var_190]; void *
0x18005a3ec  call    memset_0
0x18005a3f1  mov     [rbp+0B0h+var_F8], 0
0x18005a3f9  xorps   xmm0, xmm0
0x18005a3fc  movdqa  [rbp+0B0h+var_F0], xmm0
0x18005a401  xor     eax, eax
0x18005a403  mov     [rbp+0B0h+var_A4], eax
0x18005a406  mov     [rbp+0B0h+var_8F], eax
0x18005a409  mov     [rbp+0B0h+var_8B], ax
0x18005a40d  mov     [rbp+0B0h+var_89], al
0x18005a410  mov     [rbp+0B0h+var_77], ax
0x18005a414  mov     [rbp+0B0h+var_75], al
0x18005a417  mov     [rbp+0B0h+var_6C], eax
0x18005a41a  mov     r8d, r14d; Size
0x18005a41d  xor     edx, edx; Val
0x18005a41f  lea     rcx, [rbp+0B0h+var_E0]; void *
0x18005a423  call    memset_0
0x18005a428  xorps   xmm0, xmm0
0x18005a42b  movdqu  [rbp+0B0h+var_48], xmm0
0x18005a430  mov     [rbp+0B0h+var_38], 0
0x18005a438  lea     rdx, [rbp+0B0h+var_E0]
0x18005a43c  mov     rcx, rdi
0x18005a43f  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@$$QEAU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO &&)
0x18005a444  lea     rcx, [rbp+0B0h+var_48]
0x18005a448  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005a44d  mov     dl, 1; Wait
0x18005a44f  lea     rcx, Resource; Resource
0x18005a456  call    cs:__imp_RtlAcquireResourceShared
0x18005a45c  lea     rax, ?SecData@@3VCSecurityData@@A; CSecurityData SecData
0x18005a463  mov     [rbp+0B0h+var_30], rax
0x18005a46a  lea     rax, [rsp+1B0h+var_190]
0x18005a46f  mov     [rbp+0B0h+var_28], rax
0x18005a476  mov     [rbp+0B0h+var_20], 1
0x18005a47d  lea     rcx, [rbp+0B0h+arg_10]
0x18005a484  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18005a489  nop
0x18005a48a  cmp     [rbp+0B0h+arg_10], 0
0x18005a492  jz      loc_18005A5AB
0x18005a498  cmp     byte ptr cs:word_1800B2F08, 0
0x18005a49f  jnz     short loc_18005A4AB
0x18005a4a1  mov     ebx, 7
0x18005a4a6  jmp     loc_18005A5B0
0x18005a4ab  lea     rdx, stru_1800B2E58
0x18005a4b2  lea     rcx, [rsp+1B0h+var_190]
0x18005a4b7  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@AEBU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO const &)
0x18005a4bc  xorps   xmm0, xmm0
0x18005a4bf  movdqa  xmmword ptr [rsp+1B0h+var_150], xmm0
0x18005a4c5  mov     [rsp+1B0h+var_138], 0
0x18005a4ce  mov     [rsp+1B0h+var_190.Buffer], 0
0x18005a4d7  mov     [rsp+1B0h+var_178], 0
0x18005a4e0  mov     [rbp+0B0h+var_118], 0
0x18005a4e8  movdqu  [rbp+0B0h+var_110], xmm0
0x18005a4ed  mov     [rsp+1B0h+var_160], 1F6h
0x18005a4f5  lea     rdx, stru_1800B2E58; struct _UNICODE_STRING *
0x18005a4fc  lea     rcx, [rsp+1B0h+var_190]; struct _UNICODE_STRING *
0x18005a501  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18005a506  test    eax, eax
0x18005a508  js      loc_18005A5AB
0x18005a50e  mov     r8, cs:qword_1800B2E98; struct _KERB_STORED_CREDENTIAL *
0x18005a515  lea     rdx, [rbp+0B0h+arg_0]; unsigned int *
0x18005a51c  lea     rcx, [rsp+1B0h+var_150]; struct _KERB_STORED_CREDENTIAL **
0x18005a521  call    ?KdcDuplicateCredentials@@YAJPEAPEAU_KERB_STORED_CREDENTIAL@@PEAKPEAU1@E@Z; KdcDuplicateCredentials(_KERB_STORED_CREDENTIAL * *,ulong *,_KERB_STORED_CREDENTIAL *,uchar)
0x18005a526  mov     ebx, eax
0x18005a528  test    eax, eax
0x18005a52a  jnz     loc_18005A5B0
0x18005a530  mov     r8, cs:qword_1800B2EA0; struct _KERB_STORED_CREDENTIAL *
0x18005a537  lea     rdx, [rbp+0B0h+arg_0]; unsigned int *
0x18005a53e  lea     rcx, [rsp+1B0h+var_150+8]; struct _KERB_STORED_CREDENTIAL **
0x18005a543  call    ?KdcDuplicateCredentials@@YAJPEAPEAU_KERB_STORED_CREDENTIAL@@PEAKPEAU1@E@Z; KdcDuplicateCredentials(_KERB_STORED_CREDENTIAL * *,ulong *,_KERB_STORED_CREDENTIAL *,uchar)
0x18005a548  mov     ebx, eax
0x18005a54a  test    eax, eax
0x18005a54c  jnz     short loc_18005A5B0
0x18005a54e  lea     rdx, [rsp+1B0h+var_190]
0x18005a553  mov     rcx, rdi
0x18005a556  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@AEBU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO const &)
0x18005a55b  xor     eax, eax
0x18005a55d  mov     [rbp+0B0h+var_A4], eax
0x18005a560  mov     [rbp+0B0h+var_8F], eax
0x18005a563  mov     [rbp+0B0h+var_8B], ax
0x18005a567  mov     [rbp+0B0h+var_89], al
0x18005a56a  mov     [rbp+0B0h+var_77], ax
0x18005a56e  mov     [rbp+0B0h+var_75], al
0x18005a571  mov     [rbp+0B0h+var_6C], eax
0x18005a574  mov     r8, r14; Size
0x18005a577  xor     edx, edx; Val
0x18005a579  lea     rcx, [rbp+0B0h+var_E0]; void *
0x18005a57d  call    memset_0
0x18005a582  xorps   xmm0, xmm0
0x18005a585  movdqu  [rbp+0B0h+var_48], xmm0
0x18005a58a  mov     [rbp+0B0h+var_38], 0
0x18005a592  lea     rdx, [rbp+0B0h+var_E0]
0x18005a596  lea     rcx, [rsp+1B0h+var_190]
0x18005a59b  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@$$QEAU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO &&)
0x18005a5a0  lea     rcx, [rbp+0B0h+var_48]
0x18005a5a4  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005a5a9  jmp     short loc_18005A5B0
0x18005a5ab  mov     ebx, 3Ch ; '<'
0x18005a5b0  lea     rcx, [rbp+0B0h+arg_10]
0x18005a5b7  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18005a5bc  nop
0x18005a5bd  lea     rcx, Resource; Resource
0x18005a5c4  call    cs:__imp_RtlReleaseResource
0x18005a5ca  lea     rcx, [rsp+1B0h+var_190]; struct _KDC_TICKET_INFO *
0x18005a5cf  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005a5d4  nop
0x18005a5d5  lea     rcx, [rbp+0B0h+var_F8]
0x18005a5d9  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005a5de  mov     eax, ebx
0x18005a5e0  mov     rbx, [rsp+1B0h+arg_8]
0x18005a5e8  add     rsp, 1A0h
0x18005a5ef  pop     r14
0x18005a5f1  pop     rdi
0x18005a5f2  pop     rbp
0x18005a5f3  retn
```

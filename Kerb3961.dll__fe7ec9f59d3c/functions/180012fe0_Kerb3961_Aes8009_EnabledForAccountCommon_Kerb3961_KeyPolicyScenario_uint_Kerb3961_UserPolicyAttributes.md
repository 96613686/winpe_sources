# Kerb3961::Aes8009::EnabledForAccountCommon(Kerb3961::KeyPolicyScenario,uint,Kerb3961::UserPolicyAttributes)

- ea: `0x180012fe0`
- end: `0x1800130a8`
- name: `?EnabledForAccountCommon@Aes8009@Kerb3961@@AEAA_NUKeyPolicyScenario@2@IW4UserPolicyAttributes@2@@Z`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010e20`
- `0x180010ec0`

## callees

- `0x180003098`
- `0x180012fe0`
- `0x18001e010`

## pseudocode

```c
char __fastcall Kerb3961::Aes8009::EnabledForAccountCommon(__int64 a1, __int64 a2, __int16 a3, __int64 a4)
{
  unsigned __int8 v4; // bl
  __int64 v5; // rsi
  char v7; // r8
  char v8; // si
  unsigned __int8 v9; // cl

  v4 = a3;
  v5 = a2;
  if ( (*(_BYTE *)(a2 + 4) & 0x28) == 8 || (a4 & 0x200000000000000LL) == 0 )
  {
    if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
    {
      if ( Kerb3961::g_domainFeatureLevel < 0xAu )
      {
        v4 = ~(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1) & a3;
      }
      else if ( (a4 & 0x83) != 0 && !a3 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
      }
    }
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1) | a3;
  }
  v7 = *(_BYTE *)(v5 + 1);
  v8 = 1;
  if ( *(_QWORD *)(a1 + 64) == 16 )
    v9 = (v4 & 0x40) != 0;
  else
    v9 = v4 >> 7;
  if ( v7 != 2 && (v9 & (unsigned __int8)-(*(_BYTE *)(a1 + 164) != 0)) == 0 )
    v8 = 0;
  LOBYTE(a2) = v8;
  Kerb3961::Logging::Cipher::UsageEnabled(*(_QWORD *)(a1 + 104), a2);
  return v8;
}

```

## disassembly

```asm
0x180012fe0  mov     [rsp+arg_0], rbx
0x180012fe5  mov     [rsp+arg_8], rsi
0x180012fea  push    rdi
0x180012feb  sub     rsp, 20h
0x180012fef  mov     al, [rdx+4]
0x180012ff2  mov     ebx, r8d
0x180012ff5  and     al, 28h
0x180012ff7  mov     rsi, rdx
0x180012ffa  mov     rdi, rcx
0x180012ffd  cmp     al, 8
0x180012fff  jz      short loc_180013018
0x180013001  bt      r9, 39h ; '9'
0x180013006  jnb     short loc_180013018
0x180013008  mov     rax, [rcx]
0x18001300b  mov     rax, [rax+30h]
0x18001300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013014  or      ebx, eax
0x180013016  jmp     short loc_180013052
0x180013018  test    byte ptr [rdx+4], 2
0x18001301c  jz      short loc_180013052
0x18001301e  cmp     cs:?g_domainFeatureLevel@Kerb3961@@3UDomainFeatureLevel@1@A, 0Ah; Kerb3961::DomainFeatureLevel Kerb3961::g_domainFeatureLevel
0x180013025  jb      short loc_180013042
0x180013027  test    r9b, 83h
0x18001302b  jz      short loc_180013052
0x18001302d  test    bx, bx
0x180013030  jnz     short loc_180013052
0x180013032  mov     rax, [rcx]
0x180013035  mov     rax, [rax+30h]
0x180013039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001303e  mov     ebx, eax
0x180013040  jmp     short loc_180013052
0x180013042  mov     rax, [rcx]
0x180013045  mov     rax, [rax+30h]
0x180013049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304e  not     eax
0x180013050  and     ebx, eax
0x180013052  cmp     qword ptr [rdi+40h], 10h
0x180013057  mov     cl, bl
0x180013059  mov     r8b, [rsi+1]
0x18001305d  mov     sil, 1
0x180013060  jnz     short loc_18001306A
0x180013062  shr     cl, 6
0x180013065  and     cl, sil
0x180013068  jmp     short loc_18001306D
0x18001306a  shr     cl, 7
0x18001306d  mov     al, [rdi+0A4h]
0x180013073  neg     al
0x180013075  sbb     dl, dl
0x180013077  and     dl, cl
0x180013079  cmp     r8b, 2
0x18001307d  jz      short loc_180013086
0x18001307f  test    dl, dl
0x180013081  jnz     short loc_180013086
0x180013083  xor     sil, sil
0x180013086  mov     rcx, [rdi+68h]
0x18001308a  mov     r9d, ebx
0x18001308d  mov     dl, sil
0x180013090  call    ?UsageEnabled@Cipher@Logging@Kerb3961@@YAXPEBG_NW4KeyPolicyOperation@3@I@Z; Kerb3961::Logging::Cipher::UsageEnabled(ushort const *,bool,Kerb3961::KeyPolicyOperation,uint)
0x180013095  mov     rbx, [rsp+28h+arg_0]
0x18001309a  mov     al, sil
0x18001309d  mov     rsi, [rsp+28h+arg_8]
0x1800130a2  add     rsp, 20h
0x1800130a6  pop     rdi
0x1800130a7  retn
```

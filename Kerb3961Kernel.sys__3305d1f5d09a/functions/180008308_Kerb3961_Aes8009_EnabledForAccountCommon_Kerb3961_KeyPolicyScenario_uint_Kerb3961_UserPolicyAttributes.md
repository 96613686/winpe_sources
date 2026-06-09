# Kerb3961::Aes8009::EnabledForAccountCommon(Kerb3961::KeyPolicyScenario,uint,Kerb3961::UserPolicyAttributes)

- ea: `0x180008308`
- end: `0x1800083db`
- name: `?EnabledForAccountCommon@Aes8009@Kerb3961@@AEAA_NUKeyPolicyScenario@2@IW4UserPolicyAttributes@2@@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e40`
- `0x180006ee0`

## callees

- `0x180008308`
- `0x1800119a4`
- `0x180012240`

## pseudocode

```c
char __fastcall Kerb3961::Aes8009::EnabledForAccountCommon(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rsi
  char v7; // si
  unsigned __int8 v8; // cl

  v5 = a3;
  v6 = a2;
  if ( (*(_BYTE *)(a2 + 4) & 0x28) == 8 || (a4 & 0x200000000000000LL) == 0 )
  {
    if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
    {
      if ( Kerb3961::g_domainFeatureLevel < 0xAu )
      {
        v5 = ~(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1) & a3;
      }
      else if ( (a4 & 0x83) != 0 && !(_WORD)a3 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
      }
    }
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1) | a3;
  }
  LOBYTE(a3) = *(_BYTE *)(v6 + 1);
  v7 = 1;
  if ( *(_QWORD *)(a1 + 64) == 16 )
    v8 = (v5 & 0x40) != 0;
  else
    v8 = (unsigned __int8)v5 >> 7;
  if ( (_BYTE)a3 != 2 && (v8 & (unsigned __int8)-(*(_BYTE *)(a1 + 164) != 0)) == 0 )
    v7 = 0;
  LOBYTE(a2) = v7;
  Kerb3961::Logging::Cipher::UsageEnabled(*(_QWORD *)(a1 + 104), a2, a3, v5);
  return v7;
}

```

## disassembly

```asm
0x180008308  mov     [rsp+arg_0], rbx
0x18000830d  mov     [rsp+arg_8], rsi
0x180008312  push    rdi
0x180008313  sub     rsp, 20h
0x180008317  mov     rdi, rcx
0x18000831a  mov     ebx, r8d
0x18000831d  mov     cl, [rdx+4]
0x180008320  mov     rsi, rdx
0x180008323  mov     al, cl
0x180008325  and     al, 28h
0x180008327  cmp     al, 8
0x180008329  jz      short loc_180008345
0x18000832b  bt      r9, 39h ; '9'
0x180008330  jnb     short loc_180008345
0x180008332  mov     rax, [rdi]
0x180008335  mov     rcx, rdi
0x180008338  mov     rax, [rax+30h]
0x18000833c  call    _guard_dispatch_icall
0x180008341  or      ebx, eax
0x180008343  jmp     short loc_180008384
0x180008345  test    cl, 2
0x180008348  jz      short loc_180008384
0x18000834a  cmp     cs:?g_domainFeatureLevel@Kerb3961@@3UDomainFeatureLevel@1@A, 0Ah
0x180008351  jb      short loc_180008371
0x180008353  test    r9b, 83h
0x180008357  jz      short loc_180008384
0x180008359  test    bx, bx
0x18000835c  jnz     short loc_180008384
0x18000835e  mov     rax, [rdi]
0x180008361  mov     rcx, rdi
0x180008364  mov     rax, [rax+30h]
0x180008368  call    _guard_dispatch_icall
0x18000836d  mov     ebx, eax
0x18000836f  jmp     short loc_180008384
0x180008371  mov     rax, [rdi]
0x180008374  mov     rcx, rdi
0x180008377  mov     rax, [rax+30h]
0x18000837b  call    _guard_dispatch_icall
0x180008380  not     eax
0x180008382  and     ebx, eax
0x180008384  cmp     qword ptr [rdi+40h], 10h
0x180008389  mov     cl, bl
0x18000838b  mov     r8b, [rsi+1]
0x18000838f  mov     sil, 1
0x180008392  jnz     short loc_18000839C
0x180008394  shr     cl, 6
0x180008397  and     cl, sil
0x18000839a  jmp     short loc_18000839F
0x18000839c  shr     cl, 7
0x18000839f  mov     al, [rdi+0A4h]
0x1800083a5  neg     al
0x1800083a7  sbb     dl, dl
0x1800083a9  and     dl, cl
0x1800083ab  cmp     r8b, 2
0x1800083af  jz      short loc_1800083B8
0x1800083b1  test    dl, dl
0x1800083b3  jnz     short loc_1800083B8
0x1800083b5  xor     sil, sil
0x1800083b8  mov     rcx, [rdi+68h]
0x1800083bc  mov     r9d, ebx
0x1800083bf  mov     dl, sil
0x1800083c2  call    ?UsageEnabled@Cipher@Logging@Kerb3961@@YAXPEBG_NW4KeyPolicyOperation@3@I@Z
0x1800083c7  mov     rbx, [rsp+28h+arg_0]
0x1800083cc  mov     al, sil
0x1800083cf  mov     rsi, [rsp+28h+arg_8]
0x1800083d4  add     rsp, 20h
0x1800083d8  pop     rdi
0x1800083d9  retn
```

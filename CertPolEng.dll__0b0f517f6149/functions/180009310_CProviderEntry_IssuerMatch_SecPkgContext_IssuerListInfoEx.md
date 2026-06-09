# CProviderEntry::IssuerMatch(_SecPkgContext_IssuerListInfoEx *)

- ea: `0x180009310`
- end: `0x180009383`
- name: `?IssuerMatch@CProviderEntry@@QEAAHPEAU_SecPkgContext_IssuerListInfoEx@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(CProviderEntry *__hidden this, struct _SecPkgContext_IssuerListInfoEx *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800043d0`

## callees

- `0x180009310`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x18000935f`
- `CRYPT32!CertCompareCertificateName` at `0x18000935f`

## pseudocode

```c
__int64 __fastcall CProviderEntry::IssuerMatch(CProviderEntry *this, struct _SecPkgContext_IssuerListInfoEx *a2)
{
  DWORD v4; // esi
  unsigned int i; // ebp
  __int64 v6; // rax

  if ( !*(_DWORD *)(*((_QWORD *)this + 265) + 8LL) || !a2->cIssuers )
    return 0;
  v4 = 0;
LABEL_4:
  if ( v4 >= a2->cIssuers )
    return 0;
  for ( i = 0; ; ++i )
  {
    v6 = *((_QWORD *)this + 265);
    if ( i >= *(_DWORD *)(v6 + 8) )
    {
      ++v4;
      goto LABEL_4;
    }
    if ( CertCompareCertificateName(0x10001u, &a2->aIssuers[v4], (PCERT_NAME_BLOB)(*(_QWORD *)v6 + 16LL * i)) )
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x180009310  push    rbx
0x180009312  push    rbp
0x180009313  push    rsi
0x180009314  push    rdi
0x180009315  sub     rsp, 28h
0x180009319  mov     rax, [rcx+848h]
0x180009320  mov     rdi, rdx
0x180009323  mov     rbx, rcx
0x180009326  cmp     dword ptr [rax+8], 0
0x18000932a  jz      short loc_180009378
0x18000932c  cmp     dword ptr [rdx+8], 0
0x180009330  jz      short loc_180009378
0x180009332  xor     esi, esi
0x180009334  cmp     esi, [rdi+8]
0x180009337  jnb     short loc_180009378
0x180009339  xor     ebp, ebp
0x18000933b  mov     rax, [rbx+848h]
0x180009342  cmp     ebp, [rax+8]
0x180009345  jnb     short loc_18000936D
0x180009347  mov     r8d, ebp
0x18000934a  mov     ecx, 10001h; dwCertEncodingType
0x18000934f  shl     r8, 4
0x180009353  add     r8, [rax]; pCertName2
0x180009356  mov     edx, esi
0x180009358  shl     rdx, 4
0x18000935c  add     rdx, [rdi]; pCertName1
0x18000935f  call    cs:__imp_CertCompareCertificateName
0x180009365  test    eax, eax
0x180009367  jnz     short loc_180009371
0x180009369  inc     ebp
0x18000936b  jmp     short loc_18000933B
0x18000936d  inc     esi
0x18000936f  jmp     short loc_180009334
0x180009371  mov     eax, 1
0x180009376  jmp     short loc_18000937A
0x180009378  xor     eax, eax
0x18000937a  add     rsp, 28h
0x18000937e  pop     rdi
0x18000937f  pop     rsi
0x180009380  pop     rbp
0x180009381  pop     rbx
0x180009382  retn
```

# ABO_WRAPPER::CheckReadAccessByAppPoolSidOnApplicationNode(ABO_NODE *,void *,int *,ACCESS_GRANTED *)

- ea: `0x18000b908`
- end: `0x18000b9a6`
- name: `?CheckReadAccessByAppPoolSidOnApplicationNode@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAXPEAHPEAW4ACCESS_GRANTED@@@Z`
- size: `158`
- prototype: `int(ABO_WRAPPER *__hidden this, struct ABO_NODE *, void *, int *, enum ACCESS_GRANTED *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000baec`

## callees

- `0x18000a6a4`
- `0x18000b908`
- `0x18001aee0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b984`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b984`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckReadAccessByAppPoolSidOnApplicationNode(
        ABO_WRAPPER *this,
        struct ABO_NODE *a2,
        void *a3,
        int *a4,
        enum ACCESS_GRANTED *a5)
{
  enum ACCESS_GRANTED *v7; // rdi
  APPLICATION_CUSTOM_PROVIDER *Provider; // rax
  int v9; // ebx
  PSID pSid2; // [rsp+50h] [rbp+8h] BYREF

  pSid2 = 0;
  if ( a2 && a3 && (v7 = a5) != 0 )
  {
    *a4 = 0;
    *(_DWORD *)v7 = 3;
    Provider = ABO_NODE::QueryProvider(a2, ProviderType_NonClientArea);
    if ( Provider )
    {
      v9 = APPLICATION_CUSTOM_PROVIDER::QueryAssociatedAppPoolSid(Provider, &pSid2);
      if ( v9 >= 0 && pSid2 && EqualSid(a3, pSid2) )
        *(_DWORD *)v7 = 1;
    }
    else
    {
      v9 = 0;
      *a4 = 1;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b908  mov     [rsp+pSid2], rcx
0x18000b90d  push    rbx
0x18000b90e  push    rbp
0x18000b90f  push    rsi
0x18000b910  push    rdi
0x18000b911  sub     rsp, 28h
0x18000b915  mov     [rsp+48h+pSid2], 0
0x18000b91e  mov     rsi, r9
0x18000b921  mov     rbp, r8
0x18000b924  mov     rax, rdx
0x18000b927  test    rdx, rdx
0x18000b92a  jz      short loc_18000B996
0x18000b92c  test    r8, r8
0x18000b92f  jz      short loc_18000B996
0x18000b931  mov     rdi, [rsp+48h+arg_20]
0x18000b936  test    rdi, rdi
0x18000b939  jz      short loc_18000B996
0x18000b93b  mov     edx, 2; enum ProviderType
0x18000b940  mov     dword ptr [r9], 0
0x18000b947  mov     rcx, rax; this
0x18000b94a  mov     dword ptr [rdi], 3
0x18000b950  call    ?QueryProvider@ABO_NODE@@QEAAPEAVCUSTOM_PROPERTY_PROVIDER@@W4ProviderType@@@Z; ABO_NODE::QueryProvider(ProviderType)
0x18000b955  test    rax, rax
0x18000b958  jnz     short loc_18000B964
0x18000b95a  xor     ebx, ebx
0x18000b95c  mov     dword ptr [rsi], 1
0x18000b962  jmp     short loc_18000B99B
0x18000b964  lea     rdx, [rsp+48h+pSid2]; void **
0x18000b969  mov     rcx, rax; this
0x18000b96c  call    ?QueryAssociatedAppPoolSid@APPLICATION_CUSTOM_PROVIDER@@QEAAJPEAPEAX@Z; APPLICATION_CUSTOM_PROVIDER::QueryAssociatedAppPoolSid(void * *)
0x18000b971  mov     ebx, eax
0x18000b973  test    eax, eax
0x18000b975  js      short loc_18000B99B
0x18000b977  mov     rdx, [rsp+48h+pSid2]; pSid2
0x18000b97c  test    rdx, rdx
0x18000b97f  jz      short loc_18000B99B
0x18000b981  mov     rcx, rbp; pSid1
0x18000b984  call    cs:__imp_EqualSid
0x18000b98a  test    eax, eax
0x18000b98c  jz      short loc_18000B99B
0x18000b98e  mov     dword ptr [rdi], 1
0x18000b994  jmp     short loc_18000B99B
0x18000b996  mov     ebx, 80070057h
0x18000b99b  mov     eax, ebx
0x18000b99d  add     rsp, 28h
0x18000b9a1  pop     rdi
0x18000b9a2  pop     rsi
0x18000b9a3  pop     rbp
0x18000b9a4  pop     rbx
0x18000b9a5  retn
```

# ABO_WRAPPER::CheckReadAccessByAppPoolSidOnApppoolNode(ABO_NODE *,void *,int *,ACCESS_GRANTED *)

- ea: `0x18000b9ac`
- end: `0x18000ba4f`
- name: `?CheckReadAccessByAppPoolSidOnApppoolNode@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAXPEAHPEAW4ACCESS_GRANTED@@@Z`
- size: `163`
- prototype: `int(ABO_WRAPPER *__hidden this, struct ABO_NODE *, void *, int *, enum ACCESS_GRANTED *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000baec`

## callees

- `0x18000a6a4`
- `0x18000b9ac`
- `0x18001992c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ba25`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ba25`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckReadAccessByAppPoolSidOnApppoolNode(
        ABO_WRAPPER *this,
        struct ABO_NODE *a2,
        void *a3,
        int *a4,
        enum ACCESS_GRANTED *a5)
{
  enum ACCESS_GRANTED *v7; // rbx
  APPPOOL_CUSTOM_PROVIDER *Provider; // rax
  unsigned int v9; // edi
  PSID pSid2; // [rsp+50h] [rbp+8h] BYREF

  pSid2 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v7 = a5;
  if ( !a5 )
    return (unsigned int)-2147024809;
  *a4 = 0;
  *(_DWORD *)v7 = 3;
  Provider = ABO_NODE::QueryProvider(a2, ProviderType_BaseHwnd);
  if ( !Provider )
  {
    v9 = 0;
LABEL_6:
    *(_DWORD *)v7 = 3;
    return v9;
  }
  v9 = APPPOOL_CUSTOM_PROVIDER::QueryAssociatedAppPoolSid(Provider, &pSid2);
  if ( (v9 & 0x80000000) != 0 )
    return v9;
  if ( !pSid2 )
    goto LABEL_6;
  if ( EqualSid(a3, pSid2) )
    *(_DWORD *)v7 = 2;
  else
    *a4 = 1;
  return v9;
}

```

## disassembly

```asm
0x18000b9ac  mov     [rsp+pSid2], rcx
0x18000b9b1  push    rbx
0x18000b9b2  push    rbp
0x18000b9b3  push    rsi
0x18000b9b4  push    rdi
0x18000b9b5  sub     rsp, 28h
0x18000b9b9  mov     [rsp+48h+pSid2], 0
0x18000b9c2  mov     rsi, r9
0x18000b9c5  mov     rbp, r8
0x18000b9c8  mov     rax, rdx
0x18000b9cb  test    rdx, rdx
0x18000b9ce  jz      short loc_18000BA3F
0x18000b9d0  test    r8, r8
0x18000b9d3  jz      short loc_18000BA3F
0x18000b9d5  mov     rbx, [rsp+48h+arg_20]
0x18000b9da  test    rbx, rbx
0x18000b9dd  jz      short loc_18000BA3F
0x18000b9df  xor     edx, edx; enum ProviderType
0x18000b9e1  mov     dword ptr [r9], 0
0x18000b9e8  mov     rcx, rax; this
0x18000b9eb  mov     dword ptr [rbx], 3
0x18000b9f1  call    ?QueryProvider@ABO_NODE@@QEAAPEAVCUSTOM_PROPERTY_PROVIDER@@W4ProviderType@@@Z; ABO_NODE::QueryProvider(ProviderType)
0x18000b9f6  test    rax, rax
0x18000b9f9  jnz     short loc_18000BA05
0x18000b9fb  xor     edi, edi
0x18000b9fd  mov     dword ptr [rbx], 3
0x18000ba03  jmp     short loc_18000BA44
0x18000ba05  lea     rdx, [rsp+48h+pSid2]; void **
0x18000ba0a  mov     rcx, rax; this
0x18000ba0d  call    ?QueryAssociatedAppPoolSid@APPPOOL_CUSTOM_PROVIDER@@QEAAJPEAPEAX@Z; APPPOOL_CUSTOM_PROVIDER::QueryAssociatedAppPoolSid(void * *)
0x18000ba12  mov     edi, eax
0x18000ba14  test    eax, eax
0x18000ba16  js      short loc_18000BA44
0x18000ba18  mov     rdx, [rsp+48h+pSid2]; pSid2
0x18000ba1d  test    rdx, rdx
0x18000ba20  jz      short loc_18000B9FD
0x18000ba22  mov     rcx, rbp; pSid1
0x18000ba25  call    cs:__imp_EqualSid
0x18000ba2b  test    eax, eax
0x18000ba2d  jz      short loc_18000BA37
0x18000ba2f  mov     dword ptr [rbx], 2
0x18000ba35  jmp     short loc_18000BA44
0x18000ba37  mov     dword ptr [rsi], 1
0x18000ba3d  jmp     short loc_18000BA44
0x18000ba3f  mov     edi, 80070057h
0x18000ba44  mov     eax, edi
0x18000ba46  add     rsp, 28h
0x18000ba4a  pop     rdi
0x18000ba4b  pop     rsi
0x18000ba4c  pop     rbp
0x18000ba4d  pop     rbx
0x18000ba4e  retn
```

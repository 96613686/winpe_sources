# CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)

- ea: `0x180030754`
- end: `0x180030868`
- name: `?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(struct CMapiStore *, int *, enum POLICY_RESULT_ID *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015884`
- `0x180020e44`
- `0x1800236d4`
- `0x180035e68`
- `0x18003664c`

## callees

- `0x180030580`
- `0x180030754`
- `0x1800343f8`

## string_xrefs

- `0x180030828`: `PreventIndexingUncachedExchangeFolders`

## pseudocode

```c
__int64 __fastcall CMapiSupport::CheckPolicyOnStore(struct CMapiStore *a1, int *a2, enum POLICY_RESULT_ID *a3)
{
  int v6; // ebp
  int v7; // esi
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  v7 = 0;
  *a2 = 1;
  if ( (unsigned int)CMapiStore::IsProviderExcluded(a1) )
    goto LABEL_17;
  if ( !*((_DWORD *)a1 + 21) )
  {
    if ( !*((_DWORD *)a1 + 20) )
      goto LABEL_18;
    if ( *((_DWORD *)a1 + 22) )
    {
      v9 = 0;
      v6 = CMapiSupport::CheckPolicy(L"EnableIndexingDelegateMailboxes", &v9, 0, 0);
      if ( v6 < 0 )
        return (unsigned int)v6;
      if ( v9 )
        goto LABEL_18;
      v7 = 4;
    }
    else
    {
      if ( *((_DWORD *)a1 + 24) )
        goto LABEL_18;
      v9 = 1;
      v6 = CMapiSupport::CheckPolicy(L"PreventIndexingUncachedExchangeFolders", &v9, 0, 0);
      if ( v6 < 0 )
        return (unsigned int)v6;
      if ( !v9 )
        goto LABEL_18;
      v7 = 1;
    }
    goto LABEL_17;
  }
  if ( !*((_DWORD *)a1 + 24) )
  {
    v7 = 2;
    goto LABEL_17;
  }
  v9 = 0;
  v6 = CMapiSupport::CheckPolicy(L"PreventIndexingPublicFolders", &v9, 1, 1);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( v9 )
  {
    v7 = 3;
LABEL_17:
    *a2 = 0;
  }
LABEL_18:
  if ( a3 )
    *(_DWORD *)a3 = v7;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030754  mov     [rsp+arg_0], rbx
0x180030759  mov     [rsp+arg_10], rbp
0x18003075e  push    rsi
0x18003075f  push    rdi
0x180030760  push    r12
0x180030762  push    r14
0x180030764  push    r15
0x180030766  sub     rsp, 20h
0x18003076a  xor     r15d, r15d
0x18003076d  mov     r14, r8
0x180030770  mov     rdi, rdx
0x180030773  mov     rbx, rcx
0x180030776  mov     ebp, r15d
0x180030779  mov     esi, r15d
0x18003077c  lea     r12d, [r15+1]
0x180030780  mov     [rdx], r12d
0x180030783  call    ?IsProviderExcluded@CMapiStore@@QEAAHXZ; CMapiStore::IsProviderExcluded(void)
0x180030788  test    eax, eax
0x18003078a  jnz     loc_180030844
0x180030790  cmp     [rbx+54h], r15d
0x180030794  jz      short loc_1800307D6
0x180030796  cmp     [rbx+60h], r15d
0x18003079a  jz      short loc_1800307CF
0x18003079c  mov     r9d, r12d; int
0x18003079f  mov     [rsp+48h+arg_8], r15d
0x1800307a4  mov     r8d, r12d; int
0x1800307a7  lea     rdx, [rsp+48h+arg_8]; int *
0x1800307ac  lea     rcx, aPreventindexin_1; "PreventIndexingPublicFolders"
0x1800307b3  call    ?CheckPolicy@CMapiSupport@@SAJPEB_WPEAHHH@Z; CMapiSupport::CheckPolicy(wchar_t const *,int *,int,int)
0x1800307b8  mov     ebp, eax
0x1800307ba  test    eax, eax
0x1800307bc  js      loc_18003084F
0x1800307c2  cmp     [rsp+48h+arg_8], r15d
0x1800307c7  jz      short loc_180030847
0x1800307c9  lea     esi, [r15+3]
0x1800307cd  jmp     short loc_180030844
0x1800307cf  mov     esi, 2
0x1800307d4  jmp     short loc_180030844
0x1800307d6  cmp     [rbx+50h], r15d
0x1800307da  jz      short loc_180030847
0x1800307dc  cmp     [rbx+58h], r15d
0x1800307e0  jz      short loc_180030812
0x1800307e2  xor     r9d, r9d; int
0x1800307e5  mov     [rsp+48h+arg_8], r15d
0x1800307ea  xor     r8d, r8d; int
0x1800307ed  lea     rdx, [rsp+48h+arg_8]; int *
0x1800307f2  lea     rcx, aEnableindexing; "EnableIndexingDelegateMailboxes"
0x1800307f9  call    ?CheckPolicy@CMapiSupport@@SAJPEB_WPEAHHH@Z; CMapiSupport::CheckPolicy(wchar_t const *,int *,int,int)
0x1800307fe  mov     ebp, eax
0x180030800  test    eax, eax
0x180030802  js      short loc_18003084F
0x180030804  cmp     [rsp+48h+arg_8], r15d
0x180030809  jnz     short loc_180030847
0x18003080b  mov     esi, 4
0x180030810  jmp     short loc_180030844
0x180030812  cmp     [rbx+60h], r15d
0x180030816  jnz     short loc_180030847
0x180030818  xor     r9d, r9d; int
0x18003081b  mov     [rsp+48h+arg_8], r12d
0x180030820  xor     r8d, r8d; int
0x180030823  lea     rdx, [rsp+48h+arg_8]; int *
0x180030828  lea     rcx, aPreventindexin; "PreventIndexingUncachedExchangeFolders"
0x18003082f  call    ?CheckPolicy@CMapiSupport@@SAJPEB_WPEAHHH@Z; CMapiSupport::CheckPolicy(wchar_t const *,int *,int,int)
0x180030834  mov     ebp, eax
0x180030836  test    eax, eax
0x180030838  js      short loc_18003084F
0x18003083a  cmp     [rsp+48h+arg_8], r15d
0x18003083f  jz      short loc_180030847
0x180030841  mov     esi, r12d
0x180030844  mov     [rdi], r15d
0x180030847  test    r14, r14
0x18003084a  jz      short loc_18003084F
0x18003084c  mov     [r14], esi
0x18003084f  mov     rbx, [rsp+48h+arg_0]
0x180030854  mov     eax, ebp
0x180030856  mov     rbp, [rsp+48h+arg_10]
0x18003085b  add     rsp, 20h
0x18003085f  pop     r15
0x180030861  pop     r14
0x180030863  pop     r12
0x180030865  pop     rdi
0x180030866  pop     rsi
0x180030867  retn
```

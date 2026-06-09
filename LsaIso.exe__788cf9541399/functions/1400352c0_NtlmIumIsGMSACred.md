# NtlmIumIsGMSACred

- ea: `0x1400352c0`
- end: `0x1400353d4`
- name: `NtlmIumIsGMSACred`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400352c0`
- `0x140036038`
- `0x140036080`
- `0x140036330`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400352e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400352e3`
- `NtlmShared!MsvpGMSACred` at `0x140035333`
- `NtlmShared!MsvpGMSACred` at `0x140035333`
- `NtlmShared!MsvpCompareCredentials` at `0x140035354`
- `NtlmShared!MsvpCompareCredentials` at `0x140035354`

## pseudocode

```c
__int64 __fastcall NtlmIumIsGMSACred(__int64 a1, _BYTE *a2, _BYTE *a3)
{
  _BYTE *v4; // rbx
  int v6; // edi
  const char *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD v10[6]; // [rsp+30h] [rbp-18h] BYREF
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = a2;
  if ( qword_140052C50 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  v11 = 0;
  v12 = 0;
  v10[0] = 0;
  if ( a2 && a3 )
  {
    v6 = 0;
    if ( !a2[8] || (v6 = IumpUnprotectCredential((struct _MSV1_0_SECRETS_WRAPPER *)a2), v6 >= 0) )
    {
      v8 = MsvpGMSACred();
      MsvpCompareCredentials(v4, v8 + 32, &v11, &v12, v10);
    }
    v9 = 352;
    do
    {
      *v4++ = 0;
      --v9;
    }
    while ( v9 );
    if ( v6 >= 0 && (v11 || v12 || v10[0]) )
    {
      *a3 = 1;
    }
    else
    {
      *a3 = 0;
      if ( v6 < 0 )
      {
        NtlmTraceErrorWithStatusViaWpp("NtlmIumIsGMSACred", 0x207u, "NtlmFailure", v6);
        return (unsigned int)v6;
      }
    }
    NtlmTraceInfoViaWpp("NtlmIumIsGMSACred", 0x207u, v7);
    return (unsigned int)v6;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400352c0  mov     [rsp+arg_8], rbx
0x1400352c5  mov     [rsp+arg_10], rsi
0x1400352ca  push    rdi
0x1400352cb  sub     rsp, 40h
0x1400352cf  cmp     cs:qword_140052C50, rcx
0x1400352d6  mov     rsi, r8
0x1400352d9  mov     rbx, rdx
0x1400352dc  jz      short loc_1400352F3
0x1400352de  mov     ecx, 5; dwMilliseconds
0x1400352e3  call    cs:__imp_Sleep
0x1400352e9  mov     eax, 0C0000022h
0x1400352ee  jmp     loc_1400353C4
0x1400352f3  mov     [rsp+48h+arg_0], 0
0x1400352fb  mov     [rsp+48h+arg_18], 0
0x140035303  mov     [rsp+48h+var_18], 0
0x14003530b  test    rbx, rbx
0x14003530e  jz      loc_1400353BF
0x140035314  test    rsi, rsi
0x140035317  jz      loc_1400353BF
0x14003531d  xor     edi, edi
0x14003531f  cmp     [rdx+8], dil
0x140035323  jz      short loc_140035333
0x140035325  mov     rcx, rbx; struct _MSV1_0_SECRETS_WRAPPER *
0x140035328  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x14003532d  mov     edi, eax
0x14003532f  test    eax, eax
0x140035331  js      short loc_14003535A
0x140035333  call    cs:__imp_MsvpGMSACred
0x140035339  lea     rcx, [rsp+48h+var_18]
0x14003533e  mov     [rsp+48h+var_28], rcx
0x140035343  lea     r9, [rsp+48h+arg_18]
0x140035348  lea     r8, [rsp+48h+arg_0]
0x14003534d  mov     rcx, rbx
0x140035350  lea     rdx, [rax+20h]
0x140035354  call    cs:__imp_MsvpCompareCredentials
0x14003535a  mov     eax, 160h
0x14003535f  mov     byte ptr [rbx], 0
0x140035362  inc     rbx
0x140035365  sub     rax, 1
0x140035369  jnz     short loc_14003535F
0x14003536b  test    edi, edi
0x14003536d  js      short loc_140035386
0x14003536f  cmp     [rsp+48h+arg_0], eax
0x140035373  jnz     short loc_140035381
0x140035375  cmp     [rsp+48h+arg_18], eax
0x140035379  jnz     short loc_140035381
0x14003537b  cmp     [rsp+48h+var_18], eax
0x14003537f  jz      short loc_140035386
0x140035381  mov     byte ptr [rsi], 1
0x140035384  jmp     short loc_14003538D
0x140035386  mov     byte ptr [rsi], 0
0x140035389  test    edi, edi
0x14003538b  js      short loc_1400353A0
0x14003538d  mov     edx, 207h; unsigned int
0x140035392  lea     rcx, aNtlmiumisgmsac; "NtlmIumIsGMSACred"
0x140035399  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x14003539e  jmp     short loc_1400353BB
0x1400353a0  mov     r9d, edi; int
0x1400353a3  lea     r8, aNtlmfailure; "NtlmFailure"
0x1400353aa  mov     edx, 207h; unsigned int
0x1400353af  lea     rcx, aNtlmiumisgmsac; "NtlmIumIsGMSACred"
0x1400353b6  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x1400353bb  mov     eax, edi
0x1400353bd  jmp     short loc_1400353C4
0x1400353bf  mov     eax, 0C000000Dh
0x1400353c4  mov     rbx, [rsp+48h+arg_8]
0x1400353c9  mov     rsi, [rsp+48h+arg_10]
0x1400353ce  add     rsp, 40h
0x1400353d2  pop     rdi
0x1400353d3  retn
```

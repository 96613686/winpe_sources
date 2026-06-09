# MSCryptDHSecretAgreement

- ea: `0x180058400`
- end: `0x1800585b3`
- name: `MSCryptDHSecretAgreement`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180020408`
- `0x1800213d0`
- `0x1800579f4`
- `0x180058204`
- `0x180058400`
- `0x180063180`
- `0x18007f790`

## string_xrefs

- `0x180058554`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptDHSecretAgreement(__int64 a1, __int64 a2, _QWORD *a3, int a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  _BYTE *v19; // rax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Src[512]; // [rsp+50h] [rbp-B0h] BYREF

  v21 = 0;
  v22 = 0;
  memset_0(Src, 0, sizeof(Src));
  v23 = 0;
  if ( !a1 || !a2 || !a3 || a4 )
  {
    v10 = 1096;
    goto LABEL_19;
  }
  v8 = ValidateDHKey(a1, 1, &v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1103;
LABEL_7:
    v11 = (unsigned int)v8;
LABEL_20:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v10);
    goto LABEL_21;
  }
  v8 = ValidateDHKey(a2, 0, &v22);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1110;
    goto LABEL_7;
  }
  v14 = v21;
  if ( *(_DWORD *)(v22 + 8) != *(_DWORD *)(v21 + 8) || *(_DWORD *)(v22 + 12) != *(_DWORD *)(v21 + 12) )
  {
    v10 = 1122;
    goto LABEL_19;
  }
  v15 = *(_QWORD *)(v22 + 32);
  if ( !v15 )
  {
    v10 = 1129;
LABEL_19:
    v9 = -1073741811;
    v11 = 3221225485LL;
    goto LABEL_20;
  }
  SymCryptDhSecretAgreement(*(_QWORD *)(v21 + 32), v15, v12, v13, (__int64)Src, *(unsigned int *)(v21 + 12));
  v8 = MSCryptCreateSecret(Src, *(unsigned int *)(v14 + 12), &v23, v16, *(_DWORD *)(v14 + 8));
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 1152;
    goto LABEL_7;
  }
  *a3 = v23;
LABEL_21:
  v18 = 512;
  v19 = Src;
  do
  {
    *v19++ = 0;
    --v18;
  }
  while ( v18 );
  MSCryptAuditCheckSecureZero((__int64)Src, 0x200u, v17, (__int64)L"DH");
  return v9;
}

```

## disassembly

```asm
0x180058400  push    rbp
0x180058402  push    rbx
0x180058403  push    rsi
0x180058404  push    rdi
0x180058405  push    r14
0x180058407  lea     rbp, [rsp-160h]
0x18005840f  sub     rsp, 260h
0x180058416  mov     rax, cs:__security_cookie
0x18005841d  xor     rax, rsp
0x180058420  mov     [rbp+180h+var_30], rax
0x180058427  mov     rsi, r8
0x18005842a  mov     [rsp+280h+var_250], 0
0x180058433  mov     rdi, rdx
0x180058436  mov     [rsp+280h+var_248], 0
0x18005843f  mov     rbx, rcx
0x180058442  xor     edx, edx; Val
0x180058444  mov     r8d, 200h; Size
0x18005844a  lea     rcx, [rsp+280h+Src]; void *
0x18005844f  mov     r14d, r9d
0x180058452  call    memset_0
0x180058457  mov     [rsp+280h+var_240], 0
0x180058460  test    rbx, rbx
0x180058463  jz      loc_180058544
0x180058469  test    rdi, rdi
0x18005846c  jz      loc_180058544
0x180058472  test    rsi, rsi
0x180058475  jz      loc_180058544
0x18005847b  test    r14d, r14d
0x18005847e  jnz     loc_180058544
0x180058484  lea     r8, [rsp+280h+var_250]
0x180058489  mov     rcx, rbx
0x18005848c  lea     edx, [r14+1]
0x180058490  call    ValidateDHKey
0x180058495  mov     ebx, eax
0x180058497  test    eax, eax
0x180058499  jns     short loc_1800584A8
0x18005849b  mov     r9d, 44Fh
0x1800584a1  mov     ecx, eax
0x1800584a3  jmp     loc_180058554
0x1800584a8  lea     r8, [rsp+280h+var_248]
0x1800584ad  xor     edx, edx
0x1800584af  mov     rcx, rdi
0x1800584b2  call    ValidateDHKey
0x1800584b7  mov     ebx, eax
0x1800584b9  test    eax, eax
0x1800584bb  jns     short loc_1800584C5
0x1800584bd  mov     r9d, 456h
0x1800584c3  jmp     short loc_1800584A1
0x1800584c5  mov     rbx, [rsp+280h+var_250]
0x1800584ca  mov     rcx, [rsp+280h+var_248]
0x1800584cf  mov     eax, [rbx+8]
0x1800584d2  cmp     [rcx+8], eax
0x1800584d5  jnz     short loc_18005853C
0x1800584d7  mov     eax, [rbx+0Ch]
0x1800584da  cmp     [rcx+0Ch], eax
0x1800584dd  jnz     short loc_18005853C
0x1800584df  mov     rdx, [rcx+20h]
0x1800584e3  test    rdx, rdx
0x1800584e6  jnz     short loc_1800584F0
0x1800584e8  mov     r9d, 469h
0x1800584ee  jmp     short loc_18005854A
0x1800584f0  mov     rcx, [rbx+20h]
0x1800584f4  mov     [rsp+280h+var_258], rax
0x1800584f9  lea     rax, [rsp+280h+Src]
0x1800584fe  mov     qword ptr [rsp+280h+var_260], rax
0x180058503  call    SymCryptDhSecretAgreement
0x180058508  mov     eax, [rbx+8]
0x18005850b  lea     r8, [rsp+280h+var_240]
0x180058510  mov     edx, [rbx+0Ch]; Size
0x180058513  lea     rcx, [rsp+280h+Src]; Src
0x180058518  mov     [rsp+280h+var_260], eax; int
0x18005851c  call    MSCryptCreateSecret
0x180058521  mov     ebx, eax
0x180058523  test    eax, eax
0x180058525  jns     short loc_180058532
0x180058527  mov     r9d, 480h
0x18005852d  jmp     loc_1800584A1
0x180058532  mov     rax, [rsp+280h+var_240]
0x180058537  mov     [rsi], rax
0x18005853a  jmp     short loc_180058567
0x18005853c  mov     r9d, 462h
0x180058542  jmp     short loc_18005854A
0x180058544  mov     r9d, 448h
0x18005854a  mov     ebx, 0C000000Dh
0x18005854f  mov     ecx, 0C000000Dh
0x180058554  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005855b  lea     rdx, aStatus; "Status"
0x180058562  call    DebugTraceError
0x180058567  mov     ecx, 200h
0x18005856c  lea     rax, [rsp+280h+Src]
0x180058571  mov     byte ptr [rax], 0
0x180058574  inc     rax
0x180058577  sub     rcx, 1
0x18005857b  jnz     short loc_180058571
0x18005857d  lea     r9, aDh; "DH"
0x180058584  mov     edx, 200h
0x180058589  lea     rcx, [rsp+280h+Src]
0x18005858e  call    MSCryptAuditCheckSecureZero
0x180058593  mov     eax, ebx
0x180058595  mov     rcx, [rbp+180h+var_30]
0x18005859c  xor     rcx, rsp; StackCookie
0x18005859f  call    __security_check_cookie
0x1800585a4  add     rsp, 260h
0x1800585ab  pop     r14
0x1800585ad  pop     rdi
0x1800585ae  pop     rsi
0x1800585af  pop     rbx
0x1800585b0  pop     rbp
0x1800585b1  retn
```

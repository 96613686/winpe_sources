# SIPolicyVerifyTokenSigned

- ea: `0x180024854`
- end: `0x180024a25`
- name: `SIPolicyVerifyTokenSigned`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022f78`

## callees

- `0x180003888`
- `0x18002467c`
- `0x180024854`
- `0x1800294a4`

## pseudocode

```c
char __fastcall SIPolicyVerifyTokenSigned(__int64 a1, int a2)
{
  _QWORD *v2; // rdi
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int i; // esi
  __int64 v8; // r14
  int v9; // edx
  int v10; // r9d
  unsigned int j; // esi
  __int64 v12; // r14
  int v13; // edx
  int v14; // r9d
  unsigned int k; // esi
  __int64 v16; // r14
  int v17; // edx
  int v18; // r9d
  _QWORD v20[2]; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-89h] BYREF
  __int128 v22; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v23[4]; // [rsp+60h] [rbp-69h] BYREF
  int v24; // [rsp+64h] [rbp-65h]
  int v25; // [rsp+68h] [rbp-61h]
  __int64 v26; // [rsp+70h] [rbp-59h]

  v2 = g_SiPolicyTokens;
  if ( g_SiPolicyTokens != (_UNKNOWN *)&g_SiPolicyTokens )
  {
    while ( v2 != &g_SiPolicyTokens )
    {
      v5 = v2[2];
      v21[1] = L"SupplementalPolicyAuthorization";
      v21[0] = 4194366;
      v20[1] = L"PolicyID";
      v20[0] = 1179664;
      v22 = 0;
      if ( (int)SbGetRegistryGuidInPolicy(v5, a2, (unsigned int)v21, (unsigned int)v20, (__int64)&v22) < 0 )
        break;
      v6 = v22 - *(_QWORD *)(a1 + 720);
      if ( (_QWORD)v22 == *(_QWORD *)(a1 + 720) )
        v6 = *((_QWORD *)&v22 + 1) - *(_QWORD *)(a1 + 728);
      if ( !v6 )
      {
        for ( i = 0; ; ++i )
        {
          v8 = v2[3];
          if ( i >= *(_DWORD *)(v8 + 8) )
            break;
          memset_0(v23, 0, 0x90u);
          v24 = 32780;
          v25 = 32;
          v26 = *(_QWORD *)v8 + 32 * i;
          if ( (unsigned __int8)SIPolicyValidateChainAgainstSigner(a2, v9, (unsigned int)v23, v10, 1) )
          {
LABEL_20:
            *(_DWORD *)(a1 + 768) |= 0x20u;
            return 1;
          }
        }
        for ( j = 0; ; ++j )
        {
          v12 = v2[3];
          if ( j >= *(_DWORD *)(v12 + 24) )
            break;
          memset_0(v23, 0, 0x90u);
          v24 = 32781;
          v25 = 48;
          v26 = *(_QWORD *)(v12 + 16) + 48 * j;
          if ( (unsigned __int8)SIPolicyValidateChainAgainstSigner(a2, v13, (unsigned int)v23, v14, 1) )
            goto LABEL_20;
        }
        for ( k = 0; ; ++k )
        {
          v16 = v2[3];
          if ( k >= *(_DWORD *)(v16 + 40) )
            break;
          memset_0(v23, 0, 0x90u);
          v24 = 32782;
          v25 = 64;
          v26 = *(_QWORD *)(v16 + 32) + (k << 6);
          if ( (unsigned __int8)SIPolicyValidateChainAgainstSigner(a2, v17, (unsigned int)v23, v18, 1) )
            goto LABEL_20;
        }
      }
      v2 = (_QWORD *)*v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024854  push    rbp
0x180024856  push    rbx
0x180024857  push    rsi
0x180024858  push    rdi
0x180024859  push    r13
0x18002485b  push    r14
0x18002485d  push    r15
0x18002485f  lea     rbp, [rsp-27h]
0x180024864  sub     rsp, 0F0h
0x18002486b  mov     rdi, cs:g_SiPolicyTokens
0x180024872  lea     r13, g_SiPolicyTokens
0x180024879  mov     r15, rdx
0x18002487c  mov     rbx, rcx
0x18002487f  cmp     rdi, r13
0x180024882  jz      loc_180024A11
0x180024888  cmp     rdi, r13
0x18002488b  jz      loc_180024A11
0x180024891  mov     rcx, [rdi+10h]
0x180024895  lea     rax, SourceString; "SupplementalPolicyAuthorization"
0x18002489c  mov     [rsp+120h+var_D8], rax
0x1800248a1  lea     r9, [rsp+120h+var_F0]
0x1800248a6  lea     rax, aPolicyid; "PolicyID"
0x1800248ad  mov     [rsp+120h+var_E0], 40003Eh
0x1800248b6  mov     [rsp+120h+var_E8], rax
0x1800248bb  lea     r8, [rsp+120h+var_E0]
0x1800248c0  lea     rax, [rbp+57h+var_D0]
0x1800248c4  mov     [rsp+120h+var_F0], 120010h
0x1800248cd  xorps   xmm0, xmm0
0x1800248d0  mov     [rsp+120h+var_100], rax
0x1800248d5  movups  [rbp+57h+var_D0], xmm0
0x1800248d9  call    SbGetRegistryGuidInPolicy
0x1800248de  test    eax, eax
0x1800248e0  js      loc_180024A11
0x1800248e6  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800248ea  sub     rax, [rbx+2D0h]
0x1800248f1  jnz     short loc_1800248FE
0x1800248f3  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x1800248f7  sub     rax, [rbx+2D8h]
0x1800248fe  test    rax, rax
0x180024901  jnz     loc_1800249FE
0x180024907  xor     esi, esi
0x180024909  mov     r14, [rdi+18h]
0x18002490d  cmp     esi, [r14+8]
0x180024911  jnb     short loc_18002495B
0x180024913  xor     edx, edx; Val
0x180024915  lea     rcx, [rbp+57h+var_C0]; void *
0x180024919  mov     r8d, 90h; Size
0x18002491f  call    memset_0
0x180024924  mov     ecx, esi
0x180024926  mov     [rbp+57h+var_BC], 800Ch
0x18002492d  shl     ecx, 5
0x180024930  lea     r8, [rbp+57h+var_C0]
0x180024934  mov     [rbp+57h+var_B8], 20h ; ' '
0x18002493b  add     rcx, [r14]
0x18002493e  mov     [rbp+57h+var_B0], rcx
0x180024942  mov     rcx, r15
0x180024945  mov     byte ptr [rsp+120h+var_100], 1
0x18002494a  call    SIPolicyValidateChainAgainstSigner
0x18002494f  test    al, al
0x180024951  jnz     loc_180024A06
0x180024957  inc     esi
0x180024959  jmp     short loc_180024909
0x18002495b  xor     esi, esi
0x18002495d  mov     r14, [rdi+18h]
0x180024961  cmp     esi, [r14+18h]
0x180024965  jnb     short loc_1800249AD
0x180024967  xor     edx, edx; Val
0x180024969  lea     rcx, [rbp+57h+var_C0]; void *
0x18002496d  mov     r8d, 90h; Size
0x180024973  call    memset_0
0x180024978  lea     ecx, [rsi+rsi*2]
0x18002497b  mov     [rbp+57h+var_BC], 800Dh
0x180024982  shl     ecx, 4
0x180024985  lea     r8, [rbp+57h+var_C0]
0x180024989  mov     [rbp+57h+var_B8], 30h ; '0'
0x180024990  add     rcx, [r14+10h]
0x180024994  mov     [rbp+57h+var_B0], rcx
0x180024998  mov     rcx, r15
0x18002499b  mov     byte ptr [rsp+120h+var_100], 1
0x1800249a0  call    SIPolicyValidateChainAgainstSigner
0x1800249a5  test    al, al
0x1800249a7  jnz     short loc_180024A06
0x1800249a9  inc     esi
0x1800249ab  jmp     short loc_18002495D
0x1800249ad  xor     esi, esi
0x1800249af  mov     r14, [rdi+18h]
0x1800249b3  cmp     esi, [r14+28h]
0x1800249b7  jnb     short loc_1800249FE
0x1800249b9  xor     edx, edx; Val
0x1800249bb  lea     rcx, [rbp+57h+var_C0]; void *
0x1800249bf  mov     r8d, 90h; Size
0x1800249c5  call    memset_0
0x1800249ca  mov     ecx, esi
0x1800249cc  mov     [rbp+57h+var_BC], 800Eh
0x1800249d3  shl     ecx, 6
0x1800249d6  lea     r8, [rbp+57h+var_C0]
0x1800249da  mov     [rbp+57h+var_B8], 40h ; '@'
0x1800249e1  add     rcx, [r14+20h]
0x1800249e5  mov     [rbp+57h+var_B0], rcx
0x1800249e9  mov     rcx, r15
0x1800249ec  mov     byte ptr [rsp+120h+var_100], 1
0x1800249f1  call    SIPolicyValidateChainAgainstSigner
0x1800249f6  test    al, al
0x1800249f8  jnz     short loc_180024A06
0x1800249fa  inc     esi
0x1800249fc  jmp     short loc_1800249AF
0x1800249fe  mov     rdi, [rdi]
0x180024a01  jmp     loc_180024888
0x180024a06  or      dword ptr [rbx+300h], 20h
0x180024a0d  mov     al, 1
0x180024a0f  jmp     short loc_180024A13
0x180024a11  xor     al, al
0x180024a13  add     rsp, 0F0h
0x180024a1a  pop     r15
0x180024a1c  pop     r14
0x180024a1e  pop     r13
0x180024a20  pop     rdi
0x180024a21  pop     rsi
0x180024a22  pop     rbx
0x180024a23  pop     rbp
0x180024a24  retn
```

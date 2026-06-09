# KdcCheckKeyUsage(uchar,ulong,char * *,_CERT_CONTEXT const *,int *)

- ea: `0x180050760`
- end: `0x1800509a3`
- name: `?KdcCheckKeyUsage@@YAJEKPEAPEADPEBU_CERT_CONTEXT@@PEAH@Z`
- size: `579`
- prototype: `__int64 __fastcall(char, unsigned int, char **, const struct _CERT_CONTEXT *, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fa10`
- `0x18004ffac`
- `0x1800504e4`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x180010718`
- `0x1800107dc`
- `0x180010884`
- `0x180050760`
- `0x18005a060`
- `0x180099c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005086d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005086d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050904`
- `CRYPT32!CertFindExtension` at `0x180050804`
- `CRYPT32!CertFindExtension` at `0x180050804`
- `CRYPT32!CryptDecodeObject` at `0x180050846`
- `CRYPT32!CryptDecodeObject` at `0x1800508d9`
- `CRYPT32!CryptDecodeObject` at `0x180050846`
- `CRYPT32!CryptDecodeObject` at `0x1800508d9`

## pseudocode

```c
__int64 __fastcall KdcCheckKeyUsage(char a1, unsigned int a2, char **a3, const struct _CERT_CONTEXT *a4, int *a5)
{
  __int64 v8; // rax
  int *v9; // rdi
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // ebx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v14; // rbx
  DWORD LastError; // eax
  __int64 v16; // rdx
  _QWORD *pvStructInfo; // rax
  _QWORD *v18; // rsi
  __int64 i; // rbx
  __int64 j; // rdx
  char *v21; // r8
  __int64 v22; // r9
  int v23; // eax
  int v24; // ecx
  _QWORD *v26; // [rsp+40h] [rbp-58h] BYREF
  __int64 v27; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v28[72]; // [rsp+50h] [rbp-48h] BYREF
  DWORD pcbStructInfo; // [rsp+B8h] [rbp+20h] BYREF

  pcbStructInfo = 0;
  v26 = 0;
  v8 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v27, &v26);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v28, v8);
  v9 = a5;
  v11 = *(_QWORD *)(v10 + 24);
  *a5 = 0;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
    goto LABEL_5;
  }
  Extension = CertFindExtension("2.5.29.37", *(_DWORD *)(v11 + 192), *(CERT_EXTENSION **)(v11 + 200));
  v14 = Extension;
  if ( !Extension )
  {
    if ( !a1 )
LABEL_32:
      *v9 = 1;
    goto LABEL_33;
  }
  if ( !CryptDecodeObject(1u, (LPCSTR)0x24, Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo) )
  {
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_5;
    LastError = GetLastError();
    v16 = 13;
    goto LABEL_11;
  }
  pvStructInfo = MIDL_user_allocate(pcbStructInfo);
  v26 = pvStructInfo;
  if ( !pvStructInfo )
    goto LABEL_5;
  if ( CryptDecodeObject(1u, (LPCSTR)0x24, v14->Value.pbData, v14->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
  {
    v18 = v26;
    for ( i = 0; (unsigned int)i < *(_DWORD *)v18; i = (unsigned int)(i + 1) )
    {
      for ( j = 0; (unsigned int)j < a2; j = (unsigned int)(j + 1) )
      {
        v21 = a3[j];
        v22 = *(_QWORD *)(v18[1] + 8 * i) - (_QWORD)v21;
        do
        {
          v23 = (unsigned __int8)v21[v22];
          v24 = (unsigned __int8)*v21 - v23;
          if ( v24 )
            break;
          ++v21;
        }
        while ( v23 );
        if ( !v24 )
        {
          *v9 = 1;
          break;
        }
      }
      if ( *v9 )
        break;
      if ( !a1 && !strcmp_0("2.5.29.37.0", *(const char **)(v18[1] + 8 * i)) )
        goto LABEL_32;
    }
LABEL_33:
    v12 = 0;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_5;
  LastError = GetLastError();
  v16 = 14;
LABEL_11:
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, LastError);
LABEL_5:
  v12 = 60;
LABEL_34:
  wil::details::lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___::_lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___(v28);
  return v12;
}

```

## disassembly

```asm
0x180050760  mov     rax, rsp
0x180050763  push    rbx
0x180050764  push    rbp
0x180050765  push    rsi
0x180050766  push    rdi
0x180050767  push    r14
0x180050769  push    r15
0x18005076b  sub     rsp, 68h
0x18005076f  mov     r14d, edx
0x180050772  mov     dword ptr [rax+20h], 0
0x180050779  mov     bpl, cl
0x18005077c  mov     qword ptr [rax-58h], 0
0x180050784  lea     rdx, [rax-58h]
0x180050788  mov     r15, r8
0x18005078b  lea     rcx, [rax-50h]
0x18005078f  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x180050794  mov     rdx, rax
0x180050797  lea     rcx, [rsp+98h+var_48]
0x18005079c  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x1800507a1  mov     rdi, [rsp+98h+arg_20]
0x1800507a9  mov     rdx, [r9+18h]
0x1800507ad  mov     dword ptr [rdi], 0
0x1800507b3  test    rdx, rdx
0x1800507b6  jnz     short loc_1800507F0
0x1800507b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800507bf  lea     rax, WPP_GLOBAL_Control
0x1800507c6  cmp     rcx, rax
0x1800507c9  jz      short loc_1800507E6
0x1800507cb  test    byte ptr [rcx+1Ch], 1
0x1800507cf  jz      short loc_1800507E6
0x1800507d1  mov     rcx, [rcx+10h]
0x1800507d5  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x1800507dc  mov     edx, 0Ch
0x1800507e1  call    WPP_SF_
0x1800507e6  mov     ebx, 3Ch ; '<'
0x1800507eb  jmp     loc_18005098A
0x1800507f0  mov     r8, [rdx+0C8h]; rgExtensions
0x1800507f7  lea     rcx, pszObjId; "2.5.29.37"
0x1800507fe  mov     edx, [rdx+0C0h]; cExtensions
0x180050804  call    cs:__imp_CertFindExtension
0x18005080a  mov     rbx, rax
0x18005080d  test    rax, rax
0x180050810  jz      loc_18005097D
0x180050816  mov     r9d, [rbx+10h]; cbEncoded
0x18005081a  lea     rax, [rsp+98h+arg_18]
0x180050822  mov     r8, [rbx+18h]; pbEncoded
0x180050826  mov     esi, 24h ; '$'
0x18005082b  mov     [rsp+98h+pcbStructInfo], rax; pcbStructInfo
0x180050830  mov     edx, esi; lpszStructType
0x180050832  mov     [rsp+98h+pvStructInfo], 0; pvStructInfo
0x18005083b  mov     [rsp+98h+dwFlags], 0; dwFlags
0x180050843  lea     ecx, [rsi-23h]; dwCertEncodingType
0x180050846  call    cs:__imp_CryptDecodeObject
0x18005084c  test    eax, eax
0x18005084e  jnz     short loc_180050895
0x180050850  mov     rcx, cs:WPP_GLOBAL_Control
0x180050857  lea     rax, WPP_GLOBAL_Control
0x18005085e  cmp     rcx, rax
0x180050861  jz      short loc_1800507E6
0x180050863  test    byte ptr [rcx+1Ch], 1
0x180050867  jz      loc_1800507E6
0x18005086d  call    cs:__imp_GetLastError
0x180050873  lea     edx, [rsi-17h]
0x180050876  mov     rcx, cs:WPP_GLOBAL_Control
0x18005087d  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180050884  mov     r9d, eax
0x180050887  mov     rcx, [rcx+10h]
0x18005088b  call    WPP_SF_d
0x180050890  jmp     loc_1800507E6
0x180050895  mov     ecx, [rsp+98h+arg_18]; size
0x18005089c  call    MIDL_user_allocate
0x1800508a1  mov     [rsp+98h+var_58], rax
0x1800508a6  test    rax, rax
0x1800508a9  jz      loc_1800507E6
0x1800508af  mov     r9d, [rbx+10h]; cbEncoded
0x1800508b3  lea     rcx, [rsp+98h+arg_18]
0x1800508bb  mov     r8, [rbx+18h]; pbEncoded
0x1800508bf  mov     rdx, rsi; lpszStructType
0x1800508c2  mov     [rsp+98h+pcbStructInfo], rcx; pcbStructInfo
0x1800508c7  mov     ecx, 1; dwCertEncodingType
0x1800508cc  mov     [rsp+98h+pvStructInfo], rax; pvStructInfo
0x1800508d1  mov     [rsp+98h+dwFlags], 0; dwFlags
0x1800508d9  call    cs:__imp_CryptDecodeObject
0x1800508df  test    eax, eax
0x1800508e1  jnz     short loc_180050914
0x1800508e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508ea  lea     rax, WPP_GLOBAL_Control
0x1800508f1  cmp     rcx, rax
0x1800508f4  jz      loc_1800507E6
0x1800508fa  test    byte ptr [rcx+1Ch], 1
0x1800508fe  jz      loc_1800507E6
0x180050904  call    cs:__imp_GetLastError
0x18005090a  mov     edx, 0Eh
0x18005090f  jmp     loc_180050876
0x180050914  mov     rsi, [rsp+98h+var_58]
0x180050919  xor     ebx, ebx
0x18005091b  cmp     ebx, [rsi]
0x18005091d  jnb     short loc_180050988
0x18005091f  xor     edx, edx
0x180050921  cmp     edx, r14d
0x180050924  jnb     short loc_180050957
0x180050926  mov     rcx, [rsi+8]
0x18005092a  mov     r8, [r15+rdx*8]
0x18005092e  mov     r9, [rcx+rbx*8]
0x180050932  sub     r9, r8
0x180050935  movzx   ecx, byte ptr [r8]
0x180050939  movzx   eax, byte ptr [r8+r9]
0x18005093e  sub     ecx, eax
0x180050940  jnz     short loc_180050949
0x180050942  inc     r8
0x180050945  test    eax, eax
0x180050947  jnz     short loc_180050935
0x180050949  test    ecx, ecx
0x18005094b  jz      short loc_180050951
0x18005094d  inc     edx
0x18005094f  jmp     short loc_180050921
0x180050951  mov     dword ptr [rdi], 1
0x180050957  cmp     dword ptr [rdi], 0
0x18005095a  jnz     short loc_180050988
0x18005095c  test    bpl, bpl
0x18005095f  jnz     short loc_180050979
0x180050961  mov     rdx, [rsi+8]
0x180050965  lea     rcx, Str1; "2.5.29.37.0"
0x18005096c  mov     rdx, [rdx+rbx*8]; Str2
0x180050970  call    strcmp_0
0x180050975  test    eax, eax
0x180050977  jz      short loc_180050982
0x180050979  inc     ebx
0x18005097b  jmp     short loc_18005091B
0x18005097d  test    bpl, bpl
0x180050980  jnz     short loc_180050988
0x180050982  mov     dword ptr [rdi], 1
0x180050988  xor     ebx, ebx
0x18005098a  lea     rcx, [rsp+98h+var_48]
0x18005098f  call    wil__details__lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5______lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___
0x180050994  mov     eax, ebx
0x180050996  add     rsp, 68h
0x18005099a  pop     r15
0x18005099c  pop     r14
0x18005099e  pop     rdi
0x18005099f  pop     rsi
0x1800509a0  pop     rbp
0x1800509a1  pop     rbx
0x1800509a2  retn
```

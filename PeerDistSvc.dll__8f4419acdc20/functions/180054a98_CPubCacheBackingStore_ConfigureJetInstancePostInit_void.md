# CPubCacheBackingStore::ConfigureJetInstancePostInit(void)

- ea: `0x180054a98`
- end: `0x180054ce8`
- name: `?ConfigureJetInstancePostInit@CPubCacheBackingStore@@AEAAKXZ`
- size: `592`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800562b0`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x180054a98`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x180054bf4`
- `ESENT!JetSetSystemParameterW` at `0x180054c4f`
- `ESENT!JetSetSystemParameterW` at `0x180054c97`
- `ESENT!JetSetSystemParameterW` at `0x180054bf4`
- `ESENT!JetSetSystemParameterW` at `0x180054c4f`
- `ESENT!JetSetSystemParameterW` at `0x180054c97`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::ConfigureJetInstancePostInit(CPubCacheBackingStore *this)
{
  unsigned __int64 v1; // rbx
  CHostedCacheMsgEncoding *v3; // rcx
  JET_INSTANCE *v4; // rdi
  JET_ERR v5; // eax
  unsigned int v6; // ebx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_API_PTR v9; // rsi
  JET_ERR v10; // eax
  JET_ERR v11; // eax

  v1 = *((_QWORD *)this + 18) >> 15;
  if ( v1 > 0xFFFFFFFF )
    LODWORD(v1) = -1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v3 + 108) & 4) != 0 && *((_BYTE *)v3 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v3 + 12), 56, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v3 + 108) & 4) != 0 && *((_BYTE *)v3 + 105) >= 3u )
        {
          WPP_SF_(*((_QWORD *)v3 + 12), 57, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
          v3 = WPP_GLOBAL_Control;
        }
        if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v3 + 108) & 4) != 0 && *((_BYTE *)v3 + 105) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)v3 + 12), 58, WPP_817cd87503153d87380e6127cb13644a_Traceguids, (unsigned int)v1);
            v3 = WPP_GLOBAL_Control;
          }
          if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v3 + 108) & 4) != 0 && *((_BYTE *)v3 + 105) >= 3u )
            {
              WPP_SF_d(*((_QWORD *)v3 + 12), 59, WPP_817cd87503153d87380e6127cb13644a_Traceguids, (unsigned int)v1);
              v3 = WPP_GLOBAL_Control;
            }
            if ( v3 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v3 + 108) & 4) != 0
              && *((_BYTE *)v3 + 105) >= 3u )
            {
              WPP_SF_(*((_QWORD *)v3 + 12), 60, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
            }
          }
        }
      }
    }
  }
  v4 = (JET_INSTANCE *)((char *)this + 264);
  v5 = JetSetSystemParameterW(v4, 0, 0x10u, 1u, 0);
  if ( v5 )
  {
    v6 = TranslateJetError(v5);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 61;
LABEL_42:
      WPP_SF_Dd(*((_QWORD *)v7 + 12), v8, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
  }
  else
  {
    v9 = (unsigned int)v1;
    v10 = JetSetSystemParameterW(v4, 0, 0x3Cu, (unsigned int)v1, 0);
    if ( v10 )
    {
      v6 = TranslateJetError(v10);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 62;
        goto LABEL_42;
      }
    }
    else
    {
      v6 = 0;
      v11 = JetSetSystemParameterW(v4, 0, 0x17u, v9, 0);
      if ( v11 )
      {
        v6 = TranslateJetError(v11);
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v8 = 63;
          goto LABEL_42;
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180054a98  push    rbx
0x180054a9a  push    rsi
0x180054a9b  push    rdi
0x180054a9c  push    r14
0x180054a9e  push    r15
0x180054aa0  sub     rsp, 30h
0x180054aa4  mov     rbx, [rcx+90h]
0x180054aab  mov     eax, 0FFFFFFFFh
0x180054ab0  shr     rbx, 0Fh
0x180054ab4  mov     rdi, rcx
0x180054ab7  cmp     rbx, rax
0x180054aba  cmova   rbx, rax
0x180054abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ac5  lea     r14, WPP_GLOBAL_Control
0x180054acc  lea     r15, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180054ad3  cmp     rcx, r14
0x180054ad6  jz      loc_180054BD7
0x180054adc  test    byte ptr [rcx+6Ch], 4
0x180054ae0  jz      short loc_180054B00
0x180054ae2  cmp     byte ptr [rcx+69h], 4
0x180054ae6  jb      short loc_180054B00
0x180054ae8  mov     rcx, [rcx+60h]
0x180054aec  mov     edx, 37h ; '7'
0x180054af1  mov     r8, r15
0x180054af4  call    WPP_SF_
0x180054af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b00  cmp     rcx, r14
0x180054b03  jz      loc_180054BD7
0x180054b09  test    byte ptr [rcx+6Ch], 4
0x180054b0d  mov     sil, 3
0x180054b10  jz      short loc_180054B30
0x180054b12  cmp     [rcx+69h], sil
0x180054b16  jb      short loc_180054B30
0x180054b18  mov     rcx, [rcx+60h]
0x180054b1c  mov     edx, 38h ; '8'
0x180054b21  mov     r8, r15
0x180054b24  call    WPP_SF_
0x180054b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b30  cmp     rcx, r14
0x180054b33  jz      loc_180054BD7
0x180054b39  test    byte ptr [rcx+6Ch], 4
0x180054b3d  jz      short loc_180054B5D
0x180054b3f  cmp     [rcx+69h], sil
0x180054b43  jb      short loc_180054B5D
0x180054b45  mov     rcx, [rcx+60h]
0x180054b49  mov     edx, 39h ; '9'
0x180054b4e  mov     r8, r15
0x180054b51  call    WPP_SF_
0x180054b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b5d  cmp     rcx, r14
0x180054b60  jz      short loc_180054BD7
0x180054b62  test    byte ptr [rcx+6Ch], 4
0x180054b66  jz      short loc_180054B89
0x180054b68  cmp     [rcx+69h], sil
0x180054b6c  jb      short loc_180054B89
0x180054b6e  mov     rcx, [rcx+60h]
0x180054b72  mov     r9d, ebx
0x180054b75  mov     edx, 3Ah ; ':'
0x180054b7a  mov     r8, r15
0x180054b7d  call    WPP_SF_d
0x180054b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180054b89  cmp     rcx, r14
0x180054b8c  jz      short loc_180054BD7
0x180054b8e  test    byte ptr [rcx+6Ch], 4
0x180054b92  jz      short loc_180054BB5
0x180054b94  cmp     [rcx+69h], sil
0x180054b98  jb      short loc_180054BB5
0x180054b9a  mov     rcx, [rcx+60h]
0x180054b9e  mov     r9d, ebx
0x180054ba1  mov     edx, 3Bh ; ';'
0x180054ba6  mov     r8, r15
0x180054ba9  call    WPP_SF_d
0x180054bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180054bb5  cmp     rcx, r14
0x180054bb8  jz      short loc_180054BD7
0x180054bba  test    byte ptr [rcx+6Ch], 4
0x180054bbe  jz      short loc_180054BD7
0x180054bc0  cmp     [rcx+69h], sil
0x180054bc4  jb      short loc_180054BD7
0x180054bc6  mov     rcx, [rcx+60h]
0x180054bca  mov     edx, 3Ch ; '<'
0x180054bcf  mov     r8, r15
0x180054bd2  call    WPP_SF_
0x180054bd7  xor     edx, edx; sesid
0x180054bd9  mov     [rsp+58h+szParam], 0; szParam
0x180054be2  add     rdi, 108h
0x180054be9  mov     rcx, rdi; pinstance
0x180054bec  lea     r9d, [rdx+1]; lParam
0x180054bf0  lea     r8d, [rdx+10h]; paramid
0x180054bf4  call    cs:__imp_JetSetSystemParameterW
0x180054bfa  mov     r9d, eax
0x180054bfd  test    eax, eax
0x180054bff  jz      short loc_180054C38
0x180054c01  mov     ecx, eax; int
0x180054c03  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180054c08  mov     ebx, eax
0x180054c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c11  cmp     rcx, r14
0x180054c14  jz      loc_180054CDA
0x180054c1a  test    byte ptr [rcx+6Ch], 4
0x180054c1e  jz      loc_180054CDA
0x180054c24  cmp     byte ptr [rcx+69h], 1
0x180054c28  jb      loc_180054CDA
0x180054c2e  mov     edx, 3Dh ; '='
0x180054c33  jmp     loc_180054CCA
0x180054c38  xor     edx, edx; sesid
0x180054c3a  mov     r9d, ebx; lParam
0x180054c3d  mov     rcx, rdi; pinstance
0x180054c40  mov     esi, ebx
0x180054c42  mov     [rsp+58h+szParam], 0; szParam
0x180054c4b  lea     r8d, [rdx+3Ch]; paramid
0x180054c4f  call    cs:__imp_JetSetSystemParameterW
0x180054c55  mov     r9d, eax
0x180054c58  test    eax, eax
0x180054c5a  jz      short loc_180054C84
0x180054c5c  mov     ecx, eax; int
0x180054c5e  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180054c63  mov     ebx, eax
0x180054c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c6c  cmp     rcx, r14
0x180054c6f  jz      short loc_180054CDA
0x180054c71  test    byte ptr [rcx+6Ch], 4
0x180054c75  jz      short loc_180054CDA
0x180054c77  cmp     byte ptr [rcx+69h], 1
0x180054c7b  jb      short loc_180054CDA
0x180054c7d  mov     edx, 3Eh ; '>'
0x180054c82  jmp     short loc_180054CCA
0x180054c84  xor     ebx, ebx
0x180054c86  mov     r9, rsi; lParam
0x180054c89  xor     edx, edx; sesid
0x180054c8b  mov     [rsp+58h+szParam], rbx; szParam
0x180054c90  mov     rcx, rdi; pinstance
0x180054c93  lea     r8d, [rbx+17h]; paramid
0x180054c97  call    cs:__imp_JetSetSystemParameterW
0x180054c9d  mov     r9d, eax
0x180054ca0  test    eax, eax
0x180054ca2  jz      short loc_180054CDA
0x180054ca4  mov     ecx, eax; int
0x180054ca6  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180054cab  mov     ebx, eax
0x180054cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180054cb4  cmp     rcx, r14
0x180054cb7  jz      short loc_180054CDA
0x180054cb9  test    byte ptr [rcx+6Ch], 4
0x180054cbd  jz      short loc_180054CDA
0x180054cbf  cmp     byte ptr [rcx+69h], 1
0x180054cc3  jb      short loc_180054CDA
0x180054cc5  mov     edx, 3Fh ; '?'
0x180054cca  mov     rcx, [rcx+60h]
0x180054cce  mov     r8, r15
0x180054cd1  mov     dword ptr [rsp+58h+szParam], eax
0x180054cd5  call    WPP_SF_Dd
0x180054cda  mov     eax, ebx
0x180054cdc  add     rsp, 30h
0x180054ce0  pop     r15
0x180054ce2  pop     r14
0x180054ce4  pop     rdi
0x180054ce5  pop     rsi
0x180054ce6  pop     rbx
0x180054ce7  retn
```

# CRepubCacheBackingStore::ConfigureJetInstancePostInit(void)

- ea: `0x18003e484`
- end: `0x18003e6cd`
- name: `?ConfigureJetInstancePostInit@CRepubCacheBackingStore@@AEAAKXZ`
- size: `585`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180041740`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18003e484`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x18003e5d9`
- `ESENT!JetSetSystemParameterW` at `0x18003e634`
- `ESENT!JetSetSystemParameterW` at `0x18003e67c`
- `ESENT!JetSetSystemParameterW` at `0x18003e5d9`
- `ESENT!JetSetSystemParameterW` at `0x18003e634`
- `ESENT!JetSetSystemParameterW` at `0x18003e67c`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::ConfigureJetInstancePostInit(CRepubCacheBackingStore *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  unsigned __int64 v3; // rbx
  JET_INSTANCE *v4; // rdi
  JET_ERR v5; // eax
  unsigned int v6; // ebx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_API_PTR v9; // rsi
  JET_ERR v10; // eax
  JET_ERR v11; // eax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 13) >> 15;
  if ( v3 > 0xFFFFFFFF )
    LODWORD(v3) = -1;
  if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)v2 + 12), 54, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v2 + 12), 55, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)v2 + 12), 56, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, (unsigned int)v3);
          v2 = WPP_GLOBAL_Control;
        }
        if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)v2 + 12), 57, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, (unsigned int)v3);
            v2 = WPP_GLOBAL_Control;
          }
          if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v2 + 108) & 4) != 0
            && *((_BYTE *)v2 + 105) >= 3u )
          {
            WPP_SF_(*((_QWORD *)v2 + 12), 58, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
          }
        }
      }
    }
  }
  v4 = (JET_INSTANCE *)((char *)this + 216);
  v5 = JetSetSystemParameterW(v4, 0, 0x10u, 1u, 0);
  if ( v5 )
  {
    v6 = TranslateJetError(v5);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 59;
LABEL_42:
      WPP_SF_Dd(*((_QWORD *)v7 + 12), v8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
  }
  else
  {
    v9 = (unsigned int)v3;
    v10 = JetSetSystemParameterW(v4, 0, 0x3Cu, (unsigned int)v3, 0);
    if ( v10 )
    {
      v6 = TranslateJetError(v10);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 60;
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
          v8 = 61;
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
0x18003e484  push    rbx
0x18003e486  push    rsi
0x18003e487  push    rdi
0x18003e488  push    r14
0x18003e48a  push    r15
0x18003e48c  sub     rsp, 30h
0x18003e490  mov     rdi, rcx
0x18003e493  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e49a  lea     r14, WPP_GLOBAL_Control
0x18003e4a1  lea     r15, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e4a8  cmp     rcx, r14
0x18003e4ab  jz      short loc_18003E4D1
0x18003e4ad  test    byte ptr [rcx+6Ch], 4
0x18003e4b1  jz      short loc_18003E4D1
0x18003e4b3  cmp     byte ptr [rcx+69h], 4
0x18003e4b7  jb      short loc_18003E4D1
0x18003e4b9  mov     rcx, [rcx+60h]
0x18003e4bd  mov     edx, 35h ; '5'
0x18003e4c2  mov     r8, r15
0x18003e4c5  call    WPP_SF_
0x18003e4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4d1  mov     rbx, [rdi+68h]
0x18003e4d5  mov     eax, 0FFFFFFFFh
0x18003e4da  shr     rbx, 0Fh
0x18003e4de  cmp     rbx, rax
0x18003e4e1  cmova   rbx, rax
0x18003e4e5  cmp     rcx, r14
0x18003e4e8  jz      loc_18003E5BC
0x18003e4ee  test    byte ptr [rcx+6Ch], 4
0x18003e4f2  mov     sil, 3
0x18003e4f5  jz      short loc_18003E515
0x18003e4f7  cmp     [rcx+69h], sil
0x18003e4fb  jb      short loc_18003E515
0x18003e4fd  mov     rcx, [rcx+60h]
0x18003e501  mov     edx, 36h ; '6'
0x18003e506  mov     r8, r15
0x18003e509  call    WPP_SF_
0x18003e50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e515  cmp     rcx, r14
0x18003e518  jz      loc_18003E5BC
0x18003e51e  test    byte ptr [rcx+6Ch], 4
0x18003e522  jz      short loc_18003E542
0x18003e524  cmp     [rcx+69h], sil
0x18003e528  jb      short loc_18003E542
0x18003e52a  mov     rcx, [rcx+60h]
0x18003e52e  mov     edx, 37h ; '7'
0x18003e533  mov     r8, r15
0x18003e536  call    WPP_SF_
0x18003e53b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e542  cmp     rcx, r14
0x18003e545  jz      short loc_18003E5BC
0x18003e547  test    byte ptr [rcx+6Ch], 4
0x18003e54b  jz      short loc_18003E56E
0x18003e54d  cmp     [rcx+69h], sil
0x18003e551  jb      short loc_18003E56E
0x18003e553  mov     rcx, [rcx+60h]
0x18003e557  mov     r9d, ebx
0x18003e55a  mov     edx, 38h ; '8'
0x18003e55f  mov     r8, r15
0x18003e562  call    WPP_SF_d
0x18003e567  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e56e  cmp     rcx, r14
0x18003e571  jz      short loc_18003E5BC
0x18003e573  test    byte ptr [rcx+6Ch], 4
0x18003e577  jz      short loc_18003E59A
0x18003e579  cmp     [rcx+69h], sil
0x18003e57d  jb      short loc_18003E59A
0x18003e57f  mov     rcx, [rcx+60h]
0x18003e583  mov     r9d, ebx
0x18003e586  mov     edx, 39h ; '9'
0x18003e58b  mov     r8, r15
0x18003e58e  call    WPP_SF_d
0x18003e593  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e59a  cmp     rcx, r14
0x18003e59d  jz      short loc_18003E5BC
0x18003e59f  test    byte ptr [rcx+6Ch], 4
0x18003e5a3  jz      short loc_18003E5BC
0x18003e5a5  cmp     [rcx+69h], sil
0x18003e5a9  jb      short loc_18003E5BC
0x18003e5ab  mov     rcx, [rcx+60h]
0x18003e5af  mov     edx, 3Ah ; ':'
0x18003e5b4  mov     r8, r15
0x18003e5b7  call    WPP_SF_
0x18003e5bc  xor     edx, edx; sesid
0x18003e5be  mov     [rsp+58h+szParam], 0; szParam
0x18003e5c7  add     rdi, 0D8h
0x18003e5ce  mov     rcx, rdi; pinstance
0x18003e5d1  lea     r9d, [rdx+1]; lParam
0x18003e5d5  lea     r8d, [rdx+10h]; paramid
0x18003e5d9  call    cs:__imp_JetSetSystemParameterW
0x18003e5df  mov     r9d, eax
0x18003e5e2  test    eax, eax
0x18003e5e4  jz      short loc_18003E61D
0x18003e5e6  mov     ecx, eax; int
0x18003e5e8  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003e5ed  mov     ebx, eax
0x18003e5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5f6  cmp     rcx, r14
0x18003e5f9  jz      loc_18003E6BF
0x18003e5ff  test    byte ptr [rcx+6Ch], 4
0x18003e603  jz      loc_18003E6BF
0x18003e609  cmp     byte ptr [rcx+69h], 1
0x18003e60d  jb      loc_18003E6BF
0x18003e613  mov     edx, 3Bh ; ';'
0x18003e618  jmp     loc_18003E6AF
0x18003e61d  xor     edx, edx; sesid
0x18003e61f  mov     r9d, ebx; lParam
0x18003e622  mov     rcx, rdi; pinstance
0x18003e625  mov     esi, ebx
0x18003e627  mov     [rsp+58h+szParam], 0; szParam
0x18003e630  lea     r8d, [rdx+3Ch]; paramid
0x18003e634  call    cs:__imp_JetSetSystemParameterW
0x18003e63a  mov     r9d, eax
0x18003e63d  test    eax, eax
0x18003e63f  jz      short loc_18003E669
0x18003e641  mov     ecx, eax; int
0x18003e643  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003e648  mov     ebx, eax
0x18003e64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e651  cmp     rcx, r14
0x18003e654  jz      short loc_18003E6BF
0x18003e656  test    byte ptr [rcx+6Ch], 4
0x18003e65a  jz      short loc_18003E6BF
0x18003e65c  cmp     byte ptr [rcx+69h], 1
0x18003e660  jb      short loc_18003E6BF
0x18003e662  mov     edx, 3Ch ; '<'
0x18003e667  jmp     short loc_18003E6AF
0x18003e669  xor     ebx, ebx
0x18003e66b  mov     r9, rsi; lParam
0x18003e66e  xor     edx, edx; sesid
0x18003e670  mov     [rsp+58h+szParam], rbx; szParam
0x18003e675  mov     rcx, rdi; pinstance
0x18003e678  lea     r8d, [rbx+17h]; paramid
0x18003e67c  call    cs:__imp_JetSetSystemParameterW
0x18003e682  mov     r9d, eax
0x18003e685  test    eax, eax
0x18003e687  jz      short loc_18003E6BF
0x18003e689  mov     ecx, eax; int
0x18003e68b  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003e690  mov     ebx, eax
0x18003e692  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e699  cmp     rcx, r14
0x18003e69c  jz      short loc_18003E6BF
0x18003e69e  test    byte ptr [rcx+6Ch], 4
0x18003e6a2  jz      short loc_18003E6BF
0x18003e6a4  cmp     byte ptr [rcx+69h], 1
0x18003e6a8  jb      short loc_18003E6BF
0x18003e6aa  mov     edx, 3Dh ; '='
0x18003e6af  mov     rcx, [rcx+60h]
0x18003e6b3  mov     r8, r15
0x18003e6b6  mov     dword ptr [rsp+58h+szParam], eax
0x18003e6ba  call    WPP_SF_Dd
0x18003e6bf  mov     eax, ebx
0x18003e6c1  add     rsp, 30h
0x18003e6c5  pop     r15
0x18003e6c7  pop     r14
0x18003e6c9  pop     rdi
0x18003e6ca  pop     rsi
0x18003e6cb  pop     rbx
0x18003e6cc  retn
```

# CRepubCacheBackingStore::CreateJetInstance(void)

- ea: `0x180041740`
- end: `0x1800418eb`
- name: `?CreateJetInstance@CRepubCacheBackingStore@@AEAAKXZ`
- size: `427`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180047cf4`

## callees

- `0x180008290`
- `0x18000ceac`
- `0x180018340`
- `0x18003e484`
- `0x18003e6d4`
- `0x180041740`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetInit3W` at `0x180041842`
- `ESENT!JetInit3W` at `0x180041842`
- `ESENT!JetCreateInstanceW` at `0x1800417a0`
- `ESENT!JetCreateInstanceW` at `0x1800417a0`
- `ESENT!JetTerm2` at `0x1800418d9`
- `ESENT!JetTerm2` at `0x1800418d9`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::CreateJetInstance(WCHAR *this)
{
  JET_ERR v2; // eax
  unsigned int v3; // ebx
  CHostedCacheMsgEncoding *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_ERR v9; // eax
  JET_INSTANCE pinstance; // [rsp+60h] [rbp+8h] BYREF

  pinstance = -1;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, this + 112);
  }
  v2 = JetCreateInstanceW(&pinstance, this + 112);
  if ( v2 )
  {
    v3 = TranslateJetError(v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v5 = 26;
LABEL_10:
      WPP_SF_Dd(*((_QWORD *)v4 + 12), v5, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  v6 = CRepubCacheBackingStore::ConfigureJetInstancePreInit((CRepubCacheBackingStore *)this, pinstance);
  v3 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_27;
    }
    v8 = 27;
    goto LABEL_26;
  }
  v9 = JetInit3W(&pinstance, 0, 0x94u);
  if ( !v9 )
  {
    *((_QWORD *)this + 27) = pinstance;
    pinstance = -1;
    v6 = CRepubCacheBackingStore::ConfigureJetInstancePostInit((CRepubCacheBackingStore *)this);
    v3 = v6;
    if ( !v6 )
      goto LABEL_27;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_27;
    }
    v8 = 29;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v6);
    goto LABEL_27;
  }
  v3 = TranslateJetError(v9);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v5 = 28;
    goto LABEL_10;
  }
LABEL_27:
  if ( pinstance != -1 )
    JetTerm2(pinstance, 2u);
  return v3;
}

```

## disassembly

```asm
0x180041740  push    rbx
0x180041742  push    rbp
0x180041743  push    rdi
0x180041744  push    r14
0x180041746  sub     rsp, 38h
0x18004174a  mov     rdi, rcx
0x18004174d  mov     [rsp+58h+pinstance], 0FFFFFFFFFFFFFFFFh
0x180041756  mov     rcx, cs:WPP_GLOBAL_Control
0x18004175d  lea     rbp, WPP_GLOBAL_Control
0x180041764  lea     r14, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004176b  cmp     rcx, rbp
0x18004176e  jz      short loc_180041794
0x180041770  test    byte ptr [rcx+6Ch], 4
0x180041774  jz      short loc_180041794
0x180041776  cmp     byte ptr [rcx+69h], 4
0x18004177a  jb      short loc_180041794
0x18004177c  mov     rcx, [rcx+60h]
0x180041780  lea     r9, [rdi+0E0h]
0x180041787  mov     edx, 19h
0x18004178c  mov     r8, r14
0x18004178f  call    WPP_SF_S
0x180041794  lea     rdx, [rdi+0E0h]; szInstanceName
0x18004179b  lea     rcx, [rsp+58h+pinstance]; pinstance
0x1800417a0  call    cs:__imp_JetCreateInstanceW
0x1800417a6  mov     r9d, eax
0x1800417a9  test    eax, eax
0x1800417ab  jz      short loc_1800417F4
0x1800417ad  mov     ecx, eax; int
0x1800417af  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800417b4  mov     ebx, eax
0x1800417b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417bd  cmp     rcx, rbp
0x1800417c0  jz      loc_1800418C9
0x1800417c6  test    byte ptr [rcx+6Ch], 4
0x1800417ca  jz      loc_1800418C9
0x1800417d0  cmp     byte ptr [rcx+69h], 1
0x1800417d4  jb      loc_1800418C9
0x1800417da  mov     edx, 1Ah
0x1800417df  mov     rcx, [rcx+60h]
0x1800417e3  mov     r8, r14
0x1800417e6  mov     [rsp+58h+var_38], eax
0x1800417ea  call    WPP_SF_Dd
0x1800417ef  jmp     loc_1800418C9
0x1800417f4  mov     rdx, [rsp+58h+pinstance]; unsigned __int64
0x1800417f9  mov     rcx, rdi; this
0x1800417fc  call    ?ConfigureJetInstancePreInit@CRepubCacheBackingStore@@AEAAK_K@Z; CRepubCacheBackingStore::ConfigureJetInstancePreInit(unsigned __int64)
0x180041801  mov     ebx, eax
0x180041803  test    eax, eax
0x180041805  jz      short loc_180041835
0x180041807  mov     rcx, cs:WPP_GLOBAL_Control
0x18004180e  cmp     rcx, rbp
0x180041811  jz      loc_1800418C9
0x180041817  test    byte ptr [rcx+6Ch], 4
0x18004181b  jz      loc_1800418C9
0x180041821  cmp     byte ptr [rcx+69h], 1
0x180041825  jb      loc_1800418C9
0x18004182b  mov     edx, 1Bh
0x180041830  jmp     loc_1800418BA
0x180041835  xor     edx, edx; prstInfo
0x180041837  lea     rcx, [rsp+58h+pinstance]; pinstance
0x18004183c  mov     r8d, 94h; grbit
0x180041842  call    cs:__imp_JetInit3W
0x180041848  mov     r9d, eax
0x18004184b  test    eax, eax
0x18004184d  jz      short loc_18004187A
0x18004184f  mov     ecx, eax; int
0x180041851  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180041856  mov     ebx, eax
0x180041858  mov     rcx, cs:WPP_GLOBAL_Control
0x18004185f  cmp     rcx, rbp
0x180041862  jz      short loc_1800418C9
0x180041864  test    byte ptr [rcx+6Ch], 4
0x180041868  jz      short loc_1800418C9
0x18004186a  cmp     byte ptr [rcx+69h], 1
0x18004186e  jb      short loc_1800418C9
0x180041870  mov     edx, 1Ch
0x180041875  jmp     loc_1800417DF
0x18004187a  mov     rax, [rsp+58h+pinstance]
0x18004187f  mov     rcx, rdi; this
0x180041882  mov     [rdi+0D8h], rax
0x180041889  mov     [rsp+58h+pinstance], 0FFFFFFFFFFFFFFFFh
0x180041892  call    ?ConfigureJetInstancePostInit@CRepubCacheBackingStore@@AEAAKXZ; CRepubCacheBackingStore::ConfigureJetInstancePostInit(void)
0x180041897  mov     ebx, eax
0x180041899  test    eax, eax
0x18004189b  jz      short loc_1800418C9
0x18004189d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418a4  cmp     rcx, rbp
0x1800418a7  jz      short loc_1800418C9
0x1800418a9  test    byte ptr [rcx+6Ch], 4
0x1800418ad  jz      short loc_1800418C9
0x1800418af  cmp     byte ptr [rcx+69h], 1
0x1800418b3  jb      short loc_1800418C9
0x1800418b5  mov     edx, 1Dh
0x1800418ba  mov     rcx, [rcx+60h]
0x1800418be  mov     r9d, eax
0x1800418c1  mov     r8, r14
0x1800418c4  call    WPP_SF_d
0x1800418c9  mov     rcx, [rsp+58h+pinstance]; instance
0x1800418ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800418d2  jz      short loc_1800418DF
0x1800418d4  mov     edx, 2; grbit
0x1800418d9  call    cs:__imp_JetTerm2
0x1800418df  mov     eax, ebx
0x1800418e1  add     rsp, 38h
0x1800418e5  pop     r14
0x1800418e7  pop     rdi
0x1800418e8  pop     rbp
0x1800418e9  pop     rbx
0x1800418ea  retn
```

# CPubCacheBackingStore::CreateJetInstance(void)

- ea: `0x1800562b0`
- end: `0x18005645b`
- name: `?CreateJetInstance@CPubCacheBackingStore@@AEAAKXZ`
- size: `427`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180059c0c`

## callees

- `0x180008290`
- `0x18000ceac`
- `0x180018340`
- `0x180054a98`
- `0x180054cf0`
- `0x1800562b0`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetInit3W` at `0x1800563b2`
- `ESENT!JetInit3W` at `0x1800563b2`
- `ESENT!JetCreateInstanceW` at `0x180056310`
- `ESENT!JetCreateInstanceW` at `0x180056310`
- `ESENT!JetTerm2` at `0x180056449`
- `ESENT!JetTerm2` at `0x180056449`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::CreateJetInstance(WCHAR *this)
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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_817cd87503153d87380e6127cb13644a_Traceguids, this + 136);
  }
  v2 = JetCreateInstanceW(&pinstance, this + 136);
  if ( v2 )
  {
    v3 = TranslateJetError(v2);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v5 = 28;
LABEL_10:
      WPP_SF_Dd(*((_QWORD *)v4 + 12), v5, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  v6 = CPubCacheBackingStore::ConfigureJetInstancePreInit((CPubCacheBackingStore *)this, pinstance);
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
    v8 = 29;
    goto LABEL_26;
  }
  v9 = JetInit3W(&pinstance, 0, 0x94u);
  if ( !v9 )
  {
    *((_QWORD *)this + 33) = pinstance;
    pinstance = -1;
    v6 = CPubCacheBackingStore::ConfigureJetInstancePostInit((CPubCacheBackingStore *)this);
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
    v8 = 31;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v6);
    goto LABEL_27;
  }
  v3 = TranslateJetError(v9);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v5 = 30;
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
0x1800562b0  push    rbx
0x1800562b2  push    rbp
0x1800562b3  push    rdi
0x1800562b4  push    r14
0x1800562b6  sub     rsp, 38h
0x1800562ba  mov     rdi, rcx
0x1800562bd  mov     [rsp+58h+pinstance], 0FFFFFFFFFFFFFFFFh
0x1800562c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562cd  lea     rbp, WPP_GLOBAL_Control
0x1800562d4  lea     r14, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x1800562db  cmp     rcx, rbp
0x1800562de  jz      short loc_180056304
0x1800562e0  test    byte ptr [rcx+6Ch], 4
0x1800562e4  jz      short loc_180056304
0x1800562e6  cmp     byte ptr [rcx+69h], 4
0x1800562ea  jb      short loc_180056304
0x1800562ec  mov     rcx, [rcx+60h]
0x1800562f0  lea     r9, [rdi+110h]
0x1800562f7  mov     edx, 1Bh
0x1800562fc  mov     r8, r14
0x1800562ff  call    WPP_SF_S
0x180056304  lea     rdx, [rdi+110h]; szInstanceName
0x18005630b  lea     rcx, [rsp+58h+pinstance]; pinstance
0x180056310  call    cs:__imp_JetCreateInstanceW
0x180056316  mov     r9d, eax
0x180056319  test    eax, eax
0x18005631b  jz      short loc_180056364
0x18005631d  mov     ecx, eax; int
0x18005631f  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180056324  mov     ebx, eax
0x180056326  mov     rcx, cs:WPP_GLOBAL_Control
0x18005632d  cmp     rcx, rbp
0x180056330  jz      loc_180056439
0x180056336  test    byte ptr [rcx+6Ch], 4
0x18005633a  jz      loc_180056439
0x180056340  cmp     byte ptr [rcx+69h], 1
0x180056344  jb      loc_180056439
0x18005634a  mov     edx, 1Ch
0x18005634f  mov     rcx, [rcx+60h]
0x180056353  mov     r8, r14
0x180056356  mov     [rsp+58h+var_38], eax
0x18005635a  call    WPP_SF_Dd
0x18005635f  jmp     loc_180056439
0x180056364  mov     rdx, [rsp+58h+pinstance]; unsigned __int64
0x180056369  mov     rcx, rdi; this
0x18005636c  call    ?ConfigureJetInstancePreInit@CPubCacheBackingStore@@AEAAK_K@Z; CPubCacheBackingStore::ConfigureJetInstancePreInit(unsigned __int64)
0x180056371  mov     ebx, eax
0x180056373  test    eax, eax
0x180056375  jz      short loc_1800563A5
0x180056377  mov     rcx, cs:WPP_GLOBAL_Control
0x18005637e  cmp     rcx, rbp
0x180056381  jz      loc_180056439
0x180056387  test    byte ptr [rcx+6Ch], 4
0x18005638b  jz      loc_180056439
0x180056391  cmp     byte ptr [rcx+69h], 1
0x180056395  jb      loc_180056439
0x18005639b  mov     edx, 1Dh
0x1800563a0  jmp     loc_18005642A
0x1800563a5  xor     edx, edx; prstInfo
0x1800563a7  lea     rcx, [rsp+58h+pinstance]; pinstance
0x1800563ac  mov     r8d, 94h; grbit
0x1800563b2  call    cs:__imp_JetInit3W
0x1800563b8  mov     r9d, eax
0x1800563bb  test    eax, eax
0x1800563bd  jz      short loc_1800563EA
0x1800563bf  mov     ecx, eax; int
0x1800563c1  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800563c6  mov     ebx, eax
0x1800563c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800563cf  cmp     rcx, rbp
0x1800563d2  jz      short loc_180056439
0x1800563d4  test    byte ptr [rcx+6Ch], 4
0x1800563d8  jz      short loc_180056439
0x1800563da  cmp     byte ptr [rcx+69h], 1
0x1800563de  jb      short loc_180056439
0x1800563e0  mov     edx, 1Eh
0x1800563e5  jmp     loc_18005634F
0x1800563ea  mov     rax, [rsp+58h+pinstance]
0x1800563ef  mov     rcx, rdi; this
0x1800563f2  mov     [rdi+108h], rax
0x1800563f9  mov     [rsp+58h+pinstance], 0FFFFFFFFFFFFFFFFh
0x180056402  call    ?ConfigureJetInstancePostInit@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::ConfigureJetInstancePostInit(void)
0x180056407  mov     ebx, eax
0x180056409  test    eax, eax
0x18005640b  jz      short loc_180056439
0x18005640d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056414  cmp     rcx, rbp
0x180056417  jz      short loc_180056439
0x180056419  test    byte ptr [rcx+6Ch], 4
0x18005641d  jz      short loc_180056439
0x18005641f  cmp     byte ptr [rcx+69h], 1
0x180056423  jb      short loc_180056439
0x180056425  mov     edx, 1Fh
0x18005642a  mov     rcx, [rcx+60h]
0x18005642e  mov     r9d, eax
0x180056431  mov     r8, r14
0x180056434  call    WPP_SF_d
0x180056439  mov     rcx, [rsp+58h+pinstance]; instance
0x18005643e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180056442  jz      short loc_18005644F
0x180056444  mov     edx, 2; grbit
0x180056449  call    cs:__imp_JetTerm2
0x18005644f  mov     eax, ebx
0x180056451  add     rsp, 38h
0x180056455  pop     r14
0x180056457  pop     rdi
0x180056458  pop     rbp
0x180056459  pop     rbx
0x18005645a  retn
```

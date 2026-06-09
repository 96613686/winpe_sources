# CPreLoadingReferenceFile::CreateJetInstance(void)

- ea: `0x1801327c4`
- end: `0x18013294e`
- name: `?CreateJetInstance@CPreLoadingReferenceFile@@AEAAKXZ`
- size: `394`
- prototype: `unsigned int __fastcall(CPreLoadingReferenceFile *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180133468`

## callees

- `0x180008290`
- `0x180018340`
- `0x180131fb4`
- `0x1801321e0`
- `0x1801327c4`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetInit3W` at `0x1801328af`
- `ESENT!JetInit3W` at `0x1801328af`
- `ESENT!JetCreateInstanceW` at `0x18013281e`
- `ESENT!JetCreateInstanceW` at `0x18013281e`
- `ESENT!JetTerm2` at `0x18013293c`
- `ESENT!JetTerm2` at `0x18013293c`

## pseudocode

```c
__int64 __fastcall CPreLoadingReferenceFile::CreateJetInstance(WCHAR *this)
{
  unsigned int v2; // ebx
  CHostedCacheMsgEncoding *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_INSTANCE pinstance; // [rsp+50h] [rbp+8h] BYREF

  pinstance = -1;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, this + 8);
  }
  v2 = JetCreateInstanceW(&pinstance, this + 8);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 25;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v3 + 12), v4, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v2);
LABEL_11:
    v5 = TranslateJetError(v2);
    goto LABEL_28;
  }
  v6 = CPreLoadingReferenceFile::ConfigureJetInstancePreInit((CPreLoadingReferenceFile *)this, pinstance);
  v5 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 26;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v6);
    }
  }
  else
  {
    v2 = JetInit3W(&pinstance, 0, 0x94u);
    if ( v2 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_11;
      }
      v4 = 27;
      goto LABEL_10;
    }
    *((_QWORD *)this + 472) = pinstance;
    pinstance = -1;
    v6 = CPreLoadingReferenceFile::ConfigureJetInstancePostInit((CPreLoadingReferenceFile *)this);
    v5 = v6;
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 28;
        goto LABEL_27;
      }
    }
  }
LABEL_28:
  if ( pinstance != -1 )
    JetTerm2(pinstance, 2u);
  return v5;
}

```

## disassembly

```asm
0x1801327c4  push    rbx
0x1801327c6  push    rbp
0x1801327c7  push    rdi
0x1801327c8  push    r14
0x1801327ca  sub     rsp, 28h
0x1801327ce  mov     rdi, rcx
0x1801327d1  mov     [rsp+48h+pinstance], 0FFFFFFFFFFFFFFFFh
0x1801327da  mov     rcx, cs:WPP_GLOBAL_Control
0x1801327e1  lea     rbp, WPP_GLOBAL_Control
0x1801327e8  lea     r14, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x1801327ef  cmp     rcx, rbp
0x1801327f2  jz      short loc_180132815
0x1801327f4  test    byte ptr [rcx+6Ch], 4
0x1801327f8  jz      short loc_180132815
0x1801327fa  cmp     byte ptr [rcx+69h], 4
0x1801327fe  jb      short loc_180132815
0x180132800  mov     rcx, [rcx+60h]
0x180132804  lea     r9, [rdi+10h]
0x180132808  mov     edx, 18h
0x18013280d  mov     r8, r14
0x180132810  call    WPP_SF_S
0x180132815  lea     rdx, [rdi+10h]; szInstanceName
0x180132819  lea     rcx, [rsp+48h+pinstance]; pinstance
0x18013281e  call    cs:__imp_JetCreateInstanceW
0x180132824  mov     ebx, eax
0x180132826  test    eax, eax
0x180132828  jz      short loc_180132864
0x18013282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180132831  cmp     rcx, rbp
0x180132834  jz      short loc_180132856
0x180132836  test    byte ptr [rcx+6Ch], 4
0x18013283a  jz      short loc_180132856
0x18013283c  cmp     byte ptr [rcx+69h], 1
0x180132840  jb      short loc_180132856
0x180132842  mov     edx, 19h
0x180132847  mov     rcx, [rcx+60h]
0x18013284b  mov     r9d, ebx
0x18013284e  mov     r8, r14
0x180132851  call    WPP_SF_d
0x180132856  mov     ecx, ebx; int
0x180132858  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18013285d  mov     ebx, eax
0x18013285f  jmp     loc_18013292C
0x180132864  mov     rdx, [rsp+48h+pinstance]; unsigned __int64
0x180132869  mov     rcx, rdi; this
0x18013286c  call    ?ConfigureJetInstancePreInit@CPreLoadingReferenceFile@@AEAAK_K@Z; CPreLoadingReferenceFile::ConfigureJetInstancePreInit(unsigned __int64)
0x180132871  mov     ebx, eax
0x180132873  test    eax, eax
0x180132875  jz      short loc_1801328A2
0x180132877  mov     rcx, cs:WPP_GLOBAL_Control
0x18013287e  cmp     rcx, rbp
0x180132881  jz      loc_18013292C
0x180132887  test    byte ptr [rcx+6Ch], 4
0x18013288b  jz      loc_18013292C
0x180132891  cmp     byte ptr [rcx+69h], 1
0x180132895  jb      loc_18013292C
0x18013289b  mov     edx, 1Ah
0x1801328a0  jmp     short loc_18013291D
0x1801328a2  xor     edx, edx; prstInfo
0x1801328a4  lea     rcx, [rsp+48h+pinstance]; pinstance
0x1801328a9  mov     r8d, 94h; grbit
0x1801328af  call    cs:__imp_JetInit3W
0x1801328b5  mov     ebx, eax
0x1801328b7  test    eax, eax
0x1801328b9  jz      short loc_1801328DD
0x1801328bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801328c2  cmp     rcx, rbp
0x1801328c5  jz      short loc_180132856
0x1801328c7  test    byte ptr [rcx+6Ch], 4
0x1801328cb  jz      short loc_180132856
0x1801328cd  cmp     byte ptr [rcx+69h], 1
0x1801328d1  jb      short loc_180132856
0x1801328d3  mov     edx, 1Bh
0x1801328d8  jmp     loc_180132847
0x1801328dd  mov     rax, [rsp+48h+pinstance]
0x1801328e2  mov     rcx, rdi; this
0x1801328e5  mov     [rdi+0EC0h], rax
0x1801328ec  mov     [rsp+48h+pinstance], 0FFFFFFFFFFFFFFFFh
0x1801328f5  call    ?ConfigureJetInstancePostInit@CPreLoadingReferenceFile@@AEAAKXZ; CPreLoadingReferenceFile::ConfigureJetInstancePostInit(void)
0x1801328fa  mov     ebx, eax
0x1801328fc  test    eax, eax
0x1801328fe  jz      short loc_18013292C
0x180132900  mov     rcx, cs:WPP_GLOBAL_Control
0x180132907  cmp     rcx, rbp
0x18013290a  jz      short loc_18013292C
0x18013290c  test    byte ptr [rcx+6Ch], 4
0x180132910  jz      short loc_18013292C
0x180132912  cmp     byte ptr [rcx+69h], 1
0x180132916  jb      short loc_18013292C
0x180132918  mov     edx, 1Ch
0x18013291d  mov     rcx, [rcx+60h]
0x180132921  mov     r9d, eax
0x180132924  mov     r8, r14
0x180132927  call    WPP_SF_d
0x18013292c  mov     rcx, [rsp+48h+pinstance]; instance
0x180132931  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180132935  jz      short loc_180132942
0x180132937  mov     edx, 2; grbit
0x18013293c  call    cs:__imp_JetTerm2
0x180132942  mov     eax, ebx
0x180132944  add     rsp, 28h
0x180132948  pop     r14
0x18013294a  pop     rdi
0x18013294b  pop     rbp
0x18013294c  pop     rbx
0x18013294d  retn
```

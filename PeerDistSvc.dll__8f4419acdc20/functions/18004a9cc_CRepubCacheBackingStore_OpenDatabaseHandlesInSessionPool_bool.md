# CRepubCacheBackingStore::OpenDatabaseHandlesInSessionPool(bool)

- ea: `0x18004a9cc`
- end: `0x18004abe5`
- name: `?OpenDatabaseHandlesInSessionPool@CRepubCacheBackingStore@@AEAAK_N@Z`
- size: `537`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003cbb8`

## callees

- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18000cf48`
- `0x18000ecf4`
- `0x180015e38`
- `0x18001fc30`
- `0x18004a9cc`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetOpenDatabaseW` at `0x18004aaaf`
- `ESENT!JetOpenDatabaseW` at `0x18004aaaf`
- `ESENT!JetSetSessionContext` at `0x18004aa7d`
- `ESENT!JetSetSessionContext` at `0x18004aa7d`
- `ESENT!JetResetSessionContext` at `0x18004aac2`
- `ESENT!JetResetSessionContext` at `0x18004aac2`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::OpenDatabaseHandlesInSessionPool(CRepubCacheBackingStore *this)
{
  unsigned int v2; // esi
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rbx
  unsigned int v8; // eax
  int v9; // ebp
  JET_ERR v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  int v13; // ecx
  _BYTE v15[32]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+80h] [rbp+8h] BYREF

  v2 = 0;
  InCritSec::InCritSec((InCritSec *)v15, (CRepubCacheBackingStore *)((char *)this + 50504), 1);
  v5 = (_QWORD *)**((_QWORD **)this + 6319);
  while ( v5 != *((_QWORD **)this + 6319) )
  {
    v6 = v5[2];
    v16 = 0;
    SmartPointer<INotification>::operator=(&v16, v6, v3, v4);
    v5 = (_QWORD *)*v5;
    v7 = v16;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        667,
        WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        v16,
        *(_QWORD *)(v16 + 24));
    }
    v8 = JetSetSessionContext(*(_QWORD *)(v7 + 24), *(unsigned int *)(v7 + 40));
    v9 = v8;
    if ( v8 && v8 != -1912 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 668, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v8);
      }
LABEL_18:
      v13 = v9;
LABEL_28:
      v2 = TranslateJetError(v13);
      SmartPointer<CRepubJetSessionContext>::Release(&v16);
      break;
    }
    if ( *(_DWORD *)(v7 + 32) == -1 )
    {
      v10 = JetOpenDatabaseW(*(_QWORD *)(v7 + 24), (JET_PCWSTR)this + 1396, 0, (JET_DBID *)(v7 + 32), 0);
      v9 = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            669,
            (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
            (_DWORD)this + 2792,
            v10);
        }
        goto LABEL_18;
      }
      *(_DWORD *)(v7 + 36) = 0;
    }
    v11 = JetResetSessionContext(*(_QWORD *)(v7 + 24));
    v12 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 670, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v11);
      }
      v13 = v12;
      goto LABEL_28;
    }
    SmartPointer<CRepubJetSessionContext>::Release(&v16);
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 671, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v2);
  }
  InCritSec::~InCritSec((InCritSec *)v15);
  return v2;
}

```

## disassembly

```asm
0x18004a9cc  mov     [rsp+arg_8], rbx
0x18004a9d1  mov     [rsp+arg_10], rbp
0x18004a9d6  push    rsi
0x18004a9d7  push    rdi
0x18004a9d8  push    r13
0x18004a9da  push    r14
0x18004a9dc  push    r15
0x18004a9de  sub     rsp, 50h
0x18004a9e2  mov     r14, rcx
0x18004a9e5  lea     rdx, [rcx+0C548h]; struct CritSec *
0x18004a9ec  lea     rcx, [rsp+78h+var_48]; this
0x18004a9f1  xor     esi, esi
0x18004a9f3  mov     r8b, 1; bool
0x18004a9f6  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18004a9fb  mov     rdi, [r14+0C578h]
0x18004aa02  lea     r13, WPP_GLOBAL_Control
0x18004aa09  mov     rdi, [rdi]
0x18004aa0c  cmp     rdi, [r14+0C578h]
0x18004aa13  jz      loc_18004AB90
0x18004aa19  mov     rdx, [rdi+10h]
0x18004aa1d  lea     rcx, [rsp+78h+arg_0]
0x18004aa25  mov     [rsp+78h+arg_0], rsi
0x18004aa2d  call    ??4?$SmartPointer@VINotification@@@@QEAAAEAV0@PEAVINotification@@@Z; SmartPointer<INotification>::operator=(INotification *)
0x18004aa32  mov     rdi, [rdi]
0x18004aa35  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa3c  mov     rbx, [rsp+78h+arg_0]
0x18004aa44  cmp     rcx, r13
0x18004aa47  jz      short loc_18004AA76
0x18004aa49  test    byte ptr [rcx+6Ch], 4
0x18004aa4d  jz      short loc_18004AA76
0x18004aa4f  cmp     byte ptr [rcx+69h], 4
0x18004aa53  jb      short loc_18004AA76
0x18004aa55  mov     rax, [rbx+18h]
0x18004aa59  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004aa60  mov     rcx, [rcx+60h]
0x18004aa64  mov     edx, 29Bh
0x18004aa69  mov     r9, rbx
0x18004aa6c  mov     qword ptr [rsp+78h+grbit], rax
0x18004aa71  call    WPP_SF_qq
0x18004aa76  mov     edx, [rbx+28h]; ulContext
0x18004aa79  mov     rcx, [rbx+18h]; sesid
0x18004aa7d  call    cs:__imp_JetSetSessionContext
0x18004aa83  mov     ebp, eax
0x18004aa85  test    eax, eax
0x18004aa87  jz      short loc_18004AA90
0x18004aa89  cmp     eax, 0FFFFF888h
0x18004aa8e  jnz     short loc_18004AAE0
0x18004aa90  lea     r9, [rbx+20h]; pdbid
0x18004aa94  cmp     dword ptr [r9], 0FFFFFFFFh
0x18004aa98  jnz     short loc_18004AABE
0x18004aa9a  mov     rcx, [rbx+18h]; sesid
0x18004aa9e  lea     r15, [r14+0AE8h]
0x18004aaa5  mov     rdx, r15; szFilename
0x18004aaa8  mov     [rsp+78h+grbit], esi; grbit
0x18004aaac  xor     r8d, r8d; szConnect
0x18004aaaf  call    cs:__imp_JetOpenDatabaseW
0x18004aab5  mov     ebp, eax
0x18004aab7  test    eax, eax
0x18004aab9  jnz     short loc_18004AB14
0x18004aabb  mov     [rbx+24h], esi
0x18004aabe  mov     rcx, [rbx+18h]; sesid
0x18004aac2  call    cs:__imp_JetResetSessionContext
0x18004aac8  mov     ebx, eax
0x18004aaca  test    eax, eax
0x18004aacc  jnz     short loc_18004AB4A
0x18004aace  lea     rcx, [rsp+78h+arg_0]
0x18004aad6  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18004aadb  jmp     loc_18004AA0C
0x18004aae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aae7  cmp     rcx, r13
0x18004aaea  jz      short loc_18004AB10
0x18004aaec  test    byte ptr [rcx+6Ch], 4
0x18004aaf0  jz      short loc_18004AB10
0x18004aaf2  cmp     byte ptr [rcx+69h], 1
0x18004aaf6  jb      short loc_18004AB10
0x18004aaf8  mov     rcx, [rcx+60h]
0x18004aafc  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ab03  mov     edx, 29Ch
0x18004ab08  mov     r9d, ebp
0x18004ab0b  call    WPP_SF_d
0x18004ab10  mov     ecx, ebp
0x18004ab12  jmp     short loc_18004AB7C
0x18004ab14  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab1b  cmp     rcx, r13
0x18004ab1e  jz      short loc_18004AB10
0x18004ab20  test    byte ptr [rcx+6Ch], 4
0x18004ab24  jz      short loc_18004AB10
0x18004ab26  cmp     byte ptr [rcx+69h], 1
0x18004ab2a  jb      short loc_18004AB10
0x18004ab2c  mov     rcx, [rcx+60h]
0x18004ab30  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ab37  mov     edx, 29Dh
0x18004ab3c  mov     [rsp+78h+grbit], ebp
0x18004ab40  mov     r9, r15
0x18004ab43  call    WPP_SF_Sd
0x18004ab48  jmp     short loc_18004AB10
0x18004ab4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab51  cmp     rcx, r13
0x18004ab54  jz      short loc_18004AB7A
0x18004ab56  test    byte ptr [rcx+6Ch], 4
0x18004ab5a  jz      short loc_18004AB7A
0x18004ab5c  cmp     byte ptr [rcx+69h], 1
0x18004ab60  jb      short loc_18004AB7A
0x18004ab62  mov     rcx, [rcx+60h]
0x18004ab66  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ab6d  mov     edx, 29Eh
0x18004ab72  mov     r9d, ebx
0x18004ab75  call    WPP_SF_d
0x18004ab7a  mov     ecx, ebx; int
0x18004ab7c  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004ab81  lea     rcx, [rsp+78h+arg_0]
0x18004ab89  mov     esi, eax
0x18004ab8b  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18004ab90  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab97  cmp     rcx, r13
0x18004ab9a  jz      short loc_18004ABC0
0x18004ab9c  test    byte ptr [rcx+6Ch], 4
0x18004aba0  jz      short loc_18004ABC0
0x18004aba2  cmp     byte ptr [rcx+69h], 4
0x18004aba6  jb      short loc_18004ABC0
0x18004aba8  mov     rcx, [rcx+60h]
0x18004abac  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004abb3  mov     edx, 29Fh
0x18004abb8  mov     r9d, esi
0x18004abbb  call    WPP_SF_d
0x18004abc0  lea     rcx, [rsp+78h+var_48]; this
0x18004abc5  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18004abca  lea     r11, [rsp+78h+var_28]
0x18004abcf  mov     eax, esi
0x18004abd1  mov     rbx, [r11+38h]
0x18004abd5  mov     rbp, [r11+40h]
0x18004abd9  mov     rsp, r11
0x18004abdc  pop     r15
0x18004abde  pop     r14
0x18004abe0  pop     r13
0x18004abe2  pop     rdi
0x18004abe3  pop     rsi
0x18004abe4  retn
```

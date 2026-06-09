# CCacheStore::AppCacheCleanup(void)

- ea: `0x1800ad8e0`
- end: `0x1800adc33`
- name: `?AppCacheCleanup@CCacheStore@@AEAAJXZ`
- size: `851`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800aea70`

## callees

- `0x18001f3a4`
- `0x180021360`
- `0x180025910`
- `0x180041020`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800acab8`
- `0x1800ad8e0`
- `0x1800adc3c`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `ESENT!JetMakeKey` at `0x1800ad9c2`
- `ESENT!JetMakeKey` at `0x1800ad9c2`
- `ESENT!JetCommitTransaction` at `0x1800adbb5`
- `ESENT!JetCommitTransaction` at `0x1800adbb5`
- `ESENT!JetRollback` at `0x1800adb1f`
- `ESENT!JetRollback` at `0x1800adb1f`
- `ESENT!JetBeginTransaction` at `0x1800ad990`
- `ESENT!JetBeginTransaction` at `0x1800ad990`
- `ESENT!JetMove` at `0x1800ada39`
- `ESENT!JetMove` at `0x1800ada39`
- `ESENT!JetSeek` at `0x1800ad9e7`
- `ESENT!JetSeek` at `0x1800ad9e7`

## string_xrefs

- `0x1800adac6`: `AppCacheEx_%I64u`

## pseudocode

```c
__int64 __fastcall CCacheStore::AppCacheCleanup(CJetContextList **this)
{
  unsigned __int16 *v1; // r14
  int v3; // eax
  unsigned int v4; // r9d
  JET_SESID *v5; // rsi
  int v6; // ebx
  JET_ERR v7; // eax
  unsigned int v8; // edi
  JET_ERR Key; // eax
  int BasicColumn; // eax
  JET_ERR v11; // eax
  int v12; // r12d
  JET_ERR v13; // eax
  JET_ERR v15; // eax
  struct CJetContext *v16; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+48h] [rbp-31h]
  _QWORD v19[2]; // [rsp+50h] [rbp-29h] BYREF
  int v20; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v21; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 *v22; // [rsp+70h] [rbp-9h] BYREF
  __int64 v23; // [rsp+78h] [rbp-1h]
  int pvData; // [rsp+80h] [rbp+7h] BYREF

  v1 = (unsigned __int16 *)&Data;
  v21 = 0;
  v19[0] = &Data;
  v19[1] = 0;
  v20 = 0;
  v16 = 0;
  pvData = 0;
  v17 = (unsigned __int16 *)&Data;
  v18 = 0;
  v22 = (unsigned __int16 *)&Data;
  v23 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 36, &WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids, this);
  v3 = CJetContextList::AcquireContext(this[55], &v16, 0);
  v5 = (JET_SESID *)v16;
  v6 = v3;
  if ( v3 < 0
    || (v3 = CJetContext::SetCurrentIndex(v16, 2u, L"PartitionTypeIndex", v4), v6 = v3, v3 < 0)
    || (v7 = JetBeginTransaction(v5[2]), v8 = 1, v3 = HRESULTFromJET_ERR(v7, 1), v6 = v3, v3 < 0) )
  {
    v8 = v3;
    goto LABEL_25;
  }
  Key = JetMakeKey(v5[2], v5[4], &pvData, 4u, 1u);
  BasicColumn = HRESULTFromJET_ERR(Key, 1);
  v6 = BasicColumn;
  if ( BasicColumn < 0 )
    goto LABEL_23;
  v11 = JetSeek(v5[2], v5[4], 0x21u);
  if ( v11 == -1601 )
  {
    v6 = 1;
    goto LABEL_24;
  }
  v12 = 1;
  BasicColumn = HRESULTFromJET_ERR(v11, 1);
  v6 = BasicColumn;
  if ( BasicColumn < 0 )
  {
LABEL_23:
    v8 = BasicColumn;
    goto LABEL_24;
  }
  while ( 1 )
  {
    if ( (_DWORD)v18 )
    {
      LODWORD(v18) = 0;
      *v1 = 0;
    }
    if ( (_DWORD)v23 )
    {
      LODWORD(v23) = 0;
      *v22 = 0;
    }
    if ( v12 )
      goto LABEL_16;
    v13 = JetMove(v5[2], v5[4], 1, 0);
    if ( v13 == -1603 )
      break;
    BasicColumn = HRESULTFromJET_ERR(v13, 1);
    v6 = BasicColumn;
    if ( BasicColumn < 0 )
      goto LABEL_23;
LABEL_16:
    BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v5, 0, &v21, 8u);
    v6 = BasicColumn;
    if ( BasicColumn < 0 )
      goto LABEL_23;
    BasicColumn = CJetContext::GetStringColumn((CJetContext *)v5, 4u, (struct CWxString *)&v22);
    v6 = BasicColumn;
    if ( BasicColumn < 0 )
      goto LABEL_23;
    if ( !(_DWORD)v23 )
    {
      v6 = -2147418113;
      v8 = -2147418113;
      goto LABEL_24;
    }
    CCacheStore::AppCacheCleanupObsoletePartition((CCacheStore *)this, v21, v22, (struct CJetContext *)v5, &v20);
    if ( !v20 )
    {
      BasicColumn = CWxString::Format((CWxString *)&v17, L"AppCacheEx_%I64u", v21);
      v6 = BasicColumn;
      if ( BasicColumn < 0 )
        goto LABEL_23;
      v1 = v17;
      CCacheStore::AppCacheCleanupAppCacheTable((CCacheStore *)this, v21, v22, v17);
    }
    v12 = 0;
  }
  v15 = JetCommitTransaction(v5[2], 1u);
  v6 = HRESULTFromJET_ERR(v15, 1);
  v8 = v6;
  if ( v6 >= 0 )
    goto LABEL_25;
LABEL_24:
  JetRollback(v5[2], 0);
LABEL_25:
  if ( v5 )
    CJetContextList::ReleaseContext(this[55], &v16);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 37, &WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids, (unsigned int)v6);
  CWxString::_Release((CWxString *)&v22);
  CWxString::_Release((CWxString *)&v17);
  CWxString::_Release((CWxString *)v19);
  return v8;
}

```

## disassembly

```asm
0x1800ad8e0  push    rbp
0x1800ad8e2  push    rbx
0x1800ad8e3  push    rsi
0x1800ad8e4  push    rdi
0x1800ad8e5  push    r12
0x1800ad8e7  push    r13
0x1800ad8e9  push    r14
0x1800ad8eb  push    r15
0x1800ad8ed  lea     rbp, [rsp-1Fh]
0x1800ad8f2  sub     rsp, 98h
0x1800ad8f9  mov     rax, cs:__security_cookie
0x1800ad900  xor     rax, rsp
0x1800ad903  mov     [rbp+57h+var_48], rax
0x1800ad907  xor     r13d, r13d
0x1800ad90a  lea     r14, Data
0x1800ad911  mov     [rbp+57h+var_9C], r13d
0x1800ad915  mov     r15, rcx
0x1800ad918  mov     [rbp+57h+var_68], r13
0x1800ad91c  mov     [rbp+57h+var_80], r14
0x1800ad920  mov     [rbp+57h+var_78], r13
0x1800ad924  mov     [rbp+57h+var_70], r13d
0x1800ad928  mov     [rbp+57h+var_98], r13
0x1800ad92c  mov     [rbp+57h+pvData], r13d
0x1800ad930  mov     [rbp+57h+var_90], r14
0x1800ad934  mov     [rbp+57h+var_88], r13
0x1800ad938  mov     [rbp+57h+var_60], r14
0x1800ad93c  mov     [rbp+57h+var_58], r13
0x1800ad940  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ad947  jnz     loc_1800ADB78
0x1800ad94d  mov     rcx, [r15+1B8h]; this
0x1800ad954  lea     rdx, [rbp+57h+var_98]; struct CJetContext **
0x1800ad958  xor     r8d, r8d; int *
0x1800ad95b  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ad960  mov     rsi, [rbp+57h+var_98]
0x1800ad964  mov     ebx, eax
0x1800ad966  test    eax, eax
0x1800ad968  js      loc_1800ADB96
0x1800ad96e  lea     r8, aPartitiontypei; "PartitionTypeIndex"
0x1800ad975  mov     edx, 2; unsigned int
0x1800ad97a  mov     rcx, rsi; this
0x1800ad97d  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ad982  mov     ebx, eax
0x1800ad984  test    eax, eax
0x1800ad986  js      loc_1800ADBA1
0x1800ad98c  mov     rcx, [rsi+10h]; sesid
0x1800ad990  call    cs:__imp_JetBeginTransaction
0x1800ad996  mov     edi, 1
0x1800ad99b  mov     ecx, eax; int
0x1800ad99d  mov     edx, edi; int
0x1800ad99f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad9a4  mov     ebx, eax
0x1800ad9a6  test    eax, eax
0x1800ad9a8  js      loc_1800ADB9D
0x1800ad9ae  mov     rdx, [rsi+20h]; tableid
0x1800ad9b2  lea     r9d, [rdi+3]; cbData
0x1800ad9b6  mov     rcx, [rsi+10h]; sesid
0x1800ad9ba  lea     r8, [rbp+57h+pvData]; pvData
0x1800ad9be  mov     [rsp+0D0h+grbit], edi; grbit
0x1800ad9c2  call    cs:__imp_JetMakeKey
0x1800ad9c8  mov     ecx, eax; int
0x1800ad9ca  mov     edx, edi; int
0x1800ad9cc  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad9d1  mov     ebx, eax
0x1800ad9d3  test    eax, eax
0x1800ad9d5  js      loc_1800ADB17
0x1800ad9db  mov     rdx, [rsi+20h]; tableid
0x1800ad9df  lea     r8d, [rdi+20h]; grbit
0x1800ad9e3  mov     rcx, [rsi+10h]; sesid
0x1800ad9e7  call    cs:__imp_JetSeek
0x1800ad9ed  cmp     eax, 0FFFFF9BFh
0x1800ad9f2  jz      loc_1800ADBAA
0x1800ad9f8  mov     edx, edi; int
0x1800ad9fa  mov     ecx, eax; int
0x1800ad9fc  mov     r12d, edi
0x1800ad9ff  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ada04  mov     ebx, eax
0x1800ada06  test    eax, eax
0x1800ada08  js      loc_1800ADB17
0x1800ada0e  cmp     dword ptr [rbp+57h+var_88], r13d
0x1800ada12  jz      short loc_1800ADA1C
0x1800ada14  mov     dword ptr [rbp+57h+var_88], r13d
0x1800ada18  mov     [r14], r13w
0x1800ada1c  cmp     dword ptr [rbp+57h+var_58], r13d
0x1800ada20  jnz     loc_1800ADAFF
0x1800ada26  test    r12d, r12d
0x1800ada29  jnz     short loc_1800ADA5D
0x1800ada2b  mov     rdx, [rsi+20h]; tableid
0x1800ada2f  xor     r9d, r9d; grbit
0x1800ada32  mov     rcx, [rsi+10h]; sesid
0x1800ada36  mov     r8d, edi; cRow
0x1800ada39  call    cs:__imp_JetMove
0x1800ada3f  mov     edx, edi; int
0x1800ada41  cmp     eax, 0FFFFF9BDh
0x1800ada46  jz      loc_1800ADBB1
0x1800ada4c  mov     ecx, eax; int
0x1800ada4e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ada53  mov     ebx, eax
0x1800ada55  test    eax, eax
0x1800ada57  js      loc_1800ADB17
0x1800ada5d  mov     r9d, 8; unsigned int
0x1800ada63  lea     r8, [rbp+57h+var_68]; void *
0x1800ada67  xor     edx, edx; unsigned int
0x1800ada69  mov     rcx, rsi; this
0x1800ada6c  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800ada71  mov     ebx, eax
0x1800ada73  test    eax, eax
0x1800ada75  js      loc_1800ADB10
0x1800ada7b  lea     r8, [rbp+57h+var_60]; struct CWxString *
0x1800ada7f  mov     edx, 4; unsigned int
0x1800ada84  mov     rcx, rsi; this
0x1800ada87  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ada8c  mov     ebx, eax
0x1800ada8e  test    eax, eax
0x1800ada90  js      loc_1800ADBF4
0x1800ada96  cmp     dword ptr [rbp+57h+var_58], r13d
0x1800ada9a  jz      loc_1800ADBE1
0x1800adaa0  mov     r8, [rbp+57h+var_60]; unsigned __int16 *
0x1800adaa4  lea     rax, [rbp+57h+var_70]
0x1800adaa8  mov     rdx, [rbp+57h+var_68]; unsigned __int64
0x1800adaac  mov     r9, rsi; struct CJetContext *
0x1800adaaf  mov     rcx, r15; this
0x1800adab2  mov     qword ptr [rsp+0D0h+grbit], rax; int *
0x1800adab7  call    ?AppCacheCleanupObsoletePartition@CCacheStore@@AEAAJ_KPEBGPEAVCJetContext@@PEAH@Z; CCacheStore::AppCacheCleanupObsoletePartition(unsigned __int64,ushort const *,CJetContext *,int *)
0x1800adabc  cmp     [rbp+57h+var_70], r13d
0x1800adac0  jnz     short loc_1800ADAF7
0x1800adac2  mov     r8, [rbp+57h+var_68]
0x1800adac6  lea     rdx, ?c_wszAppCacheTable@@3QBGB; "AppCacheEx_%I64u"
0x1800adacd  lea     rcx, [rbp+57h+var_90]; this
0x1800adad1  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1800adad6  mov     ebx, eax
0x1800adad8  test    eax, eax
0x1800adada  js      loc_1800ADBD5
0x1800adae0  mov     r14, [rbp+57h+var_90]
0x1800adae4  mov     rcx, r15; this
0x1800adae7  mov     r8, [rbp+57h+var_60]; unsigned __int16 *
0x1800adaeb  mov     r9, r14; unsigned __int16 *
0x1800adaee  mov     rdx, [rbp+57h+var_68]; unsigned __int64
0x1800adaf2  call    ?AppCacheCleanupAppCacheTable@CCacheStore@@AEAAJ_KPEBG1@Z; CCacheStore::AppCacheCleanupAppCacheTable(unsigned __int64,ushort const *,ushort const *)
0x1800adaf7  mov     r12d, r13d
0x1800adafa  jmp     loc_1800ADA0E
0x1800adaff  mov     rax, [rbp+57h+var_60]
0x1800adb03  mov     dword ptr [rbp+57h+var_58], r13d
0x1800adb07  mov     [rax], r13w
0x1800adb0b  jmp     loc_1800ADA26
0x1800adb10  mov     [rbp+57h+var_9C], 3D6h
0x1800adb17  mov     edi, eax
0x1800adb19  mov     rcx, [rsi+10h]; sesid
0x1800adb1d  xor     edx, edx; grbit
0x1800adb1f  call    cs:__imp_JetRollback
0x1800adb25  test    rsi, rsi
0x1800adb28  jnz     loc_1800ADC00
0x1800adb2e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800adb35  jnz     loc_1800ADC15
0x1800adb3b  lea     rcx, [rbp+57h+var_60]; this
0x1800adb3f  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800adb44  lea     rcx, [rbp+57h+var_90]; this
0x1800adb48  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800adb4d  lea     rcx, [rbp+57h+var_80]; this
0x1800adb51  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800adb56  mov     eax, edi
0x1800adb58  mov     rcx, [rbp+57h+var_48]
0x1800adb5c  xor     rcx, rsp; StackCookie
0x1800adb5f  call    __security_check_cookie
0x1800adb64  add     rsp, 98h
0x1800adb6b  pop     r15
0x1800adb6d  pop     r14
0x1800adb6f  pop     r13
0x1800adb71  pop     r12
0x1800adb73  pop     rdi
0x1800adb74  pop     rsi
0x1800adb75  pop     rbx
0x1800adb76  pop     rbp
0x1800adb77  retn
0x1800adb78  mov     edx, 24h ; '$'
0x1800adb7d  lea     r8, WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids
0x1800adb84  mov     ecx, 40Ch
0x1800adb89  mov     r9, r15
0x1800adb8c  call    WPP_SF_q
0x1800adb91  jmp     loc_1800AD94D
0x1800adb96  mov     [rbp+57h+var_9C], 3B3h
0x1800adb9d  mov     edi, eax
0x1800adb9f  jmp     short loc_1800ADB25
0x1800adba1  mov     [rbp+57h+var_9C], 3B5h
0x1800adba8  jmp     short loc_1800ADB9D
0x1800adbaa  mov     ebx, edi
0x1800adbac  jmp     loc_1800ADB19
0x1800adbb1  mov     rcx, [rsi+10h]; sesid
0x1800adbb5  call    cs:__imp_JetCommitTransaction
0x1800adbbb  mov     ecx, eax; int
0x1800adbbd  mov     edx, edi; int
0x1800adbbf  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800adbc4  mov     ebx, eax
0x1800adbc6  mov     edi, eax
0x1800adbc8  test    eax, eax
0x1800adbca  jns     loc_1800ADB25
0x1800adbd0  jmp     loc_1800ADB19
0x1800adbd5  mov     [rbp+57h+var_9C], 3F3h
0x1800adbdc  jmp     loc_1800ADB17
0x1800adbe1  mov     ebx, 8000FFFFh
0x1800adbe6  mov     [rbp+57h+var_9C], 3E0h
0x1800adbed  mov     edi, ebx
0x1800adbef  jmp     loc_1800ADB19
0x1800adbf4  mov     [rbp+57h+var_9C], 3DCh
0x1800adbfb  jmp     loc_1800ADB17
0x1800adc00  mov     rcx, [r15+1B8h]; this
0x1800adc07  lea     rdx, [rbp+57h+var_98]; struct CJetContext **
0x1800adc0b  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800adc10  jmp     loc_1800ADB2E
0x1800adc15  mov     edx, 25h ; '%'
0x1800adc1a  lea     r8, WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids
0x1800adc21  mov     ecx, 40Ch
0x1800adc26  mov     r9d, ebx
0x1800adc29  call    WPP_SF_d
0x1800adc2e  jmp     loc_1800ADB3B
```

# CRepubCacheBackingStore::RemoveRepubCacheStore(ushort *,ulong *)

- ea: `0x18004cde0`
- end: `0x18004d2c8`
- name: `?RemoveRepubCacheStore@CRepubCacheBackingStore@@UEAAKPEAGPEAK@Z`
- size: `1256`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, LPCWSTR lpSrc, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008290`
- `0x18000cf48`
- `0x180015c28`
- `0x180018170`
- `0x180018340`
- `0x180018efc`
- `0x180018f48`
- `0x18004cde0`
- `0x18004f3d4`
- `0x1800525b8`
- `0x180062dd4`
- `0x180114f38`
- `0x180114fd4`
- `0x1801448c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004cf7f`
- `msvcrt!_wcsicmp` at `0x18004cf7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d16e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1dc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004cef5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004cef5`
- `ktmw32!CommitTransaction` at `0x18004d160`
- `ktmw32!CommitTransaction` at `0x18004d160`
- `ktmw32!CreateTransaction` at `0x18004d0a2`
- `ktmw32!CreateTransaction` at `0x18004d0a2`

## string_xrefs

- `0x18004d07b`: `PeerDistTransaction for republication cache mgmt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheBackingStore::RemoveRepubCacheStore(
        CRepubCacheBackingStore *this,
        LPCWSTR lpSrc,
        unsigned int *a3)
{
  __int64 v6; // r9
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // ebx
  DWORD v10; // eax
  DWORD updated; // eax
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // ebx
  char *Transaction; // r15
  DWORD v17; // eax
  const size_t *v19; // rax
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  char *v21; // [rsp+48h] [rbp-B8h]
  _BYTE v22[16]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Dst[264]; // [rsp+270h] [rbp+170h] BYREF

  v20 = &ObjectHandle::`vftable';
  v21 = 0;
  if ( lpSrc && *lpSrc && a3 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 492, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, lpSrc);
    }
    *a3 = 0;
    LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v22, (RTL_SRWLOCK *)this + 2);
    v6 = *((unsigned int *)this + 1968);
    if ( (unsigned int)v6 <= 1 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_14;
      }
      v8 = 493;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v6);
LABEL_14:
      LastError = 774;
      *a3 = 4;
      goto LABEL_69;
    }
    Dst[0] = 0;
    v10 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
    if ( v10 )
    {
      if ( v10 <= 0x104 )
      {
        updated = ConstructBlockDatabasePath(Dst, String2);
        LastError = updated;
        if ( updated )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_69;
          }
          v13 = 495;
        }
        else
        {
          v15 = 0;
          if ( !*((_DWORD *)this + 1968) )
            goto LABEL_58;
          do
          {
            if ( !_wcsicmp((const wchar_t *)this + 384 * v15 + 2026, String2) )
              break;
            ++v15;
          }
          while ( v15 < *((_DWORD *)this + 1968) );
          if ( !v15 )
          {
LABEL_58:
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_14;
            }
            v8 = 496;
            v6 = *((unsigned int *)this + 1968);
            goto LABEL_13;
          }
          if ( v15 >= *((_DWORD *)this + 1968) )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 497, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v15);
            }
            LastError = 1168;
            *a3 = 5;
            goto LABEL_69;
          }
          updated = RemoveRepubStoreSetting(*((struct ITnoCfgMgr **)this + 7), *((_DWORD *)this + 192 * v15 + 1148) - 1);
          LastError = updated;
          if ( updated )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_69;
            }
            v13 = 498;
          }
          else
          {
            updated = CRepubCacheBackingStore::UpdateDatabaseSettings(this, *((struct ITnoCfgMgr **)this + 7), 0);
            LastError = updated;
            if ( updated )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                goto LABEL_69;
              }
              v13 = 499;
            }
            else
            {
              Transaction = (char *)CreateTransaction(
                                      0,
                                      0,
                                      1u,
                                      0,
                                      0,
                                      0,
                                      (LPWSTR)L"PeerDistTransaction for republication cache mgmt");
              ObjectHandle::Close((ObjectHandle *)&v20);
              v21 = Transaction;
              if ( Transaction == (char *)-1LL )
              {
                updated = GetLastError();
                LastError = updated;
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_69;
                }
                v13 = 500;
              }
              else
              {
                v17 = DestroyCacheStore(String2, 0, Transaction, 0, 0x10u);
                LastError = v17;
                if ( v17 )
                {
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 12),
                      501,
                      (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
                      (unsigned int)String2,
                      v17);
                  }
                  goto LABEL_69;
                }
                if ( CommitTransaction(Transaction)
                  || (updated = GetLastError(),
                      LastError = updated,
                      v12 = WPP_GLOBAL_Control,
                      WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control)
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
LABEL_69:
                  LockSentry<ReadersWriterLock,0>::Unlock(v22);
                  v20 = &ObjectHandle::`vftable';
                  ObjectHandle::CloseNoThrow((ObjectHandle *)&v20);
                  return LastError;
                }
                v13 = 502;
              }
            }
          }
        }
        v14 = updated;
LABEL_68:
        WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v14);
        goto LABEL_69;
      }
      LastError = 774;
    }
    else
    {
      LastError = GetLastError();
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_69;
    }
    v13 = 494;
    v14 = LastError;
    goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v19 = (const size_t *)lpSrc;
    if ( !lpSrc )
      v19 = &dword_1801747C4;
    WPP_SF_qSq(*((_QWORD *)WPP_GLOBAL_Control + 12), 491, (_DWORD)a3, (_DWORD)lpSrc, (__int64)v19, (char)a3);
  }
  v20 = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((ObjectHandle *)&v20);
  return 87;
}

```

## disassembly

```asm
0x18004cde0  mov     [rsp-8+arg_18], rbx
0x18004cde5  push    rbp
0x18004cde6  push    r12
0x18004cde8  push    r13
0x18004cdea  push    r14
0x18004cdec  push    r15
0x18004cdee  lea     rbp, [rsp-390h]
0x18004cdf6  sub     rsp, 490h
0x18004cdfd  mov     rax, cs:__security_cookie
0x18004ce04  xor     rax, rsp
0x18004ce07  mov     [rbp+3B0h+var_30], rax
0x18004ce0e  mov     r12, r8
0x18004ce11  mov     rbx, rdx
0x18004ce14  mov     r15, rcx
0x18004ce17  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18004ce1e  mov     [rsp+4B0h+var_470], rax
0x18004ce23  xor     r13d, r13d
0x18004ce26  mov     [rsp+4B0h+var_468], r13
0x18004ce2b  test    rdx, rdx
0x18004ce2e  jz      loc_18004D23A
0x18004ce34  cmp     [rdx], r13w
0x18004ce38  jz      loc_18004D23A
0x18004ce3e  test    r8, r8
0x18004ce41  jz      loc_18004D23A
0x18004ce47  lea     r14, WPP_GLOBAL_Control
0x18004ce4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce55  cmp     rcx, r14
0x18004ce58  jz      short loc_18004CE7E
0x18004ce5a  test    byte ptr [rcx+6Ch], 4
0x18004ce5e  jz      short loc_18004CE7E
0x18004ce60  cmp     byte ptr [rcx+69h], 4
0x18004ce64  jb      short loc_18004CE7E
0x18004ce66  mov     edx, 1ECh
0x18004ce6b  mov     r9, rbx
0x18004ce6e  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ce75  mov     rcx, [rcx+60h]
0x18004ce79  call    WPP_SF_S
0x18004ce7e  mov     [r12], r13d
0x18004ce82  lea     rdx, [r15+10h]
0x18004ce86  lea     rcx, [rsp+4B0h+var_460]
0x18004ce8b  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18004ce90  nop
0x18004ce91  mov     r9d, [r15+1EC0h]
0x18004ce98  cmp     r9d, 1
0x18004ce9c  ja      short loc_18004CEDD
0x18004ce9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cea5  cmp     rcx, r14
0x18004cea8  jz      short loc_18004CECB
0x18004ceaa  test    byte ptr [rcx+6Ch], 4
0x18004ceae  jz      short loc_18004CECB
0x18004ceb0  cmp     byte ptr [rcx+69h], 1
0x18004ceb4  jb      short loc_18004CECB
0x18004ceb6  mov     edx, 1EDh
0x18004cebb  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004cec2  mov     rcx, [rcx+60h]
0x18004cec6  call    WPP_SF_d
0x18004cecb  mov     ebx, 306h
0x18004ced0  mov     dword ptr [r12], 4
0x18004ced8  jmp     loc_18004D215
0x18004cedd  mov     [rbp+3B0h+Dst], r13w
0x18004cee5  mov     r8d, 104h; nSize
0x18004ceeb  lea     rdx, [rbp+3B0h+Dst]; lpDst
0x18004cef2  mov     rcx, rbx; lpSrc
0x18004cef5  call    cs:__imp_ExpandEnvironmentStringsW
0x18004cefb  test    eax, eax
0x18004cefd  jz      loc_18004D1DC
0x18004cf03  cmp     eax, 104h
0x18004cf08  ja      loc_18004D1D5
0x18004cf0e  lea     rdx, [rsp+4B0h+String2]; unsigned __int16 *
0x18004cf13  lea     rcx, [rbp+3B0h+Dst]; unsigned __int16 *
0x18004cf1a  call    ?ConstructBlockDatabasePath@@YAKPEBGPEAG@Z; ConstructBlockDatabasePath(ushort const *,ushort *)
0x18004cf1f  mov     ebx, eax
0x18004cf21  test    eax, eax
0x18004cf23  jz      short loc_18004CF56
0x18004cf25  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf2c  cmp     rcx, r14
0x18004cf2f  jz      loc_18004D215
0x18004cf35  test    byte ptr [rcx+6Ch], 4
0x18004cf39  jz      loc_18004D215
0x18004cf3f  cmp     byte ptr [rcx+69h], 1
0x18004cf43  jb      loc_18004D215
0x18004cf49  mov     edx, 1EFh
0x18004cf4e  mov     r9d, eax
0x18004cf51  jmp     loc_18004D204
0x18004cf56  mov     ebx, r13d
0x18004cf59  cmp     [r15+1EC0h], r13d
0x18004cf60  jbe     loc_18004D1A0
0x18004cf66  lea     r13, [r15+0FD4h]
0x18004cf6d  mov     eax, ebx
0x18004cf6f  lea     rcx, [rax+rax*2]
0x18004cf73  shl     rcx, 8
0x18004cf77  add     rcx, r13; String1
0x18004cf7a  lea     rdx, [rsp+4B0h+String2]; String2
0x18004cf7f  call    cs:__imp__wcsicmp
0x18004cf85  test    eax, eax
0x18004cf87  jz      short loc_18004CF94
0x18004cf89  inc     ebx
0x18004cf8b  cmp     ebx, [r15+1EC0h]
0x18004cf92  jb      short loc_18004CF6D
0x18004cf94  test    ebx, ebx
0x18004cf96  jz      loc_18004D1A0
0x18004cf9c  cmp     ebx, [r15+1EC0h]
0x18004cfa3  jb      short loc_18004CFE7
0x18004cfa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cfac  cmp     rcx, r14
0x18004cfaf  jz      short loc_18004CFD5
0x18004cfb1  test    byte ptr [rcx+6Ch], 4
0x18004cfb5  jz      short loc_18004CFD5
0x18004cfb7  cmp     byte ptr [rcx+69h], 1
0x18004cfbb  jb      short loc_18004CFD5
0x18004cfbd  mov     edx, 1F1h
0x18004cfc2  mov     r9d, ebx
0x18004cfc5  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004cfcc  mov     rcx, [rcx+60h]
0x18004cfd0  call    WPP_SF_d
0x18004cfd5  mov     ebx, 490h
0x18004cfda  mov     dword ptr [r12], 5
0x18004cfe2  jmp     loc_18004D215
0x18004cfe7  mov     eax, ebx
0x18004cfe9  lea     rcx, [rax+rax*2]
0x18004cfed  shl     rcx, 8
0x18004cff1  mov     edx, [rcx+r15+11F0h]
0x18004cff9  dec     edx; unsigned int
0x18004cffb  mov     rcx, [r15+38h]; struct ITnoCfgMgr *
0x18004cfff  call    ?RemoveRepubStoreSetting@@YAKPEAVITnoCfgMgr@@K@Z; RemoveRepubStoreSetting(ITnoCfgMgr *,ulong)
0x18004d004  mov     ebx, eax
0x18004d006  test    eax, eax
0x18004d008  jz      short loc_18004D038
0x18004d00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d011  cmp     rcx, r14
0x18004d014  jz      loc_18004D215
0x18004d01a  test    byte ptr [rcx+6Ch], 4
0x18004d01e  jz      loc_18004D215
0x18004d024  cmp     byte ptr [rcx+69h], 1
0x18004d028  jb      loc_18004D215
0x18004d02e  mov     edx, 1F2h
0x18004d033  jmp     loc_18004CF4E
0x18004d038  xor     r8d, r8d; bool
0x18004d03b  mov     rdx, [r15+38h]; struct ITnoCfgMgr *
0x18004d03f  mov     rcx, r15; this
0x18004d042  call    ?UpdateDatabaseSettings@CRepubCacheBackingStore@@AEAAKPEAVITnoCfgMgr@@_N@Z; CRepubCacheBackingStore::UpdateDatabaseSettings(ITnoCfgMgr *,bool)
0x18004d047  mov     ebx, eax
0x18004d049  test    eax, eax
0x18004d04b  jz      short loc_18004D07B
0x18004d04d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d054  cmp     rcx, r14
0x18004d057  jz      loc_18004D215
0x18004d05d  test    byte ptr [rcx+6Ch], 4
0x18004d061  jz      loc_18004D215
0x18004d067  cmp     byte ptr [rcx+69h], 1
0x18004d06b  jb      loc_18004D215
0x18004d071  mov     edx, 1F3h
0x18004d076  jmp     loc_18004CF4E
0x18004d07b  lea     rax, Description; "PeerDistTransaction for republication c"...
0x18004d082  mov     [rsp+4B0h+Description], rax; Description
0x18004d087  mov     [rsp+4B0h+Timeout], 0; Timeout
0x18004d08f  mov     [rsp+4B0h+IsolationFlags], 0; IsolationFlags
0x18004d097  xor     r9d, r9d; IsolationLevel
0x18004d09a  xor     edx, edx; UOW
0x18004d09c  xor     ecx, ecx; lpTransactionAttributes
0x18004d09e  lea     r8d, [r9+1]; CreateOptions
0x18004d0a2  call    cs:__imp_CreateTransaction
0x18004d0a8  mov     r15, rax
0x18004d0ab  lea     rcx, [rsp+4B0h+var_470]; this
0x18004d0b0  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x18004d0b5  mov     [rsp+4B0h+var_468], r15
0x18004d0ba  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18004d0be  jnz     short loc_18004D0F6
0x18004d0c0  call    cs:__imp_GetLastError
0x18004d0c6  mov     ebx, eax
0x18004d0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0cf  cmp     rcx, r14
0x18004d0d2  jz      loc_18004D215
0x18004d0d8  test    byte ptr [rcx+6Ch], 4
0x18004d0dc  jz      loc_18004D215
0x18004d0e2  cmp     byte ptr [rcx+69h], 1
0x18004d0e6  jb      loc_18004D215
0x18004d0ec  mov     edx, 1F4h
0x18004d0f1  jmp     loc_18004CF4E
0x18004d0f6  mov     [rsp+4B0h+IsolationFlags], 10h; unsigned int
0x18004d0fe  xor     r9d, r9d; bool
0x18004d101  mov     r8, r15; void *
0x18004d104  xor     edx, edx; bool
0x18004d106  lea     rcx, [rsp+4B0h+String2]; unsigned __int16 *
0x18004d10b  call    ?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z; DestroyCacheStore(ushort const *,bool,void *,bool,ulong)
0x18004d110  mov     ebx, eax
0x18004d112  test    eax, eax
0x18004d114  jz      short loc_18004D15D
0x18004d116  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d11d  cmp     rcx, r14
0x18004d120  jz      loc_18004D215
0x18004d126  test    byte ptr [rcx+6Ch], 4
0x18004d12a  jz      loc_18004D215
0x18004d130  cmp     byte ptr [rcx+69h], 1
0x18004d134  jb      loc_18004D215
0x18004d13a  mov     edx, 1F5h
0x18004d13f  mov     [rsp+4B0h+IsolationFlags], eax
0x18004d143  lea     r9, [rsp+4B0h+String2]
0x18004d148  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004d14f  mov     rcx, [rcx+60h]
0x18004d153  call    WPP_SF_Sd
0x18004d158  jmp     loc_18004D215
0x18004d15d  mov     rcx, r15; TransactionHandle
0x18004d160  call    cs:__imp_CommitTransaction
0x18004d166  test    eax, eax
0x18004d168  jnz     loc_18004D215
0x18004d16e  call    cs:__imp_GetLastError
0x18004d174  mov     ebx, eax
0x18004d176  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d17d  cmp     rcx, r14
0x18004d180  jz      loc_18004D215
0x18004d186  test    byte ptr [rcx+6Ch], 4
0x18004d18a  jz      loc_18004D215
0x18004d190  cmp     byte ptr [rcx+69h], 1
0x18004d194  jb      short loc_18004D215
0x18004d196  mov     edx, 1F6h
0x18004d19b  jmp     loc_18004CF4E
0x18004d1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1a7  cmp     rcx, r14
0x18004d1aa  jz      loc_18004CECB
0x18004d1b0  test    byte ptr [rcx+6Ch], 4
0x18004d1b4  jz      loc_18004CECB
0x18004d1ba  cmp     byte ptr [rcx+69h], 1
0x18004d1be  jb      loc_18004CECB
0x18004d1c4  mov     edx, 1F0h
0x18004d1c9  mov     r9d, [r15+1EC0h]
0x18004d1d0  jmp     loc_18004CEBB
0x18004d1d5  mov     ebx, 306h
0x18004d1da  jmp     short loc_18004D1E4
0x18004d1dc  call    cs:__imp_GetLastError
0x18004d1e2  mov     ebx, eax
0x18004d1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1eb  cmp     rcx, r14
0x18004d1ee  jz      short loc_18004D215
0x18004d1f0  test    byte ptr [rcx+6Ch], 4
0x18004d1f4  jz      short loc_18004D215
0x18004d1f6  cmp     byte ptr [rcx+69h], 1
0x18004d1fa  jb      short loc_18004D215
0x18004d1fc  mov     edx, 1EEh
0x18004d201  mov     r9d, ebx
0x18004d204  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004d20b  mov     rcx, [rcx+60h]
0x18004d20f  call    WPP_SF_d
0x18004d214  nop
0x18004d215  lea     rcx, [rsp+4B0h+var_460]
0x18004d21a  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18004d21f  nop
0x18004d220  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18004d227  mov     [rsp+4B0h+var_470], rax
0x18004d22c  lea     rcx, [rsp+4B0h+var_470]; this
0x18004d231  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18004d236  mov     eax, ebx
0x18004d238  jmp     short loc_18004D2A0
0x18004d23a  lea     r14, WPP_GLOBAL_Control
0x18004d241  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d248  cmp     rcx, r14
0x18004d24b  jz      short loc_18004D28C
0x18004d24d  test    byte ptr [rcx+6Ch], 4
0x18004d251  jz      short loc_18004D28C
0x18004d253  cmp     byte ptr [rcx+69h], 1
0x18004d257  jb      short loc_18004D28C
0x18004d259  lea     rdx, dword_1801747C4
0x18004d260  mov     rax, rbx
0x18004d263  test    rbx, rbx
0x18004d266  cmovz   rax, rdx
0x18004d26a  mov     edx, 1EBh
0x18004d26f  mov     qword ptr [rsp+4B0h+Timeout], r12
0x18004d274  mov     qword ptr [rsp+4B0h+IsolationFlags], rax
0x18004d279  mov     r9, rbx
0x18004d27c  mov     rcx, [rcx+60h]
0x18004d280  call    WPP_SF_qSq
0x18004d285  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18004d28c  mov     [rsp+4B0h+var_470], rax
0x18004d291  lea     rcx, [rsp+4B0h+var_470]; this
0x18004d296  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18004d29b  mov     eax, 57h ; 'W'
0x18004d2a0  mov     rcx, [rbp+3B0h+var_30]
0x18004d2a7  xor     rcx, rsp; StackCookie
0x18004d2aa  call    __security_check_cookie
0x18004d2af  mov     rbx, [rsp+4B0h+arg_18]
0x18004d2b7  add     rsp, 490h
0x18004d2be  pop     r15
0x18004d2c0  pop     r14
0x18004d2c2  pop     r13
0x18004d2c4  pop     r12
0x18004d2c6  pop     rbp
0x18004d2c7  retn
```

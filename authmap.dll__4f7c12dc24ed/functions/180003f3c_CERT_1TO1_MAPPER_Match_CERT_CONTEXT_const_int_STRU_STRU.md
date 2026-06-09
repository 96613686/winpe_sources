# CERT_1TO1_MAPPER::Match(_CERT_CONTEXT const *,int *,STRU *,STRU *)

- ea: `0x180003f3c`
- end: `0x1800040bb`
- name: `?Match@CERT_1TO1_MAPPER@@QEAAJPEBU_CERT_CONTEXT@@PEAHPEAVSTRU@@2@Z`
- size: `383`
- prototype: `__int64 __fastcall(CERT_1TO1_MAPPER *this, const struct _CERT_CONTEXT *, int *, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001da0`

## callees

- `0x180001048`
- `0x180001af8`
- `0x180003f3c`
- `0x180006d86`
- `0x180006d92`
- `0x180006dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fc0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f95`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f95`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004027`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000404e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004027`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000404e`
- `iisutil!DecryptMemoryPassword` at `0x18000403d`
- `iisutil!DecryptMemoryPassword` at `0x18000403d`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003fe0`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003fe0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004097`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004097`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180003fb4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180003fb4`

## pseudocode

```c
__int64 __fastcall CERT_1TO1_MAPPER::Match(
        CERT_1TO1_MAPPER *this,
        const struct _CERT_CONTEXT *a2,
        int *a3,
        struct STRU *a4,
        struct STRU *a5)
{
  const unsigned __int16 **v9; // rbx
  int Key; // eax
  __int64 v11; // rdx
  DWORD cbCertEncoded; // eax
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  DWORD pcbData; // [rsp+20h] [rbp-91h] BYREF
  __int64 v17; // [rsp+28h] [rbp-89h] BYREF
  _BYTE v18[32]; // [rsp+30h] [rbp-81h] BYREF
  const unsigned __int16 *v19; // [rsp+50h] [rbp-61h]
  int v20; // [rsp+60h] [rbp-51h]
  _BYTE pvData[24]; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int16 v22[32]; // [rsp+80h] [rbp-31h] BYREF

  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v18, v22, 0x20u);
  pcbData = 20;
  if ( CertGetCertificateContextProperty(a2, 3u, pvData, &pcbData) )
  {
    v17 = 0;
    Key = CLKRHashTable::FindKey(this, pvData, &v17);
    v9 = (const unsigned __int16 **)v17;
    if ( Key
      || (v11 = *(_QWORD *)(v17 + 272), cbCertEncoded = a2->cbCertEncoded, cbCertEncoded == *(_DWORD *)(v11 + 16))
      && memcmp_0(a2->pbCertEncoded, *(const void **)(v11 + 8), cbCertEncoded) )
    {
      *a3 = 0;
    }
    else
    {
      *a3 = 1;
      if ( (int)STRU::Copy(a4, v9[5]) >= 0
        && (int)DecryptMemoryPassword((struct STRU *)(v9 + 16), (struct STRU *)v18) >= 0 )
      {
        STRU::Copy(a5, v19);
      }
    }
  }
  else
  {
    v9 = 0;
    GetLastError();
  }
  if ( v20 )
  {
    v13 = (unsigned int)(2 * v20);
    v14 = v19;
    if ( 2 * v20 )
    {
      do
      {
        *(_BYTE *)v14 = 0;
        v14 = (const unsigned __int16 *)((char *)v14 + 1);
        --v13;
      }
      while ( v13 );
    }
  }
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
  {
    CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE((CERT_1TO1_MAP_RULE *)v9);
    operator delete(v9);
  }
  STRU::~STRU((STRU *)v18);
  return 0;
}

```

## disassembly

```asm
0x180003f3c  push    rbp
0x180003f3e  push    rbx
0x180003f3f  push    rsi
0x180003f40  push    rdi
0x180003f41  push    r14
0x180003f43  push    r15
0x180003f45  lea     rbp, [rsp-27h]
0x180003f4a  sub     rsp, 0D8h
0x180003f51  mov     rax, cs:__security_cookie
0x180003f58  xor     rax, rsp
0x180003f5b  mov     [rbp+4Fh+var_40], rax
0x180003f5f  mov     r14, [rbp+4Fh+arg_20]
0x180003f63  mov     rsi, rdx
0x180003f66  xor     edx, edx; Val
0x180003f68  mov     [rsp+100h+pcbData], 0
0x180003f70  mov     rdi, r8
0x180003f73  mov     rbx, rcx
0x180003f76  lea     rcx, [rbp+4Fh+var_80]; void *
0x180003f7a  mov     r15, r9
0x180003f7d  lea     r8d, [rdx+40h]; Size
0x180003f81  call    memset_0
0x180003f86  mov     r8d, 20h ; ' '
0x180003f8c  lea     rdx, [rbp+4Fh+var_80]
0x180003f90  lea     rcx, [rsp+100h+var_D0]
0x180003f95  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003f9b  lea     r9, [rsp+100h+pcbData]; pcbData
0x180003fa0  mov     [rsp+100h+pcbData], 14h
0x180003fa8  lea     r8, [rbp+4Fh+pvData]; pvData
0x180003fac  mov     edx, 3; dwPropId
0x180003fb1  mov     rcx, rsi; pCertContext
0x180003fb4  call    cs:__imp_CertGetCertificateContextProperty
0x180003fba  test    eax, eax
0x180003fbc  jnz     short loc_180003FCB
0x180003fbe  xor     ebx, ebx
0x180003fc0  call    cs:__imp_GetLastError
0x180003fc6  jmp     loc_180004054
0x180003fcb  lea     r8, [rsp+100h+var_D8]
0x180003fd0  mov     [rsp+100h+var_D8], 0
0x180003fd9  lea     rdx, [rbp+4Fh+pvData]
0x180003fdd  mov     rcx, rbx
0x180003fe0  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180003fe6  mov     rbx, [rsp+100h+var_D8]
0x180003feb  test    eax, eax
0x180003fed  jz      short loc_180003FF7
0x180003fef  mov     dword ptr [rdi], 0
0x180003ff5  jmp     short loc_180004054
0x180003ff7  mov     rdx, [rbx+110h]
0x180003ffe  mov     eax, [rsi+10h]
0x180004001  cmp     eax, [rdx+10h]
0x180004004  jnz     short loc_18000401A
0x180004006  mov     rdx, [rdx+8]; Buf2
0x18000400a  mov     r8d, eax; Size
0x18000400d  mov     rcx, [rsi+8]; Buf1
0x180004011  call    memcmp_0
0x180004016  test    eax, eax
0x180004018  jnz     short loc_180003FEF
0x18000401a  mov     dword ptr [rdi], 1
0x180004020  mov     rcx, r15
0x180004023  mov     rdx, [rbx+28h]
0x180004027  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000402d  test    eax, eax
0x18000402f  js      short loc_180004054
0x180004031  lea     rcx, [rbx+80h]
0x180004038  lea     rdx, [rsp+100h+var_D0]
0x18000403d  call    cs:__imp_?DecryptMemoryPassword@@YAJPEAVSTRU@@0@Z; DecryptMemoryPassword(STRU *,STRU *)
0x180004043  test    eax, eax
0x180004045  js      short loc_180004054
0x180004047  mov     rdx, [rbp+4Fh+var_B0]
0x18000404b  mov     rcx, r14
0x18000404e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004054  mov     eax, [rbp+4Fh+var_A0]
0x180004057  test    eax, eax
0x180004059  jz      short loc_180004071
0x18000405b  add     eax, eax
0x18000405d  mov     ecx, eax
0x18000405f  mov     rax, [rbp+4Fh+var_B0]
0x180004063  jz      short loc_180004071
0x180004065  mov     byte ptr [rax], 0
0x180004068  inc     rax
0x18000406b  sub     rcx, 1
0x18000406f  jnz     short loc_180004065
0x180004071  test    rbx, rbx
0x180004074  jz      short loc_180004092
0x180004076  or      eax, 0FFFFFFFFh
0x180004079  lock xadd [rbx], eax
0x18000407d  cmp     eax, 1
0x180004080  jnz     short loc_180004092
0x180004082  mov     rcx, rbx; this
0x180004085  call    ??1CERT_1TO1_MAP_RULE@@QEAA@XZ; CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE(void)
0x18000408a  mov     rcx, rbx; Block
0x18000408d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004092  lea     rcx, [rsp+100h+var_D0]
0x180004097  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000409d  xor     eax, eax
0x18000409f  mov     rcx, [rbp+4Fh+var_40]
0x1800040a3  xor     rcx, rsp; StackCookie
0x1800040a6  call    __security_check_cookie
0x1800040ab  add     rsp, 0D8h
0x1800040b2  pop     r15
0x1800040b4  pop     r14
0x1800040b6  pop     rdi
0x1800040b7  pop     rsi
0x1800040b8  pop     rbx
0x1800040b9  pop     rbp
0x1800040ba  retn
```

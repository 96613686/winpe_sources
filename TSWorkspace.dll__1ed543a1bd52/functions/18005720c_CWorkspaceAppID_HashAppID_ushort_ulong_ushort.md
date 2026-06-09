# CWorkspaceAppID::HashAppID(ushort *,ulong,ushort * *)

- ea: `0x18005720c`
- end: `0x180057511`
- name: `?HashAppID@CWorkspaceAppID@@IEAAJPEAGKPEAPEAG@Z`
- size: `773`
- prototype: `int(CWorkspaceAppID *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180057700`

## callees

- `0x18000224c`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18005720c`
- `0x180057518`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800574f6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800574f6`
- `ADVAPI32!CryptGetHashParam` at `0x180057350`
- `ADVAPI32!CryptGetHashParam` at `0x180057418`
- `ADVAPI32!CryptGetHashParam` at `0x180057350`
- `ADVAPI32!CryptGetHashParam` at `0x180057418`
- `ADVAPI32!CryptHashData` at `0x1800572f2`
- `ADVAPI32!CryptHashData` at `0x1800572f2`
- `ADVAPI32!CryptCreateHash` at `0x180057270`
- `ADVAPI32!CryptCreateHash` at `0x180057270`
- `ADVAPI32!CryptDestroyHash` at `0x18005724f`
- `ADVAPI32!CryptDestroyHash` at `0x18005724f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005727a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005735a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005727a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005735a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057422`

## pseudocode

```c
__int64 __fastcall CWorkspaceAppID::HashAppID(CWorkspaceAppID *this, const BYTE *a2, int a3, unsigned __int16 **a4)
{
  HCRYPTHASH *phHash; // rbx
  HCRYPTHASH v6; // rcx
  signed int LastError; // ebx
  HCRYPTPROV v11; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  HCRYPTHASH v14; // rcx
  BYTE *v15; // rax
  unsigned __int8 *v16; // rdi
  unsigned int v17; // eax
  CWorkspaceAppID *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // eax
  DWORD pdwDataLen[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD pbData; // [rsp+60h] [rbp+8h] BYREF

  phHash = (HCRYPTHASH *)((char *)this + 64);
  pbData = 0;
  pdwDataLen[0] = 0;
  v6 = *((_QWORD *)this + 8);
  if ( !v6 )
    return (unsigned int)-2147024809;
  CryptDestroyHash(v6);
  v11 = *((_QWORD *)this + 7);
  *phHash = 0;
  if ( !CryptCreateHash(v11, 0x800Cu, 0, 0, phHash) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 21;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_9:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  if ( !CryptHashData(*phHash, a2, 2 * a3, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 22;
    goto LABEL_8;
  }
  v14 = *phHash;
  pdwDataLen[0] = 4;
  if ( !CryptGetHashParam(v14, 4u, (BYTE *)&pbData, pdwDataLen, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 23;
    goto LABEL_8;
  }
  v15 = (BYTE *)operator new[](pbData);
  v16 = v15;
  if ( v15 )
  {
    if ( CryptGetHashParam(*phHash, 2u, v15, &pbData, 0) )
    {
      LastError = CWorkspaceAppID::HashDataToString(v18, v16, pbData, a4);
      if ( LastError < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
          v20,
          (__int64)"Failed to set the pbstrHashedData",
          LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
          v19,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
    operator delete[](v16);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
        v17,
        -2147024882);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005720c  mov     rax, rsp
0x18005720f  mov     [rax+10h], rbx
0x180057213  mov     [rax+18h], rbp
0x180057217  push    rsi
0x180057218  push    rdi
0x180057219  push    r14
0x18005721b  sub     rsp, 40h
0x18005721f  lea     rbx, [rcx+40h]
0x180057223  mov     dword ptr [rax+8], 0
0x18005722a  mov     rdi, rcx
0x18005722d  mov     dword ptr [rax-28h], 0
0x180057234  mov     rcx, [rbx]; hHash
0x180057237  mov     r14, r9
0x18005723a  mov     esi, r8d
0x18005723d  mov     rbp, rdx
0x180057240  test    rcx, rcx
0x180057243  jnz     short loc_18005724F
0x180057245  mov     ebx, 80070057h
0x18005724a  jmp     loc_1800574FC
0x18005724f  call    cs:__imp_CryptDestroyHash
0x180057255  mov     rcx, [rdi+38h]; hProv
0x180057259  xor     r9d, r9d; dwFlags
0x18005725c  xor     r8d, r8d; hKey
0x18005725f  mov     qword ptr [rbx], 0
0x180057266  mov     edx, 800Ch; Algid
0x18005726b  mov     [rsp+58h+phHash], rbx; phHash
0x180057270  call    cs:__imp_CryptCreateHash
0x180057276  test    eax, eax
0x180057278  jnz     short loc_1800572E5
0x18005727a  call    cs:__imp_GetLastError
0x180057280  mov     ebx, eax
0x180057282  mov     rcx, cs:WPP_GLOBAL_Control
0x180057289  lea     rax, WPP_GLOBAL_Control
0x180057290  cmp     rcx, rax
0x180057293  jz      short loc_1800572C9
0x180057295  test    byte ptr [rcx+1Ch], 8
0x180057299  jz      short loc_1800572C9
0x18005729b  cmp     byte ptr [rcx+19h], 2
0x18005729f  jb      short loc_1800572C9
0x1800572a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800572a6  mov     edx, 15h
0x1800572ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572b2  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x1800572b9  mov     r9d, eax
0x1800572bc  mov     dword ptr [rsp+58h+phHash], ebx
0x1800572c0  mov     rcx, [rcx+10h]
0x1800572c4  call    WPP_SF_Dd
0x1800572c9  test    ebx, ebx
0x1800572cb  jle     short loc_1800572D6
0x1800572cd  movzx   ebx, bx
0x1800572d0  or      ebx, 80070000h
0x1800572d6  test    ebx, ebx
0x1800572d8  mov     eax, 80004005h
0x1800572dd  cmovns  ebx, eax
0x1800572e0  jmp     loc_1800574FC
0x1800572e5  mov     rcx, [rbx]; hHash
0x1800572e8  lea     r8d, [rsi+rsi]; dwDataLen
0x1800572ec  xor     r9d, r9d; dwFlags
0x1800572ef  mov     rdx, rbp; pbData
0x1800572f2  call    cs:__imp_CryptHashData
0x1800572f8  test    eax, eax
0x1800572fa  jnz     short loc_180057332
0x1800572fc  call    cs:__imp_GetLastError
0x180057302  mov     ebx, eax
0x180057304  mov     rcx, cs:WPP_GLOBAL_Control
0x18005730b  lea     rax, WPP_GLOBAL_Control
0x180057312  cmp     rcx, rax
0x180057315  jz      short loc_1800572C9
0x180057317  test    byte ptr [rcx+1Ch], 8
0x18005731b  jz      short loc_1800572C9
0x18005731d  cmp     byte ptr [rcx+19h], 2
0x180057321  jb      short loc_1800572C9
0x180057323  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057328  mov     edx, 16h
0x18005732d  jmp     loc_1800572AB
0x180057332  mov     rcx, [rbx]; hHash
0x180057335  lea     r9, [rsp+58h+pdwDataLen]; pdwDataLen
0x18005733a  mov     edx, 4; dwParam
0x18005733f  mov     dword ptr [rsp+58h+phHash], 0; dwFlags
0x180057347  lea     r8, [rsp+58h+pbData]; pbData
0x18005734c  mov     [rsp+58h+pdwDataLen], edx
0x180057350  call    cs:__imp_CryptGetHashParam
0x180057356  test    eax, eax
0x180057358  jnz     short loc_18005739C
0x18005735a  call    cs:__imp_GetLastError
0x180057360  mov     ebx, eax
0x180057362  mov     rcx, cs:WPP_GLOBAL_Control
0x180057369  lea     rax, WPP_GLOBAL_Control
0x180057370  cmp     rcx, rax
0x180057373  jz      loc_1800572C9
0x180057379  test    byte ptr [rcx+1Ch], 8
0x18005737d  jz      loc_1800572C9
0x180057383  cmp     byte ptr [rcx+19h], 2
0x180057387  jb      loc_1800572C9
0x18005738d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057392  mov     edx, 17h
0x180057397  jmp     loc_1800572AB
0x18005739c  mov     ecx, [rsp+58h+pbData]; unsigned __int64
0x1800573a0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800573a5  mov     rdi, rax
0x1800573a8  test    rax, rax
0x1800573ab  jnz     short loc_180057400
0x1800573ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573b4  lea     rax, WPP_GLOBAL_Control
0x1800573bb  cmp     rcx, rax
0x1800573be  jz      short loc_1800573F6
0x1800573c0  test    byte ptr [rcx+1Ch], 8
0x1800573c4  jz      short loc_1800573F6
0x1800573c6  cmp     byte ptr [rcx+19h], 2
0x1800573ca  jb      short loc_1800573F6
0x1800573cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800573d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573d8  lea     edx, [rdi+18h]
0x1800573db  mov     r9d, eax
0x1800573de  mov     dword ptr [rsp+58h+phHash], 8007000Eh
0x1800573e6  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x1800573ed  mov     rcx, [rcx+10h]
0x1800573f1  call    WPP_SF_Dd
0x1800573f6  mov     ebx, 8007000Eh
0x1800573fb  jmp     loc_1800574FC
0x180057400  mov     rcx, [rbx]; hHash
0x180057403  lea     r9, [rsp+58h+pbData]; pdwDataLen
0x180057408  mov     r8, rdi; pbData
0x18005740b  mov     dword ptr [rsp+58h+phHash], 0; dwFlags
0x180057413  mov     edx, 2; dwParam
0x180057418  call    cs:__imp_CryptGetHashParam
0x18005741e  test    eax, eax
0x180057420  jnz     short loc_18005748A
0x180057422  call    cs:__imp_GetLastError
0x180057428  mov     ebx, eax
0x18005742a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057431  lea     rax, WPP_GLOBAL_Control
0x180057438  cmp     rcx, rax
0x18005743b  jz      short loc_180057471
0x18005743d  test    byte ptr [rcx+1Ch], 8
0x180057441  jz      short loc_180057471
0x180057443  cmp     byte ptr [rcx+19h], 2
0x180057447  jb      short loc_180057471
0x180057449  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005744e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057455  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x18005745c  mov     edx, 19h
0x180057461  mov     dword ptr [rsp+58h+phHash], ebx
0x180057465  mov     r9d, eax
0x180057468  mov     rcx, [rcx+10h]
0x18005746c  call    WPP_SF_Dd
0x180057471  test    ebx, ebx
0x180057473  jle     short loc_18005747E
0x180057475  movzx   ebx, bx
0x180057478  or      ebx, 80070000h
0x18005747e  test    ebx, ebx
0x180057480  mov     eax, 80004005h
0x180057485  cmovns  ebx, eax
0x180057488  jmp     short loc_1800574F3
0x18005748a  mov     r8d, [rsp+58h+pbData]; unsigned int
0x18005748f  mov     r9, r14; unsigned __int16 **
0x180057492  mov     rdx, rdi; unsigned __int8 *
0x180057495  call    ?HashDataToString@CWorkspaceAppID@@IEBAJPEAEKPEAPEAG@Z; CWorkspaceAppID::HashDataToString(uchar *,ulong,ushort * *)
0x18005749a  mov     ebx, eax
0x18005749c  test    eax, eax
0x18005749e  jns     short loc_1800574F3
0x1800574a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574a7  lea     rax, WPP_GLOBAL_Control
0x1800574ae  cmp     rcx, rax
0x1800574b1  jz      short loc_1800574F3
0x1800574b3  test    byte ptr [rcx+1Ch], 8
0x1800574b7  jz      short loc_1800574F3
0x1800574b9  cmp     byte ptr [rcx+19h], 2
0x1800574bd  jb      short loc_1800574F3
0x1800574bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800574c4  lea     rcx, aFailedToSetThe; "Failed to set the pbstrHashedData"
0x1800574cb  mov     [rsp+58h+var_30], ebx
0x1800574cf  mov     [rsp+58h+phHash], rcx
0x1800574d4  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x1800574db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574e2  mov     edx, 1Ah
0x1800574e7  mov     r9d, eax
0x1800574ea  mov     rcx, [rcx+10h]
0x1800574ee  call    WPP_SF_DsD
0x1800574f3  mov     rcx, rdi
0x1800574f6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800574fc  mov     rbp, [rsp+58h+arg_10]
0x180057501  mov     eax, ebx
0x180057503  mov     rbx, [rsp+58h+arg_8]
0x180057508  add     rsp, 40h
0x18005750c  pop     r14
0x18005750e  pop     rdi
0x18005750f  pop     rsi
0x180057510  retn
```

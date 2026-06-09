# ABO_WRAPPER::AddBinding(ushort const *)

- ea: `0x18000b178`
- end: `0x18000b3b0`
- name: `?AddBinding@ABO_WRAPPER@@QEAAJPEBG@Z`
- size: `568`
- prototype: `int(ABO_WRAPPER *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180016200`
- `0x1800165d0`

## callees

- `0x180001f90`
- `0x180002990`
- `0x180003460`
- `0x180004048`
- `0x1800047e4`
- `0x18000b178`
- `0x18000f884`
- `0x180028448`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b218`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000b218`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b37c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b386`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b390`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b37c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b386`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b390`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000b1dc`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000b1e6`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000b1dc`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000b1e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b20a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b248`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b26b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2ec`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2f9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b20a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b248`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b26b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2ec`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b2f9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b234`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b256`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b234`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000b256`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1ae`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1b8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1c3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2ba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2c4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2ce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1ae`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1b8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b1c3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2ba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2c4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b2ce`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b320`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000b320`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::AddBinding(ABO_WRAPPER *this, wchar_t *a2)
{
  ABO_WRAPPER *v2; // rsi
  int IPPortFromBinding; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rax
  int Key; // eax
  char *v9; // rdi
  const unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // rax
  char *v13; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v14[56]; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v15[56]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v16[56]; // [rsp+98h] [rbp-11h] BYREF

  v2 = g_pAboWrapper;
  v13 = 0;
  STRU::STRU((STRU *)v16);
  STRU::STRU((STRU *)v15);
  STRU::STRU((STRU *)v14);
  if ( !a2 )
  {
    IPPortFromBinding = -2147024809;
    goto LABEL_19;
  }
  STRU::Reset((STRU *)v16);
  STRU::Reset((STRU *)v15);
  IPPortFromBinding = GetIPPortFromBinding(a2, (struct STRU *)v16, (struct STRU *)v15);
  if ( IPPortFromBinding >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v16);
    IPPortFromBinding = STRU::Copy((STRU *)v14, Str);
    if ( IPPortFromBinding >= 0 )
    {
      IPPortFromBinding = STRU::Append((STRU *)v14, L":");
      if ( IPPortFromBinding >= 0 )
      {
        v6 = STRU::QueryStr((STRU *)v15);
        IPPortFromBinding = STRU::Append((STRU *)v14, v6);
        if ( IPPortFromBinding >= 0 )
        {
          v7 = STRU::QueryStr((STRU *)v14);
          Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)v2 + 152,
                  v7,
                  &v13);
          if ( Key )
          {
            if ( Key != 2 )
            {
              IPPortFromBinding = -2147467259;
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L" Trying to find Binding in Hash returned error %X",
                2147500037LL);
              v9 = v13;
              goto LABEL_17;
            }
            v9 = (char *)operator new(0xB8u);
            if ( !v9 )
            {
              v9 = 0;
              IPPortFromBinding = -2147024888;
              goto LABEL_17;
            }
            *(_QWORD *)v9 = &BINDING_INFO_ENTRY::`vftable';
            STRU::STRU((STRU *)(v9 + 8));
            STRU::STRU((STRU *)(v9 + 64));
            STRU::STRU((STRU *)(v9 + 120));
            *((_DWORD *)v9 + 44) = 0;
            *((_DWORD *)v9 + 45) = 1;
            v10 = STRU::QueryStr((STRU *)v15);
            v11 = STRU::QueryStr((STRU *)v16);
            IPPortFromBinding = BINDING_INFO_ENTRY::Init((BINDING_INFO_ENTRY *)v9, v11, v10);
            if ( IPPortFromBinding < 0 )
              goto LABEL_17;
            if ( (unsigned int)CLKRHashTable::InsertRecord((char *)v2 + 152, v9, 0) )
            {
              IPPortFromBinding = -2147467259;
              goto LABEL_17;
            }
          }
          else
          {
            v9 = v13;
          }
          _InterlockedIncrement((volatile signed __int32 *)v9 + 44);
          IPPortFromBinding = 0;
LABEL_17:
          if ( v9 )
            BINDING_INFO_ENTRY::Release((BINDING_INFO_ENTRY *)v9);
        }
      }
    }
  }
LABEL_19:
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v15);
  STRU::~STRU((STRU *)v16);
  return (unsigned int)IPPortFromBinding;
}

```

## disassembly

```asm
0x18000b178  push    rbp
0x18000b17a  push    rbx
0x18000b17b  push    rsi
0x18000b17c  push    rdi
0x18000b17d  lea     rbp, [rsp-3Fh]
0x18000b182  sub     rsp, 0E8h
0x18000b189  mov     rax, cs:__security_cookie
0x18000b190  xor     rax, rsp
0x18000b193  mov     [rbp+57h+var_30], rax
0x18000b197  mov     rsi, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000b19e  lea     rcx, [rbp+57h+var_68]
0x18000b1a2  mov     rbx, rdx
0x18000b1a5  mov     [rsp+100h+var_E0], 0
0x18000b1ae  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b1b4  lea     rcx, [rbp+57h+var_A0]
0x18000b1b8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b1be  lea     rcx, [rsp+100h+var_D8]
0x18000b1c3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b1c9  test    rbx, rbx
0x18000b1cc  jnz     short loc_18000B1D8
0x18000b1ce  mov     ebx, 80070057h
0x18000b1d3  jmp     loc_18000B377
0x18000b1d8  lea     rcx, [rbp+57h+var_68]
0x18000b1dc  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000b1e2  lea     rcx, [rbp+57h+var_A0]
0x18000b1e6  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000b1ec  lea     r8, [rbp+57h+var_A0]; struct STRU *
0x18000b1f0  mov     rcx, rbx; Str
0x18000b1f3  lea     rdx, [rbp+57h+var_68]; struct STRU *
0x18000b1f7  call    ?GetIPPortFromBinding@@YAJPEBGPEAVSTRU@@1@Z; GetIPPortFromBinding(ushort const *,STRU *,STRU *)
0x18000b1fc  mov     ebx, eax
0x18000b1fe  test    eax, eax
0x18000b200  js      loc_18000B377
0x18000b206  lea     rcx, [rbp+57h+var_68]
0x18000b20a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b210  mov     rdx, rax
0x18000b213  lea     rcx, [rsp+100h+var_D8]
0x18000b218  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b21e  mov     ebx, eax
0x18000b220  test    eax, eax
0x18000b222  js      loc_18000B377
0x18000b228  lea     rdx, asc_180032CE8; ":"
0x18000b22f  lea     rcx, [rsp+100h+var_D8]
0x18000b234  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000b23a  mov     ebx, eax
0x18000b23c  test    eax, eax
0x18000b23e  js      loc_18000B377
0x18000b244  lea     rcx, [rbp+57h+var_A0]
0x18000b248  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b24e  mov     rdx, rax
0x18000b251  lea     rcx, [rsp+100h+var_D8]
0x18000b256  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000b25c  mov     ebx, eax
0x18000b25e  test    eax, eax
0x18000b260  js      loc_18000B377
0x18000b266  lea     rcx, [rsp+100h+var_D8]
0x18000b26b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b271  mov     rdx, rax
0x18000b274  lea     r8, [rsp+100h+var_E0]
0x18000b279  lea     rcx, [rsi+98h]
0x18000b280  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18000b285  test    eax, eax
0x18000b287  jz      loc_18000B35C
0x18000b28d  cmp     eax, 2
0x18000b290  jnz     loc_18000B33A
0x18000b296  mov     ecx, 0B8h; Size
0x18000b29b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b2a0  mov     rdi, rax
0x18000b2a3  test    rax, rax
0x18000b2a6  jz      loc_18000B331
0x18000b2ac  lea     rax, ??_7BINDING_INFO_ENTRY@@6B@; const BINDING_INFO_ENTRY::`vftable'
0x18000b2b3  lea     rcx, [rdi+8]
0x18000b2b7  mov     [rdi], rax
0x18000b2ba  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b2c0  lea     rcx, [rdi+40h]
0x18000b2c4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b2ca  lea     rcx, [rdi+78h]
0x18000b2ce  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b2d4  lea     rcx, [rbp+57h+var_A0]
0x18000b2d8  mov     dword ptr [rdi+0B0h], 0
0x18000b2e2  mov     dword ptr [rdi+0B4h], 1
0x18000b2ec  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b2f2  lea     rcx, [rbp+57h+var_68]
0x18000b2f6  mov     rbx, rax
0x18000b2f9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b2ff  mov     r8, rbx; unsigned __int16 *
0x18000b302  mov     rcx, rdi; this
0x18000b305  mov     rdx, rax; unsigned __int16 *
0x18000b308  call    ?Init@BINDING_INFO_ENTRY@@QEAAJPEBG0@Z; BINDING_INFO_ENTRY::Init(ushort const *,ushort const *)
0x18000b30d  mov     ebx, eax
0x18000b30f  test    eax, eax
0x18000b311  js      short loc_18000B36A
0x18000b313  xor     r8d, r8d
0x18000b316  lea     rcx, [rsi+98h]
0x18000b31d  mov     rdx, rdi
0x18000b320  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000b326  test    eax, eax
0x18000b328  jz      short loc_18000B361
0x18000b32a  mov     ebx, 80004005h
0x18000b32f  jmp     short loc_18000B36A
0x18000b331  xor     edi, edi
0x18000b333  mov     ebx, 80070008h
0x18000b338  jmp     short loc_18000B36A
0x18000b33a  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000b341  lea     rdx, aTryingToFindBi; " Trying to find Binding in Hash returne"...
0x18000b348  mov     ebx, 80004005h
0x18000b34d  mov     r8d, ebx
0x18000b350  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000b355  mov     rdi, [rsp+100h+var_E0]
0x18000b35a  jmp     short loc_18000B36A
0x18000b35c  mov     rdi, [rsp+100h+var_E0]
0x18000b361  lock inc dword ptr [rdi+0B0h]
0x18000b368  xor     ebx, ebx
0x18000b36a  test    rdi, rdi
0x18000b36d  jz      short loc_18000B377
0x18000b36f  mov     rcx, rdi; this
0x18000b372  call    ?Release@BINDING_INFO_ENTRY@@QEAAJXZ; BINDING_INFO_ENTRY::Release(void)
0x18000b377  lea     rcx, [rsp+100h+var_D8]
0x18000b37c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b382  lea     rcx, [rbp+57h+var_A0]
0x18000b386  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b38c  lea     rcx, [rbp+57h+var_68]
0x18000b390  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b396  mov     eax, ebx
0x18000b398  mov     rcx, [rbp+57h+var_30]
0x18000b39c  xor     rcx, rsp; StackCookie
0x18000b39f  call    __security_check_cookie
0x18000b3a4  add     rsp, 0E8h
0x18000b3ab  pop     rdi
0x18000b3ac  pop     rsi
0x18000b3ad  pop     rbx
0x18000b3ae  pop     rbp
0x18000b3af  retn
```

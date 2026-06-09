# ABO_WRAPPER::RemoveBinding(ushort const *)

- ea: `0x18000ef4c`
- end: `0x18000f0fb`
- name: `?RemoveBinding@ABO_WRAPPER@@QEAAJPEBG@Z`
- size: `431`
- prototype: `int(ABO_WRAPPER *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180013ec0`
- `0x1800165d0`

## callees

- `0x180001f90`
- `0x180003460`
- `0x180004048`
- `0x1800047e4`
- `0x18000ef4c`
- `0x18000f918`
- `0x180028448`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000efde`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000efde`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000f0b0`
- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x18000f0b0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000f077`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000f0a0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000f077`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000f0a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0d1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0db`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000efd1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f00d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f02e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000efd1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f00d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f02e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eff9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f01a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000eff9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f01a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef8a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef94`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef9e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef8a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef94`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ef9e`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::RemoveBinding(ABO_WRAPPER *this, wchar_t *a2)
{
  ABO_WRAPPER *v2; // rsi
  signed int IPPortFromBinding; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rax
  int Key; // eax
  BINDING_INFO_ENTRY *v9; // rdi
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rax
  int v13; // [rsp+20h] [rbp-89h] BYREF
  BINDING_INFO_ENTRY *v14; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v15[56]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v16[56]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v17[56]; // [rsp+A0h] [rbp-9h] BYREF

  v2 = g_pAboWrapper;
  v14 = 0;
  v13 = 0;
  STRU::STRU((STRU *)v17);
  STRU::STRU((STRU *)v16);
  STRU::STRU((STRU *)v15);
  if ( a2 )
  {
    IPPortFromBinding = GetIPPortFromBinding(a2, (struct STRU *)v17, (struct STRU *)v16);
    if ( IPPortFromBinding >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v17);
      IPPortFromBinding = STRU::Copy((STRU *)v15, Str);
      if ( IPPortFromBinding >= 0 )
      {
        IPPortFromBinding = STRU::Append((STRU *)v15, L":");
        if ( IPPortFromBinding >= 0 )
        {
          v6 = STRU::QueryStr((STRU *)v16);
          IPPortFromBinding = STRU::Append((STRU *)v15, v6);
          if ( IPPortFromBinding >= 0 )
          {
            v7 = STRU::QueryStr((STRU *)v15);
            Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                    (char *)v2 + 152,
                    v7,
                    &v14);
            v9 = v14;
            if ( Key )
            {
              IPPortFromBinding = Key != 2 ? 0x80004005 : 0;
            }
            else
            {
              IPPortFromBinding = BINDING_INFO_ENTRY::RemoveSiteReference(v14, &v13);
              if ( IPPortFromBinding < 0 )
              {
                v10 = STRU::QueryStr((BINDING_INFO_ENTRY *)((char *)v9 + 120));
                ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Error removing Site Binding for Binding %s\n", v10);
                IPPortFromBinding = 0;
              }
              if ( v13 )
              {
                v11 = STRU::QueryStr((BINDING_INFO_ENTRY *)((char *)v9 + 120));
                CLKRHashTable::DeleteKey((char *)v2 + 152, v11);
              }
            }
            if ( v9 )
              BINDING_INFO_ENTRY::Release(v9);
          }
        }
      }
    }
  }
  else
  {
    IPPortFromBinding = -2147024809;
  }
  STRU::~STRU((STRU *)v15);
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v17);
  return (unsigned int)IPPortFromBinding;
}

```

## disassembly

```asm
0x18000ef4c  push    rbp
0x18000ef4e  push    rbx
0x18000ef4f  push    rsi
0x18000ef50  push    rdi
0x18000ef51  lea     rbp, [rsp-3Fh]
0x18000ef56  sub     rsp, 0E8h
0x18000ef5d  mov     rax, cs:__security_cookie
0x18000ef64  xor     rax, rsp
0x18000ef67  mov     [rbp+57h+var_28], rax
0x18000ef6b  mov     rsi, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000ef72  lea     rcx, [rbp+57h+var_60]
0x18000ef76  mov     rbx, rdx
0x18000ef79  mov     [rsp+100h+var_D8], 0
0x18000ef82  mov     [rsp+100h+var_E0], 0
0x18000ef8a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ef90  lea     rcx, [rbp+57h+var_98]
0x18000ef94  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ef9a  lea     rcx, [rbp+57h+var_D0]
0x18000ef9e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000efa4  test    rbx, rbx
0x18000efa7  jnz     short loc_18000EFB3
0x18000efa9  mov     ebx, 80070057h
0x18000efae  jmp     loc_18000F0C3
0x18000efb3  lea     r8, [rbp+57h+var_98]; struct STRU *
0x18000efb7  mov     rcx, rbx; Str
0x18000efba  lea     rdx, [rbp+57h+var_60]; struct STRU *
0x18000efbe  call    ?GetIPPortFromBinding@@YAJPEBGPEAVSTRU@@1@Z; GetIPPortFromBinding(ushort const *,STRU *,STRU *)
0x18000efc3  mov     ebx, eax
0x18000efc5  test    eax, eax
0x18000efc7  js      loc_18000F0C3
0x18000efcd  lea     rcx, [rbp+57h+var_60]
0x18000efd1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000efd7  mov     rdx, rax
0x18000efda  lea     rcx, [rbp+57h+var_D0]
0x18000efde  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000efe4  mov     ebx, eax
0x18000efe6  test    eax, eax
0x18000efe8  js      loc_18000F0C3
0x18000efee  lea     rdx, asc_180032CE8; ":"
0x18000eff5  lea     rcx, [rbp+57h+var_D0]
0x18000eff9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000efff  mov     ebx, eax
0x18000f001  test    eax, eax
0x18000f003  js      loc_18000F0C3
0x18000f009  lea     rcx, [rbp+57h+var_98]
0x18000f00d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f013  mov     rdx, rax
0x18000f016  lea     rcx, [rbp+57h+var_D0]
0x18000f01a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f020  mov     ebx, eax
0x18000f022  test    eax, eax
0x18000f024  js      loc_18000F0C3
0x18000f02a  lea     rcx, [rbp+57h+var_D0]
0x18000f02e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f034  mov     rdx, rax
0x18000f037  lea     r8, [rsp+100h+var_D8]
0x18000f03c  lea     rcx, [rsi+98h]
0x18000f043  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18000f048  mov     rdi, [rsp+100h+var_D8]
0x18000f04d  test    eax, eax
0x18000f04f  jz      short loc_18000F060
0x18000f051  sub     eax, 2
0x18000f054  neg     eax
0x18000f056  sbb     ebx, ebx
0x18000f058  and     ebx, 80004005h
0x18000f05e  jmp     short loc_18000F0B6
0x18000f060  lea     rdx, [rsp+100h+var_E0]; int *
0x18000f065  mov     rcx, rdi; this
0x18000f068  call    ?RemoveSiteReference@BINDING_INFO_ENTRY@@QEAAJPEAH@Z; BINDING_INFO_ENTRY::RemoveSiteReference(int *)
0x18000f06d  mov     ebx, eax
0x18000f06f  test    eax, eax
0x18000f071  jns     short loc_18000F095
0x18000f073  lea     rcx, [rdi+78h]
0x18000f077  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000f07d  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000f084  lea     rdx, aErrorRemovingS; "Error removing Site Binding for Binding"...
0x18000f08b  mov     r8, rax
0x18000f08e  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000f093  xor     ebx, ebx
0x18000f095  cmp     [rsp+100h+var_E0], 0
0x18000f09a  jz      short loc_18000F0B6
0x18000f09c  lea     rcx, [rdi+78h]
0x18000f0a0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000f0a6  mov     rdx, rax
0x18000f0a9  lea     rcx, [rsi+98h]
0x18000f0b0  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x18000f0b6  test    rdi, rdi
0x18000f0b9  jz      short loc_18000F0C3
0x18000f0bb  mov     rcx, rdi; this
0x18000f0be  call    ?Release@BINDING_INFO_ENTRY@@QEAAJXZ; BINDING_INFO_ENTRY::Release(void)
0x18000f0c3  lea     rcx, [rbp+57h+var_D0]
0x18000f0c7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f0cd  lea     rcx, [rbp+57h+var_98]
0x18000f0d1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f0d7  lea     rcx, [rbp+57h+var_60]
0x18000f0db  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f0e1  mov     eax, ebx
0x18000f0e3  mov     rcx, [rbp+57h+var_28]
0x18000f0e7  xor     rcx, rsp; StackCookie
0x18000f0ea  call    __security_check_cookie
0x18000f0ef  add     rsp, 0E8h
0x18000f0f6  pop     rdi
0x18000f0f7  pop     rsi
0x18000f0f8  pop     rbx
0x18000f0f9  pop     rbp
0x18000f0fa  retn
```

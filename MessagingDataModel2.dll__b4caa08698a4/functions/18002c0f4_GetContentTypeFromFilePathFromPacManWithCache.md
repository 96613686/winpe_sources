# _GetContentTypeFromFilePathFromPacManWithCache

- ea: `0x18002c0f4`
- end: `0x18002c357`
- name: `_GetContentTypeFromFilePathFromPacManWithCache`
- size: `611`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002c870`

## callees

- `0x180004d18`
- `0x180004d60`
- `0x180004dd0`
- `0x18000a730`
- `0x18000b6d4`
- `0x18002bc98`
- `0x18002bd1c`
- `0x18002bd78`
- `0x18002bf6c`
- `0x18002c0f4`
- `0x18002dae4`
- `0x18002e400`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c1e0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c1fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c288`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c1e0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c1fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c288`
- `UserDataPlatformHelperUtil!GetContentTypeFromFilePath` at `0x18002c1b2`
- `UserDataPlatformHelperUtil!GetContentTypeFromFilePath` at `0x18002c1b2`

## pseudocode

```c
__int64 __fastcall GetContentTypeFromFilePathFromPacManWithCache(unsigned __int16 *a1, unsigned __int16 **a2)
{
  _QWORD *v5; // rax
  int ContentTypeFromFilePath; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rax
  __int64 v9; // r8
  int ElementInText; // eax
  int v11; // ecx
  __int64 *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // r8
  int v15; // eax
  int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR pszFirst; // [rsp+40h] [rbp-10h] BYREF

  if ( dword_1800FE904 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800FE904);
    if ( dword_1800FE904 == -1 )
    {
      StringCache::StringCache((StringCache *)qword_1800FE910);
      atexit(_GetContentTypeFromFilePathFromPacManWithCache_::_2_::_dynamic_atexit_destructor_for__s_resultCache__);
      Init_thread_footer(&dword_1800FE904);
    }
  }
  if ( a1 && *a1 == 46 && (unsigned int)StringCache::Find((StringCache *)qword_1800FE910, a1, a2) )
    return 0;
  pszFirst = 0;
  v5 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&pszFirst);
  ContentTypeFromFilePath = GetContentTypeFromFilePath(a1, v5);
  v7 = ContentTypeFromFilePath;
  if ( ContentTypeFromFilePath >= 0 )
  {
    if ( StrStrIW(pszFirst, L"audio") && StrStrIW(pszFirst, L"video") )
    {
      v17 = 0;
      v8 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v17);
      ElementInText = FindElementInText(pszFirst, L"video", v9, v8);
      v7 = ElementInText;
      if ( ElementInText < 0 )
      {
        v11 = ElementInText;
LABEL_14:
        Log_HREvent_11(v11);
        v12 = &v17;
LABEL_15:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(v12);
        goto LABEL_30;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::operator=(
        &pszFirst,
        &v17);
      if ( !pszFirst )
      {
        v7 = -2147024882;
        v11 = -2147024882;
        goto LABEL_14;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v17);
    }
    if ( StrStrIW(pszFirst, L";") )
    {
      v18 = 0;
      v13 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v18);
      v15 = FindElementInText(pszFirst, 0, v14, v13);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = v15;
LABEL_22:
        Log_HREvent_11(v16);
        v12 = &v18;
        goto LABEL_15;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::operator=(
        &pszFirst,
        &v18);
      if ( !pszFirst )
      {
        v7 = -2147024882;
        v16 = -2147024882;
        goto LABEL_22;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v18);
    }
    if ( a1 )
    {
      if ( *a1 == 46 )
        StringCache::Add((StringCache *)qword_1800FE910, a1, (unsigned __int16 *)pszFirst);
    }
    v7 = 0;
    *a2 = (unsigned __int16 *)pszFirst;
    pszFirst = 0;
    goto LABEL_30;
  }
  Log_HREvent_11(ContentTypeFromFilePath);
LABEL_30:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pszFirst);
  return v7;
}

```

## disassembly

```asm
0x18002c0f4  mov     [rsp-18h+arg_10], rbx
0x18002c0f9  push    rbp
0x18002c0fa  push    rsi
0x18002c0fb  push    rdi
0x18002c0fc  mov     rbp, rsp
0x18002c0ff  sub     rsp, 50h
0x18002c103  mov     rax, cs:__security_cookie
0x18002c10a  xor     rax, rsp
0x18002c10d  mov     [rbp+var_8], rax
0x18002c111  mov     rax, gs:58h
0x18002c11a  mov     rdi, rcx
0x18002c11d  mov     ecx, cs:_tls_index
0x18002c123  mov     rsi, rdx
0x18002c126  mov     edx, 4
0x18002c12b  mov     rax, [rax+rcx*8]
0x18002c12f  mov     eax, [rdx+rax]
0x18002c132  cmp     cs:dword_1800FE904, eax
0x18002c138  jle     short loc_18002C173
0x18002c13a  lea     rcx, dword_1800FE904
0x18002c141  call    _Init_thread_header
0x18002c146  cmp     cs:dword_1800FE904, 0FFFFFFFFh
0x18002c14d  jnz     short loc_18002C173
0x18002c14f  lea     rcx, qword_1800FE910; this
0x18002c156  call    ??0StringCache@@QEAA@XZ; StringCache::StringCache(void)
0x18002c15b  lea     rcx, __GetContentTypeFromFilePathFromPacManWithCache____2____dynamic_atexit_destructor_for__s_resultCache__; void (__cdecl *)()
0x18002c162  call    atexit
0x18002c167  lea     rcx, dword_1800FE904
0x18002c16e  call    _Init_thread_footer
0x18002c173  test    rdi, rdi
0x18002c176  jz      short loc_18002C19B
0x18002c178  cmp     word ptr [rdi], 2Eh ; '.'
0x18002c17c  jnz     short loc_18002C19B
0x18002c17e  mov     r8, rsi; unsigned __int16 **
0x18002c181  lea     rcx, qword_1800FE910; this
0x18002c188  mov     rdx, rdi; unsigned __int16 *
0x18002c18b  call    ?Find@StringCache@@QEAAHPEBGPEAPEAG@Z; StringCache::Find(ushort const *,ushort * *)
0x18002c190  test    eax, eax
0x18002c192  jz      short loc_18002C19B
0x18002c194  xor     eax, eax
0x18002c196  jmp     loc_18002C33B
0x18002c19b  lea     rcx, [rbp+pszFirst]
0x18002c19f  mov     [rbp+pszFirst], 0
0x18002c1a7  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18002c1ac  mov     rdx, rax
0x18002c1af  mov     rcx, rdi
0x18002c1b2  call    cs:__imp_GetContentTypeFromFilePath
0x18002c1b8  mov     ebx, eax
0x18002c1ba  test    eax, eax
0x18002c1bc  jns     short loc_18002C1D5
0x18002c1be  mov     edx, 1
0x18002c1c3  mov     r9d, 0C0h
0x18002c1c9  mov     ecx, eax; int
0x18002c1cb  call    Log_HREvent_11
0x18002c1d0  jmp     loc_18002C330
0x18002c1d5  mov     rcx, [rbp+pszFirst]; pszFirst
0x18002c1d9  lea     rdx, pszSrch; "audio"
0x18002c1e0  call    cs:__imp_StrStrIW
0x18002c1e6  test    rax, rax
0x18002c1e9  jz      loc_18002C27D
0x18002c1ef  mov     rcx, [rbp+pszFirst]; pszFirst
0x18002c1f3  lea     rdx, aVideo_1; "video"
0x18002c1fa  call    cs:__imp_StrStrIW
0x18002c200  test    rax, rax
0x18002c203  jz      short loc_18002C27D
0x18002c205  lea     rcx, [rbp+var_20]
0x18002c209  mov     [rbp+var_20], 0
0x18002c211  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18002c216  mov     rcx, [rbp+pszFirst]
0x18002c21a  lea     rdx, aVideo_1; "video"
0x18002c221  mov     r9, rax
0x18002c224  call    _FindElementInText
0x18002c229  mov     ebx, eax
0x18002c22b  test    eax, eax
0x18002c22d  jns     short loc_18002C24F
0x18002c22f  mov     edx, 1
0x18002c234  mov     r9d, 0C6h
0x18002c23a  mov     ecx, eax; int
0x18002c23c  call    Log_HREvent_11
0x18002c241  lea     rcx, [rbp+var_20]
0x18002c245  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c24a  jmp     loc_18002C330
0x18002c24f  lea     rdx, [rbp+var_20]
0x18002c253  lea     rcx, [rbp+pszFirst]
0x18002c257  call    ??4?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::operator=(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &&)
0x18002c25c  cmp     [rbp+pszFirst], 0
0x18002c261  jnz     short loc_18002C274
0x18002c263  mov     ebx, 8007000Eh
0x18002c268  xor     edx, edx
0x18002c26a  mov     ecx, ebx
0x18002c26c  mov     r9d, 0C9h
0x18002c272  jmp     short loc_18002C23C
0x18002c274  lea     rcx, [rbp+var_20]
0x18002c278  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c27d  mov     rcx, [rbp+pszFirst]; pszFirst
0x18002c281  lea     rdx, asc_1800D6C64; ";"
0x18002c288  call    cs:__imp_StrStrIW
0x18002c28e  test    rax, rax
0x18002c291  jz      short loc_18002C301
0x18002c293  lea     rcx, [rbp+var_18]
0x18002c297  mov     [rbp+var_18], 0
0x18002c29f  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18002c2a4  mov     rcx, [rbp+pszFirst]
0x18002c2a8  mov     r9, rax
0x18002c2ab  xor     edx, edx
0x18002c2ad  call    _FindElementInText
0x18002c2b2  mov     ebx, eax
0x18002c2b4  test    eax, eax
0x18002c2b6  jns     short loc_18002C2D3
0x18002c2b8  mov     edx, 1
0x18002c2bd  mov     r9d, 0D0h
0x18002c2c3  mov     ecx, eax; int
0x18002c2c5  call    Log_HREvent_11
0x18002c2ca  lea     rcx, [rbp+var_18]
0x18002c2ce  jmp     loc_18002C245
0x18002c2d3  lea     rdx, [rbp+var_18]
0x18002c2d7  lea     rcx, [rbp+pszFirst]
0x18002c2db  call    ??4?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::operator=(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &&)
0x18002c2e0  cmp     [rbp+pszFirst], 0
0x18002c2e5  jnz     short loc_18002C2F8
0x18002c2e7  mov     ebx, 8007000Eh
0x18002c2ec  xor     edx, edx
0x18002c2ee  mov     ecx, ebx
0x18002c2f0  mov     r9d, 0D3h
0x18002c2f6  jmp     short loc_18002C2C5
0x18002c2f8  lea     rcx, [rbp+var_18]
0x18002c2fc  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c301  test    rdi, rdi
0x18002c304  jz      short loc_18002C31F
0x18002c306  cmp     word ptr [rdi], 2Eh ; '.'
0x18002c30a  jnz     short loc_18002C31F
0x18002c30c  mov     r8, [rbp+pszFirst]; unsigned __int16 *
0x18002c310  lea     rcx, qword_1800FE910; this
0x18002c317  mov     rdx, rdi; unsigned __int16 *
0x18002c31a  call    ?Add@StringCache@@QEAAXPEBGPEAG@Z; StringCache::Add(ushort const *,ushort *)
0x18002c31f  mov     rax, [rbp+pszFirst]
0x18002c323  xor     ebx, ebx
0x18002c325  mov     [rsi], rax
0x18002c328  mov     [rbp+pszFirst], 0
0x18002c330  lea     rcx, [rbp+pszFirst]
0x18002c334  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c339  mov     eax, ebx
0x18002c33b  mov     rcx, [rbp+var_8]
0x18002c33f  xor     rcx, rsp; StackCookie
0x18002c342  call    __security_check_cookie
0x18002c347  mov     rbx, [rsp+50h+arg_10]
0x18002c34f  add     rsp, 50h
0x18002c353  pop     rdi
0x18002c354  pop     rsi
0x18002c355  pop     rbp
0x18002c356  retn
```

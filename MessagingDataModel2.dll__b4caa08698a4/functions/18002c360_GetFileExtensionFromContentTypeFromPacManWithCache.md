# _GetFileExtensionFromContentTypeFromPacManWithCache

- ea: `0x18002c360`
- end: `0x18002c507`
- name: `_GetFileExtensionFromContentTypeFromPacManWithCache`
- size: `423`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ca10`

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
- `0x18002c360`
- `0x18002dae4`
- `0x18002e400`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c441`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18002c441`
- `UserDataPlatformHelperUtil!GetFileExtensionFromContentType` at `0x18002c413`
- `UserDataPlatformHelperUtil!GetFileExtensionFromContentType` at `0x18002c413`

## pseudocode

```c
__int64 __fastcall GetFileExtensionFromContentTypeFromPacManWithCache(unsigned __int16 *a1, unsigned __int16 **a2)
{
  _QWORD *v5; // rax
  int FileExtensionFromContentType; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rax
  __int64 v9; // r8
  int ElementInText; // eax
  int v11; // ecx
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR pszFirst; // [rsp+38h] [rbp-18h] BYREF

  if ( dword_1800FE958 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800FE958);
    if ( dword_1800FE958 == -1 )
    {
      StringCache::StringCache((StringCache *)qword_1800FE960);
      atexit(_GetFileExtensionFromContentTypeFromPacManWithCache_::_2_::_dynamic_atexit_destructor_for__s_resultCache__);
      Init_thread_footer(&dword_1800FE958);
    }
  }
  if ( (unsigned int)StringCache::Find((StringCache *)qword_1800FE960, a1, a2) )
    return 0;
  pszFirst = 0;
  v5 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&pszFirst);
  FileExtensionFromContentType = GetFileExtensionFromContentType(a1, v5);
  v7 = FileExtensionFromContentType;
  if ( FileExtensionFromContentType >= 0 )
  {
    if ( StrStrIW(pszFirst, L";") )
    {
      v12 = 0;
      v8 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v12);
      ElementInText = FindElementInText(pszFirst, 0, v9, v8);
      v7 = ElementInText;
      if ( ElementInText < 0 )
      {
        v11 = ElementInText;
LABEL_11:
        Log_HREvent_11(v11);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v12);
        goto LABEL_16;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::operator=(
        &pszFirst,
        &v12);
      if ( !pszFirst )
      {
        v7 = -2147024882;
        v11 = -2147024882;
        goto LABEL_11;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v12);
    }
    StringCache::Add((StringCache *)qword_1800FE960, a1, (unsigned __int16 *)pszFirst);
    v7 = 0;
    *a2 = (unsigned __int16 *)pszFirst;
    pszFirst = 0;
    goto LABEL_16;
  }
  Log_HREvent_11(FileExtensionFromContentType);
LABEL_16:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&pszFirst);
  return v7;
}

```

## disassembly

```asm
0x18002c360  mov     [rsp-18h+arg_10], rbx
0x18002c365  push    rbp
0x18002c366  push    rsi
0x18002c367  push    rdi
0x18002c368  mov     rbp, rsp
0x18002c36b  sub     rsp, 50h
0x18002c36f  mov     rax, cs:__security_cookie
0x18002c376  xor     rax, rsp
0x18002c379  mov     [rbp+var_10], rax
0x18002c37d  mov     rax, gs:58h
0x18002c386  mov     rdi, rcx
0x18002c389  mov     ecx, cs:_tls_index
0x18002c38f  mov     rsi, rdx
0x18002c392  mov     edx, 4
0x18002c397  mov     rax, [rax+rcx*8]
0x18002c39b  mov     eax, [rdx+rax]
0x18002c39e  cmp     cs:dword_1800FE958, eax
0x18002c3a4  jle     short loc_18002C3DF
0x18002c3a6  lea     rcx, dword_1800FE958
0x18002c3ad  call    _Init_thread_header
0x18002c3b2  cmp     cs:dword_1800FE958, 0FFFFFFFFh
0x18002c3b9  jnz     short loc_18002C3DF
0x18002c3bb  lea     rcx, qword_1800FE960; this
0x18002c3c2  call    ??0StringCache@@QEAA@XZ; StringCache::StringCache(void)
0x18002c3c7  lea     rcx, __GetFileExtensionFromContentTypeFromPacManWithCache____2____dynamic_atexit_destructor_for__s_resultCache__; void (__cdecl *)()
0x18002c3ce  call    atexit
0x18002c3d3  lea     rcx, dword_1800FE958
0x18002c3da  call    _Init_thread_footer
0x18002c3df  mov     r8, rsi; unsigned __int16 **
0x18002c3e2  lea     rcx, qword_1800FE960; this
0x18002c3e9  mov     rdx, rdi; unsigned __int16 *
0x18002c3ec  call    ?Find@StringCache@@QEAAHPEBGPEAPEAG@Z; StringCache::Find(ushort const *,ushort * *)
0x18002c3f1  test    eax, eax
0x18002c3f3  jz      short loc_18002C3FC
0x18002c3f5  xor     eax, eax
0x18002c3f7  jmp     loc_18002C4EB
0x18002c3fc  lea     rcx, [rbp+pszFirst]
0x18002c400  mov     [rbp+pszFirst], 0
0x18002c408  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18002c40d  mov     rdx, rax
0x18002c410  mov     rcx, rdi
0x18002c413  call    cs:__imp_GetFileExtensionFromContentType
0x18002c419  mov     ebx, eax
0x18002c41b  test    eax, eax
0x18002c41d  jns     short loc_18002C436
0x18002c41f  mov     edx, 1
0x18002c424  mov     r9d, 0EFh
0x18002c42a  mov     ecx, eax; int
0x18002c42c  call    Log_HREvent_11
0x18002c431  jmp     loc_18002C4E0
0x18002c436  mov     rcx, [rbp+pszFirst]; pszFirst
0x18002c43a  lea     rdx, asc_1800D6C64; ";"
0x18002c441  call    cs:__imp_StrStrIW
0x18002c447  test    rax, rax
0x18002c44a  jz      short loc_18002C4BC
0x18002c44c  lea     rcx, [rbp+var_20]
0x18002c450  mov     [rbp+var_20], 0
0x18002c458  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x18002c45d  mov     rcx, [rbp+pszFirst]
0x18002c461  mov     r9, rax
0x18002c464  xor     edx, edx
0x18002c466  call    _FindElementInText
0x18002c46b  mov     ebx, eax
0x18002c46d  test    eax, eax
0x18002c46f  jns     short loc_18002C48E
0x18002c471  mov     edx, 1
0x18002c476  mov     r9d, 0F5h
0x18002c47c  mov     ecx, eax; int
0x18002c47e  call    Log_HREvent_11
0x18002c483  lea     rcx, [rbp+var_20]
0x18002c487  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c48c  jmp     short loc_18002C4E0
0x18002c48e  lea     rdx, [rbp+var_20]
0x18002c492  lea     rcx, [rbp+pszFirst]
0x18002c496  call    ??4?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::operator=(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &&)
0x18002c49b  cmp     [rbp+pszFirst], 0
0x18002c4a0  jnz     short loc_18002C4B3
0x18002c4a2  mov     ebx, 8007000Eh
0x18002c4a7  xor     edx, edx
0x18002c4a9  mov     ecx, ebx
0x18002c4ab  mov     r9d, 0F8h
0x18002c4b1  jmp     short loc_18002C47E
0x18002c4b3  lea     rcx, [rbp+var_20]
0x18002c4b7  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c4bc  mov     r8, [rbp+pszFirst]; unsigned __int16 *
0x18002c4c0  lea     rcx, qword_1800FE960; this
0x18002c4c7  mov     rdx, rdi; unsigned __int16 *
0x18002c4ca  call    ?Add@StringCache@@QEAAXPEBGPEAG@Z; StringCache::Add(ushort const *,ushort *)
0x18002c4cf  mov     rax, [rbp+pszFirst]
0x18002c4d3  xor     ebx, ebx
0x18002c4d5  mov     [rsi], rax
0x18002c4d8  mov     [rbp+pszFirst], 0
0x18002c4e0  lea     rcx, [rbp+pszFirst]
0x18002c4e4  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x18002c4e9  mov     eax, ebx
0x18002c4eb  mov     rcx, [rbp+var_10]
0x18002c4ef  xor     rcx, rsp; StackCookie
0x18002c4f2  call    __security_check_cookie
0x18002c4f7  mov     rbx, [rsp+50h+arg_10]
0x18002c4ff  add     rsp, 50h
0x18002c503  pop     rdi
0x18002c504  pop     rsi
0x18002c505  pop     rbp
0x18002c506  retn
```

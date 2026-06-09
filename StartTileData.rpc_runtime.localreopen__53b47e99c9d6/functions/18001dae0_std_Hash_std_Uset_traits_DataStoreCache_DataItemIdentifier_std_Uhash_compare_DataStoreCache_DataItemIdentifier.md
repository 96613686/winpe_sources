# std::_Hash<std::_Uset_traits<DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<DataStoreCache::DataItemIdentifier>,0>>::emplace<ushort const *,uint>(ushort const * &&,uint &&)

- ea: `0x18001dae0`
- end: `0x18001df48`
- name: `??$emplace@PEBGI@?$_Hash@V?$_Uset_traits@VDataItemIdentifier@DataStoreCache@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@VDataItemIdentifier@DataStoreCache@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VDataItemIdentifier@DataStoreCache@@@std@@@std@@@std@@_N@1@$$QEAPEBG$$QEAI@Z`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180044198`

## callees

- `0x18001dac0`
- `0x18001dae0`
- `0x1800471d0`
- `0x1801593b0`
- `0x180201e50`
- `0x1802022fc`
- `0x1802028f0`
- `0x18020be30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001dbdf`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001dbdf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dca4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001debf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dca4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001debf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dcf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001db6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001db6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001db91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dc7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001de3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001de55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001db91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dc7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001de3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001de55`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dcdd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dcdd`

## string_xrefs

- `0x18001dd39`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18001dd54`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Hash<std::_Uset_traits<DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<DataStoreCache::DataItemIdentifier>,0>>::emplace<unsigned short const *,unsigned int>(
        __int64 a1,
        __int64 a2,
        const WCHAR **a3,
        _DWORD *a4)
{
  __int64 **v8; // r13
  char *v9; // rsi
  const WCHAR *v10; // rdi
  HRESULT String; // eax
  wint_t *StringRawBuffer; // rdi
  const char *v13; // r9
  __int64 v14; // rdx
  wint_t *v15; // r12
  wint_t *v16; // rbx
  __int64 v17; // rdi
  unsigned __int64 i; // rcx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 *v21; // rdx
  __int64 *v22; // r13
  const WCHAR *v23; // r12
  const WCHAR *v24; // rax
  __int64 v25; // rcx
  unsigned __int64 v27; // rbx
  __int64 v28; // rcx
  float v29; // xmm0_4
  float v30; // xmm2_4
  float v31; // xmm0_4
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 *v36; // rbx
  __int64 *v37; // r13
  const WCHAR *v38; // r12
  const WCHAR *v39; // rax
  _QWORD *v40; // r8
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 *v43; // r9
  __int64 v44; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  UINT32 v46; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length; // [rsp+34h] [rbp-CCh] BYREF
  UINT32 v48[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+40h] [rbp-C0h]
  char *v50; // [rsp+48h] [rbp-B8h]
  _BYTE v51[768]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v8 = (__int64 **)(a1 + 8);
  v49 = a1 + 8;
  v9 = (char *)operator new(0x18u);
  v50 = v9;
  *(_QWORD *)v48 = v9 + 16;
  LODWORD(a4) = *a4;
  v10 = *a3;
  *((_QWORD *)v9 + 2) = 0;
  WindowsDeleteString(0);
  *((_QWORD *)v9 + 2) = 0;
  String = WindowsCreateString(v10, (UINT32)a4, (HSTRING *)v9 + 2);
  if ( String < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
      (const char *)(unsigned int)String,
      bIgnoreCase);
  length = 0;
  StringRawBuffer = (wint_t *)WindowsGetStringRawBuffer(*((HSTRING *)v9 + 2), &length);
  v14 = 380;
  if ( length > 0x17C )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEC,
      (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
      v13);
  if ( length < 0x17C )
    v14 = length;
  length = v14;
  v15 = (wint_t *)&v51[2 * v14];
  v16 = (wint_t *)v51;
  if ( v51 < (_BYTE *)v15 )
  {
    do
      *v16++ = towupper(*StringRawBuffer++);
    while ( v16 < v15 );
    LODWORD(v14) = length;
  }
  *v15 = 0;
  v17 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 2 * (unsigned __int64)(unsigned int)v14; ++i )
    v17 = 0x100000001B3LL * ((unsigned __int8)v51[i] ^ (unsigned __int64)v17);
  v19 = *(_QWORD *)(a1 + 24);
  v20 = *(__int64 **)(v19 + 16 * (v17 & *(_QWORD *)(a1 + 48)) + 8);
  v21 = *v8;
  if ( v20 == *v8 )
  {
LABEL_17:
    v25 = *(_QWORD *)(a1 + 16);
    if ( v25 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v27 = *(_QWORD *)(a1 + 56);
    v28 = v25 + 1;
    if ( v28 < 0 )
      v29 = (float)(v28 & 1 | (unsigned int)((unsigned __int64)v28 >> 1))
          + (float)(v28 & 1 | (unsigned int)((unsigned __int64)v28 >> 1));
    else
      v29 = (float)(int)v28;
    if ( (v27 & 0x8000000000000000uLL) != 0LL )
    {
      v44 = *(_QWORD *)(a1 + 56) & 1LL | (v27 >> 1);
      v30 = (float)(int)v44 + (float)(int)v44;
    }
    else
    {
      v30 = (float)(int)v27;
    }
    if ( (float)(v29 / v30) > *(float *)a1 )
    {
      v31 = o_ceilf_0(v29 / *(float *)a1);
      v32 = 0;
      if ( v31 >= 9.223372e18 )
      {
        v31 = v31 - 9.223372e18;
        if ( v31 < 9.223372e18 )
          v32 = 0x8000000000000000uLL;
      }
      v33 = v32 + (unsigned int)(int)v31;
      v34 = 8;
      if ( v33 > 8 )
        v34 = v33;
      if ( v27 < v34 )
      {
        if ( v27 >= 0x200 || (v27 *= 8LL, v27 < v34) )
          v27 = v34;
      }
      std::_Hash<std::_Uset_traits<DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<DataStoreCache::DataItemIdentifier>,0>>::_Forced_rehash(
        a1,
        v27);
      v35 = *(_QWORD *)(a1 + 24);
      v36 = *(__int64 **)(v35 + 16 * (v17 & *(_QWORD *)(a1 + 48)) + 8);
      v21 = *v8;
      if ( v36 != *v8 )
      {
        v37 = *(__int64 **)(v35 + 16 * (v17 & *(_QWORD *)(a1 + 48)));
        while ( 1 )
        {
          v46 = 0;
          v38 = WindowsGetStringRawBuffer((HSTRING)v36[2], &v46);
          v48[0] = 0;
          v39 = WindowsGetStringRawBuffer(*((HSTRING *)v9 + 2), v48);
          if ( v48[0] == v46 && (v39 == v38 || CompareStringOrdinal(v39, v48[0], v38, v46, 1) == 2) )
          {
            v21 = (__int64 *)*v36;
            goto LABEL_43;
          }
          if ( v36 == v37 )
            break;
          v36 = (__int64 *)v36[1];
        }
        v21 = v36;
LABEL_43:
        v8 = (__int64 **)(a1 + 8);
      }
    }
    v40 = (_QWORD *)v21[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v9 = v21;
    *((_QWORD *)v9 + 1) = v40;
    *v40 = v9;
    v21[1] = (__int64)v9;
    v41 = 2 * (v17 & *(_QWORD *)(a1 + 48));
    v42 = *(_QWORD *)(a1 + 24);
    v43 = *(__int64 **)(v42 + 16 * (v17 & *(_QWORD *)(a1 + 48)));
    if ( v43 == *v8 )
    {
      *(_QWORD *)(v42 + 16 * (v17 & *(_QWORD *)(a1 + 48))) = v9;
    }
    else
    {
      if ( v43 == v21 )
      {
        *(_QWORD *)(v42 + 16 * (v17 & *(_QWORD *)(a1 + 48))) = v9;
        goto LABEL_26;
      }
      if ( *(_QWORD **)(v42 + 16 * (v17 & *(_QWORD *)(a1 + 48)) + 8) != v40 )
      {
LABEL_26:
        *(_QWORD *)a2 = v9;
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
    }
    *(_QWORD *)(v42 + 8 * v41 + 8) = v9;
    goto LABEL_26;
  }
  v22 = *(__int64 **)(v19 + 16 * (v17 & *(_QWORD *)(a1 + 48)));
  while ( 1 )
  {
    v48[0] = 0;
    v23 = WindowsGetStringRawBuffer((HSTRING)v20[2], v48);
    v46 = 0;
    v24 = WindowsGetStringRawBuffer(*((HSTRING *)v9 + 2), &v46);
    if ( v46 == v48[0] && (v24 == v23 || CompareStringOrdinal(v24, v46, v23, v48[0], 1) == 2) )
      break;
    if ( v20 == v22 )
    {
      v21 = v20;
      v8 = (__int64 **)(a1 + 8);
      goto LABEL_17;
    }
    v20 = (__int64 *)v20[1];
  }
  *(_QWORD *)a2 = v20;
  *(_BYTE *)(a2 + 8) = 0;
  if ( v9 )
  {
    WindowsDeleteString(*((HSTRING *)v9 + 2));
    *((_QWORD *)v9 + 2) = 0;
    operator delete(v9, (const struct std::nothrow_t *)0x18);
  }
  return a2;
}

```

## disassembly

```asm
0x18001dae0  push    rbp
0x18001dae2  push    rbx
0x18001dae3  push    rsi
0x18001dae4  push    rdi
0x18001dae5  push    r12
0x18001dae7  push    r13
0x18001dae9  push    r14
0x18001daeb  push    r15
0x18001daed  lea     rbp, [rsp-268h]
0x18001daf5  sub     rsp, 368h
0x18001dafc  mov     rax, cs:__security_cookie
0x18001db03  xor     rax, rsp
0x18001db06  mov     [rbp+2A0h+var_50], rax
0x18001db0d  mov     rbx, r9
0x18001db10  mov     rdi, r8
0x18001db13  mov     r15, rdx
0x18001db16  mov     r14, rcx
0x18001db19  lea     r13, [rcx+8]
0x18001db1d  mov     [rsp+3A0h+var_360], r13
0x18001db22  mov     [rsp+3A0h+var_358], 0
0x18001db2b  mov     ecx, 18h; Size
0x18001db30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001db35  mov     rsi, rax
0x18001db38  mov     [rsp+3A0h+var_358], rax
0x18001db3d  lea     r12, [rax+10h]
0x18001db41  mov     qword ptr [rsp+3A0h+var_368], r12
0x18001db46  mov     ebx, [rbx]
0x18001db48  mov     rdi, [rdi]
0x18001db4b  mov     qword ptr [r12], 0
0x18001db53  xor     ecx, ecx; string
0x18001db55  call    cs:__imp_WindowsDeleteString
0x18001db5b  mov     qword ptr [r12], 0
0x18001db63  mov     r8, r12; string
0x18001db66  mov     edx, ebx; length
0x18001db68  mov     rcx, rdi; sourceString
0x18001db6b  call    cs:__imp_WindowsCreateString
0x18001db71  mov     rcx, [rbp+2A8h]; this
0x18001db78  test    eax, eax
0x18001db7a  js      loc_18001DD36
0x18001db80  mov     [rsp+3A0h+length], 0
0x18001db88  lea     rdx, [rsp+3A0h+length]; length
0x18001db8d  mov     rcx, [r12]; string
0x18001db91  call    cs:__imp_WindowsGetStringRawBuffer
0x18001db97  mov     rdi, rax
0x18001db9a  mov     r8d, [rsp+3A0h+length]
0x18001db9f  mov     edx, 17Ch
0x18001dba4  cmp     r8d, edx
0x18001dba7  setnbe  al
0x18001dbaa  mov     rcx, [rbp+2A8h]; this
0x18001dbb1  test    al, al
0x18001dbb3  jnz     loc_18001DD54
0x18001dbb9  cmp     r8d, edx
0x18001dbbc  cmovb   edx, r8d
0x18001dbc0  mov     [rsp+3A0h+length], edx
0x18001dbc4  lea     r12, [rsp+3A0h+var_350]
0x18001dbc9  lea     r12, [r12+rdx*2]
0x18001dbcd  lea     rbx, [rsp+3A0h+var_350]
0x18001dbd2  lea     rax, [rsp+3A0h+var_350]
0x18001dbd7  cmp     rax, r12
0x18001dbda  jnb     short loc_18001DBF9
0x18001dbdc  movzx   ecx, word ptr [rdi]; C
0x18001dbdf  call    cs:__imp_towupper
0x18001dbe5  mov     [rbx], ax
0x18001dbe8  lea     rdi, [rdi+2]
0x18001dbec  add     rbx, 2
0x18001dbf0  cmp     rbx, r12
0x18001dbf3  jb      short loc_18001DBDC
0x18001dbf5  mov     edx, [rsp+3A0h+length]
0x18001dbf9  xor     eax, eax
0x18001dbfb  mov     [r12], ax
0x18001dc00  mov     rdi, 0CBF29CE484222325h
0x18001dc0a  mov     r8d, edx
0x18001dc0d  add     r8, r8
0x18001dc10  mov     ecx, eax
0x18001dc12  jz      short loc_18001DC32
0x18001dc14  movzx   eax, [rsp+rcx+3A0h+var_350]
0x18001dc19  xor     rdi, rax
0x18001dc1c  mov     rdx, 100000001B3h
0x18001dc26  imul    rdi, rdx
0x18001dc2a  inc     rcx
0x18001dc2d  cmp     rcx, r8
0x18001dc30  jb      short loc_18001DC14
0x18001dc32  mov     rax, [r14+30h]
0x18001dc36  and     rax, rdi
0x18001dc39  add     rax, rax
0x18001dc3c  mov     rcx, [r14+18h]
0x18001dc40  mov     rbx, [rcx+rax*8+8]
0x18001dc45  mov     rdx, [r13+0]
0x18001dc49  cmp     rbx, rdx
0x18001dc4c  jz      short loc_18001DCBF
0x18001dc4e  mov     r13, [rcx+rax*8]
0x18001dc52  mov     [rsp+3A0h+var_368], 0
0x18001dc5a  lea     rdx, [rsp+3A0h+var_368]; length
0x18001dc5f  mov     rcx, [rbx+10h]; string
0x18001dc63  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dc69  mov     r12, rax
0x18001dc6c  mov     [rsp+3A0h+var_370], 0
0x18001dc74  lea     rdx, [rsp+3A0h+var_370]; length
0x18001dc79  mov     rcx, [rsi+10h]; string
0x18001dc7d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dc83  mov     edx, [rsp+3A0h+var_370]; cchCount1
0x18001dc87  mov     r9d, [rsp+3A0h+var_368]; cchCount2
0x18001dc8c  cmp     edx, r9d
0x18001dc8f  jnz     short loc_18001DCAF
0x18001dc91  cmp     rax, r12
0x18001dc94  jz      short loc_18001DCE4
0x18001dc96  mov     [rsp+3A0h+bIgnoreCase], 1; bIgnoreCase
0x18001dc9e  mov     r8, r12; lpString2
0x18001dca1  mov     rcx, rax; lpString1
0x18001dca4  call    cs:__imp_CompareStringOrdinal
0x18001dcaa  cmp     eax, 2
0x18001dcad  jz      short loc_18001DCE4
0x18001dcaf  cmp     rbx, r13
0x18001dcb2  jnz     loc_18001DD4B
0x18001dcb8  mov     rdx, rbx
0x18001dcbb  lea     r13, [r14+8]
0x18001dcbf  mov     rcx, [r14+10h]
0x18001dcc3  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001dccd  cmp     rcx, rax
0x18001dcd0  jnz     loc_18001DD7B
0x18001dcd6  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001dcdd  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001dce4  mov     [r15], rbx
0x18001dce7  mov     byte ptr [r15+8], 0
0x18001dcec  test    rsi, rsi
0x18001dcef  jz      short loc_18001DD10
0x18001dcf1  mov     rcx, [rsi+10h]; string
0x18001dcf5  call    cs:__imp_WindowsDeleteString
0x18001dcfb  mov     qword ptr [rsi+10h], 0
0x18001dd03  mov     edx, 18h; struct std::nothrow_t *
0x18001dd08  mov     rcx, rsi; void *
0x18001dd0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dd10  mov     rax, r15
0x18001dd13  mov     rcx, [rbp+2A0h+var_50]
0x18001dd1a  xor     rcx, rsp; StackCookie
0x18001dd1d  call    __security_check_cookie
0x18001dd22  add     rsp, 368h
0x18001dd29  pop     r15
0x18001dd2b  pop     r14
0x18001dd2d  pop     r13
0x18001dd2f  pop     r12
0x18001dd31  pop     rdi
0x18001dd32  pop     rsi
0x18001dd33  pop     rbx
0x18001dd34  pop     rbp
0x18001dd35  retn
0x18001dd36  mov     r9d, eax; char *
0x18001dd39  lea     r8, aShellcommonShe_92; "shellcommon\\shell\\DataStoreCache\\inc"...
0x18001dd40  mov     edx, 37h ; '7'; void *
0x18001dd45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dd4b  mov     rbx, [rbx+8]
0x18001dd4f  jmp     loc_18001DC52
0x18001dd54  lea     r8, aShellcommonShe_92; "shellcommon\\shell\\DataStoreCache\\inc"...
0x18001dd5b  mov     edx, 0ECh; void *
0x18001dd60  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001dd66  cmp     [rcx+rax*8+8], r8
0x18001dd6b  jz      loc_18001DEA7
0x18001dd71  mov     [r15], rsi
0x18001dd74  mov     byte ptr [r15+8], 1
0x18001dd79  jmp     short loc_18001DD10
0x18001dd7b  mov     rbx, [r14+38h]
0x18001dd7f  add     rcx, 1
0x18001dd83  xorps   xmm0, xmm0
0x18001dd86  js      loc_18001DF10
0x18001dd8c  cvtsi2ss xmm0, rcx
0x18001dd91  xorps   xmm2, xmm2
0x18001dd94  test    rbx, rbx
0x18001dd97  js      loc_18001DF2A
0x18001dd9d  cvtsi2ss xmm2, rbx
0x18001dda2  movaps  xmm1, xmm0
0x18001dda5  divss   xmm1, xmm2
0x18001dda9  comiss  xmm1, dword ptr [r14]
0x18001ddad  jbe     loc_18001DE75
0x18001ddb3  divss   xmm0, dword ptr [r14]; X
0x18001ddb8  call    _o_ceilf_0
0x18001ddbd  xor     ecx, ecx
0x18001ddbf  movss   xmm1, cs:__real@5f000000
0x18001ddc7  comiss  xmm0, xmm1
0x18001ddca  jb      short loc_18001DDE2
0x18001ddcc  subss   xmm0, xmm1
0x18001ddd0  comiss  xmm0, xmm1
0x18001ddd3  jnb     short loc_18001DDE2
0x18001ddd5  mov     rax, 8000000000000000h
0x18001dddf  mov     rcx, rax
0x18001dde2  cvttss2si rax, xmm0
0x18001dde7  add     rax, rcx
0x18001ddea  mov     ecx, 8
0x18001ddef  cmp     rax, rcx
0x18001ddf2  cmova   rcx, rax
0x18001ddf6  cmp     rbx, rcx
0x18001ddf9  jb      loc_18001DEEA
0x18001ddff  mov     rdx, rbx
0x18001de02  mov     rcx, r14
0x18001de05  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@VDataItemIdentifier@DataStoreCache@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@VDataItemIdentifier@DataStoreCache@@@4@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<DataStoreCache::DataItemIdentifier,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<DataStoreCache::DataItemIdentifier>,0>>::_Forced_rehash(unsigned __int64)
0x18001de0a  mov     rax, [r14+30h]
0x18001de0e  and     rax, rdi
0x18001de11  add     rax, rax
0x18001de14  mov     rcx, [r14+18h]
0x18001de18  mov     rbx, [rcx+rax*8+8]
0x18001de1d  mov     rdx, [r13+0]
0x18001de21  cmp     rbx, rdx
0x18001de24  jz      short loc_18001DE75
0x18001de26  mov     r13, [rcx+rax*8]
0x18001de2a  mov     [rsp+3A0h+var_370], 0
0x18001de32  lea     rdx, [rsp+3A0h+var_370]; length
0x18001de37  mov     rcx, [rbx+10h]; string
0x18001de3b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001de41  mov     r12, rax
0x18001de44  mov     [rsp+3A0h+var_368], 0
0x18001de4c  lea     rdx, [rsp+3A0h+var_368]; length
0x18001de51  mov     rcx, [rsi+10h]; string
0x18001de55  call    cs:__imp_WindowsGetStringRawBuffer
0x18001de5b  mov     edx, [rsp+3A0h+var_368]; cchCount1
0x18001de5f  mov     r9d, [rsp+3A0h+var_370]; cchCount2
0x18001de64  cmp     edx, r9d
0x18001de67  jnz     short loc_18001DECA
0x18001de69  cmp     rax, r12
0x18001de6c  jnz     short loc_18001DEB1
0x18001de6e  mov     rdx, [rbx]
0x18001de71  lea     r13, [r14+8]
0x18001de75  mov     r8, [rdx+8]
0x18001de79  inc     qword ptr [r14+10h]
0x18001de7d  mov     [rsi], rdx
0x18001de80  mov     [rsi+8], r8
0x18001de84  mov     [r8], rsi
0x18001de87  mov     [rdx+8], rsi
0x18001de8b  mov     rax, [r14+30h]
0x18001de8f  and     rax, rdi
0x18001de92  add     rax, rax
0x18001de95  mov     rcx, [r14+18h]
0x18001de99  mov     r9, [rcx+rax*8]
0x18001de9d  cmp     r9, [r13+0]
0x18001dea1  jnz     short loc_18001DED8
0x18001dea3  mov     [rcx+rax*8], rsi
0x18001dea7  mov     [rcx+rax*8+8], rsi
0x18001deac  jmp     loc_18001DD71
0x18001deb1  mov     [rsp+3A0h+bIgnoreCase], 1; bIgnoreCase
0x18001deb9  mov     r8, r12; lpString2
0x18001debc  mov     rcx, rax; lpString1
0x18001debf  call    cs:__imp_CompareStringOrdinal
0x18001dec5  cmp     eax, 2
0x18001dec8  jz      short loc_18001DE6E
0x18001deca  cmp     rbx, r13
0x18001decd  jz      short loc_18001DF08
0x18001decf  mov     rbx, [rbx+8]
0x18001ded3  jmp     loc_18001DE2A
0x18001ded8  cmp     r9, rdx
0x18001dedb  jnz     loc_18001DD66
0x18001dee1  mov     [rcx+rax*8], rsi
0x18001dee5  jmp     loc_18001DD71
0x18001deea  cmp     rbx, 200h
0x18001def1  jnb     short loc_18001DF00
0x18001def3  shl     rbx, 3
0x18001def7  cmp     rbx, rcx
0x18001defa  jnb     loc_18001DDFF
0x18001df00  mov     rbx, rcx
0x18001df03  jmp     loc_18001DDFF
0x18001df08  mov     rdx, rbx
0x18001df0b  jmp     loc_18001DE71
0x18001df10  mov     rax, rcx
0x18001df13  shr     rax, 1
0x18001df16  and     ecx, 1
0x18001df19  or      rax, rcx
0x18001df1c  cvtsi2ss xmm0, rax
0x18001df21  addss   xmm0, xmm0
0x18001df25  jmp     loc_18001DD91
0x18001df2a  mov     rcx, rbx
0x18001df2d  shr     rcx, 1
0x18001df30  mov     rax, rbx
0x18001df33  and     eax, 1
0x18001df36  or      rcx, rax
0x18001df39  cvtsi2ss xmm2, rcx
0x18001df3e  addss   xmm2, xmm2
0x18001df42  jmp     loc_18001DDA2
```

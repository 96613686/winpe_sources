# CreatePath(ushort const *)

- ea: `0x18002efe4`
- end: `0x18002f251`
- name: `?CreatePath@@YAJPEBG@Z`
- size: `621`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800384a0`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x18001f668`
- `0x18001fc40`
- `0x18002efe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1e8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f1d9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f1d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f21e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f21e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002f010`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002f1bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002f010`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002f1bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18002f16d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18002f16d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002f03d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002f03d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreatePath(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rdi
  signed int v2; // esi
  signed int v3; // eax
  PSECURITY_DESCRIPTOR v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  WCHAR *v7; // r8
  unsigned __int16 v8; // cx
  WCHAR *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // r8
  signed int LastError; // eax
  _QWORD *v13; // rdi
  _QWORD *i; // rbx
  const WCHAR *v15; // rsi
  const WCHAR *v16; // rcx
  signed int v17; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v20; // [rsp+28h] [rbp-D8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = a1;
  if ( PathFileExistsW(a1) )
    return 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;ID;FA;;;SY)(A;CIIOID;GA;;;BA)(A;OICI;GA;;;SY)(A;ID;0x1200a9;;;BU)(A;OICIIOID;GXGR;;;BU)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    v4 = SecurityDescriptor;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    memset_0(pszPath, 0, 0x208u);
    v5 = 2147483646;
    v6 = 260;
    v7 = pszPath;
    do
    {
      if ( !v5 )
        break;
      v8 = *v1;
      if ( !*v1 )
        break;
      ++v1;
      *v7++ = v8;
      --v5;
      --v6;
    }
    while ( v6 );
    v2 = v6 == 0 ? 0x8007007A : 0;
    v9 = v7 - 1;
    if ( v6 )
      v9 = v7;
    *v9 = 0;
    if ( !v6 )
      goto LABEL_42;
    v20 = 0;
    v10 = operator new(0x30u);
    *v10 = v10;
    v10[1] = v10;
    *(_QWORD *)&v20 = v10;
    do
    {
      memset(v22, 0, sizeof(v22));
      v11 = -1;
      do
        ++v11;
      while ( pszPath[v11] );
      std::wstring::_Construct<1,unsigned short const *>(v22, pszPath, v11);
      std::list<std::wstring>::_Emplace<std::wstring>(&v20, *(_QWORD *)v20, v22);
      std::wstring::~wstring(v22);
      if ( PathRemoveFileSpecW(pszPath) )
      {
        v2 = 0;
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 >= 0 )
          v2 = -2147467259;
      }
    }
    while ( v2 >= 0 );
    v13 = (_QWORD *)v20;
    for ( i = *(_QWORD **)v20; i != v13; i = (_QWORD *)*i )
    {
      v15 = (const WCHAR *)(i + 2);
      v16 = (const WCHAR *)(i + 2);
      if ( i[5] > 7u )
        v16 = *(const WCHAR **)v15;
      if ( PathFileExistsW(v16) )
      {
        v2 = 0;
      }
      else
      {
        if ( i[5] > 7u )
          v15 = *(const WCHAR **)v15;
        if ( CreateDirectoryW(v15, &SecurityAttributes) )
        {
          v2 = 0;
        }
        else
        {
          v17 = GetLastError();
          v2 = v17;
          if ( v17 > 0 )
            v2 = (unsigned __int16)v17 | 0x80070000;
          if ( v2 >= 0 )
            v2 = -2147467259;
        }
        if ( v2 < 0 )
          break;
      }
    }
    std::list<std::wstring>::~list<std::wstring>(&v20);
  }
  else
  {
    v3 = GetLastError();
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
      v2 = -2147467259;
  }
  v4 = SecurityDescriptor;
LABEL_42:
  if ( v4 )
    LocalFree(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002efe4  push    rbp
0x18002efe6  push    rbx
0x18002efe7  push    rsi
0x18002efe8  push    rdi
0x18002efe9  push    r12
0x18002efeb  push    r15
0x18002efed  lea     rbp, [rsp-198h]
0x18002eff5  sub     rsp, 298h
0x18002effc  mov     rax, cs:__security_cookie
0x18002f003  xor     rax, rsp
0x18002f006  mov     [rbp+1C0h+var_40], rax
0x18002f00d  mov     rdi, rcx
0x18002f010  call    cs:__imp_PathFileExistsW
0x18002f016  xor     r12d, r12d
0x18002f019  test    eax, eax
0x18002f01b  jz      short loc_18002F025
0x18002f01d  mov     esi, r12d
0x18002f020  jmp     loc_18002F224
0x18002f025  mov     [rsp+2C0h+SecurityDescriptor], r12
0x18002f02a  xor     r9d, r9d; SecurityDescriptorSize
0x18002f02d  lea     r8, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x18002f032  lea     edx, [r9+1]; StringSDRevision
0x18002f036  lea     rcx, StringSecurityDescriptor; "D:(A;ID;FA;;;SY)(A;CIIOID;GA;;;BA)(A;OI"...
0x18002f03d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002f043  test    eax, eax
0x18002f045  jnz     short loc_18002F06D
0x18002f047  call    cs:__imp_GetLastError
0x18002f04d  mov     esi, eax
0x18002f04f  test    eax, eax
0x18002f051  jle     short loc_18002F05C
0x18002f053  movzx   esi, ax
0x18002f056  or      esi, 80070000h
0x18002f05c  mov     r15d, 80004005h
0x18002f062  test    esi, esi
0x18002f064  cmovns  esi, r15d
0x18002f068  jmp     loc_18002F211
0x18002f06d  mov     qword ptr [rsp+2C0h+SecurityAttributes.nLength], 18h
0x18002f076  mov     rbx, [rsp+2C0h+SecurityDescriptor]
0x18002f07b  mov     [rsp+2C0h+SecurityAttributes.lpSecurityDescriptor], rbx
0x18002f080  mov     qword ptr [rsp+2C0h+SecurityAttributes.bInheritHandle], r12
0x18002f085  xor     edx, edx; Val
0x18002f087  mov     r8d, 208h; Size
0x18002f08d  lea     rcx, [rsp+2C0h+pszPath]; void *
0x18002f092  call    memset_0
0x18002f097  mov     eax, 7FFFFFFEh
0x18002f09c  mov     edx, 104h
0x18002f0a1  lea     r8, [rsp+2C0h+pszPath]
0x18002f0a6  test    rax, rax
0x18002f0a9  jz      short loc_18002F0C8
0x18002f0ab  movzx   ecx, word ptr [rdi]
0x18002f0ae  test    cx, cx
0x18002f0b1  jz      short loc_18002F0C8
0x18002f0b3  add     rdi, 2
0x18002f0b7  mov     [r8], cx
0x18002f0bb  add     r8, 2
0x18002f0bf  dec     rax
0x18002f0c2  sub     rdx, 1
0x18002f0c6  jnz     short loc_18002F0A6
0x18002f0c8  mov     rax, rdx
0x18002f0cb  neg     rax
0x18002f0ce  sbb     esi, esi
0x18002f0d0  not     esi
0x18002f0d2  and     esi, 8007007Ah
0x18002f0d8  lea     rcx, [r8-2]
0x18002f0dc  test    rdx, rdx
0x18002f0df  cmovnz  rcx, r8
0x18002f0e3  mov     [rcx], r12w
0x18002f0e7  jz      loc_18002F216
0x18002f0ed  xorps   xmm0, xmm0
0x18002f0f0  movdqu  [rsp+2C0h+var_298], xmm0
0x18002f0f6  mov     ecx, 30h ; '0'; Size
0x18002f0fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f100  mov     [rax], rax
0x18002f103  mov     [rax+8], rax
0x18002f107  mov     qword ptr [rsp+2C0h+var_298], rax
0x18002f10c  mov     r15d, 80004005h
0x18002f112  xorps   xmm0, xmm0
0x18002f115  movups  [rsp+2C0h+var_270], xmm0
0x18002f11a  xorps   xmm1, xmm1
0x18002f11d  movdqu  [rsp+2C0h+var_260], xmm1
0x18002f123  lea     rax, [rsp+2C0h+pszPath]
0x18002f128  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f12c  inc     r8
0x18002f12f  cmp     [rax+r8*2], r12w
0x18002f134  jnz     short loc_18002F12C
0x18002f136  lea     rdx, [rsp+2C0h+pszPath]
0x18002f13b  lea     rcx, [rsp+2C0h+var_270]
0x18002f140  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f145  nop
0x18002f146  lea     r8, [rsp+2C0h+var_270]
0x18002f14b  mov     rdx, qword ptr [rsp+2C0h+var_298]
0x18002f150  mov     rdx, [rdx]
0x18002f153  lea     rcx, [rsp+2C0h+var_298]
0x18002f158  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x18002f15d  nop
0x18002f15e  lea     rcx, [rsp+2C0h+var_270]; void *
0x18002f163  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f168  lea     rcx, [rsp+2C0h+pszPath]; pszPath
0x18002f16d  call    cs:__imp_PathRemoveFileSpecW
0x18002f173  test    eax, eax
0x18002f175  jz      short loc_18002F17C
0x18002f177  mov     esi, r12d
0x18002f17a  jmp     short loc_18002F197
0x18002f17c  call    cs:__imp_GetLastError
0x18002f182  mov     esi, eax
0x18002f184  test    eax, eax
0x18002f186  jle     short loc_18002F191
0x18002f188  movzx   esi, ax
0x18002f18b  or      esi, 80070000h
0x18002f191  test    esi, esi
0x18002f193  cmovns  esi, r15d
0x18002f197  test    esi, esi
0x18002f199  jns     loc_18002F112
0x18002f19f  mov     rdi, qword ptr [rsp+2C0h+var_298]
0x18002f1a4  mov     rbx, [rdi]
0x18002f1a7  cmp     rbx, rdi
0x18002f1aa  jz      short loc_18002F207
0x18002f1ac  lea     rsi, [rbx+10h]
0x18002f1b0  mov     rcx, rsi
0x18002f1b3  cmp     qword ptr [rbx+28h], 7
0x18002f1b8  jbe     short loc_18002F1BD
0x18002f1ba  mov     rcx, [rsi]; pszPath
0x18002f1bd  call    cs:__imp_PathFileExistsW
0x18002f1c3  test    eax, eax
0x18002f1c5  jnz     short loc_18002F245
0x18002f1c7  cmp     qword ptr [rsi+18h], 7
0x18002f1cc  jbe     short loc_18002F1D1
0x18002f1ce  mov     rsi, [rsi]
0x18002f1d1  lea     rdx, [rsp+2C0h+SecurityAttributes]; lpSecurityAttributes
0x18002f1d6  mov     rcx, rsi; lpPathName
0x18002f1d9  call    cs:__imp_CreateDirectoryW
0x18002f1df  test    eax, eax
0x18002f1e1  jz      short loc_18002F1E8
0x18002f1e3  mov     esi, r12d
0x18002f1e6  jmp     short loc_18002F203
0x18002f1e8  call    cs:__imp_GetLastError
0x18002f1ee  mov     esi, eax
0x18002f1f0  test    eax, eax
0x18002f1f2  jle     short loc_18002F1FD
0x18002f1f4  movzx   esi, ax
0x18002f1f7  or      esi, 80070000h
0x18002f1fd  test    esi, esi
0x18002f1ff  cmovns  esi, r15d
0x18002f203  test    esi, esi
0x18002f205  jns     short loc_18002F248
0x18002f207  lea     rcx, [rsp+2C0h+var_298]
0x18002f20c  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x18002f211  mov     rbx, [rsp+2C0h+SecurityDescriptor]
0x18002f216  test    rbx, rbx
0x18002f219  jz      short loc_18002F224
0x18002f21b  mov     rcx, rbx; hMem
0x18002f21e  call    cs:__imp_LocalFree
0x18002f224  mov     eax, esi
0x18002f226  mov     rcx, [rbp+1C0h+var_40]
0x18002f22d  xor     rcx, rsp; StackCookie
0x18002f230  call    __security_check_cookie
0x18002f235  add     rsp, 298h
0x18002f23c  pop     r15
0x18002f23e  pop     r12
0x18002f240  pop     rdi
0x18002f241  pop     rsi
0x18002f242  pop     rbx
0x18002f243  pop     rbp
0x18002f244  retn
0x18002f245  mov     esi, r12d
0x18002f248  mov     rbx, [rbx]
0x18002f24b  jmp     loc_18002F1A7
```

# Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand(void)

- ea: `0x180008bbc`
- end: `0x180008da2`
- name: `?BuildHookLaunchCommand@HookProcess@DialogBlocking@Internal@Windows@@AEAA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@XZ`
- size: `486`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800090a0`

## callees

- `0x180001620`
- `0x180001644`
- `0x180001f8c`
- `0x1800020d0`
- `0x18000852c`
- `0x18000884c`
- `0x180008bbc`
- `0x180008ec8`
- `0x180009568`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008cb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180008cb2`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180008c48`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180008cbf`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180008c48`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180008cbf`

## string_xrefs

- `0x180008d90`: `base\embedded\sys\dialogblocking\service\lib\hookmgr.cpp`
- `0x180008d4d`: `%s\rundll32.exe %s\DialogBlockerProc.dll,HookMain`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // r12d
  void *v5; // r14
  unsigned __int64 v6; // rdx
  void *v7; // rbx
  int v8; // edi
  int v9; // ecx
  UINT v10; // esi
  UINT SystemWow64DirectoryW; // eax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdx
  int v14; // ecx
  UINT SystemDirectoryW; // eax
  int v16; // edi
  __int128 *v17; // r9
  __int128 *v18; // r8
  int v19; // eax
  int v21; // [rsp+20h] [rbp-48h]
  void *v22; // [rsp+28h] [rbp-40h]
  __int128 v24; // [rsp+38h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-20h]
  unsigned __int64 v26; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v4 = 260;
  v5 = operator new[](0x208u);
  memset_0(v5, 0, 0x208u);
  v7 = v5;
  v22 = v5;
  v8 = 4;
  v9 = *(_DWORD *)(a1 + 8);
  if ( !v9 )
  {
    SystemWow64DirectoryW = GetSystemWow64DirectoryW((LPWSTR)v5, 0x104u);
LABEL_6:
    v10 = SystemWow64DirectoryW;
    if ( SystemWow64DirectoryW < 0x104 )
      goto LABEL_14;
    v4 = SystemWow64DirectoryW;
    v12 = saturated_mul(SystemWow64DirectoryW, 2u);
    v7 = operator new[](v12);
    memset_0(v7, 0, v12);
    v8 = 12;
    v22 = v7;
    operator delete(v5, v13);
    v14 = *(_DWORD *)(a1 + 8);
    if ( v14 )
    {
      if ( v14 != 1 )
      {
        v10 = 0;
LABEL_13:
        v5 = v7;
        goto LABEL_14;
      }
      SystemDirectoryW = GetSystemDirectoryW((LPWSTR)v7, v10);
    }
    else
    {
      SystemDirectoryW = GetSystemWow64DirectoryW((LPWSTR)v7, v10);
    }
    v10 = SystemDirectoryW;
    goto LABEL_13;
  }
  if ( v9 == 1 )
  {
    SystemWow64DirectoryW = GetSystemDirectoryW((LPWSTR)v5, 0x104u);
    goto LABEL_6;
  }
  v10 = 0;
LABEL_14:
  if ( v10 && v10 < v4 )
  {
    *((_WORD *)v5 + v10) = 0;
    std::wstring::wstring(&v24, v7);
  }
  else
  {
    v24 = 0;
    v25 = 0;
    v26 = 7;
    LOWORD(v24) = 0;
  }
  v16 = v8 | 2;
  if ( v5 )
    operator delete(v7, v6);
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  if ( v26 > 7 )
  {
    v17 = (__int128 *)v24;
    v18 = (__int128 *)v24;
  }
  else
  {
    v17 = &v24;
    v18 = &v24;
  }
  v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          a2,
          L"%s\\rundll32.exe %s\\DialogBlockerProc.dll,HookMain",
          v18,
          v17,
          v16 | 1u,
          v22,
          a2);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"base\\embedded\\sys\\dialogblocking\\service\\lib\\hookmgr.cpp",
      (const char *)(unsigned int)v19,
      v21);
  std::wstring::~wstring(&v24);
  return a2;
}

```

## disassembly

```asm
0x180008bbc  push    rbp
0x180008bbe  push    rbx
0x180008bbf  push    rsi
0x180008bc0  push    rdi
0x180008bc1  push    r12
0x180008bc3  push    r13
0x180008bc5  push    r14
0x180008bc7  push    r15
0x180008bc9  mov     rbp, rsp
0x180008bcc  sub     rsp, 68h
0x180008bd0  mov     rax, cs:__security_cookie
0x180008bd7  xor     rax, rsp
0x180008bda  mov     [rbp+var_10], rax
0x180008bde  mov     r15, rdx
0x180008be1  mov     r13, rcx
0x180008be4  mov     [rbp+var_38], rdx
0x180008be8  mov     [rbp+var_48], 0
0x180008bef  mov     ebx, 208h
0x180008bf4  mov     r12d, 104h
0x180008bfa  mov     ecx, ebx; unsigned __int64
0x180008bfc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008c01  mov     r14, rax
0x180008c04  mov     r8d, ebx; Size
0x180008c07  xor     edx, edx; Val
0x180008c09  mov     rcx, rax; void *
0x180008c0c  call    memset_0
0x180008c11  mov     rbx, r14
0x180008c14  mov     [rbp+var_40], rbx
0x180008c18  mov     edi, 4
0x180008c1d  mov     [rbp+var_48], edi
0x180008c20  mov     ecx, [r13+8]
0x180008c24  test    ecx, ecx
0x180008c26  jz      short loc_180008C42
0x180008c28  cmp     ecx, 1
0x180008c2b  jz      short loc_180008C34
0x180008c2d  xor     esi, esi
0x180008c2f  jmp     loc_180008CCA
0x180008c34  mov     edx, r12d; uSize
0x180008c37  mov     rcx, r14; lpBuffer
0x180008c3a  call    cs:__imp_GetSystemDirectoryW
0x180008c40  jmp     short loc_180008C4E
0x180008c42  mov     edx, r12d; uSize
0x180008c45  mov     rcx, r14; lpBuffer
0x180008c48  call    cs:__imp_GetSystemWow64DirectoryW
0x180008c4e  mov     esi, eax
0x180008c50  cmp     eax, r12d
0x180008c53  jb      short loc_180008CCA
0x180008c55  mov     r12d, eax
0x180008c58  mov     ecx, eax
0x180008c5a  mov     eax, 2
0x180008c5f  mul     rcx
0x180008c62  mov     rdi, rax
0x180008c65  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008c6c  cmovb   rdi, rax
0x180008c70  mov     rcx, rdi; unsigned __int64
0x180008c73  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008c78  mov     rbx, rax
0x180008c7b  mov     r8, rdi; Size
0x180008c7e  xor     edx, edx; Val
0x180008c80  mov     rcx, rax; void *
0x180008c83  call    memset_0
0x180008c88  mov     edi, 0Ch
0x180008c8d  mov     [rbp+var_48], edi
0x180008c90  mov     [rbp+var_40], rbx
0x180008c94  mov     rcx, r14; void *
0x180008c97  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c9c  mov     ecx, [r13+8]
0x180008ca0  test    ecx, ecx
0x180008ca2  jz      short loc_180008CBA
0x180008ca4  cmp     ecx, 1
0x180008ca7  jz      short loc_180008CAD
0x180008ca9  xor     esi, esi
0x180008cab  jmp     short loc_180008CC7
0x180008cad  mov     edx, esi; uSize
0x180008caf  mov     rcx, rbx; lpBuffer
0x180008cb2  call    cs:__imp_GetSystemDirectoryW
0x180008cb8  jmp     short loc_180008CC5
0x180008cba  mov     edx, esi; uSize
0x180008cbc  mov     rcx, rbx; lpBuffer
0x180008cbf  call    cs:__imp_GetSystemWow64DirectoryW
0x180008cc5  mov     esi, eax
0x180008cc7  mov     r14, rbx
0x180008cca  test    esi, esi
0x180008ccc  jz      short loc_180008CEA
0x180008cce  cmp     esi, r12d
0x180008cd1  jnb     short loc_180008CEA
0x180008cd3  mov     ecx, esi
0x180008cd5  xor     eax, eax
0x180008cd7  mov     [r14+rcx*2], ax
0x180008cdc  mov     rdx, rbx
0x180008cdf  lea     rcx, [rbp+var_30]
0x180008ce3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008ce8  jmp     short loc_180008D07
0x180008cea  xorps   xmm0, xmm0
0x180008ced  movups  [rbp+var_30], xmm0
0x180008cf1  mov     [rbp+var_20], 0
0x180008cf9  mov     [rbp+var_18], 7
0x180008d01  xor     eax, eax
0x180008d03  mov     word ptr [rbp+var_30], ax
0x180008d07  or      edi, 2
0x180008d0a  test    r14, r14
0x180008d0d  jz      short loc_180008D18
0x180008d0f  mov     rcx, rbx; void *
0x180008d12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d17  nop
0x180008d18  mov     qword ptr [r15], 0
0x180008d1f  mov     qword ptr [r15+8], 0
0x180008d27  mov     qword ptr [r15+10h], 0
0x180008d2f  or      edi, 1
0x180008d32  mov     [rbp+var_48], edi
0x180008d35  cmp     [rbp+var_18], 7
0x180008d3a  ja      short loc_180008D46
0x180008d3c  lea     r9, [rbp+var_30]
0x180008d40  lea     r8, [rbp+var_30]
0x180008d44  jmp     short loc_180008D4D
0x180008d46  mov     r9, qword ptr [rbp+var_30]
0x180008d4a  mov     r8, r9
0x180008d4d  lea     rdx, ?c_commandLineFormatString@HookProcess@DialogBlocking@Internal@Windows@@0QBGB; "%s\\rundll32.exe %s\\DialogBlockerProc."...
0x180008d54  mov     rcx, r15
0x180008d57  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180008d5c  mov     rcx, [rbp+40h]; this
0x180008d60  test    eax, eax
0x180008d62  js      short loc_180008D8D
0x180008d64  lea     rcx, [rbp+var_30]
0x180008d68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d6d  mov     rax, r15
0x180008d70  mov     rcx, [rbp+var_10]
0x180008d74  xor     rcx, rsp; StackCookie
0x180008d77  call    __security_check_cookie
0x180008d7c  add     rsp, 68h
0x180008d80  pop     r15
0x180008d82  pop     r14
0x180008d84  pop     r13
0x180008d86  pop     r12
0x180008d88  pop     rdi
0x180008d89  pop     rsi
0x180008d8a  pop     rbx
0x180008d8b  pop     rbp
0x180008d8c  retn
0x180008d8d  mov     r9d, eax; char *
0x180008d90  lea     r8, aBaseEmbeddedSy_0; "base\\embedded\\sys\\dialogblocking\\se"...
0x180008d97  mov     edx, 2Eh ; '.'; void *
0x180008d9c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

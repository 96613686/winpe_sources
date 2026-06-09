# GenerateOutFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_DB *,ulong)

- ea: `0x18001df98`
- end: `0x18001e21d`
- name: `?GenerateOutFilePath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@PEAU_DB@@K@Z`
- size: `645`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001e440`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000b720`
- `0x18000c190`
- `0x18000dfd8`
- `0x18000e064`
- `0x18001df98`
- `0x1800543c0`
- `0x1800545f8`
- `0x18005da34`
- `0x18005de60`
- `0x180065150`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001e106`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001e106`
- `KERNEL32!GetLastError` at `0x18001e110`
- `KERNEL32!GetLastError` at `0x18001e110`

## string_xrefs

- `0x18001e05c`: `GenerateOutFilePath`
- `0x18001e0a1`: `GenerateOutFilePath`
- `0x18001e136`: `GenerateOutFilePath`
- `0x18001e0c8`: `%WinDir%\Temp`
- `0x18001e0de`: `%WinDir%\Temp`
- `0x18001e129`: `Error Enviroment variables for Filepath. [0x%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GenerateOutFilePath(WCHAR *Src, void *a2, __int64 a3, unsigned int a4)
{
  wchar_t *v8; // r15
  unsigned int FirstTag; // eax
  int v10; // eax
  WCHAR *v11; // rbx
  const WCHAR *v12; // rcx
  signed int LastError; // eax
  unsigned int v14; // ebx
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rsi
  __int64 v17; // rbx
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[128]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+D0h] [rbp-30h] BYREF

  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  memset_0(Dst, 0, 0x208u);
  v8 = L"{Empty}";
  if ( a4 )
  {
    if ( a3 )
    {
      FirstTag = SdbFindFirstTag(a3, a4, 36868);
      if ( FirstTag )
      {
        if ( (unsigned int)SdbReadBinaryTag(a3, FirstTag, &v19, 16) )
        {
          v10 = AslGuidToString(v20, 64, &v19);
          if ( v10 < 0 )
            AslLogCallPrintf(
              3,
              "GenerateOutFilePath",
              166,
              "Failed to convert GUID to string. [0x%x]",
              v10 | 0x10000000);
          else
            v8 = (wchar_t *)v20;
        }
        else
        {
          AslLogCallPrintf(3, "GenerateOutFilePath", 151, "Couldn't get GUID from Sdb Entry.");
        }
      }
    }
  }
  if ( *((_QWORD *)Src + 3) < 0xDu )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
  }
  else
  {
    v11 = *(WCHAR **)Src;
    *((_QWORD *)Src + 2) = 13;
    memmove_0(v11, L"%WinDir%\\Temp", 0x1Au);
    v11[13] = 0;
  }
  if ( *((_QWORD *)Src + 3) <= 7u )
    v12 = Src;
  else
    v12 = *(const WCHAR **)Src;
  if ( ExpandEnvironmentStringsW(v12, Dst, 0x104u) )
  {
    v15 = -1;
    do
      ++v15;
    while ( Dst[v15] );
    if ( v15 > *((_QWORD *)Src + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
    }
    else
    {
      if ( *((_QWORD *)Src + 3) <= 7u )
        v16 = Src;
      else
        v16 = *(WCHAR **)Src;
      *((_QWORD *)Src + 2) = v15;
      v17 = v15;
      memmove_0(v16, Dst, 2 * v15);
      v16[v17] = 0;
    }
    std::wstring::append(Src, (void *)L"\\");
    std::wstring::append(Src, L"InboxUtilityMP_");
    std::wstring::append(Src, v8);
    std::wstring::append(Src, L"_");
    std::wstring::append(Src);
    std::wstring::append(Src, L".txt");
    v14 = 0;
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    AslLogCallPrintf(1, "GenerateOutFilePath", 180, "Error Enviroment variables for Filepath. [0x%x]", v14);
  }
  std::wstring::~wstring(a2);
  return v14;
}

```

## disassembly

```asm
0x18001df98  push    rbp
0x18001df9a  push    rbx
0x18001df9b  push    rsi
0x18001df9c  push    rdi
0x18001df9d  push    r12
0x18001df9f  push    r14
0x18001dfa1  push    r15
0x18001dfa3  lea     rbp, [rsp-1F0h]
0x18001dfab  sub     rsp, 2F0h
0x18001dfb2  mov     [rsp+320h+var_2F0], 0FFFFFFFFFFFFFFFEh
0x18001dfbb  mov     rax, cs:__security_cookie
0x18001dfc2  xor     rax, rsp
0x18001dfc5  mov     [rbp+220h+var_40], rax
0x18001dfcc  mov     esi, r9d
0x18001dfcf  mov     rbx, r8
0x18001dfd2  mov     r14, rdx
0x18001dfd5  mov     rdi, rcx
0x18001dfd8  mov     [rsp+320h+var_2E8], rdx
0x18001dfdd  xorps   xmm0, xmm0
0x18001dfe0  movups  [rsp+320h+var_2E0], xmm0
0x18001dfe5  xor     edx, edx; Val
0x18001dfe7  mov     r8d, 80h; Size
0x18001dfed  lea     rcx, [rsp+320h+var_2D0]; void *
0x18001dff2  call    memset_0
0x18001dff7  xor     edx, edx; Val
0x18001dff9  mov     r8d, 208h; Size
0x18001dfff  lea     rcx, [rbp+220h+Dst]; void *
0x18001e003  call    memset_0
0x18001e008  lea     r15, aEmpty; "{Empty}"
0x18001e00f  xor     r12d, r12d
0x18001e012  test    esi, esi
0x18001e014  jz      loc_18001E0B2
0x18001e01a  test    rbx, rbx
0x18001e01d  jz      loc_18001E0B2
0x18001e023  mov     r8d, 9004h
0x18001e029  mov     edx, esi
0x18001e02b  mov     rcx, rbx
0x18001e02e  call    SdbFindFirstTag
0x18001e033  test    eax, eax
0x18001e035  jz      short loc_18001E0B2
0x18001e037  lea     r9d, [r12+10h]
0x18001e03c  lea     r8, [rsp+320h+var_2E0]
0x18001e041  mov     edx, eax
0x18001e043  mov     rcx, rbx
0x18001e046  call    SdbReadBinaryTag
0x18001e04b  test    eax, eax
0x18001e04d  jnz     short loc_18001E06D
0x18001e04f  lea     r9, aCouldnTGetGuid; "Couldn't get GUID from Sdb Entry."
0x18001e056  mov     r8d, 97h
0x18001e05c  lea     rdx, aGenerateoutfil; "GenerateOutFilePath"
0x18001e063  lea     ecx, [rax+3]
0x18001e066  call    AslLogCallPrintf
0x18001e06b  jmp     short loc_18001E0B2
0x18001e06d  lea     r8, [rsp+320h+var_2E0]
0x18001e072  mov     edx, 40h ; '@'
0x18001e077  lea     rcx, [rsp+320h+var_2D0]
0x18001e07c  call    AslGuidToString
0x18001e081  test    eax, eax
0x18001e083  js      short loc_18001E08C
0x18001e085  lea     r15, [rsp+320h+var_2D0]
0x18001e08a  jmp     short loc_18001E0B2
0x18001e08c  bts     eax, 1Ch
0x18001e090  mov     [rsp+320h+var_300], eax
0x18001e094  lea     r9, aFailedToConver_20; "Failed to convert GUID to string. [0x%x"...
0x18001e09b  mov     r8d, 0A6h
0x18001e0a1  lea     rdx, aGenerateoutfil; "GenerateOutFilePath"
0x18001e0a8  mov     ecx, 3
0x18001e0ad  call    AslLogCallPrintf
0x18001e0b2  mov     edx, 0Dh
0x18001e0b7  cmp     [rdi+18h], rdx
0x18001e0bb  jb      short loc_18001E0DE
0x18001e0bd  mov     rbx, [rdi]
0x18001e0c0  mov     [rdi+10h], rdx
0x18001e0c4  lea     r8d, [rdx+0Dh]; Size
0x18001e0c8  lea     rdx, aWindirTemp; "%WinDir%\\Temp"
0x18001e0cf  mov     rcx, rbx; void *
0x18001e0d2  call    memmove_0
0x18001e0d7  mov     [rbx+1Ah], r12w
0x18001e0dc  jmp     short loc_18001E0ED
0x18001e0de  lea     r9, aWindirTemp; "%WinDir%\\Temp"
0x18001e0e5  mov     rcx, rdi
0x18001e0e8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001e0ed  cmp     qword ptr [rdi+18h], 7
0x18001e0f2  jbe     short loc_18001E0F9
0x18001e0f4  mov     rcx, [rdi]
0x18001e0f7  jmp     short loc_18001E0FC
0x18001e0f9  mov     rcx, rdi; lpSrc
0x18001e0fc  mov     r8d, 104h; nSize
0x18001e102  lea     rdx, [rbp+220h+Dst]; lpDst
0x18001e106  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e10c  test    eax, eax
0x18001e10e  jnz     short loc_18001E14C
0x18001e110  call    cs:__imp_GetLastError
0x18001e116  mov     ebx, eax
0x18001e118  test    eax, eax
0x18001e11a  jle     short loc_18001E125
0x18001e11c  movzx   ebx, ax
0x18001e11f  or      ebx, 80070000h
0x18001e125  mov     [rsp+320h+var_300], ebx
0x18001e129  lea     r9, aErrorEnviromen; "Error Enviroment variables for Filepath"...
0x18001e130  mov     r8d, 0B4h
0x18001e136  lea     rdx, aGenerateoutfil; "GenerateOutFilePath"
0x18001e13d  mov     ecx, 1
0x18001e142  call    AslLogCallPrintf
0x18001e147  jmp     loc_18001E1F2
0x18001e14c  lea     rax, [rbp+220h+Dst]
0x18001e150  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e154  inc     rdx
0x18001e157  cmp     [rax+rdx*2], r12w
0x18001e15c  jnz     short loc_18001E154
0x18001e15e  cmp     rdx, [rdi+18h]
0x18001e162  ja      short loc_18001E191
0x18001e164  cmp     qword ptr [rdi+18h], 7
0x18001e169  jbe     short loc_18001E170
0x18001e16b  mov     rsi, [rdi]
0x18001e16e  jmp     short loc_18001E173
0x18001e170  mov     rsi, rdi
0x18001e173  mov     [rdi+10h], rdx
0x18001e177  lea     rbx, [rdx+rdx]
0x18001e17b  mov     r8, rbx; Size
0x18001e17e  lea     rdx, [rbp+220h+Dst]; Src
0x18001e182  mov     rcx, rsi; void *
0x18001e185  call    memmove_0
0x18001e18a  mov     [rbx+rsi], r12w
0x18001e18f  jmp     short loc_18001E19D
0x18001e191  lea     r9, [rbp+220h+Dst]
0x18001e195  mov     rcx, rdi
0x18001e198  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001e19d  lea     rdx, asc_18006E074; "\\"
0x18001e1a4  mov     rcx, rdi; Src
0x18001e1a7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e1ac  lea     rdx, aInboxutilitymp; "InboxUtilityMP_"
0x18001e1b3  mov     rcx, rdi; Src
0x18001e1b6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e1bb  mov     rdx, r15; void *
0x18001e1be  mov     rcx, rdi; Src
0x18001e1c1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e1c6  lea     rdx, asc_180072738; "_"
0x18001e1cd  mov     rcx, rdi; Src
0x18001e1d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e1d5  mov     rdx, r14
0x18001e1d8  mov     rcx, rdi; Src
0x18001e1db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001e1e0  lea     rdx, aTxt; ".txt"
0x18001e1e7  mov     rcx, rdi; Src
0x18001e1ea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e1ef  mov     ebx, r12d
0x18001e1f2  mov     rcx, r14; void *
0x18001e1f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e1fa  mov     eax, ebx
0x18001e1fc  mov     rcx, [rbp+220h+var_40]
0x18001e203  xor     rcx, rsp; StackCookie
0x18001e206  call    __security_check_cookie
0x18001e20b  add     rsp, 2F0h
0x18001e212  pop     r15
0x18001e214  pop     r14
0x18001e216  pop     r12
0x18001e218  pop     rdi
0x18001e219  pop     rsi
0x18001e21a  pop     rbx
0x18001e21b  pop     rbp
0x18001e21c  retn
```

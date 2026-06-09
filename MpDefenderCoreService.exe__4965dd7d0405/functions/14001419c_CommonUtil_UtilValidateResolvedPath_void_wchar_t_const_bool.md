# CommonUtil::UtilValidateResolvedPath(void *,wchar_t const *,bool)

- ea: `0x14001419c`
- end: `0x1400144dc`
- name: `?UtilValidateResolvedPath@CommonUtil@@YAJPEAXPEB_W_N@Z`
- size: `832`
- prototype: `__int64 __fastcall(HANDLE hFile, void *, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140013df8`

## callees

- `0x1400138a0`
- `0x1400139dc`
- `0x14001419c`
- `0x14003a5c0`
- `0x14004f9a0`
- `0x14005a260`
- `0x140063ac0`
- `0x140085d38`
- `0x140085d94`
- `0x1400934f8`
- `0x1400bb460`
- `0x140166990`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x140014263`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140014352`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140014263`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140014352`
- `KERNEL32!GetFullPathNameW` at `0x1400141f9`
- `KERNEL32!GetFullPathNameW` at `0x1400141f9`
- `KERNEL32!GetLongPathNameW` at `0x14001423b`
- `KERNEL32!GetLongPathNameW` at `0x14001423b`
- `KERNEL32!GetLastError` at `0x140014290`
- `KERNEL32!GetLastError` at `0x140014479`
- `KERNEL32!GetLastError` at `0x140014290`
- `KERNEL32!GetLastError` at `0x140014479`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilValidateResolvedPath(HANDLE hFile, const WCHAR *a2, const wchar_t *a3)
{
  char v3; // r12
  DWORD FullPathNameW; // ebx
  WCHAR *v7; // rsi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // edi
  char v10; // al
  WCHAR *v11; // rax
  wchar_t *v12; // rbx
  DWORD v14; // eax
  const wchar_t *v15; // rdi
  const wchar_t *v16; // rax
  char LastError; // al
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szLongPath[264]; // [rsp+250h] [rbp+150h] BYREF

  v3 = (char)a3;
  memset(Buffer, 0, 0x208u);
  FullPathNameW = GetFullPathNameW(a2, 0x104u, Buffer, 0);
  if ( FullPathNameW - 1 > 0x102 )
    FullPathNameW = 0;
  memset(szLongPath, 0, 0x208u);
  v7 = (WCHAR *)a2;
  if ( FullPathNameW )
  {
    v7 = szLongPath;
    if ( GetLongPathNameW(Buffer, szLongPath, 0x104u) - 1 > 0x102 )
      v7 = Buffer;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  v9 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW )
  {
    if ( FinalPathNameByHandleW <= 0x8000 )
    {
      _mm_lfence();
      v11 = (WCHAR *)malloc(saturated_mul(FinalPathNameByHandleW, 2u));
      v12 = v11;
      if ( !v11 )
        return 2147942414LL;
      _mm_lfence();
      v14 = GetFinalPathNameByHandleW(hFile, v11, v9, 0);
      if ( v14 && v14 < v9 )
      {
        if ( v3 && (_mm_lfence(), (unsigned __int8)CommonUtil::UtilIsUncPath(v12)) )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids, v12);
          }
        }
        else
        {
          _mm_lfence();
          v15 = (const wchar_t *)CommonUtil::UtilNormalizePath(v7);
          _mm_lfence();
          v16 = (const wchar_t *)CommonUtil::UtilNormalizePath(v12);
          if ( !wcsnicmp(v15, v16, 0) )
          {
            _mm_lfence();
            free(v12);
            return 0;
          }
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_SS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              45,
              (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
              (_DWORD)v7,
              (__int64)v12);
          }
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          43,
          (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      _mm_lfence();
      free(v12);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_dS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)a2);
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v10 = GetLastError();
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      41,
      (unsigned int)WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids,
      (_DWORD)a2,
      v10);
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x14001419c  mov     [rsp-8+arg_10], rbx
0x1400141a1  push    rbp
0x1400141a2  push    rsi
0x1400141a3  push    rdi
0x1400141a4  push    r12
0x1400141a6  push    r13
0x1400141a8  push    r14
0x1400141aa  push    r15
0x1400141ac  lea     rbp, [rsp-370h]
0x1400141b4  sub     rsp, 470h
0x1400141bb  mov     rax, cs:__security_cookie
0x1400141c2  xor     rax, rsp
0x1400141c5  mov     [rbp+3A0h+var_40], rax
0x1400141cc  mov     r12b, r8b
0x1400141cf  mov     r14, rdx
0x1400141d2  mov     r15, rcx
0x1400141d5  mov     edi, 208h
0x1400141da  mov     r8d, edi; Size
0x1400141dd  lea     rcx, [rsp+4A0h+Buffer]; void *
0x1400141e2  xor     edx, edx; Val
0x1400141e4  call    memset
0x1400141e9  xor     r9d, r9d; lpFilePart
0x1400141ec  lea     r8, [rsp+4A0h+Buffer]; lpBuffer
0x1400141f1  mov     edx, 104h; nBufferLength
0x1400141f6  mov     rcx, r14; lpFileName
0x1400141f9  call    cs:__imp_GetFullPathNameW
0x1400141ff  xor     r13d, r13d
0x140014202  mov     r8d, edi; Size
0x140014205  mov     ebx, eax
0x140014207  lea     ecx, [rax-1]
0x14001420a  cmp     ecx, 102h
0x140014210  lea     rcx, [rbp+3A0h+szLongPath]; void *
0x140014217  cmova   ebx, r13d
0x14001421b  xor     edx, edx; Val
0x14001421d  call    memset
0x140014222  mov     rsi, r14
0x140014225  test    ebx, ebx
0x140014227  jz      short loc_140014258
0x140014229  mov     r8d, 104h; cchBuffer
0x14001422f  lea     rdx, [rbp+3A0h+szLongPath]; lpszLongPath
0x140014236  lea     rcx, [rsp+4A0h+Buffer]; lpszShortPath
0x14001423b  call    cs:__imp_GetLongPathNameW
0x140014241  dec     eax
0x140014243  lea     rsi, [rbp+3A0h+szLongPath]
0x14001424a  cmp     eax, 102h
0x14001424f  lea     rcx, [rsp+4A0h+Buffer]
0x140014254  cmova   rsi, rcx
0x140014258  xor     r9d, r9d; dwFlags
0x14001425b  xor     r8d, r8d; cchFilePath
0x14001425e  xor     edx, edx; lpszFilePath
0x140014260  mov     rcx, r15; hFile
0x140014263  call    cs:__imp_GetFinalPathNameByHandleW
0x140014269  mov     edi, eax
0x14001426b  test    eax, eax
0x14001426d  jnz     short loc_1400142BE
0x14001426f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014276  lea     rax, WPP_GLOBAL_Control
0x14001427d  cmp     rcx, rax
0x140014280  jz      loc_1400144AD
0x140014286  test    byte ptr [rcx+1Ch], 1
0x14001428a  jz      loc_1400144AD
0x140014290  call    cs:__imp_GetLastError
0x140014296  mov     rcx, cs:WPP_GLOBAL_Control
0x14001429d  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x1400142a4  mov     edx, 29h ; ')'
0x1400142a9  mov     dword ptr [rsp+4A0h+var_480], eax
0x1400142ad  mov     r9, r14
0x1400142b0  mov     rcx, [rcx+10h]
0x1400142b4  call    WPP_SF_Sd
0x1400142b9  jmp     loc_1400144AD
0x1400142be  cmp     edi, 8000h
0x1400142c4  jbe     short loc_140014313
0x1400142c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142cd  lea     rax, WPP_GLOBAL_Control
0x1400142d4  cmp     rcx, rax
0x1400142d7  jz      loc_1400144AD
0x1400142dd  test    byte ptr [rcx+1Ch], 1
0x1400142e1  jz      loc_1400144AD
0x1400142e7  lfence
0x1400142ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142f1  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x1400142f8  mov     edx, 2Ah ; '*'
0x1400142fd  mov     [rsp+4A0h+var_480], r14; __int64
0x140014302  mov     r9d, edi
0x140014305  mov     rcx, [rcx+10h]; LoggerHandle
0x140014309  call    WPP_SF_dS
0x14001430e  jmp     loc_1400144AD
0x140014313  lfence
0x140014316  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14001431d  mov     eax, 2
0x140014322  mul     rdi
0x140014325  cmovb   rax, rcx
0x140014329  mov     rcx, rax; Size
0x14001432c  call    malloc
0x140014331  mov     rbx, rax
0x140014334  test    rax, rax
0x140014337  jnz     short loc_140014343
0x140014339  mov     eax, 8007000Eh
0x14001433e  jmp     loc_1400144B2
0x140014343  lfence
0x140014346  xor     r9d, r9d; dwFlags
0x140014349  mov     r8d, edi; cchFilePath
0x14001434c  mov     rdx, rbx; lpszFilePath
0x14001434f  mov     rcx, r15; hFile
0x140014352  call    cs:__imp_GetFinalPathNameByHandleW
0x140014358  test    eax, eax
0x14001435a  jz      loc_140014460
0x140014360  cmp     eax, edi
0x140014362  jnb     loc_140014460
0x140014368  test    r12b, r12b
0x14001436b  jz      short loc_1400143C4
0x14001436d  lfence
0x140014370  mov     rcx, rbx; String1
0x140014373  call    CommonUtil__UtilIsUncPath
0x140014378  test    al, al
0x14001437a  jz      short loc_1400143C4
0x14001437c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014383  lea     rax, WPP_GLOBAL_Control
0x14001438a  cmp     rcx, rax
0x14001438d  jz      loc_1400144A2
0x140014393  test    byte ptr [rcx+1Ch], 1
0x140014397  jz      loc_1400144A2
0x14001439d  lfence
0x1400143a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143a7  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x1400143ae  mov     edx, 2Ch ; ','
0x1400143b3  mov     r9, rbx
0x1400143b6  mov     rcx, [rcx+10h]
0x1400143ba  call    WPP_SF_S
0x1400143bf  jmp     loc_1400144A2
0x1400143c4  lfence
0x1400143c7  lea     rdx, [rsp+4A0h+MaxCount]
0x1400143cc  mov     [rsp+4A0h+MaxCount], r13
0x1400143d1  mov     rcx, rsi; String1
0x1400143d4  call    CommonUtil__UtilNormalizePath
0x1400143d9  lea     rdx, [rsp+4A0h+var_468]
0x1400143de  mov     [rsp+4A0h+var_468], r13
0x1400143e3  mov     rcx, rbx; String1
0x1400143e6  mov     rdi, rax
0x1400143e9  call    CommonUtil__UtilNormalizePath
0x1400143ee  mov     r8, [rsp+4A0h+MaxCount]; MaxCount
0x1400143f3  cmp     r8, [rsp+4A0h+var_468]
0x1400143f8  jnz     short loc_14001441E
0x1400143fa  lfence
0x1400143fd  mov     rdx, rax; String2
0x140014400  mov     rcx, rdi; String1
0x140014403  call    _wcsnicmp
0x140014408  test    eax, eax
0x14001440a  jnz     short loc_14001441E
0x14001440c  lfence
0x14001440f  mov     rcx, rbx; Block
0x140014412  call    free
0x140014417  xor     eax, eax
0x140014419  jmp     loc_1400144B2
0x14001441e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014425  lea     rax, WPP_GLOBAL_Control
0x14001442c  cmp     rcx, rax
0x14001442f  jz      short loc_1400144A2
0x140014431  test    byte ptr [rcx+1Ch], 1
0x140014435  jz      short loc_1400144A2
0x140014437  lfence
0x14001443a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014441  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x140014448  mov     edx, 2Dh ; '-'
0x14001444d  mov     [rsp+4A0h+var_480], rbx
0x140014452  mov     r9, rsi
0x140014455  mov     rcx, [rcx+10h]
0x140014459  call    WPP_SF_SS
0x14001445e  jmp     short loc_1400144A2
0x140014460  mov     rcx, cs:WPP_GLOBAL_Control
0x140014467  lea     rax, WPP_GLOBAL_Control
0x14001446e  cmp     rcx, rax
0x140014471  jz      short loc_1400144A2
0x140014473  test    byte ptr [rcx+1Ch], 1
0x140014477  jz      short loc_1400144A2
0x140014479  call    cs:__imp_GetLastError
0x14001447f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014486  lea     r8, WPP_fdb0e9451b743826f9befb8c8f5d3e1f_Traceguids
0x14001448d  mov     edx, 2Bh ; '+'
0x140014492  mov     dword ptr [rsp+4A0h+var_480], eax
0x140014496  mov     r9, r14
0x140014499  mov     rcx, [rcx+10h]
0x14001449d  call    WPP_SF_Sd
0x1400144a2  lfence
0x1400144a5  mov     rcx, rbx; Block
0x1400144a8  call    free
0x1400144ad  mov     eax, 80070005h
0x1400144b2  mov     rcx, [rbp+3A0h+var_40]
0x1400144b9  xor     rcx, rsp; StackCookie
0x1400144bc  call    __security_check_cookie
0x1400144c1  mov     rbx, [rsp+4A0h+arg_10]
0x1400144c9  add     rsp, 470h
0x1400144d0  pop     r15
0x1400144d2  pop     r14
0x1400144d4  pop     r13
0x1400144d6  pop     r12
0x1400144d8  pop     rdi
0x1400144d9  pop     rsi
0x1400144da  pop     rbp
0x1400144db  retn
```

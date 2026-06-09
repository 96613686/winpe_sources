# AiGetMsiVersionInfo

- ea: `0x180005740`
- end: `0x180005b22`
- name: `AiGetMsiVersionInfo`
- size: `994`
- prototype: `__int64 __usercall@<rax>(LPCWSTR szDatabasePath@<rcx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180002ed0`
- `0x18000890c`

## callees

- `0x180003fd4`
- `0x180005740`
- `0x180009592`
- `0x1800095c0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000597c`
- `msvcrt!wcsstr` at `0x1800059b5`
- `msvcrt!wcsstr` at `0x1800059ec`
- `msvcrt!wcsstr` at `0x180005a22`
- `msvcrt!wcsstr` at `0x18000597c`
- `msvcrt!wcsstr` at `0x1800059b5`
- `msvcrt!wcsstr` at `0x1800059ec`
- `msvcrt!wcsstr` at `0x180005a22`
- `msvcrt!_wtol` at `0x180005992`
- `msvcrt!_wtol` at `0x1800059cb`
- `msvcrt!_wtol` at `0x180005a04`
- `msvcrt!_wtol` at `0x180005a34`
- `msvcrt!_wtol` at `0x180005992`
- `msvcrt!_wtol` at `0x1800059cb`
- `msvcrt!_wtol` at `0x180005a04`
- `msvcrt!_wtol` at `0x180005a34`
- `ntdll!RtlFreeHeap` at `0x180005a92`
- `ntdll!RtlFreeHeap` at `0x180005ac5`
- `ntdll!RtlFreeHeap` at `0x180005aeb`
- `ntdll!RtlFreeHeap` at `0x180005a92`
- `ntdll!RtlFreeHeap` at `0x180005ac5`
- `ntdll!RtlFreeHeap` at `0x180005aeb`
- `msi!__imp_MsiCloseHandle` at `0x180005830`
- `msi!__imp_MsiCloseHandle` at `0x180005a5c`
- `msi!__imp_MsiCloseHandle` at `0x180005a6a`
- `msi!__imp_MsiCloseHandle` at `0x180005a78`
- `msi!__imp_MsiCloseHandle` at `0x180005830`
- `msi!__imp_MsiCloseHandle` at `0x180005a5c`
- `msi!__imp_MsiCloseHandle` at `0x180005a6a`
- `msi!__imp_MsiCloseHandle` at `0x180005a78`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180005807`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180005807`
- `msi!__imp_MsiOpenDatabaseW` at `0x1800057e7`
- `msi!__imp_MsiOpenDatabaseW` at `0x1800057e7`
- `msi!__imp_MsiRecordGetStringW` at `0x18000586c`
- `msi!__imp_MsiRecordGetStringW` at `0x1800058e2`
- `msi!__imp_MsiRecordGetStringW` at `0x180005939`
- `msi!__imp_MsiRecordGetStringW` at `0x18000586c`
- `msi!__imp_MsiRecordGetStringW` at `0x1800058e2`
- `msi!__imp_MsiRecordGetStringW` at `0x180005939`
- `msi!__imp_MsiVerifyPackageW` at `0x1800057cd`
- `msi!__imp_MsiVerifyPackageW` at `0x1800057cd`
- `msi!__imp_MsiViewExecute` at `0x18000581d`
- `msi!__imp_MsiViewExecute` at `0x18000581d`
- `msi!__imp_MsiViewFetch` at `0x180005843`
- `msi!__imp_MsiViewFetch` at `0x180005843`

## pseudocode

```c
__int64 __fastcall AiGetMsiVersionInfo(
        LPCWSTR szDatabasePath,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6,
        __int64 a7)
{
  UINT StringW; // ebx
  UINT v10; // eax
  UINT v11; // eax
  __int16 *v12; // rdi
  __int16 v13; // cx
  WCHAR *v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rdi
  const wchar_t *v17; // rsi
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  const wchar_t *v20; // rsi
  wchar_t *v21; // rax
  wchar_t *v22; // rdi
  wchar_t *v23; // rax
  void *v24; // r8
  unsigned int v25; // edi
  void *v26; // r8
  MSIHANDLE hAny; // [rsp+20h] [rbp-E0h] BYREF
  DWORD v29; // [rsp+24h] [rbp-DCh] BYREF
  MSIHANDLE phView; // [rsp+28h] [rbp-D8h] BYREF
  MSIHANDLE phDatabase; // [rsp+2Ch] [rbp-D4h] BYREF
  DWORD pcchValueBuf; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v33; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-C0h]
  _DWORD *v35; // [rsp+48h] [rbp-B8h]
  _DWORD *v36; // [rsp+50h] [rbp-B0h]
  WCHAR szValueBuf[256]; // [rsp+60h] [rbp-A0h] BYREF

  v36 = a3;
  *(_OWORD *)a7 = 0;
  v35 = a2;
  *(_OWORD *)a6 = 0;
  *a5 = 0;
  *a4 = 0;
  *a3 = 0;
  *a2 = 0;
  phDatabase = 0;
  phView = 0;
  hAny = 0;
  v29 = 0;
  pcchValueBuf = 0;
  v33 = 0;
  Str = 0;
  StringW = MsiVerifyPackageW(szDatabasePath);
  if ( StringW )
    goto LABEL_37;
  StringW = MsiOpenDatabaseW(szDatabasePath, 0, &phDatabase);
  if ( StringW )
    goto LABEL_37;
  StringW = MsiDatabaseOpenViewW(
              phDatabase,
              L"select * from Property where Property = 'ProductName' OR Property = 'ProductCode' OR Property = 'ProductVersion' ",
              &phView);
  if ( StringW )
    goto LABEL_37;
  v10 = MsiViewExecute(phView, 0);
  while ( 2 )
  {
    StringW = v10;
    if ( v10 )
      goto LABEL_37;
    while ( 1 )
    {
      if ( hAny )
      {
        MsiCloseHandle(hAny);
        hAny = 0;
      }
      v11 = MsiViewFetch(phView, &hAny);
      StringW = v11;
      if ( v11 )
      {
        if ( v11 == 259 )
        {
          StringW = 0;
          if ( v33 )
          {
            v15 = wcsstr(Str, L".");
            v16 = v15;
            if ( v15 )
              *v15 = 0;
            *a4 = _wtol(Str) << 16;
            if ( v16 )
            {
              v17 = v16 + 1;
              v18 = wcsstr(v16 + 1, L".");
              v19 = v18;
              if ( v18 )
                *v18 = 0;
              *a4 |= (unsigned __int16)_wtol(v17);
              if ( v19 )
              {
                v20 = v19 + 1;
                v21 = wcsstr(v19 + 1, L".");
                v22 = v21;
                if ( v21 )
                  *v21 = 0;
                *a5 = _wtol(v20) << 16;
                if ( v22 )
                {
                  v23 = wcsstr(v22 + 1, L".");
                  if ( v23 )
                    *v23 = 0;
                  *a5 |= (unsigned __int16)_wtol(v22 + 1);
                }
              }
            }
          }
          *v35 = *a4;
          *v36 = *a5;
        }
        goto LABEL_37;
      }
      pcchValueBuf = 256;
      StringW = MsiRecordGetStringW(hAny, 1u, szValueBuf, &pcchValueBuf);
      if ( StringW )
        goto LABEL_37;
      if ( !wcscmp_0(szValueBuf, L"ProductName") )
      {
        v12 = (__int16 *)a6;
        goto LABEL_15;
      }
      if ( !wcscmp_0(szValueBuf, L"ProductCode") )
      {
        v12 = (__int16 *)a7;
        goto LABEL_15;
      }
      if ( !wcscmp_0(szValueBuf, L"ProductVersion") )
      {
        v12 = &v33;
LABEL_15:
        v29 = 0;
        StringW = MsiRecordGetStringW(hAny, 2u, 0, &v29);
        if ( StringW )
          goto LABEL_37;
        if ( v29 - 1 <= 0x7FFD )
          break;
      }
    }
    v13 = 2 * v29;
    *v12 = 2 * v29;
    v12[1] = v13 + 2;
    v14 = (WCHAR *)AiAlloc();
    *((_QWORD *)v12 + 1) = v14;
    if ( v14 )
    {
      ++v29;
      v10 = MsiRecordGetStringW(hAny, 2u, v14, &v29);
      continue;
    }
    break;
  }
  StringW = 8;
LABEL_37:
  if ( hAny )
    MsiCloseHandle(hAny);
  if ( phView )
    MsiCloseHandle(phView);
  if ( phDatabase )
    MsiCloseHandle(phDatabase);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Str);
  if ( StringW )
  {
    v24 = *(void **)(a7 + 8);
    v25 = -2;
    if ( StringW == 8 )
      v25 = -1073741801;
    if ( v24 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
      *(_OWORD *)a7 = 0;
    }
    v26 = *(void **)(a6 + 8);
    if ( v26 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
      *(_OWORD *)a6 = 0;
    }
  }
  else
  {
    return 0;
  }
  return v25;
}

```

## disassembly

```asm
0x180005740  push    rbp
0x180005742  push    rbx
0x180005743  push    rsi
0x180005744  push    rdi
0x180005745  push    r12
0x180005747  push    r13
0x180005749  push    r14
0x18000574b  push    r15
0x18000574d  lea     rbp, [rsp-178h]
0x180005755  sub     rsp, 278h
0x18000575c  mov     rax, cs:__security_cookie
0x180005763  xor     rax, rsp
0x180005766  mov     [rbp+1B0h+var_50], rax
0x18000576d  mov     r12, [rbp+1B0h+arg_30]
0x180005774  xor     esi, esi
0x180005776  mov     r13, [rbp+1B0h+arg_28]
0x18000577d  xorps   xmm0, xmm0
0x180005780  mov     r14, [rbp+1B0h+arg_20]
0x180005787  xorps   xmm1, xmm1
0x18000578a  mov     r15, r9
0x18000578d  mov     [rsp+2B0h+var_260], r8
0x180005792  movups  xmmword ptr [r12], xmm0
0x180005797  mov     [rsp+2B0h+var_268], rdx
0x18000579c  mov     rdi, rcx
0x18000579f  movups  xmmword ptr [r13+0], xmm1
0x1800057a4  mov     [r14], esi
0x1800057a7  mov     [r9], esi
0x1800057aa  mov     [r8], esi
0x1800057ad  mov     [rdx], esi
0x1800057af  mov     [rsp+2B0h+phDatabase], esi
0x1800057b3  mov     [rsp+2B0h+phView], esi
0x1800057b7  mov     [rsp+2B0h+hAny], esi
0x1800057bb  mov     [rsp+2B0h+var_28C], esi
0x1800057bf  mov     [rsp+2B0h+pcchValueBuf], esi
0x1800057c3  mov     [rsp+2B0h+var_278], si
0x1800057c8  mov     [rsp+2B0h+Str], rsi
0x1800057cd  call    cs:__imp_MsiVerifyPackageW
0x1800057d3  mov     ebx, eax
0x1800057d5  test    eax, eax
0x1800057d7  jnz     loc_180005A54
0x1800057dd  lea     r8, [rsp+2B0h+phDatabase]; phDatabase
0x1800057e2  xor     edx, edx; szPersist
0x1800057e4  mov     rcx, rdi; szDatabasePath
0x1800057e7  call    cs:__imp_MsiOpenDatabaseW
0x1800057ed  mov     ebx, eax
0x1800057ef  test    eax, eax
0x1800057f1  jnz     loc_180005A54
0x1800057f7  mov     ecx, [rsp+2B0h+phDatabase]; hDatabase
0x1800057fb  lea     r8, [rsp+2B0h+phView]; phView
0x180005800  lea     rdx, szQuery; "select * from Property where Property ="...
0x180005807  call    cs:__imp_MsiDatabaseOpenViewW
0x18000580d  mov     ebx, eax
0x18000580f  test    eax, eax
0x180005811  jnz     loc_180005A54
0x180005817  mov     ecx, [rsp+2B0h+phView]; hView
0x18000581b  xor     edx, edx; hRecord
0x18000581d  call    cs:__imp_MsiViewExecute
0x180005823  jmp     loc_18000593F
0x180005828  mov     ecx, [rsp+2B0h+hAny]; hAny
0x18000582c  test    ecx, ecx
0x18000582e  jz      short loc_18000583A
0x180005830  call    cs:__imp_MsiCloseHandle
0x180005836  mov     [rsp+2B0h+hAny], esi
0x18000583a  mov     ecx, [rsp+2B0h+phView]; hView
0x18000583e  lea     rdx, [rsp+2B0h+hAny]; phRecord
0x180005843  call    cs:__imp_MsiViewFetch
0x180005849  mov     ebx, eax
0x18000584b  test    eax, eax
0x18000584d  jnz     loc_180005958
0x180005853  mov     ecx, [rsp+2B0h+hAny]; hRecord
0x180005857  lea     r9, [rsp+2B0h+pcchValueBuf]; pcchValueBuf
0x18000585c  lea     r8, [rsp+2B0h+szValueBuf]; szValueBuf
0x180005861  mov     [rsp+2B0h+pcchValueBuf], 100h
0x180005869  lea     edx, [rax+1]; iField
0x18000586c  call    cs:__imp_MsiRecordGetStringW
0x180005872  mov     ebx, eax
0x180005874  test    eax, eax
0x180005876  jnz     loc_180005A54
0x18000587c  lea     rdx, aProductname; "ProductName"
0x180005883  lea     rcx, [rsp+2B0h+szValueBuf]; String1
0x180005888  call    wcscmp_0
0x18000588d  test    eax, eax
0x18000588f  jnz     short loc_180005896
0x180005891  mov     rdi, r13
0x180005894  jmp     short loc_1800058CE
0x180005896  lea     rdx, aProductcode; "ProductCode"
0x18000589d  lea     rcx, [rsp+2B0h+szValueBuf]; String1
0x1800058a2  call    wcscmp_0
0x1800058a7  test    eax, eax
0x1800058a9  jnz     short loc_1800058B0
0x1800058ab  mov     rdi, r12
0x1800058ae  jmp     short loc_1800058CE
0x1800058b0  lea     rdx, aProductversion; "ProductVersion"
0x1800058b7  lea     rcx, [rsp+2B0h+szValueBuf]; String1
0x1800058bc  call    wcscmp_0
0x1800058c1  test    eax, eax
0x1800058c3  jnz     loc_180005828
0x1800058c9  lea     rdi, [rsp+2B0h+var_278]
0x1800058ce  mov     ecx, [rsp+2B0h+hAny]; hRecord
0x1800058d2  lea     r9, [rsp+2B0h+var_28C]; pcchValueBuf
0x1800058d7  xor     r8d, r8d; szValueBuf
0x1800058da  mov     [rsp+2B0h+var_28C], esi
0x1800058de  lea     edx, [r8+2]; iField
0x1800058e2  call    cs:__imp_MsiRecordGetStringW
0x1800058e8  mov     ebx, eax
0x1800058ea  test    eax, eax
0x1800058ec  jnz     loc_180005A54
0x1800058f2  mov     ecx, [rsp+2B0h+var_28C]
0x1800058f6  lea     eax, [rcx-1]
0x1800058f9  cmp     eax, 7FFDh
0x1800058fe  ja      loc_180005828
0x180005904  add     cx, cx
0x180005907  mov     ebx, 2
0x18000590c  mov     [rdi], cx
0x18000590f  add     cx, bx
0x180005912  movzx   ecx, cx
0x180005915  mov     [rdi+2], cx
0x180005919  call    AiAlloc
0x18000591e  mov     [rdi+8], rax
0x180005922  test    rax, rax
0x180005925  jz      short loc_18000594E
0x180005927  inc     [rsp+2B0h+var_28C]
0x18000592b  lea     r9, [rsp+2B0h+var_28C]; pcchValueBuf
0x180005930  mov     ecx, [rsp+2B0h+hAny]; hRecord
0x180005934  mov     r8, rax; szValueBuf
0x180005937  mov     edx, ebx; iField
0x180005939  call    cs:__imp_MsiRecordGetStringW
0x18000593f  mov     ebx, eax
0x180005941  test    eax, eax
0x180005943  jz      loc_180005828
0x180005949  jmp     loc_180005A54
0x18000594e  mov     ebx, 8
0x180005953  jmp     loc_180005A54
0x180005958  cmp     eax, 103h
0x18000595d  jnz     loc_180005A54
0x180005963  mov     ebx, esi
0x180005965  cmp     [rsp+2B0h+var_278], si
0x18000596a  jz      loc_180005A40
0x180005970  mov     rcx, [rsp+2B0h+Str]; Str
0x180005975  lea     rdx, SubStr; "."
0x18000597c  call    cs:__imp_wcsstr
0x180005982  mov     rdi, rax
0x180005985  test    rax, rax
0x180005988  jz      short loc_18000598D
0x18000598a  mov     [rax], si
0x18000598d  mov     rcx, [rsp+2B0h+Str]; String
0x180005992  call    cs:__imp__wtol
0x180005998  shl     eax, 10h
0x18000599b  mov     [r15], eax
0x18000599e  test    rdi, rdi
0x1800059a1  jz      loc_180005A40
0x1800059a7  lea     rsi, [rdi+2]
0x1800059ab  mov     rcx, rsi; Str
0x1800059ae  lea     rdx, SubStr; "."
0x1800059b5  call    cs:__imp_wcsstr
0x1800059bb  mov     rdi, rax
0x1800059be  test    rax, rax
0x1800059c1  jz      short loc_1800059C8
0x1800059c3  xor     edx, edx
0x1800059c5  mov     [rax], dx
0x1800059c8  mov     rcx, rsi; String
0x1800059cb  call    cs:__imp__wtol
0x1800059d1  movzx   ecx, ax
0x1800059d4  xor     esi, esi
0x1800059d6  or      [r15], ecx
0x1800059d9  test    rdi, rdi
0x1800059dc  jz      short loc_180005A40
0x1800059de  lea     rsi, [rdi+2]
0x1800059e2  mov     rcx, rsi; Str
0x1800059e5  lea     rdx, SubStr; "."
0x1800059ec  call    cs:__imp_wcsstr
0x1800059f2  mov     rdi, rax
0x1800059f5  test    rax, rax
0x1800059f8  jz      short loc_180005A01
0x1800059fa  xor     r8d, r8d
0x1800059fd  mov     [rax], r8w
0x180005a01  mov     rcx, rsi; String
0x180005a04  call    cs:__imp__wtol
0x180005a0a  shl     eax, 10h
0x180005a0d  xor     esi, esi
0x180005a0f  mov     [r14], eax
0x180005a12  test    rdi, rdi
0x180005a15  jz      short loc_180005A40
0x180005a17  lea     rdx, SubStr; "."
0x180005a1e  lea     rcx, [rdi+2]; Str
0x180005a22  call    cs:__imp_wcsstr
0x180005a28  test    rax, rax
0x180005a2b  jz      short loc_180005A30
0x180005a2d  mov     [rax], si
0x180005a30  lea     rcx, [rdi+2]; String
0x180005a34  call    cs:__imp__wtol
0x180005a3a  movzx   ecx, ax
0x180005a3d  or      [r14], ecx
0x180005a40  mov     eax, [r15]
0x180005a43  mov     rcx, [rsp+2B0h+var_268]
0x180005a48  mov     [rcx], eax
0x180005a4a  mov     rcx, [rsp+2B0h+var_260]
0x180005a4f  mov     eax, [r14]
0x180005a52  mov     [rcx], eax
0x180005a54  mov     ecx, [rsp+2B0h+hAny]; hAny
0x180005a58  test    ecx, ecx
0x180005a5a  jz      short loc_180005A62
0x180005a5c  call    cs:__imp_MsiCloseHandle
0x180005a62  mov     ecx, [rsp+2B0h+phView]; hAny
0x180005a66  test    ecx, ecx
0x180005a68  jz      short loc_180005A70
0x180005a6a  call    cs:__imp_MsiCloseHandle
0x180005a70  mov     ecx, [rsp+2B0h+phDatabase]; hAny
0x180005a74  test    ecx, ecx
0x180005a76  jz      short loc_180005A7E
0x180005a78  call    cs:__imp_MsiCloseHandle
0x180005a7e  mov     rcx, gs:60h
0x180005a87  xor     edx, edx; Flags
0x180005a89  mov     r8, [rsp+2B0h+Str]; P
0x180005a8e  mov     rcx, [rcx+30h]; HeapHandle
0x180005a92  call    cs:__imp_RtlFreeHeap
0x180005a98  test    ebx, ebx
0x180005a9a  jz      short loc_180005AFB
0x180005a9c  mov     r8, [r12+8]; P
0x180005aa1  cmp     ebx, 8
0x180005aa4  mov     edi, 0FFFFFFFEh
0x180005aa9  mov     eax, 0C0000017h
0x180005aae  cmovz   edi, eax
0x180005ab1  test    r8, r8
0x180005ab4  jz      short loc_180005AD3
0x180005ab6  mov     rcx, gs:60h
0x180005abf  xor     edx, edx; Flags
0x180005ac1  mov     rcx, [rcx+30h]; HeapHandle
0x180005ac5  call    cs:__imp_RtlFreeHeap
0x180005acb  xorps   xmm0, xmm0
0x180005ace  movups  xmmword ptr [r12], xmm0
0x180005ad3  mov     r8, [r13+8]; P
0x180005ad7  test    r8, r8
0x180005ada  jz      short loc_180005AFD
0x180005adc  mov     rcx, gs:60h
0x180005ae5  xor     edx, edx; Flags
0x180005ae7  mov     rcx, [rcx+30h]; HeapHandle
0x180005aeb  call    cs:__imp_RtlFreeHeap
0x180005af1  xorps   xmm0, xmm0
0x180005af4  movups  xmmword ptr [r13+0], xmm0
0x180005af9  jmp     short loc_180005AFD
0x180005afb  mov     edi, esi
0x180005afd  mov     eax, edi
0x180005aff  mov     rcx, [rbp+1B0h+var_50]
0x180005b06  xor     rcx, rsp; StackCookie
0x180005b09  call    __security_check_cookie
0x180005b0e  add     rsp, 278h
0x180005b15  pop     r15
0x180005b17  pop     r14
0x180005b19  pop     r13
0x180005b1b  pop     r12
0x180005b1d  pop     rdi
0x180005b1e  pop     rsi
0x180005b1f  pop     rbx
0x180005b20  pop     rbp
0x180005b21  retn
```

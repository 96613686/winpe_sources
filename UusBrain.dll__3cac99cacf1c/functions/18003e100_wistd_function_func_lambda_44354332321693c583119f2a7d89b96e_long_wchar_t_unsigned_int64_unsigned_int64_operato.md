# wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18003e100`
- end: `0x18003e1b6`
- name: `??R?$__func@V_lambda_44354332321693c583119f2a7d89b96e_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006424`
- `0x18003e100`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003e157`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003e157`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003e139`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003e139`

## string_xrefs

- `0x18003e182`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        __int64 **a4)
{
  unsigned int v4; // ebx
  __int64 *v5; // rsi
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rdx
  void *v8; // r10
  HMODULE *v9; // rax
  DWORD ModuleFileName; // eax
  const char *v11; // r9
  __int64 v12; // rdx
  bool v13; // r8
  bool v14; // cf
  DWORD ModuleFileNameW; // eax
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = 0;
  v5 = *a4;
  v6 = *a3;
  v7 = *a2;
  v8 = **(void ***)(a1 + 8);
  v9 = *(HMODULE **)(a1 + 16);
  if ( v8 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v8, *v9, v7, v6);
    v12 = ModuleFileName;
    v13 = ModuleFileName == 0;
    if ( ModuleFileName )
    {
      v14 = ModuleFileName < v6 - 1;
      goto LABEL_6;
    }
  }
  else
  {
    ModuleFileNameW = GetModuleFileNameW(*v9, v7, v6);
    v12 = ModuleFileNameW;
    v13 = ModuleFileNameW == 0;
    if ( ModuleFileNameW )
    {
      v14 = ModuleFileNameW < v6;
LABEL_6:
      v16 = 1;
      if ( v14 )
        goto LABEL_8;
    }
  }
  v16 = 0;
LABEL_8:
  v17 = v12 + 1;
  if ( v13 )
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x205,
                           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opens"
                                         "ource\\wil\\win32_helpers.h",
                           v11);
  }
  else
  {
    v18 = 2 * v6;
    if ( v16 )
      v18 = v17;
    *v5 = v18;
  }
  return v4;
}

```

## disassembly

```asm
0x18003e100  mov     [rsp+arg_0], rbx
0x18003e105  mov     [rsp+arg_8], rsi
0x18003e10a  push    rdi
0x18003e10b  sub     rsp, 20h
0x18003e10f  mov     rax, [rcx+8]
0x18003e113  xor     ebx, ebx
0x18003e115  mov     rsi, [r9]
0x18003e118  mov     rdi, [r8]
0x18003e11b  mov     rdx, [rdx]; lpFilename
0x18003e11e  mov     r10, [rax]
0x18003e121  mov     rax, [rcx+10h]
0x18003e125  mov     rcx, [rax]; hModule
0x18003e128  test    r10, r10
0x18003e12b  jz      short loc_18003E154
0x18003e12d  mov     r8, rdx; lpFilename
0x18003e130  mov     r9d, edi; nSize
0x18003e133  mov     rdx, rcx; hModule
0x18003e136  mov     rcx, r10; hProcess
0x18003e139  call    cs:__imp_K32GetModuleFileNameExW
0x18003e13f  test    eax, eax
0x18003e141  mov     edx, eax
0x18003e143  setz    r8b
0x18003e147  test    eax, eax
0x18003e149  jz      short loc_18003E173
0x18003e14b  lea     rax, [rdi-1]
0x18003e14f  cmp     rdx, rax
0x18003e152  jmp     short loc_18003E16C
0x18003e154  mov     r8d, edi; nSize
0x18003e157  call    cs:__imp_GetModuleFileNameW
0x18003e15d  test    eax, eax
0x18003e15f  mov     edx, eax
0x18003e161  setz    r8b
0x18003e165  test    eax, eax
0x18003e167  jz      short loc_18003E173
0x18003e169  cmp     rdx, rdi
0x18003e16c  mov     ecx, 1
0x18003e171  jb      short loc_18003E175
0x18003e173  mov     ecx, ebx
0x18003e175  inc     rdx
0x18003e178  test    r8b, r8b
0x18003e17b  jz      short loc_18003E197
0x18003e17d  mov     rcx, [rsp+28h]; this
0x18003e182  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003e189  mov     edx, 205h; void *
0x18003e18e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e193  mov     ebx, eax
0x18003e195  jmp     short loc_18003E1A4
0x18003e197  test    ecx, ecx
0x18003e199  lea     rax, [rdi+rdi]
0x18003e19d  cmovnz  rax, rdx
0x18003e1a1  mov     [rsi], rax
0x18003e1a4  mov     rsi, [rsp+28h+arg_8]
0x18003e1a9  mov     eax, ebx
0x18003e1ab  mov     rbx, [rsp+28h+arg_0]
0x18003e1b0  add     rsp, 20h
0x18003e1b4  pop     rdi
0x18003e1b5  retn
```

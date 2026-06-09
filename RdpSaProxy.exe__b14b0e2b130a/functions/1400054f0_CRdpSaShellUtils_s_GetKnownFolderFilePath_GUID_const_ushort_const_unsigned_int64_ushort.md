# CRdpSaShellUtils::s_GetKnownFolderFilePath(_GUID const &,ushort const *,unsigned __int64,ushort *)

- ea: `0x1400054f0`
- end: `0x1400055f0`
- name: `?s_GetKnownFolderFilePath@CRdpSaShellUtils@@SAJAEBU_GUID@@PEBG_KPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x140003ef4`

## callees

- `0x140002738`
- `0x140002818`
- `0x1400054f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400055dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400055dd`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140005579`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140005579`
- `SHELL32!SHGetKnownFolderPath` at `0x14000551b`
- `SHELL32!SHGetKnownFolderPath` at `0x14000551b`

## string_xrefs

- `0x14000555c`: `SHGetKnownFolderPath`
- `0x1400055ae`: `PathCchCombine`

## pseudocode

```c
__int64 __fastcall CRdpSaShellUtils::s_GetKnownFolderFilePath(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  HRESULT v5; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  PCWSTR pszPathIn; // [rsp+50h] [rbp+18h] BYREF

  pszPathIn = 0;
  v5 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, (PWSTR *)&pszPathIn);
  if ( v5 >= 0 )
  {
    v5 = PathCchCombine(a4, 0x104u, pszPathIn, L"RdpSa.exe");
    if ( v5 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 11;
      v8 = "PathCchCombine";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 10;
    v8 = "SHGetKnownFolderPath";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_887e53613eb13c0071e3559bb10bf4e3_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      v5);
  }
  CoTaskMemFree((LPVOID)pszPathIn);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400054f0  mov     rax, rsp
0x1400054f3  mov     [rax+8], rbx
0x1400054f7  mov     [rax+18h], r8
0x1400054fb  push    rdi
0x1400054fc  sub     rsp, 30h
0x140005500  mov     rdi, r9
0x140005503  mov     qword ptr [rax+18h], 0
0x14000550b  lea     r9, [rax+18h]; ppszPath
0x14000550f  xor     r8d, r8d; hToken
0x140005512  xor     edx, edx; dwFlags
0x140005514  lea     rcx, FOLDERID_System; rfid
0x14000551b  call    cs:__imp_SHGetKnownFolderPath
0x140005521  mov     ebx, eax
0x140005523  test    eax, eax
0x140005525  jns     short loc_140005565
0x140005527  mov     rcx, cs:WPP_GLOBAL_Control
0x14000552e  lea     rdx, WPP_GLOBAL_Control
0x140005535  cmp     rcx, rdx
0x140005538  jz      loc_1400055D8
0x14000553e  test    byte ptr [rcx+1Ch], 8
0x140005542  jz      loc_1400055D8
0x140005548  cmp     byte ptr [rcx+19h], 2
0x14000554c  jb      loc_1400055D8
0x140005552  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140005557  mov     edx, 0Ah
0x14000555c  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath"
0x140005563  jmp     short loc_1400055B5
0x140005565  mov     r8, [rsp+38h+pszPathIn]; pszPathIn
0x14000556a  lea     r9, pszMore; "RdpSa.exe"
0x140005571  mov     edx, 104h; cchPathOut
0x140005576  mov     rcx, rdi; pszPathOut
0x140005579  call    cs:__imp_PathCchCombine
0x14000557f  mov     ebx, eax
0x140005581  test    eax, eax
0x140005583  jns     short loc_1400055D8
0x140005585  mov     rax, cs:WPP_GLOBAL_Control
0x14000558c  lea     rdx, WPP_GLOBAL_Control
0x140005593  cmp     rax, rdx
0x140005596  jz      short loc_1400055D8
0x140005598  test    byte ptr [rax+1Ch], 8
0x14000559c  jz      short loc_1400055D8
0x14000559e  cmp     byte ptr [rax+19h], 2
0x1400055a2  jb      short loc_1400055D8
0x1400055a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400055a9  mov     edx, 0Bh
0x1400055ae  lea     rcx, aPathcchcombine; "PathCchCombine"
0x1400055b5  mov     [rsp+38h+var_10], ebx
0x1400055b9  lea     r8, WPP_887e53613eb13c0071e3559bb10bf4e3_Traceguids
0x1400055c0  mov     [rsp+38h+var_18], rcx
0x1400055c5  mov     r9d, eax
0x1400055c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055cf  mov     rcx, [rcx+10h]
0x1400055d3  call    WPP_SF_DsD
0x1400055d8  mov     rcx, [rsp+38h+pszPathIn]; pv
0x1400055dd  call    cs:__imp_CoTaskMemFree
0x1400055e3  mov     eax, ebx
0x1400055e5  mov     rbx, [rsp+38h+arg_0]
0x1400055ea  add     rsp, 30h
0x1400055ee  pop     rdi
0x1400055ef  retn
```

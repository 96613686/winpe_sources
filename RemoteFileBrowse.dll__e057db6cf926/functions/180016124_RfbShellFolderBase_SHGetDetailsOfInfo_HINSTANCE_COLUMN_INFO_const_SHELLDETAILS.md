# RfbShellFolderBase::SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,_SHELLDETAILS *)

- ea: `0x180016124`
- end: `0x1800162fc`
- name: `?SHGetDetailsOfInfo@RfbShellFolderBase@@IEAAXPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@PEAU_SHELLDETAILS@@@Z`
- size: `472`
- prototype: `void __fastcall(RfbShellFolderBase *__hidden this, HINSTANCE, const struct COLUMN_INFO *, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800155f0`

## callees

- `0x180002030`
- `0x1800056e0`
- `0x180007150`
- `0x180016124`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016189`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180016189`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016206`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161c1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800161b4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180016262`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800161b4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180016262`

## pseudocode

```c
void __fastcall RfbShellFolderBase::SHGetDetailsOfInfo(
        RfbShellFolderBase *this,
        HINSTANCE a2,
        const struct COLUMN_INFO *a3,
        struct _SHELLDETAILS *a4)
{
  UINT v6; // edx
  int v7; // ebx
  signed int LastError; // eax
  LPVOID v9; // rcx
  unsigned int v10; // eax
  WCHAR *ppv; // [rsp+20h] [rbp-258h]
  LPVOID v12; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( !a4 )
  {
    v10 = wil::verify_hresult<long>(0x80070057);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54B,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)v10,
      (int)ppv);
  }
  if ( !a3 )
  {
    v7 = -2147467263;
    goto LABEL_19;
  }
  a4->fmt = *((_DWORD *)a3 + 3);
  a4->cxChar = *((_DWORD *)a3 + 4);
  v6 = *((_DWORD *)a3 + 6);
  if ( v6 )
  {
    if ( LoadStringW(g_hInstance, v6, Buffer, 260) )
    {
      v7 = -2147024809;
      if ( a4 != (struct _SHELLDETAILS *)-8LL )
      {
        a4->str.uType = 0;
        v7 = SHStrDupW(Buffer, &a4->str.pOleStr);
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v12 = 0;
    v7 = CoCreateInstance(&CLSID_PropertiesUI, 0, 1u, &GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66, &v12);
    if ( v7 >= 0 )
    {
      ppv = Buffer;
      v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 40LL))(
             v12,
             *(_QWORD *)a3,
             *(unsigned int *)(*(_QWORD *)a3 + 16LL),
             0);
      if ( v7 >= 0 )
      {
        v7 = -2147024809;
        if ( a4 != (struct _SHELLDETAILS *)-8LL )
        {
          a4->str.uType = 0;
          v7 = SHStrDupW(Buffer, &a4->str.pOleStr);
        }
      }
    }
    v9 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  if ( v7 < 0 )
LABEL_19:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56E,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v7,
      (int)ppv);
}

```

## disassembly

```asm
0x180016124  mov     [rsp+arg_0], rbx
0x180016129  mov     [rsp+arg_8], rsi
0x18001612e  push    rdi
0x18001612f  sub     rsp, 270h
0x180016136  mov     rax, cs:__security_cookie
0x18001613d  xor     rax, rsp
0x180016140  mov     [rsp+278h+var_18], rax
0x180016148  mov     rdi, r9
0x18001614b  mov     rsi, r8
0x18001614e  test    r9, r9
0x180016151  jz      loc_1800162B3
0x180016157  test    r8, r8
0x18001615a  jz      loc_1800162DA
0x180016160  mov     eax, [r8+0Ch]
0x180016164  mov     [r9], eax
0x180016167  mov     eax, [r8+10h]
0x18001616b  mov     [r9+4], eax
0x18001616f  mov     edx, [r8+18h]; uID
0x180016173  test    edx, edx
0x180016175  jz      short loc_1800161DF
0x180016177  mov     r9d, 104h; cchBufferMax
0x18001617d  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x180016182  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180016189  call    cs:__imp_LoadStringW
0x18001618f  test    eax, eax
0x180016191  jz      short loc_1800161C1
0x180016193  lea     rdx, [rdi+8]
0x180016197  mov     ebx, 80070057h
0x18001619c  test    rdx, rdx
0x18001619f  jz      loc_18001628A
0x1800161a5  mov     dword ptr [rdx], 0
0x1800161ab  add     rdx, 8; ppwsz
0x1800161af  lea     rcx, [rsp+278h+Buffer]; psz
0x1800161b4  call    cs:__imp_SHStrDupW
0x1800161ba  mov     ebx, eax
0x1800161bc  jmp     loc_18001628A
0x1800161c1  call    cs:__imp_GetLastError
0x1800161c7  mov     ebx, eax
0x1800161c9  test    eax, eax
0x1800161cb  jle     loc_18001628A
0x1800161d1  movzx   ebx, ax
0x1800161d4  or      ebx, 80070000h
0x1800161da  jmp     loc_18001628A
0x1800161df  mov     [rsp+278h+var_238], 0
0x1800161e8  lea     rax, [rsp+278h+var_238]
0x1800161ed  mov     [rsp+278h+ppv], rax; ppv
0x1800161f2  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x1800161f9  xor     edx, edx; pUnkOuter
0x1800161fb  lea     r8d, [rdx+1]; dwClsContext
0x1800161ff  lea     rcx, CLSID_PropertiesUI; rclsid
0x180016206  call    cs:__imp_CoCreateInstance
0x18001620c  mov     ebx, eax
0x18001620e  test    eax, eax
0x180016210  js      short loc_18001626A
0x180016212  mov     rcx, [rsp+278h+var_238]
0x180016217  mov     rdx, [rsi]
0x18001621a  mov     rax, [rcx]
0x18001621d  mov     [rsp+278h+var_250], 80h
0x180016225  lea     r8, [rsp+278h+Buffer]
0x18001622a  mov     [rsp+278h+ppv], r8
0x18001622f  xor     r9d, r9d
0x180016232  mov     r8d, [rdx+10h]
0x180016236  mov     rax, [rax+28h]
0x18001623a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623f  mov     ebx, eax
0x180016241  test    eax, eax
0x180016243  js      short loc_18001626A
0x180016245  lea     rdx, [rdi+8]
0x180016249  mov     ebx, 80070057h
0x18001624e  test    rdx, rdx
0x180016251  jz      short loc_18001626A
0x180016253  mov     dword ptr [rdx], 0
0x180016259  add     rdx, 8; ppwsz
0x18001625d  lea     rcx, [rsp+278h+Buffer]; psz
0x180016262  call    cs:__imp_SHStrDupW
0x180016268  mov     ebx, eax
0x18001626a  mov     rcx, [rsp+278h+var_238]
0x18001626f  test    rcx, rcx
0x180016272  jz      short loc_18001628A
0x180016274  mov     [rsp+278h+var_238], 0
0x18001627d  mov     rax, [rcx]
0x180016280  mov     rax, [rax+10h]
0x180016284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016289  nop
0x18001628a  test    ebx, ebx
0x18001628c  js      short loc_1800162DF
0x18001628e  mov     rcx, [rsp+278h+var_18]
0x180016296  xor     rcx, rsp; StackCookie
0x180016299  call    __security_check_cookie
0x18001629e  lea     r11, [rsp+278h+var_8]
0x1800162a6  mov     rbx, [r11+10h]
0x1800162aa  mov     rsi, [r11+18h]
0x1800162ae  mov     rsp, r11
0x1800162b1  pop     rdi
0x1800162b2  retn
0x1800162b3  mov     ecx, 80070057h
0x1800162b8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800162bd  mov     r9d, eax; char *
0x1800162c0  mov     rcx, [rsp+278h]; this
0x1800162c8  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800162cf  mov     edx, 54Bh; void *
0x1800162d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800162da  mov     ebx, 80004001h
0x1800162df  mov     rcx, [rsp+278h]; this
0x1800162e7  mov     r9d, ebx; char *
0x1800162ea  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800162f1  mov     edx, 56Eh; void *
0x1800162f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

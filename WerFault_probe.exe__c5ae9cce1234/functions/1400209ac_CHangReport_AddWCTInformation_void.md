# CHangReport::_AddWCTInformation(void)

- ea: `0x1400209ac`
- end: `0x140020c1a`
- name: `?_AddWCTInformation@CHangReport@@IEAAJXZ`
- size: `622`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140021830`
- `0x140021bc0`

## callees

- `0x140002470`
- `0x14000b540`
- `0x14000d28c`
- `0x14001444c`
- `0x140014474`
- `0x140014ddc`
- `0x1400209ac`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020b77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020b77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020bdb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140020bf2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140020bf2`
- `wer!WerpAddFile` at `0x140020ba6`
- `wer!WerpAddFile` at `0x140020ba6`

## string_xrefs

- `0x140020adc`: `%s.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHangReport::_AddWCTInformation(CHangReport *this)
{
  HANDLE v2; // rdi
  int v3; // ebx
  int TempFile; // eax
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  CUserModeHangReport *v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v15[264]; // [rsp+260h] [rbp+160h] BYREF

  v2 = 0;
  hObject = 0;
  FileName[0] = 0;
  if ( *((_DWORD *)this + 21) )
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    }
    goto LABEL_30;
  }
  *((_DWORD *)this + 21) = 1;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
      *((_QWORD *)this + 3054) + 256LL);
  }
  TempFile = UtilGetTempFile(&hObject, 0, (__int64)L".xml", FileName, v12, 0, 0, 0);
  v3 = TempFile;
  if ( TempFile < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v6 = 18;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)TempFile);
LABEL_13:
    v2 = hObject;
    goto LABEL_30;
  }
  TempFile = StringCchPrintfW(v15, 0x104u, L"%s.xml", *((_QWORD *)this + 3054) + 256LL);
  v3 = TempFile;
  if ( TempFile < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v6 = 19;
    goto LABEL_12;
  }
  v2 = hObject;
  v7 = (*(__int64 (__fastcall **)(CHangReport *, HANDLE))(*(_QWORD *)this + 184LL))(this, hObject);
  v3 = v7;
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_30;
    }
    v9 = 20;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)v7);
    goto LABEL_30;
  }
  v10 = v2;
  v2 = 0;
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  v7 = WerpAddFile(*((_QWORD *)this + 3055), FileName, 5);
  v3 = v7;
  if ( v7 >= 0 )
  {
    v3 = 0;
    goto LABEL_30;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 21;
    goto LABEL_22;
  }
LABEL_30:
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  if ( v3 < 0 && FileName[0] )
    DeleteFileW(FileName);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400209ac  push    rbp
0x1400209ae  push    rbx
0x1400209af  push    rsi
0x1400209b0  push    rdi
0x1400209b1  push    r12
0x1400209b3  push    r14
0x1400209b5  lea     rbp, [rsp-388h]
0x1400209bd  sub     rsp, 488h
0x1400209c4  mov     rax, cs:__security_cookie
0x1400209cb  xor     rax, rsp
0x1400209ce  mov     [rbp+3B0h+var_40], rax
0x1400209d5  mov     r14, rcx
0x1400209d8  xor     r12d, r12d
0x1400209db  mov     edi, r12d
0x1400209de  mov     [rsp+4B0h+hObject], r12
0x1400209e3  mov     [rsp+4B0h+FileName], r12w
0x1400209e9  cmp     [rcx+54h], r12d
0x1400209ed  jz      short loc_140020A2D
0x1400209ef  mov     ebx, r12d
0x1400209f2  lea     rsi, WPP_GLOBAL_Control
0x1400209f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a00  cmp     rcx, rsi
0x140020a03  jz      loc_140020BCE
0x140020a09  test    byte ptr [rcx+1Ch], 4
0x140020a0d  jz      loc_140020BCE
0x140020a13  lea     edx, [r12+10h]
0x140020a18  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020a1f  mov     rcx, [rcx+10h]
0x140020a23  call    WPP_SF_
0x140020a28  jmp     loc_140020BCE
0x140020a2d  mov     dword ptr [rcx+54h], 1
0x140020a34  lea     rsi, WPP_GLOBAL_Control
0x140020a3b  mov     edi, 100h
0x140020a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a47  cmp     rcx, rsi
0x140020a4a  jz      short loc_140020A71
0x140020a4c  test    byte ptr [rcx+1Ch], 8
0x140020a50  jz      short loc_140020A71
0x140020a52  mov     r9, [r14+5F70h]
0x140020a59  add     r9, rdi
0x140020a5c  mov     edx, 11h
0x140020a61  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020a68  mov     rcx, [rcx+10h]
0x140020a6c  call    WPP_SF_S
0x140020a71  mov     [rsp+4B0h+var_478], r12d
0x140020a76  mov     [rsp+4B0h+var_480], r12d
0x140020a7b  mov     [rsp+4B0h+var_488], r12
0x140020a80  lea     r9, [rsp+4B0h+FileName]
0x140020a85  lea     r8, aXml; ".xml"
0x140020a8c  xor     edx, edx
0x140020a8e  lea     rcx, [rsp+4B0h+hObject]
0x140020a93  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140020a98  mov     ebx, eax
0x140020a9a  test    eax, eax
0x140020a9c  jns     short loc_140020AD2
0x140020a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020aa5  cmp     rcx, rsi
0x140020aa8  jz      short loc_140020AC8
0x140020aaa  test    byte ptr [rcx+1Ch], 1
0x140020aae  jz      short loc_140020AC8
0x140020ab0  mov     edx, 12h
0x140020ab5  mov     r9d, eax
0x140020ab8  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020abf  mov     rcx, [rcx+10h]
0x140020ac3  call    WPP_SF_d
0x140020ac8  mov     rdi, [rsp+4B0h+hObject]
0x140020acd  jmp     loc_140020BCE
0x140020ad2  mov     r9, [r14+5F70h]
0x140020ad9  add     r9, rdi
0x140020adc  lea     r8, aSXml; "%s.xml"
0x140020ae3  mov     edx, 104h; unsigned __int64
0x140020ae8  lea     rcx, [rbp+3B0h+var_250]; wchar_t *
0x140020aef  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140020af4  mov     ebx, eax
0x140020af6  test    eax, eax
0x140020af8  jns     short loc_140020B13
0x140020afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b01  cmp     rcx, rsi
0x140020b04  jz      short loc_140020AC8
0x140020b06  test    byte ptr [rcx+1Ch], 1
0x140020b0a  jz      short loc_140020AC8
0x140020b0c  mov     edx, 13h
0x140020b11  jmp     short loc_140020AB5
0x140020b13  mov     rax, [r14]
0x140020b16  mov     rdi, [rsp+4B0h+hObject]
0x140020b1b  mov     rdx, rdi
0x140020b1e  mov     rcx, r14
0x140020b21  mov     rax, [rax+0B8h]
0x140020b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020b2d  mov     ebx, eax
0x140020b2f  test    eax, eax
0x140020b31  jns     short loc_140020B67
0x140020b33  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b3a  cmp     rcx, rsi
0x140020b3d  jz      loc_140020BCE
0x140020b43  test    byte ptr [rcx+1Ch], 1
0x140020b47  jz      loc_140020BCE
0x140020b4d  mov     edx, 14h
0x140020b52  mov     r9d, eax
0x140020b55  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020b5c  mov     rcx, [rcx+10h]
0x140020b60  call    WPP_SF_d
0x140020b65  jmp     short loc_140020BCE
0x140020b67  mov     rcx, rdi; hObject
0x140020b6a  mov     rdi, r12
0x140020b6d  lea     rax, [rcx+1]
0x140020b71  cmp     rax, 1
0x140020b75  jbe     short loc_140020B7D
0x140020b77  call    cs:__imp_CloseHandle
0x140020b7d  mov     [rsp+4B0h+var_488], r12
0x140020b82  lea     rax, [rbp+3B0h+var_250]
0x140020b89  mov     [rsp+4B0h+var_490], rax
0x140020b8e  mov     r9d, 40001h
0x140020b94  mov     r8d, 5
0x140020b9a  lea     rdx, [rsp+4B0h+FileName]
0x140020b9f  mov     rcx, [r14+5F78h]
0x140020ba6  call    cs:__imp_WerpAddFile
0x140020bac  mov     ebx, eax
0x140020bae  test    eax, eax
0x140020bb0  jns     short loc_140020BCB
0x140020bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140020bb9  cmp     rcx, rsi
0x140020bbc  jz      short loc_140020BCE
0x140020bbe  test    byte ptr [rcx+1Ch], 1
0x140020bc2  jz      short loc_140020BCE
0x140020bc4  mov     edx, 15h
0x140020bc9  jmp     short loc_140020B52
0x140020bcb  mov     ebx, r12d
0x140020bce  lea     rax, [rdi+1]
0x140020bd2  cmp     rax, 1
0x140020bd6  jbe     short loc_140020BE1
0x140020bd8  mov     rcx, rdi; hObject
0x140020bdb  call    cs:__imp_CloseHandle
0x140020be1  test    ebx, ebx
0x140020be3  jns     short loc_140020BF9
0x140020be5  cmp     [rsp+4B0h+FileName], r12w
0x140020beb  jz      short loc_140020BF9
0x140020bed  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x140020bf2  call    cs:__imp_DeleteFileW
0x140020bf8  nop
0x140020bf9  mov     eax, ebx
0x140020bfb  mov     rcx, [rbp+3B0h+var_40]
0x140020c02  xor     rcx, rsp; StackCookie
0x140020c05  call    __security_check_cookie
0x140020c0a  add     rsp, 488h
0x140020c11  pop     r14
0x140020c13  pop     r12
0x140020c15  pop     rdi
0x140020c16  pop     rsi
0x140020c17  pop     rbx
0x140020c18  pop     rbp
0x140020c19  retn
```

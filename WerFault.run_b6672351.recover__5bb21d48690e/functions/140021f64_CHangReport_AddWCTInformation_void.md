# CHangReport::_AddWCTInformation(void)

- ea: `0x140021f64`
- end: `0x1400221ee`
- name: `?_AddWCTInformation@CHangReport@@IEAAJXZ`
- size: `650`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140022e70`
- `0x140023210`

## callees

- `0x140002490`
- `0x14000b580`
- `0x14000d544`
- `0x140014ee4`
- `0x140014f14`
- `0x1400158e8`
- `0x140021f64`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002212f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400221a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002212f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400221a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400221bf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400221bf`
- `wer!WerpAddFile` at `0x140022164`
- `wer!WerpAddFile` at `0x140022164`

## string_xrefs

- `0x140022094`: `%s.xml`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
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
      WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
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
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)TempFile);
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
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)v7);
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
0x140021f64  push    rbp
0x140021f66  push    rbx
0x140021f67  push    rsi
0x140021f68  push    rdi
0x140021f69  push    r12
0x140021f6b  push    r14
0x140021f6d  lea     rbp, [rsp-388h]
0x140021f75  sub     rsp, 488h
0x140021f7c  mov     rax, cs:__security_cookie
0x140021f83  xor     rax, rsp
0x140021f86  mov     [rbp+3B0h+var_40], rax
0x140021f8d  mov     r14, rcx
0x140021f90  xor     r12d, r12d
0x140021f93  mov     edi, r12d
0x140021f96  mov     [rsp+4B0h+hObject], r12
0x140021f9b  mov     [rsp+4B0h+FileName], r12w
0x140021fa1  cmp     [rcx+54h], r12d
0x140021fa5  jz      short loc_140021FE5
0x140021fa7  mov     ebx, r12d
0x140021faa  lea     rsi, WPP_GLOBAL_Control
0x140021fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fb8  cmp     rcx, rsi
0x140021fbb  jz      loc_140022195
0x140021fc1  test    byte ptr [rcx+1Ch], 4
0x140021fc5  jz      loc_140022195
0x140021fcb  lea     edx, [r12+10h]
0x140021fd0  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140021fd7  mov     rcx, [rcx+10h]
0x140021fdb  call    WPP_SF_
0x140021fe0  jmp     loc_140022195
0x140021fe5  mov     dword ptr [rcx+54h], 1
0x140021fec  lea     rsi, WPP_GLOBAL_Control
0x140021ff3  mov     edi, 100h
0x140021ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fff  cmp     rcx, rsi
0x140022002  jz      short loc_140022029
0x140022004  test    byte ptr [rcx+1Ch], 8
0x140022008  jz      short loc_140022029
0x14002200a  mov     r9, [r14+5F70h]
0x140022011  add     r9, rdi
0x140022014  mov     edx, 11h
0x140022019  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022020  mov     rcx, [rcx+10h]
0x140022024  call    WPP_SF_S
0x140022029  mov     [rsp+4B0h+var_478], r12d
0x14002202e  mov     [rsp+4B0h+var_480], r12d
0x140022033  mov     [rsp+4B0h+var_488], r12
0x140022038  lea     r9, [rsp+4B0h+FileName]
0x14002203d  lea     r8, aXml; ".xml"
0x140022044  xor     edx, edx
0x140022046  lea     rcx, [rsp+4B0h+hObject]
0x14002204b  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140022050  mov     ebx, eax
0x140022052  test    eax, eax
0x140022054  jns     short loc_14002208A
0x140022056  mov     rcx, cs:WPP_GLOBAL_Control
0x14002205d  cmp     rcx, rsi
0x140022060  jz      short loc_140022080
0x140022062  test    byte ptr [rcx+1Ch], 1
0x140022066  jz      short loc_140022080
0x140022068  mov     edx, 12h
0x14002206d  mov     r9d, eax
0x140022070  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022077  mov     rcx, [rcx+10h]
0x14002207b  call    WPP_SF_d
0x140022080  mov     rdi, [rsp+4B0h+hObject]
0x140022085  jmp     loc_140022195
0x14002208a  mov     r9, [r14+5F70h]
0x140022091  add     r9, rdi
0x140022094  lea     r8, aSXml; "%s.xml"
0x14002209b  mov     edx, 104h; unsigned __int64
0x1400220a0  lea     rcx, [rbp+3B0h+var_250]; wchar_t *
0x1400220a7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400220ac  mov     ebx, eax
0x1400220ae  test    eax, eax
0x1400220b0  jns     short loc_1400220CB
0x1400220b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220b9  cmp     rcx, rsi
0x1400220bc  jz      short loc_140022080
0x1400220be  test    byte ptr [rcx+1Ch], 1
0x1400220c2  jz      short loc_140022080
0x1400220c4  mov     edx, 13h
0x1400220c9  jmp     short loc_14002206D
0x1400220cb  mov     rax, [r14]
0x1400220ce  mov     rdi, [rsp+4B0h+hObject]
0x1400220d3  mov     rdx, rdi
0x1400220d6  mov     rcx, r14
0x1400220d9  mov     rax, [rax+0B8h]
0x1400220e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400220e5  mov     ebx, eax
0x1400220e7  test    eax, eax
0x1400220e9  jns     short loc_14002211F
0x1400220eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220f2  cmp     rcx, rsi
0x1400220f5  jz      loc_140022195
0x1400220fb  test    byte ptr [rcx+1Ch], 1
0x1400220ff  jz      loc_140022195
0x140022105  mov     edx, 14h
0x14002210a  mov     r9d, eax
0x14002210d  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140022114  mov     rcx, [rcx+10h]
0x140022118  call    WPP_SF_d
0x14002211d  jmp     short loc_140022195
0x14002211f  mov     rcx, rdi; hObject
0x140022122  mov     rdi, r12
0x140022125  lea     rax, [rcx+1]
0x140022129  cmp     rax, 1
0x14002212d  jbe     short loc_14002213B
0x14002212f  call    cs:__imp_CloseHandle
0x140022136  nop     dword ptr [rax+rax+00h]
0x14002213b  mov     [rsp+4B0h+var_488], r12
0x140022140  lea     rax, [rbp+3B0h+var_250]
0x140022147  mov     [rsp+4B0h+var_490], rax
0x14002214c  mov     r9d, 40001h
0x140022152  mov     r8d, 5
0x140022158  lea     rdx, [rsp+4B0h+FileName]
0x14002215d  mov     rcx, [r14+5F78h]
0x140022164  call    cs:__imp_WerpAddFile
0x14002216b  nop     dword ptr [rax+rax+00h]
0x140022170  mov     ebx, eax
0x140022172  test    eax, eax
0x140022174  jns     short loc_140022192
0x140022176  mov     rcx, cs:WPP_GLOBAL_Control
0x14002217d  cmp     rcx, rsi
0x140022180  jz      short loc_140022195
0x140022182  test    byte ptr [rcx+1Ch], 1
0x140022186  jz      short loc_140022195
0x140022188  mov     edx, 15h
0x14002218d  jmp     loc_14002210A
0x140022192  mov     ebx, r12d
0x140022195  lea     rax, [rdi+1]
0x140022199  cmp     rax, 1
0x14002219d  jbe     short loc_1400221AE
0x14002219f  mov     rcx, rdi; hObject
0x1400221a2  call    cs:__imp_CloseHandle
0x1400221a9  nop     dword ptr [rax+rax+00h]
0x1400221ae  test    ebx, ebx
0x1400221b0  jns     short loc_1400221CC
0x1400221b2  cmp     [rsp+4B0h+FileName], r12w
0x1400221b8  jz      short loc_1400221CC
0x1400221ba  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x1400221bf  call    cs:__imp_DeleteFileW
0x1400221c6  nop     dword ptr [rax+rax+00h]
0x1400221cb  nop
0x1400221cc  mov     eax, ebx
0x1400221ce  mov     rcx, [rbp+3B0h+var_40]
0x1400221d5  xor     rcx, rsp; StackCookie
0x1400221d8  call    __security_check_cookie
0x1400221dd  add     rsp, 488h
0x1400221e4  pop     r14
0x1400221e6  pop     r12
0x1400221e8  pop     rdi
0x1400221e9  pop     rsi
0x1400221ea  pop     rbx
0x1400221eb  pop     rbp
0x1400221ec  retn
```

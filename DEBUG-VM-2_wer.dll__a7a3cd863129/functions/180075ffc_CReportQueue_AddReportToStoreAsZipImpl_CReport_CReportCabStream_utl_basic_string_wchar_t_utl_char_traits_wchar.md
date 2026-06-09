# CReportQueue::AddReportToStoreAsZipImpl(CReport *,CReportCabStream *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180075ffc`
- end: `0x1800764d2`
- name: `?AddReportToStoreAsZipImpl@CReportQueue@@AEAAJPEAVCReport@@PEAVCReportCabStream@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x180045458`

## callees

- `0x180007db4`
- `0x180007de0`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001abd8`
- `0x180039f70`
- `0x18003db78`
- `0x18003e864`
- `0x180045bdc`
- `0x18004bc2c`
- `0x18004ed14`
- `0x1800734c4`
- `0x1800740c4`
- `0x180075fb0`
- `0x180075ffc`
- `0x1800767b0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007639c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007639c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800763b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800763b6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800762d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800762d8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076392`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076392`

## string_xrefs

- `0x180076039`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800760b9`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800760f7`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076189`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800761f8`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800762ae`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076345`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800763d9`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CReportQueue::AddReportToStoreAsZipImpl(__int64 a1, CReport *a2, _DWORD *a3, __int64 a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // esi
  int UniqueIdentifier; // eax
  int v13; // eax
  const wchar_t *v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  int v21; // r8d
  int v22; // eax
  int v23; // r8d
  __int64 v24; // rdx
  DWORD LastError; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  int v29; // [rsp+28h] [rbp-E0h]
  int v30; // [rsp+28h] [rbp-E0h]
  unsigned int v31; // [rsp+28h] [rbp-E0h]
  wchar_t *v32[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v33[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h]
  wchar_t *v35[4]; // [rsp+70h] [rbp-98h] BYREF
  LPCWSTR v36[4]; // [rsp+90h] [rbp-78h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+B0h] [rbp-58h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+D0h] [rbp-38h] BYREF
  wchar_t *v39[5]; // [rsp+F0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]
  CReport *v41; // [rsp+150h] [rbp+48h] BYREF

  v41 = a2;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = 350;
      goto LABEL_3;
    }
    *((_DWORD *)a2 + 1656) = 9;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v39);
    v32[0] = 0;
    if ( (unsigned int)CReport::GetStorePath(v41, (const wchar_t **)v32) != -2147467259 && v32[0] && *v32[0] )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v39,
                               v32[0]) )
      {
        v8 = -2147024882;
        v9 = 2147942414LL;
        v10 = 368;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
          (const char *)v9,
          v29);
LABEL_57:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v39);
        return v8;
      }
      v11 = 1;
    }
    else
    {
      v11 = 0;
      v13 = CReportStore::ReserveReportDirInStore(a1, v41, v39);
      v8 = v13;
      if ( v13 < 0 )
      {
        v9 = (unsigned int)v13;
        v10 = 364;
        goto LABEL_11;
      }
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
    UniqueIdentifier = CReport::GetUniqueIdentifier(v41, v36);
    v8 = UniqueIdentifier;
    if ( UniqueIdentifier < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)UniqueIdentifier,
        v29);
LABEL_15:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
      goto LABEL_57;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
    v14 = L"zip";
    if ( !a3[4] )
      v14 = L"cab";
    v15 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v35,
            L"%s\\%s.%s",
            v39[0],
            v36[0],
            v14);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v15,
        v30);
LABEL_22:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
      goto LABEL_15;
    }
    v32[0] = (wchar_t *)&CFileByteStream::`vftable';
    v32[1] = 0;
    v16 = CFileByteStream::OpenFile((CFileByteStream *)v32, v35[0], 0x40000000u, 0, 0, 1u, 0x80u, 0);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 402;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v16,
        v31);
      CFileByteStream::~CFileByteStream((CFileByteStream *)v32);
      goto LABEL_22;
    }
    v16 = (*(__int64 (__fastcall **)(_DWORD *, wchar_t **, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, v32, 0);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 404;
      goto LABEL_25;
    }
    CFileByteStream::Close((CFileByteStream *)v32);
    CFileByteStream::~CFileByteStream((CFileByteStream *)v32);
    v33[0] = v35;
    v33[1] = &v41;
    LOBYTE(v34) = 1;
    *((_DWORD *)v41 + 1637) = 1;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
    v18 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpFileName,
            L"%s\\%s",
            v39[0],
            L"Report.wer");
    v8 = v18;
    if ( v18 < 0 )
    {
      v19 = 421;
LABEL_30:
      v20 = (unsigned int)v18;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)v20,
        v31);
LABEL_32:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
      tlx::_UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___::__UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___(v33);
      goto LABEL_22;
    }
    if ( GetFileAttributesW(lpFileName[0]) == -1 )
    {
      v8 = CReport::WriteReportToFile(v41, lpFileName[0], v21, 0);
      if ( (v8 & 0x80000000) != 0 )
      {
        *((_DWORD *)v41 + 1656) = 15;
        v20 = v8;
        v19 = 434;
        goto LABEL_31;
      }
      goto LABEL_49;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
    v22 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            lpExistingFileName,
            L"%s\\%s",
            v39[0],
            L"Report.wer.tmp");
    v8 = v22;
    if ( v22 >= 0 )
    {
      v22 = CReport::WriteReportToFile(v41, lpExistingFileName[0], v23, 0);
      v8 = v22;
      if ( v22 >= 0 )
      {
        if ( MoveFileExW(lpExistingFileName[0], lpFileName[0], 1u) )
        {
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
LABEL_49:
          LOBYTE(v34) = 0;
          if ( v11 )
          {
            v18 = UtilRecursiveRemoveDirectory(v39[0], 0, v35[0], lpFileName[0], v31);
            v8 = v18;
            if ( v18 )
            {
              if ( v18 != -2147024751 )
              {
                if ( v18 >= 0 )
                  goto LABEL_32;
                v19 = 467;
                goto LABEL_30;
              }
            }
          }
          *((_DWORD *)v41 + 11636) = *(_DWORD *)(a1 + 8);
          CReport::SetStorePath(v41, v39[0]);
          *((_DWORD *)v41 + 1656) = 14;
          if ( a4 )
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a4, v39);
LABEL_56:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
          tlx::_UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___::__UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___(v33);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
          v8 = 0;
          goto LABEL_57;
        }
        LastError = GetLastError();
        *((_DWORD *)v41 + 1656) = 15;
        if ( !DeleteFileW(lpExistingFileName[0]) )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x1C1, v26, v27);
        if ( !LastError )
        {
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
          goto LABEL_56;
        }
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1C3,
               (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
               (const char *)LastError,
               v31);
LABEL_39:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
        goto LABEL_32;
      }
      v24 = 442;
    }
    else
    {
      v24 = 440;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
      (const char *)(unsigned int)v22,
      v31);
    goto LABEL_39;
  }
  v7 = 349;
LABEL_3:
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
    (const char *)0x80070057LL,
    v29);
  return v8;
}

```

## disassembly

```asm
0x180075ffc  mov     rax, rsp
0x180075fff  mov     [rax+8], rbx
0x180076003  mov     [rax+18h], rsi
0x180076007  mov     [rax+10h], rdx
0x18007600b  push    rbp
0x18007600c  push    rdi
0x18007600d  push    r12
0x18007600f  push    r14
0x180076011  push    r15
0x180076013  lea     rbp, [rax-38h]
0x180076017  sub     rsp, 110h
0x18007601e  mov     r14, r9
0x180076021  mov     rdi, r8
0x180076024  mov     r15, rcx
0x180076027  xor     r12d, r12d
0x18007602a  test    rdx, rdx
0x18007602d  jnz     short loc_180076051
0x18007602f  mov     edx, 15Dh; void *
0x180076034  mov     ebx, 80070057h
0x180076039  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076040  mov     r9d, ebx; char *
0x180076043  mov     rcx, [rbp+38h]; this
0x180076047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007604c  jmp     loc_1800764B4
0x180076051  test    rdi, rdi
0x180076054  jnz     short loc_18007605D
0x180076056  mov     edx, 15Eh
0x18007605b  jmp     short loc_180076034
0x18007605d  mov     dword ptr [rdx+19E0h], 9
0x180076067  lea     rcx, [rbp+30h+var_48]; void *
0x18007606b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076070  nop
0x180076071  mov     [rsp+130h+var_F0], r12
0x180076076  lea     rdx, [rsp+130h+var_F0]; wchar_t **
0x18007607b  mov     rcx, [rbp+30h+arg_8]; this
0x18007607f  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x180076084  cmp     eax, 80004005h
0x180076089  jz      loc_180076117
0x18007608f  mov     rdx, [rsp+130h+var_F0]
0x180076094  test    rdx, rdx
0x180076097  jz      short loc_180076117
0x180076099  cmp     [rdx], r12w
0x18007609d  jz      short loc_180076117
0x18007609f  lea     rcx, [rbp+30h+var_48]
0x1800760a3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800760a8  test    al, al
0x1800760aa  jnz     short loc_1800760CE
0x1800760ac  mov     ebx, 8007000Eh
0x1800760b1  mov     r9d, ebx; char *
0x1800760b4  mov     edx, 170h; void *
0x1800760b9  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800760c0  mov     rcx, [rbp+38h]; this
0x1800760c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800760c9  jmp     loc_1800764AB
0x1800760ce  mov     esi, 1
0x1800760d3  lea     rcx, [rbp+30h+var_A8]; void *
0x1800760d7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800760dc  nop
0x1800760dd  lea     rdx, [rbp+30h+var_A8]
0x1800760e1  mov     rcx, [rbp+30h+arg_8]
0x1800760e5  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800760ea  mov     ebx, eax
0x1800760ec  test    eax, eax
0x1800760ee  jns     short loc_18007613D
0x1800760f0  mov     rcx, [rbp+38h]; this
0x1800760f4  mov     r9d, eax; char *
0x1800760f7  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800760fe  mov     edx, 17Dh; void *
0x180076103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076108  nop
0x180076109  lea     rcx, [rbp+30h+var_A8]; void *
0x18007610d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076112  jmp     loc_1800764AB
0x180076117  mov     esi, r12d
0x18007611a  lea     r8, [rbp+30h+var_48]
0x18007611e  mov     rdx, [rbp+30h+arg_8]
0x180076122  mov     rcx, r15
0x180076125  call    ?ReserveReportDirInStore@CReportStore@@QEAAJPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::ReserveReportDirInStore(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007612a  mov     ebx, eax
0x18007612c  test    eax, eax
0x18007612e  jns     short loc_1800760D3
0x180076130  mov     r9d, eax
0x180076133  mov     edx, 16Ch
0x180076138  jmp     loc_1800760B9
0x18007613d  lea     rcx, [rsp+130h+var_C8]; void *
0x180076142  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076147  nop
0x180076148  lea     rcx, aCab_1; "cab"
0x18007614f  lea     rax, aZip_0; "zip"
0x180076156  cmp     [rdi+10h], r12d
0x18007615a  cmovz   rax, rcx
0x18007615e  mov     [rsp+130h+var_110], rax; int
0x180076163  mov     r9, [rbp+30h+var_A8]
0x180076167  mov     r8, [rbp+30h+var_48]
0x18007616b  lea     rdx, aSSS_0; "%s\\%s.%s"
0x180076172  lea     rcx, [rsp+130h+var_C8]
0x180076177  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007617c  mov     ebx, eax
0x18007617e  test    eax, eax
0x180076180  jns     short loc_1800761AA
0x180076182  mov     rcx, [rbp+38h]; this
0x180076186  mov     r9d, eax; char *
0x180076189  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076190  mov     edx, 184h; void *
0x180076195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007619a  nop
0x18007619b  lea     rcx, [rsp+130h+var_C8]; void *
0x1800761a0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800761a5  jmp     loc_180076109
0x1800761aa  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x1800761b1  mov     [rsp+130h+var_F0], rax
0x1800761b6  mov     [rsp+130h+var_E8], r12
0x1800761bb  mov     [rsp+130h+var_F8], r12; void *
0x1800761c0  mov     [rsp+130h+var_100], 80h; unsigned int
0x1800761c8  mov     [rsp+130h+var_108], 1; unsigned int
0x1800761d0  mov     [rsp+130h+var_110], r12; int
0x1800761d5  xor     r9d, r9d; unsigned int
0x1800761d8  mov     r8d, 40000000h; unsigned int
0x1800761de  mov     rdx, [rsp+130h+var_C8]; wchar_t *
0x1800761e3  lea     rcx, [rsp+130h+var_F0]; this
0x1800761e8  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800761ed  mov     ebx, eax
0x1800761ef  test    eax, eax
0x1800761f1  jns     short loc_180076218
0x1800761f3  mov     edx, 192h; void *
0x1800761f8  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800761ff  mov     r9d, eax; char *
0x180076202  mov     rcx, [rbp+38h]; this
0x180076206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007620b  nop
0x18007620c  lea     rcx, [rsp+130h+var_F0]; this
0x180076211  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x180076216  jmp     short loc_18007619B
0x180076218  mov     rax, [rdi]
0x18007621b  xor     r8d, r8d
0x18007621e  lea     rdx, [rsp+130h+var_F0]
0x180076223  mov     rcx, rdi
0x180076226  mov     rax, [rax+18h]
0x18007622a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007622f  mov     ebx, eax
0x180076231  test    eax, eax
0x180076233  jns     short loc_18007623C
0x180076235  mov     edx, 194h
0x18007623a  jmp     short loc_1800761F8
0x18007623c  lea     rcx, [rsp+130h+var_F0]; this
0x180076241  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x180076246  nop
0x180076247  lea     rcx, [rsp+130h+var_F0]; this
0x18007624c  call    ??1CFileByteStream@@UEAA@XZ; CFileByteStream::~CFileByteStream(void)
0x180076251  lea     rax, [rsp+130h+var_C8]
0x180076256  mov     [rsp+130h+var_E0], rax
0x18007625b  lea     rax, [rbp+30h+arg_8]
0x18007625f  mov     qword ptr [rsp+130h+var_D8], rax
0x180076264  mov     byte ptr [rsp+130h+var_D0], 1
0x180076269  mov     rax, [rbp+30h+arg_8]
0x18007626d  mov     dword ptr [rax+1994h], 1
0x180076277  lea     rcx, [rbp+30h+lpFileName]; void *
0x18007627b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076280  nop
0x180076281  lea     r9, aReportWer; "Report.wer"
0x180076288  mov     r8, [rbp+30h+var_48]
0x18007628c  lea     rdx, aSS; "%s\\%s"
0x180076293  lea     rcx, [rbp+30h+lpFileName]
0x180076297  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007629c  mov     ebx, eax
0x18007629e  test    eax, eax
0x1800762a0  jns     short loc_1800762D4
0x1800762a2  mov     edx, 1A5h; void *
0x1800762a7  mov     r9d, eax; char *
0x1800762aa  mov     rcx, [rbp+38h]; this
0x1800762ae  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800762b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800762ba  nop
0x1800762bb  lea     rcx, [rbp+30h+lpFileName]; void *
0x1800762bf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800762c4  nop
0x1800762c5  lea     rcx, [rsp+130h+var_E0]
0x1800762ca  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x1800762cf  jmp     loc_18007619B
0x1800762d4  mov     rcx, [rbp+30h+lpFileName]; lpFileName
0x1800762d8  call    cs:__imp_GetFileAttributesW
0x1800762de  cmp     eax, 0FFFFFFFFh
0x1800762e1  jnz     short loc_180076315
0x1800762e3  xor     r9d, r9d; unsigned int
0x1800762e6  mov     rdx, [rbp+30h+lpFileName]; wchar_t *
0x1800762ea  mov     rcx, [rbp+30h+arg_8]; this
0x1800762ee  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x1800762f3  mov     ebx, eax
0x1800762f5  test    eax, eax
0x1800762f7  jns     loc_180076408
0x1800762fd  mov     rax, [rbp+30h+arg_8]
0x180076301  mov     dword ptr [rax+19E0h], 0Fh
0x18007630b  mov     r9d, ebx
0x18007630e  mov     edx, 1B2h
0x180076313  jmp     short loc_1800762AA
0x180076315  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180076319  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007631e  nop
0x18007631f  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x180076326  mov     r8, [rbp+30h+var_48]
0x18007632a  lea     rdx, aSS; "%s\\%s"
0x180076331  lea     rcx, [rbp+30h+lpExistingFileName]
0x180076335  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007633a  mov     ebx, eax
0x18007633c  test    eax, eax
0x18007633e  jns     short loc_180076367
0x180076340  mov     edx, 1B8h; void *
0x180076345  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007634c  mov     r9d, eax; char *
0x18007634f  mov     rcx, [rbp+38h]; this
0x180076353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076358  nop
0x180076359  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x18007635d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076362  jmp     loc_1800762BB
0x180076367  xor     r9d, r9d; unsigned int
0x18007636a  mov     rdx, [rbp+30h+lpExistingFileName]; wchar_t *
0x18007636e  mov     rcx, [rbp+30h+arg_8]; this
0x180076372  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x180076377  mov     ebx, eax
0x180076379  test    eax, eax
0x18007637b  jns     short loc_180076384
0x18007637d  mov     edx, 1BAh
0x180076382  jmp     short loc_180076345
0x180076384  mov     r8d, 1; dwFlags
0x18007638a  mov     rdx, [rbp+30h+lpFileName]; lpNewFileName
0x18007638e  mov     rcx, [rbp+30h+lpExistingFileName]; lpExistingFileName
0x180076392  call    cs:__imp_MoveFileExW
0x180076398  test    eax, eax
0x18007639a  jnz     short loc_1800763FF
0x18007639c  call    cs:__imp_GetLastError
0x1800763a2  mov     ebx, eax
0x1800763a4  mov     rcx, [rbp+30h+arg_8]
0x1800763a8  mov     dword ptr [rcx+19E0h], 0Fh
0x1800763b2  mov     rcx, [rbp+30h+lpExistingFileName]; lpFileName
0x1800763b6  call    cs:__imp_DeleteFileW
0x1800763bc  mov     rcx, [rbp+38h]; this
0x1800763c0  test    eax, eax
0x1800763c2  jnz     short loc_1800763CE
0x1800763c4  mov     edx, 1C1h; void *
0x1800763c9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800763ce  test    ebx, ebx
0x1800763d0  jz      short loc_1800763F1
0x1800763d2  mov     rcx, [rbp+38h]; this
0x1800763d6  mov     r9d, ebx; char *
0x1800763d9  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800763e0  mov     edx, 1C3h; void *
0x1800763e5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800763ea  mov     ebx, eax
0x1800763ec  jmp     loc_180076359
0x1800763f1  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x1800763f5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800763fa  jmp     loc_18007647F
0x1800763ff  lea     rcx, [rbp+30h+lpExistingFileName]; void *
0x180076403  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076408  mov     byte ptr [rsp+130h+var_D0], r12b
0x18007640d  test    esi, esi
0x18007640f  jz      short loc_180076444
0x180076411  mov     r9, [rbp+30h+lpFileName]; wchar_t *
0x180076415  mov     r8, [rsp+130h+var_C8]; wchar_t *
0x18007641a  xor     edx, edx; int
0x18007641c  mov     rcx, [rbp+30h+var_48]; wchar_t *
0x180076420  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x180076425  mov     ebx, eax
0x180076427  test    eax, eax
0x180076429  jz      short loc_180076444
0x18007642b  cmp     eax, 80070091h
0x180076430  jz      short loc_180076444
0x180076432  test    eax, eax
0x180076434  jns     loc_1800762BB
0x18007643a  mov     edx, 1D3h
0x18007643f  jmp     loc_1800762A7
0x180076444  mov     ecx, [r15+8]
0x180076448  mov     rax, [rbp+30h+arg_8]
0x18007644c  mov     [rax+0B5D0h], ecx
0x180076452  mov     rdx, [rbp+30h+var_48]; wchar_t *
0x180076456  mov     rcx, [rbp+30h+arg_8]; this
0x18007645a  call    ?SetStorePath@CReport@@QEAAJPEB_W@Z; CReport::SetStorePath(wchar_t const *)
0x18007645f  mov     rax, [rbp+30h+arg_8]
0x180076463  mov     dword ptr [rax+19E0h], 0Eh
0x18007646d  test    r14, r14
0x180076470  jz      short loc_18007647F
0x180076472  lea     rdx, [rbp+30h+var_48]
0x180076476  mov     rcx, r14
0x180076479  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18007647e  nop
0x18007647f  lea     rcx, [rbp+30h+lpFileName]; void *
0x180076483  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076488  nop
0x180076489  lea     rcx, [rsp+130h+var_E0]
0x18007648e  call    tlx___UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf_______UndoSolo__lambda_d94280cfbb51293804d685e486ee07cf___
0x180076493  nop
0x180076494  lea     rcx, [rsp+130h+var_C8]; void *
0x180076499  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007649e  nop
0x18007649f  lea     rcx, [rbp+30h+var_A8]; void *
0x1800764a3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800764a8  mov     ebx, r12d
0x1800764ab  lea     rcx, [rbp+30h+var_48]; void *
0x1800764af  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
  ... truncated ...
```

# File::OpenFile(utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800227b4`
- end: `0x180022d54`
- name: `?OpenFile@File@@AEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `1440`
- prototype: `__int64 __fastcall(File *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180030e88`
- `0x180031754`

## callees

- `0x18001585c`
- `0x1800223c8`
- `0x1800227b4`
- `0x180022d7c`
- `0x180023548`
- `0x1800311d4`
- `0x180031200`
- `0x180033258`
- `0x180034874`
- `0x180034988`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b95`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800228e9`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800228e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800228c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800228c7`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800229a8`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800229dc`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180022a15`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800229a8`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800229dc`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180022a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall File::OpenFile(File *this)
{
  const WCHAR *v2; // rcx
  char v3; // r14
  HANDLE FileW; // rax
  int IsCreated; // eax
  bool v6; // di
  HANDLE v7; // r14
  int v8; // r8d
  DWORD v9; // r14d
  DWORD LastError; // eax
  __int64 v11; // r8
  int v12; // r8d
  int v13; // r14d
  unsigned int v14; // r14d
  LastErrInfo *v15; // rcx
  HANDLE v17; // [rsp+40h] [rbp-30h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+64h] [rbp-Ch]
  char v22; // [rsp+6Ch] [rbp-4h]
  File *v23; // [rsp+B0h] [rbp+40h] BYREF
  char *v24; // [rsp+C0h] [rbp+50h] BYREF
  char *v25; // [rsp+C8h] [rbp+58h] BYREF

  *((_BYTE *)this + 827) = 0;
  *((_DWORD *)this + 203) = 0;
  *((_QWORD *)this + 97) = -1;
  *((_QWORD *)this + 98) = -1;
  *((_QWORD *)this + 21) = -1;
  *((_QWORD *)this + 102) = 0;
  *((_BYTE *)this + 826) = 0;
  *((_BYTE *)this + 838) = 0;
  *((_QWORD *)this + 96) = -1;
  v2 = (const WCHAR *)*((_QWORD *)this + 85);
  if ( v2 == *((const WCHAR **)this + 86) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 87);
    }
    pExceptionObject = 0;
    v19 = 0;
    v20 = 87;
    v21 = 0x19FFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = *((_BYTE *)this + 825) & 4;
  FileW = CreateFileW(v2, v3 != 0 ? 0x80000000 : -1073741824, 1u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 672, FileW);
  if ( (unsigned __int64)(*((_QWORD *)this + 84) + 1LL) <= 1 )
  {
    LastError = GetLastError();
    if ( v3 )
    {
      v14 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, LastError, *((_QWORD *)this + 85));
        v15 = WPP_GLOBAL_Control;
      }
      if ( !v14 )
        v14 = 1287;
      if ( v15 != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v15 + 7) & 0x8000) != 0
        && *((_BYTE *)v15 + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)v15 + 2), 27, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v14);
      }
      pExceptionObject = 0;
      v19 = 0;
      v20 = v14;
      v21 = 0x243FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    *((_BYTE *)this + 832) = 1;
    if ( (*((_BYTE *)this + 825) & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v11, *((_QWORD *)this + 85));
      }
    }
    else if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v11, LastError, *((_QWORD *)this + 85));
    }
    IsCreated = File::EnsureFileIsCreated(this);
    v13 = IsCreated;
    if ( IsCreated )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v12, IsCreated, *((_QWORD *)this + 85));
      }
      *(_QWORD *)&pExceptionObject = &word_18004024A;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v19 = 0;
      v20 = v13;
      v21 = -1;
      v22 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    if ( GetFileType(*((HANDLE *)this + 84)) != 1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 4300);
      }
      pExceptionObject = 0;
      v19 = 0;
      v20 = 4300;
      v21 = 0x1B2FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v23 = this;
    LOBYTE(IsCreated) = File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
    if ( (*((_BYTE *)this + 136) & 1) != 0 )
    {
      v6 = (*((_BYTE *)this + 825) & 0x10) == 0;
      if ( v3 && (*((_BYTE *)this + 825) & 0x10) == 0 )
      {
        v7 = ReOpenFile(*((HANDLE *)this + 84), 0x80000000, 3u, 0);
        v17 = v7;
        if ( (unsigned __int64)v7 + 1 <= 1 )
        {
          v6 = 0;
          *((_BYTE *)this + 825) |= 0x10u;
        }
        else
        {
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 672, 0);
          v25 = (char *)ReOpenFile(v7, 0xC0000000, 1u, 0);
          if ( v25 == (char *)-1LL || v25 + 1 == (char *)1 )
          {
            v24 = (char *)ReOpenFile(v7, 0x80000000, 1u, 0);
            if ( v24 == (char *)-1LL || v24 + 1 == (char *)1 )
            {
              v9 = GetLastError();
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v8, v9, *((_QWORD *)this + 85));
              }
              *(_QWORD *)&pExceptionObject = &word_18004024A;
              *((_QWORD *)&pExceptionObject + 1) = 0;
              v19 = 0;
              v20 = v9;
              v21 = -1;
              v22 = 0;
              throw (EvtException *)&pExceptionObject;
            }
            tlx::unique_any<tlx::file_handle_traits>::operator=((char *)this + 672, &v24);
            v6 = 0;
            *((_BYTE *)this + 825) |= 0x10u;
            File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
            tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v24);
          }
          else
          {
            tlx::unique_any<tlx::file_handle_traits>::operator=((char *)this + 672, &v25);
            File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
          }
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
        }
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
      }
      LOBYTE(IsCreated) = File::Recover(this);
      if ( !v6 )
      {
        LOBYTE(IsCreated) = *((_BYTE *)this + 824);
        if ( (IsCreated & 0xE) == 0 )
        {
          if ( (_BYTE)IsCreated )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 1500);
            }
            pExceptionObject = 0;
            v19 = 0;
            v20 = 1500;
            v21 = 0x216FFFFFFFFLL;
            throw (EvtException *)&pExceptionObject;
          }
        }
      }
    }
    *((_BYTE *)this + 829) = 1;
  }
  return IsCreated;
}

```

## disassembly

```asm
0x1800227b4  push    rbp
0x1800227b6  push    rbx
0x1800227b7  push    rsi
0x1800227b8  push    rdi
0x1800227b9  push    r12
0x1800227bb  push    r14
0x1800227bd  push    r15
0x1800227bf  mov     rbp, rsp
0x1800227c2  sub     rsp, 70h
0x1800227c6  mov     r15, rdx
0x1800227c9  mov     rbx, rcx
0x1800227cc  xor     r12d, r12d
0x1800227cf  mov     [rcx+33Bh], r12b
0x1800227d6  mov     [rcx+32Ch], r12d
0x1800227dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800227e1  mov     [rcx+308h], rax
0x1800227e8  mov     [rcx+310h], rax
0x1800227ef  mov     [rcx+0A8h], rax
0x1800227f6  mov     [rcx+330h], r12
0x1800227fd  mov     [rcx+33Ah], r12b
0x180022804  mov     [rcx+346h], r12b
0x18002280b  mov     [rcx+300h], rax
0x180022812  mov     rcx, [rcx+2A8h]; lpFileName
0x180022819  cmp     rcx, [rbx+2B0h]
0x180022820  jnz     short loc_18002288C
0x180022822  lea     rdi, WPP_GLOBAL_Control
0x180022829  lea     ebx, [rax+58h]
0x18002282c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022833  cmp     rcx, rdi
0x180022836  jz      short loc_18002285E
0x180022838  mov     esi, 8000h
0x18002283d  test    [rcx+1Ch], esi
0x180022840  jz      short loc_18002285E
0x180022842  cmp     byte ptr [rcx+19h], 2
0x180022846  jb      short loc_18002285E
0x180022848  lea     edx, [rax+0Fh]
0x18002284b  mov     r9d, ebx
0x18002284e  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180022855  mov     rcx, [rcx+10h]
0x180022859  call    WPP_SF_D
0x18002285e  xorps   xmm0, xmm0
0x180022861  movdqu  [rbp+pExceptionObject], xmm0
0x180022866  mov     [rbp+var_18], r12
0x18002286a  mov     [rbp+var_10], ebx
0x18002286d  mov     dword ptr [rbp+var_C], 0FFFFFFFFh
0x180022874  mov     dword ptr [rbp+var_C+4], 19Fh
0x18002287b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022882  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022886  call    _CxxThrowException_0
0x18002288c  mov     r14b, [rbx+339h]
0x180022893  and     r14b, 4
0x180022897  lea     rsi, [rbx+2A0h]
0x18002289e  mov     al, r14b
0x1800228a1  neg     al
0x1800228a3  sbb     edx, edx
0x1800228a5  mov     eax, 0C0000000h
0x1800228aa  and     edx, eax
0x1800228ac  add     edx, eax; dwDesiredAccess
0x1800228ae  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x1800228b3  mov     [rsp+70h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800228b8  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x1800228c0  xor     r9d, r9d; lpSecurityAttributes
0x1800228c3  lea     r8d, [r9+1]; dwShareMode
0x1800228c7  call    cs:__imp_CreateFileW
0x1800228cd  mov     rdx, rax
0x1800228d0  mov     rcx, rsi
0x1800228d3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800228d8  mov     rcx, [rsi]; hFile
0x1800228db  lea     rax, [rcx+1]
0x1800228df  cmp     rax, 1
0x1800228e3  jbe     loc_180022B95
0x1800228e9  call    cs:__imp_GetFileType
0x1800228ef  cmp     eax, 1
0x1800228f2  jz      short loc_180022962
0x1800228f4  lea     rdi, WPP_GLOBAL_Control
0x1800228fb  mov     ebx, 10CCh
0x180022900  mov     rcx, cs:WPP_GLOBAL_Control
0x180022907  cmp     rcx, rdi
0x18002290a  jz      short loc_180022934
0x18002290c  mov     esi, 8000h
0x180022911  test    [rcx+1Ch], esi
0x180022914  jz      short loc_180022934
0x180022916  cmp     byte ptr [rcx+19h], 2
0x18002291a  jb      short loc_180022934
0x18002291c  mov     edx, 0Fh
0x180022921  mov     r9d, ebx
0x180022924  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x18002292b  mov     rcx, [rcx+10h]
0x18002292f  call    WPP_SF_D
0x180022934  xorps   xmm0, xmm0
0x180022937  movdqu  [rbp+pExceptionObject], xmm0
0x18002293c  mov     [rbp+var_18], r12
0x180022940  mov     [rbp+var_10], ebx
0x180022943  mov     dword ptr [rbp+var_C], 0FFFFFFFFh
0x18002294a  mov     dword ptr [rbp+var_C+4], 1B2h
0x180022951  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022958  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002295c  call    _CxxThrowException_0
0x180022962  mov     [rbp+arg_0], rbx
0x180022966  lea     rcx, [rbp+arg_0]
0x18002296a  call    _File__OpenFile____11____lambda_1___operator__
0x18002296f  test    byte ptr [rbx+88h], 1
0x180022976  jz      loc_180022B7F
0x18002297c  mov     al, [rbx+339h]
0x180022982  and     al, 10h
0x180022984  setz    dil
0x180022988  test    r14b, r14b
0x18002298b  jz      loc_180022AF0
0x180022991  test    al, al
0x180022993  jnz     loc_180022AF0
0x180022999  xor     r9d, r9d; dwFlagsAndAttributes
0x18002299c  mov     edx, 80000000h; dwDesiredAccess
0x1800229a1  lea     r8d, [r9+3]; dwShareMode
0x1800229a5  mov     rcx, [rsi]; hOriginalFile
0x1800229a8  call    cs:__imp_ReOpenFile
0x1800229ae  mov     r14, rax
0x1800229b1  mov     [rbp+var_30], rax
0x1800229b5  lea     rcx, [rax+1]
0x1800229b9  cmp     rcx, 1
0x1800229bd  jbe     loc_180022ADD
0x1800229c3  xor     edx, edx
0x1800229c5  mov     rcx, rsi
0x1800229c8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800229cd  xor     r9d, r9d; dwFlagsAndAttributes
0x1800229d0  mov     edx, 0C0000000h; dwDesiredAccess
0x1800229d5  lea     r8d, [r9+1]; dwShareMode
0x1800229d9  mov     rcx, r14; hOriginalFile
0x1800229dc  call    cs:__imp_ReOpenFile
0x1800229e2  mov     [rbp+arg_18], rax
0x1800229e6  inc     rax
0x1800229e9  cmp     rax, 1
0x1800229ed  jbe     short loc_180022A06
0x1800229ef  lea     rdx, [rbp+arg_18]
0x1800229f3  mov     rcx, rsi
0x1800229f6  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800229fb  lea     rcx, [rbp+arg_0]
0x1800229ff  call    _File__OpenFile____11____lambda_1___operator__
0x180022a04  jmp     short loc_180022A52
0x180022a06  xor     r9d, r9d; dwFlagsAndAttributes
0x180022a09  mov     edx, 80000000h; dwDesiredAccess
0x180022a0e  lea     r8d, [r9+1]; dwShareMode
0x180022a12  mov     rcx, r14; hOriginalFile
0x180022a15  call    cs:__imp_ReOpenFile
0x180022a1b  mov     [rbp+arg_10], rax
0x180022a1f  inc     rax
0x180022a22  cmp     rax, 1
0x180022a26  jbe     short loc_180022A60
0x180022a28  lea     rdx, [rbp+arg_10]
0x180022a2c  mov     rcx, rsi
0x180022a2f  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180022a34  mov     dil, r12b
0x180022a37  or      byte ptr [rbx+339h], 10h
0x180022a3e  lea     rcx, [rbp+arg_0]
0x180022a42  call    _File__OpenFile____11____lambda_1___operator__
0x180022a47  nop
0x180022a48  lea     rcx, [rbp+arg_10]
0x180022a4c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022a51  nop
0x180022a52  lea     rcx, [rbp+arg_18]
0x180022a56  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022a5b  jmp     loc_180022AE7
0x180022a60  call    cs:__imp_GetLastError
0x180022a66  mov     r14d, eax
0x180022a69  lea     rdi, WPP_GLOBAL_Control
0x180022a70  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a77  cmp     rcx, rdi
0x180022a7a  jz      short loc_180022AA9
0x180022a7c  mov     esi, 8000h
0x180022a81  test    [rcx+1Ch], esi
0x180022a84  jz      short loc_180022AA9
0x180022a86  cmp     byte ptr [rcx+19h], 2
0x180022a8a  jb      short loc_180022AA9
0x180022a8c  mov     edx, 14h
0x180022a91  mov     rax, [rbx+2A8h]
0x180022a98  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180022a9d  mov     r9d, r14d
0x180022aa0  mov     rcx, [rcx+10h]
0x180022aa4  call    WPP_SF_DS
0x180022aa9  lea     rax, word_18004024A
0x180022ab0  mov     qword ptr [rbp+pExceptionObject], rax
0x180022ab4  mov     qword ptr [rbp+pExceptionObject+8], r12
0x180022ab8  mov     [rbp+var_18], r12
0x180022abc  mov     [rbp+var_10], r14d
0x180022ac0  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180022ac8  mov     [rbp+var_4], r12b
0x180022acc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022ad3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022ad7  call    _CxxThrowException_0
0x180022add  mov     dil, r12b
0x180022ae0  or      byte ptr [rbx+339h], 10h
0x180022ae7  lea     rcx, [rbp+var_30]
0x180022aeb  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022af0  mov     r8, r15
0x180022af3  mov     dl, dil
0x180022af6  mov     rcx, rbx; this
0x180022af9  call    ?Recover@File@@AEAAX_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::Recover(bool,utl::unique_lock<utl::shared_mutex> &)
0x180022afe  test    dil, dil
0x180022b01  jnz     short loc_180022B7F
0x180022b03  mov     al, [rbx+338h]
0x180022b09  test    al, 0Eh
0x180022b0b  jnz     short loc_180022B7F
0x180022b0d  test    al, al
0x180022b0f  jz      short loc_180022B7F
0x180022b11  lea     rdi, WPP_GLOBAL_Control
0x180022b18  mov     ebx, 5DCh
0x180022b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b24  cmp     rcx, rdi
0x180022b27  jz      short loc_180022B51
0x180022b29  mov     esi, 8000h
0x180022b2e  test    [rcx+1Ch], esi
0x180022b31  jz      short loc_180022B51
0x180022b33  cmp     byte ptr [rcx+19h], 2
0x180022b37  jb      short loc_180022B51
0x180022b39  mov     edx, 15h
0x180022b3e  mov     r9d, ebx
0x180022b41  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180022b48  mov     rcx, [rcx+10h]
0x180022b4c  call    WPP_SF_D
0x180022b51  xorps   xmm0, xmm0
0x180022b54  movdqu  [rbp+pExceptionObject], xmm0
0x180022b59  mov     [rbp+var_18], r12
0x180022b5d  mov     [rbp+var_10], ebx
0x180022b60  mov     dword ptr [rbp+var_C], 0FFFFFFFFh
0x180022b67  mov     dword ptr [rbp+var_C+4], 216h
0x180022b6e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022b75  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022b79  call    _CxxThrowException_0
0x180022b7f  mov     byte ptr [rbx+33Dh], 1
0x180022b86  add     rsp, 70h
0x180022b8a  pop     r15
0x180022b8c  pop     r14
0x180022b8e  pop     r12
0x180022b90  pop     rdi
0x180022b91  pop     rsi
0x180022b92  pop     rbx
0x180022b93  pop     rbp
0x180022b94  retn
0x180022b95  call    cs:__imp_GetLastError
0x180022b9b  test    r14b, r14b
0x180022b9e  jnz     loc_180022CA7
0x180022ba4  mov     r9d, eax
0x180022ba7  mov     byte ptr [rbx+340h], 1
0x180022bae  mov     esi, 8000h
0x180022bb3  test    byte ptr [rbx+339h], 8
0x180022bba  jnz     short loc_180022BF6
0x180022bbc  lea     rdi, WPP_GLOBAL_Control
0x180022bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bca  cmp     rcx, rdi
0x180022bcd  jz      short loc_180022C29
0x180022bcf  test    [rcx+1Ch], esi
0x180022bd2  jz      short loc_180022C29
0x180022bd4  cmp     byte ptr [rcx+19h], 4
0x180022bd8  jb      short loc_180022C29
0x180022bda  mov     edx, 17h
0x180022bdf  mov     rax, [rbx+2A8h]
0x180022be6  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180022beb  mov     rcx, [rcx+10h]
0x180022bef  call    WPP_SF_DS
0x180022bf4  jmp     short loc_180022C29
0x180022bf6  lea     rdi, WPP_GLOBAL_Control
0x180022bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c04  cmp     rcx, rdi
0x180022c07  jz      short loc_180022C29
0x180022c09  test    [rcx+1Ch], esi
0x180022c0c  jz      short loc_180022C29
0x180022c0e  cmp     byte ptr [rcx+19h], 4
0x180022c12  jb      short loc_180022C29
0x180022c14  mov     edx, 18h
0x180022c19  mov     r9, [rbx+2A8h]
0x180022c20  mov     rcx, [rcx+10h]
0x180022c24  call    WPP_SF_S
0x180022c29  mov     rdx, r15
0x180022c2c  mov     rcx, rbx; this
0x180022c2f  call    ?EnsureFileIsCreated@File@@AEAAKAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::EnsureFileIsCreated(utl::unique_lock<utl::shared_mutex> &)
0x180022c34  mov     r14d, eax
0x180022c37  test    eax, eax
0x180022c39  jz      loc_180022B86
0x180022c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c46  cmp     rcx, rdi
0x180022c49  jz      short loc_180022C73
0x180022c4b  test    [rcx+1Ch], esi
0x180022c4e  jz      short loc_180022C73
0x180022c50  cmp     byte ptr [rcx+19h], 2
0x180022c54  jb      short loc_180022C73
0x180022c56  mov     edx, 19h
0x180022c5b  mov     rax, [rbx+2A8h]
0x180022c62  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180022c67  mov     r9d, r14d
0x180022c6a  mov     rcx, [rcx+10h]
0x180022c6e  call    WPP_SF_DS
0x180022c73  lea     rax, word_18004024A
0x180022c7a  mov     qword ptr [rbp+pExceptionObject], rax
0x180022c7e  mov     qword ptr [rbp+pExceptionObject+8], r12
0x180022c82  mov     [rbp+var_18], r12
0x180022c86  mov     [rbp+var_10], r14d
0x180022c8a  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x180022c92  mov     [rbp+var_4], r12b
0x180022c96  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180022c9d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022ca1  call    _CxxThrowException_0
  ... truncated ...
```

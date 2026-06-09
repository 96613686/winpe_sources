# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x140015580`
- end: `0x1400158df`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `863`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1400158e8`
- `0x140044974`

## callees

- `0x140001150`
- `0x140001368`
- `0x140002490`
- `0x140002748`
- `0x1400151b8`
- `0x140015580`
- `0x14005f588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015793`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400155fa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400155fa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400155dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400155dc`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400155bb`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1400155bb`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName)
{
  DWORD FileAttributesW; // eax
  signed int v3; // eax
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  signed int LastError; // eax
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-39h] BYREF
  WCHAR *v13; // [rsp+38h] [rbp-31h] BYREF
  void *Src; // [rsp+40h] [rbp-29h]
  char *v15; // [rsp+48h] [rbp-21h]
  _WORD v16[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        v12 = v6;
        v18 = &v12;
        v19 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &dword_140072EEC, 0, 0, 3, v17);
      }
      goto LABEL_36;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0) && !CreateDirectoryW(lpFileName, 0) )
    {
      v3 = GetLastError();
      v6 = v3;
      if ( v3 > 0 )
        v6 = (unsigned __int16)v3 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        v12 = v6;
        v13 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          qword_14007E018,
          (unsigned int)&unk_140072EA8,
          v4,
          v5,
          (__int64)&v13,
          (__int64)&v12);
      }
      *lpFileName = 0;
LABEL_36:
      if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 )
      {
        v10 = qword_14007E018 & 8;
        if ( v10 == qword_14007E018 )
        {
          v12 = v6;
          v13 = lpFileName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_140072E3B,
            v4,
            v5,
            (__int64)&v13,
            (__int64)&v12);
        }
      }
      return (unsigned int)v6;
    }
    v16[0] = 0;
    Src = v16;
    v15 = (char *)v16;
    if ( (unsigned int)UtilGetFinalPath(lpFileName) )
    {
      v7 = (v15 - (_BYTE *)Src) >> 1;
      if ( v7 >= 0x104 )
      {
        *lpFileName = 0;
        v6 = -2147024809;
        if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
        {
          v12 = -2147024809;
          v18 = &v12;
          v19 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &dword_140072E74, 0, 0, 3, v17);
        }
        if ( Src != v16 )
          operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_36;
      }
      v8 = v7;
      memcpy_0(lpFileName, Src, v8 * 2);
      lpFileName[v8] = 0;
    }
    if ( Src != v16 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v6 = 0;
    goto LABEL_36;
  }
  if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, qword_140072F20, 0, 0, 2, v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140015580  push    rbp
0x140015582  push    rbx
0x140015583  push    rdi
0x140015584  push    r14
0x140015586  lea     rbp, [rsp-3Fh]
0x14001558b  sub     rsp, 0A8h
0x140015592  mov     rax, cs:__security_cookie
0x140015599  xor     rax, rsp
0x14001559c  mov     [rbp+57h+var_30], rax
0x1400155a0  xor     r14d, r14d
0x1400155a3  mov     rdi, rcx
0x1400155a6  test    rcx, rcx
0x1400155a9  jz      loc_14001586E
0x1400155af  mov     [rcx], r14w
0x1400155b3  mov     rdx, rcx
0x1400155b6  mov     ecx, 104h
0x1400155bb  call    cs:__imp_GetTempPath2W
0x1400155c2  nop     dword ptr [rax+rax+00h]
0x1400155c7  test    eax, eax
0x1400155c9  jz      loc_140015793
0x1400155cf  cmp     [rdi], r14w
0x1400155d3  jz      loc_140015793
0x1400155d9  mov     rcx, rdi; lpFileName
0x1400155dc  call    cs:__imp_GetFileAttributesW
0x1400155e3  nop     dword ptr [rax+rax+00h]
0x1400155e8  cmp     eax, 0FFFFFFFFh
0x1400155eb  jz      short loc_1400155F5
0x1400155ed  test    al, 10h
0x1400155ef  jnz     loc_140015685
0x1400155f5  xor     edx, edx; lpSecurityAttributes
0x1400155f7  mov     rcx, rdi; lpPathName
0x1400155fa  call    cs:__imp_CreateDirectoryW
0x140015601  nop     dword ptr [rax+rax+00h]
0x140015606  test    eax, eax
0x140015608  jnz     short loc_140015685
0x14001560a  call    cs:__imp_GetLastError
0x140015611  nop     dword ptr [rax+rax+00h]
0x140015616  mov     ebx, eax
0x140015618  test    eax, eax
0x14001561a  jle     short loc_140015625
0x14001561c  movzx   ebx, ax
0x14001561f  or      ebx, 80070000h
0x140015625  test    ebx, ebx
0x140015627  mov     eax, 80004005h
0x14001562c  cmovns  ebx, eax
0x14001562f  mov     eax, cs:dword_14007E000
0x140015635  cmp     eax, 2
0x140015638  jbe     short loc_14001567C
0x14001563a  mov     rcx, cs:qword_14007E018
0x140015641  mov     rax, cs:qword_14007E010
0x140015648  test    al, 8
0x14001564a  jz      short loc_14001567C
0x14001564c  mov     rax, rcx
0x14001564f  and     eax, 8
0x140015652  cmp     rax, rcx
0x140015655  jnz     short loc_14001567C
0x140015657  lea     rax, [rbp+57h+var_90]
0x14001565b  mov     [rbp+57h+var_90], ebx
0x14001565e  mov     [rsp+0C0h+var_98], rax
0x140015663  lea     rdx, unk_140072EA8
0x14001566a  lea     rax, [rbp+57h+var_88]
0x14001566e  mov     [rbp+57h+var_88], rdi
0x140015672  mov     [rsp+0C0h+var_A0], rax
0x140015677  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14001567c  mov     [rdi], r14w
0x140015680  jmp     loc_14001581D
0x140015685  lea     rax, [rbp+57h+var_70]
0x140015689  mov     [rbp+57h+var_70], r14w
0x14001568e  mov     [rbp+57h+Src], rax
0x140015692  lea     rdx, [rbp+57h+Src]
0x140015696  lea     rax, [rbp+57h+var_70]
0x14001569a  mov     rcx, rdi; lpFileName
0x14001569d  mov     [rbp+57h+var_78], rax
0x1400156a1  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400156a6  test    eax, eax
0x1400156a8  jz      loc_140015771
0x1400156ae  mov     rbx, [rbp+57h+var_78]
0x1400156b2  sub     rbx, [rbp+57h+Src]
0x1400156b6  sar     rbx, 1
0x1400156b9  cmp     rbx, 104h
0x1400156c0  jb      loc_14001575A
0x1400156c6  mov     [rdi], r14w
0x1400156ca  mov     ebx, 80070057h
0x1400156cf  mov     eax, cs:dword_14007E000
0x1400156d5  cmp     eax, 2
0x1400156d8  jbe     short loc_140015738
0x1400156da  mov     rcx, cs:qword_14007E018
0x1400156e1  mov     rax, cs:qword_14007E010
0x1400156e8  test    al, 8
0x1400156ea  jz      short loc_140015738
0x1400156ec  mov     rax, rcx
0x1400156ef  and     eax, 8
0x1400156f2  cmp     rax, rcx
0x1400156f5  jnz     short loc_140015738
0x1400156f7  lea     rax, [rbp+57h+var_90]
0x1400156fb  mov     [rbp+57h+var_90], 80070057h
0x140015702  mov     [rbp+57h+var_40], rax
0x140015706  lea     rdx, dword_140072E74
0x14001570d  lea     rax, [rbp+57h+var_60]
0x140015711  mov     [rbp+57h+var_38], 4
0x140015719  mov     [rsp+0C0h+var_98], rax
0x14001571e  lea     rcx, dword_14007E000
0x140015725  xor     r9d, r9d
0x140015728  mov     dword ptr [rsp+0C0h+var_A0], 3
0x140015730  xor     r8d, r8d
0x140015733  call    _tlgWriteTransfer_EventWriteTransfer
0x140015738  mov     rcx, [rbp+57h+Src]; void *
0x14001573c  lea     rax, [rbp+57h+var_70]
0x140015740  cmp     rcx, rax
0x140015743  jz      loc_14001581D
0x140015749  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015750  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015755  jmp     loc_14001581D
0x14001575a  mov     rdx, [rbp+57h+Src]; Src
0x14001575e  add     rbx, rbx
0x140015761  mov     r8, rbx; Size
0x140015764  mov     rcx, rdi; void *
0x140015767  call    memcpy_0
0x14001576c  mov     [rbx+rdi], r14w
0x140015771  lea     rax, [rbp+57h+var_70]
0x140015775  cmp     [rbp+57h+Src], rax
0x140015779  jz      short loc_14001578B
0x14001577b  mov     rcx, [rbp+57h+Src]; void *
0x14001577f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015786  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001578b  mov     ebx, r14d
0x14001578e  jmp     loc_14001581D
0x140015793  call    cs:__imp_GetLastError
0x14001579a  nop     dword ptr [rax+rax+00h]
0x14001579f  mov     ebx, eax
0x1400157a1  test    eax, eax
0x1400157a3  jle     short loc_1400157AE
0x1400157a5  movzx   ebx, ax
0x1400157a8  or      ebx, 80070000h
0x1400157ae  test    ebx, ebx
0x1400157b0  mov     eax, 80004005h
0x1400157b5  cmovns  ebx, eax
0x1400157b8  mov     eax, cs:dword_14007E000
0x1400157be  cmp     eax, 2
0x1400157c1  jbe     short loc_14001581D
0x1400157c3  mov     rcx, cs:qword_14007E018
0x1400157ca  mov     rax, cs:qword_14007E010
0x1400157d1  test    al, 8
0x1400157d3  jz      short loc_14001581D
0x1400157d5  mov     rax, rcx
0x1400157d8  and     eax, 8
0x1400157db  cmp     rax, rcx
0x1400157de  jnz     short loc_14001581D
0x1400157e0  lea     rax, [rbp+57h+var_90]
0x1400157e4  mov     [rbp+57h+var_90], ebx
0x1400157e7  mov     [rbp+57h+var_40], rax
0x1400157eb  lea     rdx, dword_140072EEC
0x1400157f2  lea     rax, [rbp+57h+var_60]
0x1400157f6  mov     [rbp+57h+var_38], 4
0x1400157fe  mov     [rsp+0C0h+var_98], rax
0x140015803  lea     rcx, dword_14007E000
0x14001580a  xor     r9d, r9d
0x14001580d  mov     dword ptr [rsp+0C0h+var_A0], 3
0x140015815  xor     r8d, r8d
0x140015818  call    _tlgWriteTransfer_EventWriteTransfer
0x14001581d  mov     eax, cs:dword_14007E000
0x140015823  cmp     eax, 2
0x140015826  jbe     short loc_14001586A
0x140015828  mov     rdx, cs:qword_14007E018
0x14001582f  mov     rax, cs:qword_14007E010
0x140015836  test    al, 8
0x140015838  jz      short loc_14001586A
0x14001583a  mov     rcx, rdx
0x14001583d  and     ecx, 8
0x140015840  cmp     rcx, rdx
0x140015843  jnz     short loc_14001586A
0x140015845  lea     rax, [rbp+57h+var_90]
0x140015849  mov     [rbp+57h+var_90], ebx
0x14001584c  mov     [rsp+0C0h+var_98], rax
0x140015851  lea     rdx, byte_140072E3B
0x140015858  lea     rax, [rbp+57h+var_88]
0x14001585c  mov     [rbp+57h+var_88], rdi
0x140015860  mov     [rsp+0C0h+var_A0], rax
0x140015865  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14001586a  mov     eax, ebx
0x14001586c  jmp     short loc_1400158C5
0x14001586e  mov     eax, cs:dword_14007E000
0x140015874  cmp     eax, 2
0x140015877  jbe     short loc_1400158C0
0x140015879  mov     rcx, cs:qword_14007E018
0x140015880  mov     rax, cs:qword_14007E010
0x140015887  test    al, 8
0x140015889  jz      short loc_1400158C0
0x14001588b  mov     rax, rcx
0x14001588e  and     eax, 8
0x140015891  cmp     rax, rcx
0x140015894  jnz     short loc_1400158C0
0x140015896  lea     rax, [rbp+57h+var_60]
0x14001589a  xor     r9d, r9d
0x14001589d  mov     [rsp+0C0h+var_98], rax
0x1400158a2  lea     rdx, qword_140072F20
0x1400158a9  xor     r8d, r8d
0x1400158ac  mov     dword ptr [rsp+0C0h+var_A0], 2
0x1400158b4  lea     rcx, dword_14007E000
0x1400158bb  call    _tlgWriteTransfer_EventWriteTransfer
0x1400158c0  mov     eax, 80070057h
0x1400158c5  mov     rcx, [rbp+57h+var_30]
0x1400158c9  xor     rcx, rsp; StackCookie
0x1400158cc  call    __security_check_cookie
0x1400158d1  add     rsp, 0A8h
0x1400158d8  pop     r14
0x1400158da  pop     rdi
0x1400158db  pop     rbx
0x1400158dc  pop     rbp
0x1400158dd  retn
```

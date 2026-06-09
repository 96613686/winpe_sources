# SmartCards::SmartCardReaderProxy::Initialize(ushort const *,ulong)

- ea: `0x1800955f8`
- end: `0x1800958ba`
- name: `?Initialize@SmartCardReaderProxy@SmartCards@@QEAAJPEBGK@Z`
- size: `706`
- prototype: `__int64 __fastcall(SmartCards::SmartCardReaderProxy *__hidden this, LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180070c20`
- `0x180077240`

## callees

- `0x1800049a0`
- `0x1800057c6`
- `0x180005840`
- `0x18000c944`
- `0x18000c964`
- `0x180095588`
- `0x1800955f8`
- `0x180096c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180095878`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180095878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095703`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800956d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095716`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800956d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095716`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800956b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800956b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800956cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800956cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009568b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009570e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009577f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009568b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009570e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009577f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180095653`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180095653`

## string_xrefs

- `0x180095764`: `onecoreuap\ds\nfc\product\semanagement\common\smartcardreaderconnector\src\smartcardreaderproxy.cpp`
- `0x1800957b4`: `onecoreuap\ds\nfc\product\semanagement\common\smartcardreaderconnector\src\smartcardreaderproxy.cpp`
- `0x18009580b`: `onecoreuap\ds\nfc\product\semanagement\common\smartcardreaderconnector\src\smartcardreaderproxy.cpp`
- `0x180095824`: `onecoreuap\ds\nfc\product\semanagement\common\smartcardreaderconnector\src\smartcardreaderproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SmartCards::SmartCardReaderProxy::Initialize(
        SmartCards::SmartCardReaderProxy *this,
        LPCWSTR lpFileName,
        unsigned int a3)
{
  char *FileW; // rbx
  const char *v6; // r9
  int v7; // edi
  char *v8; // rsi
  const char *v9; // r9
  PTP_IO ThreadpoolIo; // r14
  struct _TP_IO *v11; // r12
  DWORD LastError; // edi
  void *v13; // r14
  DWORD v14; // edi
  int v15; // eax
  int Atr; // eax
  unsigned int v18; // ebx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int16 v22; // bx
  char v23; // di
  int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-49h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-49h]
  bool v27; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-25h] BYREF
  char v29; // [rsp+48h] [rbp-21h] BYREF
  int v30; // [rsp+50h] [rbp-19h] BYREF
  char v31; // [rsp+54h] [rbp-15h]
  int Src; // [rsp+55h] [rbp-14h] BYREF
  __int16 v33; // [rsp+59h] [rbp-10h]
  char v34; // [rsp+5Bh] [rbp-Eh]
  __int16 v35; // [rsp+5Ch] [rbp-Dh]
  unsigned __int8 v36[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  FileW = (char *)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v8 = (char *)this + 8;
    ThreadpoolIo = CreateThreadpoolIo(FileW, NfcAsyncIo::IoCompletionCallback, 0, 0);
    v11 = (struct _TP_IO *)*((_QWORD *)this + 2);
    if ( v11 )
    {
      LastError = GetLastError();
      CloseThreadpoolIo(v11);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 2) = ThreadpoolIo;
    if ( ThreadpoolIo )
    {
      if ( v8 != &v29 )
      {
        v13 = *(void **)v8;
        if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v14 = GetLastError();
          CloseHandle(v13);
          SetLastError(v14);
        }
        *(_QWORD *)v8 = FileW;
        goto LABEL_17;
      }
    }
    else
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x13,
              (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\nfcasyncio\\src\\nfcasyncio.cpp",
              v9);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\nfcasyncio\\src\\nfcasyncio.cpp",
          (const char *)(unsigned int)v15,
          dwCreationDisposition);
        CloseHandle(FileW);
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\smartcardreaderconnector\\src\\smartcardreaderproxy.cpp",
          (const char *)(unsigned int)v7,
          dwCreationDisposition);
        return (unsigned int)v7;
      }
    }
    CloseHandle(FileW);
    goto LABEL_17;
  }
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x25,
         (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\nfcasyncio\\src\\nfcasyncio.cpp",
         v6);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( v7 < 0 )
    goto LABEL_15;
LABEL_17:
  v28 = 0;
  Atr = SmartCards::SmartCardReaderProxy::GetAtr(this, a3, v36, 0x20u, &v28);
  v18 = Atr;
  if ( Atr < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\smartcardreaderconnector\\src\\smartcardreaderproxy.cpp",
      (const char *)(unsigned int)Atr,
      dwCreationDispositiona);
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\smartcardreaderconnector\\src\\smartcardreaderproxy.cpp",
      (const char *)v18,
      dwCreationDispositionb);
    return v18;
  }
  v30 = 0;
  v31 = 0;
  Src = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  v27 = 0;
  v19 = ATRParser::Parse((ATRParser *)&v30, v36, v28, &v27);
  v18 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\smartcardreaderconnector\\src\\smartcardreaderproxy.cpp",
      (const char *)(unsigned int)v19,
      dwCreationDispositiona);
    goto LABEL_21;
  }
  if ( v27 )
  {
    v22 = 0;
    LOWORD(v28) = 0;
    v23 = 0;
    BYTE2(v28) = 0;
    if ( (v30 & 0x80u) != 0 && HIBYTE(Src) )
    {
      if ( HIBYTE(Src) > 3uLL )
      {
        *(_DWORD *)_o__errno(v21, v20, HIBYTE(Src)) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(&v28, &Src, HIBYTE(Src));
        v23 = BYTE2(v28);
        v22 = v28;
      }
    }
    *(_WORD *)this = v22;
    *((_BYTE *)this + 2) = v23;
  }
  return 0;
}

```

## disassembly

```asm
0x1800955f8  mov     [rsp-8+arg_18], rbx
0x1800955fd  push    rbp
0x1800955fe  push    rsi
0x1800955ff  push    rdi
0x180095600  push    r12
0x180095602  push    r13
0x180095604  push    r14
0x180095606  push    r15
0x180095608  lea     rbp, [rsp-27h]
0x18009560d  sub     rsp, 90h
0x180095614  mov     rax, cs:__security_cookie
0x18009561b  xor     rax, rsp
0x18009561e  mov     [rbp+57h+var_40], rax
0x180095622  mov     r13d, r8d
0x180095625  mov     rax, rdx
0x180095628  mov     r15, rcx
0x18009562b  xor     r12d, r12d
0x18009562e  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x180095633  mov     [rsp+0C0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18009563b  mov     [rsp+0C0h+dwCreationDisposition], 3; int
0x180095643  xor     r9d, r9d; lpSecurityAttributes
0x180095646  mov     edx, 0C0000000h; dwDesiredAccess
0x18009564b  lea     r8d, [r12+3]; dwShareMode
0x180095650  mov     rcx, rax; lpFileName
0x180095653  call    cs:__imp_CreateFileW
0x180095659  mov     rbx, rax
0x18009565c  inc     rax
0x18009565f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180095665  jnz     short loc_18009569E
0x180095667  mov     rcx, [rbp+5Fh]; this
0x18009566b  lea     r8, aOnecoreuapDsNf_24; "onecoreuap\\ds\\nfc\\product\\utils\\nf"...
0x180095672  lea     edx, [r12+25h]; void *
0x180095677  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009567c  mov     edi, eax
0x18009567e  lea     rax, [rbx-1]
0x180095682  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180095686  ja      short loc_180095691
0x180095688  mov     rcx, rbx; hObject
0x18009568b  call    cs:__imp_CloseHandle
0x180095691  test    edi, edi
0x180095693  jns     loc_180095785
0x180095699  jmp     loc_18009575D
0x18009569e  lea     rsi, [r15+8]
0x1800956a2  xor     r9d, r9d; pcbe
0x1800956a5  xor     r8d, r8d; pv
0x1800956a8  lea     rdx, ?IoCompletionCallback@NfcAsyncIo@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800956af  mov     rcx, rbx; fl
0x1800956b2  call    cs:__imp_CreateThreadpoolIo
0x1800956b8  mov     r14, rax
0x1800956bb  mov     r12, [rsi+8]
0x1800956bf  test    r12, r12
0x1800956c2  jz      short loc_1800956DD
0x1800956c4  call    cs:__imp_GetLastError
0x1800956ca  mov     edi, eax
0x1800956cc  mov     rcx, r12; pio
0x1800956cf  call    cs:__imp_CloseThreadpoolIo
0x1800956d5  mov     ecx, edi; dwErrCode
0x1800956d7  call    cs:__imp_SetLastError
0x1800956dd  mov     [rsi+8], r14
0x1800956e1  xor     r12d, r12d
0x1800956e4  test    r14, r14
0x1800956e7  jz      short loc_180095721
0x1800956e9  lea     rax, [rbp+57h+var_78]
0x1800956ed  cmp     rsi, rax
0x1800956f0  jz      loc_18009577C
0x1800956f6  mov     r14, [rsi]
0x1800956f9  lea     rax, [r14-1]
0x1800956fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180095701  ja      short loc_18009571C
0x180095703  call    cs:__imp_GetLastError
0x180095709  mov     edi, eax
0x18009570b  mov     rcx, r14; hObject
0x18009570e  call    cs:__imp_CloseHandle
0x180095714  mov     ecx, edi; dwErrCode
0x180095716  call    cs:__imp_SetLastError
0x18009571c  mov     [rsi], rbx
0x18009571f  jmp     short loc_180095785
0x180095721  mov     rcx, [rbp+5Fh]; this
0x180095725  lea     r8, aOnecoreuapDsNf_24; "onecoreuap\\ds\\nfc\\product\\utils\\nf"...
0x18009572c  mov     edx, 13h; void *
0x180095731  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180095736  mov     edi, eax
0x180095738  test    eax, eax
0x18009573a  jns     short loc_18009577C
0x18009573c  mov     rcx, [rbp+5Fh]; this
0x180095740  mov     r9d, eax; char *
0x180095743  lea     r8, aOnecoreuapDsNf_24; "onecoreuap\\ds\\nfc\\product\\utils\\nf"...
0x18009574a  mov     edx, 27h ; '''; void *
0x18009574f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095754  mov     rcx, rbx; hObject
0x180095757  call    cs:__imp_CloseHandle
0x18009575d  mov     rcx, [rbp+5Fh]; this
0x180095761  mov     r9d, edi; char *
0x180095764  lea     r8, aOnecoreuapDsNf_38; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18009576b  mov     edx, 16h; void *
0x180095770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095775  mov     eax, edi
0x180095777  jmp     loc_180095893
0x18009577c  mov     rcx, rbx; hObject
0x18009577f  call    cs:__imp_CloseHandle
0x180095785  mov     [rbp+57h+var_7C], r12d
0x180095789  lea     rax, [rbp+57h+var_7C]
0x18009578d  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; int
0x180095792  mov     r9d, 20h ; ' '; unsigned int
0x180095798  lea     r8, [rbp+57h+var_60]; unsigned __int8 *
0x18009579c  mov     edx, r13d; unsigned int
0x18009579f  mov     rcx, r15; this
0x1800957a2  call    ?GetAtr@SmartCardReaderProxy@SmartCards@@QEAAJKPEAEKPEAK@Z; SmartCards::SmartCardReaderProxy::GetAtr(ulong,uchar *,ulong,ulong *)
0x1800957a7  mov     ebx, eax
0x1800957a9  test    eax, eax
0x1800957ab  jns     short loc_1800957C7
0x1800957ad  mov     rcx, [rbp+5Fh]; this
0x1800957b1  mov     r9d, eax; char *
0x1800957b4  lea     r8, aOnecoreuapDsNf_38; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800957bb  mov     edx, 0A8h; void *
0x1800957c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800957c5  jmp     short loc_18009581D
0x1800957c7  mov     [rbp+57h+var_70], r12d
0x1800957cb  mov     [rbp+57h+var_6C], r12b
0x1800957cf  mov     [rbp+57h+Src], 0
0x1800957d6  mov     [rbp+57h+var_64], 0
0x1800957dc  xor     eax, eax
0x1800957de  mov     [rbp+57h+var_67], ax
0x1800957e2  mov     [rbp+57h+var_65], al
0x1800957e5  mov     [rbp+57h+var_80], r12b
0x1800957e9  lea     r9, [rbp+57h+var_80]; bool *
0x1800957ed  mov     r8d, [rbp+57h+var_7C]; unsigned int
0x1800957f1  lea     rdx, [rbp+57h+var_60]; unsigned __int8 *
0x1800957f5  lea     rcx, [rbp+57h+var_70]; this
0x1800957f9  call    ?Parse@ATRParser@@QEAAJPEAEKPEA_N@Z; ATRParser::Parse(uchar *,ulong,bool *)
0x1800957fe  mov     ebx, eax
0x180095800  test    eax, eax
0x180095802  jns     short loc_180095839
0x180095804  mov     rcx, [rbp+5Fh]; this
0x180095808  mov     r9d, eax; char *
0x18009580b  lea     r8, aOnecoreuapDsNf_38; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180095812  mov     edx, 0ACh; void *
0x180095817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009581c  nop
0x18009581d  mov     rcx, [rbp+5Fh]; this
0x180095821  mov     r9d, ebx; char *
0x180095824  lea     r8, aOnecoreuapDsNf_38; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18009582b  mov     edx, 18h; void *
0x180095830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095835  mov     eax, ebx
0x180095837  jmp     short loc_180095893
0x180095839  cmp     [rbp+57h+var_80], r12b
0x18009583d  jz      short loc_180095891
0x18009583f  xor     ebx, ebx
0x180095841  mov     word ptr [rbp+57h+var_7C], bx
0x180095845  mov     dil, bl
0x180095848  mov     byte ptr [rbp+57h+var_7C+2], bl
0x18009584b  test    byte ptr [rbp+57h+var_70], 80h
0x18009584f  jz      short loc_180095889
0x180095851  movzx   r8d, byte ptr [rbp+57h+Src+3]; Size
0x180095856  test    r8, r8
0x180095859  jz      short loc_180095889
0x18009585b  cmp     r8, 3
0x18009585f  ja      short loc_180095878
0x180095861  lea     rdx, [rbp+57h+Src]; Src
0x180095865  lea     rcx, [rbp+57h+var_7C]; void *
0x180095869  call    memcpy_0
0x18009586e  mov     dil, byte ptr [rbp+57h+var_7C+2]
0x180095872  movzx   ebx, word ptr [rbp+57h+var_7C]
0x180095876  jmp     short loc_180095889
0x180095878  call    cs:__imp__o__errno
0x18009587e  mov     dword ptr [rax], 22h ; '"'
0x180095884  call    _invalid_parameter_noinfo
0x180095889  mov     [r15], bx
0x18009588d  mov     [r15+2], dil
0x180095891  xor     eax, eax
0x180095893  mov     rcx, [rbp+57h+var_40]
0x180095897  xor     rcx, rsp; StackCookie
0x18009589a  call    __security_check_cookie
0x18009589f  mov     rbx, [rsp+0C0h+arg_18]
0x1800958a7  add     rsp, 90h
0x1800958ae  pop     r15
0x1800958b0  pop     r14
0x1800958b2  pop     r13
0x1800958b4  pop     r12
0x1800958b6  pop     rdi
0x1800958b7  pop     rsi
0x1800958b8  pop     rbp
0x1800958b9  retn
```

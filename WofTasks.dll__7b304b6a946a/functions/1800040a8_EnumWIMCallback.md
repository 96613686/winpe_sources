# EnumWIMCallback

- ea: `0x1800040a8`
- end: `0x1800043d2`
- name: `EnumWIMCallback`
- size: `810`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180004788`

## callees

- `0x180001948`
- `0x180001e9c`
- `0x180002474`
- `0x1800040a8`
- `0x180004434`
- `0x1800044f4`
- `0x1800045cc`
- `0x18000466c`
- `0x180004c4c`
- `0x180004ef4`
- `0x180005176`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180004172`
- `msvcrt!swprintf_s` at `0x180004172`
- `KERNEL32!GetLastError` at `0x1800041d7`
- `KERNEL32!GetLastError` at `0x1800041d7`
- `KERNEL32!CloseHandle` at `0x180004325`
- `KERNEL32!CloseHandle` at `0x180004325`
- `KERNEL32!DeleteFileW` at `0x1800041cd`
- `KERNEL32!DeleteFileW` at `0x180004333`
- `KERNEL32!DeleteFileW` at `0x1800041cd`
- `KERNEL32!DeleteFileW` at `0x180004333`

## pseudocode

```c
_BOOL8 __fastcall EnumWIMCallback(__int64 a1, __int64 a2)
{
  signed int v4; // edi
  __int64 v5; // rax
  int v6; // eax
  signed int LastError; // eax
  unsigned __int64 v8; // rsi
  bool v9; // sf
  int v10; // eax
  HANDLE v11; // rsi
  const EVENT_DESCRIPTOR *v12; // rcx
  DWORD v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v17[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h]
  unsigned __int64 v20; // [rsp+98h] [rbp-68h]
  _BYTE Buf1[68]; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v22; // [rsp+E8h] [rbp-18h]
  __int64 v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+100h] [rbp+0h]
  __int64 v25; // [rsp+110h] [rbp+10h]
  wchar_t Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  *(__m128i *)v17 = _mm_load_si128((const __m128i *)&_xmm);
  v4 = 0;
  memset_0(v18, 0, 0x74u);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v14 = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&ExitFlag, 0, 0) == 1 )
    goto LABEL_37;
  v5 = *(_QWORD *)(a1 + 8);
  if ( v5 < *(_QWORD *)(a2 + 528) )
    *(_QWORD *)(a2 + 528) = v5;
  v6 = swprintf_s(
         Buffer,
         0x104u,
         L"%s%s\\%s%016I64X",
         a2 + 4,
         L"\\System Volume Information",
         L"WIMH.",
         *(_QWORD *)(a1 + 8));
  if ( v6 >= 0 )
  {
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        v4 = ReportDataSourceIdDeletion(*(union _LARGE_INTEGER *)(a1 + 8));
        if ( !v4 )
        {
          v14 = 0;
          *(_QWORD *)v15 = 0;
          hObject[0] = (HANDLE)-1LL;
          v10 = WofpOpenSystemVolumeWithFlagsAndAttributes(128, hObject);
          v11 = hObject[0];
          v4 = v10;
          if ( v10 >= 0 )
          {
            v15[0] = 1;
            v15[1] = 1;
            v4 = WofpDeviceIoControl((int)hObject[0], 590628, (int)v15, 8, 0, 0, &v14);
          }
          if ( v11 != (HANDLE)-1LL )
            CloseHandle(v11);
          v9 = v4 < 0;
          if ( v4 )
          {
LABEL_31:
            if ( !v9 )
              goto LABEL_37;
            goto LABEL_32;
          }
          if ( DeleteFileW(Buffer) )
          {
            LogFile(&WofTaskDeleteHashFileEventId, Buffer, *(const unsigned __int16 **)(a1 + 32));
            goto LABEL_37;
          }
          goto LABEL_10;
        }
      }
      else
      {
        v4 = (v6 >> 31) & 0x80004005;
      }
    }
    else
    {
      v4 = WIMHashFile::Initialize(
             (WIMHashFile *)v17,
             *(const unsigned __int16 **)(a1 + 32),
             Buffer,
             *(union _LARGE_INTEGER *)(a1 + 8),
             (int *)&v14);
      if ( !v4 )
      {
        if ( !v14 )
          goto LABEL_13;
        WIMHashFile::~WIMHashFile((WIMHashFile *)v17);
        if ( !DeleteFileW(Buffer) )
        {
LABEL_10:
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_30;
        }
        LogFile(&WofTaskDeleteHashFileEventId, Buffer, *(const unsigned __int16 **)(a1 + 32));
        v4 = WIMHashFile::Initialize(
               (WIMHashFile *)v17,
               *(const unsigned __int16 **)(a1 + 32),
               Buffer,
               *(union _LARGE_INTEGER *)(a1 + 8),
               (int *)&v14);
        if ( !v4 )
        {
LABEL_13:
          v8 = v20;
          if ( v20 != v19 || (v4 = 0, !memcmp_0(Buf1, qword_18000B580, 0x20u)) )
          {
            if ( v8 )
              LogFileOffset(&WofTaskResumeHashFileEventId, v17[1], v8);
            v4 = WIMHashFile::ResumeHashWrites((WIMHashFile *)v17);
          }
          v9 = v4 < 0;
          if ( !v4 )
            goto LABEL_37;
          goto LABEL_31;
        }
      }
    }
LABEL_30:
    v9 = v4 < 0;
    goto LABEL_31;
  }
  v4 = -2147467259;
LABEL_32:
  if ( !*(_DWORD *)a2 )
  {
    v12 = (const EVENT_DESCRIPTOR *)WofTaskGenerateHashFileErrorEventId;
LABEL_36:
    LogFileError(v12, Buffer, *(const unsigned __int16 **)(a1 + 32), v4);
    goto LABEL_37;
  }
  if ( *(_DWORD *)a2 == 1 )
  {
    v12 = &WofTaskDeleteHashFileErrorEventId;
    goto LABEL_36;
  }
LABEL_37:
  *(_DWORD *)(a2 + 524) = v4;
  WIMHashFile::~WIMHashFile((WIMHashFile *)v17);
  return v4 == 0;
}

```

## disassembly

```asm
0x1800040a8  mov     [rsp-8+arg_10], rbx
0x1800040ad  mov     [rsp-8+arg_18], rsi
0x1800040b2  push    rbp
0x1800040b3  push    rdi
0x1800040b4  push    r14
0x1800040b6  lea     rbp, [rsp-240h]
0x1800040be  sub     rsp, 340h
0x1800040c5  mov     rax, cs:__security_cookie
0x1800040cc  xor     rax, rsp
0x1800040cf  mov     [rbp+250h+var_20], rax
0x1800040d6  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800040de  mov     r14, rdx
0x1800040e1  mov     rbx, rcx
0x1800040e4  movdqa  xmmword ptr [rsp+350h+var_2F0], xmm0
0x1800040ea  xor     edi, edi
0x1800040ec  lea     rcx, [rsp+350h+var_2E0]; void *
0x1800040f1  xor     edx, edx; Val
0x1800040f3  lea     r8d, [rdi+74h]; Size
0x1800040f7  call    memset_0
0x1800040fc  xor     eax, eax
0x1800040fe  xorps   xmm0, xmm0
0x180004101  mov     [rbp+250h+var_268], rax
0x180004105  xor     ecx, ecx
0x180004107  mov     [rbp+250h+var_260], rax
0x18000410b  movdqa  [rbp+250h+var_250], xmm0
0x180004110  mov     [rbp+250h+var_240], rax
0x180004114  mov     [rsp+350h+var_310], eax
0x180004118  lock cmpxchg cs:?ExitFlag@@3KA, ecx; ulong ExitFlag
0x180004120  cmp     eax, 1
0x180004123  jz      loc_180004391
0x180004129  mov     rax, [rbx+8]
0x18000412d  cmp     rax, [r14+210h]
0x180004134  jge     short loc_18000413D
0x180004136  mov     [r14+210h], rax
0x18000413d  mov     rax, [rbx+8]
0x180004141  lea     r9, [r14+4]
0x180004145  mov     [rsp+350h+var_320], rax
0x18000414a  lea     r8, aSSS016i64x; "%s%s\\%s%016I64X"
0x180004151  lea     rax, aWimh; "WIMH."
0x180004158  mov     edx, 104h; BufferCount
0x18000415d  mov     qword ptr [rsp+350h+var_328], rax
0x180004162  lea     rcx, [rbp+250h+Buffer]; Buffer
0x180004166  lea     rax, aSystemVolumeIn; "\\System Volume Information"
0x18000416d  mov     [rsp+350h+var_330], rax
0x180004172  call    cs:__imp_swprintf_s
0x180004178  test    eax, eax
0x18000417a  jns     short loc_180004186
0x18000417c  mov     edi, 80004005h
0x180004181  jmp     loc_180004365
0x180004186  cmp     [r14], edi
0x180004189  jnz     loc_18000428A
0x18000418f  mov     r9, [rbx+8]; union _LARGE_INTEGER
0x180004193  lea     rax, [rsp+350h+var_310]
0x180004198  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18000419c  lea     r8, [rbp+250h+Buffer]; unsigned __int16 *
0x1800041a0  lea     rcx, [rsp+350h+var_2F0]; this
0x1800041a5  mov     [rsp+350h+var_330], rax; int *
0x1800041aa  call    ?Initialize@WIMHashFile@@QEAAJPEBG0T_LARGE_INTEGER@@PEAH@Z; WIMHashFile::Initialize(ushort const *,ushort const *,_LARGE_INTEGER,int *)
0x1800041af  mov     edi, eax
0x1800041b1  test    eax, eax
0x1800041b3  jnz     loc_180004361
0x1800041b9  cmp     [rsp+350h+var_310], eax
0x1800041bd  jz      short loc_180004233
0x1800041bf  lea     rcx, [rsp+350h+var_2F0]; this
0x1800041c4  call    ??1WIMHashFile@@QEAA@XZ; WIMHashFile::~WIMHashFile(void)
0x1800041c9  lea     rcx, [rbp+250h+Buffer]; lpFileName
0x1800041cd  call    cs:__imp_DeleteFileW
0x1800041d3  test    eax, eax
0x1800041d5  jnz     short loc_1800041F5
0x1800041d7  call    cs:__imp_GetLastError
0x1800041dd  mov     edi, eax
0x1800041df  test    eax, eax
0x1800041e1  jle     loc_180004361
0x1800041e7  movzx   edi, ax
0x1800041ea  or      edi, 80070000h
0x1800041f0  jmp     loc_180004361
0x1800041f5  mov     r8, [rbx+20h]; unsigned __int16 *
0x1800041f9  lea     rdx, [rbp+250h+Buffer]; unsigned __int16 *
0x1800041fd  lea     rcx, WofTaskDeleteHashFileEventId; EventDescriptor
0x180004204  call    ?LogFile@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1@Z; LogFile(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x180004209  mov     r9, [rbx+8]; union _LARGE_INTEGER
0x18000420d  lea     rax, [rsp+350h+var_310]
0x180004212  mov     rdx, [rbx+20h]; unsigned __int16 *
0x180004216  lea     r8, [rbp+250h+Buffer]; unsigned __int16 *
0x18000421a  lea     rcx, [rsp+350h+var_2F0]; this
0x18000421f  mov     [rsp+350h+var_330], rax; int *
0x180004224  call    ?Initialize@WIMHashFile@@QEAAJPEBG0T_LARGE_INTEGER@@PEAH@Z; WIMHashFile::Initialize(ushort const *,ushort const *,_LARGE_INTEGER,int *)
0x180004229  mov     edi, eax
0x18000422b  test    eax, eax
0x18000422d  jnz     loc_180004361
0x180004233  mov     rsi, [rbp+250h+var_2B8]
0x180004237  cmp     rsi, [rsp+350h+var_2D8]
0x18000423c  jnz     short loc_180004258
0x18000423e  xor     edi, edi
0x180004240  lea     rdx, qword_18000B580; Buf2
0x180004247  lea     rcx, [rbp+250h+Buf1]; Buf1
0x18000424b  lea     r8d, [rdi+20h]; Size
0x18000424f  call    memcmp_0
0x180004254  test    eax, eax
0x180004256  jnz     short loc_18000427D
0x180004258  test    rsi, rsi
0x18000425b  jz      short loc_180004271
0x18000425d  mov     rdx, [rsp+350h+var_2F0+8]; unsigned __int16 *
0x180004262  lea     rcx, WofTaskResumeHashFileEventId; EventDescriptor
0x180004269  mov     r8, rsi; unsigned __int64
0x18000426c  call    ?LogFileOffset@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG_K@Z; LogFileOffset(_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x180004271  lea     rcx, [rsp+350h+var_2F0]; this
0x180004276  call    ?ResumeHashWrites@WIMHashFile@@AEAAJXZ; WIMHashFile::ResumeHashWrites(void)
0x18000427b  mov     edi, eax
0x18000427d  test    edi, edi
0x18000427f  jnz     loc_180004363
0x180004285  jmp     loc_180004391
0x18000428a  cmp     dword ptr [r14], 1
0x18000428e  jnz     loc_180004357
0x180004294  mov     rcx, [rbx+8]; union _LARGE_INTEGER
0x180004298  call    ?ReportDataSourceIdDeletion@@YAJT_LARGE_INTEGER@@@Z; ReportDataSourceIdDeletion(_LARGE_INTEGER)
0x18000429d  mov     edi, eax
0x18000429f  test    eax, eax
0x1800042a1  jnz     loc_180004361
0x1800042a7  lea     rdx, [rsp+350h+hObject]
0x1800042ac  mov     [rsp+350h+var_310], eax
0x1800042b0  mov     ecx, 80h
0x1800042b5  mov     qword ptr [rsp+350h+var_308], 0
0x1800042be  mov     [rsp+350h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800042c7  call    WofpOpenSystemVolumeWithFlagsAndAttributes
0x1800042cc  mov     rsi, [rsp+350h+hObject]
0x1800042d1  mov     edi, eax
0x1800042d3  test    eax, eax
0x1800042d5  js      short loc_18000431C
0x1800042d7  lea     rax, [rsp+350h+var_310]
0x1800042dc  mov     [rsp+350h+var_308], 1
0x1800042e4  mov     [rsp+350h+var_320], rax; LPDWORD
0x1800042e9  lea     r8, [rsp+350h+var_308]; int
0x1800042ee  mov     [rsp+350h+var_328], 0; DWORD
0x1800042f6  mov     r9d, 8; int
0x1800042fc  mov     edx, 90324h; int
0x180004301  mov     [rsp+350h+var_330], 0; LPVOID
0x18000430a  mov     rcx, rsi; int
0x18000430d  mov     [rsp+350h+var_308+4], 1
0x180004315  call    WofpDeviceIoControl
0x18000431a  mov     edi, eax
0x18000431c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004320  jz      short loc_18000432B
0x180004322  mov     rcx, rsi; hObject
0x180004325  call    cs:__imp_CloseHandle
0x18000432b  test    edi, edi
0x18000432d  jnz     short loc_180004363
0x18000432f  lea     rcx, [rbp+250h+Buffer]; lpFileName
0x180004333  call    cs:__imp_DeleteFileW
0x180004339  test    eax, eax
0x18000433b  jz      loc_1800041D7
0x180004341  mov     r8, [rbx+20h]; unsigned __int16 *
0x180004345  lea     rdx, [rbp+250h+Buffer]; unsigned __int16 *
0x180004349  lea     rcx, WofTaskDeleteHashFileEventId; EventDescriptor
0x180004350  call    ?LogFile@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1@Z; LogFile(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x180004355  jmp     short loc_180004391
0x180004357  sar     eax, 1Fh
0x18000435a  mov     edi, 80004005h
0x18000435f  and     edi, eax
0x180004361  test    edi, edi
0x180004363  jns     short loc_180004391
0x180004365  cmp     dword ptr [r14], 0
0x180004369  jnz     short loc_180004374
0x18000436b  lea     rcx, WofTaskGenerateHashFileErrorEventId
0x180004372  jmp     short loc_180004381
0x180004374  cmp     dword ptr [r14], 1
0x180004378  jnz     short loc_180004391
0x18000437a  lea     rcx, WofTaskDeleteHashFileErrorEventId; EventDescriptor
0x180004381  mov     r8, [rbx+20h]; unsigned __int16 *
0x180004385  lea     rdx, [rbp+250h+Buffer]; unsigned __int16 *
0x180004389  mov     r9d, edi; int
0x18000438c  call    ?LogFileError@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1H@Z; LogFileError(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,int)
0x180004391  xor     ebx, ebx
0x180004393  mov     [r14+20Ch], edi
0x18000439a  test    edi, edi
0x18000439c  lea     rcx, [rsp+350h+var_2F0]; this
0x1800043a1  setz    bl
0x1800043a4  call    ??1WIMHashFile@@QEAA@XZ; WIMHashFile::~WIMHashFile(void)
0x1800043a9  mov     eax, ebx
0x1800043ab  mov     rcx, [rbp+250h+var_20]
0x1800043b2  xor     rcx, rsp; StackCookie
0x1800043b5  call    __security_check_cookie
0x1800043ba  lea     r11, [rsp+350h+var_10]
0x1800043c2  mov     rbx, [r11+30h]
0x1800043c6  mov     rsi, [r11+38h]
0x1800043ca  mov     rsp, r11
0x1800043cd  pop     r14
0x1800043cf  pop     rdi
0x1800043d0  pop     rbp
0x1800043d1  retn
```

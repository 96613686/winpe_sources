# s_WTSVirtualChannelWrite

- ea: `0x18001764c`
- end: `0x18001786b`
- name: `s_WTSVirtualChannelWrite`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015fe8`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180014b90`
- `0x1800172fc`
- `0x18001764c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001772d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001772d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017716`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180017716`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001776a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001776a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800176eb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800176eb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180017699`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x180017699`

## string_xrefs

- `0x1800176cf`: `s_WTSVirtualChannelWrite`

## pseudocode

```c
__int64 __fastcall s_WTSVirtualChannelWrite(void *a1, const void *a2, DWORD a3, DWORD *a4)
{
  signed int v4; // ebx
  signed int LastError; // eax
  int v9; // edx
  int v10; // ecx
  int v11; // r9d
  void *v12; // rdi
  signed int v13; // eax
  int lpOverlapped; // [rsp+20h] [rbp-99h]
  DWORD pBytesReturned; // [rsp+30h] [rbp-89h] BYREF
  DWORD v17; // [rsp+34h] [rbp-85h] BYREF
  DWORD v18; // [rsp+38h] [rbp-81h] BYREF
  signed int v19; // [rsp+3Ch] [rbp-7Dh] BYREF
  PVOID ppBuffer; // [rsp+40h] [rbp-79h] BYREF
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-69h] BYREF
  char v23[32]; // [rsp+70h] [rbp-49h] BYREF
  __int64 *v24; // [rsp+90h] [rbp-29h]
  __int64 v25; // [rsp+98h] [rbp-21h]
  signed int *v26; // [rsp+A0h] [rbp-19h]
  __int64 v27; // [rsp+A8h] [rbp-11h]
  DWORD *v28; // [rsp+B0h] [rbp-9h]
  __int64 v29; // [rsp+B8h] [rbp-1h]
  DWORD *v30; // [rsp+C0h] [rbp+7h]
  __int64 v31; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( WTSVirtualChannelQuery(a1, WTSVirtualFileHandle, &ppBuffer, &pBytesReturned) )
    goto LABEL_8;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_8:
    v12 = *(void **)ppBuffer;
    WTSFreeMemory(ppBuffer);
    Overlapped.hEvent = 0;
    Overlapped.Pointer = 0;
    if ( !WriteFile(v12, a2, a3, a4, &Overlapped) )
    {
      if ( GetLastError() == 997 )
        goto LABEL_15;
      v13 = GetLastError();
      v4 = v13;
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_15:
        GetOverlappedResult(v12, &Overlapped, a4, 1);
        goto LABEL_16;
      }
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      {
        v11 = 73;
        goto LABEL_7;
      }
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v11 = 56;
LABEL_7:
    McTemplateU0sqq_EventWriteTransfer(v10, v9, (unsigned int)"s_WTSVirtualChannelWrite", v11, v4);
  }
LABEL_16:
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000400000LL) != 0
    && (qword_180082098 & 0x400000400000LL) == qword_180082098 )
  {
    v17 = *a4;
    v18 = a3;
    v30 = &v17;
    v19 = v4;
    v28 = &v18;
    v21 = 0x1000000;
    v26 = &v19;
    v24 = &v21;
    v31 = 4;
    v29 = 4;
    v27 = 4;
    v25 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_18007538A, 0, 0, 6, v23);
  }
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\DVCTransport\\DynamicVirtualChannelTransport.cpp",
      (const char *)(unsigned int)v4,
      lpOverlapped);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001764c  push    rbp
0x18001764e  push    rbx
0x18001764f  push    rsi
0x180017650  push    rdi
0x180017651  push    r14
0x180017653  push    r15
0x180017655  lea     rbp, [rsp-2Fh]
0x18001765a  sub     rsp, 0E8h
0x180017661  mov     rax, cs:__security_cookie
0x180017668  xor     rax, rsp
0x18001766b  mov     [rbp+57h+var_40], rax
0x18001766f  xor     ebx, ebx
0x180017671  xorps   xmm0, xmm0
0x180017674  mov     rsi, r9
0x180017677  mov     [rbp+57h+ppBuffer], rbx
0x18001767b  mov     r15d, r8d
0x18001767e  mov     [rsp+110h+pBytesReturned], ebx
0x180017682  mov     r14, rdx
0x180017685  lea     r9, [rsp+110h+pBytesReturned]; pBytesReturned
0x18001768a  lea     edx, [rbx+1]; WTS_VIRTUAL_CLASS
0x18001768d  lea     r8, [rbp+57h+ppBuffer]; ppBuffer
0x180017691  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180017695  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180017699  call    cs:__imp_WTSVirtualChannelQuery
0x18001769f  test    eax, eax
0x1800176a1  jnz     short loc_1800176E4
0x1800176a3  call    cs:__imp_GetLastError
0x1800176a9  mov     ebx, eax
0x1800176ab  test    eax, eax
0x1800176ad  jle     short loc_1800176B8
0x1800176af  movzx   ebx, ax
0x1800176b2  or      ebx, 80070000h
0x1800176b8  test    ebx, ebx
0x1800176ba  jns     short loc_1800176E4
0x1800176bc  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800176c3  jz      loc_180017770
0x1800176c9  mov     r9d, 38h ; '8'
0x1800176cf  lea     r8, aSWtsvirtualcha; "s_WTSVirtualChannelWrite"
0x1800176d6  mov     dword ptr [rsp+110h+lpOverlapped], ebx
0x1800176da  call    McTemplateU0sqq_EventWriteTransfer
0x1800176df  jmp     loc_180017770
0x1800176e4  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x1800176e8  mov     rdi, [rcx]
0x1800176eb  call    cs:__imp_WTSFreeMemory
0x1800176f1  lea     rax, [rbp+57h+Overlapped]
0x1800176f5  mov     [rbp+57h+Overlapped.hEvent], 0
0x1800176fd  mov     r9, rsi; lpNumberOfBytesWritten
0x180017700  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x180017705  mov     r8d, r15d; nNumberOfBytesToWrite
0x180017708  mov     qword ptr [rbp+57h+Overlapped.10h], 0
0x180017710  mov     rdx, r14; lpBuffer
0x180017713  mov     rcx, rdi; hFile
0x180017716  call    cs:__imp_WriteFile
0x18001771c  test    eax, eax
0x18001771e  jnz     short loc_180017770
0x180017720  call    cs:__imp_GetLastError
0x180017726  cmp     eax, 3E5h
0x18001772b  jz      short loc_18001775A
0x18001772d  call    cs:__imp_GetLastError
0x180017733  mov     ebx, eax
0x180017735  test    eax, eax
0x180017737  jle     short loc_180017742
0x180017739  movzx   ebx, ax
0x18001773c  or      ebx, 80070000h
0x180017742  test    ebx, ebx
0x180017744  jns     short loc_18001775A
0x180017746  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001774d  jz      short loc_180017770
0x18001774f  mov     r9d, 49h ; 'I'
0x180017755  jmp     loc_1800176CF
0x18001775a  mov     r9d, 1; bWait
0x180017760  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180017764  mov     r8, rsi; lpNumberOfBytesTransferred
0x180017767  mov     rcx, rdi; hFile
0x18001776a  call    cs:__imp_GetOverlappedResult
0x180017770  mov     eax, cs:dword_180082080
0x180017776  cmp     eax, 5
0x180017779  jbe     loc_180017831
0x18001777f  mov     rcx, cs:qword_180082098
0x180017786  mov     rdx, 400000400000h
0x180017790  mov     rax, cs:qword_180082090
0x180017797  test    rdx, rax
0x18001779a  jz      loc_180017831
0x1800177a0  mov     rax, rcx
0x1800177a3  and     rax, rdx
0x1800177a6  cmp     rax, rcx
0x1800177a9  jnz     loc_180017831
0x1800177af  mov     eax, [rsi]
0x1800177b1  lea     rdx, unk_18007538A
0x1800177b8  mov     [rsp+110h+var_DC], eax
0x1800177bc  lea     rcx, dword_180082080
0x1800177c3  lea     rax, [rsp+110h+var_DC]
0x1800177c8  mov     [rsp+110h+var_D8], r15d
0x1800177cd  mov     [rbp+57h+var_50], rax
0x1800177d1  xor     r9d, r9d
0x1800177d4  lea     rax, [rsp+110h+var_D8]
0x1800177d9  mov     [rbp+57h+var_D4], ebx
0x1800177dc  mov     [rbp+57h+var_60], rax
0x1800177e0  xor     r8d, r8d
0x1800177e3  lea     rax, [rbp+57h+var_D4]
0x1800177e7  mov     [rbp+57h+var_C8], 1000000h
0x1800177ef  mov     [rbp+57h+var_70], rax
0x1800177f3  lea     rax, [rbp+57h+var_C8]
0x1800177f7  mov     [rbp+57h+var_80], rax
0x1800177fb  lea     rax, [rbp+57h+var_A0]
0x1800177ff  mov     [rsp+110h+var_E8], rax
0x180017804  mov     dword ptr [rsp+110h+lpOverlapped], 6; int
0x18001780c  mov     [rbp+57h+var_48], 4
0x180017814  mov     [rbp+57h+var_58], 4
0x18001781c  mov     [rbp+57h+var_68], 4
0x180017824  mov     [rbp+57h+var_78], 8
0x18001782c  call    _tlgWriteTransfer_EventWriteTransfer
0x180017831  test    ebx, ebx
0x180017833  jns     short loc_18001784D
0x180017835  mov     rcx, [rbp+5Fh]; this
0x180017839  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\virtualization"...
0x180017840  mov     r9d, ebx; char *
0x180017843  mov     edx, 5Ah ; 'Z'; void *
0x180017848  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001784d  mov     eax, ebx
0x18001784f  mov     rcx, [rbp+57h+var_40]
0x180017853  xor     rcx, rsp; StackCookie
0x180017856  call    __security_check_cookie
0x18001785b  add     rsp, 0E8h
0x180017862  pop     r15
0x180017864  pop     r14
0x180017866  pop     rdi
0x180017867  pop     rsi
0x180017868  pop     rbx
0x180017869  pop     rbp
0x18001786a  retn
```

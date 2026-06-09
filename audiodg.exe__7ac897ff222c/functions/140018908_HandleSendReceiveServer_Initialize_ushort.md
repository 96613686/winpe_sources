# HandleSendReceiveServer::Initialize(ushort * *)

- ea: `0x140018908`
- end: `0x140018c3c`
- name: `?Initialize@HandleSendReceiveServer@@QEAAJPEAPEAG@Z`
- size: `820`
- prototype: `__int64 __fastcall(HandleSendReceiveServer *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400a4aa8`

## callees

- `0x140018908`
- `0x140018e68`
- `0x140019488`
- `0x14005d0e0`
- `0x14005e168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018bca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140018bb7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140018bb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018a80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018a80`
- `ntdll!RtlRandomEx` at `0x14001899c`
- `ntdll!RtlRandomEx` at `0x140018b07`
- `ntdll!RtlRandomEx` at `0x14001899c`
- `ntdll!RtlRandomEx` at `0x140018b07`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400189e9`
- `ntdll!RtlInitUnicodeStringEx` at `0x140018b50`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400189e9`
- `ntdll!RtlInitUnicodeStringEx` at `0x140018b50`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x140018ab3`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x140018ab3`
- `ntdll!NtAlpcCreatePort` at `0x140018a67`
- `ntdll!NtAlpcCreatePort` at `0x140018a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018ad1`

## pseudocode

```c
__int64 __fastcall HandleSendReceiveServer::Initialize(HandleSendReceiveServer *this, unsigned __int16 **a2)
{
  HandleSendReceiveServer *v2; // rsi
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // rdi
  ULONG v5; // eax
  ULONG v6; // r14d
  signed int v7; // ebx
  HandleSendReceiveServer *v8; // rcx
  int inited; // esi
  HLOCAL v10; // r12
  int v11; // r15d
  int v12; // r13d
  HLOCAL v13; // rax
  int v14; // eax
  signed int LastError; // eax
  ULONG v16; // eax
  char *Thread; // rax
  signed int v18; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-A1h]
  __int64 Seed; // [rsp+30h] [rbp-99h] BYREF
  HandleSendReceiveServer *v22; // [rsp+38h] [rbp-91h]
  HLOCAL hMem; // [rsp+40h] [rbp-89h] BYREF
  __int128 v24; // [rsp+48h] [rbp-81h] BYREF
  __int128 v25; // [rsp+58h] [rbp-71h]
  __int128 v26; // [rsp+68h] [rbp-61h]
  _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int16 **v28; // [rsp+88h] [rbp-41h]
  _BYTE v29[16]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-29h]

  v28 = a2;
  v22 = this;
  v2 = this;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  memset_0(v29, 0, 0x48u);
  hMem = 0;
  DestinationString = 0;
  v3 = (unsigned __int16 *)CoTaskMemAlloc(0x80u);
  v4 = v3;
  if ( v3 )
  {
    *v3 = 0;
    LODWORD(Seed) = MEMORY[0x7FFE0320];
    do
    {
      v5 = RtlRandomEx((PULONG)&Seed);
      v6 = v5;
    }
    while ( !v5 );
    v7 = StringCchPrintfW(
           v4,
           0x40u,
           L"%ws%ws%ld",
           L"\\BaseNamedObjects\\",
           L"AudioEngineDuplicateHandleApiPort",
           v5,
           Seed);
    if ( v7 >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&DestinationString, v4);
      if ( inited < 0 )
        goto LABEL_15;
      v7 = HandleSendReceiveServer::SecurityCreateSecurityDescriptor(v8, &hMem);
      if ( v7 >= 0 )
      {
        DWORD2(v25) = 64;
        v10 = hMem;
        v26 = (unsigned __int64)hMem;
        LODWORD(v24) = 48;
        *((_QWORD *)&v24 + 1) = 0;
        v11 = 0;
        *(_QWORD *)&v25 = &DestinationString;
        memset_0(v29, 0, 0x48u);
        v12 = 3;
        v13 = (char *)v22 + 8;
        v30 = 48;
        for ( hMem = (char *)v22 + 8; ; v13 = hMem )
        {
          v14 = NtAlpcCreatePort(v13, &v24, v29);
          inited = v14;
          if ( v14 != 0x40000000 && v14 != -1073741771 )
            break;
          LODWORD(Seed) = 0;
          if ( ++v11 && !v6 )
          {
            v7 = -2147024809;
            break;
          }
          if ( v11 )
          {
            v16 = v11 + v6;
          }
          else
          {
            LODWORD(Seed) = MEMORY[0x7FFE0320];
            do
              v16 = RtlRandomEx((PULONG)&Seed);
            while ( !v16 );
            v6 = v16;
          }
          LODWORD(lpThreadId) = v16;
          v7 = StringCchPrintfW(
                 v4,
                 0x40u,
                 L"%ws%ws%ld",
                 L"\\BaseNamedObjects\\",
                 L"AudioEngineDuplicateHandleApiPort",
                 lpThreadId,
                 Seed);
          if ( v7 < 0 )
            break;
          if ( RtlInitUnicodeStringEx(&DestinationString, v4) < 0 )
            break;
          --v12;
          LODWORD(v24) = 48;
          *((_QWORD *)&v24 + 1) = 0;
          DWORD2(v25) = 64;
          *(_QWORD *)&v25 = &DestinationString;
          v26 = (unsigned __int64)v10;
          if ( v12 <= 0 )
            break;
        }
        LocalFree(v10);
        if ( inited < 0 )
        {
LABEL_15:
          RtlSetLastWin32ErrorAndNtStatusFromNtStatus(inited);
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          CoTaskMemFree(v4);
          v4 = 0;
        }
      }
      v2 = v22;
    }
    if ( v7 < 0 )
      goto LABEL_13;
    Thread = (char *)CreateThread(0, 0, HandleSendReceiveServer::AeServerApiProc, v2, 0, 0);
    *((_QWORD *)v2 + 5) = Thread;
    if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *v28 = v4;
      return (unsigned int)v7;
    }
    v18 = GetLastError();
    v7 = v18;
    if ( v18 > 0 )
      v7 = (unsigned __int16)v18 | 0x80070000;
    if ( v7 < 0 )
    {
LABEL_13:
      if ( v4 )
        CoTaskMemFree(v4);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140018908  mov     [rsp-8+arg_10], rbx
0x14001890d  push    rbp
0x14001890e  push    rsi
0x14001890f  push    rdi
0x140018910  push    r12
0x140018912  push    r13
0x140018914  push    r14
0x140018916  push    r15
0x140018918  lea     rbp, [rsp-27h]
0x14001891d  sub     rsp, 0F0h
0x140018924  mov     rax, cs:__security_cookie
0x14001892b  xor     rax, rsp
0x14001892e  mov     [rbp+57h+var_40], rax
0x140018932  xorps   xmm0, xmm0
0x140018935  mov     [rbp+57h+var_98], rdx
0x140018939  xor     edx, edx; Val
0x14001893b  mov     [rsp+120h+var_E8], rcx
0x140018940  mov     rsi, rcx
0x140018943  lea     rcx, [rbp+57h+var_90]; void *
0x140018947  movups  [rsp+120h+var_D8], xmm0
0x14001894c  lea     r8d, [rdx+48h]; Size
0x140018950  movups  [rbp+57h+var_C8], xmm0
0x140018954  movups  [rbp+57h+var_B8], xmm0
0x140018958  call    memset_0
0x14001895d  xorps   xmm0, xmm0
0x140018960  xor     r13d, r13d
0x140018963  mov     ecx, 80h; cb
0x140018968  mov     [rsp+120h+hMem], r13
0x14001896d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140018971  call    cs:__imp_CoTaskMemAlloc
0x140018977  mov     rdi, rax
0x14001897a  test    rax, rax
0x14001897d  jz      loc_140018C19
0x140018983  mov     dword ptr [rsp+120h+Seed], r13d
0x140018988  mov     [rax], r13w
0x14001898c  mov     eax, ds:7FFE0320h
0x140018993  mov     dword ptr [rsp+120h+Seed], eax
0x140018997  lea     rcx, [rsp+120h+Seed]; Seed
0x14001899c  call    cs:__imp_RtlRandomEx
0x1400189a2  mov     r14d, eax
0x1400189a5  test    eax, eax
0x1400189a7  jz      short loc_140018997
0x1400189a9  mov     dword ptr [rsp+120h+lpThreadId], eax
0x1400189ad  lea     r9, aBasenamedobjec; "\\BaseNamedObjects\\"
0x1400189b4  lea     rax, aAudioenginedup; "AudioEngineDuplicateHandleApiPort"
0x1400189bb  mov     r12d, 40h ; '@'
0x1400189c1  mov     edx, r12d; unsigned __int64
0x1400189c4  mov     qword ptr [rsp+120h+dwCreationFlags], rax
0x1400189c9  lea     r8, aWsWsLd; "%ws%ws%ld"
0x1400189d0  mov     rcx, rdi; unsigned __int16 *
0x1400189d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400189d8  mov     ebx, eax
0x1400189da  test    eax, eax
0x1400189dc  js      loc_140018A92
0x1400189e2  mov     rdx, rdi; SourceString
0x1400189e5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400189e9  call    cs:__imp_RtlInitUnicodeStringEx
0x1400189ef  mov     esi, eax
0x1400189f1  test    eax, eax
0x1400189f3  js      loc_140018AB1
0x1400189f9  lea     rdx, [rsp+120h+hMem]; void **
0x1400189fe  call    ?SecurityCreateSecurityDescriptor@HandleSendReceiveServer@@AEAAJPEAPEAX@Z; HandleSendReceiveServer::SecurityCreateSecurityDescriptor(void * *)
0x140018a03  mov     ebx, eax
0x140018a05  test    eax, eax
0x140018a07  js      loc_140018A8D
0x140018a0d  lea     esi, [r12-10h]
0x140018a12  mov     dword ptr [rbp+57h+var_C8+8], r12d
0x140018a16  mov     r12, [rsp+120h+hMem]
0x140018a1b  lea     rax, [rbp+57h+DestinationString]
0x140018a1f  lea     r8d, [rsi+18h]; Size
0x140018a23  mov     qword ptr [rbp+57h+var_B8], r12
0x140018a27  xor     edx, edx; Val
0x140018a29  mov     dword ptr [rsp+120h+var_D8], esi
0x140018a2d  lea     rcx, [rbp+57h+var_90]; void *
0x140018a31  mov     qword ptr [rbp+57h+var_D8+8], r13
0x140018a35  mov     r15d, r13d
0x140018a38  mov     qword ptr [rbp+57h+var_C8], rax
0x140018a3c  mov     qword ptr [rbp+57h+var_B8+8], r13
0x140018a40  call    memset_0
0x140018a45  mov     rax, [rsp+120h+var_E8]
0x140018a4a  lea     r13d, [rsi-2Dh]
0x140018a4e  add     rax, 8
0x140018a52  mov     [rbp+57h+var_80], rsi
0x140018a56  mov     [rsp+120h+hMem], rax
0x140018a5b  lea     r8, [rbp+57h+var_90]
0x140018a5f  mov     rcx, rax
0x140018a62  lea     rdx, [rsp+120h+var_D8]
0x140018a67  call    cs:__imp_NtAlpcCreatePort
0x140018a6d  mov     esi, eax
0x140018a6f  cmp     eax, 40000000h
0x140018a74  jz      short loc_140018ADC
0x140018a76  cmp     eax, 0C0000035h
0x140018a7b  jz      short loc_140018ADC
0x140018a7d  mov     rcx, r12; hMem
0x140018a80  call    cs:__imp_LocalFree
0x140018a86  xor     r13d, r13d
0x140018a89  test    esi, esi
0x140018a8b  js      short loc_140018AB1
0x140018a8d  mov     rsi, [rsp+120h+var_E8]
0x140018a92  test    ebx, ebx
0x140018a94  jns     loc_140018B9F
0x140018a9a  test    rdi, rdi
0x140018a9d  jz      loc_140018BE7
0x140018aa3  mov     rcx, rdi; pv
0x140018aa6  call    cs:__imp_CoTaskMemFree
0x140018aac  jmp     loc_140018BE7
0x140018ab1  mov     ecx, esi; Status
0x140018ab3  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x140018ab9  call    cs:__imp_GetLastError
0x140018abf  mov     ebx, eax
0x140018ac1  test    eax, eax
0x140018ac3  jle     short loc_140018ACE
0x140018ac5  movzx   ebx, ax
0x140018ac8  or      ebx, 80070000h
0x140018ace  mov     rcx, rdi; pv
0x140018ad1  call    cs:__imp_CoTaskMemFree
0x140018ad7  mov     rdi, r13
0x140018ada  jmp     short loc_140018A8D
0x140018adc  mov     dword ptr [rsp+120h+Seed], 0
0x140018ae4  add     r15d, 1
0x140018ae8  jnz     loc_140018C20
0x140018aee  test    r15d, r15d
0x140018af1  jnz     loc_140018C10
0x140018af7  mov     eax, ds:7FFE0320h
0x140018afe  mov     dword ptr [rsp+120h+Seed], eax
0x140018b02  lea     rcx, [rsp+120h+Seed]; Seed
0x140018b07  call    cs:__imp_RtlRandomEx
0x140018b0d  test    eax, eax
0x140018b0f  jz      short loc_140018B02
0x140018b11  mov     r14d, eax
0x140018b14  mov     dword ptr [rsp+120h+lpThreadId], eax
0x140018b18  lea     r9, aBasenamedobjec; "\\BaseNamedObjects\\"
0x140018b1f  lea     rax, aAudioenginedup; "AudioEngineDuplicateHandleApiPort"
0x140018b26  mov     edx, 40h ; '@'; unsigned __int64
0x140018b2b  lea     r8, aWsWsLd; "%ws%ws%ld"
0x140018b32  mov     qword ptr [rsp+120h+dwCreationFlags], rax
0x140018b37  mov     rcx, rdi; unsigned __int16 *
0x140018b3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018b3f  mov     ebx, eax
0x140018b41  test    eax, eax
0x140018b43  js      loc_140018A7D
0x140018b49  mov     rdx, rdi; SourceString
0x140018b4c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018b50  call    cs:__imp_RtlInitUnicodeStringEx
0x140018b56  test    eax, eax
0x140018b58  js      loc_140018A7D
0x140018b5e  dec     r13d
0x140018b61  mov     dword ptr [rsp+120h+var_D8], 30h ; '0'
0x140018b69  mov     qword ptr [rbp+57h+var_D8+8], 0
0x140018b71  lea     rax, [rbp+57h+DestinationString]
0x140018b75  mov     dword ptr [rbp+57h+var_C8+8], 40h ; '@'
0x140018b7c  mov     qword ptr [rbp+57h+var_C8], rax
0x140018b80  mov     qword ptr [rbp+57h+var_B8], r12
0x140018b84  mov     qword ptr [rbp+57h+var_B8+8], 0
0x140018b8c  test    r13d, r13d
0x140018b8f  jle     loc_140018A7D
0x140018b95  mov     rax, [rsp+120h+hMem]
0x140018b9a  jmp     loc_140018A5B
0x140018b9f  mov     [rsp+120h+lpThreadId], r13; lpThreadId
0x140018ba4  lea     r8, ?AeServerApiProc@HandleSendReceiveServer@@CAKPEAX@Z; lpStartAddress
0x140018bab  mov     r9, rsi; lpParameter
0x140018bae  mov     [rsp+120h+dwCreationFlags], r13d; dwCreationFlags
0x140018bb3  xor     edx, edx; dwStackSize
0x140018bb5  xor     ecx, ecx; lpThreadAttributes
0x140018bb7  call    cs:__imp_CreateThread
0x140018bbd  mov     [rsi+28h], rax
0x140018bc1  dec     rax
0x140018bc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018bc8  jbe     short loc_140018C33
0x140018bca  call    cs:__imp_GetLastError
0x140018bd0  mov     ebx, eax
0x140018bd2  test    eax, eax
0x140018bd4  jle     short loc_140018BDF
0x140018bd6  movzx   ebx, ax
0x140018bd9  or      ebx, 80070000h
0x140018bdf  test    ebx, ebx
0x140018be1  js      loc_140018A9A
0x140018be7  mov     eax, ebx
0x140018be9  mov     rcx, [rbp+57h+var_40]
0x140018bed  xor     rcx, rsp; StackCookie
0x140018bf0  call    __security_check_cookie
0x140018bf5  mov     rbx, [rsp+120h+arg_10]
0x140018bfd  add     rsp, 0F0h
0x140018c04  pop     r15
0x140018c06  pop     r14
0x140018c08  pop     r13
0x140018c0a  pop     r12
0x140018c0c  pop     rdi
0x140018c0d  pop     rsi
0x140018c0e  pop     rbp
0x140018c0f  retn
0x140018c10  lea     eax, [r15+r14]
0x140018c14  jmp     loc_140018B14
0x140018c19  mov     ebx, 8007000Eh
0x140018c1e  jmp     short loc_140018BE7
0x140018c20  test    r14d, r14d
0x140018c23  jnz     loc_140018AEE
0x140018c29  mov     ebx, 80070057h
0x140018c2e  jmp     loc_140018A7D
0x140018c33  mov     rax, [rbp+57h+var_98]
0x140018c37  mov     [rax], rdi
0x140018c3a  jmp     short loc_140018BE7
```

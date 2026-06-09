# CCabDecompressor::CabDecompressorFileRead(__int64,void *,uint)

- ea: `0x180059830`
- end: `0x1800599a2`
- name: `?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z`
- size: `370`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800110fc`
- `0x180059830`
- `0x180061960`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059946`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005991b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005991b`

## string_xrefs

- `0x1800598b6`: `CabDecompressorFileRead - invalid offset`
- `0x180059966`: `CabDecompressorFileRead - ReadFile`
- `0x18005986e`: `CabDecompressorFileRead - invalid buffer`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileRead(INT_PTR hf, _BYTE *pv, UINT cb)
{
  bool v3; // zf
  _BYTE *v5; // rsi
  __int64 v7; // r14
  UINT v8; // ebx
  UINT v9; // ecx
  UINT v10; // ebx
  __int64 v11; // rcx
  signed int LastError; // eax
  signed int v13; // ecx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-48h]
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(_DWORD *)(hf + 16) == 0;
  v5 = pv;
  NumberOfBytesRead = -1;
  if ( v3 )
  {
    v7 = *(_QWORD *)(hf + 8);
    if ( !v7 )
    {
      WUTrace(0, 0, 32, 3, 0, L"CabDecompressorFileRead - invalid buffer");
      return NumberOfBytesRead;
    }
    v9 = *(_DWORD *)(hf + 20);
    v10 = *(_DWORD *)(v7 + 20);
    if ( v9 + cb >= v10 )
    {
      if ( v9 > v10 )
      {
        WUTrace(0, 0, 32, 3, 0, L"CabDecompressorFileRead - invalid offset");
        v8 = -1;
      }
      else
      {
        v8 = v10 - v9;
      }
    }
    else
    {
      v8 = cb;
    }
    NumberOfBytesRead = v8;
    if ( v8 != -1 && v8 == cb )
    {
      memmove(v5, (const void *)(*(_QWORD *)(v7 + 8) + *(unsigned int *)(hf + 20)), v8);
      *(_DWORD *)(hf + 20) += v8;
    }
  }
  else if ( ReadFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesRead, 0) )
  {
    if ( !*(_DWORD *)(hf + 24) )
      return NumberOfBytesRead;
    v8 = NumberOfBytesRead;
    if ( NumberOfBytesRead )
    {
      v11 = NumberOfBytesRead;
      do
      {
        *v5 = ~*v5;
        ++v5;
        --v11;
      }
      while ( v11 );
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v13 = LastError;
    if ( v13 >= 0 )
      v13 = -2147418113;
    LODWORD(lpOverlapped) = v13;
    WUTrace(0, 0, 32, 3, lpOverlapped, L"CabDecompressorFileRead - ReadFile");
    return (UINT)-1;
  }
  return v8;
}

```

## disassembly

```asm
0x180059830  push    rbx
0x180059832  push    rbp
0x180059833  push    rsi
0x180059834  push    rdi
0x180059835  push    r14
0x180059837  sub     rsp, 40h
0x18005983b  mov     rax, cs:__security_cookie
0x180059842  xor     rax, rsp
0x180059845  mov     [rsp+68h+var_30], rax
0x18005984a  cmp     dword ptr [rcx+10h], 0
0x18005984e  mov     ebp, r8d
0x180059851  mov     rsi, rdx
0x180059854  mov     [rsp+68h+NumberOfBytesRead], 0FFFFFFFFh
0x18005985c  mov     rdi, rcx
0x18005985f  jnz     loc_180059909
0x180059865  mov     r14, [rcx+8]
0x180059869  test    r14, r14
0x18005986c  jnz     short loc_180059899
0x18005986e  lea     rax, aCabdecompresso_0; "CabDecompressorFileRead - invalid buffe"...
0x180059875  xor     edx, edx
0x180059877  mov     [rsp+68h+var_40], rax
0x18005987c  lea     r9d, [r14+3]
0x180059880  xor     ecx, ecx
0x180059882  mov     [rsp+68h+lpOverlapped], r14
0x180059887  lea     r8d, [r14+20h]
0x18005988b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180059890  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x180059894  jmp     loc_180059988
0x180059899  mov     ecx, [rcx+14h]
0x18005989c  mov     ebx, [r14+14h]
0x1800598a0  lea     eax, [rcx+r8]
0x1800598a4  cmp     eax, ebx
0x1800598a6  jnb     short loc_1800598AC
0x1800598a8  mov     ebx, ebp
0x1800598aa  jmp     short loc_1800598DD
0x1800598ac  cmp     ecx, ebx
0x1800598ae  ja      short loc_1800598B4
0x1800598b0  sub     ebx, ecx
0x1800598b2  jmp     short loc_1800598DD
0x1800598b4  xor     edx, edx
0x1800598b6  lea     rax, aCabdecompresso_2; "CabDecompressorFileRead - invalid offse"...
0x1800598bd  mov     [rsp+68h+var_40], rax
0x1800598c2  xor     ecx, ecx
0x1800598c4  mov     [rsp+68h+lpOverlapped], 0
0x1800598cd  lea     r9d, [rdx+3]
0x1800598d1  lea     r8d, [rdx+20h]
0x1800598d5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800598da  or      ebx, 0FFFFFFFFh
0x1800598dd  mov     [rsp+68h+NumberOfBytesRead], ebx
0x1800598e1  cmp     ebx, 0FFFFFFFFh
0x1800598e4  jz      loc_180059988
0x1800598ea  cmp     ebx, ebp
0x1800598ec  jnz     loc_180059988
0x1800598f2  mov     edx, [rdi+14h]
0x1800598f5  mov     rcx, rsi; void *
0x1800598f8  add     rdx, [r14+8]; Src
0x1800598fc  mov     r8d, ebx; Size
0x1800598ff  call    memmove
0x180059904  add     [rdi+14h], ebx
0x180059907  jmp     short loc_180059988
0x180059909  mov     rcx, [rcx+8]; hFile
0x18005990d  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180059912  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18005991b  call    cs:__imp_ReadFile
0x180059921  test    eax, eax
0x180059923  jz      short loc_180059946
0x180059925  cmp     dword ptr [rdi+18h], 0
0x180059929  jz      loc_180059890
0x18005992f  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x180059933  test    ebx, ebx
0x180059935  jz      short loc_180059988
0x180059937  mov     ecx, ebx
0x180059939  not     byte ptr [rsi]
0x18005993b  inc     rsi
0x18005993e  sub     rcx, 1
0x180059942  jnz     short loc_180059939
0x180059944  jmp     short loc_180059988
0x180059946  call    cs:__imp_GetLastError
0x18005994c  movzx   ecx, ax
0x18005994f  or      ecx, 80070000h
0x180059955  test    eax, eax
0x180059957  cmovle  ecx, eax
0x18005995a  mov     eax, 8000FFFFh
0x18005995f  test    ecx, ecx
0x180059961  cmovns  ecx, eax
0x180059964  xor     edx, edx
0x180059966  lea     rax, aCabdecompresso; "CabDecompressorFileRead - ReadFile"
0x18005996d  mov     [rsp+68h+var_40], rax
0x180059972  mov     dword ptr [rsp+68h+lpOverlapped], ecx
0x180059976  xor     ecx, ecx
0x180059978  lea     r9d, [rdx+3]
0x18005997c  lea     r8d, [rdx+20h]
0x180059980  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180059985  or      ebx, 0FFFFFFFFh
0x180059988  mov     eax, ebx
0x18005998a  mov     rcx, [rsp+68h+var_30]
0x18005998f  xor     rcx, rsp; StackCookie
0x180059992  call    __security_check_cookie
0x180059997  add     rsp, 40h
0x18005999b  pop     r14
0x18005999d  pop     rdi
0x18005999e  pop     rsi
0x18005999f  pop     rbp
0x1800599a0  pop     rbx
0x1800599a1  retn
```

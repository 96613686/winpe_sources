# DirectorySizeFileCallback

- ea: `0x180044600`
- end: `0x1800446e5`
- name: `DirectorySizeFileCallback`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180024c80`
- `0x18002d2b0`
- `0x180044600`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004468a`
- `KERNEL32!GetLastError` at `0x18004468a`
- `KERNEL32!GetCompressedFileSizeW` at `0x180044675`
- `KERNEL32!GetCompressedFileSizeW` at `0x180044675`

## pseudocode

```c
__int64 __fastcall DirectorySizeFileCallback(const WCHAR *a1, __int64 a2, unsigned int *a3)
{
  const char *v5; // r9
  unsigned int v6; // ebx
  DWORD FileSizeHigh[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)FileSizeHigh = 0;
  if ( !a1 )
  {
    v5 = "No file specified";
LABEL_3:
    v6 = -2147024809;
    CBSWdsLog(0x4000000, 2147942487LL, 1, v5, *(_QWORD *)FileSizeHigh);
    return v6;
  }
  if ( !a2 )
  {
    v5 = "No find data specified";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v5 = "No context specified";
    goto LABEL_3;
  }
  v6 = 0;
  FileSizeHigh[0] = GetCompressedFileSizeW(a1, &FileSizeHigh[1]);
  if ( FileSizeHigh[0] == -1 && GetLastError() )
  {
    FileSizeHigh[1] = *(_DWORD *)(a2 + 28);
    FileSizeHigh[0] = *(_DWORD *)(a2 + 32);
  }
  *((_QWORD *)a3 + 1) += *a3
                       + *(_QWORD *)FileSizeHigh
                       - 1LL
                       - ((unsigned __int64)*a3 + *(_QWORD *)FileSizeHigh - 1LL) % *a3;
  return v6;
}

```

## disassembly

```asm
0x180044600  mov     [rsp+arg_8], rbx
0x180044605  mov     [rsp+arg_18], rsi
0x18004460a  push    rdi
0x18004460b  sub     rsp, 30h
0x18004460f  mov     rax, cs:__security_cookie
0x180044616  xor     rax, rsp
0x180044619  mov     [rsp+38h+var_10], rax
0x18004461e  mov     qword ptr [rsp+38h+FileSizeHigh], 0
0x180044627  mov     rsi, r8
0x18004462a  mov     rdi, rdx
0x18004462d  test    rcx, rcx
0x180044630  jnz     short loc_180044652
0x180044632  lea     r9, aNoFileSpecifie; "No file specified"
0x180044639  mov     edx, 80070057h
0x18004463e  mov     ecx, 4000000h
0x180044643  mov     r8d, 1
0x180044649  mov     ebx, edx
0x18004464b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180044650  jmp     short loc_1800446C5
0x180044652  test    rdi, rdi
0x180044655  jnz     short loc_180044660
0x180044657  lea     r9, aNoFindDataSpec; "No find data specified"
0x18004465e  jmp     short loc_180044639
0x180044660  test    rsi, rsi
0x180044663  jnz     short loc_18004466E
0x180044665  lea     r9, aNoContextSpeci; "No context specified"
0x18004466c  jmp     short loc_180044639
0x18004466e  lea     rdx, [rsp+38h+FileSizeHigh+4]; lpFileSizeHigh
0x180044673  xor     ebx, ebx
0x180044675  call    cs:__imp_GetCompressedFileSizeW
0x18004467c  nop     dword ptr [rax+rax+00h]
0x180044681  mov     [rsp+38h+FileSizeHigh], eax
0x180044685  cmp     eax, 0FFFFFFFFh
0x180044688  jnz     short loc_1800446A8
0x18004468a  call    cs:__imp_GetLastError
0x180044691  nop     dword ptr [rax+rax+00h]
0x180044696  test    eax, eax
0x180044698  jz      short loc_1800446A8
0x18004469a  mov     eax, [rdi+1Ch]
0x18004469d  mov     [rsp+38h+FileSizeHigh+4], eax
0x1800446a1  mov     eax, [rdi+20h]
0x1800446a4  mov     [rsp+38h+FileSizeHigh], eax
0x1800446a8  mov     r8d, [rsi]
0x1800446ab  xor     edx, edx
0x1800446ad  mov     r9, qword ptr [rsp+38h+FileSizeHigh]
0x1800446b2  dec     r9
0x1800446b5  add     r9, r8
0x1800446b8  mov     rax, r9
0x1800446bb  div     r8
0x1800446be  sub     r9, rdx
0x1800446c1  add     [rsi+8], r9
0x1800446c5  mov     eax, ebx
0x1800446c7  mov     rcx, [rsp+38h+var_10]
0x1800446cc  xor     rcx, rsp; StackCookie
0x1800446cf  call    __security_check_cookie
0x1800446d4  mov     rbx, [rsp+38h+arg_8]
0x1800446d9  mov     rsi, [rsp+38h+arg_18]
0x1800446de  add     rsp, 30h
0x1800446e2  pop     rdi
0x1800446e3  retn
```

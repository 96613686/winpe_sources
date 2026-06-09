# FormModuleFullPathName

- ea: `0x1400226f8`
- end: `0x140022861`
- name: `FormModuleFullPathName`
- size: `361`
- prototype: `__int64 __fastcall(HMODULE hModule, LPWSTR *lpFilePart)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021744`

## callees

- `0x140002116`
- `0x1400226f8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400227a3`
- `KERNEL32!HeapAlloc` at `0x1400227a3`
- `KERNEL32!GetProcessHeap` at `0x14002278e`
- `KERNEL32!GetProcessHeap` at `0x14002278e`
- `KERNEL32!GetLastError` at `0x1400227d5`
- `KERNEL32!GetLastError` at `0x140022810`
- `KERNEL32!GetLastError` at `0x1400227d5`
- `KERNEL32!GetLastError` at `0x140022810`
- `KERNEL32!GetModuleFileNameW` at `0x140022747`
- `KERNEL32!GetModuleFileNameW` at `0x140022747`
- `KERNEL32!GetFullPathNameW` at `0x140022775`
- `KERNEL32!GetFullPathNameW` at `0x1400227c5`
- `KERNEL32!GetFullPathNameW` at `0x140022775`
- `KERNEL32!GetFullPathNameW` at `0x1400227c5`
- `KERNEL32!SetLastError` at `0x1400227e5`
- `KERNEL32!SetLastError` at `0x140022804`
- `KERNEL32!SetLastError` at `0x14002282a`
- `KERNEL32!SetLastError` at `0x1400227e5`
- `KERNEL32!SetLastError` at `0x140022804`
- `KERNEL32!SetLastError` at `0x14002282a`

## pseudocode

```c
WCHAR *__fastcall FormModuleFullPathName(HMODULE hModule, LPWSTR *lpFilePart)
{
  DWORD v4; // edi
  WCHAR *v5; // rsi
  DWORD LastError; // ebp
  DWORD FullPathNameW; // r14d
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  DWORD v10; // eax
  WCHAR Filename[264]; // [rsp+20h] [rbp-248h] BYREF

  v4 = 0;
  v5 = 0;
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
  {
    LastError = 0;
    if ( Filename[0] )
    {
      FullPathNameW = GetFullPathNameW(Filename, 0, 0, 0);
      if ( FullPathNameW )
      {
        ProcessHeap = GetProcessHeap();
        v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
        v5 = v9;
        if ( !v9 )
        {
          LastError = 14;
LABEL_7:
          SetLastError(LastError);
          if ( v5 )
            goto LABEL_14;
          goto LABEL_11;
        }
        if ( GetFullPathNameW(Filename, FullPathNameW, v9, lpFilePart) )
          goto LABEL_7;
      }
      LastError = GetLastError();
      goto LABEL_7;
    }
    SetLastError(0x57u);
  }
LABEL_11:
  v10 = GetLastError();
  if ( !v10 )
    v10 = 31;
  v4 = v10;
LABEL_14:
  SetLastError(v4);
  return v5;
}

```

## disassembly

```asm
0x1400226f8  mov     [rsp+arg_10], rbx
0x1400226fd  push    rbp
0x1400226fe  push    rsi
0x1400226ff  push    rdi
0x140022700  push    r14
0x140022702  push    r15
0x140022704  sub     rsp, 240h
0x14002270b  mov     rax, cs:__security_cookie
0x140022712  xor     rax, rsp
0x140022715  mov     [rsp+268h+var_38], rax
0x14002271d  mov     r15, rdx
0x140022720  mov     rbx, rcx
0x140022723  xor     edi, edi
0x140022725  lea     rcx, [rsp+268h+Filename]; void *
0x14002272a  xor     edx, edx; Val
0x14002272c  mov     r8d, 208h; Size
0x140022732  mov     esi, edi
0x140022734  call    memset_0
0x140022739  mov     r8d, 104h; nSize
0x14002273f  lea     rdx, [rsp+268h+Filename]; lpFilename
0x140022744  mov     rcx, rbx; hModule
0x140022747  call    cs:__imp_GetModuleFileNameW
0x14002274e  nop     dword ptr [rax+rax+00h]
0x140022753  test    eax, eax
0x140022755  jz      loc_140022810
0x14002275b  mov     ebp, edi
0x14002275d  cmp     di, [rsp+268h+Filename]
0x140022762  jz      loc_1400227FF
0x140022768  xor     r9d, r9d; lpFilePart
0x14002276b  lea     rcx, [rsp+268h+Filename]; lpFileName
0x140022770  xor     r8d, r8d; lpBuffer
0x140022773  xor     edx, edx; nBufferLength
0x140022775  call    cs:__imp_GetFullPathNameW
0x14002277c  nop     dword ptr [rax+rax+00h]
0x140022781  mov     r14d, eax
0x140022784  test    eax, eax
0x140022786  jz      short loc_1400227D5
0x140022788  mov     ebx, r14d
0x14002278b  add     rbx, rbx
0x14002278e  call    cs:__imp_GetProcessHeap
0x140022795  nop     dword ptr [rax+rax+00h]
0x14002279a  mov     r8, rbx; dwBytes
0x14002279d  lea     edx, [rdi+8]; dwFlags
0x1400227a0  mov     rcx, rax; hHeap
0x1400227a3  call    cs:__imp_HeapAlloc
0x1400227aa  nop     dword ptr [rax+rax+00h]
0x1400227af  mov     rsi, rax
0x1400227b2  test    rax, rax
0x1400227b5  jz      short loc_1400227F8
0x1400227b7  mov     r9, r15; lpFilePart
0x1400227ba  lea     rcx, [rsp+268h+Filename]; lpFileName
0x1400227bf  mov     r8, rax; lpBuffer
0x1400227c2  mov     edx, r14d; nBufferLength
0x1400227c5  call    cs:__imp_GetFullPathNameW
0x1400227cc  nop     dword ptr [rax+rax+00h]
0x1400227d1  test    eax, eax
0x1400227d3  jnz     short loc_1400227E3
0x1400227d5  call    cs:__imp_GetLastError
0x1400227dc  nop     dword ptr [rax+rax+00h]
0x1400227e1  mov     ebp, eax
0x1400227e3  mov     ecx, ebp; dwErrCode
0x1400227e5  call    cs:__imp_SetLastError
0x1400227ec  nop     dword ptr [rax+rax+00h]
0x1400227f1  test    rsi, rsi
0x1400227f4  jnz     short loc_140022828
0x1400227f6  jmp     short loc_140022810
0x1400227f8  mov     ebp, 0Eh
0x1400227fd  jmp     short loc_1400227E3
0x1400227ff  mov     ecx, 57h ; 'W'; dwErrCode
0x140022804  call    cs:__imp_SetLastError
0x14002280b  nop     dword ptr [rax+rax+00h]
0x140022810  call    cs:__imp_GetLastError
0x140022817  nop     dword ptr [rax+rax+00h]
0x14002281c  test    eax, eax
0x14002281e  mov     ecx, 1Fh
0x140022823  cmovz   eax, ecx
0x140022826  mov     edi, eax
0x140022828  mov     ecx, edi; dwErrCode
0x14002282a  call    cs:__imp_SetLastError
0x140022831  nop     dword ptr [rax+rax+00h]
0x140022836  mov     rax, rsi
0x140022839  mov     rcx, [rsp+268h+var_38]
0x140022841  xor     rcx, rsp; StackCookie
0x140022844  call    __security_check_cookie
0x140022849  mov     rbx, [rsp+268h+arg_10]
0x140022851  add     rsp, 240h
0x140022858  pop     r15
0x14002285a  pop     r14
0x14002285c  pop     rdi
0x14002285d  pop     rsi
0x14002285e  pop     rbp
0x14002285f  retn
```

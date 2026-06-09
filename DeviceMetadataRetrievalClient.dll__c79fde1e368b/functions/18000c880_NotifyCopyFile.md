# NotifyCopyFile

- ea: `0x18000c880`
- end: `0x18000ca54`
- name: `NotifyCopyFile`
- size: `468`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c820`

## callees

- `0x1800030c4`
- `0x1800039d0`
- `0x180004dec`
- `0x18000c880`
- `0x18000ede8`
- `0x18000eed0`
- `0x180014010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000c8e4`
- `KERNEL32!HeapAlloc` at `0x18000c8e4`
- `KERNEL32!GetProcessHeap` at `0x18000c8d6`
- `KERNEL32!GetProcessHeap` at `0x18000c990`
- `KERNEL32!GetProcessHeap` at `0x18000ca1e`
- `KERNEL32!GetProcessHeap` at `0x18000ca32`
- `KERNEL32!GetProcessHeap` at `0x18000c8d6`
- `KERNEL32!GetProcessHeap` at `0x18000c990`
- `KERNEL32!GetProcessHeap` at `0x18000ca1e`
- `KERNEL32!GetProcessHeap` at `0x18000ca32`
- `KERNEL32!HeapFree` at `0x18000c99e`
- `KERNEL32!HeapFree` at `0x18000ca2c`
- `KERNEL32!HeapFree` at `0x18000ca40`
- `KERNEL32!HeapFree` at `0x18000c99e`
- `KERNEL32!HeapFree` at `0x18000ca2c`
- `KERNEL32!HeapFree` at `0x18000ca40`
- `KERNEL32!MultiByteToWideChar` at `0x18000c8c3`
- `KERNEL32!MultiByteToWideChar` at `0x18000c90c`
- `KERNEL32!MultiByteToWideChar` at `0x18000c8c3`
- `KERNEL32!MultiByteToWideChar` at `0x18000c90c`
- `KERNEL32!GetLastError` at `0x18000c9f0`
- `KERNEL32!GetLastError` at `0x18000c9f0`
- `KERNEL32!CreateFileW` at `0x18000c9cc`
- `KERNEL32!CreateFileW` at `0x18000c9cc`

## pseudocode

```c
__int64 __fastcall NotifyCopyFile(__int64 a1, __int64 a2)
{
  const CHAR *v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rax
  int cchWideChar; // ebp
  unsigned int v7; // eax
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v11; // rbx
  __int64 (__fastcall *v12)(WCHAR *, _QWORD); // rax
  int v13; // eax
  const unsigned __int16 *v14; // rax
  WCHAR *v15; // rbp
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rsi
  HANDLE v18; // rax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  HANDLE v21; // rax
  HANDLE v22; // rax

  v2 = *(const CHAR **)(a2 + 8);
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  cchWideChar = v4 + 1;
  v7 = MultiByteToWideChar(0, 1u, v2, v4 + 1, 0, 0);
  if ( v7 )
  {
    v8 = 2LL * v7;
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v8);
    v11 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0, 1u, v2, cchWideChar, lpWideCharStr, cchWideChar) )
      {
        v12 = *(__int64 (__fastcall **)(WCHAR *, _QWORD))(a1 + 8);
        if ( !v12 )
          goto LABEL_9;
        v13 = v12(v11, *(_QWORD *)(a1 + 16)) - 1;
        if ( v13 )
        {
          if ( v13 == 1 )
          {
LABEL_9:
            v14 = MemMallocAndCat(*(const unsigned __int16 **)a1, L"\\", v11, 0);
            v15 = (WCHAR *)v14;
            if ( v14 )
            {
              v16 = MemMallocAndCopy(v14);
              v17 = v16;
              if ( v16 )
              {
                FSSplitFileName(v16);
                if ( (unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(v17, 0) )
                {
                  v18 = GetProcessHeap();
                  HeapFree(v18, 0, v17);
                  FileW = CreateFileW(v15, 0xC0000000, 3u, 0, 2u, 0x80u, 0);
                  if ( FileW == (HANDLE)-1LL )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      LastError = GetLastError();
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        12,
                        WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids,
                        LastError);
                    }
                  }
                  else
                  {
                    v3 = (__int64)FileW;
                  }
                }
              }
              v21 = GetProcessHeap();
              HeapFree(v21, 0, v15);
            }
          }
        }
        else
        {
          v3 = 0;
        }
      }
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000c880  push    rbx
0x18000c882  push    rbp
0x18000c883  push    rsi
0x18000c884  push    rdi
0x18000c885  push    r14
0x18000c887  sub     rsp, 40h
0x18000c88b  mov     rsi, [rdx+8]
0x18000c88f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c893  mov     rax, rdi
0x18000c896  mov     r14, rcx
0x18000c899  inc     rax
0x18000c89c  cmp     byte ptr [rsi+rax], 0
0x18000c8a0  jnz     short loc_18000C899
0x18000c8a2  lea     ebp, [rax+1]
0x18000c8a5  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18000c8ad  mov     r9d, ebp; cbMultiByte
0x18000c8b0  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x18000c8b9  mov     r8, rsi; lpMultiByteStr
0x18000c8bc  mov     edx, 1; dwFlags
0x18000c8c1  xor     ecx, ecx; CodePage
0x18000c8c3  call    cs:__imp_MultiByteToWideChar
0x18000c8c9  test    eax, eax
0x18000c8cb  jz      loc_18000CA46
0x18000c8d1  mov     ebx, eax
0x18000c8d3  add     rbx, rbx
0x18000c8d6  call    cs:__imp_GetProcessHeap
0x18000c8dc  mov     r8, rbx; dwBytes
0x18000c8df  xor     edx, edx; dwFlags
0x18000c8e1  mov     rcx, rax; hHeap
0x18000c8e4  call    cs:__imp_HeapAlloc
0x18000c8ea  mov     rbx, rax
0x18000c8ed  test    rax, rax
0x18000c8f0  jz      loc_18000CA46
0x18000c8f6  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x18000c8fa  mov     r9d, ebp; cbMultiByte
0x18000c8fd  mov     r8, rsi; lpMultiByteStr
0x18000c900  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18000c905  mov     edx, 1; dwFlags
0x18000c90a  xor     ecx, ecx; CodePage
0x18000c90c  call    cs:__imp_MultiByteToWideChar
0x18000c912  test    eax, eax
0x18000c914  jz      loc_18000CA32
0x18000c91a  mov     rax, [r14+8]
0x18000c91e  test    rax, rax
0x18000c921  jz      short loc_18000C941
0x18000c923  mov     rdx, [r14+10h]
0x18000c927  mov     rcx, rbx
0x18000c92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c92f  sub     eax, 1
0x18000c932  jz      loc_18000CA17
0x18000c938  cmp     eax, 1
0x18000c93b  jnz     loc_18000CA32
0x18000c941  mov     rcx, [r14]; unsigned __int16 *
0x18000c944  lea     rdx, asc_180016E08; "\\"
0x18000c94b  xor     r9d, r9d
0x18000c94e  mov     r8, rbx
0x18000c951  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000c956  mov     rbp, rax
0x18000c959  test    rax, rax
0x18000c95c  jz      loc_18000CA32
0x18000c962  mov     rcx, rax; unsigned __int16 *
0x18000c965  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000c96a  mov     rsi, rax
0x18000c96d  test    rax, rax
0x18000c970  jz      loc_18000CA1E
0x18000c976  mov     rcx, rax
0x18000c979  call    FSSplitFileName
0x18000c97e  xor     edx, edx; StringSecurityDescriptor
0x18000c980  mov     rcx, rsi; lpFileName
0x18000c983  call    FSMakeDirPathExist_StringSecurityDescriptor
0x18000c988  test    eax, eax
0x18000c98a  jz      loc_18000CA1E
0x18000c990  call    cs:__imp_GetProcessHeap
0x18000c996  mov     r8, rsi; lpMem
0x18000c999  xor     edx, edx; dwFlags
0x18000c99b  mov     rcx, rax; hHeap
0x18000c99e  call    cs:__imp_HeapFree
0x18000c9a4  xor     r9d, r9d; lpSecurityAttributes
0x18000c9a7  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000c9b0  mov     [rsp+68h+cchWideChar], 80h; dwFlagsAndAttributes
0x18000c9b8  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c9bd  mov     rcx, rbp; lpFileName
0x18000c9c0  mov     dword ptr [rsp+68h+lpWideCharStr], 2; dwCreationDisposition
0x18000c9c8  lea     r8d, [r9+3]; dwShareMode
0x18000c9cc  call    cs:__imp_CreateFileW
0x18000c9d2  cmp     rax, rdi
0x18000c9d5  jnz     short loc_18000CA1B
0x18000c9d7  mov     rax, cs:WPP_GLOBAL_Control
0x18000c9de  lea     rcx, WPP_GLOBAL_Control
0x18000c9e5  cmp     rax, rcx
0x18000c9e8  jz      short loc_18000CA1E
0x18000c9ea  test    byte ptr [rax+1Ch], 1
0x18000c9ee  jz      short loc_18000CA1E
0x18000c9f0  call    cs:__imp_GetLastError
0x18000c9f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9fd  lea     r8, WPP_f77506d0df2b3a3ef06aa35cafdd3fca_Traceguids
0x18000ca04  mov     edx, 0Ch
0x18000ca09  mov     r9d, eax
0x18000ca0c  mov     rcx, [rcx+10h]
0x18000ca10  call    WPP_SF_d
0x18000ca15  jmp     short loc_18000CA1E
0x18000ca17  xor     edi, edi
0x18000ca19  jmp     short loc_18000CA32
0x18000ca1b  mov     rdi, rax
0x18000ca1e  call    cs:__imp_GetProcessHeap
0x18000ca24  mov     r8, rbp; lpMem
0x18000ca27  xor     edx, edx; dwFlags
0x18000ca29  mov     rcx, rax; hHeap
0x18000ca2c  call    cs:__imp_HeapFree
0x18000ca32  call    cs:__imp_GetProcessHeap
0x18000ca38  mov     r8, rbx; lpMem
0x18000ca3b  xor     edx, edx; dwFlags
0x18000ca3d  mov     rcx, rax; hHeap
0x18000ca40  call    cs:__imp_HeapFree
0x18000ca46  mov     rax, rdi
0x18000ca49  add     rsp, 40h
0x18000ca4d  pop     r14
0x18000ca4f  pop     rdi
0x18000ca50  pop     rsi
0x18000ca51  pop     rbp
0x18000ca52  pop     rbx
0x18000ca53  retn
```

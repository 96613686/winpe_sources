# LoadContainerHeader

- ea: `0x140053f0c`
- end: `0x1400540af`
- name: `LoadContainerHeader`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400544e4`

## callees

- `0x140053304`
- `0x140053f0c`
- `0x140080c50`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140053fde`
- `KERNEL32!HeapAlloc` at `0x140053fde`
- `KERNEL32!GetProcessHeap` at `0x140053fca`
- `KERNEL32!GetProcessHeap` at `0x140053fca`
- `KERNEL32!GetLastError` at `0x140053f8b`
- `KERNEL32!GetLastError` at `0x14005405f`
- `KERNEL32!GetLastError` at `0x140053f8b`
- `KERNEL32!GetLastError` at `0x14005405f`
- `KERNEL32!ReadFile` at `0x140053f7b`
- `KERNEL32!ReadFile` at `0x140054034`
- `KERNEL32!ReadFile` at `0x140053f7b`
- `KERNEL32!ReadFile` at `0x140054034`

## pseudocode

```c
__int64 __fastcall LoadContainerHeader(__int64 a1)
{
  __int64 v1; // rdx
  HANDLE v3; // rcx
  signed int v4; // edi
  unsigned int v5; // esi
  signed int v6; // eax
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  char *v9; // rax
  char *v10; // rbx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-40h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-38h] BYREF
  SIZE_T dwBytes[2]; // [rsp+48h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-18h]

  v1 = *(_QWORD *)(a1 + 32);
  v3 = *(HANDLE *)a1;
  Buffer = 0;
  v16 = 0;
  *(_OWORD *)dwBytes = 0;
  NumberOfBytesRead = 0;
  v4 = FileSetPointer(v3, *(_QWORD *)(v1 + 8));
  if ( v4 >= 0 )
  {
    v5 = 36;
    if ( ReadFile(*(HANDLE *)a1, &Buffer, 0x24u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 36 )
      {
        v7 = dwBytes[1];
        ProcessHeap = GetProcessHeap();
        v9 = (char *)HeapAlloc(ProcessHeap, 0, v7);
        v10 = v9;
        if ( v9 )
        {
          *(_OWORD *)v9 = Buffer;
          *((_OWORD *)v9 + 1) = *(_OWORD *)dwBytes;
          *((_DWORD *)v9 + 8) = v16;
          NumberOfBytesRead = 0;
          do
          {
            if ( !ReadFile(*(HANDLE *)a1, &v10[v5], LODWORD(dwBytes[1]) - v5, &NumberOfBytesRead, 0) )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              if ( LastError >= 0 )
                LastError = -2147467259;
              v4 = LastError;
              goto LABEL_22;
            }
            v5 += NumberOfBytesRead;
          }
          while ( NumberOfBytesRead );
          if ( v5 == LODWORD(dwBytes[1]) )
          {
            *(_QWORD *)(a1 + 40) = v10;
            return (unsigned int)v4;
          }
          v4 = -2147024866;
LABEL_22:
          MemFree(v10);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        return (unsigned int)-2147024866;
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 >= 0 )
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140053f0c  mov     [rsp-18h+arg_8], rbx
0x140053f11  mov     [rsp-18h+arg_10], rsi
0x140053f16  push    rbp
0x140053f17  push    rdi
0x140053f18  push    r14
0x140053f1a  mov     rbp, rsp
0x140053f1d  sub     rsp, 70h
0x140053f21  mov     rax, cs:__security_cookie
0x140053f28  xor     rax, rsp
0x140053f2b  mov     [rbp+var_10], rax
0x140053f2f  mov     rdx, [rcx+20h]
0x140053f33  xorps   xmm0, xmm0
0x140053f36  xor     eax, eax
0x140053f38  mov     r14, rcx
0x140053f3b  mov     rcx, [rcx]
0x140053f3e  movups  [rbp+Buffer], xmm0
0x140053f42  mov     [rbp+var_18], eax
0x140053f45  movups  xmmword ptr [rbp+dwBytes], xmm0
0x140053f49  mov     [rbp+NumberOfBytesRead], eax
0x140053f4c  mov     rdx, [rdx+8]
0x140053f50  call    FileSetPointer
0x140053f55  mov     edi, eax
0x140053f57  test    eax, eax
0x140053f59  js      loc_14005408B
0x140053f5f  mov     rcx, [r14]; hFile
0x140053f62  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140053f66  mov     esi, 24h ; '$'
0x140053f6b  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x140053f74  mov     r8d, esi; nNumberOfBytesToRead
0x140053f77  lea     rdx, [rbp+Buffer]; lpBuffer
0x140053f7b  call    cs:__imp_ReadFile
0x140053f82  nop     dword ptr [rax+rax+00h]
0x140053f87  test    eax, eax
0x140053f89  jnz     short loc_140053FB8
0x140053f8b  call    cs:__imp_GetLastError
0x140053f92  nop     dword ptr [rax+rax+00h]
0x140053f97  mov     edi, eax
0x140053f99  test    eax, eax
0x140053f9b  jle     short loc_140053FA6
0x140053f9d  movzx   edi, ax
0x140053fa0  or      edi, 80070000h
0x140053fa6  test    edi, edi
0x140053fa8  js      loc_14005408B
0x140053fae  mov     edi, 80004005h
0x140053fb3  jmp     loc_14005408B
0x140053fb8  cmp     [rbp+NumberOfBytesRead], esi
0x140053fbb  jz      short loc_140053FC7
0x140053fbd  mov     edi, 8007001Eh
0x140053fc2  jmp     loc_14005408B
0x140053fc7  mov     ebx, dword ptr [rbp+dwBytes+8]
0x140053fca  call    cs:__imp_GetProcessHeap
0x140053fd1  nop     dword ptr [rax+rax+00h]
0x140053fd6  mov     r8d, ebx; dwBytes
0x140053fd9  xor     edx, edx; dwFlags
0x140053fdb  mov     rcx, rax; hHeap
0x140053fde  call    cs:__imp_HeapAlloc
0x140053fe5  nop     dword ptr [rax+rax+00h]
0x140053fea  mov     rbx, rax
0x140053fed  test    rax, rax
0x140053ff0  jnz     short loc_140053FFC
0x140053ff2  mov     edi, 8007000Eh
0x140053ff7  jmp     loc_14005408B
0x140053ffc  movups  xmm0, [rbp+Buffer]
0x140054000  movups  xmmword ptr [rax], xmm0
0x140054003  movups  xmm1, xmmword ptr [rbp+dwBytes]
0x140054007  movups  xmmword ptr [rax+10h], xmm1
0x14005400b  mov     eax, [rbp+var_18]
0x14005400e  mov     [rbx+20h], eax
0x140054011  mov     [rbp+NumberOfBytesRead], 0
0x140054018  mov     r8d, dword ptr [rbp+dwBytes+8]
0x14005401c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140054020  mov     rcx, [r14]; hFile
0x140054023  sub     r8d, esi; nNumberOfBytesToRead
0x140054026  mov     edx, esi
0x140054028  add     rdx, rbx; lpBuffer
0x14005402b  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x140054034  call    cs:__imp_ReadFile
0x14005403b  nop     dword ptr [rax+rax+00h]
0x140054040  test    eax, eax
0x140054042  jz      short loc_14005405F
0x140054044  mov     eax, [rbp+NumberOfBytesRead]
0x140054047  add     esi, eax
0x140054049  test    eax, eax
0x14005404b  jnz     short loc_140054018
0x14005404d  cmp     esi, dword ptr [rbp+dwBytes+8]
0x140054050  jz      short loc_140054059
0x140054052  mov     edi, 8007001Eh
0x140054057  jmp     short loc_140054083
0x140054059  mov     [r14+28h], rbx
0x14005405d  jmp     short loc_14005408B
0x14005405f  call    cs:__imp_GetLastError
0x140054066  nop     dword ptr [rax+rax+00h]
0x14005406b  test    eax, eax
0x14005406d  jle     short loc_140054077
0x14005406f  movzx   eax, ax
0x140054072  or      eax, 80070000h
0x140054077  mov     edi, 80004005h
0x14005407c  test    eax, eax
0x14005407e  cmovns  eax, edi
0x140054081  mov     edi, eax
0x140054083  mov     rcx, rbx; lpMem
0x140054086  call    MemFree
0x14005408b  mov     eax, edi
0x14005408d  mov     rcx, [rbp+var_10]
0x140054091  xor     rcx, rsp; StackCookie
0x140054094  call    __security_check_cookie
0x140054099  lea     r11, [rsp+70h+var_s0]
0x14005409e  mov     rbx, [r11+28h]
0x1400540a2  mov     rsi, [r11+30h]
0x1400540a6  mov     rsp, r11
0x1400540a9  pop     r14
0x1400540ab  pop     rdi
0x1400540ac  pop     rbp
0x1400540ad  retn
```

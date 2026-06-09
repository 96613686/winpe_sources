# LoadBoxHeaderIntoHandle

- ea: `0x140053c68`
- end: `0x140053f04`
- name: `LoadBoxHeaderIntoHandle`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140054ac8`

## callees

- `0x140002326`
- `0x140053304`
- `0x140053360`
- `0x140053c68`
- `0x140080c50`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140053cc0`
- `KERNEL32!HeapAlloc` at `0x140053e3d`
- `KERNEL32!HeapAlloc` at `0x140053e74`
- `KERNEL32!HeapAlloc` at `0x140053cc0`
- `KERNEL32!HeapAlloc` at `0x140053e3d`
- `KERNEL32!HeapAlloc` at `0x140053e74`
- `KERNEL32!GetProcessHeap` at `0x140053cab`
- `KERNEL32!GetProcessHeap` at `0x140053e28`
- `KERNEL32!GetProcessHeap` at `0x140053e5d`
- `KERNEL32!GetProcessHeap` at `0x140053cab`
- `KERNEL32!GetProcessHeap` at `0x140053e28`
- `KERNEL32!GetProcessHeap` at `0x140053e5d`
- `KERNEL32!GetLastError` at `0x140053eb1`
- `KERNEL32!GetLastError` at `0x140053eb1`
- `KERNEL32!ReadFile` at `0x140053d1c`
- `KERNEL32!ReadFile` at `0x140053d1c`

## pseudocode

```c
__int64 __fastcall LoadBoxHeaderIntoHandle(__int64 a1)
{
  char *v2; // rsi
  unsigned int v3; // ebp
  unsigned int v4; // ebx
  signed int v5; // edi
  __int64 v6; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v8; // rax
  void *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r11
  __int64 v13; // rdx
  char *v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v17; // r14
  __int64 v18; // rcx
  char *v19; // rbp
  size_t v20; // r12
  HANDLE v21; // rax
  LPVOID v22; // rax
  unsigned int v23; // ebx
  HANDLE v24; // rax
  LPVOID v25; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = FileSetPointer(*(_QWORD *)a1, 0);
  if ( v5 >= 0 )
  {
    while ( 1 )
    {
      v6 = v3;
      if ( v2 )
      {
        v3 = v4;
        v8 = MemReAlloc(v2, v4, 0);
        if ( !v8 )
        {
          v5 = -2147024882;
          goto LABEL_34;
        }
        v2 = (char *)v8;
      }
      else
      {
        v3 = 0x20000;
        ProcessHeap = GetProcessHeap();
        v2 = (char *)HeapAlloc(ProcessHeap, 8u, 0x20000u);
        if ( !v2 )
          return (unsigned int)-2147024882;
      }
      v9 = *(void **)a1;
      NumberOfBytesRead = 0;
      if ( !ReadFile(v9, &v2[v6], v3 - v6, &NumberOfBytesRead, 0) )
        break;
      if ( v3 >= 0x40 )
      {
        if ( *(_WORD *)v2 != 23117 )
          goto LABEL_27;
        v10 = *((int *)v2 + 15);
        if ( v3 >= (unsigned int)v10 )
        {
          if ( *(_DWORD *)&v2[v10] != 17744 )
            goto LABEL_27;
          v11 = *(unsigned __int16 *)&v2[v10 + 6];
          v12 = *(unsigned __int16 *)&v2[v10 + 20];
          if ( v3 >= (unsigned __int64)(v10 + v12 + 8 * (v11 + 4 * v11 + 3)) )
          {
            v13 = 0;
            v14 = &v2[v12 + v10];
            if ( !(_DWORD)v11 )
              goto LABEL_27;
            do
            {
              if ( *(_QWORD *)&v14[40 * v13 + 24] == 0x64616F6C786F622ELL )
                break;
              v13 = (unsigned int)(v13 + 1);
            }
            while ( (unsigned int)v13 < (unsigned int)v11 );
            if ( (unsigned int)v11 <= (unsigned int)v13 )
            {
LABEL_27:
              v5 = -2147024883;
              goto LABEL_34;
            }
            v15 = 5 * v13;
            v16 = *(unsigned int *)&v14[8 * v15 + 44];
            v4 = v16 + *(_DWORD *)&v14[8 * v15 + 40];
            if ( v3 >= v4 )
            {
              v17 = &v2[v16];
              if ( *(_DWORD *)&v2[v16] != -1329266686 )
                goto LABEL_27;
              v18 = *((unsigned int *)v17 + 8);
              v4 = v18 + *((_DWORD *)v17 + 7);
              if ( v3 >= v4 )
              {
                v19 = &v2[v18];
                v20 = *(unsigned int *)&v14[8 * v15 + 32];
                v5 = 0;
                v21 = GetProcessHeap();
                v22 = HeapAlloc(v21, 8u, (unsigned int)v20);
                *(_QWORD *)(a1 + 16) = v22;
                if ( v22
                  && (v23 = *((_DWORD *)v17 + 7),
                      v24 = GetProcessHeap(),
                      v25 = HeapAlloc(v24, 8u, v23),
                      (*(_QWORD *)(a1 + 24) = v25) != 0) )
                {
                  memcpy_0(*(void **)(a1 + 16), v17, v20);
                  memcpy_0(*(void **)(a1 + 24), v19, *((unsigned int *)v17 + 7));
                }
                else
                {
                  v5 = -2147024882;
                }
                goto LABEL_34;
              }
            }
          }
          else
          {
            v4 = v10 + v12 + 8 * (v11 + 4 * v11 + 3);
          }
        }
        else
        {
          v4 = v10 + 264;
        }
      }
      else
      {
        v4 = 328;
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
LABEL_34:
    MemFree(v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140053c68  mov     [rsp+arg_8], rbx
0x140053c6d  mov     [rsp+arg_10], rbp
0x140053c72  push    rsi
0x140053c73  push    rdi
0x140053c74  push    r12
0x140053c76  push    r14
0x140053c78  push    r15
0x140053c7a  sub     rsp, 30h
0x140053c7e  mov     r15, rcx
0x140053c81  xor     edx, edx
0x140053c83  mov     rcx, [rcx]
0x140053c86  xor     esi, esi
0x140053c88  xor     ebp, ebp
0x140053c8a  xor     ebx, ebx
0x140053c8c  call    FileSetPointer
0x140053c91  mov     edi, eax
0x140053c93  test    eax, eax
0x140053c95  js      loc_140053EEA
0x140053c9b  mov     r12d, 20000h
0x140053ca1  mov     edi, ebp
0x140053ca3  test    rsi, rsi
0x140053ca6  jnz     short loc_140053CDE
0x140053ca8  mov     ebp, r12d
0x140053cab  call    cs:__imp_GetProcessHeap
0x140053cb2  nop     dword ptr [rax+rax+00h]
0x140053cb7  mov     r8, r12; dwBytes
0x140053cba  lea     edx, [rsi+8]; dwFlags
0x140053cbd  mov     rcx, rax; hHeap
0x140053cc0  call    cs:__imp_HeapAlloc
0x140053cc7  nop     dword ptr [rax+rax+00h]
0x140053ccc  mov     rsi, rax
0x140053ccf  test    rax, rax
0x140053cd2  jnz     short loc_140053CF9
0x140053cd4  mov     edi, 8007000Eh
0x140053cd9  jmp     loc_140053EEA
0x140053cde  mov     edx, ebx
0x140053ce0  xor     r8d, r8d
0x140053ce3  mov     rcx, rsi
0x140053ce6  mov     ebp, ebx
0x140053ce8  call    MemReAlloc
0x140053ced  test    rax, rax
0x140053cf0  jz      loc_140053EDD
0x140053cf6  mov     rsi, rax
0x140053cf9  mov     rcx, [r15]; hFile
0x140053cfc  lea     rdx, [rsi+rdi]; lpBuffer
0x140053d00  mov     r8d, ebp
0x140053d03  mov     [rsp+58h+NumberOfBytesRead], 0
0x140053d0b  sub     r8d, edi; nNumberOfBytesToRead
0x140053d0e  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x140053d17  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140053d1c  call    cs:__imp_ReadFile
0x140053d23  nop     dword ptr [rax+rax+00h]
0x140053d28  test    eax, eax
0x140053d2a  jz      loc_140053EB1
0x140053d30  cmp     ebp, 40h ; '@'
0x140053d33  jnb     short loc_140053D3F
0x140053d35  mov     ebx, 148h
0x140053d3a  jmp     loc_140053CA1
0x140053d3f  mov     eax, 5A4Dh
0x140053d44  cmp     ax, [rsi]
0x140053d47  jnz     loc_140053EAA
0x140053d4d  movsxd  r9, dword ptr [rsi+3Ch]
0x140053d51  cmp     ebp, r9d
0x140053d54  jnb     short loc_140053D62
0x140053d56  lea     ebx, [r9+108h]
0x140053d5d  jmp     loc_140053CA1
0x140053d62  cmp     dword ptr [r9+rsi], 4550h
0x140053d6a  jnz     loc_140053EAA
0x140053d70  movzx   r8d, word ptr [r9+rsi+6]
0x140053d76  movzx   r11d, word ptr [r9+rsi+14h]
0x140053d7c  lea     rax, ds:3[r8*4]
0x140053d84  add     rax, r8
0x140053d87  lea     rdx, [r11+rax*8]
0x140053d8b  mov     eax, ebp
0x140053d8d  add     rdx, r9
0x140053d90  cmp     rax, rdx
0x140053d93  jnb     short loc_140053DAC
0x140053d95  lea     ebx, ds:3[r8*4]
0x140053d9d  add     ebx, r8d
0x140053da0  lea     ecx, [r9+r11]
0x140053da4  lea     ebx, [rcx+rbx*8]
0x140053da7  jmp     loc_140053CA1
0x140053dac  add     r9, r11
0x140053daf  xor     edx, edx
0x140053db1  add     r9, rsi
0x140053db4  test    r8d, r8d
0x140053db7  jz      loc_140053EAA
0x140053dbd  lea     rcx, [rdx+rdx*4]
0x140053dc1  mov     rax, 64616F6C786F622Eh
0x140053dcb  cmp     [r9+rcx*8+18h], rax
0x140053dd0  jz      short loc_140053DD9
0x140053dd2  inc     edx
0x140053dd4  cmp     edx, r8d
0x140053dd7  jb      short loc_140053DBD
0x140053dd9  cmp     r8d, edx
0x140053ddc  jbe     loc_140053EAA
0x140053de2  lea     rdx, [rdx+rdx*4]
0x140053de6  mov     ecx, [r9+rdx*8+2Ch]
0x140053deb  mov     ebx, [r9+rdx*8+28h]
0x140053df0  add     ebx, ecx
0x140053df2  cmp     ebp, ebx
0x140053df4  jb      loc_140053CA1
0x140053dfa  lea     r14, [rsi+rcx]
0x140053dfe  cmp     dword ptr [r14], 0B0C50002h
0x140053e05  jnz     loc_140053EAA
0x140053e0b  mov     ecx, [r14+20h]
0x140053e0f  mov     ebx, [r14+1Ch]
0x140053e13  add     ebx, ecx
0x140053e15  cmp     ebp, ebx
0x140053e17  jb      loc_140053CA1
0x140053e1d  lea     rbp, [rsi+rcx]
0x140053e21  mov     r12d, [r9+rdx*8+20h]
0x140053e26  xor     edi, edi
0x140053e28  call    cs:__imp_GetProcessHeap
0x140053e2f  nop     dword ptr [rax+rax+00h]
0x140053e34  mov     r8d, r12d; dwBytes
0x140053e37  lea     edx, [rdi+8]; dwFlags
0x140053e3a  mov     rcx, rax; hHeap
0x140053e3d  call    cs:__imp_HeapAlloc
0x140053e44  nop     dword ptr [rax+rax+00h]
0x140053e49  mov     [r15+10h], rax
0x140053e4d  test    rax, rax
0x140053e50  jnz     short loc_140053E59
0x140053e52  mov     edi, 8007000Eh
0x140053e57  jmp     short loc_140053ED6
0x140053e59  mov     ebx, [r14+1Ch]
0x140053e5d  call    cs:__imp_GetProcessHeap
0x140053e64  nop     dword ptr [rax+rax+00h]
0x140053e69  mov     r8d, ebx; dwBytes
0x140053e6c  mov     edx, 8; dwFlags
0x140053e71  mov     rcx, rax; hHeap
0x140053e74  call    cs:__imp_HeapAlloc
0x140053e7b  nop     dword ptr [rax+rax+00h]
0x140053e80  mov     [r15+18h], rax
0x140053e84  test    rax, rax
0x140053e87  jz      short loc_140053E52
0x140053e89  mov     rcx, [r15+10h]; void *
0x140053e8d  mov     r8, r12; Size
0x140053e90  mov     rdx, r14; Src
0x140053e93  call    memcpy_0
0x140053e98  mov     r8d, [r14+1Ch]; Size
0x140053e9c  mov     rdx, rbp; Src
0x140053e9f  mov     rcx, [r15+18h]; void *
0x140053ea3  call    memcpy_0
0x140053ea8  jmp     short loc_140053ED6
0x140053eaa  mov     edi, 8007000Dh
0x140053eaf  jmp     short loc_140053ED6
0x140053eb1  call    cs:__imp_GetLastError
0x140053eb8  nop     dword ptr [rax+rax+00h]
0x140053ebd  mov     edi, eax
0x140053ebf  test    eax, eax
0x140053ec1  jle     short loc_140053ECC
0x140053ec3  movzx   edi, ax
0x140053ec6  or      edi, 80070000h
0x140053ecc  test    edi, edi
0x140053ece  mov     eax, 80004005h
0x140053ed3  cmovns  edi, eax
0x140053ed6  test    rsi, rsi
0x140053ed9  jz      short loc_140053EEA
0x140053edb  jmp     short loc_140053EE2
0x140053edd  mov     edi, 8007000Eh
0x140053ee2  mov     rcx, rsi; lpMem
0x140053ee5  call    MemFree
0x140053eea  mov     rbx, [rsp+58h+arg_8]
0x140053eef  mov     eax, edi
0x140053ef1  mov     rbp, [rsp+58h+arg_10]
0x140053ef6  add     rsp, 30h
0x140053efa  pop     r15
0x140053efc  pop     r14
0x140053efe  pop     r12
0x140053f00  pop     rdi
0x140053f01  pop     rsi
0x140053f02  retn
```

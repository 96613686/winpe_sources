# OPFlushToSpool

- ea: `0x180016df0`
- end: `0x180017095`
- name: `OPFlushToSpool`
- size: `677`
- prototype: `bool __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c180`
- `0x18000f2e4`
- `0x18001502c`
- `0x180015524`
- `0x180015750`
- `0x180016898`
- `0x180016a50`
- `0x1800170a0`

## callees

- `0x180016df0`
- `0x18005e0c4`
- `0x18005f010`

## import_xrefs

- `WINSPOOL!WritePrinter` at `0x180017048`
- `WINSPOOL!WritePrinter` at `0x180017048`
- `KERNEL32!WriteFile` at `0x180016f60`
- `KERNEL32!WriteFile` at `0x180016f60`
- `KERNEL32!CreateFileW` at `0x180016f24`
- `KERNEL32!CreateFileW` at `0x180016f24`
- `KERNEL32!LocalAlloc` at `0x180016e58`
- `KERNEL32!LocalAlloc` at `0x180016e58`

## pseudocode

```c
bool __fastcall OPFlushToSpool(__int64 a1)
{
  _DWORD *v1; // r14
  DWORD v4; // esi
  char *v5; // rax
  char *v6; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rcx
  HANDLE FileW; // rax
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  DWORD pcWritten; // [rsp+60h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+10h] BYREF

  v1 = *(_DWORD **)(a1 + 2896);
  pcWritten = 0;
  if ( v1 )
  {
    if ( *(_DWORD *)(a1 + 3440) )
      goto LABEL_37;
    v4 = *v1 - *(_DWORD *)(a1 + 2896) - 16;
    if ( *v1 - *(_DWORD *)(a1 + 2896) == 16 )
      goto LABEL_37;
    if ( *(_DWORD *)(a1 + 3664) )
    {
      v5 = (char *)LocalAlloc(0x40u, 0x1010u);
      v6 = v5;
      if ( v5 )
      {
        if ( *(_QWORD *)(a1 + 3672) )
          **(_QWORD **)(a1 + 3680) = v5;
        else
          *(_QWORD *)(a1 + 3672) = v5;
        v7 = 4096;
        *(_QWORD *)(a1 + 3680) = v5;
        if ( v4 < 0x1000 )
          v7 = v4;
        memcpy_0(v5 + 12, v1 + 4, v7);
        *((_DWORD *)v6 + 2) = v7;
        if ( v4 == v7 )
          goto LABEL_37;
      }
    }
    else
    {
      v8 = *(_QWORD *)(a1 + 3464);
      if ( (*(_BYTE *)(v8 + 12) & 1) != 0
        && (*(_BYTE *)(v8 + 16) & 1) != 0
        && (*(_DWORD *)(a1 + 2152) & 0x10000000) == 0 )
      {
        FileW = *(HANDLE *)(a1 + 2200);
        NumberOfBytesWritten = 0;
        if ( FileW
          || (FileW = CreateFileW(*(LPCWSTR *)(a1 + 2192), 0x40000000u, 0, 0, 2u, 0x100100u, 0),
              *(_QWORD *)(a1 + 2200) = FileW,
              FileW != (HANDLE)-1LL) )
        {
          if ( WriteFile(FileW, (LPCVOID)(*(_QWORD *)(a1 + 2896) + 16LL), v4, &NumberOfBytesWritten, 0) )
          {
            *(_DWORD *)(a1 + 2208) += v4;
LABEL_37:
            **(_QWORD **)(a1 + 2896) = *(_QWORD *)(a1 + 2896) + 16LL;
            return *(_DWORD *)(a1 + 3440) == 0;
          }
        }
      }
      else
      {
        v10 = *(_DWORD *)(a1 + 3480);
        if ( (v10 & 0x10000) != 0 )
        {
          v11 = *(_DWORD *)(v8 + 8);
          v12 = v8 + 24;
          if ( !v11 )
            goto LABEL_37;
          while ( 1 )
          {
            v13 = *(_QWORD *)(v12 + 32);
            if ( v13 )
            {
              *(_QWORD *)(a1 + 32) = v13;
              *(_QWORD *)(a1 + 8) = *(_QWORD *)(v12 + 40);
              *(_QWORD *)(a1 + 48) = *(_QWORD *)(v12 + 56);
              if ( *(_QWORD *)(v12 + 72) )
              {
                if ( (*(_BYTE *)(v12 + 48) & 8) != 0 )
                  break;
              }
            }
            v12 += 176;
            if ( !--v11 )
              goto LABEL_37;
          }
          *(_DWORD *)(a1 + 3480) = v10 | 2;
          if ( *(_QWORD *)(v12 + 80) == *(_QWORD *)&IID_IPrintOemPS2.Data1
            && *(_QWORD *)(v12 + 88) == *(_QWORD *)IID_IPrintOemPS2.Data4 )
          {
            v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *, _QWORD, DWORD *))(**(_QWORD **)(v12 + 72) + 96LL))(
                    *(_QWORD *)(v12 + 72),
                    a1,
                    v1 + 4,
                    v4,
                    &pcWritten);
          }
          else
          {
            v14 = -2147467262;
          }
          *(_DWORD *)(a1 + 3480) &= ~2u;
          if ( v14 >= 0 )
            goto LABEL_37;
        }
        else if ( WritePrinter(*(HANDLE *)(a1 + 24), v1 + 4, v4, &pcWritten) && v4 == pcWritten )
        {
          goto LABEL_37;
        }
      }
    }
    *(_DWORD *)(a1 + 3440) = 1;
    goto LABEL_37;
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180016df0  mov     [rsp+arg_10], rbx
0x180016df5  mov     [rsp+arg_18], rbp
0x180016dfa  push    rsi
0x180016dfb  push    rdi
0x180016dfc  push    r14
0x180016dfe  sub     rsp, 40h
0x180016e02  mov     r14, [rcx+0B50h]
0x180016e09  mov     rdi, rcx
0x180016e0c  mov     [rsp+58h+pcWritten], 0
0x180016e14  test    r14, r14
0x180016e17  jnz     short loc_180016E26
0x180016e19  xor     eax, eax
0x180016e1b  cmp     [rcx+0D70h], eax
0x180016e21  jmp     loc_18001707E
0x180016e26  cmp     dword ptr [rcx+0D70h], 0
0x180016e2d  jnz     loc_180017068
0x180016e33  mov     esi, [r14]
0x180016e36  sub     esi, [rcx+0B50h]
0x180016e3c  add     esi, 0FFFFFFF0h
0x180016e3f  jz      loc_180017068
0x180016e45  cmp     dword ptr [rcx+0E50h], 0
0x180016e4c  jz      short loc_180016EBE
0x180016e4e  mov     edx, 1010h; uBytes
0x180016e53  mov     ecx, 40h ; '@'; uFlags
0x180016e58  call    cs:__imp_LocalAlloc
0x180016e5f  nop     dword ptr [rax+rax+00h]
0x180016e64  mov     rbp, rax
0x180016e67  test    rax, rax
0x180016e6a  jz      loc_18001705E
0x180016e70  cmp     qword ptr [rdi+0E58h], 0
0x180016e78  jnz     short loc_180016E83
0x180016e7a  mov     [rdi+0E58h], rax
0x180016e81  jmp     short loc_180016E8D
0x180016e83  mov     rax, [rdi+0E60h]
0x180016e8a  mov     [rax], rbp
0x180016e8d  mov     ebx, 1000h
0x180016e92  mov     [rdi+0E60h], rbp
0x180016e99  cmp     esi, ebx
0x180016e9b  lea     rdx, [r14+10h]; Src
0x180016e9f  lea     rcx, [rbp+0Ch]; void *
0x180016ea3  cmovb   ebx, esi
0x180016ea6  mov     r8d, ebx; Size
0x180016ea9  call    memcpy_0
0x180016eae  mov     [rbp+8], ebx
0x180016eb1  cmp     esi, ebx
0x180016eb3  jnz     loc_18001705E
0x180016eb9  jmp     loc_180017068
0x180016ebe  mov     rcx, [rcx+0D88h]
0x180016ec5  test    byte ptr [rcx+0Ch], 1
0x180016ec9  jz      loc_180016F7F
0x180016ecf  test    byte ptr [rcx+10h], 1
0x180016ed3  jz      loc_180016F7F
0x180016ed9  test    dword ptr [rdi+868h], 10000000h
0x180016ee3  jnz     loc_180016F7F
0x180016ee9  mov     rax, [rdi+898h]
0x180016ef0  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180016ef8  test    rax, rax
0x180016efb  jnz     short loc_180016F41
0x180016efd  mov     rcx, [rdi+890h]; lpFileName
0x180016f04  xor     r9d, r9d; lpSecurityAttributes
0x180016f07  mov     [rsp+58h+hTemplateFile], rax; hTemplateFile
0x180016f0c  xor     r8d, r8d; dwShareMode
0x180016f0f  mov     [rsp+58h+dwFlagsAndAttributes], 100100h; dwFlagsAndAttributes
0x180016f17  mov     edx, 40000000h; dwDesiredAccess
0x180016f1c  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180016f24  call    cs:__imp_CreateFileW
0x180016f2b  nop     dword ptr [rax+rax+00h]
0x180016f30  mov     [rdi+898h], rax
0x180016f37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016f3b  jz      loc_18001705E
0x180016f41  mov     rdx, [rdi+0B50h]
0x180016f48  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016f4d  add     rdx, 10h; lpBuffer
0x180016f51  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180016f5a  mov     r8d, esi; nNumberOfBytesToWrite
0x180016f5d  mov     rcx, rax; hFile
0x180016f60  call    cs:__imp_WriteFile
0x180016f67  nop     dword ptr [rax+rax+00h]
0x180016f6c  test    eax, eax
0x180016f6e  jz      loc_18001705E
0x180016f74  add     [rdi+8A0h], esi
0x180016f7a  jmp     loc_180017068
0x180016f7f  mov     r8d, [rdi+0D98h]
0x180016f86  bt      r8d, 10h
0x180016f8b  jnb     loc_180017038
0x180016f91  mov     edx, [rcx+8]
0x180016f94  add     rcx, 18h
0x180016f98  test    edx, edx
0x180016f9a  jz      loc_180017068
0x180016fa0  mov     rax, [rcx+20h]
0x180016fa4  test    rax, rax
0x180016fa7  jz      short loc_180016FCA
0x180016fa9  mov     [rdi+20h], rax
0x180016fad  mov     rax, [rcx+28h]
0x180016fb1  mov     [rdi+8], rax
0x180016fb5  mov     rax, [rcx+38h]
0x180016fb9  mov     [rdi+30h], rax
0x180016fbd  cmp     qword ptr [rcx+48h], 0
0x180016fc2  jz      short loc_180016FCA
0x180016fc4  test    byte ptr [rcx+30h], 8
0x180016fc8  jnz     short loc_180016FDB
0x180016fca  add     rcx, 0B0h
0x180016fd1  add     edx, 0FFFFFFFFh
0x180016fd4  jnz     short loc_180016FA0
0x180016fd6  jmp     loc_180017068
0x180016fdb  or      r8d, 2
0x180016fdf  mov     [rdi+0D98h], r8d
0x180016fe6  mov     rax, [rcx+50h]
0x180016fea  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x180016ff1  jnz     short loc_180017026
0x180016ff3  mov     rax, [rcx+58h]
0x180016ff7  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x180016ffe  jnz     short loc_180017026
0x180017000  mov     rcx, [rcx+48h]
0x180017004  lea     rdx, [rsp+58h+pcWritten]
0x180017009  mov     qword ptr [rsp+58h+dwCreationDisposition], rdx
0x18001700e  lea     r8, [r14+10h]
0x180017012  mov     r9d, esi
0x180017015  mov     rdx, rdi
0x180017018  mov     rax, [rcx]
0x18001701b  mov     rax, [rax+60h]
0x18001701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017024  jmp     short loc_18001702B
0x180017026  mov     eax, 80004002h
0x18001702b  and     dword ptr [rdi+0D98h], 0FFFFFFFDh
0x180017032  test    eax, eax
0x180017034  jns     short loc_180017068
0x180017036  jmp     short loc_18001705E
0x180017038  mov     rcx, [rdi+18h]; hPrinter
0x18001703c  lea     rdx, [r14+10h]; pBuf
0x180017040  lea     r9, [rsp+58h+pcWritten]; pcWritten
0x180017045  mov     r8d, esi; cbBuf
0x180017048  call    cs:__imp_WritePrinter
0x18001704f  nop     dword ptr [rax+rax+00h]
0x180017054  test    eax, eax
0x180017056  jz      short loc_18001705E
0x180017058  cmp     esi, [rsp+58h+pcWritten]
0x18001705c  jz      short loc_180017068
0x18001705e  mov     dword ptr [rdi+0D70h], 1
0x180017068  mov     rcx, [rdi+0B50h]
0x18001706f  lea     rax, [rcx+10h]
0x180017073  mov     [rcx], rax
0x180017076  xor     eax, eax
0x180017078  cmp     [rdi+0D70h], eax
0x18001707e  mov     rbx, [rsp+58h+arg_10]
0x180017083  setz    al
0x180017086  mov     rbp, [rsp+58h+arg_18]
0x18001708b  add     rsp, 40h
0x18001708f  pop     r14
0x180017091  pop     rdi
0x180017092  pop     rsi
0x180017093  retn
```

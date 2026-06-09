# OPFlushToSpool

- ea: `0x1800166a0`
- end: `0x18001692c`
- name: `OPFlushToSpool`
- size: `652`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bd5c`
- `0x18000ee40`
- `0x180014988`
- `0x180014e7c`
- `0x180015074`
- `0x180016158`
- `0x180016310`
- `0x180016940`

## callees

- `0x1800166a0`
- `0x18005c434`
- `0x18005d010`

## import_xrefs

- `WINSPOOL!WritePrinter` at `0x1800168e6`
- `WINSPOOL!WritePrinter` at `0x1800168e6`
- `KERNEL32!WriteFile` at `0x180016804`
- `KERNEL32!WriteFile` at `0x180016804`
- `KERNEL32!CreateFileW` at `0x1800167ce`
- `KERNEL32!CreateFileW` at `0x1800167ce`
- `KERNEL32!LocalAlloc` at `0x180016708`
- `KERNEL32!LocalAlloc` at `0x180016708`

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
0x1800166a0  mov     [rsp+arg_10], rbx
0x1800166a5  mov     [rsp+arg_18], rbp
0x1800166aa  push    rsi
0x1800166ab  push    rdi
0x1800166ac  push    r14
0x1800166ae  sub     rsp, 40h
0x1800166b2  mov     r14, [rcx+0B50h]
0x1800166b9  mov     rdi, rcx
0x1800166bc  mov     [rsp+58h+pcWritten], 0
0x1800166c4  test    r14, r14
0x1800166c7  jnz     short loc_1800166D6
0x1800166c9  xor     eax, eax
0x1800166cb  cmp     [rcx+0D70h], eax
0x1800166d1  jmp     loc_180016916
0x1800166d6  cmp     dword ptr [rcx+0D70h], 0
0x1800166dd  jnz     loc_180016900
0x1800166e3  mov     esi, [r14]
0x1800166e6  sub     esi, [rcx+0B50h]
0x1800166ec  add     esi, 0FFFFFFF0h
0x1800166ef  jz      loc_180016900
0x1800166f5  cmp     dword ptr [rcx+0E50h], 0
0x1800166fc  jz      short loc_180016768
0x1800166fe  mov     edx, 1010h; uBytes
0x180016703  mov     ecx, 40h ; '@'; uFlags
0x180016708  call    cs:__imp_LocalAlloc
0x18001670e  mov     rbp, rax
0x180016711  test    rax, rax
0x180016714  jz      loc_1800168F6
0x18001671a  cmp     qword ptr [rdi+0E58h], 0
0x180016722  jnz     short loc_18001672D
0x180016724  mov     [rdi+0E58h], rax
0x18001672b  jmp     short loc_180016737
0x18001672d  mov     rax, [rdi+0E60h]
0x180016734  mov     [rax], rbp
0x180016737  mov     ebx, 1000h
0x18001673c  mov     [rdi+0E60h], rbp
0x180016743  cmp     esi, ebx
0x180016745  lea     rdx, [r14+10h]; Src
0x180016749  lea     rcx, [rbp+0Ch]; void *
0x18001674d  cmovb   ebx, esi
0x180016750  mov     r8d, ebx; Size
0x180016753  call    memcpy_0
0x180016758  mov     [rbp+8], ebx
0x18001675b  cmp     esi, ebx
0x18001675d  jnz     loc_1800168F6
0x180016763  jmp     loc_180016900
0x180016768  mov     rcx, [rcx+0D88h]
0x18001676f  test    byte ptr [rcx+0Ch], 1
0x180016773  jz      loc_18001681D
0x180016779  test    byte ptr [rcx+10h], 1
0x18001677d  jz      loc_18001681D
0x180016783  test    dword ptr [rdi+868h], 10000000h
0x18001678d  jnz     loc_18001681D
0x180016793  mov     rax, [rdi+898h]
0x18001679a  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800167a2  test    rax, rax
0x1800167a5  jnz     short loc_1800167E5
0x1800167a7  mov     rcx, [rdi+890h]; lpFileName
0x1800167ae  xor     r9d, r9d; lpSecurityAttributes
0x1800167b1  mov     [rsp+58h+hTemplateFile], rax; hTemplateFile
0x1800167b6  xor     r8d, r8d; dwShareMode
0x1800167b9  mov     [rsp+58h+dwFlagsAndAttributes], 100100h; dwFlagsAndAttributes
0x1800167c1  mov     edx, 40000000h; dwDesiredAccess
0x1800167c6  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x1800167ce  call    cs:__imp_CreateFileW
0x1800167d4  mov     [rdi+898h], rax
0x1800167db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800167df  jz      loc_1800168F6
0x1800167e5  mov     rdx, [rdi+0B50h]
0x1800167ec  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800167f1  add     rdx, 10h; lpBuffer
0x1800167f5  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x1800167fe  mov     r8d, esi; nNumberOfBytesToWrite
0x180016801  mov     rcx, rax; hFile
0x180016804  call    cs:__imp_WriteFile
0x18001680a  test    eax, eax
0x18001680c  jz      loc_1800168F6
0x180016812  add     [rdi+8A0h], esi
0x180016818  jmp     loc_180016900
0x18001681d  mov     r8d, [rdi+0D98h]
0x180016824  bt      r8d, 10h
0x180016829  jnb     loc_1800168D6
0x18001682f  mov     edx, [rcx+8]
0x180016832  add     rcx, 18h
0x180016836  test    edx, edx
0x180016838  jz      loc_180016900
0x18001683e  mov     rax, [rcx+20h]
0x180016842  test    rax, rax
0x180016845  jz      short loc_180016868
0x180016847  mov     [rdi+20h], rax
0x18001684b  mov     rax, [rcx+28h]
0x18001684f  mov     [rdi+8], rax
0x180016853  mov     rax, [rcx+38h]
0x180016857  mov     [rdi+30h], rax
0x18001685b  cmp     qword ptr [rcx+48h], 0
0x180016860  jz      short loc_180016868
0x180016862  test    byte ptr [rcx+30h], 8
0x180016866  jnz     short loc_180016879
0x180016868  add     rcx, 0B0h
0x18001686f  add     edx, 0FFFFFFFFh
0x180016872  jnz     short loc_18001683E
0x180016874  jmp     loc_180016900
0x180016879  or      r8d, 2
0x18001687d  mov     [rdi+0D98h], r8d
0x180016884  mov     rax, [rcx+50h]
0x180016888  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001688f  jnz     short loc_1800168C4
0x180016891  mov     rax, [rcx+58h]
0x180016895  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001689c  jnz     short loc_1800168C4
0x18001689e  mov     rcx, [rcx+48h]
0x1800168a2  lea     rdx, [rsp+58h+pcWritten]
0x1800168a7  mov     qword ptr [rsp+58h+dwCreationDisposition], rdx
0x1800168ac  lea     r8, [r14+10h]
0x1800168b0  mov     r9d, esi
0x1800168b3  mov     rdx, rdi
0x1800168b6  mov     rax, [rcx]
0x1800168b9  mov     rax, [rax+60h]
0x1800168bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c2  jmp     short loc_1800168C9
0x1800168c4  mov     eax, 80004002h
0x1800168c9  and     dword ptr [rdi+0D98h], 0FFFFFFFDh
0x1800168d0  test    eax, eax
0x1800168d2  jns     short loc_180016900
0x1800168d4  jmp     short loc_1800168F6
0x1800168d6  mov     rcx, [rdi+18h]; hPrinter
0x1800168da  lea     rdx, [r14+10h]; pBuf
0x1800168de  lea     r9, [rsp+58h+pcWritten]; pcWritten
0x1800168e3  mov     r8d, esi; cbBuf
0x1800168e6  call    cs:__imp_WritePrinter
0x1800168ec  test    eax, eax
0x1800168ee  jz      short loc_1800168F6
0x1800168f0  cmp     esi, [rsp+58h+pcWritten]
0x1800168f4  jz      short loc_180016900
0x1800168f6  mov     dword ptr [rdi+0D70h], 1
0x180016900  mov     rcx, [rdi+0B50h]
0x180016907  lea     rax, [rcx+10h]
0x18001690b  mov     [rcx], rax
0x18001690e  xor     eax, eax
0x180016910  cmp     [rdi+0D70h], eax
0x180016916  mov     rbx, [rsp+58h+arg_10]
0x18001691b  setz    al
0x18001691e  mov     rbp, [rsp+58h+arg_18]
0x180016923  add     rsp, 40h
0x180016927  pop     r14
0x180016929  pop     rdi
0x18001692a  pop     rsi
0x18001692b  retn
```

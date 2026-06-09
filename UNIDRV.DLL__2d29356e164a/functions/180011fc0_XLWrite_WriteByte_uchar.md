# XLWrite::WriteByte(uchar)

- ea: `0x180011fc0`
- end: `0x180012084`
- name: `?WriteByte@XLWrite@@QEAAJE@Z`
- size: `196`
- prototype: `__int64 __fastcall(XLWrite *__hidden this, unsigned __int8)`
- caller_count: `56`
- callee_count: `2`
- tags: ``

## callers

- `0x18000edc0`
- `0x18000f324`
- `0x18000f420`
- `0x18000f700`
- `0x18000f7ac`
- `0x18000faa8`
- `0x18000fde0`
- `0x180011f0c`
- `0x18001208c`
- `0x180012118`
- `0x180012298`
- `0x1800122e0`
- `0x18001265c`
- `0x1800128c0`
- `0x180012a94`
- `0x180012cf0`
- `0x18001348c`
- `0x180013944`
- `0x180013e00`
- `0x180014270`
- `0x1800148e0`
- `0x180015380`
- `0x1800155b0`
- `0x180015934`
- `0x1800159a8`
- `0x180015d30`
- `0x18001d530`
- `0x18001d890`
- `0x18001dc38`
- `0x180030de0`
- `0x1800318b4`
- `0x18003c178`
- `0x18003c708`
- `0x18003d590`
- `0x18003dbb0`
- `0x18003e54c`
- `0x180040e00`
- `0x180042668`
- `0x1800427a0`
- `0x1800446c4`
- `0x1800452d0`
- `0x180045b8c`
- `0x18006be30`
- `0x18006c9b0`
- `0x18006cac8`
- `0x18006cb00`
- `0x18006cb34`
- `0x18006cb88`
- `0x18006cbdc`
- `0x18006cc1c`

## callees

- `0x180011fc0`
- `0x180074580`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180012068`
- `KERNEL32!LocalFree` at `0x180012068`
- `KERNEL32!LocalAlloc` at `0x180012036`
- `KERNEL32!LocalAlloc` at `0x180012036`

## pseudocode

```c
__int64 __fastcall XLWrite::WriteByte(XLWrite *this, char a2)
{
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned int v7; // eax
  unsigned int v8; // esi
  char *v9; // rbp
  const void *v10; // rdx
  unsigned int v11; // eax
  void *v12; // rcx
  __int64 v13; // rax

  v4 = *((unsigned int *)this + 7);
  if ( (int)v4 + 1 >= (unsigned int)v4 )
  {
    v5 = *((unsigned int *)this + 6);
    if ( v5 < v4 + 8 )
    {
      v7 = v5 + 8;
      if ( (int)v5 + 8 < (unsigned int)v5 )
        return 2147549183LL;
      v8 = v5 + 2048;
      if ( (int)v5 + 2048 < (unsigned int)v5 || v7 > 0xFFFFF7FF )
        return 2147549183LL;
      for ( ; v8 < v7; v8 += 2048 )
        ;
      v9 = (char *)LocalAlloc(0, v8);
      if ( !v9 )
        return 2147549183LL;
      v10 = (const void *)*((_QWORD *)this + 1);
      if ( v10 )
      {
        v11 = *((_DWORD *)this + 7);
        if ( v11 )
          memcpy_0(v9, v10, v11);
        v12 = (void *)*((_QWORD *)this + 1);
        if ( v12 )
          LocalFree(v12);
      }
      v13 = *((unsigned int *)this + 7);
      *((_DWORD *)this + 6) = v8;
      *((_QWORD *)this + 2) = &v9[v13];
      *((_QWORD *)this + 1) = v9;
    }
    if ( *((_QWORD *)this + 1) )
    {
      *(_BYTE *)(*((_QWORD *)this + 2))++ = a2;
      ++*((_DWORD *)this + 7);
      return 0;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180011fc0  push    rbx
0x180011fc2  push    rbp
0x180011fc3  push    rsi
0x180011fc4  push    rdi
0x180011fc5  sub     rsp, 28h
0x180011fc9  mov     rbx, rcx
0x180011fcc  movzx   edi, dl
0x180011fcf  mov     ecx, [rcx+1Ch]
0x180011fd2  lea     eax, [rcx+1]
0x180011fd5  cmp     eax, ecx
0x180011fd7  jb      short loc_18001200C
0x180011fd9  mov     edx, [rbx+18h]
0x180011fdc  lea     rax, [rcx+8]
0x180011fe0  cmp     rdx, rax
0x180011fe3  jb      short loc_180012005
0x180011fe5  cmp     qword ptr [rbx+8], 0
0x180011fea  jz      short loc_18001200C
0x180011fec  mov     rax, [rbx+10h]
0x180011ff0  mov     [rax], dil
0x180011ff3  inc     qword ptr [rbx+10h]
0x180011ff7  inc     dword ptr [rbx+1Ch]
0x180011ffa  xor     eax, eax
0x180011ffc  add     rsp, 28h
0x180012000  pop     rdi
0x180012001  pop     rsi
0x180012002  pop     rbp
0x180012003  pop     rbx
0x180012004  retn
0x180012005  lea     eax, [rdx+8]
0x180012008  cmp     eax, edx
0x18001200a  jnb     short loc_180012013
0x18001200c  mov     eax, 8000FFFFh
0x180012011  jmp     short loc_180011FFC
0x180012013  lea     esi, [rdx+800h]
0x180012019  cmp     esi, edx
0x18001201b  jb      short loc_18001200C
0x18001201d  cmp     eax, 0FFFFF7FFh
0x180012022  ja      short loc_18001200C
0x180012024  cmp     esi, eax
0x180012026  jnb     short loc_180012032
0x180012028  add     esi, 800h
0x18001202e  cmp     esi, eax
0x180012030  jb      short loc_180012028
0x180012032  mov     edx, esi; uBytes
0x180012034  xor     ecx, ecx; uFlags
0x180012036  call    cs:__imp_LocalAlloc
0x18001203c  mov     rbp, rax
0x18001203f  test    rax, rax
0x180012042  jz      short loc_18001200C
0x180012044  mov     rdx, [rbx+8]; Src
0x180012048  test    rdx, rdx
0x18001204b  jz      short loc_18001206E
0x18001204d  mov     eax, [rbx+1Ch]
0x180012050  test    eax, eax
0x180012052  jz      short loc_18001205F
0x180012054  mov     r8d, eax; Size
0x180012057  mov     rcx, rbp; void *
0x18001205a  call    memcpy_0
0x18001205f  mov     rcx, [rbx+8]; hMem
0x180012063  test    rcx, rcx
0x180012066  jz      short loc_18001206E
0x180012068  call    cs:__imp_LocalFree
0x18001206e  mov     eax, [rbx+1Ch]
0x180012071  add     rax, rbp
0x180012074  mov     [rbx+18h], esi
0x180012077  mov     [rbx+10h], rax
0x18001207b  mov     [rbx+8], rbp
0x18001207f  jmp     loc_180011FE5
```

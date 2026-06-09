# SIPolicyPmGetTokenFolderFiles

- ea: `0x180021758`
- end: `0x1800218b4`
- name: `SIPolicyPmGetTokenFolderFiles`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180020e20`

## callees

- `0x180003870`
- `0x180020ecc`
- `0x180021758`
- `0x18002247c`
- `0x180022f2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002189b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002189b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800217b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002184c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800217b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002184c`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetTokenFolderFiles(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r12
  __int64 v9; // rsi
  char *v12; // rdi
  int NameFromPath; // ebx
  int PolicyFolderFiles; // eax
  unsigned int v15; // r14d
  HLOCAL v16; // rax
  void *Src[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING v19[2]; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+C0h] [rbp+48h] BYREF

  v7 = a6;
  v8 = a5;
  v9 = 0;
  v19[0].Buffer = L"*.TOK";
  *(_QWORD *)&v19[0].Length = 786442;
  HIDWORD(Src[0]) = 0;
  v20 = 0;
  v19[1] = 0;
  if ( a4 || !a5 )
  {
    v12 = (char *)a4;
  }
  else
  {
    v12 = (char *)LocalAlloc(0x40u, 24LL * a6);
    if ( !v12 )
    {
      NameFromPath = -1073741801;
      *a7 = 0;
      return (unsigned int)NameFromPath;
    }
  }
  PolicyFolderFiles = SIPolicyPmGetPolicyFolderFiles(a1, a2, v19, a4, 0, (__int64)v12, v7, &v20);
  v15 = v20;
  NameFromPath = PolicyFolderFiles;
  if ( PolicyFolderFiles >= 0 && v8 )
  {
    while ( (unsigned int)v9 < v15 )
    {
      *(_OWORD *)Src = 0;
      NameFromPath = SIPolicyPmFindNameFromPath(&v12[24 * v9], Src);
      if ( NameFromPath < 0 )
        break;
      if ( LOWORD(Src[0]) <= 8u )
      {
        NameFromPath = -1073741275;
        break;
      }
      LOWORD(Src[0]) -= 8;
      v16 = LocalAlloc(0x40u, LOWORD(Src[0]) + 2LL);
      *(_QWORD *)(v8 + 8 * v9) = v16;
      if ( !v16 )
      {
        NameFromPath = -1073741801;
        break;
      }
      memcpy_0(v16, Src[1], LOWORD(Src[0]));
      v9 = (unsigned int)(v9 + 1);
    }
  }
  *a7 = v15;
  if ( v12 && v12 != (char *)a4 )
  {
    SIPolicyPmFreeFileItems(v12, v15);
    LocalFree(v12);
  }
  return (unsigned int)NameFromPath;
}

```

## disassembly

```asm
0x180021758  mov     [rsp-40h+arg_0], ecx
0x18002175c  push    rbp
0x18002175d  push    rbx
0x18002175e  push    rsi
0x18002175f  push    rdi
0x180021760  push    r12
0x180021762  push    r13
0x180021764  push    r14
0x180021766  push    r15
0x180021768  mov     rbp, rsp
0x18002176b  sub     rsp, 78h
0x18002176f  mov     ebx, [rbp+arg_28]
0x180021772  lea     rax, aTok; "*.TOK"
0x180021779  mov     r12, [rbp+arg_20]
0x18002177d  xor     esi, esi
0x18002177f  mov     [rbp+var_20], rax
0x180021783  xorps   xmm0, xmm0
0x180021786  xor     eax, eax
0x180021788  mov     [rbp+var_28], 0C000Ah
0x180021790  mov     dword ptr [rbp+Src+4], eax
0x180021793  mov     r13, r9
0x180021796  mov     [rbp+arg_0], esi
0x180021799  mov     r14, rdx
0x18002179c  movups  [rbp+var_18], xmm0
0x1800217a0  test    r9, r9
0x1800217a3  jnz     short loc_1800217D3
0x1800217a5  test    r12, r12
0x1800217a8  jz      short loc_1800217D3
0x1800217aa  lea     rdx, [rbx+rbx*2]
0x1800217ae  shl     rdx, 3; uBytes
0x1800217b2  lea     ecx, [rax+40h]; uFlags
0x1800217b5  call    cs:__imp_LocalAlloc
0x1800217bb  mov     rdi, rax
0x1800217be  test    rax, rax
0x1800217c1  jnz     short loc_1800217D6
0x1800217c3  mov     rax, [rbp+arg_30]
0x1800217c7  mov     ebx, 0C0000017h
0x1800217cc  mov     [rax], esi
0x1800217ce  jmp     loc_1800218A1
0x1800217d3  mov     rdi, r13
0x1800217d6  lea     rax, [rbp+arg_0]
0x1800217da  mov     rdx, r14
0x1800217dd  mov     [rsp+78h+var_40], rax
0x1800217e2  lea     r8, [rbp+var_28]
0x1800217e6  mov     [rsp+78h+var_48], ebx
0x1800217ea  mov     [rsp+78h+var_50], rdi
0x1800217ef  mov     [rsp+78h+var_58], sil
0x1800217f4  call    SIPolicyPmGetPolicyFolderFiles
0x1800217f9  mov     r14d, [rbp+arg_0]
0x1800217fd  mov     ebx, eax
0x1800217ff  test    eax, eax
0x180021801  js      short loc_18002187C
0x180021803  test    r12, r12
0x180021806  jz      short loc_18002187C
0x180021808  cmp     esi, r14d
0x18002180b  jnb     short loc_18002187C
0x18002180d  lea     rax, [rsi+rsi*2]
0x180021811  xorps   xmm0, xmm0
0x180021814  lea     rcx, [rdi+rax*8]
0x180021818  lea     rdx, [rbp+Src]
0x18002181c  movups  xmmword ptr [rbp+Src], xmm0
0x180021820  call    SIPolicyPmFindNameFromPath
0x180021825  mov     ebx, eax
0x180021827  test    eax, eax
0x180021829  js      short loc_18002187C
0x18002182b  movzx   eax, word ptr [rbp+Src]
0x18002182f  mov     ecx, 8
0x180021834  cmp     ax, cx
0x180021837  jbe     short loc_180021877
0x180021839  sub     ax, cx
0x18002183c  mov     ecx, 40h ; '@'; uFlags
0x180021841  movzx   edx, ax
0x180021844  mov     word ptr [rbp+Src], dx
0x180021848  add     rdx, 2; uBytes
0x18002184c  call    cs:__imp_LocalAlloc
0x180021852  mov     [r12+rsi*8], rax
0x180021856  test    rax, rax
0x180021859  jz      short loc_180021870
0x18002185b  movzx   r8d, word ptr [rbp+Src]; Size
0x180021860  mov     rcx, rax; void *
0x180021863  mov     rdx, [rbp+Src+8]; Src
0x180021867  call    memcpy_0
0x18002186c  inc     esi
0x18002186e  jmp     short loc_180021808
0x180021870  mov     ebx, 0C0000017h
0x180021875  jmp     short loc_18002187C
0x180021877  mov     ebx, 0C0000225h
0x18002187c  mov     rax, [rbp+arg_30]
0x180021880  mov     [rax], r14d
0x180021883  test    rdi, rdi
0x180021886  jz      short loc_1800218A1
0x180021888  cmp     rdi, r13
0x18002188b  jz      short loc_1800218A1
0x18002188d  mov     edx, r14d
0x180021890  mov     rcx, rdi
0x180021893  call    SIPolicyPmFreeFileItems
0x180021898  mov     rcx, rdi; hMem
0x18002189b  call    cs:__imp_LocalFree
0x1800218a1  mov     eax, ebx
0x1800218a3  add     rsp, 78h
0x1800218a7  pop     r15
0x1800218a9  pop     r14
0x1800218ab  pop     r13
0x1800218ad  pop     r12
0x1800218af  pop     rdi
0x1800218b0  pop     rsi
0x1800218b1  pop     rbx
0x1800218b2  pop     rbp
0x1800218b3  retn
```

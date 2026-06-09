# CMFRSA::MFRsaSign(void *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180049fa8`
- end: `0x18004a172`
- name: `?MFRsaSign@CMFRSA@@QEAAJPEAXPEBEKPEAPEAEPEAK@Z`
- size: `458`
- prototype: `int(CMFRSA *__hidden this, void *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b900`

## callees

- `0x180002160`
- `0x180002178`
- `0x1800021a8`
- `0x180049fa8`
- `0x18004a3c0`
- `0x18004a6dc`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a112`

## pseudocode

```c
__int64 __fastcall CMFRSA::MFRsaSign(
        CMFRSA *this,
        _DWORD *a2,
        const unsigned __int8 *a3,
        int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  void *v6; // rdi
  unsigned int *v9; // r14
  unsigned int v10; // esi
  unsigned int v11; // r15d
  int v12; // ebx
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rbp
  __int64 v15; // rdx
  int v16; // eax
  _BYTE *v17; // r15
  _BYTE *v18; // rcx
  __int64 v19; // r8
  unsigned __int8 *v20; // rax
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  int v23; // [rsp+80h] [rbp+8h] BYREF
  int v24; // [rsp+84h] [rbp+Ch]
  int v25; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v24 = a4;
  v23 = 0;
  if ( a5 && (v9 = a6) != 0 && (Block = 0, v25 = 0, a3) && a4 && (v10 = a2[1] - 8, a2[1] != 8) )
  {
    v11 = 2 * v10;
    if ( 2 * v10 > v10 )
    {
      v13 = (unsigned __int8 *)o_malloc_0(v11);
      v14 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, v11);
        v12 = _PSSEncode(a3, (const struct __tagMFSubString *)&v23, 8 * v10 - 1, &v14[v10], v10);
        if ( v12 >= 0 )
        {
          v15 = 0;
          do
          {
            v14[v15] = v14[v11 - (unsigned int)v15 - 1];
            v15 = (unsigned int)(v15 + 1);
          }
          while ( (unsigned int)v15 < v10 );
          v16 = MFRsaProcess(a2, v14, v10, &Block, &v25);
          v17 = Block;
          v12 = v16;
          if ( v16 >= 0 )
          {
            v18 = o_malloc_0(v10);
            if ( v18 )
            {
              v19 = 0;
              do
              {
                v18[v19] = v17[v10 - (unsigned int)v19 - 1];
                v19 = (unsigned int)(v19 + 1);
              }
              while ( (unsigned int)v19 < v10 );
              v6 = v18;
              *v9 = v10;
            }
            else
            {
              v12 = -2147024882;
            }
          }
          if ( v17 )
            free(v17);
        }
        free(v14);
        if ( v12 >= 0 )
        {
          v20 = (unsigned __int8 *)CoTaskMemAlloc(*v9);
          *a5 = v20;
          if ( v20 )
            memcpy_0(v20, v6, *v9);
          else
            v12 = -2147024882;
        }
        if ( v6 )
          free(v6);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180049fa8  mov     rax, rsp
0x180049fab  mov     [rax+10h], rbx
0x180049faf  mov     [rax+8], rcx
0x180049fb3  push    rbp
0x180049fb4  push    rsi
0x180049fb5  push    rdi
0x180049fb6  push    r12
0x180049fb8  push    r13
0x180049fba  push    r14
0x180049fbc  push    r15
0x180049fbe  sub     rsp, 40h
0x180049fc2  xor     edi, edi
0x180049fc4  mov     [rax+0Ch], r9d
0x180049fc8  mov     rbx, r8
0x180049fcb  mov     r13, rdx
0x180049fce  mov     [rax+8], edi
0x180049fd1  cmp     [rsp+78h+arg_20], rdi
0x180049fd9  jz      loc_18004A152
0x180049fdf  mov     r14, [rsp+78h+arg_28]
0x180049fe7  test    r14, r14
0x180049fea  jz      loc_18004A152
0x180049ff0  mov     [rax-48h], rdi
0x180049ff4  mov     [rax+20h], edi
0x180049ff7  test    rbx, rbx
0x180049ffa  jz      loc_18004A152
0x18004a000  test    r9d, r9d
0x18004a003  jz      loc_18004A152
0x18004a009  mov     esi, [rdx+4]
0x18004a00c  sub     esi, 8
0x18004a00f  jz      loc_18004A152
0x18004a015  lea     r15d, [rsi+rsi]
0x18004a019  cmp     r15d, esi
0x18004a01c  ja      short loc_18004A028
0x18004a01e  mov     ebx, 80004005h
0x18004a023  jmp     loc_18004A157
0x18004a028  mov     ecx, r15d; Size
0x18004a02b  mov     r12d, r15d
0x18004a02e  call    _o_malloc_0
0x18004a033  mov     rbp, rax
0x18004a036  test    rax, rax
0x18004a039  jnz     short loc_18004A045
0x18004a03b  mov     ebx, 8007000Eh
0x18004a040  jmp     loc_18004A157
0x18004a045  mov     r8, r12; Size
0x18004a048  xor     edx, edx; Val
0x18004a04a  mov     rcx, rbp; void *
0x18004a04d  call    memset_0
0x18004a052  lea     r9, [rsi+rbp]; unsigned __int8 *
0x18004a056  mov     r12d, esi
0x18004a059  lea     r8d, ds:0FFFFFFFFFFFFFFFFh[rsi*8]; unsigned int
0x18004a061  mov     [rsp+78h+var_58], esi; unsigned int
0x18004a065  lea     rdx, [rsp+78h+arg_0]; struct __tagMFSubString *
0x18004a06d  mov     rcx, rbx; unsigned __int8 *
0x18004a070  call    ?_PSSEncode@@YAJPEBEPEBU__tagMFSubString@@KPEAEK@Z; _PSSEncode(uchar const *,__tagMFSubString const *,ulong,uchar *,ulong)
0x18004a075  mov     ebx, eax
0x18004a077  test    eax, eax
0x18004a079  js      loc_18004A103
0x18004a07f  xor     edx, edx
0x18004a081  mov     eax, r15d
0x18004a084  sub     eax, edx
0x18004a086  dec     eax
0x18004a088  mov     al, [rax+rbp]
0x18004a08b  mov     [rdx+rbp], al
0x18004a08e  inc     edx
0x18004a090  cmp     edx, esi
0x18004a092  jb      short loc_18004A081
0x18004a094  lea     rax, [rsp+78h+arg_18]
0x18004a09c  mov     r8d, esi
0x18004a09f  lea     r9, [rsp+78h+Block]
0x18004a0a4  mov     qword ptr [rsp+78h+var_58], rax
0x18004a0a9  mov     rdx, rbp
0x18004a0ac  mov     rcx, r13
0x18004a0af  call    _MFRsaProcess
0x18004a0b4  mov     r15, [rsp+78h+Block]
0x18004a0b9  mov     ebx, eax
0x18004a0bb  test    eax, eax
0x18004a0bd  js      short loc_18004A0F6
0x18004a0bf  mov     rcx, r12; Size
0x18004a0c2  call    _o_malloc_0
0x18004a0c7  mov     rcx, rax
0x18004a0ca  test    rax, rax
0x18004a0cd  jnz     short loc_18004A0D6
0x18004a0cf  mov     ebx, 8007000Eh
0x18004a0d4  jmp     short loc_18004A0F6
0x18004a0d6  xor     r8d, r8d
0x18004a0d9  mov     eax, esi
0x18004a0db  sub     eax, r8d
0x18004a0de  dec     eax
0x18004a0e0  mov     al, [rax+r15]
0x18004a0e4  mov     [r8+rcx], al
0x18004a0e8  inc     r8d
0x18004a0eb  cmp     r8d, esi
0x18004a0ee  jb      short loc_18004A0D9
0x18004a0f0  mov     rdi, rcx
0x18004a0f3  mov     [r14], esi
0x18004a0f6  test    r15, r15
0x18004a0f9  jz      short loc_18004A103
0x18004a0fb  mov     rcx, r15; Block
0x18004a0fe  call    free
0x18004a103  mov     rcx, rbp; Block
0x18004a106  call    free
0x18004a10b  test    ebx, ebx
0x18004a10d  js      short loc_18004A143
0x18004a10f  mov     ecx, [r14]; cb
0x18004a112  call    cs:__imp_CoTaskMemAlloc
0x18004a119  nop     dword ptr [rax+rax+00h]
0x18004a11e  mov     rcx, [rsp+78h+arg_20]
0x18004a126  mov     [rcx], rax
0x18004a129  test    rax, rax
0x18004a12c  jnz     short loc_18004A135
0x18004a12e  mov     ebx, 8007000Eh
0x18004a133  jmp     short loc_18004A143
0x18004a135  mov     r8d, [r14]; Size
0x18004a138  mov     rdx, rdi; Src
0x18004a13b  mov     rcx, rax; void *
0x18004a13e  call    memcpy_0
0x18004a143  test    rdi, rdi
0x18004a146  jz      short loc_18004A157
0x18004a148  mov     rcx, rdi; Block
0x18004a14b  call    free
0x18004a150  jmp     short loc_18004A157
0x18004a152  mov     ebx, 80070057h
0x18004a157  mov     eax, ebx
0x18004a159  mov     rbx, [rsp+78h+arg_8]
0x18004a161  add     rsp, 40h
0x18004a165  pop     r15
0x18004a167  pop     r14
0x18004a169  pop     r13
0x18004a16b  pop     r12
0x18004a16d  pop     rdi
0x18004a16e  pop     rsi
0x18004a16f  pop     rbp
0x18004a170  retn
```

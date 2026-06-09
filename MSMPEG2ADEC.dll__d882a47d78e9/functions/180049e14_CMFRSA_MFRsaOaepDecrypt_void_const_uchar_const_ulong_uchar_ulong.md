# CMFRSA::MFRsaOaepDecrypt(void const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180049e14`
- end: `0x180049fa2`
- name: `?MFRsaOaepDecrypt@CMFRSA@@QEAAJPEBXPEBEKPEAPEAEPEAK@Z`
- size: `398`
- prototype: `__int64 __fastcall(CMFRSA *__hidden this, const void *, const unsigned __int8 *, unsigned int, unsigned __int8 **Block, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800598f0`

## callees

- `0x180002160`
- `0x180002178`
- `0x180049c1c`
- `0x180049e14`
- `0x18004a3c0`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049f50`

## pseudocode

```c
__int64 __fastcall CMFRSA::MFRsaOaepDecrypt(
        CMFRSA *this,
        _DWORD *a2,
        const unsigned __int8 *a3,
        int a4,
        unsigned __int8 **Block,
        unsigned int *a6)
{
  unsigned __int8 **v6; // r13
  void *v7; // rbp
  unsigned int *v10; // r15
  unsigned __int8 **v11; // rsi
  unsigned int v12; // edi
  int v13; // ebx
  _BYTE *v14; // r14
  __int64 i; // rdx
  int v16; // eax
  __int64 j; // rdx
  int v18; // eax
  unsigned __int8 *v19; // rax
  void *v21; // [rsp+30h] [rbp-58h] BYREF
  CMFRSA *v22; // [rsp+90h] [rbp+8h] BYREF

  v22 = this;
  v6 = Block;
  v7 = 0;
  v21 = 0;
  if ( Block && (v10 = a6) != 0 )
  {
    v11 = 0;
    Block = 0;
    LODWORD(v22) = 0;
    if ( a3 )
    {
      v12 = 0;
      if ( a2 && (*a2 == 826364754 || *a2 == 843141970) )
        v12 = a2[2] >> 3;
      if ( v12 != a4 )
        return (unsigned int)-2147024809;
      v14 = o_malloc_0(v12);
      if ( !v14 )
        return (unsigned int)-2147024882;
      for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        v14[i] = a3[v12 - (unsigned int)i - 1];
      v16 = MFRsaProcess(a2, v14, v12, &Block, &v22);
      v11 = Block;
      v13 = v16;
      if ( v16 >= 0 )
      {
        for ( j = 0; (unsigned int)j < v12; j = (unsigned int)(j + 1) )
          v14[j] = *((_BYTE *)v11 + v12 - (unsigned int)j - 1);
        v18 = MFOAEPDecode(v12, v14, &v21, v10);
        v7 = v21;
        v13 = v18;
      }
      free(v14);
    }
    else
    {
      v13 = -2147024809;
    }
    if ( v11 )
      free(v11);
    if ( v13 >= 0 )
    {
      v19 = (unsigned __int8 *)CoTaskMemAlloc(*v10);
      *v6 = v19;
      if ( v19 )
        memcpy_0(v19, v7, *v10);
      else
        v13 = -2147024882;
    }
  }
  else
  {
    v13 = -2147024809;
  }
  if ( v7 )
    free(v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180049e14  mov     rax, rsp
0x180049e17  mov     [rax+8], rcx
0x180049e1b  push    rbx
0x180049e1c  push    rbp
0x180049e1d  push    rsi
0x180049e1e  push    rdi
0x180049e1f  push    r12
0x180049e21  push    r13
0x180049e23  push    r14
0x180049e25  push    r15
0x180049e27  sub     rsp, 48h
0x180049e2b  mov     r13, [rsp+88h+Block]
0x180049e33  xor     ebp, ebp
0x180049e35  mov     [rax-58h], rbp
0x180049e39  mov     r12, r8
0x180049e3c  mov     rbx, rdx
0x180049e3f  test    r13, r13
0x180049e42  jz      loc_180049F7C
0x180049e48  mov     r15, [rsp+88h+arg_28]
0x180049e50  test    r15, r15
0x180049e53  jz      loc_180049F7C
0x180049e59  xor     esi, esi
0x180049e5b  mov     [rax+28h], rsi
0x180049e5f  mov     [rax+8], esi
0x180049e62  test    r8, r8
0x180049e65  jz      loc_180049F37
0x180049e6b  xor     edi, edi
0x180049e6d  test    rdx, rdx
0x180049e70  jz      short loc_180049E88
0x180049e72  cmp     dword ptr [rdx], 31415352h
0x180049e78  jz      short loc_180049E82
0x180049e7a  cmp     dword ptr [rdx], 32415352h
0x180049e80  jnz     short loc_180049E88
0x180049e82  mov     edi, [rdx+8]
0x180049e85  shr     edi, 3
0x180049e88  cmp     edi, r9d
0x180049e8b  jz      short loc_180049E97
0x180049e8d  mov     ebx, 80070057h
0x180049e92  jmp     loc_180049F8E
0x180049e97  mov     ecx, edi; Size
0x180049e99  call    _o_malloc_0
0x180049e9e  mov     r14, rax
0x180049ea1  test    rax, rax
0x180049ea4  jnz     short loc_180049EB0
0x180049ea6  mov     ebx, 8007000Eh
0x180049eab  jmp     loc_180049F8E
0x180049eb0  xor     edx, edx
0x180049eb2  test    edi, edi
0x180049eb4  jz      short loc_180049ECA
0x180049eb6  mov     eax, edi
0x180049eb8  sub     eax, edx
0x180049eba  dec     eax
0x180049ebc  mov     al, [rax+r12]
0x180049ec0  mov     [rdx+r14], al
0x180049ec4  inc     edx
0x180049ec6  cmp     edx, edi
0x180049ec8  jb      short loc_180049EB6
0x180049eca  lea     rax, [rsp+88h+arg_0]
0x180049ed2  mov     r8d, edi
0x180049ed5  lea     r9, [rsp+88h+Block]
0x180049edd  mov     [rsp+88h+var_68], rax
0x180049ee2  mov     rdx, r14
0x180049ee5  mov     rcx, rbx
0x180049ee8  call    _MFRsaProcess
0x180049eed  mov     rsi, [rsp+88h+Block]
0x180049ef5  mov     ebx, eax
0x180049ef7  test    eax, eax
0x180049ef9  js      short loc_180049F2D
0x180049efb  xor     edx, edx
0x180049efd  test    edi, edi
0x180049eff  jz      short loc_180049F14
0x180049f01  mov     eax, edi
0x180049f03  sub     eax, edx
0x180049f05  dec     eax
0x180049f07  mov     al, [rax+rsi]
0x180049f0a  mov     [rdx+r14], al
0x180049f0e  inc     edx
0x180049f10  cmp     edx, edi
0x180049f12  jb      short loc_180049F01
0x180049f14  mov     r9, r15
0x180049f17  lea     r8, [rsp+88h+var_58]
0x180049f1c  mov     rdx, r14
0x180049f1f  mov     ecx, edi
0x180049f21  call    MFOAEPDecode
0x180049f26  mov     rbp, [rsp+88h+var_58]
0x180049f2b  mov     ebx, eax
0x180049f2d  mov     rcx, r14; Block
0x180049f30  call    free
0x180049f35  jmp     short loc_180049F3C
0x180049f37  mov     ebx, 80070057h
0x180049f3c  test    rsi, rsi
0x180049f3f  jz      short loc_180049F49
0x180049f41  mov     rcx, rsi; Block
0x180049f44  call    free
0x180049f49  test    ebx, ebx
0x180049f4b  js      short loc_180049F81
0x180049f4d  mov     ecx, [r15]; cb
0x180049f50  call    cs:__imp_CoTaskMemAlloc
0x180049f57  nop     dword ptr [rax+rax+00h]
0x180049f5c  mov     [r13+0], rax
0x180049f60  test    rax, rax
0x180049f63  jnz     short loc_180049F6C
0x180049f65  mov     ebx, 8007000Eh
0x180049f6a  jmp     short loc_180049F81
0x180049f6c  mov     r8d, [r15]; Size
0x180049f6f  mov     rdx, rbp; Src
0x180049f72  mov     rcx, rax; void *
0x180049f75  call    memcpy_0
0x180049f7a  jmp     short loc_180049F81
0x180049f7c  mov     ebx, 80070057h
0x180049f81  test    rbp, rbp
0x180049f84  jz      short loc_180049F8E
0x180049f86  mov     rcx, rbp; Block
0x180049f89  call    free
0x180049f8e  mov     eax, ebx
0x180049f90  add     rsp, 48h
0x180049f94  pop     r15
0x180049f96  pop     r14
0x180049f98  pop     r13
0x180049f9a  pop     r12
0x180049f9c  pop     rdi
0x180049f9d  pop     rsi
0x180049f9e  pop     rbp
0x180049f9f  pop     rbx
0x180049fa0  retn
```

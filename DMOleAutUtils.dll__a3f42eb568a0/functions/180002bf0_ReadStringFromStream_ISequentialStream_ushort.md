# ReadStringFromStream(ISequentialStream *,ushort * *)

- ea: `0x180002bf0`
- end: `0x180002d0c`
- name: `?ReadStringFromStream@@YAJPEAUISequentialStream@@PEAPEAG@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct ISequentialStream *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002bf0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002cf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002cf9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ca4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ca4`

## pseudocode

```c
__int64 __fastcall ReadStringFromStream(struct ISequentialStream *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  int v5; // ebx
  struct ISequentialStreamVtbl *lpVtbl; // rax
  unsigned __int16 *v7; // rax
  int v9; // [rsp+60h] [rbp+30h] BYREF
  SIZE_T uBytes; // [rsp+70h] [rbp+40h] BYREF
  int v11; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  LODWORD(uBytes) = 0;
  v11 = 0;
  v9 = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v5 = ((__int64 (__fastcall *)(struct ISequentialStream *, int *, __int64, int *))a1->lpVtbl->Read)(a1, &v11, 4, &v9);
    if ( v5 >= 0 )
    {
      if ( v9 != 4 )
      {
LABEL_6:
        v5 = -2147467259;
        goto LABEL_17;
      }
      if ( v11 )
      {
        lpVtbl = a1->lpVtbl;
        v9 = 0;
        v5 = ((__int64 (__fastcall *)(struct ISequentialStream *, SIZE_T *, __int64, int *))lpVtbl->Read)(
               a1,
               &uBytes,
               4,
               &v9);
        if ( v5 >= 0 )
        {
          if ( v9 == 4 )
          {
            if ( (unsigned int)uBytes <= 2 )
            {
              v5 = -2147418113;
              goto LABEL_17;
            }
            v7 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)uBytes);
            v2 = v7;
            if ( !v7 )
            {
              v5 = -2147024882;
              goto LABEL_17;
            }
            v5 = ((__int64 (__fastcall *)(struct ISequentialStream *, unsigned __int16 *, _QWORD, int *))a1->lpVtbl->Read)(
                   a1,
                   v7,
                   (unsigned int)uBytes,
                   &v9);
            if ( v5 < 0 )
              goto LABEL_17;
            if ( (_DWORD)uBytes == v9 )
            {
              v2[((unsigned __int64)(unsigned int)uBytes >> 1) - 1] = 0;
              *a2 = v2;
              v2 = 0;
              goto LABEL_17;
            }
          }
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_17:
  LocalFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002bf0  push    rbp
0x180002bf2  push    rbx
0x180002bf3  push    rsi
0x180002bf4  push    rdi
0x180002bf5  push    r14
0x180002bf7  mov     rbp, rsp
0x180002bfa  sub     rsp, 30h
0x180002bfe  xor     edi, edi
0x180002c00  mov     r14, rdx
0x180002c03  mov     dword ptr [rbp+uBytes], edi
0x180002c06  mov     rsi, rcx
0x180002c09  mov     [rbp+arg_18], edi
0x180002c0c  mov     [rbp+arg_0], edi
0x180002c0f  test    rcx, rcx
0x180002c12  jnz     short loc_180002C1E
0x180002c14  mov     ebx, 80004003h
0x180002c19  jmp     loc_180002CF6
0x180002c1e  test    r14, r14
0x180002c21  jz      short loc_180002C14
0x180002c23  mov     [rdx], rdi
0x180002c26  lea     r9, [rbp+arg_0]
0x180002c2a  mov     rax, [rcx]
0x180002c2d  lea     rdx, [rbp+arg_18]
0x180002c31  mov     r8d, 4
0x180002c37  mov     rax, [rax+18h]
0x180002c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c40  mov     ebx, eax
0x180002c42  test    eax, eax
0x180002c44  js      loc_180002CF6
0x180002c4a  cmp     [rbp+arg_0], 4
0x180002c4e  jz      short loc_180002C5A
0x180002c50  mov     ebx, 80004005h
0x180002c55  jmp     loc_180002CF6
0x180002c5a  cmp     [rbp+arg_18], edi
0x180002c5d  jz      loc_180002CF6
0x180002c63  mov     rax, [rsi]
0x180002c66  lea     r9, [rbp+arg_0]
0x180002c6a  mov     r8d, 4
0x180002c70  mov     [rbp+arg_0], edi
0x180002c73  lea     rdx, [rbp+uBytes]
0x180002c77  mov     rcx, rsi
0x180002c7a  mov     rax, [rax+18h]
0x180002c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c83  mov     ebx, eax
0x180002c85  test    eax, eax
0x180002c87  js      short loc_180002CF6
0x180002c89  cmp     [rbp+arg_0], 4
0x180002c8d  jnz     short loc_180002C50
0x180002c8f  cmp     dword ptr [rbp+uBytes], 2
0x180002c93  ja      short loc_180002C9C
0x180002c95  mov     ebx, 8000FFFFh
0x180002c9a  jmp     short loc_180002CF6
0x180002c9c  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180002c9f  mov     ecx, 40h ; '@'; uFlags
0x180002ca4  call    cs:__imp_LocalAlloc
0x180002caa  mov     rdi, rax
0x180002cad  test    rax, rax
0x180002cb0  jnz     short loc_180002CB9
0x180002cb2  mov     ebx, 8007000Eh
0x180002cb7  jmp     short loc_180002CF6
0x180002cb9  mov     rax, [rsi]
0x180002cbc  lea     r9, [rbp+arg_0]
0x180002cc0  mov     r8d, dword ptr [rbp+uBytes]
0x180002cc4  mov     rdx, rdi
0x180002cc7  mov     rcx, rsi
0x180002cca  mov     rax, [rax+18h]
0x180002cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd3  mov     ebx, eax
0x180002cd5  test    eax, eax
0x180002cd7  js      short loc_180002CF6
0x180002cd9  mov     eax, dword ptr [rbp+uBytes]
0x180002cdc  cmp     eax, [rbp+arg_0]
0x180002cdf  jnz     loc_180002C50
0x180002ce5  mov     ecx, eax
0x180002ce7  xor     eax, eax
0x180002ce9  shr     rcx, 1
0x180002cec  mov     [rdi+rcx*2-2], ax
0x180002cf1  mov     [r14], rdi
0x180002cf4  xor     edi, edi
0x180002cf6  mov     rcx, rdi; hMem
0x180002cf9  call    cs:__imp_LocalFree
0x180002cff  mov     eax, ebx
0x180002d01  add     rsp, 30h
0x180002d05  pop     r14
0x180002d07  pop     rdi
0x180002d08  pop     rsi
0x180002d09  pop     rbx
0x180002d0a  pop     rbp
0x180002d0b  retn
```

# I_CacheHashKeys

- ea: `0x180029768`
- end: `0x180029824`
- name: `I_CacheHashKeys`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800294c0`
- `0x180029578`
- `0x1800296c0`

## callees

- `0x180029768`
- `0x18002982c`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x1800297eb`
- `bcrypt!BCryptDestroyHash` at `0x18002980e`
- `bcrypt!BCryptDestroyHash` at `0x1800297eb`
- `bcrypt!BCryptDestroyHash` at `0x18002980e`
- `bcrypt!BCryptCreateHash` at `0x1800297a5`
- `bcrypt!BCryptCreateHash` at `0x1800297a5`
- `bcrypt!BCryptHashData` at `0x1800297d7`
- `bcrypt!BCryptHashData` at `0x1800297d7`
- `bcrypt!BCryptFinishHash` at `0x1800297fe`
- `bcrypt!BCryptFinishHash` at `0x1800297fe`

## pseudocode

```c
unsigned int __fastcall I_CacheHashKeys(__int64 a1, __int64 a2, UCHAR *a3)
{
  unsigned int v5; // eax
  int v6; // edx
  errcntrctlib *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // ebx
  BCRYPT_HASH_HANDLE hHash; // [rsp+88h] [rbp+20h] BYREF

  hHash = 0;
  v5 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0);
  if ( v5 )
  {
    v7 = (errcntrctlib *)v5;
  }
  else
  {
    v8 = 2;
    while ( v8 )
    {
      --v8;
      v9 = BCryptHashData(hHash, *(PUCHAR *)(a1 + 16LL * v8 + 8), *(_DWORD *)(a1 + 16LL * v8), 0);
      if ( v9 )
      {
        BCryptDestroyHash(hHash);
        v7 = (errcntrctlib *)v9;
        return errcntrctlib::WIN32_FROM_NTSTATUS(v7, v6);
      }
    }
    v10 = BCryptFinishHash(hHash, a3, 0x20u, 0);
    BCryptDestroyHash(hHash);
    v7 = (errcntrctlib *)v10;
  }
  return errcntrctlib::WIN32_FROM_NTSTATUS(v7, v6);
}

```

## disassembly

```asm
0x180029768  mov     rax, rsp
0x18002976b  push    rbx
0x18002976c  push    rbp
0x18002976d  push    rsi
0x18002976e  push    rdi
0x18002976f  sub     rsp, 48h
0x180029773  mov     dword ptr [rax-38h], 0
0x18002977a  lea     rdx, [rax+20h]; phHash
0x18002977e  xor     r9d, r9d; cbHashObject
0x180029781  mov     dword ptr [rax-40h], 0
0x180029788  mov     rbp, r8
0x18002978b  mov     qword ptr [rax+20h], 0
0x180029793  mov     rsi, rcx
0x180029796  mov     qword ptr [rax-48h], 0
0x18002979e  xor     r8d, r8d; pbHashObject
0x1800297a1  lea     ecx, [r9+41h]; hAlgorithm
0x1800297a5  call    cs:__imp_BCryptCreateHash
0x1800297ab  test    eax, eax
0x1800297ad  jz      short loc_1800297B3
0x1800297af  mov     ecx, eax
0x1800297b1  jmp     short loc_180029816
0x1800297b3  mov     ebx, 2
0x1800297b8  mov     rcx, [rsp+68h+hHash]; hHash
0x1800297c0  xor     r9d, r9d; dwFlags
0x1800297c3  test    ebx, ebx
0x1800297c5  jz      short loc_1800297F5
0x1800297c7  dec     ebx
0x1800297c9  mov     edx, ebx
0x1800297cb  add     rdx, rdx
0x1800297ce  mov     r8d, [rsi+rdx*8]; cbInput
0x1800297d2  mov     rdx, [rsi+rdx*8+8]; pbInput
0x1800297d7  call    cs:__imp_BCryptHashData
0x1800297dd  mov     edi, eax
0x1800297df  test    eax, eax
0x1800297e1  jz      short loc_1800297B8
0x1800297e3  mov     rcx, [rsp+68h+hHash]; hHash
0x1800297eb  call    cs:__imp_BCryptDestroyHash
0x1800297f1  mov     ecx, edi
0x1800297f3  jmp     short loc_180029816
0x1800297f5  mov     r8d, 20h ; ' '; cbOutput
0x1800297fb  mov     rdx, rbp; pbOutput
0x1800297fe  call    cs:__imp_BCryptFinishHash
0x180029804  mov     rcx, [rsp+68h+hHash]; hHash
0x18002980c  mov     ebx, eax
0x18002980e  call    cs:__imp_BCryptDestroyHash
0x180029814  mov     ecx, ebx; this
0x180029816  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x18002981b  add     rsp, 48h
0x18002981f  pop     rdi
0x180029820  pop     rsi
0x180029821  pop     rbp
0x180029822  pop     rbx
0x180029823  retn
```

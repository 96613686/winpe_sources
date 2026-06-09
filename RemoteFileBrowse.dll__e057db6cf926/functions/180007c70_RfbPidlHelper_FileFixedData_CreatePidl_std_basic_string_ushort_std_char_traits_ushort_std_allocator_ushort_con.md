# RfbPidlHelper<FileFixedData>::CreatePidl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,FileFixedData const &)

- ea: `0x180007c70`
- end: `0x180007d32`
- name: `?CreatePidl@?$RfbPidlHelper@UFileFixedData@@@@SAPEFBU_ITEMIDLIST@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUFileFixedData@@@Z`
- size: `194`
- prototype: `char *__fastcall(_QWORD *Src, _OWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008d90`
- `0x180013bb0`
- `0x180014570`

## callees

- `0x180002dac`
- `0x180002dc4`
- `0x180007c70`
- `0x180019010`

## import_xrefs

- `SHELL32!SHGetMalloc` at `0x180007c93`
- `SHELL32!SHGetMalloc` at `0x180007c93`

## pseudocode

```c
char *__fastcall RfbPidlHelper<FileFixedData>::CreatePidl(_QWORD *Src, _OWORD *a2)
{
  char *v4; // rbx
  _QWORD *v5; // r14
  __int64 v6; // rbp
  char *v7; // rax
  IMalloc *ppMalloc; // [rsp+70h] [rbp+18h] BYREF

  ppMalloc = 0;
  v4 = 0;
  if ( SHGetMalloc(&ppMalloc) >= 0 )
  {
    v5 = Src + 2;
    v6 = 2LL * Src[2] + 52;
    v7 = (char *)((__int64 (__fastcall *)(IMalloc *, __int64))ppMalloc->lpVtbl->Alloc)(ppMalloc, 2LL * Src[2] + 55);
    v4 = v7;
    if ( v7 )
    {
      memset_0(v7, 0, v6 + 3);
      *(_WORD *)v4 = v6;
      *(_OWORD *)(v4 + 2) = *a2;
      *(_OWORD *)(v4 + 18) = a2[1];
      *(_OWORD *)(v4 + 34) = a2[2];
      if ( Src[3] > 7u )
        Src = (_QWORD *)*Src;
      memcpy_0(v4 + 50, Src, 2LL * *v5);
    }
    ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  return v4;
}

```

## disassembly

```asm
0x180007c70  push    rbx
0x180007c72  push    rbp
0x180007c73  push    rsi
0x180007c74  push    rdi
0x180007c75  push    r14
0x180007c77  push    r15
0x180007c79  sub     rsp, 28h
0x180007c7d  mov     rdi, rcx
0x180007c80  mov     [rsp+58h+ppMalloc], 0
0x180007c89  lea     rcx, [rsp+58h+ppMalloc]; ppMalloc
0x180007c8e  mov     rsi, rdx
0x180007c91  xor     ebx, ebx
0x180007c93  call    cs:__imp_SHGetMalloc
0x180007c99  test    eax, eax
0x180007c9b  js      loc_180007D22
0x180007ca1  mov     rcx, [rsp+58h+ppMalloc]
0x180007ca6  lea     r14, [rdi+10h]
0x180007caa  mov     rax, [r14]
0x180007cad  lea     rbp, ds:34h[rax*2]
0x180007cb5  mov     rax, [rcx]
0x180007cb8  lea     rdx, [rbp+3]
0x180007cbc  mov     rax, [rax+18h]
0x180007cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc5  mov     rbx, rax
0x180007cc8  test    rax, rax
0x180007ccb  jz      short loc_180007D11
0x180007ccd  lea     r8, [rbp+3]; Size
0x180007cd1  xor     edx, edx; Val
0x180007cd3  mov     rcx, rax; void *
0x180007cd6  call    memset_0
0x180007cdb  mov     [rbx], bp
0x180007cde  movups  xmm0, xmmword ptr [rsi]
0x180007ce1  movups  xmmword ptr [rbx+2], xmm0
0x180007ce5  movups  xmm1, xmmword ptr [rsi+10h]
0x180007ce9  movups  xmmword ptr [rbx+12h], xmm1
0x180007ced  movups  xmm0, xmmword ptr [rsi+20h]
0x180007cf1  movups  xmmword ptr [rbx+22h], xmm0
0x180007cf5  cmp     qword ptr [rdi+18h], 7
0x180007cfa  jbe     short loc_180007CFF
0x180007cfc  mov     rdi, [rdi]
0x180007cff  mov     r8, [r14]
0x180007d02  lea     rcx, [rbx+32h]; void *
0x180007d06  add     r8, r8; Size
0x180007d09  mov     rdx, rdi; Src
0x180007d0c  call    memcpy_0
0x180007d11  mov     rcx, [rsp+58h+ppMalloc]
0x180007d16  mov     rdx, [rcx]
0x180007d19  mov     rax, [rdx+10h]
0x180007d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d22  mov     rax, rbx
0x180007d25  add     rsp, 28h
0x180007d29  pop     r15
0x180007d2b  pop     r14
0x180007d2d  pop     rdi
0x180007d2e  pop     rsi
0x180007d2f  pop     rbp
0x180007d30  pop     rbx
0x180007d31  retn
```

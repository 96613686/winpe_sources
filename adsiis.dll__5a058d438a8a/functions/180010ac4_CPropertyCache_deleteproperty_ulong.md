# CPropertyCache::deleteproperty(ulong)

- ea: `0x180010ac4`
- end: `0x180010bf2`
- name: `?deleteproperty@CPropertyCache@@QEAAJK@Z`
- size: `302`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007940`

## callees

- `0x180010ac4`
- `0x180010e8c`
- `0x1800184ac`
- `0x18001d652`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180010b50`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180010b50`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180010b24`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180010bce`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180010b24`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180010bce`

## pseudocode

```c
__int64 __fastcall CPropertyCache::deleteproperty(const void **this, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned int v4; // r14d
  char *v5; // rbp
  __int64 v6; // rdi
  struct _iistype *v7; // rcx
  __int64 result; // rax
  char *v9; // rax
  char *v10; // r15
  int v11; // ecx
  struct _iistype *v12; // rcx

  v2 = a2;
  if ( !(unsigned int)CPropertyCache::index_valid((CPropertyCache *)this, a2) )
    return (unsigned int)-2147467259;
  v5 = (char *)this[4];
  v6 = 544 * v2;
  if ( *((_DWORD *)this + 2) != 1 )
  {
    v9 = (char *)AllocADsMem(*((_DWORD *)this + 11) - 544);
    v10 = v9;
    if ( v9 )
    {
      v4 = 0;
      if ( (_DWORD)v2 )
        memcpy_0(v9, this[4], 544 * v2);
      v11 = *((_DWORD *)this + 2);
      if ( (_DWORD)v2 != v11 - 1 )
        memcpy_0(&v10[v6], (char *)this[4] + v6 + 544, 544LL * (unsigned int)(v11 + ~(_DWORD)v2));
      v12 = *(struct _iistype **)&v5[v6 + 536];
      if ( v12 )
      {
        IISTypeFreeIISObjects(v12, *(_DWORD *)&v5[v6 + 524]);
        *(_QWORD *)&v5[v6 + 536] = 0;
      }
      FreeADsMem((LPVOID)this[4]);
      --*((_DWORD *)this + 2);
      *((_DWORD *)this + 11) -= 544;
      this[4] = v10;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return v4;
  }
  v7 = *(struct _iistype **)&v5[v6 + 536];
  if ( v7 )
  {
    IISTypeFreeIISObjects(v7, *(_DWORD *)&v5[v6 + 524]);
    *(_QWORD *)&v5[v6 + 536] = 0;
  }
  FreeADsMem((LPVOID)this[4]);
  result = 0;
  this[4] = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 11) = 0;
  return result;
}

```

## disassembly

```asm
0x180010ac4  push    rbx
0x180010ac6  push    rbp
0x180010ac7  push    rsi
0x180010ac8  push    rdi
0x180010ac9  push    r14
0x180010acb  push    r15
0x180010acd  sub     rsp, 28h
0x180010ad1  mov     esi, edx
0x180010ad3  mov     rbx, rcx
0x180010ad6  call    ?index_valid@CPropertyCache@@QEAAHK@Z; CPropertyCache::index_valid(ulong)
0x180010adb  test    eax, eax
0x180010add  jnz     short loc_180010AEA
0x180010adf  mov     r14d, 80004005h
0x180010ae5  jmp     loc_180010BE2
0x180010aea  mov     rbp, [rbx+20h]
0x180010aee  imul    rdi, rsi, 220h
0x180010af5  cmp     dword ptr [rbx+8], 1
0x180010af9  jnz     short loc_180010B47
0x180010afb  mov     rcx, [rdi+rbp+218h]; struct _iistype *
0x180010b03  test    rcx, rcx
0x180010b06  jz      short loc_180010B20
0x180010b08  mov     edx, [rdi+rbp+20Ch]; unsigned int
0x180010b0f  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180010b14  mov     qword ptr [rdi+rbp+218h], 0
0x180010b20  mov     rcx, [rbx+20h]; pMem
0x180010b24  call    cs:__imp_FreeADsMem
0x180010b2a  xor     eax, eax
0x180010b2c  mov     qword ptr [rbx+20h], 0
0x180010b34  mov     dword ptr [rbx+8], 0
0x180010b3b  mov     dword ptr [rbx+2Ch], 0
0x180010b42  jmp     loc_180010BE5
0x180010b47  mov     ecx, [rbx+2Ch]
0x180010b4a  sub     ecx, 220h; cb
0x180010b50  call    cs:__imp_AllocADsMem
0x180010b56  mov     r15, rax
0x180010b59  test    rax, rax
0x180010b5c  jnz     short loc_180010B66
0x180010b5e  mov     r14d, 8007000Eh
0x180010b64  jmp     short loc_180010BE2
0x180010b66  xor     r14d, r14d
0x180010b69  test    esi, esi
0x180010b6b  jz      short loc_180010B7C
0x180010b6d  mov     rdx, [rbx+20h]; Src
0x180010b71  mov     r8, rdi; Size
0x180010b74  mov     rcx, r15; void *
0x180010b77  call    memcpy_0
0x180010b7c  mov     ecx, [rbx+8]
0x180010b7f  lea     eax, [rcx-1]
0x180010b82  cmp     esi, eax
0x180010b84  jz      short loc_180010BA9
0x180010b86  mov     rdx, [rbx+20h]
0x180010b8a  not     esi
0x180010b8c  add     rdx, 220h
0x180010b93  add     rdx, rdi; Src
0x180010b96  lea     eax, [rcx+rsi]
0x180010b99  imul    r8, rax, 220h; Size
0x180010ba0  lea     rcx, [rdi+r15]; void *
0x180010ba4  call    memcpy_0
0x180010ba9  mov     rcx, [rdi+rbp+218h]; struct _iistype *
0x180010bb1  test    rcx, rcx
0x180010bb4  jz      short loc_180010BCA
0x180010bb6  mov     edx, [rdi+rbp+20Ch]; unsigned int
0x180010bbd  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180010bc2  mov     [rdi+rbp+218h], r14
0x180010bca  mov     rcx, [rbx+20h]; pMem
0x180010bce  call    cs:__imp_FreeADsMem
0x180010bd4  dec     dword ptr [rbx+8]
0x180010bd7  add     dword ptr [rbx+2Ch], 0FFFFFDE0h
0x180010bde  mov     [rbx+20h], r15
0x180010be2  mov     eax, r14d
0x180010be5  add     rsp, 28h
0x180010be9  pop     r15
0x180010beb  pop     r14
0x180010bed  pop     rdi
0x180010bee  pop     rsi
0x180010bef  pop     rbp
0x180010bf0  pop     rbx
0x180010bf1  retn
```

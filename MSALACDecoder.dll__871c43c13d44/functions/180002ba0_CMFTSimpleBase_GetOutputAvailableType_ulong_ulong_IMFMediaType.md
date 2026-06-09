# CMFTSimpleBase::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x180002ba0`
- end: `0x180002c88`
- name: `?GetOutputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ba0`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180002c3f`
- `MFPlat!MFCreateMediaType` at `0x180002c3f`

## pseudocode

```c
__int64 __fastcall CMFTSimpleBase::GetOutputAvailableType(
        CMFTSimpleBase *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  HRESULT v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // ecx
  int v11; // edx
  __int64 v12; // r14
  __int64 v14; // rcx

  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    v8 = -1072875853;
    goto LABEL_14;
  }
  if ( !*((_DWORD *)this + 36) && !*((_QWORD *)this + 5) )
  {
    v8 = -1072861856;
    goto LABEL_14;
  }
  v9 = *((_DWORD *)this + 6);
  if ( !v9 )
  {
    v8 = -2147467263;
    goto LABEL_14;
  }
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v12 = 2LL * v10;
    if ( *(_DWORD *)(*((_QWORD *)this + 4) + 16LL * v10 + 8) )
      break;
LABEL_12:
    if ( ++v10 >= v9 )
    {
      v8 = -1072875847;
      goto LABEL_14;
    }
  }
  if ( v11 != a3 )
  {
    ++v11;
    goto LABEL_12;
  }
  v8 = MFCreateMediaType(a4);
  if ( v8 >= 0 )
  {
    v14 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v12);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 256LL))(v14, *a4);
    if ( v8 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_14:
  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002ba0  push    rbx
0x180002ba2  push    rbp
0x180002ba3  push    rsi
0x180002ba4  push    rdi
0x180002ba5  push    r14
0x180002ba7  sub     rsp, 20h
0x180002bab  mov     rsi, r9
0x180002bae  mov     ebp, r8d
0x180002bb1  mov     ebx, edx
0x180002bb3  mov     rdi, rcx
0x180002bb6  mov     rax, [rcx]
0x180002bb9  mov     rax, [rax+0D0h]
0x180002bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc5  test    ebx, ebx
0x180002bc7  jz      short loc_180002BD0
0x180002bc9  mov     ebx, 0C00D36B3h
0x180002bce  jmp     short loc_180002C1C
0x180002bd0  cmp     dword ptr [rdi+90h], 0
0x180002bd7  jnz     short loc_180002BE7
0x180002bd9  cmp     qword ptr [rdi+28h], 0
0x180002bde  jnz     short loc_180002BE7
0x180002be0  mov     ebx, 0C00D6D60h
0x180002be5  jmp     short loc_180002C1C
0x180002be7  mov     eax, [rdi+18h]
0x180002bea  test    eax, eax
0x180002bec  jnz     short loc_180002BF5
0x180002bee  mov     ebx, 80004001h
0x180002bf3  jmp     short loc_180002C1C
0x180002bf5  xor     ecx, ecx
0x180002bf7  xor     edx, edx
0x180002bf9  mov     r8, [rdi+20h]
0x180002bfd  mov     r14d, ecx
0x180002c00  add     r14, r14
0x180002c03  cmp     dword ptr [r8+r14*8+8], 0
0x180002c09  jz      short loc_180002C11
0x180002c0b  cmp     edx, ebp
0x180002c0d  jz      short loc_180002C3C
0x180002c0f  inc     edx
0x180002c11  inc     ecx
0x180002c13  cmp     ecx, eax
0x180002c15  jb      short loc_180002BFD
0x180002c17  mov     ebx, 0C00D36B9h
0x180002c1c  mov     rax, [rdi]
0x180002c1f  mov     rcx, rdi
0x180002c22  mov     rax, [rax+0D8h]
0x180002c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2e  nop
0x180002c2f  mov     eax, ebx
0x180002c31  add     rsp, 20h
0x180002c35  pop     r14
0x180002c37  pop     rdi
0x180002c38  pop     rsi
0x180002c39  pop     rbp
0x180002c3a  pop     rbx
0x180002c3b  retn
0x180002c3c  mov     rcx, rsi; ppMFType
0x180002c3f  call    cs:__imp_MFCreateMediaType
0x180002c45  mov     ebx, eax
0x180002c47  test    eax, eax
0x180002c49  js      short loc_180002C1C
0x180002c4b  mov     rax, [rdi+20h]
0x180002c4f  mov     rcx, [rax+r14*8]
0x180002c53  mov     rax, [rcx]
0x180002c56  mov     rdx, [rsi]
0x180002c59  mov     rax, [rax+100h]
0x180002c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c65  mov     ebx, eax
0x180002c67  test    eax, eax
0x180002c69  jns     short loc_180002C1C
0x180002c6b  mov     rcx, [rsi]
0x180002c6e  test    rcx, rcx
0x180002c71  jz      short loc_180002C1C
0x180002c73  mov     rax, [rcx]
0x180002c76  mov     rax, [rax+10h]
0x180002c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7f  mov     qword ptr [rsi], 0
0x180002c86  jmp     short loc_180002C1C
```

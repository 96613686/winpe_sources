# CMFTSimpleBase::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x18001c740`
- end: `0x18001c828`
- name: `?GetOutputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c740`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001c7df`
- `MFPlat!MFCreateMediaType` at `0x18001c7df`

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
0x18001c740  push    rbx
0x18001c742  push    rbp
0x18001c743  push    rsi
0x18001c744  push    rdi
0x18001c745  push    r14
0x18001c747  sub     rsp, 20h
0x18001c74b  mov     rsi, r9
0x18001c74e  mov     ebp, r8d
0x18001c751  mov     ebx, edx
0x18001c753  mov     rdi, rcx
0x18001c756  mov     rax, [rcx]
0x18001c759  mov     rax, [rax+0D0h]
0x18001c760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c765  test    ebx, ebx
0x18001c767  jz      short loc_18001C770
0x18001c769  mov     ebx, 0C00D36B3h
0x18001c76e  jmp     short loc_18001C7BC
0x18001c770  cmp     dword ptr [rdi+90h], 0
0x18001c777  jnz     short loc_18001C787
0x18001c779  cmp     qword ptr [rdi+28h], 0
0x18001c77e  jnz     short loc_18001C787
0x18001c780  mov     ebx, 0C00D6D60h
0x18001c785  jmp     short loc_18001C7BC
0x18001c787  mov     eax, [rdi+18h]
0x18001c78a  test    eax, eax
0x18001c78c  jnz     short loc_18001C795
0x18001c78e  mov     ebx, 80004001h
0x18001c793  jmp     short loc_18001C7BC
0x18001c795  xor     ecx, ecx
0x18001c797  xor     edx, edx
0x18001c799  mov     r8, [rdi+20h]
0x18001c79d  mov     r14d, ecx
0x18001c7a0  add     r14, r14
0x18001c7a3  cmp     dword ptr [r8+r14*8+8], 0
0x18001c7a9  jz      short loc_18001C7B1
0x18001c7ab  cmp     edx, ebp
0x18001c7ad  jz      short loc_18001C7DC
0x18001c7af  inc     edx
0x18001c7b1  inc     ecx
0x18001c7b3  cmp     ecx, eax
0x18001c7b5  jb      short loc_18001C79D
0x18001c7b7  mov     ebx, 0C00D36B9h
0x18001c7bc  mov     rax, [rdi]
0x18001c7bf  mov     rcx, rdi
0x18001c7c2  mov     rax, [rax+0D8h]
0x18001c7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7ce  nop
0x18001c7cf  mov     eax, ebx
0x18001c7d1  add     rsp, 20h
0x18001c7d5  pop     r14
0x18001c7d7  pop     rdi
0x18001c7d8  pop     rsi
0x18001c7d9  pop     rbp
0x18001c7da  pop     rbx
0x18001c7db  retn
0x18001c7dc  mov     rcx, rsi; ppMFType
0x18001c7df  call    cs:__imp_MFCreateMediaType
0x18001c7e5  mov     ebx, eax
0x18001c7e7  test    eax, eax
0x18001c7e9  js      short loc_18001C7BC
0x18001c7eb  mov     rax, [rdi+20h]
0x18001c7ef  mov     rcx, [rax+r14*8]
0x18001c7f3  mov     rax, [rcx]
0x18001c7f6  mov     rdx, [rsi]
0x18001c7f9  mov     rax, [rax+100h]
0x18001c800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c805  mov     ebx, eax
0x18001c807  test    eax, eax
0x18001c809  jns     short loc_18001C7BC
0x18001c80b  mov     rcx, [rsi]
0x18001c80e  test    rcx, rcx
0x18001c811  jz      short loc_18001C7BC
0x18001c813  mov     rax, [rcx]
0x18001c816  mov     rax, [rax+10h]
0x18001c81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c81f  mov     qword ptr [rsi], 0
0x18001c826  jmp     short loc_18001C7BC
```

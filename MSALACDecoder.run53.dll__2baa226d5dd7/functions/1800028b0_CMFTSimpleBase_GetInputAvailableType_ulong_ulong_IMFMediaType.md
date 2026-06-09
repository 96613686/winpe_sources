# CMFTSimpleBase::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800028b0`
- end: `0x180002998`
- name: `?GetInputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800028b0`
- `0x18000b010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18000294f`
- `MFPlat!MFCreateMediaType` at `0x18000294f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFTSimpleBase::GetInputAvailableType(
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
  if ( *((_DWORD *)this + 36) == 1 && !*((_QWORD *)this + 10) )
  {
    v8 = -1072861856;
    goto LABEL_14;
  }
  v9 = *((_DWORD *)this + 2);
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
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 16LL * v10 + 8) )
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
    v14 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v12);
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
0x1800028b0  push    rbx
0x1800028b2  push    rbp
0x1800028b3  push    rsi
0x1800028b4  push    rdi
0x1800028b5  push    r14
0x1800028b7  sub     rsp, 20h
0x1800028bb  mov     rsi, r9
0x1800028be  mov     ebp, r8d
0x1800028c1  mov     ebx, edx
0x1800028c3  mov     rdi, rcx
0x1800028c6  mov     rax, [rcx]
0x1800028c9  mov     rax, [rax+0D0h]
0x1800028d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d5  test    ebx, ebx
0x1800028d7  jz      short loc_1800028E0
0x1800028d9  mov     ebx, 0C00D36B3h
0x1800028de  jmp     short loc_18000292C
0x1800028e0  cmp     dword ptr [rdi+90h], 1
0x1800028e7  jnz     short loc_1800028F7
0x1800028e9  cmp     qword ptr [rdi+50h], 0
0x1800028ee  jnz     short loc_1800028F7
0x1800028f0  mov     ebx, 0C00D6D60h
0x1800028f5  jmp     short loc_18000292C
0x1800028f7  mov     eax, [rdi+8]
0x1800028fa  test    eax, eax
0x1800028fc  jnz     short loc_180002905
0x1800028fe  mov     ebx, 80004001h
0x180002903  jmp     short loc_18000292C
0x180002905  xor     ecx, ecx
0x180002907  xor     edx, edx
0x180002909  mov     r8, [rdi+10h]
0x18000290d  mov     r14d, ecx
0x180002910  add     r14, r14
0x180002913  cmp     dword ptr [r8+r14*8+8], 0
0x180002919  jz      short loc_180002921
0x18000291b  cmp     edx, ebp
0x18000291d  jz      short loc_18000294C
0x18000291f  inc     edx
0x180002921  inc     ecx
0x180002923  cmp     ecx, eax
0x180002925  jb      short loc_18000290D
0x180002927  mov     ebx, 0C00D36B9h
0x18000292c  mov     rax, [rdi]
0x18000292f  mov     rcx, rdi
0x180002932  mov     rax, [rax+0D8h]
0x180002939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293e  nop
0x18000293f  mov     eax, ebx
0x180002941  add     rsp, 20h
0x180002945  pop     r14
0x180002947  pop     rdi
0x180002948  pop     rsi
0x180002949  pop     rbp
0x18000294a  pop     rbx
0x18000294b  retn
0x18000294c  mov     rcx, rsi; ppMFType
0x18000294f  call    cs:__imp_MFCreateMediaType
0x180002955  mov     ebx, eax
0x180002957  test    eax, eax
0x180002959  js      short loc_18000292C
0x18000295b  mov     rax, [rdi+10h]
0x18000295f  mov     rcx, [rax+r14*8]
0x180002963  mov     rax, [rcx]
0x180002966  mov     rdx, [rsi]
0x180002969  mov     rax, [rax+100h]
0x180002970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002975  mov     ebx, eax
0x180002977  test    eax, eax
0x180002979  jns     short loc_18000292C
0x18000297b  mov     rcx, [rsi]
0x18000297e  test    rcx, rcx
0x180002981  jz      short loc_18000292C
0x180002983  mov     rax, [rcx]
0x180002986  mov     rax, [rax+10h]
0x18000298a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298f  mov     qword ptr [rsi], 0
0x180002996  jmp     short loc_18000292C
```

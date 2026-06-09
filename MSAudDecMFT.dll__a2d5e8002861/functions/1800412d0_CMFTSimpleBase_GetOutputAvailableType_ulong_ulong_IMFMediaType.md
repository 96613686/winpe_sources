# CMFTSimpleBase::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800412d0`
- end: `0x1800413e6`
- name: `?GetOutputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `278`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800412d0`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18004133e`
- `MFPlat!MFCreateMediaType` at `0x18004133e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFTSimpleBase::GetOutputAvailableType(
        CMFTSimpleBase *this,
        int a2,
        int a3,
        struct IMFMediaType **a4)
{
  int v8; // edx
  unsigned int i; // ecx
  __int64 v10; // r14
  HRESULT v11; // ebx
  __int64 v12; // rcx

  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 208LL))(this);
  if ( a2 )
  {
    v11 = -1072875853;
    goto LABEL_10;
  }
  if ( !*((_DWORD *)this + 36) && !*((_QWORD *)this + 5) )
  {
    v11 = -1072861856;
    goto LABEL_10;
  }
  if ( !*((_DWORD *)this + 6) )
  {
    v11 = -2147467263;
    goto LABEL_10;
  }
  v8 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 6) )
    {
      v11 = -1072875847;
      goto LABEL_10;
    }
    v10 = 2LL * i;
    if ( *(_DWORD *)(*((_QWORD *)this + 4) + 16LL * i + 8) )
      break;
LABEL_11:
    ;
  }
  if ( v8 != a3 )
  {
    ++v8;
    goto LABEL_11;
  }
  v11 = MFCreateMediaType(a4);
  if ( v11 >= 0 )
  {
    _mm_lfence();
    v12 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v10);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 256LL))(v12, *a4);
    if ( v11 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_10:
  (*(void (__fastcall **)(CMFTSimpleBase *))(*(_QWORD *)this + 216LL))(this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800412d0  push    rbx
0x1800412d2  push    rbp
0x1800412d3  push    rsi
0x1800412d4  push    rdi
0x1800412d5  push    r14
0x1800412d7  sub     rsp, 20h
0x1800412db  mov     rsi, r9
0x1800412de  mov     ebp, r8d
0x1800412e1  mov     ebx, edx
0x1800412e3  mov     rdi, rcx
0x1800412e6  mov     rax, [rcx]
0x1800412e9  mov     rax, [rax+0D0h]
0x1800412f0  call    cs:__guard_dispatch_icall_fptr
0x1800412f6  test    ebx, ebx
0x1800412f8  jnz     loc_18004139D
0x1800412fe  cmp     [rdi+90h], ebx
0x180041304  jz      loc_1800413AB
0x18004130a  cmp     dword ptr [rdi+18h], 0
0x18004130e  jz      loc_1800413BD
0x180041314  xor     edx, edx
0x180041316  xor     ecx, ecx
0x180041318  cmp     ecx, [rdi+18h]
0x18004131b  jnb     loc_1800413A4
0x180041321  mov     r14d, ecx
0x180041324  add     r14, r14
0x180041327  mov     rax, [rdi+20h]
0x18004132b  cmp     dword ptr [rax+r14*8+8], 0
0x180041331  jz      short loc_180041396
0x180041333  cmp     edx, ebp
0x180041335  jnz     loc_1800413C4
0x18004133b  mov     rcx, rsi; ppMFType
0x18004133e  call    cs:__imp_MFCreateMediaType
0x180041345  nop     dword ptr [rax+rax+00h]
0x18004134a  mov     ebx, eax
0x18004134c  test    eax, eax
0x18004134e  js      short loc_180041374
0x180041350  lfence
0x180041353  mov     rax, [rdi+20h]
0x180041357  mov     rcx, [rax+r14*8]
0x18004135b  mov     rax, [rcx]
0x18004135e  mov     rdx, [rsi]
0x180041361  mov     rax, [rax+100h]
0x180041368  call    cs:__guard_dispatch_icall_fptr
0x18004136e  mov     ebx, eax
0x180041370  test    eax, eax
0x180041372  js      short loc_1800413C8
0x180041374  mov     rax, [rdi]
0x180041377  mov     rcx, rdi
0x18004137a  mov     rax, [rax+0D8h]
0x180041381  call    cs:__guard_dispatch_icall_fptr
0x180041387  nop
0x180041388  mov     eax, ebx
0x18004138a  add     rsp, 20h
0x18004138e  pop     r14
0x180041390  pop     rdi
0x180041391  pop     rsi
0x180041392  pop     rbp
0x180041393  pop     rbx
0x180041394  retn
0x180041396  inc     ecx
0x180041398  jmp     loc_180041318
0x18004139d  mov     ebx, 0C00D36B3h
0x1800413a2  jmp     short loc_180041374
0x1800413a4  mov     ebx, 0C00D36B9h
0x1800413a9  jmp     short loc_180041374
0x1800413ab  cmp     qword ptr [rdi+28h], 0
0x1800413b0  jnz     loc_18004130A
0x1800413b6  mov     ebx, 0C00D6D60h
0x1800413bb  jmp     short loc_180041374
0x1800413bd  mov     ebx, 80004001h
0x1800413c2  jmp     short loc_180041374
0x1800413c4  inc     edx
0x1800413c6  jmp     short loc_180041396
0x1800413c8  mov     rcx, [rsi]
0x1800413cb  test    rcx, rcx
0x1800413ce  jz      short loc_180041374
0x1800413d0  mov     rax, [rcx]
0x1800413d3  mov     rax, [rax+10h]
0x1800413d7  call    cs:__guard_dispatch_icall_fptr
0x1800413dd  mov     qword ptr [rsi], 0
0x1800413e4  jmp     short loc_180041374
```

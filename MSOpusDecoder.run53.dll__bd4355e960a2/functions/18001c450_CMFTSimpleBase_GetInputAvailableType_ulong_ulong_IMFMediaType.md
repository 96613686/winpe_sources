# CMFTSimpleBase::GetInputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x18001c450`
- end: `0x18001c538`
- name: `?GetInputAvailableType@CMFTSimpleBase@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `232`
- prototype: `int(CMFTSimpleBase *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c450`
- `0x180024010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001c4ef`
- `MFPlat!MFCreateMediaType` at `0x18001c4ef`

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
0x18001c450  push    rbx
0x18001c452  push    rbp
0x18001c453  push    rsi
0x18001c454  push    rdi
0x18001c455  push    r14
0x18001c457  sub     rsp, 20h
0x18001c45b  mov     rsi, r9
0x18001c45e  mov     ebp, r8d
0x18001c461  mov     ebx, edx
0x18001c463  mov     rdi, rcx
0x18001c466  mov     rax, [rcx]
0x18001c469  mov     rax, [rax+0D0h]
0x18001c470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c475  test    ebx, ebx
0x18001c477  jz      short loc_18001C480
0x18001c479  mov     ebx, 0C00D36B3h
0x18001c47e  jmp     short loc_18001C4CC
0x18001c480  cmp     dword ptr [rdi+90h], 1
0x18001c487  jnz     short loc_18001C497
0x18001c489  cmp     qword ptr [rdi+50h], 0
0x18001c48e  jnz     short loc_18001C497
0x18001c490  mov     ebx, 0C00D6D60h
0x18001c495  jmp     short loc_18001C4CC
0x18001c497  mov     eax, [rdi+8]
0x18001c49a  test    eax, eax
0x18001c49c  jnz     short loc_18001C4A5
0x18001c49e  mov     ebx, 80004001h
0x18001c4a3  jmp     short loc_18001C4CC
0x18001c4a5  xor     ecx, ecx
0x18001c4a7  xor     edx, edx
0x18001c4a9  mov     r8, [rdi+10h]
0x18001c4ad  mov     r14d, ecx
0x18001c4b0  add     r14, r14
0x18001c4b3  cmp     dword ptr [r8+r14*8+8], 0
0x18001c4b9  jz      short loc_18001C4C1
0x18001c4bb  cmp     edx, ebp
0x18001c4bd  jz      short loc_18001C4EC
0x18001c4bf  inc     edx
0x18001c4c1  inc     ecx
0x18001c4c3  cmp     ecx, eax
0x18001c4c5  jb      short loc_18001C4AD
0x18001c4c7  mov     ebx, 0C00D36B9h
0x18001c4cc  mov     rax, [rdi]
0x18001c4cf  mov     rcx, rdi
0x18001c4d2  mov     rax, [rax+0D8h]
0x18001c4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4de  nop
0x18001c4df  mov     eax, ebx
0x18001c4e1  add     rsp, 20h
0x18001c4e5  pop     r14
0x18001c4e7  pop     rdi
0x18001c4e8  pop     rsi
0x18001c4e9  pop     rbp
0x18001c4ea  pop     rbx
0x18001c4eb  retn
0x18001c4ec  mov     rcx, rsi; ppMFType
0x18001c4ef  call    cs:__imp_MFCreateMediaType
0x18001c4f5  mov     ebx, eax
0x18001c4f7  test    eax, eax
0x18001c4f9  js      short loc_18001C4CC
0x18001c4fb  mov     rax, [rdi+10h]
0x18001c4ff  mov     rcx, [rax+r14*8]
0x18001c503  mov     rax, [rcx]
0x18001c506  mov     rdx, [rsi]
0x18001c509  mov     rax, [rax+100h]
0x18001c510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c515  mov     ebx, eax
0x18001c517  test    eax, eax
0x18001c519  jns     short loc_18001C4CC
0x18001c51b  mov     rcx, [rsi]
0x18001c51e  test    rcx, rcx
0x18001c521  jz      short loc_18001C4CC
0x18001c523  mov     rax, [rcx]
0x18001c526  mov     rax, [rax+10h]
0x18001c52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c52f  mov     qword ptr [rsi], 0
0x18001c536  jmp     short loc_18001C4CC
```

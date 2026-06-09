# CLstBxWinHost::SetTopViewableItem(long)

- ea: `0x18006baec`
- end: `0x18006bc86`
- name: `?SetTopViewableItem@CLstBxWinHost@@IEAAHJ@Z`
- size: `410`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180067fbc`
- `0x180069850`
- `0x1800699dc`

## callees

- `0x180067178`
- `0x18006b380`
- `0x18006b51c`
- `0x18006baec`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18006bc5d`
- `USER32!UpdateWindow` at `0x18006bc5d`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::SetTopViewableItem(CLstBxWinHost *this, int a2)
{
  int v2; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  CLstBxWinHost *v8; // rcx
  int v9; // r8d
  int v10; // r14d
  int v11; // edx
  unsigned int v12; // ebx
  CLstBxWinHost *v13; // rcx
  int v14; // r8d
  unsigned int v15; // ebx
  void (__fastcall *v16)(CLstBxWinHost *, __int128 *); // rax
  void (__fastcall *v17)(CLstBxWinHost *, _QWORD, _QWORD, _QWORD, __int128 *, _QWORD, _QWORD, int); // rax
  __int128 v18; // [rsp+50h] [rbp-38h] BYREF

  v2 = *((_DWORD *)this + 48);
  if ( v2 )
  {
    if ( a2 >= v2 )
      return 0;
    v6 = *((_DWORD *)this + 32);
    if ( (v6 & 1) != 0 )
    {
      v15 = *((_DWORD *)this + 46) * (*((_DWORD *)this + 31) - a2);
      v16 = *(void (__fastcall **)(CLstBxWinHost *, __int128 *))(*(_QWORD *)this + 192LL);
      v18 = 0;
      v16(this, &v18);
      v17 = *(void (__fastcall **)(CLstBxWinHost *, _QWORD, _QWORD, _QWORD, __int128 *, _QWORD, _QWORD, int))(*(_QWORD *)this + 128LL);
      *((_DWORD *)this + 31) = a2;
      v17(this, 0, v15, 0, &v18, 0, 0, 7);
      (*(void (__fastcall **)(CLstBxWinHost *, __int64, __int64))(*(_QWORD *)this + 416LL))(this, 1, 1);
      UpdateWindow(*((HWND *)this + 2));
      return 1;
    }
    v7 = v6 >> 7;
    *((_DWORD *)this + 32) = v6 & 0xFFFFFF7F;
    if ( (v6 & 0x80) != 0 && (unsigned int)CLstBxWinHost::IsItemViewable(this, *((_DWORD *)this + 50)) )
      CLstBxWinHost::SetCursor(v8, 0, v9, 1);
    v10 = *((_DWORD *)this + 31);
    *((_DWORD *)this + 31) = a2;
    if ( !CLstBxWinHost::ScrollToView(this, a2) )
    {
      if ( *((int *)this + 52) >= 0 )
        return 1;
      *((_DWORD *)this + 31) = v10;
    }
    v11 = *((_DWORD *)this + 50);
    v12 = *((_DWORD *)this + 32) ^ ((unsigned __int8)*((_DWORD *)this + 32) ^ (unsigned __int8)((_BYTE)v7 << 7)) & 0x80;
    *((_DWORD *)this + 32) = v12;
    if ( ((unsigned __int8)(v12 >> 7) & (unsigned __int8)CLstBxWinHost::IsItemViewable(this, v11) & 1) != 0 )
      CLstBxWinHost::SetCursor(v13, 0, v14, 0);
    return 1;
  }
  *((_DWORD *)this + 31) = 0;
  return 1;
}

```

## disassembly

```asm
0x18006baec  mov     [rsp+arg_10], rbx
0x18006baf1  push    rbp
0x18006baf2  push    rdi
0x18006baf3  push    r14
0x18006baf5  sub     rsp, 70h
0x18006baf9  mov     rax, cs:__security_cookie
0x18006bb00  xor     rax, rsp
0x18006bb03  mov     [rsp+88h+var_28], rax
0x18006bb08  mov     eax, [rcx+0C0h]
0x18006bb0e  mov     ebp, edx
0x18006bb10  mov     rdi, rcx
0x18006bb13  test    eax, eax
0x18006bb15  jnz     short loc_18006BB1F
0x18006bb17  mov     [rcx+7Ch], eax
0x18006bb1a  jmp     loc_18006BC63
0x18006bb1f  cmp     ebp, eax
0x18006bb21  jl      short loc_18006BB2A
0x18006bb23  xor     eax, eax
0x18006bb25  jmp     loc_18006BC68
0x18006bb2a  mov     eax, [rcx+80h]
0x18006bb30  test    al, 1
0x18006bb32  jnz     loc_18006BBD6
0x18006bb38  mov     ebx, eax
0x18006bb3a  btr     eax, 7
0x18006bb3e  shr     ebx, 7
0x18006bb41  mov     [rcx+80h], eax
0x18006bb47  test    bl, 1
0x18006bb4a  jz      short loc_18006BB6A
0x18006bb4c  mov     r8d, [rcx+0C8h]
0x18006bb53  mov     edx, r8d; int
0x18006bb56  call    ?IsItemViewable@CLstBxWinHost@@QEBAHJ@Z; CLstBxWinHost::IsItemViewable(long)
0x18006bb5b  test    eax, eax
0x18006bb5d  jz      short loc_18006BB6A
0x18006bb5f  xor     edx, edx; HDC
0x18006bb61  lea     r9d, [rdx+1]; int
0x18006bb65  call    ?SetCursor@CLstBxWinHost@@QEAAXPEAUHDC__@@HH@Z; CLstBxWinHost::SetCursor(HDC__ *,int,int)
0x18006bb6a  mov     r14d, [rdi+7Ch]
0x18006bb6e  mov     edx, ebp; int
0x18006bb70  mov     rcx, rdi; this
0x18006bb73  mov     [rdi+7Ch], ebp
0x18006bb76  call    ?ScrollToView@CLstBxWinHost@@IEAAHJ@Z; CLstBxWinHost::ScrollToView(long)
0x18006bb7b  test    eax, eax
0x18006bb7d  jnz     short loc_18006BB8F
0x18006bb7f  cmp     [rdi+0D0h], eax
0x18006bb85  jge     loc_18006BC63
0x18006bb8b  mov     [rdi+7Ch], r14d
0x18006bb8f  mov     eax, [rdi+80h]
0x18006bb95  mov     rcx, rdi; this
0x18006bb98  mov     r8d, [rdi+0C8h]
0x18006bb9f  mov     edx, r8d; int
0x18006bba2  shl     ebx, 7
0x18006bba5  xor     ebx, eax
0x18006bba7  and     ebx, 80h
0x18006bbad  xor     ebx, eax
0x18006bbaf  mov     [rdi+80h], ebx
0x18006bbb5  call    ?IsItemViewable@CLstBxWinHost@@QEBAHJ@Z; CLstBxWinHost::IsItemViewable(long)
0x18006bbba  shr     ebx, 7
0x18006bbbd  and     eax, ebx
0x18006bbbf  test    al, 1
0x18006bbc1  jz      loc_18006BC63
0x18006bbc7  xor     r9d, r9d; int
0x18006bbca  xor     edx, edx; HDC
0x18006bbcc  call    ?SetCursor@CLstBxWinHost@@QEAAXPEAUHDC__@@HH@Z; CLstBxWinHost::SetCursor(HDC__ *,int,int)
0x18006bbd1  jmp     loc_18006BC63
0x18006bbd6  mov     rax, [rcx]
0x18006bbd9  lea     rdx, [rsp+88h+var_38]
0x18006bbde  mov     ebx, [rcx+7Ch]
0x18006bbe1  xorps   xmm0, xmm0
0x18006bbe4  sub     ebx, ebp
0x18006bbe6  imul    ebx, [rcx+0B8h]
0x18006bbed  mov     rax, [rax+0C0h]
0x18006bbf4  movups  [rsp+88h+var_38], xmm0
0x18006bbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbfe  mov     rax, [rdi]
0x18006bc01  lea     rcx, [rsp+88h+var_38]
0x18006bc06  mov     [rsp+88h+var_50], 7
0x18006bc0e  xor     r9d, r9d
0x18006bc11  mov     [rsp+88h+var_58], 0
0x18006bc1a  mov     r8d, ebx
0x18006bc1d  mov     [rsp+88h+var_60], 0
0x18006bc26  xor     edx, edx
0x18006bc28  mov     rax, [rax+80h]
0x18006bc2f  mov     [rsp+88h+var_68], rcx
0x18006bc34  mov     rcx, rdi
0x18006bc37  mov     [rdi+7Ch], ebp
0x18006bc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc3f  mov     rax, [rdi]
0x18006bc42  mov     edx, 1
0x18006bc47  mov     r8d, edx
0x18006bc4a  mov     rcx, rdi
0x18006bc4d  mov     rax, [rax+1A0h]
0x18006bc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc59  mov     rcx, [rdi+10h]; hWnd
0x18006bc5d  call    cs:__imp_UpdateWindow
0x18006bc63  mov     eax, 1
0x18006bc68  mov     rcx, [rsp+88h+var_28]
0x18006bc6d  xor     rcx, rsp; StackCookie
0x18006bc70  call    __security_check_cookie
0x18006bc75  mov     rbx, [rsp+88h+arg_10]
0x18006bc7d  add     rsp, 70h
0x18006bc81  pop     r14
0x18006bc83  pop     rdi
0x18006bc84  pop     rbp
0x18006bc85  retn
```

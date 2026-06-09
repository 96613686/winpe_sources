# PathCchIsRoot(ushort const *)

- ea: `0x18002f230`
- end: `0x18002f3f8`
- name: `?PathCchIsRoot@@YAHPEBG@Z`
- size: `456`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18002ee90`

## callees

- `0x18002f230`
- `0x18002f580`
- `0x18002f658`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002f262`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002f378`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002f262`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18002f378`

## pseudocode

```c
__int64 __fastcall PathCchIsRoot(const unsigned __int16 *a1)
{
  int v2; // ebp
  const wchar_t *v3; // rdi
  int v4; // esi
  const wchar_t *v5; // r9
  const unsigned __int16 *v6; // r10
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // r11d
  unsigned __int16 *v11; // rax
  unsigned __int16 v12; // cx
  int v13; // edx
  int v14; // r11d
  const wchar_t *v15; // r8
  const unsigned __int16 *v16; // r9
  int v17; // ecx
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r10d
  const unsigned __int16 *v21; // r9
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  unsigned __int16 *v27; // [rsp+40h] [rbp+8h] BYREF

  v27 = 0;
  if ( a1 && *a1 )
  {
    v2 = 3;
    v3 = L":\\";
    if ( (unsigned int)((__int64 (*)(void))_o_iswalpha)() )
    {
      v4 = 3;
      v5 = L":\\";
      v6 = a1 + 1;
      do
      {
        v7 = *v6;
        v8 = v7 + 32;
        if ( (unsigned int)(v7 - 65) > 0x19 )
          v8 = *v6;
        v9 = *v5;
        v10 = v9 + 32;
        if ( (unsigned int)(v9 - 65) > 0x19 )
          v10 = *v5;
        if ( !--v4 )
          break;
        if ( !v8 )
          break;
        ++v6;
        ++v5;
      }
      while ( v8 == v10 );
      if ( v8 == v10 )
        return 1;
    }
    if ( *a1 == 92 && !a1[1] )
      return 1;
    if ( (unsigned int)PathIsUNCEx(a1, (const unsigned __int16 **)&v27) )
    {
      v11 = v27;
      v12 = *v27;
      if ( *v27 )
      {
        v13 = 0;
        while ( v12 != 92 || ++v13 <= 1 && v11[1] )
        {
          v12 = *++v11;
          if ( !*v11 )
            return 1;
        }
        return 0;
      }
      return 1;
    }
    v14 = 4;
    v15 = L"\\\\?\\";
    v16 = a1;
    do
    {
      v17 = *v16;
      v18 = (unsigned int)(v17 + 32);
      if ( (unsigned int)(v17 - 65) > 0x19 )
        v18 = *v16;
      v19 = *v15;
      v20 = v19 + 32;
      if ( (unsigned int)(v19 - 65) > 0x19 )
        v20 = *v15;
      if ( !--v14 )
        break;
      if ( !(_DWORD)v18 )
        break;
      ++v16;
      ++v15;
    }
    while ( (_DWORD)v18 == v20 );
    if ( (_DWORD)v18 == v20 && (unsigned int)_o_iswalpha(a1[4], v18, v15, v16) )
    {
      v21 = a1 + 5;
      do
      {
        v22 = *v21;
        v23 = v22 + 32;
        if ( (unsigned int)(v22 - 65) > 0x19 )
          v23 = *v21;
        v24 = *v3;
        v25 = v24 + 32;
        if ( (unsigned int)(v24 - 65) > 0x19 )
          v25 = *v3;
        if ( !--v2 )
          break;
        if ( !v23 )
          break;
        ++v21;
        ++v3;
      }
      while ( v23 == v25 );
      if ( v23 == v25 )
        return 1;
    }
    if ( (unsigned int)PathIsVolumeGUIDWorker(a1) && a1[48] == 92 && !a1[49] )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002f230  mov     [rsp+arg_8], rbx
0x18002f235  mov     [rsp+arg_10], rbp
0x18002f23a  push    rsi
0x18002f23b  push    rdi
0x18002f23c  push    r14
0x18002f23e  sub     rsp, 20h
0x18002f242  xor     r14d, r14d
0x18002f245  mov     rbx, rcx
0x18002f248  mov     [rsp+38h+arg_0], r14
0x18002f24d  test    rcx, rcx
0x18002f250  jz      loc_18002F3E3
0x18002f256  movzx   ecx, word ptr [rcx]
0x18002f259  test    cx, cx
0x18002f25c  jz      loc_18002F3E3
0x18002f262  call    cs:__imp__o_iswalpha
0x18002f268  lea     ebp, [r14+3]
0x18002f26c  lea     rdi, asc_18003B6F4; ":\\"
0x18002f273  lea     r8, [rbx+2]
0x18002f277  test    eax, eax
0x18002f279  jz      short loc_18002F2C4
0x18002f27b  mov     esi, ebp
0x18002f27d  mov     r9, rdi
0x18002f280  mov     r10, r8
0x18002f283  movzx   ecx, word ptr [r10]
0x18002f287  lea     eax, [rcx-41h]
0x18002f28a  cmp     eax, 19h
0x18002f28d  lea     edx, [rcx+20h]
0x18002f290  cmova   edx, ecx
0x18002f293  movzx   ecx, word ptr [r9]
0x18002f297  lea     eax, [rcx-41h]
0x18002f29a  cmp     eax, 19h
0x18002f29d  lea     r11d, [rcx+20h]
0x18002f2a1  cmova   r11d, ecx
0x18002f2a5  sub     esi, 1
0x18002f2a8  jz      short loc_18002F2BB
0x18002f2aa  test    edx, edx
0x18002f2ac  jz      short loc_18002F2BB
0x18002f2ae  add     r10, 2
0x18002f2b2  add     r9, 2
0x18002f2b6  cmp     edx, r11d
0x18002f2b9  jz      short loc_18002F283
0x18002f2bb  cmp     edx, r11d
0x18002f2be  jz      loc_18002F3DC
0x18002f2c4  cmp     word ptr [rbx], 5Ch ; '\'
0x18002f2c8  jnz     short loc_18002F2D4
0x18002f2ca  cmp     [r8], r14w
0x18002f2ce  jz      loc_18002F3DC
0x18002f2d4  lea     rdx, [rsp+38h+arg_0]; unsigned __int16 **
0x18002f2d9  mov     rcx, rbx; unsigned __int16 *
0x18002f2dc  call    ?PathIsUNCEx@@YAHPEBGPEAPEBG@Z; PathIsUNCEx(ushort const *,ushort const * *)
0x18002f2e1  test    eax, eax
0x18002f2e3  jz      short loc_18002F326
0x18002f2e5  mov     rax, [rsp+38h+arg_0]
0x18002f2ea  movzx   ecx, word ptr [rax]
0x18002f2ed  test    cx, cx
0x18002f2f0  jz      loc_18002F3DC
0x18002f2f6  mov     edx, r14d
0x18002f2f9  cmp     cx, 5Ch ; '\'
0x18002f2fd  jnz     short loc_18002F315
0x18002f2ff  inc     edx
0x18002f301  cmp     edx, 1
0x18002f304  jg      loc_18002F3E3
0x18002f30a  cmp     [rax+2], r14w
0x18002f30f  jz      loc_18002F3E3
0x18002f315  add     rax, 2
0x18002f319  movzx   ecx, word ptr [rax]
0x18002f31c  test    cx, cx
0x18002f31f  jnz     short loc_18002F2F9
0x18002f321  jmp     loc_18002F3DC
0x18002f326  mov     r11d, 4
0x18002f32c  lea     r8, asc_18003B700; "\\\\?\\"
0x18002f333  mov     r9, rbx
0x18002f336  movzx   ecx, word ptr [r9]
0x18002f33a  lea     eax, [rcx-41h]
0x18002f33d  cmp     eax, 19h
0x18002f340  lea     edx, [rcx+20h]
0x18002f343  cmova   edx, ecx
0x18002f346  movzx   ecx, word ptr [r8]
0x18002f34a  lea     eax, [rcx-41h]
0x18002f34d  cmp     eax, 19h
0x18002f350  lea     r10d, [rcx+20h]
0x18002f354  cmova   r10d, ecx
0x18002f358  sub     r11d, 1
0x18002f35c  jz      short loc_18002F36F
0x18002f35e  test    edx, edx
0x18002f360  jz      short loc_18002F36F
0x18002f362  add     r9, 2
0x18002f366  add     r8, 2
0x18002f36a  cmp     edx, r10d
0x18002f36d  jz      short loc_18002F336
0x18002f36f  cmp     edx, r10d
0x18002f372  jnz     short loc_18002F3C2
0x18002f374  movzx   ecx, word ptr [rbx+8]
0x18002f378  call    cs:__imp__o_iswalpha
0x18002f37e  test    eax, eax
0x18002f380  jz      short loc_18002F3C2
0x18002f382  lea     r9, [rbx+0Ah]
0x18002f386  movzx   ecx, word ptr [r9]
0x18002f38a  lea     eax, [rcx-41h]
0x18002f38d  cmp     eax, 19h
0x18002f390  lea     edx, [rcx+20h]
0x18002f393  cmova   edx, ecx
0x18002f396  movzx   ecx, word ptr [rdi]
0x18002f399  lea     eax, [rcx-41h]
0x18002f39c  cmp     eax, 19h
0x18002f39f  lea     r8d, [rcx+20h]
0x18002f3a3  cmova   r8d, ecx
0x18002f3a7  sub     ebp, 1
0x18002f3aa  jz      short loc_18002F3BD
0x18002f3ac  test    edx, edx
0x18002f3ae  jz      short loc_18002F3BD
0x18002f3b0  add     r9, 2
0x18002f3b4  add     rdi, 2
0x18002f3b8  cmp     edx, r8d
0x18002f3bb  jz      short loc_18002F386
0x18002f3bd  cmp     edx, r8d
0x18002f3c0  jz      short loc_18002F3DC
0x18002f3c2  mov     rcx, rbx; unsigned __int16 *
0x18002f3c5  call    ?PathIsVolumeGUIDWorker@@YAHPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18002f3ca  test    eax, eax
0x18002f3cc  jz      short loc_18002F3E3
0x18002f3ce  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x18002f3d3  jnz     short loc_18002F3E3
0x18002f3d5  cmp     [rbx+62h], r14w
0x18002f3da  jnz     short loc_18002F3E3
0x18002f3dc  mov     eax, 1
0x18002f3e1  jmp     short loc_18002F3E5
0x18002f3e3  xor     eax, eax
0x18002f3e5  mov     rbx, [rsp+38h+arg_8]
0x18002f3ea  mov     rbp, [rsp+38h+arg_10]
0x18002f3ef  add     rsp, 20h
0x18002f3f3  pop     r14
0x18002f3f5  pop     rdi
0x18002f3f6  pop     rsi
0x18002f3f7  retn
```

# PathCchIsRoot(ushort const *)

- ea: `0x140009000`
- end: `0x1400091b3`
- name: `?PathCchIsRoot@@YAHPEBG@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140008974`

## callees

- `0x140009000`
- `0x1400091bc`
- `0x14000928c`

## pseudocode

```c
__int64 __fastcall PathCchIsRoot(const unsigned __int16 *a1)
{
  int v2; // ebp
  const wchar_t *v3; // rdi
  int v4; // esi
  const wchar_t *v5; // r8
  const unsigned __int16 *v6; // r9
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  int v10; // r10d
  unsigned __int16 *v11; // rax
  unsigned __int16 v12; // cx
  int v13; // edx
  int v14; // r11d
  const wchar_t *v15; // r8
  const unsigned __int16 *v16; // r9
  int v17; // ecx
  int v18; // edx
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
    if ( v8 == v10 || *a1 == 92 && !a1[1] )
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
      v18 = v17 + 32;
      if ( (unsigned int)(v17 - 65) > 0x19 )
        v18 = *v16;
      v19 = *v15;
      v20 = v19 + 32;
      if ( (unsigned int)(v19 - 65) > 0x19 )
        v20 = *v15;
      if ( !--v14 )
        break;
      if ( !v18 )
        break;
      ++v16;
      ++v15;
    }
    while ( v18 == v20 );
    if ( v18 == v20 && a1[4] )
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
0x140009000  mov     [rsp+arg_8], rbx
0x140009005  mov     [rsp+arg_10], rbp
0x14000900a  push    rsi
0x14000900b  push    rdi
0x14000900c  push    r14
0x14000900e  sub     rsp, 20h
0x140009012  xor     r14d, r14d
0x140009015  mov     rbx, rcx
0x140009018  mov     [rsp+38h+arg_0], r14
0x14000901d  test    rcx, rcx
0x140009020  jz      loc_14000919E
0x140009026  cmp     [rcx], r14w
0x14000902a  jz      loc_14000919E
0x140009030  lea     ebp, [r14+3]
0x140009034  lea     rdi, asc_140010D0C; ":\\"
0x14000903b  mov     esi, ebp
0x14000903d  mov     r8, rdi
0x140009040  lea     r9, [rcx+2]
0x140009044  movzx   ecx, word ptr [r9]
0x140009048  lea     eax, [rcx-41h]
0x14000904b  cmp     eax, 19h
0x14000904e  lea     edx, [rcx+20h]
0x140009051  cmova   edx, ecx
0x140009054  movzx   ecx, word ptr [r8]
0x140009058  lea     eax, [rcx-41h]
0x14000905b  cmp     eax, 19h
0x14000905e  lea     r10d, [rcx+20h]
0x140009062  cmova   r10d, ecx
0x140009066  sub     esi, 1
0x140009069  jz      short loc_14000907C
0x14000906b  test    edx, edx
0x14000906d  jz      short loc_14000907C
0x14000906f  add     r9, 2
0x140009073  add     r8, 2
0x140009077  cmp     edx, r10d
0x14000907a  jz      short loc_140009044
0x14000907c  cmp     edx, r10d
0x14000907f  jz      loc_140009197
0x140009085  cmp     word ptr [rbx], 5Ch ; '\'
0x140009089  jnz     short loc_140009096
0x14000908b  cmp     [rbx+2], r14w
0x140009090  jz      loc_140009197
0x140009096  lea     rdx, [rsp+38h+arg_0]; unsigned __int16 **
0x14000909b  mov     rcx, rbx; unsigned __int16 *
0x14000909e  call    ?PathIsUNCEx@@YAHPEBGPEAPEBG@Z; PathIsUNCEx(ushort const *,ushort const * *)
0x1400090a3  test    eax, eax
0x1400090a5  jz      short loc_1400090E8
0x1400090a7  mov     rax, [rsp+38h+arg_0]
0x1400090ac  movzx   ecx, word ptr [rax]
0x1400090af  test    cx, cx
0x1400090b2  jz      loc_140009197
0x1400090b8  mov     edx, r14d
0x1400090bb  cmp     cx, 5Ch ; '\'
0x1400090bf  jnz     short loc_1400090D7
0x1400090c1  inc     edx
0x1400090c3  cmp     edx, 1
0x1400090c6  jg      loc_14000919E
0x1400090cc  cmp     [rax+2], r14w
0x1400090d1  jz      loc_14000919E
0x1400090d7  add     rax, 2
0x1400090db  movzx   ecx, word ptr [rax]
0x1400090de  test    cx, cx
0x1400090e1  jnz     short loc_1400090BB
0x1400090e3  jmp     loc_140009197
0x1400090e8  mov     r11d, 4
0x1400090ee  lea     r8, asc_140010D00; "\\\\?\\"
0x1400090f5  mov     r9, rbx
0x1400090f8  movzx   ecx, word ptr [r9]
0x1400090fc  lea     eax, [rcx-41h]
0x1400090ff  cmp     eax, 19h
0x140009102  lea     edx, [rcx+20h]
0x140009105  cmova   edx, ecx
0x140009108  movzx   ecx, word ptr [r8]
0x14000910c  lea     eax, [rcx-41h]
0x14000910f  cmp     eax, 19h
0x140009112  lea     r10d, [rcx+20h]
0x140009116  cmova   r10d, ecx
0x14000911a  sub     r11d, 1
0x14000911e  jz      short loc_140009131
0x140009120  test    edx, edx
0x140009122  jz      short loc_140009131
0x140009124  add     r9, 2
0x140009128  add     r8, 2
0x14000912c  cmp     edx, r10d
0x14000912f  jz      short loc_1400090F8
0x140009131  cmp     edx, r10d
0x140009134  jnz     short loc_14000917D
0x140009136  cmp     [rbx+8], r14w
0x14000913b  jz      short loc_14000917D
0x14000913d  lea     r9, [rbx+0Ah]
0x140009141  movzx   ecx, word ptr [r9]
0x140009145  lea     eax, [rcx-41h]
0x140009148  cmp     eax, 19h
0x14000914b  lea     edx, [rcx+20h]
0x14000914e  cmova   edx, ecx
0x140009151  movzx   ecx, word ptr [rdi]
0x140009154  lea     eax, [rcx-41h]
0x140009157  cmp     eax, 19h
0x14000915a  lea     r8d, [rcx+20h]
0x14000915e  cmova   r8d, ecx
0x140009162  sub     ebp, 1
0x140009165  jz      short loc_140009178
0x140009167  test    edx, edx
0x140009169  jz      short loc_140009178
0x14000916b  add     r9, 2
0x14000916f  add     rdi, 2
0x140009173  cmp     edx, r8d
0x140009176  jz      short loc_140009141
0x140009178  cmp     edx, r8d
0x14000917b  jz      short loc_140009197
0x14000917d  mov     rcx, rbx; unsigned __int16 *
0x140009180  call    ?PathIsVolumeGUIDWorker@@YAHPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x140009185  test    eax, eax
0x140009187  jz      short loc_14000919E
0x140009189  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x14000918e  jnz     short loc_14000919E
0x140009190  cmp     [rbx+62h], r14w
0x140009195  jnz     short loc_14000919E
0x140009197  mov     eax, 1
0x14000919c  jmp     short loc_1400091A0
0x14000919e  xor     eax, eax
0x1400091a0  mov     rbx, [rsp+38h+arg_8]
0x1400091a5  mov     rbp, [rsp+38h+arg_10]
0x1400091aa  add     rsp, 20h
0x1400091ae  pop     r14
0x1400091b0  pop     rdi
0x1400091b1  pop     rsi
0x1400091b2  retn
```

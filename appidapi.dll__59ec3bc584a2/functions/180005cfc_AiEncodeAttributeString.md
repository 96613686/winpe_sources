# AiEncodeAttributeString

- ea: `0x180005cfc`
- end: `0x180005e7e`
- name: `AiEncodeAttributeString`
- size: `386`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a70`
- `0x180007748`
- `0x18000890c`

## callees

- `0x180003fd4`
- `0x180005cfc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005dd3`
- `ntdll!RtlFreeHeap` at `0x180005dd3`

## pseudocode

```c
__int64 __fastcall AiEncodeAttributeString(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  unsigned __int16 v4; // di
  __int64 v7; // r9
  unsigned __int16 v8; // cx
  __int64 v9; // r12
  int v10; // edx
  unsigned __int16 v11; // r8
  unsigned __int16 v12; // dx
  _WORD *v13; // rax
  _WORD *v14; // r8
  void *v15; // r8
  unsigned __int16 i; // r9
  __int16 v17; // cx
  unsigned __int8 v18; // dl

  v3 = 0;
  v4 = *(_WORD *)a1 >> 1;
  *(_OWORD *)a3 = 0;
  if ( v4 )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = 0;
    v9 = 0x400000020000109LL;
    v10 = 0;
    do
    {
      v11 = *(_WORD *)(v7 + 2LL * v8) - 34;
      if ( v11 <= 0x3Au && _bittest64(&v9, v11) )
        ++v10;
      ++v8;
    }
    while ( v8 < v4 );
    if ( v10 )
    {
      if ( (unsigned int)v4 + 2 * v10 > 0x7FFE )
      {
        v3 = -1073741675;
        goto LABEL_12;
      }
      v12 = *(_WORD *)a1 + 4 * v10;
      *(_WORD *)a3 = v12;
      v12 += 2;
      *(_WORD *)(a3 + 2) = v12;
      v13 = AiAlloc(v12);
      *(_QWORD *)(a3 + 8) = v13;
      v14 = v13;
      if ( !v13 )
      {
        v3 = -1073741801;
LABEL_12:
        v15 = *(void **)(a3 + 8);
        if ( v15 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
          *(_OWORD *)a3 = 0;
        }
        return v3;
      }
      for ( i = 0; i < v4; ++i )
      {
        v17 = *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * i);
        if ( (unsigned __int16)(v17 - 34) <= 0x3Au && _bittest64(&v9, (unsigned __int16)(v17 - 34)) )
        {
          *v14 = 37;
          v18 = *(_BYTE *)(*(_QWORD *)(a1 + 8) + 2LL * i);
          v14[2] = (v18 & 0xF) + ((v18 & 0xFu) < 0xA ? 48 : 55);
          v14[1] = (v18 >> 4) + ((unsigned __int8)(v18 >> 4) < 0xAu ? 48 : 55);
          v14 += 2;
        }
        else
        {
          *v14 = v17;
        }
        ++v14;
      }
      *v14 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005cfc  push    rbx
0x180005cfe  push    rbp
0x180005cff  push    rsi
0x180005d00  push    rdi
0x180005d01  push    r12
0x180005d03  push    r14
0x180005d05  push    r15
0x180005d07  sub     rsp, 20h
0x180005d0b  movzx   edi, word ptr [rcx]
0x180005d0e  xor     esi, esi
0x180005d10  shr     di, 1
0x180005d13  xor     eax, eax
0x180005d15  xorps   xmm0, xmm0
0x180005d18  mov     rbx, r8
0x180005d1b  mov     r14, rcx
0x180005d1e  movups  xmmword ptr [r8], xmm0
0x180005d22  cmp     ax, di
0x180005d25  jnb     loc_180005E6D
0x180005d2b  mov     r9, [r14+8]
0x180005d2f  lea     ebp, [rsi+1]
0x180005d32  xor     ecx, ecx
0x180005d34  mov     r12, 400000020000109h
0x180005d3e  xor     edx, edx
0x180005d40  movzx   eax, cx
0x180005d43  movzx   r8d, word ptr [r9+rax*2]
0x180005d48  sub     r8w, 22h ; '"'
0x180005d4d  cmp     r8w, 3Ah ; ':'
0x180005d52  ja      short loc_180005D60
0x180005d54  movzx   eax, r8w
0x180005d58  bt      r12, rax
0x180005d5c  jnb     short loc_180005D60
0x180005d5e  add     edx, ebp
0x180005d60  add     cx, bp
0x180005d63  cmp     cx, di
0x180005d66  jb      short loc_180005D40
0x180005d68  test    edx, edx
0x180005d6a  jz      loc_180005E6D
0x180005d70  movzx   eax, di
0x180005d73  lea     ecx, [rax+rdx*2]
0x180005d76  cmp     ecx, 7FFEh
0x180005d7c  jbe     short loc_180005D85
0x180005d7e  mov     esi, 0C0000095h
0x180005d83  jmp     short loc_180005DB7
0x180005d85  shl     dx, 2
0x180005d89  mov     r15d, 2
0x180005d8f  add     dx, [r14]
0x180005d93  mov     [rbx], dx
0x180005d96  add     dx, r15w
0x180005d9a  movzx   ecx, dx
0x180005d9d  mov     [rbx+2], cx
0x180005da1  call    AiAlloc
0x180005da6  mov     [rbx+8], rax
0x180005daa  mov     r8, rax
0x180005dad  test    rax, rax
0x180005db0  jnz     short loc_180005DE4
0x180005db2  mov     esi, 0C0000017h
0x180005db7  mov     r8, [rbx+8]; P
0x180005dbb  test    r8, r8
0x180005dbe  jz      loc_180005E6D
0x180005dc4  mov     rcx, gs:60h
0x180005dcd  xor     edx, edx; Flags
0x180005dcf  mov     rcx, [rcx+30h]; HeapHandle
0x180005dd3  call    cs:__imp_RtlFreeHeap
0x180005dd9  xorps   xmm0, xmm0
0x180005ddc  movups  xmmword ptr [rbx], xmm0
0x180005ddf  jmp     loc_180005E6D
0x180005de4  xor     r9d, r9d
0x180005de7  mov     r10w, 0FFF9h
0x180005dec  mov     rax, [r14+8]
0x180005df0  movzx   edx, r9w
0x180005df4  movzx   ecx, word ptr [rax+rdx*2]
0x180005df8  lea     eax, [rcx-22h]
0x180005dfb  cmp     ax, 3Ah ; ':'
0x180005dff  ja      short loc_180005E56
0x180005e01  movzx   eax, ax
0x180005e04  bt      r12, rax
0x180005e08  jnb     short loc_180005E56
0x180005e0a  mov     word ptr [r8], 25h ; '%'
0x180005e10  mov     rax, [r14+8]
0x180005e14  mov     dl, [rax+rdx*2]
0x180005e17  mov     al, dl
0x180005e19  and     al, 0Fh
0x180005e1b  movzx   ecx, al
0x180005e1e  cmp     cl, 0Ah
0x180005e21  sbb     ax, ax
0x180005e24  shr     dl, 4
0x180005e27  and     ax, r10w
0x180005e2b  add     ax, 37h ; '7'
0x180005e2f  add     ax, cx
0x180005e32  movzx   ecx, dl
0x180005e35  mov     [r8+4], ax
0x180005e3a  cmp     cl, 0Ah
0x180005e3d  sbb     ax, ax
0x180005e40  and     ax, r10w
0x180005e44  add     ax, 37h ; '7'
0x180005e48  add     ax, cx
0x180005e4b  mov     [r8+2], ax
0x180005e50  add     r8, 4
0x180005e54  jmp     short loc_180005E5A
0x180005e56  mov     [r8], cx
0x180005e5a  add     r9w, bp
0x180005e5e  add     r8, r15
0x180005e61  cmp     r9w, di
0x180005e65  jb      short loc_180005DEC
0x180005e67  xor     ecx, ecx
0x180005e69  mov     [r8], cx
0x180005e6d  mov     eax, esi
0x180005e6f  add     rsp, 20h
0x180005e73  pop     r15
0x180005e75  pop     r14
0x180005e77  pop     r12
0x180005e79  pop     rdi
0x180005e7a  pop     rsi
0x180005e7b  pop     rbp
0x180005e7c  pop     rbx
0x180005e7d  retn
```

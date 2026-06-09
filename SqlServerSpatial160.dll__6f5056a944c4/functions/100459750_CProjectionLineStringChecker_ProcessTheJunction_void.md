# CProjectionLineStringChecker::ProcessTheJunction(void)

- ea: `0x100459750`
- end: `0x100459924`
- name: `?ProcessTheJunction@CProjectionLineStringChecker@@UEAAJXZ`
- size: `468`
- prototype: `__int64 __fastcall(CProjectionLineStringChecker *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x100459750`

## pseudocode

```c
__int64 __fastcall CProjectionLineStringChecker::ProcessTheJunction(CProjectionLineStringChecker *this)
{
  int v2; // eax
  __int64 v3; // rbx
  __int64 v4; // r9
  unsigned int i; // r11d
  __int64 v6; // r8
  bool v7; // cl
  unsigned int v8; // esi
  __int64 v9; // rbx
  unsigned int v10; // edx
  __int64 v11; // r8

  (*(void (__fastcall **)(CProjectionLineStringChecker *))(*(_QWORD *)this + 112LL))(this);
  v2 = *((_DWORD *)this + 146);
  v3 = *((_QWORD *)this + 40);
  v4 = qword_10049A070;
  for ( i = (unsigned int)g_attributesTable; !v2; v3 = *(_QWORD *)(v3 + 24) )
  {
    if ( !v3 )
      break;
    LODWORD(v6) = i & *(_DWORD *)(*(_QWORD *)(v3 + 16) + 104LL);
    v7 = (v4 & *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 24LL) + 104LL)) != 0;
    if ( (*(_BYTE *)(v3 + 72) & 0x20) != 0 )
    {
      do
      {
        v3 = *(_QWORD *)(v3 + 24);
        v8 = v6;
        v6 = i & *(_DWORD *)(*(_QWORD *)(v3 + 16) + 104LL);
        v7 = v7 || (v4 & *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 24LL) + 104LL)) != 0;
      }
      while ( (*(_BYTE *)(v3 + 72) & 0x20) != 0 );
      if ( !v7 )
      {
        (*(void (__fastcall **)(CProjectionLineStringChecker *, __int64, __int64, _QWORD))(*(_QWORD *)this + 104LL))(
          this,
          12,
          v6,
          v8);
        v4 = qword_10049A070;
        i = (unsigned int)g_attributesTable;
      }
    }
    v2 = *((_DWORD *)this + 146);
  }
  v9 = *((_QWORD *)this + 38);
  if ( !v2 )
  {
    while ( v9 )
    {
      v10 = *(unsigned __int16 *)(v9 + 72);
      if ( (v10 & 0x200) != 0 )
      {
        (*(void (__fastcall **)(CProjectionLineStringChecker *, __int64, _QWORD, __int64))(*(_QWORD *)this + 104LL))(
          this,
          8,
          i & *(_DWORD *)(*(_QWORD *)(v9 + 16) + 104LL),
          0xFFFFFFFFLL);
        return 0;
      }
      if ( (v4 & *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 24LL) + 104LL)) == 0 )
      {
        v11 = *(_QWORD *)(v9 + 16);
        if ( *(_QWORD *)v9 != v11
          && (v10 & 0x4840) == 0
          && ((((unsigned __int8)v10 >> 4) ^ (unsigned __int8)(~BYTE1(v10) ^ ~(unsigned __int8)(v10 >> 12))) & 1) != 0 )
        {
          (*(void (__fastcall **)(CProjectionLineStringChecker *, __int64, _QWORD, __int64))(*(_QWORD *)this + 104LL))(
            this,
            8,
            i & *(_DWORD *)(v11 + 104),
            0xFFFFFFFFLL);
          v4 = qword_10049A070;
          i = (unsigned int)g_attributesTable;
        }
      }
      v9 = *(_QWORD *)(v9 + 24);
      if ( *((_DWORD *)this + 146) )
        return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100459750  mov     [rsp+arg_0], rbx
0x100459755  mov     [rsp+arg_8], rsi
0x10045975a  push    rdi
0x10045975b  sub     rsp, 20h
0x10045975f  mov     rax, [rcx]
0x100459762  mov     rdi, rcx
0x100459765  call    qword ptr [rax+70h]
0x100459768  mov     eax, [rdi+248h]
0x10045976e  mov     rbx, [rdi+140h]
0x100459775  mov     r9, cs:qword_10049A070
0x10045977c  mov     r11d, cs:?g_attributesTable@@3QBUCAttribute@@B; CAttribute const near * const g_attributesTable
0x100459783  test    eax, eax
0x100459785  jnz     loc_100459840
0x10045978b  nop     dword ptr [rax+rax+00h]
0x100459790  mov     edx, eax
0x100459792  test    rbx, rbx
0x100459795  jz      loc_100459840
0x10045979b  mov     rax, [rbx+10h]
0x10045979f  mov     r8d, [rax+68h]
0x1004597a3  mov     rax, [rbx+8]
0x1004597a7  and     r8d, r11d
0x1004597aa  mov     rcx, [rax+18h]
0x1004597ae  movzx   eax, byte ptr [rbx+48h]
0x1004597b2  test    [rcx+68h], r9
0x1004597b6  setnz   cl
0x1004597b9  xor     r10b, r10b
0x1004597bc  xor     esi, esi
0x1004597be  shr     al, 5
0x1004597c1  test    al, 1
0x1004597c3  jz      short loc_10045982E
0x1004597c5  test    edx, edx
0x1004597c7  jnz     short loc_100459806
0x1004597c9  mov     rbx, [rbx+18h]
0x1004597cd  mov     esi, r8d
0x1004597d0  mov     r10b, 1
0x1004597d3  mov     rax, [rbx+10h]
0x1004597d7  mov     r8d, [rax+68h]
0x1004597db  and     r8d, r11d
0x1004597de  test    cl, cl
0x1004597e0  jnz     short loc_1004597F4
0x1004597e2  mov     rax, [rbx+8]
0x1004597e6  mov     rcx, [rax+18h]
0x1004597ea  test    [rcx+68h], r9
0x1004597ee  jnz     short loc_1004597F4
0x1004597f0  xor     cl, cl
0x1004597f2  jmp     short loc_1004597F8
0x1004597f4  movzx   ecx, r10b
0x1004597f8  movzx   eax, byte ptr [rbx+48h]
0x1004597fc  shr     al, 5
0x1004597ff  test    r10b, al
0x100459802  jnz     short loc_1004597C5
0x100459804  jmp     short loc_10045980B
0x100459806  test    r10b, r10b
0x100459809  jz      short loc_10045982E
0x10045980b  test    cl, cl
0x10045980d  jnz     short loc_10045982E
0x10045980f  mov     rax, [rdi]
0x100459812  mov     r9d, esi
0x100459815  mov     edx, 0Ch
0x10045981a  mov     rcx, rdi
0x10045981d  call    qword ptr [rax+68h]
0x100459820  mov     r9, cs:qword_10049A070
0x100459827  mov     r11d, cs:?g_attributesTable@@3QBUCAttribute@@B; CAttribute const near * const g_attributesTable
0x10045982e  mov     eax, [rdi+248h]
0x100459834  mov     rbx, [rbx+18h]
0x100459838  test    eax, eax
0x10045983a  jz      loc_100459790
0x100459840  mov     rbx, [rdi+130h]
0x100459847  test    eax, eax
0x100459849  jnz     loc_100459912
0x10045984f  mov     esi, 4840h
0x100459854  test    rbx, rbx
0x100459857  jz      loc_100459912
0x10045985d  movzx   edx, word ptr [rbx+48h]
0x100459861  movzx   eax, dx
0x100459864  shr     ax, 9
0x100459868  test    al, 1
0x10045986a  jnz     loc_1004598F2
0x100459870  mov     rax, [rbx+8]
0x100459874  mov     rcx, [rax+18h]
0x100459878  test    [rcx+68h], r9
0x10045987c  jnz     short loc_1004598CF
0x10045987e  mov     r8, [rbx+10h]
0x100459882  cmp     [rbx], r8
0x100459885  jz      short loc_1004598CF
0x100459887  test    si, dx
0x10045988a  jnz     short loc_1004598CF
0x10045988c  mov     eax, edx
0x10045988e  mov     ecx, edx
0x100459890  shr     ecx, 0Ch
0x100459893  shr     eax, 8
0x100459896  not     cl
0x100459898  shr     dl, 4
0x10045989b  not     al
0x10045989d  xor     cl, al
0x10045989f  xor     cl, dl
0x1004598a1  test    cl, 1
0x1004598a4  jz      short loc_1004598CF
0x1004598a6  mov     r8d, [r8+68h]
0x1004598aa  mov     edx, 8
0x1004598af  mov     rax, [rdi]
0x1004598b2  and     r8d, r11d
0x1004598b5  mov     r9d, 0FFFFFFFFh
0x1004598bb  mov     rcx, rdi
0x1004598be  call    qword ptr [rax+68h]
0x1004598c1  mov     r9, cs:qword_10049A070
0x1004598c8  mov     r11d, cs:?g_attributesTable@@3QBUCAttribute@@B; CAttribute const near * const g_attributesTable
0x1004598cf  cmp     dword ptr [rdi+248h], 0
0x1004598d6  mov     rbx, [rbx+18h]
0x1004598da  jz      loc_100459854
0x1004598e0  xor     eax, eax
0x1004598e2  mov     rbx, [rsp+28h+arg_0]
0x1004598e7  mov     rsi, [rsp+28h+arg_8]
0x1004598ec  add     rsp, 20h
0x1004598f0  pop     rdi
0x1004598f1  retn
0x1004598f2  mov     rax, [rbx+10h]
0x1004598f6  mov     edx, 8
0x1004598fb  mov     r10, [rdi]
0x1004598fe  mov     r9d, 0FFFFFFFFh
0x100459904  mov     rcx, rdi
0x100459907  mov     r8d, [rax+68h]
0x10045990b  and     r8d, r11d
0x10045990e  call    qword ptr [r10+68h]
0x100459912  mov     rbx, [rsp+28h+arg_0]
0x100459917  xor     eax, eax
0x100459919  mov     rsi, [rsp+28h+arg_8]
0x10045991e  add     rsp, 20h
0x100459922  pop     rdi
0x100459923  retn
```

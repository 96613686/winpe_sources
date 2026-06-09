# CPersistStreamInit::GetXMLColumnName(CRowInfo &,ushort)

- ea: `0x18001b4c0`
- end: `0x18001b71f`
- name: `?GetXMLColumnName@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `607`
- prototype: `int(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001adfc`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180004038`
- `0x18001b4c0`
- `0x18001b884`
- `0x18001b90c`
- `0x180022ea0`

## import_xrefs

- `msvcrt!_itow_s` at `0x18001b69b`
- `msvcrt!_itow_s` at `0x18001b69b`
- `msvcrt!_itoa_s` at `0x18001b649`
- `msvcrt!_itoa_s` at `0x18001b649`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::GetXMLColumnName(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  char *v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // esi
  unsigned __int16 *Name; // rax
  unsigned int v8; // edx
  CPersistStreamInit *v9; // r9
  wchar_t *v10; // r10
  wchar_t *v11; // r14
  _BYTE *v12; // r15
  char IsValidTagName; // r12
  void *v14; // rbp
  bool IsUniqueColumnName; // al
  unsigned __int8 *v16; // rax
  int v17; // esi
  size_t v18; // r8
  __int64 v19; // r8
  char v22; // [rsp+88h] [rbp+10h]
  char *v24; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v22 = 0;
  v24 = 0;
  LODWORD(v5) = 0;
  v6 = 0;
  Name = CMetaData::mdGetName(a2, a3);
  v11 = Name;
  if ( !Name )
    goto LABEL_9;
  v5 = -1;
  do
    ++v5;
  while ( Name[v5] != (_WORD)v10 );
  if ( (_DWORD)v5 )
  {
    v12 = (char *)v9 + 64;
    IsValidTagName = (char)v10;
    if ( *((_BYTE *)v9 + 64) != (_BYTE)v10 )
    {
      LODWORD(v5) = ToUTF8(Name, v5, &v24);
      if ( (_DWORD)v5 == -1 )
        return (unsigned int)-2147024882;
      v4 = v24;
      v10 = 0;
      v9 = this;
      v22 = 1;
    }
  }
  else
  {
LABEL_9:
    IsValidTagName = 1;
    v12 = (char *)v9 + 64;
  }
  v14 = v11;
  if ( *v12 != (_BYTE)v10 )
    v14 = v4;
  if ( !IsValidTagName )
  {
    IsValidTagName = CPersistStreamInit::IsValidTagName(v9, v14, v5);
    v10 = 0;
  }
  if ( *v12 == (_BYTE)v10 )
  {
    LODWORD(v5) = (_DWORD)v10;
    v11 = v10;
  }
  if ( !IsValidTagName )
  {
    IsUniqueColumnName = CPersistStreamInit::IsUniqueColumnName(this, a2, a3, v14);
    LOBYTE(v10) = 0;
    if ( IsUniqueColumnName )
      goto LABEL_37;
  }
  if ( (int)v5 >= 7 )
  {
LABEL_25:
    v17 = a3;
    LOBYTE(v24) = 1;
    do
    {
      v18 = (unsigned int)v5 - 1LL;
      if ( *v12 )
      {
        *v4 = 99;
        _itoa_s(v17, v4 + 1, v18, 10);
      }
      else
      {
        *v11 = 99;
        _itow_s(v17, v11 + 1, v18, 10);
      }
      ++v17;
    }
    while ( !CPersistStreamInit::IsUniqueColumnName(this, a2, a3, v14) );
    v6 = 0;
    IsValidTagName = (char)v24;
LABEL_37:
    v19 = 2LL * a3;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 8) = IsValidTagName;
    *(_QWORD *)(*((_QWORD *)a2 + 8) + 8 * v19) = v14;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 9) = v22;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 10) = *v12;
    return v6;
  }
  if ( *v12 == (_BYTE)v10 )
  {
    v16 = MMMAlloc(0xEu, v8);
    v11 = (wchar_t *)v16;
  }
  else
  {
    if ( v4 )
      MMMFree((unsigned __int8 *)v4);
    v16 = MMMAlloc(7u, v8);
    v4 = (char *)v16;
  }
  if ( v16 )
  {
    v14 = v16;
    v22 = 1;
    LODWORD(v5) = 7;
    goto LABEL_25;
  }
  v6 = -2147024882;
  if ( v22 )
  {
    if ( v11 )
      MMMFree((unsigned __int8 *)v11);
    if ( v4 )
      MMMFree((unsigned __int8 *)v4);
  }
  return v6;
}

```

## disassembly

```asm
0x18001b4c0  mov     rax, rsp
0x18001b4c3  mov     [rax+18h], r8w
0x18001b4c8  mov     [rax+8], rcx
0x18001b4cc  push    rbx
0x18001b4cd  push    rbp
0x18001b4ce  push    rsi
0x18001b4cf  push    rdi
0x18001b4d0  push    r12
0x18001b4d2  push    r13
0x18001b4d4  push    r14
0x18001b4d6  push    r15
0x18001b4d8  sub     rsp, 38h
0x18001b4dc  xor     r10d, r10d
0x18001b4df  mov     r13, rdx
0x18001b4e2  mov     ebx, r10d
0x18001b4e5  mov     [rsp+78h+arg_8], r10b
0x18001b4ed  mov     r9, rcx
0x18001b4f0  mov     [rax+20h], rbx
0x18001b4f4  movzx   edx, r8w; unsigned __int16
0x18001b4f8  mov     [rsp+78h+var_58], r10d
0x18001b4fd  mov     rcx, r13; this
0x18001b500  mov     edi, r10d
0x18001b503  mov     esi, r10d
0x18001b506  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x18001b50b  mov     r14, rax
0x18001b50e  test    rax, rax
0x18001b511  jz      short loc_18001B576
0x18001b513  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b517  inc     rdi
0x18001b51a  cmp     [rax+rdi*2], r10w
0x18001b51f  jnz     short loc_18001B517
0x18001b521  test    edi, edi
0x18001b523  jz      short loc_18001B576
0x18001b525  lea     r15, [r9+40h]
0x18001b529  mov     r12b, r10b
0x18001b52c  cmp     [r15], r10b
0x18001b52f  jz      short loc_18001B57D
0x18001b531  lea     r8, [rsp+78h+arg_18]; char **
0x18001b539  mov     edx, edi; int
0x18001b53b  mov     rcx, r14; unsigned __int16 *
0x18001b53e  call    ?ToUTF8@@YAHPEAGHPEAPEAD@Z; ToUTF8(ushort *,int,char * *)
0x18001b543  mov     edi, eax
0x18001b545  cmp     eax, 0FFFFFFFFh
0x18001b548  jz      short loc_18001B56C
0x18001b54a  mov     rbx, [rsp+78h+arg_18]
0x18001b552  xor     r10d, r10d
0x18001b555  mov     r9, [rsp+78h+arg_0]
0x18001b55d  mov     [rsp+78h+var_58], r10d
0x18001b562  mov     [rsp+78h+arg_8], 1
0x18001b56a  jmp     short loc_18001B57D
0x18001b56c  mov     esi, 8007000Eh
0x18001b571  jmp     loc_18001B70C
0x18001b576  mov     r12b, 1
0x18001b579  lea     r15, [r9+40h]
0x18001b57d  cmp     [r15], r10b
0x18001b580  mov     rbp, r14
0x18001b583  cmovnz  rbp, rbx
0x18001b587  test    r12b, r12b
0x18001b58a  jnz     short loc_18001B5A0
0x18001b58c  mov     r8d, edi; unsigned int
0x18001b58f  mov     rdx, rbp; void *
0x18001b592  mov     rcx, r9; this
0x18001b595  call    ?IsValidTagName@CPersistStreamInit@@AEBA_NPEAXK@Z; CPersistStreamInit::IsValidTagName(void *,ulong)
0x18001b59a  mov     r12b, al
0x18001b59d  xor     r10d, r10d
0x18001b5a0  cmp     [r15], r10b
0x18001b5a3  jnz     short loc_18001B5AB
0x18001b5a5  mov     edi, r10d
0x18001b5a8  mov     r14, r10
0x18001b5ab  test    r12b, r12b
0x18001b5ae  jnz     short loc_18001B5D7
0x18001b5b0  movzx   r8d, [rsp+78h+arg_10]; unsigned __int16
0x18001b5b9  mov     r9, rbp; void *
0x18001b5bc  mov     rcx, [rsp+78h+arg_0]; this
0x18001b5c4  mov     rdx, r13; struct CRowInfo *
0x18001b5c7  call    ?IsUniqueColumnName@CPersistStreamInit@@AEBA_NAEAVCRowInfo@@GPEAX@Z; CPersistStreamInit::IsUniqueColumnName(CRowInfo &,ushort,void *)
0x18001b5cc  xor     r10d, r10d
0x18001b5cf  test    al, al
0x18001b5d1  jnz     loc_18001B6D3
0x18001b5d7  mov     r12d, 7
0x18001b5dd  cmp     edi, r12d
0x18001b5e0  jge     short loc_18001B612
0x18001b5e2  cmp     [r15], r10b
0x18001b5e5  jz      short loc_18001B651
0x18001b5e7  test    rbx, rbx
0x18001b5ea  jz      short loc_18001B5F4
0x18001b5ec  mov     rcx, rbx; unsigned __int8 *
0x18001b5ef  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001b5f4  mov     ecx, r12d; unsigned int
0x18001b5f7  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001b5fc  mov     rbx, rax
0x18001b5ff  test    rax, rax
0x18001b602  jz      short loc_18001B660
0x18001b604  mov     rbp, rax
0x18001b607  mov     [rsp+78h+arg_8], 1
0x18001b60f  mov     edi, r12d
0x18001b612  movzx   esi, [rsp+78h+arg_10]
0x18001b61a  mov     eax, 63h ; 'c'
0x18001b61f  mov     r12, [rsp+78h+arg_0]
0x18001b627  mov     byte ptr [rsp+78h+arg_18], 1
0x18001b62f  mov     edi, edi
0x18001b631  cmp     byte ptr [r15], 0
0x18001b635  lea     r8, [rdi-1]; BufferCount
0x18001b639  mov     r9d, 0Ah; Radix
0x18001b63f  mov     ecx, esi; Value
0x18001b641  jz      short loc_18001B693
0x18001b643  lea     rdx, [rbx+1]; Buffer
0x18001b647  mov     [rbx], al
0x18001b649  call    cs:__imp__itoa_s
0x18001b64f  jmp     short loc_18001B6A1
0x18001b651  mov     ecx, 0Eh; unsigned int
0x18001b656  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001b65b  mov     r14, rax
0x18001b65e  jmp     short loc_18001B5FF
0x18001b660  cmp     [rsp+78h+arg_8], 0
0x18001b668  mov     esi, 8007000Eh
0x18001b66d  jz      loc_18001B70C
0x18001b673  test    r14, r14
0x18001b676  jz      short loc_18001B680
0x18001b678  mov     rcx, r14; unsigned __int8 *
0x18001b67b  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001b680  test    rbx, rbx
0x18001b683  jz      loc_18001B70C
0x18001b689  mov     rcx, rbx; unsigned __int8 *
0x18001b68c  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001b691  jmp     short loc_18001B70C
0x18001b693  lea     rdx, [r14+2]; Buffer
0x18001b697  mov     [r14], ax
0x18001b69b  call    cs:__imp__itow_s
0x18001b6a1  movzx   r8d, [rsp+78h+arg_10]; unsigned __int16
0x18001b6aa  mov     r9, rbp; void *
0x18001b6ad  mov     rdx, r13; struct CRowInfo *
0x18001b6b0  mov     rcx, r12; this
0x18001b6b3  inc     esi
0x18001b6b5  call    ?IsUniqueColumnName@CPersistStreamInit@@AEBA_NAEAVCRowInfo@@GPEAX@Z; CPersistStreamInit::IsUniqueColumnName(CRowInfo &,ushort,void *)
0x18001b6ba  test    al, al
0x18001b6bc  mov     eax, 63h ; 'c'
0x18001b6c1  jz      loc_18001B631
0x18001b6c7  mov     esi, [rsp+78h+var_58]
0x18001b6cb  mov     r12b, byte ptr [rsp+78h+arg_18]
0x18001b6d3  mov     rcx, [r13+40h]
0x18001b6d7  movzx   r8d, [rsp+78h+arg_10]
0x18001b6e0  mov     al, [rsp+78h+arg_8]
0x18001b6e7  add     r8, r8
0x18001b6ea  mov     [rcx+r8*8+8], r12b
0x18001b6ef  mov     rcx, [r13+40h]
0x18001b6f3  mov     [rcx+r8*8], rbp
0x18001b6f7  mov     rcx, [r13+40h]
0x18001b6fb  mov     [rcx+r8*8+9], al
0x18001b700  mov     rdx, [r13+40h]
0x18001b704  mov     cl, [r15]
0x18001b707  mov     [rdx+r8*8+0Ah], cl
0x18001b70c  mov     eax, esi
0x18001b70e  add     rsp, 38h
0x18001b712  pop     r15
0x18001b714  pop     r14
0x18001b716  pop     r13
0x18001b718  pop     r12
0x18001b71a  pop     rdi
0x18001b71b  pop     rsi
0x18001b71c  pop     rbp
0x18001b71d  pop     rbx
0x18001b71e  retn
```

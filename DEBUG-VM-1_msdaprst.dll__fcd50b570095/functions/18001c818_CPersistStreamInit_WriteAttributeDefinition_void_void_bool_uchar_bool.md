# CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)

- ea: `0x18001c818`
- end: `0x18001c92d`
- name: `?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z`
- size: `277`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, bool@<r9b>, char, bool)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x18001ca70`
- `0x18001ccf4`
- `0x18001ce6c`
- `0x18001d3b4`
- `0x18001e44c`
- `0x18001e7a4`
- `0x18001edac`
- `0x18001f1a4`

## callees

- `0x18001c36c`
- `0x18001c6a4`
- `0x18001c818`
- `0x18001e348`
- `0x18001f470`
- `0x18001f7ec`

## pseudocode

```c
int __fastcall CPersistStreamInit::WriteAttributeDefinition(
        CPersistStreamInit *this,
        void *a2,
        unsigned __int16 *a3,
        char a4,
        char a5,
        bool a6)
{
  __int64 v7; // rdx
  int result; // eax
  unsigned int v11; // eax
  _BYTE *v12; // rdx
  CPersistStreamInit *v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  _BYTE *v16; // rdx
  CPersistStreamInit *v17; // rcx
  unsigned int v18; // [rsp+78h] [rbp+20h] BYREF

  LOBYTE(v18) = a4;
  v7 = *((_QWORD *)this + 9);
  v18 = 0;
  result = CPersistStreamInit::Write(this, *(_BYTE **)(v7 + 704), *(unsigned __int8 *)(v7 + 712), &v18, 1);
  if ( result >= 0 )
  {
    if ( !a5 || (result = CPersistStreamInit::WriteNamespace(this, a5), result >= 0) )
    {
      v11 = CPersistStreamInit::_len(this, a2);
      result = CPersistStreamInit::Write(v13, v12, v11, &v18, 0);
      if ( result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v18);
        if ( result >= 0 )
        {
          result = CPersistStreamInit::WriteTag(this, 0x29u, &v18);
          if ( result >= 0 )
          {
            if ( a6 && *((_BYTE *)this + 64) )
            {
              v14 = -1;
              do
                ++v14;
              while ( a3[v14] );
              result = CPersistStreamInit::TextOutW(this, a3, v14, 0x82u);
            }
            else
            {
              v15 = CPersistStreamInit::_len(this, a3);
              result = CPersistStreamInit::Write(v17, v16, v15, &v18, 0);
            }
            if ( result >= 0 )
              return CPersistStreamInit::WriteTag(this, 0x29u, &v18);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c818  mov     rax, rsp
0x18001c81b  mov     [rax+20h], r9b
0x18001c81f  push    rbx
0x18001c820  push    rbp
0x18001c821  push    rsi
0x18001c822  push    rdi
0x18001c823  sub     rsp, 38h
0x18001c827  mov     rsi, rdx
0x18001c82a  mov     byte ptr [rax-38h], 1
0x18001c82e  mov     rdx, [rcx+48h]
0x18001c832  lea     r9, [rax+20h]; unsigned int *
0x18001c836  mov     rdi, r8
0x18001c839  xor     ebp, ebp
0x18001c83b  mov     [rax+20h], ebp
0x18001c83e  mov     rbx, rcx
0x18001c841  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001c849  mov     rdx, [rdx+2C0h]; Src
0x18001c850  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001c855  test    eax, eax
0x18001c857  js      loc_18001C924
0x18001c85d  mov     dl, [rsp+58h+arg_20]; unsigned __int8
0x18001c864  test    dl, dl
0x18001c866  jz      short loc_18001C878
0x18001c868  mov     rcx, rbx; this
0x18001c86b  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001c870  test    eax, eax
0x18001c872  js      loc_18001C924
0x18001c878  mov     rdx, rsi; void *
0x18001c87b  mov     rcx, rbx; this
0x18001c87e  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001c883  mov     r8d, eax; Size
0x18001c886  mov     [rsp+58h+var_38], bpl; bool
0x18001c88b  lea     r9, [rsp+58h+arg_18]; unsigned int *
0x18001c890  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001c895  test    eax, eax
0x18001c897  js      loc_18001C924
0x18001c89d  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001c8a2  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001c8a4  mov     rcx, rbx; this
0x18001c8a7  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001c8ac  test    eax, eax
0x18001c8ae  js      short loc_18001C924
0x18001c8b0  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001c8b5  mov     dl, 29h ; ')'; unsigned __int8
0x18001c8b7  mov     rcx, rbx; this
0x18001c8ba  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001c8bf  test    eax, eax
0x18001c8c1  js      short loc_18001C924
0x18001c8c3  cmp     [rsp+58h+arg_28], bpl
0x18001c8cb  jz      short loc_18001C8F4
0x18001c8cd  cmp     [rbx+40h], bpl
0x18001c8d1  jz      short loc_18001C8F4
0x18001c8d3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c8d7  inc     r8; unsigned int
0x18001c8da  cmp     [rdi+r8*2], bp
0x18001c8df  jnz     short loc_18001C8D7
0x18001c8e1  mov     r9d, 82h; unsigned __int16
0x18001c8e7  mov     rdx, rdi; unsigned __int16 *
0x18001c8ea  mov     rcx, rbx; this
0x18001c8ed  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001c8f2  jmp     short loc_18001C911
0x18001c8f4  mov     rdx, rdi; void *
0x18001c8f7  mov     rcx, rbx; this
0x18001c8fa  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001c8ff  mov     r8d, eax; Size
0x18001c902  mov     [rsp+58h+var_38], bpl; bool
0x18001c907  lea     r9, [rsp+58h+arg_18]; unsigned int *
0x18001c90c  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001c911  test    eax, eax
0x18001c913  js      short loc_18001C924
0x18001c915  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001c91a  mov     dl, 29h ; ')'; unsigned __int8
0x18001c91c  mov     rcx, rbx; this
0x18001c91f  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001c924  add     rsp, 38h
0x18001c928  pop     rdi
0x18001c929  pop     rsi
0x18001c92a  pop     rbp
0x18001c92b  pop     rbx
0x18001c92c  retn
```

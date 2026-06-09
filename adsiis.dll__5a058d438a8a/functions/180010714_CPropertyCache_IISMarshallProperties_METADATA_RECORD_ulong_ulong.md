# CPropertyCache::IISMarshallProperties(_METADATA_RECORD * *,ulong *,ulong)

- ea: `0x180010714`
- end: `0x1800107e9`
- name: `?IISMarshallProperties@CPropertyCache@@QEAAJPEAPEAU_METADATA_RECORD@@PEAKK@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct IIsSchema **this, struct _METADATA_RECORD **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006894`

## callees

- `0x180010714`
- `0x180010968`
- `0x180017f6c`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180010752`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180010752`

## pseudocode

```c
__int64 __fastcall CPropertyCache::IISMarshallProperties(
        struct IIsSchema **this,
        struct _METADATA_RECORD **a2,
        unsigned int *a3,
        int a4)
{
  int Schema; // ebx
  unsigned int v9; // eax
  struct _METADATA_RECORD *v10; // rax
  struct _METADATA_RECORD *v11; // rbp
  unsigned int v12; // r14d
  unsigned int i; // esi
  struct IIsSchema *v14; // rcx
  __int64 v15; // rdx

  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema >= 0 )
  {
    v9 = *((_DWORD *)this + 2);
    if ( v9 > 0x6666666 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v10 = (struct _METADATA_RECORD *)AllocADsMem(40 * v9);
      v11 = v10;
      if ( v10 )
      {
        *a2 = v10;
        v12 = 0;
        for ( i = 0; i < *((_DWORD *)this + 2); ++i )
        {
          v14 = this[4];
          v15 = 544LL * i;
          if ( *(_DWORD *)((char *)v14 + v15 + 520) == a4 )
          {
            CopyIISSynIdToIIS(
              this[9],
              *(_DWORD *)((char *)v14 + v15 + 528),
              *(_DWORD *)((char *)v14 + v15 + 532),
              v11,
              *(struct _iistype **)((char *)v14 + v15 + 536),
              *(_DWORD *)((char *)v14 + v15 + 524));
            Schema = 0;
            ++v11;
            ++v12;
          }
        }
        *a3 = v12;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x180010714  push    rbx
0x180010716  push    rbp
0x180010717  push    rsi
0x180010718  push    rdi
0x180010719  push    r12
0x18001071b  push    r14
0x18001071d  push    r15
0x18001071f  sub     rsp, 30h
0x180010723  mov     r12d, r9d
0x180010726  mov     r15, r8
0x180010729  mov     rsi, rdx
0x18001072c  mov     rdi, rcx
0x18001072f  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010734  mov     ebx, eax
0x180010736  test    eax, eax
0x180010738  js      loc_1800107D8
0x18001073e  mov     eax, [rdi+8]
0x180010741  cmp     eax, 6666666h
0x180010746  ja      loc_1800107D3
0x18001074c  lea     ecx, [rax+rax*4]
0x18001074f  shl     ecx, 3; cb
0x180010752  call    cs:__imp_AllocADsMem
0x180010758  mov     rbp, rax
0x18001075b  test    rax, rax
0x18001075e  jnz     short loc_180010767
0x180010760  mov     ebx, 8007000Eh
0x180010765  jmp     short loc_1800107D8
0x180010767  mov     [rsi], rax
0x18001076a  xor     r14d, r14d
0x18001076d  xor     esi, esi
0x18001076f  cmp     [rdi+8], esi
0x180010772  jbe     short loc_1800107CE
0x180010774  mov     rcx, [rdi+20h]
0x180010778  mov     eax, esi
0x18001077a  imul    rdx, rax, 220h
0x180010781  cmp     [rdx+rcx+208h], r12d
0x180010789  jnz     short loc_1800107C7
0x18001078b  mov     eax, [rdx+rcx+20Ch]
0x180010792  mov     r9, rbp; struct _METADATA_RECORD *
0x180010795  mov     r8d, [rdx+rcx+214h]; unsigned int
0x18001079d  mov     [rsp+68h+var_40], eax; unsigned int
0x1800107a1  mov     rax, [rdx+rcx+218h]
0x1800107a9  mov     edx, [rdx+rcx+210h]; unsigned int
0x1800107b0  mov     rcx, [rdi+48h]; struct IIsSchema *
0x1800107b4  mov     [rsp+68h+var_48], rax; struct _iistype *
0x1800107b9  call    ?CopyIISSynIdToIIS@@YAPEAU_METADATA_RECORD@@PEAVIIsSchema@@KKPEAU1@PEAU_iistype@@K@Z; CopyIISSynIdToIIS(IIsSchema *,ulong,ulong,_METADATA_RECORD *,_iistype *,ulong)
0x1800107be  xor     ebx, ebx
0x1800107c0  add     rbp, 28h ; '('
0x1800107c4  inc     r14d
0x1800107c7  inc     esi
0x1800107c9  cmp     esi, [rdi+8]
0x1800107cc  jb      short loc_180010774
0x1800107ce  mov     [r15], r14d
0x1800107d1  jmp     short loc_1800107D8
0x1800107d3  mov     ebx, 80070216h
0x1800107d8  mov     eax, ebx
0x1800107da  add     rsp, 30h
0x1800107de  pop     r15
0x1800107e0  pop     r14
0x1800107e2  pop     r12
0x1800107e4  pop     rdi
0x1800107e5  pop     rsi
0x1800107e6  pop     rbp
0x1800107e7  pop     rbx
0x1800107e8  retn
```

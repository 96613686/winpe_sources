# CScopeItem::Save(IStream *,int)

- ea: `0x180051200`
- end: `0x18005130b`
- name: `?Save@CScopeItem@@UEAAJPEAUIStream@@H@Z`
- size: `267`
- prototype: `int(CScopeItem *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180051200`

## import_xrefs

- `SHCORE!IStream_Write` at `0x18005122f`
- `SHCORE!IStream_Write` at `0x180051248`
- `SHCORE!IStream_Write` at `0x180051261`
- `SHCORE!IStream_Write` at `0x180051288`
- `SHCORE!IStream_Write` at `0x1800512fd`
- `SHCORE!IStream_Write` at `0x18005122f`
- `SHCORE!IStream_Write` at `0x180051248`
- `SHCORE!IStream_Write` at `0x180051261`
- `SHCORE!IStream_Write` at `0x180051288`
- `SHCORE!IStream_Write` at `0x1800512fd`
- `SHCORE!IStream_WriteStr` at `0x1800512e2`
- `SHCORE!IStream_WriteStr` at `0x1800512e2`
- `Windows.Storage!__imp_ILSaveToStream` at `0x1800512ad`
- `Windows.Storage!__imp_ILSaveToStream` at `0x1800512ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800512b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800512b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005121c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005121c`

## pseudocode

```c
__int64 __fastcall CScopeItem::Save(CScopeItem *this, struct IStream *a2)
{
  HRESULT v4; // ebx
  const ITEMIDLIST *v5; // rdx
  BOOL pv; // [rsp+40h] [rbp+8h] BYREF

  AcquireSRWLockShared((PSRWLOCK)this + 7);
  v4 = IStream_Write(a2, (char *)this + 20, 4u);
  if ( v4 >= 0 )
  {
    v4 = IStream_Write(a2, (char *)this + 16, 4u);
    if ( v4 >= 0 )
    {
      v4 = IStream_Write(a2, (char *)this + 24, 4u);
      if ( v4 >= 0 )
      {
        pv = *((_QWORD *)this + 6) != 0;
        v4 = IStream_Write(a2, &pv, 4u);
        if ( v4 >= 0 )
        {
          if ( !pv || (v4 = IStream_WriteStr(a2, *((PCWSTR *)this + 6)), v4 >= 0) )
          {
            if ( (*((_BYTE *)this + 24) & 2) == 0 || (v4 = IStream_Write(a2, (char *)this + 28, 0x10u), v4 >= 0) )
            {
              v5 = (const ITEMIDLIST *)*((_QWORD *)this + 1);
              if ( v5 )
                v4 = ILSaveToStream(a2, v5);
              else
                v4 = -2147418113;
            }
          }
        }
      }
    }
  }
  ReleaseSRWLockShared((PSRWLOCK)this + 7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180051200  mov     [rsp+arg_8], rbx
0x180051205  mov     [rsp+arg_10], rbp
0x18005120a  push    rsi
0x18005120b  push    rdi
0x18005120c  push    r14
0x18005120e  sub     rsp, 20h
0x180051212  mov     rdi, rcx
0x180051215  mov     rsi, rdx
0x180051218  add     rcx, 38h ; '8'; SRWLock
0x18005121c  call    cs:__imp_AcquireSRWLockShared
0x180051222  lea     rdx, [rdi+14h]; pv
0x180051226  mov     r8d, 4; cb
0x18005122c  mov     rcx, rsi; pstm
0x18005122f  call    cs:__imp_IStream_Write
0x180051235  mov     ebx, eax
0x180051237  test    eax, eax
0x180051239  js      short loc_1800512B5
0x18005123b  lea     rdx, [rdi+10h]; pv
0x18005123f  mov     r8d, 4; cb
0x180051245  mov     rcx, rsi; pstm
0x180051248  call    cs:__imp_IStream_Write
0x18005124e  mov     ebx, eax
0x180051250  test    eax, eax
0x180051252  js      short loc_1800512B5
0x180051254  mov     r8d, 4; cb
0x18005125a  lea     rdx, [rdi+18h]; pv
0x18005125e  mov     rcx, rsi; pstm
0x180051261  call    cs:__imp_IStream_Write
0x180051267  mov     ebx, eax
0x180051269  test    eax, eax
0x18005126b  js      short loc_1800512B5
0x18005126d  xor     eax, eax
0x18005126f  lea     rdx, [rsp+38h+pv]; pv
0x180051274  cmp     [rdi+30h], rax
0x180051278  mov     r8d, 4; cb
0x18005127e  mov     rcx, rsi; pstm
0x180051281  setnz   al
0x180051284  mov     [rsp+38h+pv], eax
0x180051288  call    cs:__imp_IStream_Write
0x18005128e  mov     ebx, eax
0x180051290  test    eax, eax
0x180051292  js      short loc_1800512B5
0x180051294  cmp     [rsp+38h+pv], 0
0x180051299  jnz     short loc_1800512DB
0x18005129b  test    byte ptr [rdi+18h], 2
0x18005129f  jnz     short loc_1800512F0
0x1800512a1  mov     rdx, [rdi+8]; pidl
0x1800512a5  test    rdx, rdx
0x1800512a8  jz      short loc_1800512D4
0x1800512aa  mov     rcx, rsi; pstm
0x1800512ad  call    cs:__imp_ILSaveToStream
0x1800512b3  mov     ebx, eax
0x1800512b5  lea     rcx, [rdi+38h]; SRWLock
0x1800512b9  call    cs:__imp_ReleaseSRWLockShared
0x1800512bf  mov     rbp, [rsp+38h+arg_10]
0x1800512c4  mov     eax, ebx
0x1800512c6  mov     rbx, [rsp+38h+arg_8]
0x1800512cb  add     rsp, 20h
0x1800512cf  pop     r14
0x1800512d1  pop     rdi
0x1800512d2  pop     rsi
0x1800512d3  retn
0x1800512d4  mov     ebx, 8000FFFFh
0x1800512d9  jmp     short loc_1800512B5
0x1800512db  mov     rdx, [rdi+30h]; psz
0x1800512df  mov     rcx, rsi; pstm
0x1800512e2  call    cs:__imp_IStream_WriteStr
0x1800512e8  mov     ebx, eax
0x1800512ea  test    eax, eax
0x1800512ec  jns     short loc_18005129B
0x1800512ee  jmp     short loc_1800512B5
0x1800512f0  lea     rdx, [rdi+1Ch]; pv
0x1800512f4  mov     r8d, 10h; cb
0x1800512fa  mov     rcx, rsi; pstm
0x1800512fd  call    cs:__imp_IStream_Write
0x180051303  mov     ebx, eax
0x180051305  test    eax, eax
0x180051307  jns     short loc_1800512A1
0x180051309  jmp     short loc_1800512B5
```

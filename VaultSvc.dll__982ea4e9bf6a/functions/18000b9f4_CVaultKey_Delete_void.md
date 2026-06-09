# CVaultKey::Delete(void)

- ea: `0x18000b9f4`
- end: `0x18000ba46`
- name: `?Delete@CVaultKey@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(CVaultKey *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000acfc`
- `0x18000af08`
- `0x18000af40`
- `0x180037f5c`

## callees

- `0x18000b9f4`
- `0x180012210`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18000ba05`
- `bcrypt!BCryptDestroyKey` at `0x18000ba05`

## pseudocode

```c
void __fastcall CVaultKey::Delete(CVaultKey *this)
{
  void *v2; // rcx
  _BYTE *v3; // rax
  __int64 v4; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    BCryptDestroyKey(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (_BYTE *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    v4 = *((unsigned int *)this + 4);
    if ( *((_DWORD *)this + 4) )
    {
      do
      {
        *v3++ = 0;
        --v4;
      }
      while ( v4 );
    }
    VaultFreeInternal(*((HLOCAL *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000b9f4  push    rbx
0x18000b9f6  sub     rsp, 20h
0x18000b9fa  mov     rbx, rcx
0x18000b9fd  mov     rcx, [rcx]; hKey
0x18000ba00  test    rcx, rcx
0x18000ba03  jz      short loc_18000BA12
0x18000ba05  call    cs:__imp_BCryptDestroyKey
0x18000ba0b  mov     qword ptr [rbx], 0
0x18000ba12  mov     rax, [rbx+8]
0x18000ba16  test    rax, rax
0x18000ba19  jz      short loc_18000BA40
0x18000ba1b  mov     ecx, [rbx+10h]
0x18000ba1e  test    rcx, rcx
0x18000ba21  jz      short loc_18000BA2F
0x18000ba23  mov     byte ptr [rax], 0
0x18000ba26  inc     rax
0x18000ba29  sub     rcx, 1
0x18000ba2d  jnz     short loc_18000BA23
0x18000ba2f  mov     rcx, [rbx+8]; hMem
0x18000ba33  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000ba38  mov     qword ptr [rbx+8], 0
0x18000ba40  add     rsp, 20h
0x18000ba44  pop     rbx
0x18000ba45  retn
```

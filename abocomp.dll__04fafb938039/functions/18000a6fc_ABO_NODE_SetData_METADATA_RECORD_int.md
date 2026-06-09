# ABO_NODE::SetData(_METADATA_RECORD *,int)

- ea: `0x18000a6fc`
- end: `0x18000a82f`
- name: `?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z`
- size: `307`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, struct _METADATA_RECORD *, int)`
- caller_count: `15`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180006040`
- `0x180006f54`
- `0x180007f40`
- `0x180008050`
- `0x18000a838`
- `0x18000a8cc`
- `0x18000bf00`
- `0x18000f390`
- `0x180010880`
- `0x180013570`
- `0x1800153f4`
- `0x180016200`
- `0x18001a690`
- `0x180020890`
- `0x18002ac00`

## callees

- `0x180001f90`
- `0x1800077dc`
- `0x180007d4c`
- `0x18000a584`
- `0x18000a6fc`
- `0x18000fde4`
- `0x18001015c`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a748`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a777`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a790`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a748`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a777`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000a790`

## string_xrefs

- `0x18000a755`: ` An Error (%08x) was detected while generating node (%s). Please verify your configuration files that map to this node.`
- `0x18000a796`: ` Location properties could not read on node (%s) due to error %08x.`

## pseudocode

```c
__int64 __fastcall ABO_NODE::SetData(ABO_NODE *this, struct _METADATA_RECORD *a2, int a3)
{
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  const unsigned __int16 *v9; // rax
  unsigned int v10; // ebx
  const unsigned __int16 *Str; // rax
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rax
  PROPERTY_MAPPING *v15; // [rsp+48h] [rbp+10h] BYREF

  v15 = 0;
  if ( a2 )
  {
    v7 = *((_DWORD *)this + 61);
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          v10 = *((_DWORD *)this + 62);
          Str = STRU::QueryStr((ABO_NODE *)((char *)this + 56));
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L" Not all properties could be set on node (%s) due to error %08x.",
            Str,
            v10);
        }
        else
        {
          v9 = STRU::QueryStr((ABO_NODE *)((char *)this + 56));
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L" An Error (%08x) was detected while generating node (%s). Please verify your configuration files that map to this node.",
            *((unsigned int *)this + 62),
            v9);
        }
      }
      else
      {
        v12 = *((_DWORD *)this + 62);
        v13 = STRU::QueryStr((ABO_NODE *)((char *)this + 56));
        ABO_MAPPER_LOG::WriteLogEntry(
          g_pAboLog,
          L" Location properties could not read on node (%s) due to error %08x.",
          v13,
          v12);
      }
    }
    v6 = PROPERTY_BAG::SetData((ABO_NODE *)((char *)this + 184), a2, a3, &v15);
    if ( v6 >= 0 && !a3 )
    {
      v6 = ABO_NODE::MapSetData(this, v15);
      if ( v6 < 0
        && *((_QWORD *)this + 29)
        && (int)PROPERTY_BAG::DeleteEntry((ABO_NODE *)((char *)this + 184), a2->dwMDIdentifier) >= 0 )
      {
        ABO_NODE::GenerateLocationProperties(this);
      }
    }
    if ( v15 )
      PROPERTY_MAPPING::DereferencePropertyMapping(v15);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a6fc  mov     [rsp+arg_0], rbx
0x18000a701  mov     [rsp+arg_10], rbp
0x18000a706  push    rdi
0x18000a707  push    r14
0x18000a709  push    r15
0x18000a70b  sub     rsp, 20h
0x18000a70f  mov     [rsp+38h+arg_8], 0
0x18000a718  mov     ebp, r8d
0x18000a71b  mov     r14, rdx
0x18000a71e  mov     rdi, rcx
0x18000a721  test    rdx, rdx
0x18000a724  jnz     short loc_18000A730
0x18000a726  mov     ebx, 80070057h
0x18000a72b  jmp     loc_18000A819
0x18000a730  mov     eax, [rcx+0F4h]
0x18000a736  test    eax, eax
0x18000a738  jz      short loc_18000A7AF
0x18000a73a  sub     eax, 1
0x18000a73d  jz      short loc_18000A786
0x18000a73f  cmp     eax, 1
0x18000a742  jz      short loc_18000A76D
0x18000a744  add     rcx, 38h ; '8'
0x18000a748  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000a74e  mov     r8d, [rdi+0F8h]
0x18000a755  lea     rdx, aAnError08xWasD; " An Error (%08x) was detected while gen"...
0x18000a75c  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000a763  mov     r9, rax
0x18000a766  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000a76b  jmp     short loc_18000A7AF
0x18000a76d  mov     ebx, [rcx+0F8h]
0x18000a773  add     rcx, 38h ; '8'
0x18000a777  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000a77d  lea     rdx, aNotAllProperti; " Not all properties could be set on nod"...
0x18000a784  jmp     short loc_18000A79D
0x18000a786  mov     ebx, [rcx+0F8h]
0x18000a78c  add     rcx, 38h ; '8'
0x18000a790  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000a796  lea     rdx, aLocationProper; " Location properties could not read on "...
0x18000a79d  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000a7a4  mov     r9d, ebx
0x18000a7a7  mov     r8, rax
0x18000a7aa  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000a7af  lea     r15, [rdi+0B8h]
0x18000a7b6  mov     r8d, ebp; int
0x18000a7b9  mov     rcx, r15; this
0x18000a7bc  lea     r9, [rsp+38h+arg_8]; struct PROPERTY_ENTRY **
0x18000a7c1  mov     rdx, r14; struct _METADATA_RECORD *
0x18000a7c4  call    ?SetData@PROPERTY_BAG@@QEAAJPEAU_METADATA_RECORD@@HPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::SetData(_METADATA_RECORD *,int,PROPERTY_ENTRY * *)
0x18000a7c9  mov     ebx, eax
0x18000a7cb  test    eax, eax
0x18000a7cd  js      short loc_18000A807
0x18000a7cf  test    ebp, ebp
0x18000a7d1  jnz     short loc_18000A807
0x18000a7d3  mov     rdx, [rsp+38h+arg_8]; struct PROPERTY_ENTRY *
0x18000a7d8  mov     rcx, rdi; this
0x18000a7db  call    ?MapSetData@ABO_NODE@@AEAAJPEAVPROPERTY_ENTRY@@@Z; ABO_NODE::MapSetData(PROPERTY_ENTRY *)
0x18000a7e0  mov     ebx, eax
0x18000a7e2  test    eax, eax
0x18000a7e4  jns     short loc_18000A807
0x18000a7e6  cmp     qword ptr [rdi+0E8h], 0
0x18000a7ee  jz      short loc_18000A807
0x18000a7f0  mov     edx, [r14]; unsigned int
0x18000a7f3  mov     rcx, r15; this
0x18000a7f6  call    ?DeleteEntry@PROPERTY_BAG@@QEAAJK@Z; PROPERTY_BAG::DeleteEntry(ulong)
0x18000a7fb  test    eax, eax
0x18000a7fd  js      short loc_18000A807
0x18000a7ff  mov     rcx, rdi; this
0x18000a802  call    ?GenerateLocationProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateLocationProperties(void)
0x18000a807  cmp     [rsp+38h+arg_8], 0
0x18000a80d  jz      short loc_18000A819
0x18000a80f  mov     rcx, [rsp+38h+arg_8]; this
0x18000a814  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18000a819  mov     rbp, [rsp+38h+arg_10]
0x18000a81e  mov     eax, ebx
0x18000a820  mov     rbx, [rsp+38h+arg_0]
0x18000a825  add     rsp, 20h
0x18000a829  pop     r15
0x18000a82b  pop     r14
0x18000a82d  pop     rdi
0x18000a82e  retn
```

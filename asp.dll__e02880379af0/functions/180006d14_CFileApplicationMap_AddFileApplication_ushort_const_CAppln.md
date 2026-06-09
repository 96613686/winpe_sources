# CFileApplicationMap::AddFileApplication(ushort const *,CAppln *)

- ea: `0x180006d14`
- end: `0x180006e1e`
- name: `?AddFileApplication@CFileApplicationMap@@QEAAJPEBGPEAVCAppln@@@Z`
- size: `266`
- prototype: `int(CFileApplicationMap *__hidden this, const unsigned __int16 *, struct CAppln *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009180`
- `0x180034fc0`

## callees

- `0x180006560`
- `0x180006a94`
- `0x180006b00`
- `0x180006d14`
- `0x180006ed4`
- `0x180007228`
- `0x18001c620`
- `0x180064010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180006e0d`
- `KERNEL32!LeaveCriticalSection` at `0x180006e0d`
- `KERNEL32!EnterCriticalSection` at `0x180006d2a`
- `KERNEL32!EnterCriticalSection` at `0x180006d2a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180006d61`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180006d61`

## pseudocode

```c
__int64 __fastcall CFileApplicationMap::AddFileApplication(
        CFileApplicationMap *this,
        unsigned __int16 *a2,
        struct CAppln *a3)
{
  __int64 v5; // r8
  struct CLinkElem *Elem; // rbx
  struct CLinkElem *v7; // rax
  int v8; // edi
  int v9; // r8d
  int *v10; // rcx
  int v12; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection(&stru_18007A148);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  Elem = CHashTable::FindElem((CHashTable *)&g_FileAppMap, a2, 2 * (int)v5);
  if ( !Elem )
  {
    v7 = (struct CLinkElem *)ALLOC_CACHE_HANDLER::Alloc(CFileApplnList::sm_pach);
    Elem = v7;
    if ( !v7 )
    {
      v8 = -2147024882;
      goto LABEL_9;
    }
    *((_QWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 4) = 0;
    *((_WORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *(_QWORD *)v7 = &CFileApplnList::`vftable';
    *((_QWORD *)v7 + 5) = 0;
    *((_DWORD *)v7 + 12) = 0;
    *((_DWORD *)v7 + 13) = 8;
    *((_QWORD *)v7 + 7) = 0;
    *((_DWORD *)v7 + 16) = 0;
    *((_DWORD *)v7 + 18) = 0;
    v8 = CFileApplnList::Init(v7, a2);
    if ( v8 < 0 )
    {
      (**(void (__fastcall ***)(struct CLinkElem *, __int64))Elem)(Elem, 1);
      goto LABEL_9;
    }
    if ( !CHashTable::AddElem((CHashTable *)&g_FileAppMap, Elem, v9) )
    {
      (**(void (__fastcall ***)(struct CLinkElem *, __int64))Elem)(Elem, 1);
      v8 = -2147467259;
      goto LABEL_9;
    }
  }
  v8 = CFileApplnList::AddApplication(Elem, a3);
  if ( (unsigned int)CPtrArray::Find((struct CAppln *)((char *)a3 + 312), Elem, &v12) == 1 )
    CPtrArray::Insert((CPtrArray *)v10, v10[4], Elem);
LABEL_9:
  LeaveCriticalSection(&stru_18007A148);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006d14  push    rbx
0x180006d16  push    rbp
0x180006d17  push    rsi
0x180006d18  push    rdi
0x180006d19  sub     rsp, 28h
0x180006d1d  lea     rcx, stru_18007A148; lpCriticalSection
0x180006d24  mov     rsi, r8
0x180006d27  mov     rdi, rdx
0x180006d2a  call    cs:__imp_EnterCriticalSection
0x180006d30  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006d34  xor     ebp, ebp
0x180006d36  inc     r8
0x180006d39  cmp     [rdi+r8*2], bp
0x180006d3e  jnz     short loc_180006D36
0x180006d40  add     r8d, r8d; int
0x180006d43  lea     rcx, ?g_FileAppMap@@3VCFileApplicationMap@@A; this
0x180006d4a  mov     rdx, rdi; void *
0x180006d4d  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x180006d52  mov     rbx, rax
0x180006d55  test    rax, rax
0x180006d58  jnz     short loc_180006DD5
0x180006d5a  mov     rcx, cs:?sm_pach@CFileApplnList@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CFileApplnList::sm_pach
0x180006d61  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180006d67  mov     rbx, rax
0x180006d6a  test    rax, rax
0x180006d6d  jz      loc_180026582
0x180006d73  mov     [rax+8], rbp
0x180006d77  mov     rdx, rdi; Source
0x180006d7a  mov     [rax+10h], ebp
0x180006d7d  mov     rcx, rbx; this
0x180006d80  mov     [rax+14h], bp
0x180006d84  mov     [rax+18h], rbp
0x180006d88  mov     [rax+20h], rbp
0x180006d8c  lea     rax, ??_7CFileApplnList@@6B@; const CFileApplnList::`vftable'
0x180006d93  mov     [rbx], rax
0x180006d96  mov     [rbx+28h], rbp
0x180006d9a  mov     [rbx+30h], ebp
0x180006d9d  mov     dword ptr [rbx+34h], 8
0x180006da4  mov     [rbx+38h], rbp
0x180006da8  mov     [rbx+40h], ebp
0x180006dab  mov     [rbx+48h], ebp
0x180006dae  call    ?Init@CFileApplnList@@QEAAJPEBG@Z; CFileApplnList::Init(ushort const *)
0x180006db3  mov     edi, eax
0x180006db5  test    eax, eax
0x180006db7  js      loc_18002654C
0x180006dbd  mov     rdx, rbx; struct CLinkElem *
0x180006dc0  lea     rcx, ?g_FileAppMap@@3VCFileApplicationMap@@A; this
0x180006dc7  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x180006dcc  test    rax, rax
0x180006dcf  jz      loc_180026565
0x180006dd5  mov     rdx, rsi; void *
0x180006dd8  mov     rcx, rbx; this
0x180006ddb  call    ?AddApplication@CFileApplnList@@QEAAJPEAX@Z; CFileApplnList::AddApplication(void *)
0x180006de0  lea     rcx, [rsi+138h]; this
0x180006de7  mov     rdx, rbx; void *
0x180006dea  lea     r8, [rsp+48h+arg_0]; int *
0x180006def  mov     edi, eax
0x180006df1  call    ?Find@CPtrArray@@QEBAJPEAXPEAH@Z; CPtrArray::Find(void *,int *)
0x180006df6  cmp     eax, 1
0x180006df9  jnz     short loc_180006E06
0x180006dfb  mov     edx, [rcx+10h]; int
0x180006dfe  mov     r8, rbx; void *
0x180006e01  call    ?Insert@CPtrArray@@QEAAJHPEAX@Z; CPtrArray::Insert(int,void *)
0x180006e06  lea     rcx, stru_18007A148; lpCriticalSection
0x180006e0d  call    cs:__imp_LeaveCriticalSection
0x180006e13  mov     eax, edi
0x180006e15  add     rsp, 28h
0x180006e19  pop     rdi
0x180006e1a  pop     rsi
0x180006e1b  pop     rbp
0x180006e1c  pop     rbx
0x180006e1d  retn
0x18002654c  mov     rcx, [rbx]
0x18002654f  mov     edx, 1
0x180026554  mov     rax, [rcx]
0x180026557  mov     rcx, rbx
0x18002655a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002655f  nop
0x180026560  jmp     loc_180006E06
0x180026565  mov     rax, [rbx]
0x180026568  mov     edx, 1
0x18002656d  mov     rcx, rbx
0x180026570  mov     rax, [rax]
0x180026573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026578  mov     edi, 80004005h
0x18002657d  jmp     loc_180006E06
0x180026582  mov     edi, 8007000Eh
0x180026587  jmp     loc_180006E06
```

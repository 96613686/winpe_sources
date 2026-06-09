# CAppInfo::~CAppInfo(void)

- ea: `0x180004fc0`
- end: `0x180005191`
- name: `??1CAppInfo@@QEAA@XZ`
- size: `465`
- prototype: `void __fastcall(CAppInfo *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003370`
- `0x180004bf0`
- `0x18000a2cc`
- `0x18000f024`
- `0x18000f8bc`
- `0x1800101fc`
- `0x180010ae8`

## callees

- `0x1800016f4`
- `0x180004fc0`
- `0x18000c480`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000503a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000510d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000511a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005134`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000514e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000515b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005168`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000503a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000510d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000511a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005134`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000514e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000515b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005168`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005175`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004ffa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180004ffa`

## pseudocode

```c
void __fastcall CAppInfo::~CAppInfo(CAppInfo *this)
{
  const WCHAR *v2; // rcx
  __int64 i; // rdi
  __int64 j; // rdi
  _QWORD *v5; // rcx

  if ( (*((_DWORD *)this + 58) || !*((_DWORD *)this + 57)) && (*((_DWORD *)this + 56) & 0x603) == 0x600 )
  {
    v2 = (const WCHAR *)*((_QWORD *)this + 11);
    if ( v2 )
      DeleteFileW(v2);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 86); i = (unsigned int)(i + 1) )
    LocalFree(*(HLOCAL *)(*((_QWORD *)this + 42) + 8 * i));
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 82); j = (unsigned int)(j + 1) )
    LocalFree(*(HLOCAL *)(*((_QWORD *)this + 40) + 8 * j));
  *((_QWORD *)this + 53) = *((_QWORD *)this + 52);
  *((_QWORD *)this + 52) = *((_QWORD *)this + 51);
  while ( 1 )
  {
    v5 = (_QWORD *)*((_QWORD *)this + 52);
    if ( v5 == (_QWORD *)((char *)this + 400) || !v5 )
      break;
    *((_QWORD *)this + 52) = v5[1];
    operator delete(v5, 0x28u);
  }
  LocalFree(*((HLOCAL *)this + 5));
  LocalFree(*((HLOCAL *)this + 9));
  LocalFree(*((HLOCAL *)this + 6));
  LocalFree(*((HLOCAL *)this + 7));
  LocalFree(*((HLOCAL *)this + 8));
  LocalFree(*((HLOCAL *)this + 10));
  LocalFree(*((HLOCAL *)this + 11));
  LocalFree(*((HLOCAL *)this + 12));
  LocalFree(*((HLOCAL *)this + 14));
  LocalFree(*((HLOCAL *)this + 16));
  LocalFree(*((HLOCAL *)this + 17));
  LocalFree(*((HLOCAL *)this + 18));
  LocalFree(*((HLOCAL *)this + 19));
  LocalFree(*((HLOCAL *)this + 30));
  LocalFree(*((HLOCAL *)this + 42));
  LocalFree(*((HLOCAL *)this + 40));
  LocalFree(*((HLOCAL *)this + 44));
  LocalFree(*((HLOCAL *)this + 49));
  LocalFree(*((HLOCAL *)this + 46));
  LocalFree(*((HLOCAL *)this + 55));
  CConflictList::~CConflictList((CAppInfo *)((char *)this + 256));
}

```

## disassembly

```asm
0x180004fc0  mov     [rsp+arg_0], rbx
0x180004fc5  push    rdi
0x180004fc6  sub     rsp, 20h
0x180004fca  cmp     dword ptr [rcx+0E8h], 0
0x180004fd1  mov     rbx, rcx
0x180004fd4  jnz     short loc_180004FDF
0x180004fd6  cmp     dword ptr [rcx+0E4h], 0
0x180004fdd  jnz     short loc_180005000
0x180004fdf  mov     eax, [rcx+0E0h]
0x180004fe5  and     eax, 603h
0x180004fea  cmp     eax, 600h
0x180004fef  jnz     short loc_180005000
0x180004ff1  mov     rcx, [rcx+58h]; lpFileName
0x180004ff5  test    rcx, rcx
0x180004ff8  jz      short loc_180005000
0x180004ffa  call    cs:__imp_DeleteFileW
0x180005000  xor     edi, edi
0x180005002  cmp     [rbx+158h], edi
0x180005008  jbe     short loc_180005025
0x18000500a  mov     rcx, [rbx+150h]
0x180005011  mov     rcx, [rcx+rdi*8]; hMem
0x180005015  call    cs:__imp_LocalFree
0x18000501b  inc     edi
0x18000501d  cmp     edi, [rbx+158h]
0x180005023  jb      short loc_18000500A
0x180005025  xor     edi, edi
0x180005027  cmp     [rbx+148h], edi
0x18000502d  jbe     short loc_18000504A
0x18000502f  mov     rcx, [rbx+140h]
0x180005036  mov     rcx, [rcx+rdi*8]; hMem
0x18000503a  call    cs:__imp_LocalFree
0x180005040  inc     edi
0x180005042  cmp     edi, [rbx+148h]
0x180005048  jb      short loc_18000502F
0x18000504a  mov     rax, [rbx+1A0h]
0x180005051  lea     rdi, [rbx+190h]
0x180005058  mov     [rbx+1A8h], rax
0x18000505f  mov     rax, [rbx+198h]
0x180005066  mov     [rbx+1A0h], rax
0x18000506d  mov     rcx, [rdi+10h]; void *
0x180005071  cmp     rcx, rdi
0x180005074  jz      short loc_180005092
0x180005076  test    rcx, rcx
0x180005079  jz      short loc_180005092
0x18000507b  mov     rax, [rcx+8]
0x18000507f  mov     edx, 28h ; '('; unsigned __int64
0x180005084  mov     [rbx+1A0h], rax
0x18000508b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005090  jmp     short loc_18000506D
0x180005092  mov     rcx, [rbx+28h]; hMem
0x180005096  call    cs:__imp_LocalFree
0x18000509c  mov     rcx, [rbx+48h]; hMem
0x1800050a0  call    cs:__imp_LocalFree
0x1800050a6  mov     rcx, [rbx+30h]; hMem
0x1800050aa  call    cs:__imp_LocalFree
0x1800050b0  mov     rcx, [rbx+38h]; hMem
0x1800050b4  call    cs:__imp_LocalFree
0x1800050ba  mov     rcx, [rbx+40h]; hMem
0x1800050be  call    cs:__imp_LocalFree
0x1800050c4  mov     rcx, [rbx+50h]; hMem
0x1800050c8  call    cs:__imp_LocalFree
0x1800050ce  mov     rcx, [rbx+58h]; hMem
0x1800050d2  call    cs:__imp_LocalFree
0x1800050d8  mov     rcx, [rbx+60h]; hMem
0x1800050dc  call    cs:__imp_LocalFree
0x1800050e2  mov     rcx, [rbx+70h]; hMem
0x1800050e6  call    cs:__imp_LocalFree
0x1800050ec  mov     rcx, [rbx+80h]; hMem
0x1800050f3  call    cs:__imp_LocalFree
0x1800050f9  mov     rcx, [rbx+88h]; hMem
0x180005100  call    cs:__imp_LocalFree
0x180005106  mov     rcx, [rbx+90h]; hMem
0x18000510d  call    cs:__imp_LocalFree
0x180005113  mov     rcx, [rbx+98h]; hMem
0x18000511a  call    cs:__imp_LocalFree
0x180005120  mov     rcx, [rbx+0F0h]; hMem
0x180005127  call    cs:__imp_LocalFree
0x18000512d  mov     rcx, [rbx+150h]; hMem
0x180005134  call    cs:__imp_LocalFree
0x18000513a  mov     rcx, [rbx+140h]; hMem
0x180005141  call    cs:__imp_LocalFree
0x180005147  mov     rcx, [rbx+160h]; hMem
0x18000514e  call    cs:__imp_LocalFree
0x180005154  mov     rcx, [rbx+188h]; hMem
0x18000515b  call    cs:__imp_LocalFree
0x180005161  mov     rcx, [rbx+170h]; hMem
0x180005168  call    cs:__imp_LocalFree
0x18000516e  mov     rcx, [rbx+1B8h]; hMem
0x180005175  call    cs:__imp_LocalFree
0x18000517b  lea     rcx, [rbx+100h]; this
0x180005182  mov     rbx, [rsp+28h+arg_0]
0x180005187  add     rsp, 20h
0x18000518b  pop     rdi
0x18000518c  jmp     ??1CConflictList@@QEAA@XZ; CConflictList::~CConflictList(void)
```

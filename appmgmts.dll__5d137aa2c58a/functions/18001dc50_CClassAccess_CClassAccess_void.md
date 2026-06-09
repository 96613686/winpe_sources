# CClassAccess::~CClassAccess(void)

- ea: `0x18001dc50`
- end: `0x18001dcd6`
- name: `??1CClassAccess@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(HLOCAL *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e600`

## callees

- `0x18001dc50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcc0`

## pseudocode

```c
void __fastcall CClassAccess::~CClassAccess(HLOCAL *this)
{
  __int64 v2; // rsi
  HLOCAL *i; // rbx
  void *v4; // rcx

  *this = &CClassAccess::`vftable';
  LocalFree(this[3]);
  v2 = 0;
  for ( i = this + 1; (unsigned int)v2 < *((_DWORD *)this + 4); v2 = (unsigned int)(v2 + 1) )
  {
    v4 = (void *)**((_QWORD **)*i + v2);
    if ( v4 )
    {
      LocalFree(v4);
      **((_QWORD **)*i + v2) = 0;
    }
    LocalFree(*((HLOCAL *)*i + v2));
    *((_QWORD *)*i + v2) = 0;
  }
  LocalFree(*i);
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x18001dc50  push    rbx
0x18001dc52  push    rbp
0x18001dc53  push    rsi
0x18001dc54  push    rdi
0x18001dc55  sub     rsp, 28h
0x18001dc59  lea     rax, ??_7CClassAccess@@6B@; const CClassAccess::`vftable'
0x18001dc60  mov     rdi, rcx
0x18001dc63  mov     [rcx], rax
0x18001dc66  mov     rcx, [rcx+18h]; hMem
0x18001dc6a  call    cs:__imp_LocalFree
0x18001dc70  xor     esi, esi
0x18001dc72  lea     rbx, [rdi+8]
0x18001dc76  cmp     [rdi+10h], esi
0x18001dc79  jbe     short loc_18001DCBD
0x18001dc7b  mov     rax, [rbx]
0x18001dc7e  mov     rcx, [rax+rsi*8]
0x18001dc82  mov     rcx, [rcx]; hMem
0x18001dc85  test    rcx, rcx
0x18001dc88  jz      short loc_18001DC9E
0x18001dc8a  call    cs:__imp_LocalFree
0x18001dc90  mov     rax, [rbx]
0x18001dc93  mov     rcx, [rax+rsi*8]
0x18001dc97  mov     qword ptr [rcx], 0
0x18001dc9e  mov     rcx, [rbx]
0x18001dca1  mov     rcx, [rcx+rsi*8]; hMem
0x18001dca5  call    cs:__imp_LocalFree
0x18001dcab  mov     rax, [rbx]
0x18001dcae  mov     qword ptr [rax+rsi*8], 0
0x18001dcb6  inc     esi
0x18001dcb8  cmp     esi, [rdi+10h]
0x18001dcbb  jb      short loc_18001DC7B
0x18001dcbd  mov     rcx, [rbx]; hMem
0x18001dcc0  call    cs:__imp_LocalFree
0x18001dcc6  mov     dword ptr [rdi+10h], 0
0x18001dccd  add     rsp, 28h
0x18001dcd1  pop     rdi
0x18001dcd2  pop     rsi
0x18001dcd3  pop     rbp
0x18001dcd4  pop     rbx
0x18001dcd5  retn
```

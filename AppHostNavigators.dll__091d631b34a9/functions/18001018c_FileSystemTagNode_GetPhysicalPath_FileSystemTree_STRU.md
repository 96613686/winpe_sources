# FileSystemTagNode::GetPhysicalPath(FileSystemTree *,STRU &)

- ea: `0x18001018c`
- end: `0x180010299`
- name: `?GetPhysicalPath@FileSystemTagNode@@QEAAXPEAVFileSystemTree@@AEAVSTRU@@@Z`
- size: `269`
- prototype: `void(FileSystemTagNode *__hidden this, struct FileSystemTree *, struct STRU *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800103d0`

## callees

- `0x1800021e0`
- `0x18000ab38`
- `0x180010144`
- `0x18001018c`
- `0x180010530`
- `0x180012f3c`
- `0x1800130a0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FileSystemTagNode::GetPhysicalPath(FileSystemTagNode *this, struct FileSystemTree *a2, struct STRU *a3)
{
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  unsigned int v7; // r9d
  int v8; // eax
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[4]; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 *v12; // [rsp+40h] [rbp-C0h]
  unsigned int v13; // [rsp+48h] [rbp-B8h]
  __int16 v14; // [rsp+50h] [rbp-B0h] BYREF

  **((_WORD **)a3 + 1) = 0;
  *((_DWORD *)a3 + 4) = 0;
  v10[2] = 0;
  v11 = 520;
  v12 = (unsigned __int16 *)&v14;
  v13 = 0;
  v14 = 0;
  (*(void (__fastcall **)(FileSystemTagNode *, struct FileSystemTree *, __int64, _BYTE *))(*(_QWORD *)this + 72LL))(
    this,
    a2,
    2,
    v10);
  v5 = &qword_1800181B0;
  if ( *((_QWORD *)a2 + 3) )
    v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
  v6 = STRU::Copy(a3, v5, 0);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  if ( *((_DWORD *)a3 + 4) )
  {
    Helpers::AppendTrailingSlashIfNotPresent(a3);
    v8 = STRU::Append(a3, v12, v13, v7);
    if ( v8 < 0 )
    {
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
  }
  BUFFER::~BUFFER((BUFFER *)v10);
}

```

## disassembly

```asm
0x18001018c  push    rbp
0x18001018e  push    rbx
0x18001018f  push    rdi
0x180010190  lea     rbp, [rsp-170h]
0x180010198  sub     rsp, 270h
0x18001019f  mov     rax, cs:__security_cookie
0x1800101a6  xor     rax, rsp
0x1800101a9  mov     [rbp+180h+var_20], rax
0x1800101b0  mov     rdi, r8
0x1800101b3  mov     rbx, rdx
0x1800101b6  mov     r10, rcx
0x1800101b9  mov     rcx, [r8+8]
0x1800101bd  xor     eax, eax
0x1800101bf  mov     [rcx], ax
0x1800101c2  mov     [r8+10h], eax
0x1800101c6  mov     [rsp+280h+var_246], al
0x1800101ca  mov     [rsp+280h+var_244], 208h
0x1800101d2  lea     rax, [rsp+280h+var_230]
0x1800101d7  mov     [rsp+280h+var_240], rax
0x1800101dc  mov     [rsp+280h+var_238], 0
0x1800101e4  xor     eax, eax
0x1800101e6  mov     [rsp+280h+var_230], ax
0x1800101eb  mov     rax, [r10]
0x1800101ee  lea     r9, [rsp+280h+var_248]
0x1800101f3  mov     r8d, 2
0x1800101f9  mov     rcx, r10
0x1800101fc  mov     rax, [rax+48h]
0x180010200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010205  lea     rdx, qword_1800181B0
0x18001020c  cmp     qword ptr [rbx+18h], 0
0x180010211  cmovnz  rdx, [rbx+18h]; unsigned __int16 *
0x180010216  xor     r8d, r8d; unsigned int
0x180010219  mov     rcx, rdi; this
0x18001021c  call    ?Copy@STRU@@QEAAJPEBGKK@Z; STRU::Copy(ushort const *,ulong,ulong)
0x180010221  test    eax, eax
0x180010223  jns     short loc_18001023B
0x180010225  mov     [rsp+280h+pExceptionObject], eax
0x180010229  lea     rdx, _TI1J; pThrowInfo
0x180010230  lea     rcx, [rsp+280h+pExceptionObject]; pExceptionObject
0x180010235  call    _CxxThrowException_0
0x18001023b  cmp     dword ptr [rdi+10h], 0
0x18001023f  jz      short loc_180010275
0x180010241  mov     rcx, rdi; struct STRU *
0x180010244  call    ?AppendTrailingSlashIfNotPresent@Helpers@@SAXAEAVSTRU@@@Z; Helpers::AppendTrailingSlashIfNotPresent(STRU &)
0x180010249  mov     r8d, [rsp+280h+var_238]; unsigned int
0x18001024e  mov     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180010253  mov     rcx, rdi; this
0x180010256  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18001025b  test    eax, eax
0x18001025d  jns     short loc_180010275
0x18001025f  mov     [rsp+280h+pExceptionObject], eax
0x180010263  lea     rdx, _TI1J; pThrowInfo
0x18001026a  lea     rcx, [rsp+280h+pExceptionObject]; pExceptionObject
0x18001026f  call    _CxxThrowException_0
0x180010275  lea     rcx, [rsp+280h+var_248]; this
0x18001027a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001027f  mov     rcx, [rbp+180h+var_20]
0x180010286  xor     rcx, rsp; StackCookie
0x180010289  call    __security_check_cookie
0x18001028e  add     rsp, 270h
0x180010295  pop     rdi
0x180010296  pop     rbx
0x180010297  pop     rbp
0x180010298  retn
```

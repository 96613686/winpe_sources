# FileSystemTree::FileSystemTree(ushort const *,ConfigNameTablePair *)

- ea: `0x180005b24`
- end: `0x180005bf5`
- name: `??0FileSystemTree@@QEAA@PEBGPEAVConfigNameTablePair@@@Z`
- size: `209`
- prototype: `FileSystemTree *__fastcall(FileSystemTree *__hidden this, const unsigned __int16 *, struct ConfigNameTablePair *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005fdc`

## callees

- `0x1800042ec`
- `0x180005b24`
- `0x180011240`
- `0x1800126b0`
- `0x180012f3c`

## pseudocode

```c
FileSystemTree *__fastcall FileSystemTree::FileSystemTree(
        FileSystemTree *this,
        const unsigned __int16 *a2,
        struct ConfigNameTablePair *a3)
{
  String *v4; // rcx
  const unsigned __int16 *v5; // r9
  int v6; // eax
  int pExceptionObject; // [rsp+48h] [rbp+20h] BYREF

  NavigationTreeBase::NavigationTreeBase(this, a3);
  *(_QWORD *)v4 = &FileSystemTree::`vftable';
  v4 = (String *)((char *)v4 + 24);
  *(_QWORD *)v4 = 0;
  *((_DWORD *)this + 10) = -1;
  *((_DWORD *)this + 11) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 4) = &FileSystemRootNode::`vftable';
  v6 = String::Initialize(v4, v5);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  NavigationNodeBase::Initialize((FileSystemTree *)((char *)this + 32), this, &qword_1800181B0);
  *((_DWORD *)this + 10) = 0;
  return this;
}

```

## disassembly

```asm
0x180005b24  mov     [rsp+arg_8], rbx
0x180005b29  mov     [rsp+arg_0], rcx
0x180005b2e  push    rdi
0x180005b2f  sub     rsp, 20h
0x180005b33  mov     r9, rdx
0x180005b36  mov     rdi, rcx
0x180005b39  mov     rdx, r8; struct ConfigNameTablePair *
0x180005b3c  call    ??0NavigationTreeBase@@QEAA@PEAVConfigNameTablePair@@@Z; NavigationTreeBase::NavigationTreeBase(ConfigNameTablePair *)
0x180005b41  nop
0x180005b42  lea     rax, ??_7FileSystemTree@@6B@; const FileSystemTree::`vftable'
0x180005b49  mov     [rcx], rax
0x180005b4c  add     rcx, 18h; this
0x180005b50  mov     qword ptr [rcx], 0
0x180005b57  mov     dword ptr [rdi+28h], 0FFFFFFFFh
0x180005b5e  mov     dword ptr [rdi+2Ch], 0
0x180005b65  mov     qword ptr [rdi+30h], 0
0x180005b6d  mov     qword ptr [rdi+38h], 0
0x180005b75  mov     qword ptr [rdi+40h], 0
0x180005b7d  lea     rax, [rdi+48h]
0x180005b81  mov     [rax+8], rax
0x180005b85  mov     [rax], rax
0x180005b88  mov     qword ptr [rdi+60h], 0
0x180005b90  mov     qword ptr [rdi+58h], 0
0x180005b98  mov     qword ptr [rdi+68h], 0
0x180005ba0  lea     rax, ??_7FileSystemRootNode@@6B@; const FileSystemRootNode::`vftable'
0x180005ba7  mov     [rdi+20h], rax
0x180005bab  mov     rdx, r9; unsigned __int16 *
0x180005bae  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x180005bb3  test    eax, eax
0x180005bb5  jns     short loc_180005BCD
0x180005bb7  mov     [rsp+28h+pExceptionObject], eax
0x180005bbb  lea     rdx, _TI1J; pThrowInfo
0x180005bc2  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005bc7  call    _CxxThrowException_0
0x180005bcd  lea     r8, qword_1800181B0; unsigned __int16 *
0x180005bd4  mov     rdx, rdi; struct NavigationTreeBase *
0x180005bd7  lea     rcx, [rdi+20h]; this
0x180005bdb  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x180005be0  mov     dword ptr [rdi+28h], 0
0x180005be7  mov     rax, rdi
0x180005bea  mov     rbx, [rsp+28h+arg_8]
0x180005bef  add     rsp, 20h
0x180005bf3  pop     rdi
0x180005bf4  retn
```

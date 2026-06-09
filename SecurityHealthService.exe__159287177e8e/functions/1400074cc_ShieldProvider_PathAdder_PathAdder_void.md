# ShieldProvider::PathAdder::~PathAdder(void)

- ea: `0x1400074cc`
- end: `0x140007532`
- name: `??1PathAdder@ShieldProvider@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(ShieldProvider::PathAdder *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003d24`

## callees

- `0x1400074cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!RemoveDllDirectory` at `0x140007503`
- `api-ms-win-core-libraryloader-l1-2-0!RemoveDllDirectory` at `0x140007503`

## pseudocode

```c
void __fastcall ShieldProvider::PathAdder::~PathAdder(ShieldProvider::PathAdder *this)
{
  __int64 v2; // rdx
  void *v3; // rcx

  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 4) + 4LL) - 32) = &ShieldProvider::PathAdder::`vftable';
  v2 = *(int *)(*((_QWORD *)this - 4) + 4LL);
  *(_DWORD *)((char *)this + v2 - 36) = v2 - 32;
  v3 = (void *)*((_QWORD *)this - 2);
  if ( v3 )
    RemoveDllDirectory(v3);
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 4) + 4LL) - 32) = &CRefCountedBaseX::`vftable';
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this - 4) + 4LL) - 36) = *(_DWORD *)(*((_QWORD *)this - 4) + 4LL) - 24;
}

```

## disassembly

```asm
0x1400074cc  push    rbx
0x1400074ce  sub     rsp, 20h
0x1400074d2  mov     rax, [rcx-20h]
0x1400074d6  mov     rbx, rcx
0x1400074d9  movsxd  rdx, dword ptr [rax+4]
0x1400074dd  lea     rax, ??_7PathAdder@ShieldProvider@@6B@; const ShieldProvider::PathAdder::`vftable'
0x1400074e4  mov     [rdx+rcx-20h], rax
0x1400074e9  mov     rax, [rcx-20h]
0x1400074ed  movsxd  rdx, dword ptr [rax+4]
0x1400074f1  lea     r8d, [rdx-20h]
0x1400074f5  mov     [rdx+rcx-24h], r8d
0x1400074fa  mov     rcx, [rcx-10h]; Cookie
0x1400074fe  test    rcx, rcx
0x140007501  jz      short loc_140007509
0x140007503  call    cs:__imp_RemoveDllDirectory
0x140007509  mov     rax, [rbx-20h]
0x14000750d  movsxd  rcx, dword ptr [rax+4]
0x140007511  lea     rax, ??_7CRefCountedBaseX@@6B@; const CRefCountedBaseX::`vftable'
0x140007518  mov     [rcx+rbx-20h], rax
0x14000751d  mov     rax, [rbx-20h]
0x140007521  movsxd  rcx, dword ptr [rax+4]
0x140007525  lea     edx, [rcx-18h]
0x140007528  mov     [rcx+rbx-24h], edx
0x14000752c  add     rsp, 20h
0x140007530  pop     rbx
0x140007531  retn
```

# JDictsDictionaryManifest::~JDictsDictionaryManifest(void)

- ea: `0x1800164c4`
- end: `0x180016563`
- name: `??1JDictsDictionaryManifest@@EEAA@XZ`
- size: `159`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800166c0`

## callees

- `0x1800164c4`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800164e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016509`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800164e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016509`

## pseudocode

```c
void __fastcall JDictsDictionaryManifest::~JDictsDictionaryManifest(void **this)
{
  void *v2; // rcx
  void *v3; // rcx

  *this = &JDictsDictionaryManifest::`vftable';
  if ( (unsigned __int64)this[11] >= 8 )
    operator delete(this[8]);
  this[11] = (void *)7;
  this[10] = 0;
  *((_WORD *)this + 32) = 0;
  if ( (unsigned __int64)this[7] >= 8 )
    operator delete(this[4]);
  this[7] = (void *)7;
  this[6] = 0;
  *((_WORD *)this + 16) = 0;
  v2 = this[3];
  if ( v2 )
  {
    this[3] = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = this[2];
  if ( v3 )
  {
    this[2] = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x1800164c4  push    rbx
0x1800164c6  sub     rsp, 20h
0x1800164ca  mov     rbx, rcx
0x1800164cd  lea     rax, ??_7JDictsDictionaryManifest@@6B@; const JDictsDictionaryManifest::`vftable'
0x1800164d4  mov     [rcx], rax
0x1800164d7  cmp     qword ptr [rcx+58h], 8
0x1800164dc  jb      short loc_1800164E8
0x1800164de  mov     rcx, [rcx+40h]
0x1800164e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800164e8  mov     qword ptr [rbx+58h], 7
0x1800164f0  mov     qword ptr [rbx+50h], 0
0x1800164f8  xor     eax, eax
0x1800164fa  mov     [rbx+40h], ax
0x1800164fe  cmp     qword ptr [rbx+38h], 8
0x180016503  jb      short loc_18001650F
0x180016505  mov     rcx, [rbx+20h]
0x180016509  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001650f  mov     qword ptr [rbx+38h], 7
0x180016517  mov     qword ptr [rbx+30h], 0
0x18001651f  xor     eax, eax
0x180016521  mov     [rbx+20h], ax
0x180016525  mov     rcx, [rbx+18h]
0x180016529  test    rcx, rcx
0x18001652c  jz      short loc_18001653F
0x18001652e  mov     [rbx+18h], rax
0x180016532  mov     rax, [rcx]
0x180016535  mov     rax, [rax+10h]
0x180016539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001653e  nop
0x18001653f  mov     rcx, [rbx+10h]
0x180016543  test    rcx, rcx
0x180016546  jz      short loc_18001655D
0x180016548  mov     qword ptr [rbx+10h], 0
0x180016550  mov     rax, [rcx]
0x180016553  mov     rax, [rax+10h]
0x180016557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001655c  nop
0x18001655d  add     rsp, 20h
0x180016561  pop     rbx
0x180016562  retn
```

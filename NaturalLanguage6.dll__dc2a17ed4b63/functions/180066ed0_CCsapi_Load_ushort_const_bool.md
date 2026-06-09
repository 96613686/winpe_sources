# CCsapi::Load(ushort const *,bool)

- ea: `0x180066ed0`
- end: `0x180066f27`
- name: `?Load@CCsapi@@UEAAHPEBG_N@Z`
- size: `87`
- prototype: `int(CCsapi *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180066ed0`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180066ef2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180066ef2`

## pseudocode

```c
__int64 __fastcall CCsapi::Load(CCsapi *this, const unsigned __int16 *a2, char a3)
{
  HMODULE LibraryW; // rax
  __int64 v6; // rdx

  if ( !a2 || *((_QWORD *)this + 30) )
    return 0;
  LibraryW = LoadLibraryW(a2);
  LOBYTE(v6) = a3;
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 30) = LibraryW;
  return (*(__int64 (__fastcall **)(CCsapi *, __int64))(*(_QWORD *)this + 8LL))(this, v6);
}

```

## disassembly

```asm
0x180066ed0  mov     [rsp+arg_0], rbx
0x180066ed5  push    rdi
0x180066ed6  sub     rsp, 20h
0x180066eda  mov     dil, r8b
0x180066edd  mov     rbx, rcx
0x180066ee0  test    rdx, rdx
0x180066ee3  jz      short loc_180066F1A
0x180066ee5  cmp     qword ptr [rcx+0F0h], 0
0x180066eed  jnz     short loc_180066F1A
0x180066eef  mov     rcx, rdx; lpLibFileName
0x180066ef2  call    cs:__imp_LoadLibraryW
0x180066ef8  mov     dl, dil
0x180066efb  mov     byte ptr [rbx+0F8h], 0
0x180066f02  mov     [rbx+0F0h], rax
0x180066f09  mov     rcx, rbx
0x180066f0c  mov     rax, [rbx]
0x180066f0f  mov     rax, [rax+8]
0x180066f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f18  jmp     short loc_180066F1C
0x180066f1a  xor     eax, eax
0x180066f1c  mov     rbx, [rsp+28h+arg_0]
0x180066f21  add     rsp, 20h
0x180066f25  pop     rdi
0x180066f26  retn
```

# CompactDirPath(DirQueItem &,ushort const *,ushort const *,DirQueItem &)

- ea: `0x180020bc0`
- end: `0x180020c28`
- name: `?CompactDirPath@@YAJAEAUDirQueItem@@PEBG10@Z`
- size: `104`
- prototype: `__int64 __fastcall(struct DirQueItem *, const unsigned __int16 *, const unsigned __int16 *, struct DirQueItem *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022ab4`

## callees

- `0x1800152d4`
- `0x18001f334`
- `0x18001f66c`
- `0x180020bc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180020c10`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180020c10`

## pseudocode

```c
__int64 __fastcall CompactDirPath(
        struct DirQueItem *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct DirQueItem *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 *v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = 0;
  v5 = CompactFullPath((const unsigned __int16 *)a1, a2, a3, &v11);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = _o_wcscpy_s(a4, 260, v11);
    return HrFromErrno(v8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v5,
      v9);
    return v6;
  }
}

```

## disassembly

```asm
0x180020bc0  mov     [rsp+arg_8], rbx
0x180020bc5  push    rdi; int
0x180020bc6  sub     rsp, 20h
0x180020bca  mov     rdi, r9
0x180020bcd  mov     [rsp+28h+arg_0], 0
0x180020bd6  lea     r9, [rsp+28h+arg_0]; unsigned __int16 **
0x180020bdb  call    ?CompactFullPath@@YAJPEBG00PEAPEAG@Z; CompactFullPath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180020be0  mov     ebx, eax
0x180020be2  test    eax, eax
0x180020be4  jns     short loc_180020C03
0x180020be6  mov     rcx, [rsp+28h]; this
0x180020beb  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180020bf2  mov     r9d, eax; char *
0x180020bf5  mov     edx, 355h; void *
0x180020bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bff  mov     eax, ebx
0x180020c01  jmp     short loc_180020C1D
0x180020c03  mov     r8, [rsp+28h+arg_0]
0x180020c08  mov     edx, 104h
0x180020c0d  mov     rcx, rdi
0x180020c10  call    cs:__imp__o_wcscpy_s
0x180020c16  mov     ecx, eax; int
0x180020c18  call    ?HrFromErrno@@YAJH@Z; HrFromErrno(int)
0x180020c1d  mov     rbx, [rsp+28h+arg_8]
0x180020c22  add     rsp, 20h
0x180020c26  pop     rdi
0x180020c27  retn
```

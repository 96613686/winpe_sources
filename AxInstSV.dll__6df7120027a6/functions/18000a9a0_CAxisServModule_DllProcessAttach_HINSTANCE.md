# CAxisServModule::DllProcessAttach(HINSTANCE__ *)

- ea: `0x18000a9a0`
- end: `0x18000aa47`
- name: `?DllProcessAttach@CAxisServModule@@QEAAXPEAUHINSTANCE__@@@Z`
- size: `167`
- prototype: `void __fastcall(CAxisServModule *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001250`

## callees

- `0x18000725c`
- `0x18000a9a0`
- `0x180015010`

## string_xrefs

- `0x18000aa20`: `CAxisServModule::DllProcessAttach hinst= %p. hr=%!HRESULT!\n`

## pseudocode

```c
void __fastcall CAxisServModule::DllProcessAttach(CAxisServModule *this, HINSTANCE a2)
{
  void (__fastcall **v3)(CAxisServModule *); // rbx
  __int64 *v4; // rbx
  unsigned __int64 v5; // rax
  int v6; // [rsp+28h] [rbp-10h]

  v3 = (void (__fastcall **)(CAxisServModule *))&off_180021000;
  if ( &off_180021000 != (_UNKNOWN *)-1LL )
  {
    qword_180021638 = (ATL::_ATL_OBJMAP_ENTRY30 *)&off_180021000;
    if ( off_180021000 )
    {
      do
      {
        LOBYTE(this) = 1;
        v3[8](this);
        v3 += 9;
      }
      while ( *v3 );
    }
  }
  v4 = off_1800210B0[0];
  v5 = *(_QWORD *)&off_1800210B8;
  while ( (unsigned __int64)v4 < v5 )
  {
    if ( *v4 )
    {
      LOBYTE(this) = 1;
      (*(void (__fastcall **)(CAxisServModule *))(*v4 + 64))(this);
      v5 = *(_QWORD *)&off_1800210B8;
    }
    ++v4;
  }
  v6 = 0;
  AxISEvents::DebugMsg(
    (AxISEvents *)&qword_180021AD8,
    8u,
    5u,
    L"CAxisServModule::DllProcessAttach hinst= %p. hr=%!HRESULT!\n",
    a2,
    v6);
}

```

## disassembly

```asm
0x18000a9a0  mov     [rsp+arg_0], rbx
0x18000a9a5  push    rdi
0x18000a9a6  sub     rsp, 30h
0x18000a9aa  mov     rdi, rdx
0x18000a9ad  lea     rbx, off_180021000
0x18000a9b4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a9b8  jz      short loc_18000A9E0
0x18000a9ba  mov     cs:qword_180021638, rbx
0x18000a9c1  cmp     cs:off_180021000, 0
0x18000a9c9  jz      short loc_18000A9E0
0x18000a9cb  mov     cl, 1
0x18000a9cd  mov     rax, [rbx+40h]
0x18000a9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d6  lea     rbx, [rbx+48h]
0x18000a9da  cmp     qword ptr [rbx], 0
0x18000a9de  jnz     short loc_18000A9CB
0x18000a9e0  mov     rbx, cs:off_1800210B0
0x18000a9e7  mov     rax, cs:off_1800210B8
0x18000a9ee  jmp     short loc_18000AA0E
0x18000a9f0  mov     rdx, [rbx]
0x18000a9f3  test    rdx, rdx
0x18000a9f6  jz      short loc_18000AA0A
0x18000a9f8  mov     cl, 1
0x18000a9fa  mov     rax, [rdx+40h]
0x18000a9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa03  mov     rax, cs:off_1800210B8
0x18000aa0a  add     rbx, 8
0x18000aa0e  cmp     rbx, rax
0x18000aa11  jb      short loc_18000A9F0
0x18000aa13  mov     [rsp+38h+var_10], 0
0x18000aa1b  mov     [rsp+38h+var_18], rdi
0x18000aa20  lea     r9, aCaxisservmodul_2; "CAxisServModule::DllProcessAttach hinst"...
0x18000aa27  mov     edx, 8; unsigned int
0x18000aa2c  lea     r8d, [rdx-3]; unsigned __int8
0x18000aa30  lea     rcx, qword_180021AD8; this
0x18000aa37  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000aa3c  mov     rbx, [rsp+38h+arg_0]
0x18000aa41  add     rsp, 30h
0x18000aa45  pop     rdi
0x18000aa46  retn
```

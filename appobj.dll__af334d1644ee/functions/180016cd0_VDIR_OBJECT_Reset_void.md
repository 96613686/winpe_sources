# VDIR_OBJECT::Reset(void)

- ea: `0x180016cd0`
- end: `0x180016d63`
- name: `?Reset@VDIR_OBJECT@@QEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(VDIR_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015398`

## callees

- `0x180002e90`
- `0x180005ba8`
- `0x180016cd0`

## string_xrefs

- `0x180016ce7`: `physicalPath`

## pseudocode

```c
signed int __fastcall VDIR_OBJECT::Reset(VDIR_OBJECT *this)
{
  signed int result; // eax

  result = COMMAND_OBJECT::AddAttribute(this, L"physicalPath", &Str);
  if ( result >= 0 )
  {
    result = COMMAND_OBJECT::AddAttribute(this, L"path", &Str);
    if ( result >= 0 )
    {
      result = STRU::Copy((VDIR_OBJECT *)((char *)this + 16), (const unsigned __int8 *)&Str);
      if ( result >= 0 )
      {
        result = COMMAND_OBJECT::AddAttribute(this, L"APP.NAME", &Str);
        if ( result >= 0 )
        {
          result = COMMAND_OBJECT::AddAttribute(this, L"VDIR.NAME", &Str);
          if ( result >= 0 )
            return STRU::Copy((VDIR_OBJECT *)((char *)this + 128), (const unsigned __int8 *)&Str);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016cd0  mov     [rsp+arg_0], rbx
0x180016cd5  push    rdi
0x180016cd6  sub     rsp, 20h
0x180016cda  lea     rdi, Str
0x180016ce1  mov     rbx, rcx
0x180016ce4  mov     r8, rdi; unsigned __int16 *
0x180016ce7  lea     rdx, aPhysicalpath; "physicalPath"
0x180016cee  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180016cf3  test    eax, eax
0x180016cf5  js      short loc_180016D58
0x180016cf7  mov     r8, rdi; unsigned __int16 *
0x180016cfa  lea     rdx, aPath_1; "path"
0x180016d01  mov     rcx, rbx; this
0x180016d04  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180016d09  test    eax, eax
0x180016d0b  js      short loc_180016D58
0x180016d0d  lea     rcx, [rbx+10h]; this
0x180016d11  mov     rdx, rdi; unsigned __int16 *
0x180016d14  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016d19  test    eax, eax
0x180016d1b  js      short loc_180016D58
0x180016d1d  mov     r8, rdi; unsigned __int16 *
0x180016d20  lea     rdx, aAppName_0; "APP.NAME"
0x180016d27  mov     rcx, rbx; this
0x180016d2a  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180016d2f  test    eax, eax
0x180016d31  js      short loc_180016D58
0x180016d33  mov     r8, rdi; unsigned __int16 *
0x180016d36  lea     rdx, aVdirName; "VDIR.NAME"
0x180016d3d  mov     rcx, rbx; this
0x180016d40  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180016d45  test    eax, eax
0x180016d47  js      short loc_180016D58
0x180016d49  lea     rcx, [rbx+80h]; this
0x180016d50  mov     rdx, rdi; unsigned __int16 *
0x180016d53  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016d58  mov     rbx, [rsp+28h+arg_0]
0x180016d5d  add     rsp, 20h
0x180016d61  pop     rdi
0x180016d62  retn
```

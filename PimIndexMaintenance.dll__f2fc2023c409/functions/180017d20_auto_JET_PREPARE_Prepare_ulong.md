# auto_JET_PREPARE::Prepare(ulong)

- ea: `0x180017d20`
- end: `0x180017d6d`
- name: `?Prepare@auto_JET_PREPARE@@QEAAJK@Z`
- size: `77`
- prototype: `int(auto_JET_PREPARE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800180c4`
- `0x180019254`

## callees

- `0x1800086a0`
- `0x180017d20`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180017d51`
- `ESENT!JetPrepareUpdate` at `0x180017d51`

## string_xrefs

- `0x180017d3b`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
JET_ERR __fastcall auto_JET_PREPARE::Prepare(JET_TABLEID *this, unsigned int a2)
{
  JET_ERR result; // eax

  if ( *((_DWORD *)this + 4) )
    Log_AssertionEvent(this, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 522);
  result = JetPrepareUpdate(*this, this[1], a2);
  if ( !result )
    *((_DWORD *)this + 4) = 1;
  return result;
}

```

## disassembly

```asm
0x180017d20  mov     [rsp+arg_0], rbx
0x180017d25  push    rdi
0x180017d26  sub     rsp, 20h
0x180017d2a  cmp     dword ptr [rcx+10h], 0
0x180017d2e  mov     edi, edx
0x180017d30  mov     rbx, rcx
0x180017d33  jz      short loc_180017D47
0x180017d35  mov     r8d, 20Ah
0x180017d3b  lea     rdx, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180017d42  call    Log_AssertionEvent
0x180017d47  mov     rdx, [rbx+8]; tableid
0x180017d4b  mov     r8d, edi; prep
0x180017d4e  mov     rcx, [rbx]; sesid
0x180017d51  call    cs:__imp_JetPrepareUpdate
0x180017d57  test    eax, eax
0x180017d59  jnz     short loc_180017D62
0x180017d5b  mov     dword ptr [rbx+10h], 1
0x180017d62  mov     rbx, [rsp+28h+arg_0]
0x180017d67  add     rsp, 20h
0x180017d6b  pop     rdi
0x180017d6c  retn
```

# auto_JET_TABLEID::close(void)

- ea: `0x18001968c`
- end: `0x1800196f8`
- name: `?close@auto_JET_TABLEID@@QEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(JET_SESID *this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001673c`
- `0x180016828`
- `0x1800168e8`
- `0x180018778`
- `0x180018be4`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x18001968c`

## import_xrefs

- `ESENT!JetCloseTable` at `0x1800196bb`
- `ESENT!JetCloseTable` at `0x1800196bb`

## string_xrefs

- `0x1800196a8`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x1800196d2`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
__int64 __fastcall auto_JET_TABLEID::close(JET_SESID *this)
{
  JET_ERR v2; // eax
  unsigned int HresultFromJetError; // ebx

  if ( this[1] != -1 )
  {
    if ( *this == -1 )
      Log_AssertionEvent(this, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 268);
    v2 = JetCloseTable(*this, this[1]);
    if ( v2 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v2);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h",
        269);
      return HresultFromJetError;
    }
    this[1] = -1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001968c  push    rbx
0x18001968e  sub     rsp, 30h
0x180019692  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180019697  mov     rbx, rcx
0x18001969a  jz      short loc_1800196F0
0x18001969c  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800196a0  jnz     short loc_1800196B4
0x1800196a2  mov     r8d, 10Ch
0x1800196a8  lea     rdx, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800196af  call    Log_AssertionEvent
0x1800196b4  mov     rdx, [rbx+8]; tableid
0x1800196b8  mov     rcx, [rbx]; sesid
0x1800196bb  call    cs:__imp_JetCloseTable
0x1800196c1  test    eax, eax
0x1800196c3  jns     short loc_1800196E8
0x1800196c5  mov     ecx, eax; int
0x1800196c7  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800196cc  mov     r9d, 10Dh
0x1800196d2  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800196d9  xor     edx, edx
0x1800196db  mov     ecx, eax
0x1800196dd  mov     ebx, eax
0x1800196df  call    Log_HREvent
0x1800196e4  mov     eax, ebx
0x1800196e6  jmp     short loc_1800196F2
0x1800196e8  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800196f0  xor     eax, eax
0x1800196f2  add     rsp, 30h
0x1800196f6  pop     rbx
0x1800196f7  retn
```

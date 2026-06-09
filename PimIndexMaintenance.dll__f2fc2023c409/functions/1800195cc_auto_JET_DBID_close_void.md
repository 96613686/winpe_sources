# auto_JET_DBID::close(void)

- ea: `0x1800195cc`
- end: `0x180019635`
- name: `?close@auto_JET_DBID@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(JET_DBID *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001673c`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x1800195cc`

## import_xrefs

- `ESENT!JetCloseDatabase` at `0x180019601`
- `ESENT!JetCloseDatabase` at `0x180019601`

## string_xrefs

- `0x1800195e7`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`
- `0x180019614`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
void __fastcall auto_JET_DBID::close(JET_DBID *this)
{
  JET_DBID v2; // edx
  JET_ERR v3; // eax
  unsigned int HresultFromJetError; // eax

  if ( this[2] != -1 && *(_QWORD *)this == -1 )
    Log_AssertionEvent(this, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h", 220);
  v2 = this[2];
  if ( v2 != -1 )
  {
    v3 = JetCloseDatabase(*(_QWORD *)this, v2, 0);
    if ( v3 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v3);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h",
        223);
    }
    this[2] = -1;
  }
}

```

## disassembly

```asm
0x1800195cc  push    rbx
0x1800195ce  sub     rsp, 30h
0x1800195d2  cmp     dword ptr [rcx+8], 0FFFFFFFFh
0x1800195d6  mov     rbx, rcx
0x1800195d9  jz      short loc_1800195F3
0x1800195db  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800195df  jnz     short loc_1800195F3
0x1800195e1  mov     r8d, 0DCh
0x1800195e7  lea     rdx, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800195ee  call    Log_AssertionEvent
0x1800195f3  mov     edx, [rbx+8]; dbid
0x1800195f6  cmp     edx, 0FFFFFFFFh
0x1800195f9  jz      short loc_18001962F
0x1800195fb  mov     rcx, [rbx]; sesid
0x1800195fe  xor     r8d, r8d; grbit
0x180019601  call    cs:__imp_JetCloseDatabase
0x180019607  test    eax, eax
0x180019609  jns     short loc_180019628
0x18001960b  mov     ecx, eax; int
0x18001960d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180019612  mov     ecx, eax
0x180019614  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18001961b  mov     r9d, 0DFh
0x180019621  xor     edx, edx
0x180019623  call    Log_HREvent
0x180019628  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18001962f  add     rsp, 30h
0x180019633  pop     rbx
0x180019634  retn
```

# auto_JET_SESID::close(void)

- ea: `0x18001963c`
- end: `0x180019686`
- name: `?close@auto_JET_SESID@@QEAAXXZ`
- size: `74`
- prototype: `void __fastcall(auto_JET_SESID *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001673c`

## callees

- `0x180002da8`
- `0x180010638`
- `0x18001963c`

## import_xrefs

- `ESENT!JetEndSession` at `0x180019651`
- `ESENT!JetEndSession` at `0x180019651`

## string_xrefs

- `0x180019664`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\JetInterop.h`

## pseudocode

```c
void __fastcall auto_JET_SESID::close(auto_JET_SESID *this)
{
  JET_SESID v2; // rcx
  JET_ERR v3; // eax
  unsigned int HresultFromJetError; // eax

  v2 = *((_QWORD *)this + 1);
  if ( v2 != -1 )
  {
    v3 = JetEndSession(v2, 0);
    if ( v3 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v3);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\JetInterop.h",
        183);
    }
    *((_QWORD *)this + 1) = -1;
  }
}

```

## disassembly

```asm
0x18001963c  push    rbx
0x18001963e  sub     rsp, 30h
0x180019642  mov     rbx, rcx
0x180019645  mov     rcx, [rcx+8]; sesid
0x180019649  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001964d  jz      short loc_180019680
0x18001964f  xor     edx, edx; grbit
0x180019651  call    cs:__imp_JetEndSession
0x180019657  test    eax, eax
0x180019659  jns     short loc_180019678
0x18001965b  mov     ecx, eax; int
0x18001965d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180019662  mov     ecx, eax
0x180019664  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18001966b  mov     r9d, 0B7h
0x180019671  xor     edx, edx
0x180019673  call    Log_HREvent
0x180019678  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180019680  add     rsp, 30h
0x180019684  pop     rbx
0x180019685  retn
```

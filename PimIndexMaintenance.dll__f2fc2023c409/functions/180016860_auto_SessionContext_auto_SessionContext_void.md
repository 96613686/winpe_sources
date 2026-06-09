# auto_SessionContext::~auto_SessionContext(void)

- ea: `0x180016860`
- end: `0x1800168a9`
- name: `??1auto_SessionContext@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(auto_SessionContext *__hidden this)`
- caller_count: `20`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800168e8`
- `0x180016a70`
- `0x180016b68`
- `0x180016db0`
- `0x180016f5c`
- `0x18001706c`
- `0x1800173c4`
- `0x180017638`
- `0x1800177fc`
- `0x180017e2c`
- `0x180017ec8`
- `0x180017f74`
- `0x1800180c4`
- `0x1800183b4`
- `0x180018630`
- `0x180018778`
- `0x180018be4`
- `0x180018c98`
- `0x180018f58`
- `0x180019254`

## callees

- `0x180002da8`
- `0x180010638`
- `0x180016860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800168a2`
- `ESENT!JetResetSessionContext` at `0x180016872`
- `ESENT!JetResetSessionContext` at `0x180016872`

## string_xrefs

- `0x180016885`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
void __fastcall auto_SessionContext::~auto_SessionContext(auto_SessionContext *this)
{
  JET_ERR v2; // eax
  unsigned int HresultFromJetError; // eax

  if ( *((_DWORD *)this + 2) )
  {
    v2 = JetResetSessionContext(*(_QWORD *)this);
    if ( v2 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v2);
      Log_HREvent(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        58);
    }
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 2));
}

```

## disassembly

```asm
0x180016860  push    rbx
0x180016862  sub     rsp, 30h
0x180016866  cmp     dword ptr [rcx+8], 0
0x18001686a  mov     rbx, rcx
0x18001686d  jz      short loc_180016899
0x18001686f  mov     rcx, [rcx]; sesid
0x180016872  call    cs:__imp_JetResetSessionContext
0x180016878  test    eax, eax
0x18001687a  jns     short loc_180016899
0x18001687c  mov     ecx, eax; int
0x18001687e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180016883  mov     ecx, eax
0x180016885  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001688c  mov     r9d, 3Ah ; ':'
0x180016892  xor     edx, edx
0x180016894  call    Log_HREvent
0x180016899  mov     rcx, [rbx+10h]
0x18001689d  add     rsp, 30h
0x1800168a1  pop     rbx
0x1800168a2  jmp     cs:__imp_LeaveCriticalSection
```

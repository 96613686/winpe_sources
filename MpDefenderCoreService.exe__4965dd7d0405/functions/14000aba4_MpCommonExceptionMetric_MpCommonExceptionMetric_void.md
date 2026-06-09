# MpCommonExceptionMetric::~MpCommonExceptionMetric(void)

- ea: `0x14000aba4`
- end: `0x14000ac23`
- name: `??1MpCommonExceptionMetric@@AEAA@XZ`
- size: `127`
- prototype: `void __fastcall(MpCommonExceptionMetric *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140170ce0`

## callees

- `0x14000aba4`
- `0x14000afbc`

## import_xrefs

- `KERNEL32!RemoveVectoredExceptionHandler` at `0x14000abb9`
- `KERNEL32!RemoveVectoredExceptionHandler` at `0x14000abb9`
- `ADVAPI32!EventUnregister` at `0x14000ac10`
- `ADVAPI32!EventUnregister` at `0x14000ac10`

## pseudocode

```c
void __fastcall MpCommonExceptionMetric::~MpCommonExceptionMetric(MpCommonExceptionMetric *this)
{
  void *v2; // rcx
  REGHANDLE v3; // rcx

  v2 = (void *)*((_QWORD *)this + 66);
  if ( v2 )
  {
    RemoveVectoredExceptionHandler(v2);
    *((_QWORD *)this + 66) = 0;
  }
  if ( *((_BYTE *)this + 522) )
  {
    if ( !*((_BYTE *)this + 523) )
      MpCommonExceptionMetric::WriteExceptionMetric(this, 0, L"NormalExit", &Src);
    v3 = RegHandle;
    RegHandle = 0;
    dword_1401D8000 = 0;
    EventUnregister(v3);
    *((_BYTE *)this + 522) = 0;
  }
}

```

## disassembly

```asm
0x14000aba4  push    rbx
0x14000aba6  sub     rsp, 20h
0x14000abaa  mov     rbx, rcx
0x14000abad  mov     rcx, [rcx+210h]; Handle
0x14000abb4  test    rcx, rcx
0x14000abb7  jz      short loc_14000ABCA
0x14000abb9  call    cs:__imp_RemoveVectoredExceptionHandler
0x14000abbf  mov     qword ptr [rbx+210h], 0
0x14000abca  cmp     byte ptr [rbx+20Ah], 0
0x14000abd1  jz      short loc_14000AC1D
0x14000abd3  cmp     byte ptr [rbx+20Bh], 0
0x14000abda  jnz     short loc_14000ABF4
0x14000abdc  lea     r9, Src; wchar_t *
0x14000abe3  xor     edx, edx; unsigned int
0x14000abe5  lea     r8, aNormalexit; "NormalExit"
0x14000abec  mov     rcx, rbx; this
0x14000abef  call    ?WriteExceptionMetric@MpCommonExceptionMetric@@AEBAXKPEB_W0@Z; MpCommonExceptionMetric::WriteExceptionMetric(ulong,wchar_t const *,wchar_t const *)
0x14000abf4  mov     rcx, cs:RegHandle; RegHandle
0x14000abfb  mov     cs:RegHandle, 0
0x14000ac06  mov     cs:dword_1401D8000, 0
0x14000ac10  call    cs:__imp_EventUnregister
0x14000ac16  mov     byte ptr [rbx+20Ah], 0
0x14000ac1d  add     rsp, 20h
0x14000ac21  pop     rbx
0x14000ac22  retn
```

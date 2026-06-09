# CReaderDriver::Disable(void)

- ea: `0x18002ccd0`
- end: `0x18002cd4f`
- name: `?Disable@CReaderDriver@@UEAAXXZ`
- size: `127`
- prototype: `void __fastcall(void **this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800016c0`
- `0x1800044e0`
- `0x18000d7a0`
- `0x180014180`
- `0x180029dd4`
- `0x18002ccd0`
- `0x18002d770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cce5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccef`

## pseudocode

```c
void __fastcall CReaderDriver::Disable(void **this)
{
  void **v2; // r8
  char v3; // [rsp+30h] [rbp+8h] BYREF

  CReader::Disable((CReader *)this);
  if ( !SetEvent(this[113]) )
    GetLastError();
  if ( (unsigned int)CHandleObject::IsValid((CHandleObject *)(this + 95)) )
    WaitForAnObject(*v2, 0x7530u);
  CLockWrite::CLockWrite((CLockWrite *)&v3, (struct CAccessLock *)(this + 7));
  if ( (unsigned int)CHandleObject::IsValid((CHandleObject *)(this + 104)) )
    CHandleObject::Close(this + 104);
  CLockWrite::~CLockWrite((CLockWrite *)&v3);
}

```

## disassembly

```asm
0x18002ccd0  push    rbx
0x18002ccd2  sub     rsp, 20h
0x18002ccd6  mov     rbx, rcx
0x18002ccd9  call    ?Disable@CReader@@UEAAXXZ; CReader::Disable(void)
0x18002ccde  mov     rcx, [rbx+388h]; hEvent
0x18002cce5  call    cs:__imp_SetEvent
0x18002cceb  test    eax, eax
0x18002cced  jnz     short loc_18002CCF5
0x18002ccef  call    cs:__imp_GetLastError
0x18002ccf5  lea     r8, [rbx+2F8h]
0x18002ccfc  mov     rcx, r8; this
0x18002ccff  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cd04  test    eax, eax
0x18002cd06  jz      short loc_18002CD15
0x18002cd08  mov     rcx, [r8]; void *
0x18002cd0b  mov     edx, 7530h; unsigned int
0x18002cd10  call    ?WaitForAnObject@@YAKPEAXK@Z; WaitForAnObject(void *,ulong)
0x18002cd15  lea     rdx, [rbx+38h]; struct CAccessLock *
0x18002cd19  lea     rcx, [rsp+28h+arg_0]; this
0x18002cd1e  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002cd23  lea     rcx, [rbx+340h]; this
0x18002cd2a  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cd2f  test    eax, eax
0x18002cd31  jz      short loc_18002CD3F
0x18002cd33  lea     rcx, [rbx+340h]; this
0x18002cd3a  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cd3f  lea     rcx, [rsp+28h+arg_0]; this
0x18002cd44  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18002cd49  add     rsp, 20h
0x18002cd4d  pop     rbx
0x18002cd4e  retn
```

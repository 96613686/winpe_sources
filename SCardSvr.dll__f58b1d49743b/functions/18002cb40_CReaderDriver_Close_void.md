# CReaderDriver::Close(void)

- ea: `0x18002cb40`
- end: `0x18002cc85`
- name: `?Close@CReaderDriver@@UEAAXXZ`
- size: `325`
- prototype: `void __fastcall(CReaderDriver *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800178d4`

## callees

- `0x1800016c0`
- `0x1800022b0`
- `0x180014180`
- `0x1800153ac`
- `0x180029dd4`
- `0x18002cb40`
- `0x18002d530`
- `0x18002f334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cbab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cbab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReaderDriver::Close(CReaderDriver *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const unsigned __int8 *v4; // rcx
  void *v5; // r14
  void **v6; // r8

  if ( *((_DWORD *)this + 10) == 256 )
    CPowerSupport::RemoveReader(*((_DWORD *)this + 184));
  AppUnregisterDevice(this, a2, (void **)this + 106);
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 832)) )
    CReader::Close(this);
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 760)) )
  {
    if ( !SetEvent(*((HANDLE *)this + 113)) )
    {
      LastError = GetLastError();
      CalaisError(v4, 0x25Cu, LastError, 0, 0, 0);
    }
    v5 = (void *)*((_QWORD *)this + 95);
    while ( WaitForAnObject(v5, 0xFFFFFFFF) )
      ;
    CHandleObject::Close((void **)this + 95);
    CHandleObject::Close((void **)this + 113);
  }
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 832)) )
    CHandleObject::Close((void **)this + 104);
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 904)) )
    CHandleObject::Close((void **)this + 113);
  if ( (unsigned int)CHandleObject::IsValid((CReaderDriver *)((char *)this + 888)) )
    CHandleObject::Close(v6);
  *((_QWORD *)this + 106) = 0;
  *((_DWORD *)this + 194) = 0;
  *((_DWORD *)this + 200) = 0;
  *((_DWORD *)this + 206) = 0;
  *(_OWORD *)((char *)this + 856) = 0;
  *(_OWORD *)((char *)this + 872) = 0;
}

```

## disassembly

```asm
0x18002cb40  push    rbx
0x18002cb42  push    rbp
0x18002cb43  push    rsi
0x18002cb44  push    rdi
0x18002cb45  push    r14
0x18002cb47  push    r15
0x18002cb49  sub     rsp, 38h
0x18002cb4d  cmp     dword ptr [rcx+28h], 100h
0x18002cb54  mov     rbx, rcx
0x18002cb57  jnz     short loc_18002CB64
0x18002cb59  mov     ecx, [rcx+2E0h]; unsigned int
0x18002cb5f  call    ?RemoveReader@CPowerSupport@@SAXK@Z; CPowerSupport::RemoveReader(ulong)
0x18002cb64  lea     r15, [rbx+350h]
0x18002cb6b  mov     r8, r15; void **
0x18002cb6e  call    ?AppUnregisterDevice@@YAXPEAXPEBGPEAPEAX@Z; AppUnregisterDevice(void *,ushort const *,void * *)
0x18002cb73  lea     rbp, [rbx+340h]
0x18002cb7a  mov     rcx, rbp; this
0x18002cb7d  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cb82  test    eax, eax
0x18002cb84  jz      short loc_18002CB8E
0x18002cb86  mov     rcx, rbx; this
0x18002cb89  call    ?Close@CReader@@UEAAXXZ; CReader::Close(void)
0x18002cb8e  lea     rsi, [rbx+2F8h]
0x18002cb95  mov     rcx, rsi; this
0x18002cb98  lea     rdi, [rbx+388h]
0x18002cb9f  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cba4  test    eax, eax
0x18002cba6  jz      short loc_18002CBFF
0x18002cba8  mov     rcx, [rdi]; hEvent
0x18002cbab  call    cs:__imp_SetEvent
0x18002cbb1  test    eax, eax
0x18002cbb3  jnz     short loc_18002CBDD
0x18002cbb5  call    cs:__imp_GetLastError
0x18002cbbb  mov     [rsp+68h+var_40], 0; unsigned __int16 *
0x18002cbc4  xor     r9d, r9d; unsigned __int16 *
0x18002cbc7  mov     r8d, eax; unsigned int
0x18002cbca  mov     [rsp+68h+var_48], 0; unsigned __int16 *
0x18002cbd3  mov     edx, 25Ch; unsigned int
0x18002cbd8  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18002cbdd  mov     r14, [rsi]
0x18002cbe0  or      edx, 0FFFFFFFFh; unsigned int
0x18002cbe3  mov     rcx, r14; void *
0x18002cbe6  call    ?WaitForAnObject@@YAKPEAXK@Z; WaitForAnObject(void *,ulong)
0x18002cbeb  test    eax, eax
0x18002cbed  jnz     short loc_18002CBE0
0x18002cbef  mov     rcx, rsi; this
0x18002cbf2  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cbf7  mov     rcx, rdi; this
0x18002cbfa  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cbff  mov     rcx, rbp; this
0x18002cc02  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cc07  test    eax, eax
0x18002cc09  jz      short loc_18002CC13
0x18002cc0b  mov     rcx, rbp; this
0x18002cc0e  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cc13  mov     rcx, rdi; this
0x18002cc16  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cc1b  test    eax, eax
0x18002cc1d  jz      short loc_18002CC27
0x18002cc1f  mov     rcx, rdi; this
0x18002cc22  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cc27  lea     r8, [rbx+378h]
0x18002cc2e  mov     rcx, r8; this
0x18002cc31  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x18002cc36  test    eax, eax
0x18002cc38  jz      short loc_18002CC42
0x18002cc3a  mov     rcx, r8; this
0x18002cc3d  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18002cc42  mov     qword ptr [r15], 0
0x18002cc49  xorps   xmm0, xmm0
0x18002cc4c  mov     dword ptr [rbx+308h], 0
0x18002cc56  mov     dword ptr [rbx+320h], 0
0x18002cc60  mov     dword ptr [rbx+338h], 0
0x18002cc6a  movups  xmmword ptr [rbx+358h], xmm0
0x18002cc71  movups  xmmword ptr [rbx+368h], xmm0
0x18002cc78  add     rsp, 38h
0x18002cc7c  pop     r15
0x18002cc7e  pop     r14
0x18002cc80  pop     rdi
0x18002cc81  pop     rsi
0x18002cc82  pop     rbp
0x18002cc83  pop     rbx
0x18002cc84  retn
```

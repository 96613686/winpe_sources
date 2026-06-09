# CAACDec::WriteFrame(void)

- ea: `0x18000205c`
- end: `0x180002131`
- name: `?WriteFrame@CAACDec@@AEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(CAACDec *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180003ec8`

## callees

- `0x18000205c`
- `0x180003af0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800020a2`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800020a2`

## string_xrefs

- `0x1800020c6`: `CAACDec::WriteFrame`
- `0x18000211e`: `CAACDec::WriteFrame`
- `0x1800020d6`: `CAACDec::WriteFrame() m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d`
- `0x180002105`: `CAACDec::WriteFrame() Failed DeliverOutBuffer()`

## pseudocode

```c
__int64 __fastcall CAACDec::WriteFrame(CAACDec *this)
{
  int v2; // eax
  unsigned int v3; // edi
  int v4; // r8d
  int v5; // ecx
  int v6; // eax

  v2 = (*(__int64 (__fastcall **)(CAACDec *, _QWORD))(*(_QWORD *)this + 24LL))(this, *((unsigned int *)this + 28));
  v3 = v2;
  if ( v2 < 0 )
  {
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)this + 246488),
      2u,
      "CAACDec::WriteFrame",
      0x342u,
      "CAACDec::WriteFrame() Failed DeliverOutBuffer()");
  }
  else
  {
    ++*((_DWORD *)this + 61503);
    if ( v2 )
    {
      ++*((_DWORD *)this + 61505);
    }
    else
    {
      v4 = *((_DWORD *)this + 61487);
      v5 = *((_DWORD *)this + 29);
      ++*((_DWORD *)this + 61504);
      v6 = MulDiv(v5, 10000000, v4);
      *((_QWORD *)this + 4) = v6;
      *((_QWORD *)this + 8) += v6;
      TraceLoggingHelperBase::TraceVA(
        (CAACDec *)((char *)this + 246488),
        v3 + 5,
        "CAACDec::WriteFrame",
        0x34Eu,
        "CAACDec::WriteFrame() m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d",
        v6,
        *((_QWORD *)this + 8));
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000205c  mov     [rsp+arg_0], rbx
0x180002061  push    rdi
0x180002062  sub     rsp, 40h
0x180002066  mov     rax, [rcx]
0x180002069  mov     rbx, rcx
0x18000206c  mov     edx, [rcx+70h]
0x18000206f  mov     rax, [rax+18h]
0x180002073  call    cs:__guard_dispatch_icall_fptr
0x180002079  mov     edi, eax
0x18000207b  test    eax, eax
0x18000207d  js      loc_180002105
0x180002083  inc     dword ptr [rbx+3C0FCh]
0x180002089  test    eax, eax
0x18000208b  jnz     short loc_1800020FD
0x18000208d  mov     r8d, [rbx+3C0BCh]; nDenominator
0x180002094  mov     edx, 989680h; nNumerator
0x180002099  mov     ecx, [rbx+74h]; nNumber
0x18000209c  inc     dword ptr [rbx+3C100h]
0x1800020a2  call    cs:__imp_MulDiv
0x1800020a9  nop     dword ptr [rax+rax+00h]
0x1800020ae  movsxd  rdx, eax
0x1800020b1  lea     rcx, [rbx+3C2D8h]; this
0x1800020b8  mov     [rbx+20h], rdx
0x1800020bc  mov     r9d, 34Eh; unsigned int
0x1800020c2  add     [rbx+40h], rdx
0x1800020c6  lea     r8, aCaacdecWritefr_1; "CAACDec::WriteFrame"
0x1800020cd  mov     rax, [rbx+40h]
0x1800020d1  mov     [rsp+48h+var_18], rax
0x1800020d6  lea     rax, aCaacdecWritefr; "CAACDec::WriteFrame() m_TimePerFrame = "...
0x1800020dd  mov     [rsp+48h+var_20], rdx
0x1800020e2  lea     edx, [rdi+5]; unsigned __int8
0x1800020e5  mov     [rsp+48h+Format], rax; Format
0x1800020ea  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800020ef  mov     rbx, [rsp+48h+arg_0]
0x1800020f4  mov     eax, edi
0x1800020f6  add     rsp, 40h
0x1800020fa  pop     rdi
0x1800020fb  retn
0x1800020fd  inc     dword ptr [rbx+3C104h]
0x180002103  jmp     short loc_1800020EF
0x180002105  lea     rax, aCaacdecWritefr_0; "CAACDec::WriteFrame() Failed DeliverOut"...
0x18000210c  mov     r9d, 342h; unsigned int
0x180002112  lea     rcx, [rbx+3C2D8h]; this
0x180002119  mov     [rsp+48h+Format], rax; Format
0x18000211e  lea     r8, aCaacdecWritefr_1; "CAACDec::WriteFrame"
0x180002125  mov     edx, 2; unsigned __int8
0x18000212a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18000212f  jmp     short loc_1800020EF
```

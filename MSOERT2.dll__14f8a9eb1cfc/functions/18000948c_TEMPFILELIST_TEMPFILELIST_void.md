# TEMPFILELIST::~TEMPFILELIST(void)

- ea: `0x18000948c`
- end: `0x1800094fa`
- name: `??1TEMPFILELIST@@EEAA@XZ`
- size: `110`
- prototype: `void __fastcall(TEMPFILELIST *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009540`

## callees

- `0x180009220`
- `0x18000948c`
- `0x180012790`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800094f3`

## pseudocode

```c
void __fastcall TEMPFILELIST::~TEMPFILELIST(TEMPFILELIST *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // rsi

  *(_QWORD *)this = &TEMPFILELIST::`vftable';
  v2 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = 0;
    for ( *((_QWORD *)this + 1) = 0; (unsigned int)v3 < *(_DWORD *)v2; v3 = (unsigned int)(v3 + 1) )
    {
      if ( !(unsigned int)OE_DPA_ReleaseCB<TEMPFILEINFO>(*(_QWORD *)(v2[1] + 8 * v3), 0) )
        break;
    }
    OE_DPA_Destroy(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000948c  mov     [rsp+arg_0], rbx
0x180009491  mov     [rsp+arg_8], rsi
0x180009496  push    rdi
0x180009497  sub     rsp, 20h
0x18000949b  lea     rax, ??_7TEMPFILELIST@@6B@; const TEMPFILELIST::`vftable'
0x1800094a2  mov     rdi, rcx
0x1800094a5  mov     [rcx], rax
0x1800094a8  mov     rbx, [rcx+8]
0x1800094ac  test    rbx, rbx
0x1800094af  jz      short loc_1800094E0
0x1800094b1  xor     esi, esi
0x1800094b3  mov     qword ptr [rcx+8], 0
0x1800094bb  cmp     [rbx], esi
0x1800094bd  jbe     short loc_1800094D8
0x1800094bf  mov     rcx, [rbx+8]
0x1800094c3  xor     edx, edx
0x1800094c5  mov     rcx, [rcx+rsi*8]
0x1800094c9  call    ??$OE_DPA_ReleaseCB@VTEMPFILEINFO@@@@YAHPEAVTEMPFILEINFO@@PEAX@Z; OE_DPA_ReleaseCB<TEMPFILEINFO>(TEMPFILEINFO *,void *)
0x1800094ce  test    eax, eax
0x1800094d0  jz      short loc_1800094D8
0x1800094d2  inc     esi
0x1800094d4  cmp     esi, [rbx]
0x1800094d6  jb      short loc_1800094BF
0x1800094d8  mov     rcx, rbx; lpMem
0x1800094db  call    OE_DPA_Destroy
0x1800094e0  lea     rcx, [rdi+10h]
0x1800094e4  mov     rbx, [rsp+28h+arg_0]
0x1800094e9  mov     rsi, [rsp+28h+arg_8]
0x1800094ee  add     rsp, 20h
0x1800094f2  pop     rdi
0x1800094f3  jmp     cs:__imp_DeleteCriticalSection
```

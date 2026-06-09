# CalaisRemoveDevice(ushort const *)

- ea: `0x18002a5c0`
- end: `0x18002a674`
- name: `?CalaisRemoveDevice@@YAKPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, __int64, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800144e0`

## callees

- `0x180002680`
- `0x180012380`
- `0x1800123a0`
- `0x18002a5c0`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18002a622`
- `KERNEL32!lstrcmpiW` at `0x18002a622`

## pseudocode

```c
__int64 __fastcall CalaisRemoveDevice(
        LPCWSTR lpString1,
        __int64 a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  unsigned int v5; // esi
  __int64 v6; // rdi
  signed int v7; // ebx
  const WCHAR *v8; // rax
  ulong pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  ulong v11; // [rsp+24h] [rbp-34h] BYREF
  int v12; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  try
  {
    COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v12, g_pcsControlLocks, a3, a4);
    v7 = HIDWORD(qword_18004B0C8);
    while ( v7 )
    {
      if ( HIDWORD(qword_18004B0C8) <= --v7 )
        goto LABEL_6;
      _mm_lfence();
      v6 = *((_QWORD *)qword_18004B0D0 + v7);
      if ( v6 )
      {
        v8 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 40LL))(*((_QWORD *)qword_18004B0D0 + v7));
        if ( !lstrcmpiW(lpString1, v8) )
          break;
LABEL_6:
        v6 = 0;
      }
    }
    COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v12);
    if ( !v6 )
    {
      pExceptionObject = -2146435063;
      throw &pExceptionObject;
    }
    CalaisRemoveReader(v7);
  }
  catch ( ulong v11 )
  {
    return v11;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v5;
}

```

## disassembly

```asm
0x18002a5c0  push    rbx
0x18002a5c2  push    rsi
0x18002a5c3  push    rdi
0x18002a5c4  push    r14
0x18002a5c6  sub     rsp, 38h
0x18002a5ca  mov     r14, rcx
0x18002a5cd  xor     esi, esi
0x18002a5cf  xor     edi, edi
0x18002a5d1  mov     rdx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; struct CCriticalSectionObject *
0x18002a5d8  lea     rcx, [rsp+58h+arg_8]; this
0x18002a5dd  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a5e2  nop
0x18002a5e3  mov     ebx, dword ptr cs:qword_18004B0C8+4
0x18002a5e9  test    ebx, ebx
0x18002a5eb  jz      short loc_18002A630
0x18002a5ed  dec     ebx
0x18002a5ef  cmp     dword ptr cs:qword_18004B0C8+4, ebx
0x18002a5f5  jbe     short loc_18002A62C
0x18002a5f7  lfence
0x18002a5fa  movsxd  rcx, ebx
0x18002a5fd  mov     rax, cs:qword_18004B0D0
0x18002a604  mov     rdi, [rax+rcx*8]
0x18002a608  test    rdi, rdi
0x18002a60b  jz      short loc_18002A5E9
0x18002a60d  mov     rax, [rdi]
0x18002a610  mov     rcx, rdi
0x18002a613  mov     rax, [rax+28h]
0x18002a617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a61c  mov     rdx, rax; lpString2
0x18002a61f  mov     rcx, r14; lpString1
0x18002a622  call    cs:__imp_lstrcmpiW
0x18002a628  test    eax, eax
0x18002a62a  jz      short loc_18002A630
0x18002a62c  xor     edi, edi
0x18002a62e  jmp     short loc_18002A5E9
0x18002a630  lea     rcx, [rsp+58h+arg_8]; this
0x18002a635  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a63a  test    rdi, rdi
0x18002a63d  jnz     short loc_18002A658
0x18002a63f  mov     [rsp+58h+pExceptionObject], 80100009h
0x18002a647  lea     rdx, _TI1K; pThrowInfo
0x18002a64e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002a653  call    _CxxThrowException_0
0x18002a658  mov     ecx, ebx; unsigned int
0x18002a65a  call    ?CalaisRemoveReader@@YAKK@Z; CalaisRemoveReader(ulong)
0x18002a65f  nop
0x18002a660  jmp     short loc_18002A668
0x18002a662  jmp     short $+2
0x18002a664  mov     esi, [rsp+58h+arg_8]
0x18002a668  mov     eax, esi
0x18002a66a  add     rsp, 38h
0x18002a66e  pop     r14
0x18002a670  pop     rdi
0x18002a671  pop     rsi
0x18002a672  pop     rbx
0x18002a673  retn
```

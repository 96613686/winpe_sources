# CalaisRemoveReader(ushort const *)

- ea: `0x18002a72c`
- end: `0x18002a7de`
- name: `?CalaisRemoveReader@@YAKPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, __int64, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001950`

## callees

- `0x180002680`
- `0x180012380`
- `0x1800123a0`
- `0x18002a72c`
- `0x18003261b`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18002a78a`
- `KERNEL32!lstrcmpiW` at `0x18002a78a`

## pseudocode

```c
__int64 __fastcall CalaisRemoveReader(
        LPCWSTR lpString1,
        __int64 a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  unsigned int v5; // esi
  __int64 v6; // rdi
  int v7; // ebx
  const WCHAR *v8; // rdx
  ulong pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  ulong v11; // [rsp+24h] [rbp-34h] BYREF
  int v12; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  try
  {
    COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v12, g_pcsControlLocks, a3, a4);
    v7 = HIDWORD(qword_18004B0C8);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v7 )
        {
LABEL_9:
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v12);
          if ( !v6 )
          {
            pExceptionObject = -2146435063;
            throw &pExceptionObject;
          }
          CalaisRemoveReader(v7);
          return v5;
        }
        if ( HIDWORD(qword_18004B0C8) > --v7 )
          break;
LABEL_7:
        v6 = 0;
      }
      _mm_lfence();
      v6 = *((_QWORD *)qword_18004B0D0 + v7);
      if ( v6 )
      {
        v8 = &Data;
        if ( *(_DWORD *)(v6 + 28) )
          v8 = *(const WCHAR **)(v6 + 16);
        if ( !lstrcmpiW(lpString1, v8) )
          goto LABEL_9;
        goto LABEL_7;
      }
    }
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
0x18002a72c  push    rbx
0x18002a72e  push    rsi
0x18002a72f  push    rdi
0x18002a730  push    r14
0x18002a732  sub     rsp, 38h
0x18002a736  mov     r14, rcx
0x18002a739  xor     esi, esi
0x18002a73b  xor     edi, edi
0x18002a73d  mov     rdx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; struct CCriticalSectionObject *
0x18002a744  lea     rcx, [rsp+58h+arg_8]; this
0x18002a749  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a74e  mov     ebx, dword ptr cs:qword_18004B0C8+4
0x18002a754  jmp     short loc_18002A796
0x18002a756  dec     ebx
0x18002a758  cmp     dword ptr cs:qword_18004B0C8+4, ebx
0x18002a75e  jbe     short loc_18002A794
0x18002a760  lfence
0x18002a763  movsxd  rcx, ebx
0x18002a766  mov     rax, cs:qword_18004B0D0
0x18002a76d  mov     rdi, [rax+rcx*8]
0x18002a771  test    rdi, rdi
0x18002a774  jz      short loc_18002A796
0x18002a776  cmp     dword ptr [rdi+1Ch], 0
0x18002a77a  lea     rdx, Data
0x18002a781  jbe     short loc_18002A787
0x18002a783  mov     rdx, [rdi+10h]; lpString2
0x18002a787  mov     rcx, r14; lpString1
0x18002a78a  call    cs:__imp_lstrcmpiW
0x18002a790  test    eax, eax
0x18002a792  jz      short loc_18002A79A
0x18002a794  xor     edi, edi
0x18002a796  test    ebx, ebx
0x18002a798  jnz     short loc_18002A756
0x18002a79a  lea     rcx, [rsp+58h+arg_8]; this
0x18002a79f  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a7a4  test    rdi, rdi
0x18002a7a7  jnz     short loc_18002A7C2
0x18002a7a9  mov     [rsp+58h+pExceptionObject], 80100009h
0x18002a7b1  lea     rdx, _TI1K; pThrowInfo
0x18002a7b8  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002a7bd  call    _CxxThrowException_0
0x18002a7c2  mov     ecx, ebx; unsigned int
0x18002a7c4  call    ?CalaisRemoveReader@@YAKK@Z; CalaisRemoveReader(ulong)
0x18002a7c9  nop
0x18002a7ca  jmp     short loc_18002A7D2
0x18002a7cc  jmp     short $+2
0x18002a7ce  mov     esi, [rsp+58h+arg_8]
0x18002a7d2  mov     eax, esi
0x18002a7d4  add     rsp, 38h
0x18002a7d8  pop     r14
0x18002a7da  pop     rdi
0x18002a7db  pop     rsi
0x18002a7dc  pop     rbx
0x18002a7dd  retn
```

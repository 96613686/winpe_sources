# CalaisAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)

- ea: `0x180029ea0`
- end: `0x180029f72`
- name: `?CalaisAddReader@@YAKP6AKPEBGK@Z0K@Z`
- size: `210`
- prototype: `__int64 __fastcall(unsigned int (*)(const unsigned __int16 *, unsigned int), const unsigned __int16 *, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800144e0`
- `0x18002a350`

## callees

- `0x180012380`
- `0x1800123a0`
- `0x1800140f0`
- `0x180029ea0`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180029f22`
- `KERNEL32!lstrcmpiW` at `0x180029f22`

## pseudocode

```c
__int64 __fastcall CalaisAddReader(
        unsigned int (*a1)(const unsigned __int16 *, unsigned int),
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  unsigned int v4; // esi
  unsigned int v7; // eax
  int v8; // ebx
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  unsigned int v11; // ebx
  _BYTE v13[56]; // [rsp+20h] [rbp-38h] BYREF
  ulong pExceptionObject; // [rsp+78h] [rbp+20h] BYREF

  v4 = (unsigned int)a3;
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)v13, g_pcsControlLocks, a3, a4);
  if ( CalaisCountReaders() >= 0xA )
  {
    pExceptionObject = -2146435066;
    throw &pExceptionObject;
  }
  v7 = HIDWORD(qword_18004B0C8);
  v8 = HIDWORD(qword_18004B0C8);
  while ( v8 )
  {
    if ( v7 > --v8 )
    {
      _mm_lfence();
      v9 = *((_QWORD *)qword_18004B0D0 + v8);
      if ( v9 )
      {
        v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
        if ( !lstrcmpiW(a2, v10) )
        {
          pExceptionObject = -2146435045;
          throw &pExceptionObject;
        }
      }
      v7 = HIDWORD(qword_18004B0C8);
    }
  }
  v11 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD))a1)(a2, v4);
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v13);
  return v11;
}

```

## disassembly

```asm
0x180029ea0  push    rbx
0x180029ea2  push    rbp
0x180029ea3  push    rsi
0x180029ea4  push    rdi
0x180029ea5  sub     rsp, 38h
0x180029ea9  mov     esi, r8d
0x180029eac  mov     rdi, rdx
0x180029eaf  mov     rbp, rcx
0x180029eb2  mov     rdx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; struct CCriticalSectionObject *
0x180029eb9  lea     rcx, [rsp+58h+var_38]; this
0x180029ebe  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x180029ec3  nop
0x180029ec4  call    ?CalaisCountReaders@@YAKXZ; CalaisCountReaders(void)
0x180029ec9  cmp     eax, 0Ah
0x180029ecc  jb      short loc_180029EE8
0x180029ece  mov     [rsp+58h+pExceptionObject], 80100006h
0x180029ed6  lea     rdx, _TI1K; pThrowInfo
0x180029edd  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180029ee2  call    _CxxThrowException_0
0x180029ee8  mov     eax, dword ptr cs:qword_18004B0C8+4
0x180029eee  mov     ebx, eax
0x180029ef0  test    ebx, ebx
0x180029ef2  jz      short loc_180029F4E
0x180029ef4  dec     ebx
0x180029ef6  cmp     eax, ebx
0x180029ef8  jbe     short loc_180029EF0
0x180029efa  lfence
0x180029efd  movsxd  rcx, ebx
0x180029f00  mov     rax, cs:qword_18004B0D0
0x180029f07  mov     rcx, [rax+rcx*8]
0x180029f0b  test    rcx, rcx
0x180029f0e  jz      short loc_180029F2C
0x180029f10  mov     rax, [rcx]
0x180029f13  mov     rax, [rax+28h]
0x180029f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f1c  mov     rdx, rax; lpString2
0x180029f1f  mov     rcx, rdi; lpString1
0x180029f22  call    cs:__imp_lstrcmpiW
0x180029f28  test    eax, eax
0x180029f2a  jz      short loc_180029F34
0x180029f2c  mov     eax, dword ptr cs:qword_18004B0C8+4
0x180029f32  jmp     short loc_180029EF0
0x180029f34  mov     [rsp+58h+pExceptionObject], 8010001Bh
0x180029f3c  lea     rdx, _TI1K; pThrowInfo
0x180029f43  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180029f48  call    _CxxThrowException_0
0x180029f4e  mov     edx, esi
0x180029f50  mov     rcx, rdi
0x180029f53  mov     rax, rbp
0x180029f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f5b  mov     ebx, eax
0x180029f5d  lea     rcx, [rsp+58h+var_38]; this
0x180029f62  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180029f67  mov     eax, ebx
0x180029f69  add     rsp, 38h
0x180029f6d  pop     rdi
0x180029f6e  pop     rsi
0x180029f6f  pop     rbp
0x180029f70  pop     rbx
0x180029f71  retn
```

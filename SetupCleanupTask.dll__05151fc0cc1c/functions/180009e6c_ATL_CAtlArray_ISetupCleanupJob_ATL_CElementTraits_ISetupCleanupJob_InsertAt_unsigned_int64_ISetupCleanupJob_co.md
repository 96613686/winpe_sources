# ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::InsertAt(unsigned __int64,ISetupCleanupJob * const &,unsigned __int64)

- ea: `0x180009e6c`
- end: `0x180009fa8`
- name: `?InsertAt@?$CAtlArray@PEAVISetupCleanupJob@@V?$CElementTraits@PEAVISetupCleanupJob@@@ATL@@@ATL@@QEAAX_KAEBQEAVISetupCleanupJob@@0@Z`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180009db4`

## callees

- `0x180005ef8`
- `0x180006160`
- `0x180009e6c`
- `0x18000c1c0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180009ef9`
- `msvcrt!memmove_s` at `0x180009ef9`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::InsertAt(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 *a3)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rsi
  __int64 result; // rax
  __int64 v9; // r12
  errno_t v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rcx

  v6 = a1[1];
  if ( a2 >= v6 )
  {
    v7 = a2 + 1;
    result = ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::SetCount(
               a1,
               a2 + 1,
               0xFFFFFFFFLL);
    if ( (_BYTE)result )
    {
      v9 = 8 * a2;
      goto LABEL_11;
    }
LABEL_21:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( !(unsigned __int8)ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::SetCount(
                           a1,
                           v6 + 1,
                           0xFFFFFFFFLL) )
    goto LABEL_21;
  v9 = 8 * a2;
  v7 = a2 + 1;
  v10 = memmove_s((void *const)(*a1 + 8 * (a2 + 1)), 8 * (v6 - a2), (const void *const)(8 * a2 + *a1), 8 * (v6 - a2));
  if ( v10 )
  {
    if ( v10 == 12 )
      goto LABEL_21;
    if ( v10 == 22 || v10 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v10 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  try
  {
    result = ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::CallConstructors(v11, 1);
  }
  catch ( ... )
  {
    ATL::CElementTraitsBase<ISetupCleanupJob *>::RelocateElements(*a1 + 8 * a2, *a1 + 8 * (a2 + 1), v6 - a2);
    ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::SetCount(a1, v6, 0xFFFFFFFFLL);
    throw;
  }
LABEL_11:
  if ( a2 < v7 )
  {
    v12 = a2;
    if ( v7 - a2 < 2 )
      goto LABEL_31;
    v13 = v9 + *a1;
    if ( v13 <= (unsigned __int64)a1 && v13 >= (unsigned __int64)a1 )
      goto LABEL_31;
    if ( v13 <= (unsigned __int64)a3 && v13 >= (unsigned __int64)a3 )
      goto LABEL_31;
    do
    {
      v12 += 2LL;
      result = v12;
    }
    while ( v12 < a2 );
    if ( v12 < v7 )
    {
LABEL_31:
      do
      {
        result = *a3;
        *(_QWORD *)(*a1 + 8 * v12++) = *a3;
      }
      while ( v12 < v7 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009e6c  mov     rax, rsp
0x180009e6f  mov     [rax+18h], rbx
0x180009e73  mov     [rax+20h], r9
0x180009e77  mov     [rax+10h], rdx
0x180009e7b  mov     [rax+8], rcx
0x180009e7f  push    rsi
0x180009e80  push    rdi
0x180009e81  push    r12
0x180009e83  push    r14
0x180009e85  push    r15
0x180009e87  sub     rsp, 20h
0x180009e8b  mov     r15, r8
0x180009e8e  mov     rbx, rdx
0x180009e91  mov     rdi, rcx
0x180009e94  mov     r14, [rcx+8]
0x180009e98  or      r8d, 0FFFFFFFFh
0x180009e9c  cmp     rdx, r14
0x180009e9f  jb      short loc_180009EBF
0x180009ea1  lea     rsi, [rdx+1]
0x180009ea5  mov     rdx, rsi
0x180009ea8  call    ?SetCount@?$CAtlArray@PEAVISetupCleanupJob@@V?$CElementTraits@PEAVISetupCleanupJob@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::SetCount(unsigned __int64,int)
0x180009ead  test    al, al
0x180009eaf  jz      loc_180009F87
0x180009eb5  lea     r12, ds:0[rbx*8]
0x180009ebd  jmp     short loc_180009F2A
0x180009ebf  lea     rdx, [r14+1]
0x180009ec3  call    ?SetCount@?$CAtlArray@PEAVISetupCleanupJob@@V?$CElementTraits@PEAVISetupCleanupJob@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::SetCount(unsigned __int64,int)
0x180009ec8  test    al, al
0x180009eca  jz      loc_180009F87
0x180009ed0  mov     [rsp+48h+arg_18], r14
0x180009ed5  mov     rax, [rdi]
0x180009ed8  sub     r14, rbx
0x180009edb  shl     r14, 3
0x180009edf  lea     r12, ds:0[rbx*8]
0x180009ee7  lea     rsi, [rbx+1]
0x180009eeb  lea     r8, [r12+rax]; Source
0x180009eef  lea     rcx, [rax+rsi*8]; Destination
0x180009ef3  mov     r9, r14; SourceSize
0x180009ef6  mov     rdx, r14; DestinationSize
0x180009ef9  call    cs:__imp_memmove_s
0x180009eff  test    eax, eax
0x180009f01  jz      short loc_180009F1F
0x180009f03  cmp     eax, 0Ch
0x180009f06  jz      short loc_180009F87
0x180009f08  cmp     eax, 16h
0x180009f0b  jz      loc_180009F9D
0x180009f11  cmp     eax, 22h ; '"'
0x180009f14  jz      loc_180009F9D
0x180009f1a  cmp     eax, 50h ; 'P'
0x180009f1d  jnz     short loc_180009F92
0x180009f1f  mov     edx, 1
0x180009f24  call    ?CallConstructors@?$CAtlArray@PEAVISetupCleanupJob@@V?$CElementTraits@PEAVISetupCleanupJob@@@ATL@@@ATL@@CAXPEAPEAVISetupCleanupJob@@_K@Z; ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::CallConstructors(ISetupCleanupJob * *,unsigned __int64)
0x180009f29  nop
0x180009f2a  cmp     rbx, rsi
0x180009f2d  jnb     short loc_180009F75
0x180009f2f  mov     rdx, rbx
0x180009f32  mov     rax, rsi
0x180009f35  sub     rax, rbx
0x180009f38  cmp     rax, 2
0x180009f3c  jb      short loc_180009F63
0x180009f3e  mov     rcx, [rdi]
0x180009f41  add     rcx, r12
0x180009f44  cmp     rcx, rdi
0x180009f47  ja      short loc_180009F4B
0x180009f49  jnb     short loc_180009F63
0x180009f4b  cmp     rcx, r15
0x180009f4e  ja      short loc_180009F52
0x180009f50  jnb     short loc_180009F63
0x180009f52  add     rdx, 2
0x180009f56  mov     rax, rdx
0x180009f59  cmp     rdx, rbx
0x180009f5c  jb      short loc_180009F52
0x180009f5e  cmp     rax, rsi
0x180009f61  jnb     short loc_180009F75
0x180009f63  mov     rcx, [rdi]
0x180009f66  mov     rax, [r15]
0x180009f69  mov     [rcx+rdx*8], rax
0x180009f6d  inc     rdx
0x180009f70  cmp     rdx, rsi
0x180009f73  jb      short loc_180009F63
0x180009f75  mov     rbx, [rsp+48h+arg_10]
0x180009f7a  add     rsp, 20h
0x180009f7e  pop     r15
0x180009f80  pop     r14
0x180009f82  pop     r12
0x180009f84  pop     rdi
0x180009f85  pop     rsi
0x180009f86  retn
0x180009f87  mov     ecx, 8007000Eh; int
0x180009f8c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f92  mov     ecx, 80004005h; int
0x180009f97  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f9d  mov     ecx, 80070057h; int
0x180009fa2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

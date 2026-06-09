# CSMBHelperClass::ReproduceFailure(ushort *,INDFEtw *,ulong &)

- ea: `0x180008214`
- end: `0x18000842c`
- name: `?ReproduceFailure@CSMBHelperClass@@CAJPEAGPEAUINDFEtw@@AEAK@Z`
- size: `536`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct INDFEtw *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008440`
- `0x1800088e0`

## callees

- `0x180004ee0`
- `0x180008214`
- `0x180012010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000841b`
- `KERNEL32!CloseHandle` at `0x18000841b`
- `KERNEL32!CreateFileW` at `0x1800082f0`
- `KERNEL32!CreateFileW` at `0x1800082f0`
- `KERNEL32!GetLastError` at `0x180008303`
- `KERNEL32!GetLastError` at `0x180008303`

## string_xrefs

- `0x18000825b`: `CSMBHelperClass::ReproduceFailure UNCPath  is Invalid`
- `0x18000833a`: `CSMBHelperClass::ReproduceFailure CreateFile %ws failed with %d`
- `0x1800083bf`: `CSMBHelperClass::ReproduceFailure CreateFile succeeded`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailure(unsigned __int16 *a1, struct INDFEtw *a2, unsigned int *a3)
{
  __int64 v6; // rbx
  __int64 result; // rax
  HANDLE FileW; // rbp
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  *a3 = 0;
  if ( a1 )
  {
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x2000080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      *a3 = GetLastError();
      if ( a2 )
      {
        v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v11,
          L"CSMBHelperClass::ReproduceFailure CreateFile %ws failed with %d",
          a1,
          *a3);
        v9 = v11;
        (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)a2 + 24LL))(
          a2,
          2,
          0,
          L"SMBHelperClass",
          v11);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
      }
    }
    else
    {
      if ( a2 )
      {
        v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v11,
          L"CSMBHelperClass::ReproduceFailure CreateFile succeeded");
        v10 = v11;
        (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)a2 + 24LL))(
          a2,
          2,
          0,
          L"SMBHelperClass",
          v11);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
      }
      CloseHandle(FileW);
    }
    return 0;
  }
  else
  {
    if ( a2 )
    {
      v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v11,
        L"CSMBHelperClass::ReproduceFailure UNCPath  is Invalid");
      v6 = v11;
      (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)a2 + 24LL))(
        a2,
        2,
        0,
        L"SMBHelperClass",
        v11);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
    }
    result = *a3;
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008214  push    rbx
0x180008216  push    rbp
0x180008217  push    rsi
0x180008218  push    rdi
0x180008219  sub     rsp, 48h
0x18000821d  mov     rsi, r8
0x180008220  mov     rdi, rdx
0x180008223  mov     rbx, rcx
0x180008226  mov     dword ptr [r8], 0
0x18000822d  test    rcx, rcx
0x180008230  jnz     loc_1800082CB
0x180008236  test    rdx, rdx
0x180008239  jz      short loc_1800082B4
0x18000823b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008242  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008249  mov     rax, [rax+18h]
0x18000824d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008252  add     rax, 18h
0x180008256  mov     [rsp+68h+arg_0], rax
0x18000825b  lea     rdx, aCsmbhelperclas_16; "CSMBHelperClass::ReproduceFailure UNCPa"...
0x180008262  lea     rcx, [rsp+68h+arg_0]
0x180008267  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000826c  mov     rax, [rdi]
0x18000826f  xor     r8d, r8d
0x180008272  mov     rbx, [rsp+68h+arg_0]
0x180008277  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx
0x18000827c  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180008283  lea     edx, [r8+2]
0x180008287  mov     rcx, rdi
0x18000828a  mov     rax, [rax+18h]
0x18000828e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008293  nop
0x180008294  lea     rdx, [rbx-18h]
0x180008298  or      eax, 0FFFFFFFFh
0x18000829b  lock xadd [rdx+10h], eax
0x1800082a0  sub     eax, 1
0x1800082a3  jg      short loc_1800082B4
0x1800082a5  mov     rcx, [rdx]
0x1800082a8  mov     rax, [rcx]
0x1800082ab  mov     rax, [rax+8]
0x1800082af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b4  mov     eax, [rsi]
0x1800082b6  test    eax, eax
0x1800082b8  jle     loc_180008423
0x1800082be  movzx   eax, ax
0x1800082c1  or      eax, 80070000h
0x1800082c6  jmp     loc_180008423
0x1800082cb  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800082d4  mov     [rsp+68h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800082dc  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800082e4  xor     r9d, r9d; lpSecurityAttributes
0x1800082e7  mov     edx, 80000000h; dwDesiredAccess
0x1800082ec  lea     r8d, [r9+1]; dwShareMode
0x1800082f0  call    cs:__imp_CreateFileW
0x1800082f6  mov     rbp, rax
0x1800082f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800082fd  jnz     loc_18000839A
0x180008303  call    cs:__imp_GetLastError
0x180008309  mov     [rsi], eax
0x18000830b  test    rdi, rdi
0x18000830e  jz      loc_180008421
0x180008314  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000831b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008322  mov     rax, [rax+18h]
0x180008326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832b  add     rax, 18h
0x18000832f  mov     [rsp+68h+arg_0], rax
0x180008334  mov     r9d, [rsi]
0x180008337  mov     r8, rbx
0x18000833a  lea     rdx, aCsmbhelperclas_20; "CSMBHelperClass::ReproduceFailure Creat"...
0x180008341  lea     rcx, [rsp+68h+arg_0]
0x180008346  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000834b  mov     rax, [rdi]
0x18000834e  xor     r8d, r8d
0x180008351  mov     rbx, [rsp+68h+arg_0]
0x180008356  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx
0x18000835b  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180008362  lea     edx, [rbp+3]
0x180008365  mov     rcx, rdi
0x180008368  mov     rax, [rax+18h]
0x18000836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008371  nop
0x180008372  lea     rdx, [rbx-18h]
0x180008376  or      eax, ebp
0x180008378  lock xadd [rdx+10h], eax
0x18000837d  sub     eax, 1
0x180008380  jg      loc_180008421
0x180008386  mov     rcx, [rdx]
0x180008389  mov     rax, [rcx]
0x18000838c  mov     rax, [rax+8]
0x180008390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008395  jmp     loc_180008421
0x18000839a  test    rdi, rdi
0x18000839d  jz      short loc_180008418
0x18000839f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800083a6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800083ad  mov     rax, [rax+18h]
0x1800083b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b6  add     rax, 18h
0x1800083ba  mov     [rsp+68h+arg_0], rax
0x1800083bf  lea     rdx, aCsmbhelperclas_8; "CSMBHelperClass::ReproduceFailure Creat"...
0x1800083c6  lea     rcx, [rsp+68h+arg_0]
0x1800083cb  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800083d0  mov     rax, [rdi]
0x1800083d3  xor     r8d, r8d
0x1800083d6  mov     rbx, [rsp+68h+arg_0]
0x1800083db  mov     qword ptr [rsp+68h+dwCreationDisposition], rbx
0x1800083e0  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x1800083e7  lea     edx, [r8+2]
0x1800083eb  mov     rcx, rdi
0x1800083ee  mov     rax, [rax+18h]
0x1800083f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f7  nop
0x1800083f8  lea     rdx, [rbx-18h]
0x1800083fc  or      eax, 0FFFFFFFFh
0x1800083ff  lock xadd [rdx+10h], eax
0x180008404  sub     eax, 1
0x180008407  jg      short loc_180008418
0x180008409  mov     rcx, [rdx]
0x18000840c  mov     rax, [rcx]
0x18000840f  mov     rax, [rax+8]
0x180008413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008418  mov     rcx, rbp; hObject
0x18000841b  call    cs:__imp_CloseHandle
0x180008421  xor     eax, eax
0x180008423  add     rsp, 48h
0x180008427  pop     rdi
0x180008428  pop     rsi
0x180008429  pop     rbp
0x18000842a  pop     rbx
0x18000842b  retn
```

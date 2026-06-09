# CSMBHelperClass::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x180008fc0`
- end: `0x1800090be`
- name: `?Validate@CSMBHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(CSMBHelperClass *this, __int64, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180004ee0`
- `0x180008fc0`
- `0x180012010`

## string_xrefs

- `0x180009033`: `CSMBHelperClass::Validate ReproTimeout %d, CreateFileError %d`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::Validate(CSMBHelperClass *this, __int64 a2, int *a3, enum tagREPAIR_STATUS *a4)
{
  enum tagREPAIR_STATUS v6; // edi
  int v7; // ebp
  __int64 v8; // rbx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v6 = RS_UNREPAIRED;
  v7 = (*(__int64 (__fastcall **)(char *, __int64, int *))(*((_QWORD *)this + 7) + 40LL))((char *)this + 56, a2, a3);
  if ( v7 >= 0 )
  {
    if ( *((_QWORD *)this + 22) )
    {
      v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v10,
        L"CSMBHelperClass::Validate ReproTimeout %d, CreateFileError %d",
        *((unsigned int *)this + 72),
        *((unsigned int *)this + 34));
      v8 = v10;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this + 22)
                                                                                         + 24LL))(
        *((_QWORD *)this + 22),
        2,
        0,
        L"SMBHelperClass",
        v10);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
    }
    if ( !*((_DWORD *)this + 72) && !*((_DWORD *)this + 34) )
      v6 = RS_REPAIRED;
  }
  *a4 = v6;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008fc0  mov     [rsp+arg_8], rbx
0x180008fc5  mov     [rsp+arg_10], rbp
0x180008fca  push    rsi
0x180008fcb  push    rdi
0x180008fcc  push    r14
0x180008fce  sub     rsp, 30h
0x180008fd2  mov     r14, r9
0x180008fd5  mov     rsi, rcx
0x180008fd8  mov     edi, 2
0x180008fdd  add     rcx, 38h ; '8'
0x180008fe1  mov     rax, [rcx]
0x180008fe4  mov     rax, [rax+28h]
0x180008fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fed  mov     ebp, eax
0x180008fef  test    eax, eax
0x180008ff1  js      loc_1800090A6
0x180008ff7  cmp     qword ptr [rsi+0B0h], 0
0x180008fff  jz      loc_18000908E
0x180009005  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000900c  mov     rax, [rcx+18h]
0x180009010  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901c  add     rax, 18h
0x180009020  mov     [rsp+48h+arg_0], rax
0x180009025  mov     r9d, [rsi+88h]
0x18000902c  mov     r8d, [rsi+120h]
0x180009033  lea     rdx, aCsmbhelperclas_10; "CSMBHelperClass::Validate ReproTimeout "...
0x18000903a  lea     rcx, [rsp+48h+arg_0]
0x18000903f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009044  mov     rcx, [rsi+0B0h]
0x18000904b  mov     rax, [rcx]
0x18000904e  xor     r8d, r8d
0x180009051  mov     rbx, [rsp+48h+arg_0]
0x180009056  mov     [rsp+48h+var_28], rbx
0x18000905b  lea     r9, aSmbhelperclass_0; "SMBHelperClass"
0x180009062  mov     edx, edi
0x180009064  mov     rax, [rax+18h]
0x180009068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906d  nop
0x18000906e  lea     rdx, [rbx-18h]
0x180009072  or      eax, 0FFFFFFFFh
0x180009075  lock xadd [rdx+10h], eax
0x18000907a  sub     eax, 1
0x18000907d  jg      short loc_18000908E
0x18000907f  mov     rcx, [rdx]
0x180009082  mov     rax, [rcx]
0x180009085  mov     rax, [rax+8]
0x180009089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000908e  cmp     dword ptr [rsi+120h], 0
0x180009095  jnz     short loc_1800090A6
0x180009097  mov     eax, 1
0x18000909c  cmp     dword ptr [rsi+88h], 0
0x1800090a3  cmovz   edi, eax
0x1800090a6  mov     [r14], edi
0x1800090a9  mov     eax, ebp
0x1800090ab  mov     rbx, [rsp+48h+arg_8]
0x1800090b0  mov     rbp, [rsp+48h+arg_10]
0x1800090b5  add     rsp, 30h
0x1800090b9  pop     r14
0x1800090bb  pop     rdi
0x1800090bc  pop     rsi
0x1800090bd  retn
```

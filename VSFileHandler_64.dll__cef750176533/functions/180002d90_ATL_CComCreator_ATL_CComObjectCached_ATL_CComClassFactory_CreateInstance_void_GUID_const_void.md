# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002d90`
- end: `0x180002eb2`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `290`
- prototype: `__int64 __fastcall(void **, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002d90`
- `0x180003624`
- `0x180007db0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180002e1f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180002e1f`
- `KERNEL32!GetLastError` at `0x180002e29`
- `KERNEL32!GetLastError` at `0x180002e29`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        void **a1,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v7; // edi
  void ***v8; // rax
  void ***v9; // rbx
  signed int v10; // edi
  signed int LastError; // eax
  int v12; // eax
  __int64 (__fastcall *v13)(void ***, const struct _GUID *, void **); // r9
  unsigned int Interface; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (void ***)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    v8[6] = 0;
    *((_BYTE *)v8 + 56) = 0;
    *v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v9[8] = a1;
    v10 = 0;
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v9 + 2), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    if ( v10 >= 0 )
LABEL_11:
      *((_BYTE *)v9 + 56) = 1;
    v12 = 0;
    if ( v10 < 0 )
      v12 = v10;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7
      || ((v13 = (__int64 (__fastcall *)(void ***, const struct _GUID *, void **))**v9,
           (char *)v13 != (char *)&ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface)
        ? (Interface = v13(v9, a2, a3))
        : (Interface = ATL::AtlInternalQueryInterface(
                         v9,
                         (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComClassFactory::_GetEntries'::`2'::_entries,
                         a2,
                         a3)),
          (v7 = Interface) != 0) )
    {
      ((void (__fastcall *)(void ***, __int64))(*v9)[5])(v9, 1);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_0], rbx
0x180002d95  mov     [rsp+arg_8], rbp
0x180002d9a  push    rsi
0x180002d9b  push    rdi
0x180002d9c  push    r14
0x180002d9e  sub     rsp, 20h
0x180002da2  mov     rsi, r8
0x180002da5  mov     r14, rdx
0x180002da8  mov     rbp, rcx
0x180002dab  test    r8, r8
0x180002dae  jnz     short loc_180002DBA
0x180002db0  mov     eax, 80004003h
0x180002db5  jmp     loc_180002E9F
0x180002dba  and     qword ptr [r8], 0
0x180002dbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002dc5  mov     ecx, 48h ; 'H'; unsigned __int64
0x180002dca  mov     edi, 8007000Eh
0x180002dcf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002dd4  mov     [rsp+38h+arg_10], rax
0x180002dd9  mov     rbx, rax
0x180002ddc  test    rax, rax
0x180002ddf  jz      short loc_180002E05
0x180002de1  and     dword ptr [rax+8], 0
0x180002de5  xorps   xmm0, xmm0
0x180002de8  movups  xmmword ptr [rbx+10h], xmm0
0x180002dec  xor     eax, eax
0x180002dee  movups  xmmword ptr [rbx+20h], xmm0
0x180002df2  mov     [rbx+30h], rax
0x180002df6  mov     [rbx+38h], al
0x180002df9  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002e00  mov     [rbx], rax
0x180002e03  jmp     short loc_180002E07
0x180002e05  xor     ebx, ebx
0x180002e07  test    rbx, rbx
0x180002e0a  jz      loc_180002E9D
0x180002e10  xor     r8d, r8d; Flags
0x180002e13  mov     [rbx+40h], rbp
0x180002e17  xor     edx, edx; dwSpinCount
0x180002e19  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002e1d  xor     edi, edi
0x180002e1f  call    cs:__imp_InitializeCriticalSectionEx
0x180002e25  test    eax, eax
0x180002e27  jnz     short loc_180002E41
0x180002e29  call    cs:__imp_GetLastError
0x180002e2f  movzx   edi, ax
0x180002e32  or      edi, 80070000h
0x180002e38  test    eax, eax
0x180002e3a  cmovle  edi, eax
0x180002e3d  test    edi, edi
0x180002e3f  js      short loc_180002E45
0x180002e41  mov     byte ptr [rbx+38h], 1
0x180002e45  xor     eax, eax
0x180002e47  test    edi, edi
0x180002e49  cmovs   eax, edi
0x180002e4c  xor     edi, edi
0x180002e4e  test    eax, eax
0x180002e50  cmovs   edi, eax
0x180002e53  test    edi, edi
0x180002e55  jnz     short loc_180002E8F
0x180002e57  mov     rax, [rbx]
0x180002e5a  mov     rcx, rbx; void *
0x180002e5d  mov     r9, [rax]
0x180002e60  lea     rax, ?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)
0x180002e67  cmp     r9, rax
0x180002e6a  jnz     short loc_180002E80
0x180002e6c  mov     r9, rsi; void **
0x180002e6f  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180002e76  mov     r8, r14; struct _GUID *
0x180002e79  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180002e7e  jmp     short loc_180002E89
0x180002e80  mov     r8, rsi
0x180002e83  mov     rdx, r14
0x180002e86  call    r9
0x180002e89  mov     edi, eax
0x180002e8b  test    eax, eax
0x180002e8d  jz      short loc_180002E9D
0x180002e8f  mov     rax, [rbx]
0x180002e92  mov     edx, 1
0x180002e97  mov     rcx, rbx
0x180002e9a  call    qword ptr [rax+28h]
0x180002e9d  mov     eax, edi
0x180002e9f  mov     rbx, [rsp+38h+arg_0]
0x180002ea4  mov     rbp, [rsp+38h+arg_8]
0x180002ea9  add     rsp, 20h
0x180002ead  pop     r14
0x180002eaf  pop     rdi
0x180002eb0  pop     rsi
0x180002eb1  retn
```

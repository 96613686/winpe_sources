# StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x14000d1b8`
- end: `0x14000d32e`
- name: `?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee8c`
- `0x140010960`

## callees

- `0x14000c19c`
- `0x14000c340`
- `0x14000ce48`
- `0x14000ced0`
- `0x14000d118`
- `0x14000d1b8`
- `0x140010c6c`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000d251`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d251`
- `ADVAPI32!RegCloseKey` at `0x14000d278`
- `ADVAPI32!RegCloseKey` at `0x14000d278`

## string_xrefs

- `0x14000d200`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StartList::BuildConfigList(__int64 a1, __int64 a2)
{
  HKEY v4; // rbx
  LPCWSTR v5; // rdx
  __int64 v6; // rax
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  signed __int32 v9; // eax
  bool v10; // cc
  __int64 result; // rax
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h] BYREF
  HKEY v16; // [rsp+50h] [rbp-20h]
  __int64 v17; // [rsp+58h] [rbp-18h]
  __int64 v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  int v20; // [rsp+A8h] [rbp+38h] BYREF

  v19 = 0;
  v20 = 44;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
    a1,
    &v12,
    &v20,
    &v19);
  while ( (unsigned __int8)ATL::operator!=(&v12) )
  {
    if ( *(_DWORD *)(v12 - 16) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &lpSubKey,
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs\\");
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, v12);
      v4 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &phkResult) )
      {
        v4 = phkResult;
        v16 = phkResult;
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          a2,
          v12);
      }
      if ( v4 )
        RegCloseKey(v4);
      v5 = lpSubKey - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    }
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
           a1,
           &v15,
           &v20,
           &v19);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(&v12, v6);
    v7 = (_QWORD *)(v15 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
  }
  v8 = (_QWORD *)(v12 - 24);
  v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(v12 - 24 + 16), 0xFFFFFFFF);
  v10 = v9 <= 1;
  result = (unsigned int)(v9 - 1);
  if ( v10 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  return result;
}

```

## disassembly

```asm
0x14000d1b8  mov     [rsp-18h+arg_0], rbx
0x14000d1bd  push    rbp
0x14000d1be  push    rsi
0x14000d1bf  push    rdi
0x14000d1c0  mov     rbp, rsp
0x14000d1c3  sub     rsp, 70h
0x14000d1c7  mov     rsi, rdx
0x14000d1ca  mov     rdi, rcx
0x14000d1cd  mov     [rbp+arg_10], 0
0x14000d1d4  mov     [rbp+arg_18], 2Ch ; ','
0x14000d1db  lea     r9, [rbp+arg_10]
0x14000d1df  lea     r8, [rbp+arg_18]
0x14000d1e3  lea     rdx, [rbp+var_40]
0x14000d1e7  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14000d1ec  nop
0x14000d1ed  jmp     loc_14000D2E9
0x14000d1f2  mov     rax, [rbp+var_40]
0x14000d1f6  cmp     dword ptr [rax-10h], 0
0x14000d1fa  jz      loc_14000D2A3
0x14000d200  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000d207  lea     rcx, [rbp+lpSubKey]
0x14000d20b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000d210  nop
0x14000d211  mov     rdx, [rbp+var_40]
0x14000d215  mov     r8d, [rdx-10h]
0x14000d219  lea     rcx, [rbp+lpSubKey]
0x14000d21d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000d222  xor     ebx, ebx
0x14000d224  mov     [rbp+var_20], rbx
0x14000d228  mov     [rbp+var_18], rbx
0x14000d22c  mov     [rbp+var_10], rbx
0x14000d230  mov     [rbp+var_30], rbx
0x14000d234  lea     rax, [rbp+var_30]
0x14000d238  mov     [rsp+70h+phkResult], rax; phkResult
0x14000d23d  mov     r9d, 20019h; samDesired
0x14000d243  xor     r8d, r8d; ulOptions
0x14000d246  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14000d24a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d251  call    cs:__imp_RegOpenKeyExW
0x14000d257  test    eax, eax
0x14000d259  jnz     short loc_14000D270
0x14000d25b  mov     rbx, [rbp+var_30]
0x14000d25f  mov     [rbp+var_20], rbx
0x14000d263  mov     rdx, [rbp+var_40]
0x14000d267  mov     rcx, rsi
0x14000d26a  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14000d26f  nop
0x14000d270  test    rbx, rbx
0x14000d273  jz      short loc_14000D27F
0x14000d275  mov     rcx, rbx; hKey
0x14000d278  call    cs:__imp_RegCloseKey
0x14000d27e  nop
0x14000d27f  mov     rdx, [rbp+lpSubKey]
0x14000d283  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d287  or      eax, 0FFFFFFFFh
0x14000d28a  lock xadd [rdx+10h], eax
0x14000d28f  sub     eax, 1
0x14000d292  jg      short loc_14000D2A3
0x14000d294  mov     rcx, [rdx]
0x14000d297  mov     rax, [rcx]
0x14000d29a  mov     rax, [rax+8]
0x14000d29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2a3  lea     r9, [rbp+arg_10]
0x14000d2a7  lea     r8, [rbp+arg_18]
0x14000d2ab  lea     rdx, [rbp+var_28]
0x14000d2af  mov     rcx, rdi
0x14000d2b2  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x14000d2b7  nop
0x14000d2b8  mov     rdx, rax
0x14000d2bb  lea     rcx, [rbp+var_40]
0x14000d2bf  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d2c4  nop
0x14000d2c5  mov     rdx, [rbp+var_28]
0x14000d2c9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d2cd  or      eax, 0FFFFFFFFh
0x14000d2d0  lock xadd [rdx+10h], eax
0x14000d2d5  sub     eax, 1
0x14000d2d8  jg      short loc_14000D2E9
0x14000d2da  mov     rcx, [rdx]
0x14000d2dd  mov     rax, [rcx]
0x14000d2e0  mov     rax, [rax+8]
0x14000d2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d2e9  lea     rcx, [rbp+var_40]
0x14000d2ed  call    ??9ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBD@Z; ATL::operator!=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x14000d2f2  test    al, al
0x14000d2f4  jnz     loc_14000D1F2
0x14000d2fa  mov     rdx, [rbp+var_40]
0x14000d2fe  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d302  or      eax, 0FFFFFFFFh
0x14000d305  lock xadd [rdx+10h], eax
0x14000d30a  sub     eax, 1
0x14000d30d  jg      short loc_14000D31E
0x14000d30f  mov     rcx, [rdx]
0x14000d312  mov     rax, [rcx]
0x14000d315  mov     rax, [rax+8]
0x14000d319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d31e  mov     rbx, [rsp+70h+arg_0]
0x14000d326  add     rsp, 70h
0x14000d32a  pop     rdi
0x14000d32b  pop     rsi
0x14000d32c  pop     rbp
0x14000d32d  retn
```

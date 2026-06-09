# FSMVirtualCamera::InternalUpdateRegistryEntry(IFSMCameraDeviceRegistryEntry *)

- ea: `0x1800223cc`
- end: `0x180022574`
- name: `?InternalUpdateRegistryEntry@FSMVirtualCamera@@IEAAJPEAUIFSMCameraDeviceRegistryEntry@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(FSMVirtualCamera *__hidden this, struct IFSMCameraDeviceRegistryEntry *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022110`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18000afb0`
- `0x18000c8d4`
- `0x1800223cc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002243e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800224b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002243e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800224b6`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalUpdateRegistryEntry(
        FSMVirtualCamera *this,
        struct IFSMCameraDeviceRegistryEntry *a2)
{
  unsigned int v2; // r13d
  _QWORD *v3; // r15
  __int64 i; // rsi
  _QWORD *v7; // r14
  __int64 v8; // rcx
  const WCHAR *v9; // rbx
  const WCHAR *v10; // rax
  const WCHAR *v11; // rbx
  const WCHAR *v12; // rax
  bool v13; // zf
  __int64 v14; // rbx
  __int64 v15; // rsi
  unsigned int v16; // ebx

  v2 = *((_DWORD *)this + 140);
  v3 = (_QWORD *)((char *)this + 552);
  for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
  {
    v7 = (_QWORD *)((char *)this + 552);
    v8 = *(_QWORD *)(*((_QWORD *)this + 69) + 8 * i);
    v9 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
    v10 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IFSMCameraDeviceRegistryEntry *))(*(_QWORD *)a2 + 24LL))(a2);
    if ( CompareStringOrdinal(v10, -1, v9, -1, 1) == 2 )
    {
      if ( (*(__int64 (__fastcall **)(struct IFSMCameraDeviceRegistryEntry *))(*(_QWORD *)a2 + 32LL))(a2)
        && (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * i) + 32LL))(*(_QWORD *)(*v7 + 8 * i)) )
      {
        v11 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * i) + 32LL))(*(_QWORD *)(*v7 + 8 * i));
        v12 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IFSMCameraDeviceRegistryEntry *))(*(_QWORD *)a2 + 32LL))(a2);
        v13 = CompareStringOrdinal(v12, -1, v11, -1, 1) == 2;
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v7 + 8 * i) + 32LL))(*(_QWORD *)(*v7 + 8 * i));
        v13 = (*(__int64 (__fastcall **)(struct IFSMCameraDeviceRegistryEntry *))(*(_QWORD *)a2 + 32LL))(a2) == v14;
      }
      if ( v13 )
      {
        CTUnkArray<FSMCameraDeviceProperty>::RemoveAt((char *)this + 552, (unsigned int)i);
        break;
      }
    }
  }
  v15 = *((unsigned int *)this + 140);
  if ( (unsigned int)CTEntryArray<IFSConfigurationEntry *>::SetSize(v3, (unsigned int)(v15 + 1)) )
  {
    v16 = 0;
    *(_QWORD *)(*v3 + 8 * v15) = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IFSMCameraDeviceRegistryEntry *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v16 = -2147024882;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        276,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        this,
        -2147024882);
  }
  return v16;
}

```

## disassembly

```asm
0x1800223cc  push    rbx
0x1800223ce  push    rbp
0x1800223cf  push    rsi
0x1800223d0  push    rdi
0x1800223d1  push    r12
0x1800223d3  push    r13
0x1800223d5  push    r14
0x1800223d7  push    r15
0x1800223d9  sub     rsp, 38h
0x1800223dd  mov     r13d, [rcx+230h]
0x1800223e4  lea     r15, [rcx+228h]
0x1800223eb  mov     rdi, rdx
0x1800223ee  mov     rbp, rcx
0x1800223f1  xor     esi, esi
0x1800223f3  cmp     esi, r13d
0x1800223f6  jnb     loc_1800224FC
0x1800223fc  lea     r14, [rbp+228h]
0x180022403  mov     rax, [r14]
0x180022406  mov     rcx, [rax+rsi*8]
0x18002240a  mov     rax, [rcx]
0x18002240d  mov     rax, [rax+18h]
0x180022411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022416  mov     rcx, [rdi]
0x180022419  mov     rbx, rax
0x18002241c  mov     rax, [rcx+18h]
0x180022420  mov     rcx, rdi
0x180022423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022428  or      ecx, 0FFFFFFFFh
0x18002242b  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180022433  mov     r9d, ecx; cchCount2
0x180022436  mov     edx, ecx; cchCount1
0x180022438  mov     rcx, rax; lpString1
0x18002243b  mov     r8, rbx; lpString2
0x18002243e  call    cs:__imp_CompareStringOrdinal
0x180022444  cmp     eax, 2
0x180022447  jnz     loc_1800224EB
0x18002244d  mov     rax, [rdi]
0x180022450  mov     rcx, rdi
0x180022453  mov     rax, [rax+20h]
0x180022457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002245c  test    rax, rax
0x18002245f  jz      short loc_1800224C1
0x180022461  mov     rax, [r14]
0x180022464  mov     rcx, [rax+rsi*8]
0x180022468  mov     rax, [rcx]
0x18002246b  mov     rax, [rax+20h]
0x18002246f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022474  test    rax, rax
0x180022477  jz      short loc_1800224C1
0x180022479  mov     rax, [r14]
0x18002247c  mov     rcx, [rax+rsi*8]
0x180022480  mov     rax, [rcx]
0x180022483  mov     rax, [rax+20h]
0x180022487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002248c  mov     rcx, [rdi]
0x18002248f  mov     rbx, rax
0x180022492  mov     rax, [rcx+20h]
0x180022496  mov     rcx, rdi
0x180022499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002249e  or      r12d, 0FFFFFFFFh
0x1800224a2  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800224aa  mov     r9d, r12d; cchCount2
0x1800224ad  mov     edx, r12d; cchCount1
0x1800224b0  mov     r8, rbx; lpString2
0x1800224b3  mov     rcx, rax; lpString1
0x1800224b6  call    cs:__imp_CompareStringOrdinal
0x1800224bc  cmp     eax, 2
0x1800224bf  jmp     short loc_1800224E9
0x1800224c1  mov     rax, [r14]
0x1800224c4  mov     rcx, [rax+rsi*8]
0x1800224c8  mov     rax, [rcx]
0x1800224cb  mov     rax, [rax+20h]
0x1800224cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d4  mov     rcx, [rdi]
0x1800224d7  mov     rbx, rax
0x1800224da  mov     rax, [rcx+20h]
0x1800224de  mov     rcx, rdi
0x1800224e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e6  cmp     rax, rbx
0x1800224e9  jz      short loc_1800224F2
0x1800224eb  inc     esi
0x1800224ed  jmp     loc_1800223F3
0x1800224f2  mov     edx, esi
0x1800224f4  mov     rcx, r14
0x1800224f7  call    ?RemoveAt@?$CTUnkArray@VFSMCameraDeviceProperty@@@@QEAAHK@Z; CTUnkArray<FSMCameraDeviceProperty>::RemoveAt(ulong)
0x1800224fc  mov     esi, [rbp+230h]
0x180022502  mov     rcx, r15
0x180022505  lea     edx, [rsi+1]
0x180022508  call    ?SetSize@?$CTEntryArray@PEAUIFSConfigurationEntry@@@@QEAAHKK@Z; CTEntryArray<IFSConfigurationEntry *>::SetSize(ulong,ulong)
0x18002250d  test    eax, eax
0x18002250f  jnz     short loc_180022544
0x180022511  mov     ebx, 8007000Eh
0x180022516  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002251b  cmp     al, 1
0x18002251d  jb      short loc_180022561
0x18002251f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022526  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18002252d  mov     edx, 114h
0x180022532  mov     [rsp+78h+bIgnoreCase], ebx
0x180022536  mov     r9, rbp
0x180022539  mov     rcx, [rcx+10h]
0x18002253d  call    WPP_SF_qD
0x180022542  jmp     short loc_180022561
0x180022544  mov     rcx, [r15]
0x180022547  xor     ebx, ebx
0x180022549  mov     [rcx+rsi*8], rdi
0x18002254d  test    rdi, rdi
0x180022550  jz      short loc_180022561
0x180022552  mov     rcx, [rdi]
0x180022555  mov     rax, [rcx+8]
0x180022559  mov     rcx, rdi
0x18002255c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022561  mov     eax, ebx
0x180022563  add     rsp, 38h
0x180022567  pop     r15
0x180022569  pop     r14
0x18002256b  pop     r13
0x18002256d  pop     r12
0x18002256f  pop     rdi
0x180022570  pop     rsi
0x180022571  pop     rbp
0x180022572  pop     rbx
0x180022573  retn
```

# FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)

- ea: `0x18004633c`
- end: `0x18004647d`
- name: `?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `321`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18001fb2c`
- `0x180020a0c`
- `0x180024b00`

## callees

- `0x18000261c`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d4f8`
- `0x18004633c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004639c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004639c`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceProperties::CreateFSMDeviceProperties(const struct _GUID *a1, void **a2)
{
  int v3; // edi
  __int64 v4; // rdx
  char *v5; // rbx

  if ( a2 )
  {
    *a2 = 0;
    v5 = (char *)operator new(0x50u);
    if ( v5 )
    {
      *((_DWORD *)v5 + 2) = 1;
      *(_QWORD *)v5 = &FSMCameraDeviceProperties::`vftable';
      InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
      *((_QWORD *)v5 + 7) = 0;
      *(_QWORD *)(v5 + 68) = 0;
      *((_DWORD *)v5 + 16) = 0;
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, v5);
      v3 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))v5)(v5, &GUID_9257d918_c95f_42d2_8bc7_a722fad119b2, a2);
      if ( v3 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, 0, v3);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      v3 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 11;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v3 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v4 = 10;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids, 0, v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004633c  mov     [rsp+arg_0], rbx
0x180046341  push    rdi
0x180046342  sub     rsp, 30h
0x180046346  mov     rdi, rdx
0x180046349  test    rdx, rdx
0x18004634c  jnz     short loc_18004636A
0x18004634e  mov     edi, 80004003h
0x180046353  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046358  cmp     al, 1
0x18004635a  jb      loc_180046470
0x180046360  mov     edx, 0Ah
0x180046365  jmp     loc_180046452
0x18004636a  mov     ecx, 50h ; 'P'; Size
0x18004636f  mov     qword ptr [rdx], 0
0x180046376  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004637b  mov     rbx, rax
0x18004637e  test    rax, rax
0x180046381  jz      loc_18004643F
0x180046387  lea     rax, ??_7FSMCameraDeviceProperties@@6B@; const FSMCameraDeviceProperties::`vftable'
0x18004638e  mov     dword ptr [rbx+8], 1
0x180046395  lea     rcx, [rbx+10h]; lpCriticalSection
0x180046399  mov     [rbx], rax
0x18004639c  call    cs:__imp_InitializeCriticalSection
0x1800463a2  mov     qword ptr [rbx+38h], 0
0x1800463aa  mov     qword ptr [rbx+44h], 0
0x1800463b2  mov     dword ptr [rbx+40h], 0
0x1800463b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800463be  cmp     al, 10h
0x1800463c0  jb      short loc_1800463E4
0x1800463c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463c9  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x1800463d0  mov     edx, 0Dh
0x1800463d5  mov     r9, rbx
0x1800463d8  mov     rcx, [rcx+0D8h]
0x1800463df  call    WPP_SF_q
0x1800463e4  mov     rax, [rbx]
0x1800463e7  lea     rdx, _GUID_9257d918_c95f_42d2_8bc7_a722fad119b2
0x1800463ee  mov     r8, rdi
0x1800463f1  mov     rcx, rbx
0x1800463f4  mov     rax, [rax]
0x1800463f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463fc  mov     edi, eax
0x1800463fe  test    eax, eax
0x180046400  jns     short loc_18004642E
0x180046402  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046407  cmp     al, 1
0x180046409  jb      short loc_18004642E
0x18004640b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046412  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x180046419  mov     edx, 0Ch
0x18004641e  mov     [rsp+38h+var_18], edi
0x180046422  xor     r9d, r9d
0x180046425  mov     rcx, [rcx+10h]
0x180046429  call    WPP_SF_qD
0x18004642e  mov     rax, [rbx]
0x180046431  mov     rcx, rbx
0x180046434  mov     rax, [rax+10h]
0x180046438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004643d  jmp     short loc_180046470
0x18004643f  mov     edi, 8007000Eh
0x180046444  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046449  cmp     al, 1
0x18004644b  jb      short loc_180046470
0x18004644d  mov     edx, 0Bh
0x180046452  mov     rcx, cs:WPP_GLOBAL_Control
0x180046459  lea     r8, WPP_dbd64952e28a33ff92c337baa52cb8c3_Traceguids
0x180046460  xor     r9d, r9d
0x180046463  mov     [rsp+38h+var_18], edi
0x180046467  mov     rcx, [rcx+10h]
0x18004646b  call    WPP_SF_qD
0x180046470  mov     rbx, [rsp+38h+arg_0]
0x180046475  mov     eax, edi
0x180046477  add     rsp, 30h
0x18004647b  pop     rdi
0x18004647c  retn
```

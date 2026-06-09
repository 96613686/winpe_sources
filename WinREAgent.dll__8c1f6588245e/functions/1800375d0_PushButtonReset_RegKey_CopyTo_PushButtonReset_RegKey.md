# PushButtonReset::RegKey::CopyTo(PushButtonReset::RegKey *)

- ea: `0x1800375d0`
- end: `0x180037b68`
- name: `?CopyTo@RegKey@PushButtonReset@@UEAAJPEAV12@@Z`
- size: `1432`
- prototype: `__int64 __fastcall(PushButtonReset::RegKey *__hidden this, struct PushButtonReset::RegKey *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004978`
- `0x1800050bc`
- `0x180005c00`
- `0x180005c70`
- `0x180005cc0`
- `0x18000d5c0`
- `0x18000d6f0`
- `0x18000d740`
- `0x18000d92c`
- `0x180037344`
- `0x1800375d0`
- `0x18006f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180037a19`
- `KERNEL32!HeapAlloc` at `0x180037a19`
- `KERNEL32!GetProcessHeap` at `0x180037a0b`
- `KERNEL32!GetProcessHeap` at `0x180037a0b`

## string_xrefs

- `0x18003762f`: `base\reset\util\src\registry.cpp`
- `0x180037775`: `base\reset\util\src\registry.cpp`
- `0x1800377b2`: `base\reset\util\src\registry.cpp`
- `0x1800377f5`: `base\reset\util\src\registry.cpp`
- `0x180037960`: `base\reset\util\src\registry.cpp`
- `0x1800379e9`: `base\reset\util\src\registry.cpp`
- `0x180037a4f`: `base\reset\util\src\registry.cpp`
- `0x180037b0f`: `base\reset\util\src\registry.cpp`
- `0x180037636`: `PushButtonReset::RegKey::CopyTo`
- `0x18003777c`: `PushButtonReset::RegKey::CopyTo`
- `0x1800377b9`: `PushButtonReset::RegKey::CopyTo`
- `0x1800377fc`: `PushButtonReset::RegKey::CopyTo`
- `0x180037967`: `PushButtonReset::RegKey::CopyTo`
- `0x1800379f0`: `PushButtonReset::RegKey::CopyTo`
- `0x180037a56`: `PushButtonReset::RegKey::CopyTo`
- `0x180037b16`: `PushButtonReset::RegKey::CopyTo`
- `0x1800377e1`: `Failed to open [%s] from source key`
- `0x18003779e`: `Failed to create [%s] under target key`
- `0x180037761`: `Failed to copy [%s]`
- `0x18003794c`: `Failed to read value [%s] from source key`
- `0x180037931`: `Failed to write value [%s] to target key`
- `0x1800379d5`: `Failed to get size of security info`
- `0x180037ab6`: `Failed to read security info from source key`
- `0x180037afb`: `Failed to write security info to target key`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PushButtonReset::RegKey::CopyTo(PushButtonReset::RegKey *this, struct PushButtonReset::RegKey *a2)
{
  int v4; // ebx
  __int64 v5; // r8
  unsigned __int64 i; // r15
  _QWORD *v7; // rax
  __int64 (__fastcall *v8)(PushButtonReset::RegKey *, __int64, __int64); // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  int v11; // edi
  __int64 (__fastcall *v12)(struct PushButtonReset::RegKey *, __int64, __int64); // rdi
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, __int64); // rdi
  __int64 v16; // rax
  __int64 v18; // r8
  unsigned __int64 j; // rsi
  _QWORD *v20; // rax
  __int64 (__fastcall *v21)(PushButtonReset::RegKey *, __int64, __int64); // rdi
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(struct PushButtonReset::RegKey *, __int64, __int64); // rdi
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  HANDLE ProcessHeap; // rax
  __int64 (__fastcall *v29)(PushButtonReset::RegKey *, __int64, __int64, SIZE_T *); // rbx
  __int64 v30; // rax
  __int64 (__fastcall *v31)(struct PushButtonReset::RegKey *, __int64, __int64); // rbx
  __int64 v32; // rax
  __int64 v33[2]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v34[2]; // [rsp+50h] [rbp-39h] BYREF
  void **v35; // [rsp+60h] [rbp-29h] BYREF
  __int64 v36; // [rsp+68h] [rbp-21h]
  __int64 v37; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v38; // [rsp+78h] [rbp-11h]
  __int64 v39; // [rsp+80h] [rbp-9h]
  int v40; // [rsp+88h] [rbp-1h]
  __int64 v41; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp+Fh]
  __int64 v43; // [rsp+A0h] [rbp+17h]
  int v44; // [rsp+A8h] [rbp+1Fh]
  SIZE_T dwBytes; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v46; // [rsp+100h] [rbp+77h] BYREF

  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v4 = (*(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64 *))(*(_QWORD *)this + 56LL))(this, &v37);
  if ( v4 >= 0 )
  {
    for ( i = 0; i < v38; ++i )
    {
      v7 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                       &v37,
                       i,
                       v5);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v46,
        v7);
      v34[1] = 0;
      v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      v8 = *(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64, __int64))(*(_QWORD *)this + 24LL);
      v9 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v34);
      v10 = v46;
      v11 = v8(this, v46, v9);
      if ( v11 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::RegKey::CopyTo",
          "base\\reset\\util\\src\\registry.cpp",
          282,
          L"Failed to open [%s] from source key",
          v10);
        goto LABEL_13;
      }
      v36 = 0;
      v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      v12 = *(__int64 (__fastcall **)(struct PushButtonReset::RegKey *, __int64, __int64))(*(_QWORD *)a2 + 32LL);
      v13 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v35);
      v11 = v12(a2, v10, v13);
      if ( v11 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::RegKey::CopyTo",
          "base\\reset\\util\\src\\registry.cpp",
          286,
          L"Failed to create [%s] under target key",
          v10);
LABEL_11:
        v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v35);
LABEL_13:
        v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v34);
        ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
LABEL_14:
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v37);
        return (unsigned int)v11;
      }
      v14 = (*(__int64 (__fastcall **)(_QWORD *))(v34[0] + 24LL))(v34);
      v15 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 160LL);
      v16 = ((__int64 (__fastcall *)(void ***))v35[4])(&v35);
      v11 = v15(v14, v16);
      if ( v11 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::RegKey::CopyTo",
          "base\\reset\\util\\src\\registry.cpp",
          289,
          L"Failed to copy [%s]",
          v10);
        goto LABEL_11;
      }
      v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v35);
      v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v34);
      ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    }
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v4 = (*(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64 *))(*(_QWORD *)this + 152LL))(this, &v41);
    if ( v4 >= 0 )
    {
      for ( j = 0; j < v42; ++j )
      {
        v20 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                          &v41,
                          j,
                          v18);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v46,
          v20);
        v36 = 0;
        v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable';
        v21 = *(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64, __int64))(*(_QWORD *)this + 104LL);
        v22 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v35);
        v23 = v46;
        v11 = v21(this, v46, v22);
        if ( v11 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v11,
            "PushButtonReset::RegKey::CopyTo",
            "base\\reset\\util\\src\\registry.cpp",
            303,
            L"Failed to read value [%s] from source key",
            v23);
          goto LABEL_24;
        }
        v24 = *(__int64 (__fastcall **)(struct PushButtonReset::RegKey *, __int64, __int64))(*(_QWORD *)a2 + 120LL);
        v25 = ((__int64 (__fastcall *)(void ***))v35[4])(&v35);
        v11 = v24(a2, v23, v25);
        if ( v11 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v11,
            "PushButtonReset::RegKey::CopyTo",
            "base\\reset\\util\\src\\registry.cpp",
            306,
            L"Failed to write value [%s] to target key",
            v23);
LABEL_24:
          v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(&v35);
          ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
          goto LABEL_14;
        }
        v35 = &RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(&v35);
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      }
      LODWORD(dwBytes) = 0;
      v26 = (*(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64, _QWORD, SIZE_T *))(*(_QWORD *)this + 8LL))(
              this,
              15,
              0,
              &dwBytes);
      v4 = v26;
      if ( v26 == -2147024774 || v26 == -2147024662 || v26 >= 0 )
      {
        v27 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v33[1] = (__int64)HeapAlloc(ProcessHeap, 0, v27);
        v33[0] = (__int64)&RAII::CAutoPbrHeapFree<_SECURITY_DESCRIPTOR *>::`vftable';
        if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v33) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147942414LL,
            "PushButtonReset::RegKey::CopyTo",
            "base\\reset\\util\\src\\registry.cpp",
            328,
            L"Failed to allocate desc");
          v33[0] = (__int64)&RAII::CAutoPbrHeapFree<_SECURITY_DESCRIPTOR *>::`vftable';
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v33);
          v4 = -2147024882;
        }
        else
        {
          v29 = *(__int64 (__fastcall **)(PushButtonReset::RegKey *, __int64, __int64, SIZE_T *))(*(_QWORD *)this + 8LL);
          v30 = (*(__int64 (__fastcall **)(__int64 *))(v33[0] + 32))(v33);
          v4 = v29(this, 15, v30, &dwBytes);
          if ( v4 >= 0 )
          {
            v31 = *(__int64 (__fastcall **)(struct PushButtonReset::RegKey *, __int64, __int64))(*(_QWORD *)a2 + 16LL);
            v32 = (*(__int64 (__fastcall **)(__int64 *))(v33[0] + 32))(v33);
            v4 = v31(a2, 15, v32);
            if ( v4 < 0 )
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v4,
                "PushButtonReset::RegKey::CopyTo",
                "base\\reset\\util\\src\\registry.cpp",
                334,
                L"Failed to write security info to target key");
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v4,
              "PushButtonReset::RegKey::CopyTo",
              "base\\reset\\util\\src\\registry.cpp",
              331,
              L"Failed to read security info from source key");
          }
          v33[0] = (__int64)&RAII::CAutoPbrHeapFree<_SECURITY_DESCRIPTOR *>::`vftable';
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v33);
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v26,
          "PushButtonReset::RegKey::CopyTo",
          "base\\reset\\util\\src\\registry.cpp",
          324,
          L"Failed to get size of security info");
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v4,
        "PushButtonReset::RegKey::CopyTo",
        "base\\reset\\util\\src\\registry.cpp",
        295,
        L"Failed to enumerate values");
    }
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v4,
      "PushButtonReset::RegKey::CopyTo",
      "base\\reset\\util\\src\\registry.cpp",
      274,
      L"Failed to enumerate subkeys");
  }
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v37);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800375d0  mov     [rsp-8+arg_8], rbx
0x1800375d5  push    rbp
0x1800375d6  push    rsi
0x1800375d7  push    rdi
0x1800375d8  push    r12
0x1800375da  push    r13
0x1800375dc  push    r14
0x1800375de  push    r15
0x1800375e0  lea     rbp, [rsp-27h]
0x1800375e5  sub     rsp, 0B0h
0x1800375ec  mov     r12, rdx
0x1800375ef  mov     r14, rcx
0x1800375f2  xor     r13d, r13d
0x1800375f5  mov     [rbp+57h+var_70], r13
0x1800375f9  mov     [rbp+57h+var_68], r13
0x1800375fd  mov     [rbp+57h+var_60], r13
0x180037601  mov     [rbp+57h+var_58], r13d
0x180037605  mov     rax, [rcx]
0x180037608  lea     rdx, [rbp+57h+var_70]
0x18003760c  mov     rax, [rax+38h]
0x180037610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037615  mov     ebx, eax
0x180037617  test    eax, eax
0x180037619  jns     short loc_18003764D
0x18003761b  lea     rax, aFailedToEnumer_11; "Failed to enumerate subkeys"
0x180037622  mov     [rsp+0E0h+var_B8], rax
0x180037627  mov     [rsp+0E0h+var_C0], 112h
0x18003762f  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x180037636  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x18003763d  mov     edx, ebx
0x18003763f  lea     ecx, [r13+2]
0x180037643  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180037648  jmp     loc_180037B42
0x18003764d  mov     r15, r13
0x180037650  lea     rsi, ??_7?$CAutoPbrDelete@PEAVRegKey@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable'
0x180037657  cmp     r15, [rbp+57h+var_68]
0x18003765b  jnb     loc_180037838
0x180037661  mov     rdx, r15
0x180037664  lea     rcx, [rbp+57h+var_70]
0x180037668  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18003766d  mov     rdx, rax
0x180037670  lea     rcx, [rbp+57h+arg_10]
0x180037674  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180037679  nop
0x18003767a  mov     [rbp+57h+var_88], r13
0x18003767e  mov     [rbp+57h+var_90], rsi
0x180037682  mov     rax, [r14]
0x180037685  mov     rdi, [rax+18h]
0x180037689  lea     rcx, [rbp+57h+var_90]
0x18003768d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180037692  mov     r8, rax
0x180037695  mov     rbx, [rbp+57h+arg_10]
0x180037699  mov     rdx, rbx
0x18003769c  mov     rcx, r14
0x18003769f  mov     rax, rdi
0x1800376a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376a7  mov     edi, eax
0x1800376a9  test    eax, eax
0x1800376ab  js      loc_1800377DC
0x1800376b1  mov     [rbp+57h+var_78], r13
0x1800376b5  mov     [rbp+57h+var_80], rsi
0x1800376b9  mov     rax, [r12]
0x1800376bd  mov     rdi, [rax+20h]
0x1800376c1  lea     rcx, [rbp+57h+var_80]
0x1800376c5  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800376ca  mov     r8, rax
0x1800376cd  mov     rdx, rbx
0x1800376d0  mov     rcx, r12
0x1800376d3  mov     rax, rdi
0x1800376d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376db  mov     edi, eax
0x1800376dd  test    eax, eax
0x1800376df  js      loc_180037799
0x1800376e5  mov     rax, [rbp+57h+var_90]
0x1800376e9  lea     rcx, [rbp+57h+var_90]
0x1800376ed  mov     rax, [rax+18h]
0x1800376f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f6  mov     rsi, rax
0x1800376f9  mov     rcx, [rax]
0x1800376fc  mov     rdi, [rcx+0A0h]
0x180037703  mov     rcx, [rbp+57h+var_80]
0x180037707  mov     rax, [rcx+20h]
0x18003770b  lea     rcx, [rbp+57h+var_80]
0x18003770f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037714  mov     rdx, rax
0x180037717  mov     rcx, rsi
0x18003771a  mov     rax, rdi
0x18003771d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037722  mov     edi, eax
0x180037724  test    eax, eax
0x180037726  js      short loc_18003775C
0x180037728  lea     rsi, ??_7?$CAutoPbrDelete@PEAVRegKey@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable'
0x18003772f  mov     [rbp+57h+var_80], rsi
0x180037733  lea     rcx, [rbp+57h+var_80]
0x180037737  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18003773c  nop
0x18003773d  mov     [rbp+57h+var_90], rsi
0x180037741  lea     rcx, [rbp+57h+var_90]
0x180037745  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18003774a  nop
0x18003774b  lea     rcx, [rbx-18h]; this
0x18003774f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037754  inc     r15
0x180037757  jmp     loc_180037657
0x18003775c  mov     [rsp+0E0h+var_B0], rbx
0x180037761  lea     rax, aFailedToCopyS; "Failed to copy [%s]"
0x180037768  mov     [rsp+0E0h+var_B8], rax
0x18003776d  mov     [rsp+0E0h+var_C0], 121h
0x180037775  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x18003777c  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x180037783  mov     edx, edi
0x180037785  mov     ecx, 2
0x18003778a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003778f  nop
0x180037790  lea     rsi, ??_7?$CAutoPbrDelete@PEAVRegKey@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable'
0x180037797  jmp     short loc_1800377CD
0x180037799  mov     [rsp+0E0h+var_B0], rbx
0x18003779e  lea     rax, aFailedToCreate_22; "Failed to create [%s] under target key"
0x1800377a5  mov     [rsp+0E0h+var_B8], rax
0x1800377aa  mov     [rsp+0E0h+var_C0], 11Eh
0x1800377b2  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800377b9  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x1800377c0  mov     edx, edi
0x1800377c2  mov     ecx, 2
0x1800377c7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800377cc  nop
0x1800377cd  mov     [rbp+57h+var_80], rsi
0x1800377d1  lea     rcx, [rbp+57h+var_80]
0x1800377d5  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x1800377da  jmp     short loc_180037810
0x1800377dc  mov     [rsp+0E0h+var_B0], rbx
0x1800377e1  lea     rax, aFailedToOpenSF_0; "Failed to open [%s] from source key"
0x1800377e8  mov     [rsp+0E0h+var_B8], rax
0x1800377ed  mov     [rsp+0E0h+var_C0], 11Ah
0x1800377f5  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800377fc  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x180037803  mov     edx, edi
0x180037805  mov     ecx, 2
0x18003780a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003780f  nop
0x180037810  mov     [rbp+57h+var_90], rsi
0x180037814  lea     rcx, [rbp+57h+var_90]
0x180037818  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18003781d  nop
0x18003781e  lea     rcx, [rbx-18h]; this
0x180037822  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037827  nop
0x180037828  lea     rcx, [rbp+57h+var_70]
0x18003782c  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x180037831  mov     eax, edi
0x180037833  jmp     loc_180037B4D
0x180037838  mov     [rbp+57h+var_50], r13
0x18003783c  mov     [rbp+57h+var_48], r13
0x180037840  mov     [rbp+57h+var_40], r13
0x180037844  mov     [rbp+57h+var_38], r13d
0x180037848  mov     rax, [r14]
0x18003784b  lea     rdx, [rbp+57h+var_50]
0x18003784f  mov     rcx, r14
0x180037852  mov     rax, [rax+98h]
0x180037859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003785e  mov     ebx, eax
0x180037860  test    eax, eax
0x180037862  jns     short loc_18003787D
0x180037864  lea     rax, aFailedToEnumer_3; "Failed to enumerate values"
0x18003786b  mov     [rsp+0E0h+var_B8], rax
0x180037870  mov     [rsp+0E0h+var_C0], 127h
0x180037878  jmp     loc_1800379E9
0x18003787d  mov     rsi, r13
0x180037880  lea     r15, ??_7?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable'
0x180037887  cmp     rsi, [rbp+57h+var_48]
0x18003788b  jnb     loc_1800379A1
0x180037891  mov     rdx, rsi
0x180037894  lea     rcx, [rbp+57h+var_50]
0x180037898  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18003789d  mov     rdx, rax
0x1800378a0  lea     rcx, [rbp+57h+arg_10]
0x1800378a4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800378a9  nop
0x1800378aa  mov     [rbp+57h+var_78], r13
0x1800378ae  mov     [rbp+57h+var_80], r15
0x1800378b2  mov     rax, [r14]
0x1800378b5  mov     rdi, [rax+68h]
0x1800378b9  lea     rcx, [rbp+57h+var_80]
0x1800378bd  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800378c2  mov     r8, rax
0x1800378c5  mov     rbx, [rbp+57h+arg_10]
0x1800378c9  mov     rdx, rbx
0x1800378cc  mov     rcx, r14
0x1800378cf  mov     rax, rdi
0x1800378d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378d7  mov     edi, eax
0x1800378d9  test    eax, eax
0x1800378db  js      short loc_180037947
0x1800378dd  mov     rax, [r12]
0x1800378e1  mov     rdi, [rax+78h]
0x1800378e5  mov     rcx, [rbp+57h+var_80]
0x1800378e9  mov     rax, [rcx+20h]
0x1800378ed  lea     rcx, [rbp+57h+var_80]
0x1800378f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378f6  mov     r8, rax
0x1800378f9  mov     rdx, rbx
0x1800378fc  mov     rcx, r12
0x1800378ff  mov     rax, rdi
0x180037902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037907  mov     edi, eax
0x180037909  test    eax, eax
0x18003790b  js      short loc_18003792C
0x18003790d  mov     [rbp+57h+var_80], r15
0x180037911  lea     rcx, [rbp+57h+var_80]
0x180037915  call    ?Release@?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(void)
0x18003791a  nop
0x18003791b  lea     rcx, [rbx-18h]; this
0x18003791f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037924  inc     rsi
0x180037927  jmp     loc_180037887
0x18003792c  mov     [rsp+0E0h+var_B0], rbx
0x180037931  lea     rax, aFailedToWriteV; "Failed to write value [%s] to target ke"...
0x180037938  mov     [rsp+0E0h+var_B8], rax
0x18003793d  mov     [rsp+0E0h+var_C0], 132h
0x180037945  jmp     short loc_180037960
0x180037947  mov     [rsp+0E0h+var_B0], rbx
0x18003794c  lea     rax, aFailedToReadVa_1; "Failed to read value [%s] from source k"...
0x180037953  mov     [rsp+0E0h+var_B8], rax
0x180037958  mov     [rsp+0E0h+var_C0], 12Fh
0x180037960  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x180037967  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x18003796e  mov     edx, edi
0x180037970  mov     ecx, 2
0x180037975  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003797a  nop
0x18003797b  mov     [rbp+57h+var_80], r15
0x18003797f  lea     rcx, [rbp+57h+var_80]
0x180037983  call    ?Release@?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(void)
0x180037988  nop
0x180037989  lea     rcx, [rbx-18h]; this
0x18003798d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180037992  nop
0x180037993  lea     rcx, [rbp+57h+var_50]
0x180037997  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18003799c  jmp     loc_180037828
0x1800379a1  mov     dword ptr [rbp+57h+dwBytes], r13d
0x1800379a5  mov     rax, [r14]
0x1800379a8  lea     r9, [rbp+57h+dwBytes]
0x1800379ac  xor     r8d, r8d
0x1800379af  lea     esi, [r8+0Fh]
0x1800379b3  mov     edx, esi
0x1800379b5  mov     rcx, r14
0x1800379b8  mov     rax, [rax+8]
0x1800379bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379c1  mov     ebx, eax
0x1800379c3  cmp     eax, 8007007Ah
0x1800379c8  jz      short loc_180037A08
0x1800379ca  cmp     eax, 800700EAh
0x1800379cf  jz      short loc_180037A08
0x1800379d1  test    eax, eax
0x1800379d3  jns     short loc_180037A08
0x1800379d5  lea     rax, aFailedToGetSiz_1; "Failed to get size of security info"
0x1800379dc  mov     [rsp+0E0h+var_B8], rax
0x1800379e1  mov     [rsp+0E0h+var_C0], 144h
0x1800379e9  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800379f0  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x1800379f7  mov     edx, ebx
0x1800379f9  mov     ecx, 2
0x1800379fe  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180037a03  jmp     loc_180037B38
0x180037a08  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180037a0b  call    cs:__imp_GetProcessHeap
0x180037a11  mov     rcx, rax; hHeap
0x180037a14  mov     r8d, ebx; dwBytes
0x180037a17  xor     edx, edx; dwFlags
0x180037a19  call    cs:__imp_HeapAlloc
0x180037a1f  mov     [rbp+57h+var_98], rax
0x180037a23  lea     rdi, ??_7?$CAutoPbrHeapFree@PEAU_SECURITY_DESCRIPTOR@@@RAII@@6B@; const RAII::CAutoPbrHeapFree<_SECURITY_DESCRIPTOR *>::`vftable'
0x180037a2a  mov     [rbp+57h+var_A0], rdi
0x180037a2e  lea     rcx, [rbp+57h+var_A0]
0x180037a32  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180037a37  test    al, al
0x180037a39  jz      short loc_180037A84
0x180037a3b  lea     rax, aFailedToAlloca_29; "Failed to allocate desc"
0x180037a42  mov     [rsp+0E0h+var_B8], rax
0x180037a47  mov     [rsp+0E0h+var_C0], 148h
0x180037a4f  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x180037a56  lea     r8, aPushbuttonrese_79; "PushButtonReset::RegKey::CopyTo"
0x180037a5d  mov     edx, 8007000Eh
0x180037a62  mov     ecx, 2
0x180037a67  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180037a6c  nop
0x180037a6d  mov     [rbp+57h+var_A0], rdi
0x180037a71  lea     rcx, [rbp+57h+var_A0]
0x180037a75  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180037a7a  mov     ebx, 8007000Eh
0x180037a7f  jmp     loc_180037B38
0x180037a84  mov     rax, [r14]
0x180037a87  mov     rbx, [rax+8]
0x180037a8b  mov     rcx, [rbp+57h+var_A0]
0x180037a8f  mov     rax, [rcx+20h]
0x180037a93  lea     rcx, [rbp+57h+var_A0]
0x180037a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a9c  lea     r9, [rbp+57h+dwBytes]
0x180037aa0  mov     r8, rax
  ... truncated ...
```

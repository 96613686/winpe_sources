# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000d9a4`
- end: `0x18000dc29`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `645`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d790`
- `0x18000dc30`
- `0x18000e5ac`

## callees

- `0x180001800`
- `0x18000980c`
- `0x18000b290`
- `0x18000d9a4`
- `0x18000e8b8`
- `0x180035010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d9ff`
- `KERNEL32!EnterCriticalSection` at `0x18000d9ff`
- `KERNEL32!LeaveCriticalSection` at `0x18000dbfd`
- `KERNEL32!LeaveCriticalSection` at `0x18000dbfd`
- `KERNEL32!GetModuleFileNameW` at `0x18000da88`
- `KERNEL32!GetModuleFileNameW` at `0x18000da88`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000daab`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000daab`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000dac0`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000dac0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  ATL::CComTypeInfoHolder *v5; // rcx
  int NameCache; // ebx
  DWORD ModuleFileNameW; // eax
  HRESULT v8; // eax
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rcx
  unsigned __int64 v10; // r8
  struct ITypeInfo *v11; // rax
  struct ITypeInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v15[2])(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( qword_18004B948 && qword_18004B958 )
    return 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v15[1] = (void (__fastcall ***)(_QWORD, GUID *, __int64))((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v16 = 1;
  if ( qword_18004B948 )
  {
    NameCache = 0;
  }
  else
  {
    pptlib = 0;
    if ( ATL::CAtlModule::m_libid.Data1 != rguid->Data1
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)&rguid->Data2
      || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)rguid->Data4
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)&rguid->Data4[4]
      || *(_DWORD *)&wVerMajor != -1 )
    {
      v8 = LoadRegTypeLib(rguid, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_14:
      NameCache = v8;
      if ( v8 >= 0 )
      {
        v14 = 0;
        NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                      pptlib,
                      ATL::IDispatchImpl<IAxWinAmbientDispatchEx,&__s_GUID const _GUID_b2d0778b_ac99_4c58_a5c8_e7724e5316b5,&public: static _GUID ATL::CAtlModule::m_libid,65535,65535,ATL::CComTypeInfoHolder>::_tih[0],
                      &v14);
        if ( NameCache >= 0 )
        {
          v9 = v14;
          v12 = (struct ITypeInfo *)v14;
          if ( v14 )
          {
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[1])(v14);
            v9 = v14;
          }
          v15[0] = 0;
          if ( (**v9)(v9, &GUID_00020412_0000_0000_c000_000000000046, v15) >= 0 )
            ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v12, v15);
          v11 = v12;
          v12 = 0;
          qword_18004B948 = v11;
          ATL::AtlModuleAddTermFunc(
            (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
            (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
            v10);
          if ( v15[0] )
            (*((void (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64)))*v15[0] + 2))(v15[0]);
          if ( v12 )
            ((void (__fastcall *)(struct ITypeInfo *))v12->lpVtbl->Release)(v12);
        }
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        v5 = (ATL::CComTypeInfoHolder *)v14;
        if ( v14 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[2])(v14);
      }
      goto LABEL_28;
    }
    NameCache = -2147467259;
    ModuleFileNameW = GetModuleFileNameW(hInst, Filename, 0x104u);
    if ( ModuleFileNameW && ModuleFileNameW != 260 )
    {
      v8 = LoadTypeLib(Filename, &pptlib);
      goto LABEL_14;
    }
  }
LABEL_28:
  if ( qword_18004B948 )
  {
    if ( !qword_18004B958 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_18004B948);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18000d9a4  mov     [rsp-8+arg_0], rbx
0x18000d9a9  mov     [rsp-8+arg_10], rdi
0x18000d9ae  push    rbp
0x18000d9af  lea     rbp, [rsp-180h]
0x18000d9b7  sub     rsp, 280h
0x18000d9be  mov     rax, cs:__security_cookie
0x18000d9c5  xor     rax, rsp
0x18000d9c8  mov     [rbp+180h+var_10], rax
0x18000d9cf  mov     ebx, edx
0x18000d9d1  cmp     cs:qword_18004B948, 0
0x18000d9d9  jz      short loc_18000D9EC
0x18000d9db  cmp     cs:qword_18004B958, 0
0x18000d9e3  jz      short loc_18000D9EC
0x18000d9e5  xor     eax, eax
0x18000d9e7  jmp     loc_18000DC05
0x18000d9ec  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d9f3  add     rdi, 18h
0x18000d9f7  mov     [rsp+280h+var_230], rdi
0x18000d9fc  mov     rcx, rdi; lpCriticalSection
0x18000d9ff  call    cs:__imp_EnterCriticalSection
0x18000da05  mov     [rsp+280h+var_228], 1
0x18000da0a  cmp     cs:qword_18004B948, 0
0x18000da12  jnz     loc_18000DBDB
0x18000da18  mov     [rsp+280h+pptlib], 0
0x18000da21  mov     r8, cs:wVerMajor+2; wVerMinor
0x18000da28  mov     rdx, cs:wVerMajor; wVerMajor
0x18000da2f  mov     rcx, cs:rguid; rguid
0x18000da36  mov     eax, [rcx]
0x18000da38  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000da3e  jnz     short loc_18000DAB3
0x18000da40  mov     eax, [rcx+4]
0x18000da43  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000da49  jnz     short loc_18000DAB3
0x18000da4b  mov     eax, [rcx+8]
0x18000da4e  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000da54  jnz     short loc_18000DAB3
0x18000da56  mov     eax, [rcx+0Ch]
0x18000da59  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000da5f  jnz     short loc_18000DAB3
0x18000da61  mov     eax, 0FFFFh
0x18000da66  cmp     dx, ax
0x18000da69  jnz     short loc_18000DAB3
0x18000da6b  cmp     r8w, ax
0x18000da6f  jnz     short loc_18000DAB3
0x18000da71  mov     ebx, 80004005h
0x18000da76  mov     r8d, 104h; nSize
0x18000da7c  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000da81  mov     rcx, cs:hInst; hModule
0x18000da88  call    cs:__imp_GetModuleFileNameW
0x18000da8e  test    eax, eax
0x18000da90  jz      loc_18000DBDD
0x18000da96  cmp     eax, 104h
0x18000da9b  jz      loc_18000DBDD
0x18000daa1  lea     rdx, [rsp+280h+pptlib]; pptlib
0x18000daa6  lea     rcx, [rsp+280h+Filename]; szFile
0x18000daab  call    cs:__imp_LoadTypeLib
0x18000dab1  jmp     short loc_18000DAC6
0x18000dab3  lea     rax, [rsp+280h+pptlib]
0x18000dab8  mov     [rsp+280h+var_260], rax; pptlib
0x18000dabd  mov     r9d, ebx; lcid
0x18000dac0  call    cs:__imp_LoadRegTypeLib
0x18000dac6  mov     ebx, eax
0x18000dac8  test    eax, eax
0x18000daca  js      loc_18000DBDD
0x18000dad0  mov     [rsp+280h+var_240], 0
0x18000dad9  mov     rcx, [rsp+280h+pptlib]
0x18000dade  mov     rax, [rcx]
0x18000dae1  lea     r8, [rsp+280h+var_240]
0x18000dae6  mov     rdx, cs:?_tih@?$IDispatchImpl@UIAxWinAmbientDispatchEx@@$1?_GUID_b2d0778b_ac99_4c58_a5c8_e7724e5316b5@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$0PPPP@$0PPPP@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IAxWinAmbientDispatchEx,&__s_GUID const _GUID_b2d0778b_ac99_4c58_a5c8_e7724e5316b5,&_GUID ATL::CAtlModule::m_libid,65535,65535,ATL::CComTypeInfoHolder>::_tih
0x18000daed  mov     rax, [rax+30h]
0x18000daf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf6  mov     ebx, eax
0x18000daf8  test    eax, eax
0x18000dafa  js      loc_18000DBB0
0x18000db00  mov     rcx, [rsp+280h+var_240]
0x18000db05  mov     [rsp+280h+var_250], rcx
0x18000db0a  test    rcx, rcx
0x18000db0d  jz      short loc_18000DB20
0x18000db0f  mov     rax, [rcx]
0x18000db12  mov     rax, [rax+8]
0x18000db16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db1b  mov     rcx, [rsp+280h+var_240]
0x18000db20  mov     [rsp+280h+var_238], 0
0x18000db29  mov     rax, [rcx]
0x18000db2c  lea     r8, [rsp+280h+var_238]
0x18000db31  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000db38  mov     rax, [rax]
0x18000db3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db40  test    eax, eax
0x18000db42  js      short loc_18000DB53
0x18000db44  lea     rdx, [rsp+280h+var_238]
0x18000db49  lea     rcx, [rsp+280h+var_250]
0x18000db4e  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x18000db53  mov     rax, [rsp+280h+var_250]
0x18000db58  mov     [rsp+280h+var_250], 0
0x18000db61  mov     cs:qword_18004B948, rax
0x18000db68  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000db6f  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x18000db73  neg     rax
0x18000db76  sbb     rcx, rcx
0x18000db79  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18000db7c  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000db81  nop
0x18000db82  mov     rcx, [rsp+280h+var_238]
0x18000db87  test    rcx, rcx
0x18000db8a  jz      short loc_18000DB99
0x18000db8c  mov     rax, [rcx]
0x18000db8f  mov     rax, [rax+10h]
0x18000db93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db98  nop
0x18000db99  mov     rcx, [rsp+280h+var_250]
0x18000db9e  test    rcx, rcx
0x18000dba1  jz      short loc_18000DBB0
0x18000dba3  mov     rax, [rcx]
0x18000dba6  mov     rax, [rax+10h]
0x18000dbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbaf  nop
0x18000dbb0  mov     rcx, [rsp+280h+pptlib]
0x18000dbb5  mov     rax, [rcx]
0x18000dbb8  mov     rax, [rax+10h]
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  nop
0x18000dbc2  mov     rcx, [rsp+280h+var_240]
0x18000dbc7  test    rcx, rcx
0x18000dbca  jz      short loc_18000DBD9
0x18000dbcc  mov     rax, [rcx]
0x18000dbcf  mov     rax, [rax+10h]
0x18000dbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd8  nop
0x18000dbd9  jmp     short loc_18000DBDD
0x18000dbdb  xor     ebx, ebx
0x18000dbdd  mov     rdx, cs:qword_18004B948; struct ITypeInfo *
0x18000dbe4  test    rdx, rdx
0x18000dbe7  jz      short loc_18000DBFA
0x18000dbe9  cmp     cs:qword_18004B958, 0
0x18000dbf1  jnz     short loc_18000DBFA
0x18000dbf3  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000dbf8  mov     ebx, eax
0x18000dbfa  mov     rcx, rdi; lpCriticalSection
0x18000dbfd  call    cs:__imp_LeaveCriticalSection
0x18000dc03  mov     eax, ebx
0x18000dc05  mov     rcx, [rbp+180h+var_10]
0x18000dc0c  xor     rcx, rsp; StackCookie
0x18000dc0f  call    __security_check_cookie
0x18000dc14  lea     r11, [rsp+280h+var_s0]
0x18000dc1c  mov     rbx, [r11+10h]
0x18000dc20  mov     rdi, [r11+20h]
0x18000dc24  mov     rsp, r11
0x18000dc27  pop     rbp
0x18000dc28  retn
```

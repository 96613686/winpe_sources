# CTemplate::CreateTransServiceConfig(int)

- ea: `0x1800133f8`
- end: `0x180013449`
- name: `?CreateTransServiceConfig@CTemplate@@QEAAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(LPVOID *this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800108d0`

## callees

- `0x1800133f8`
- `0x18005d090`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002b9cc`
- `ole32!CoCreateInstance` at `0x18002b9cc`
- `iisutil!PuDbgPrint` at `0x18002bbf1`
- `iisutil!PuDbgPrint` at `0x18002bbf1`

## string_xrefs

- `0x18002bbe5`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002b9ef`: `CTemplate::CreateTransServiceConfig() - Could not CCI ServicesConfig, hr = %#08x\n`
- `0x18002bbde`: `CTemplate::CreateTransServiceConfig`
- `0x18002ba35`: `CTemplate::CreateTransServiceConfig() - Could not QI for IServiceInheritanceConfig, hr = %#08x\n`
- `0x18002bbd0`: `CTemplate::CreateTransServiceConfig() - Could not set Inherit mode, hr = %#08x\n`
- `0x18002bae1`: `CTemplate::CreateTransServiceConfig() - Could not QI for IID_IServiceTransactionConfig, hr = %#08x\n`
- `0x18002bb20`: `CTemplate::CreateTransServiceConfig() - Could not set transaction type, hr = %#08x\n`
- `0x18002bb6b`: `CTemplate::CreateTransServiceConfig() - Could not QI for IID_IServiceTrackerConfig, hr = %#08x\n`

## pseudocode

```c
__int64 __fastcall CTemplate::CreateTransServiceConfig(LPVOID *this, int a2)
{
  int *v2; // rdi
  _QWORD *v6; // r14
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  _WORD *v20; // rbx
  __int64 v21; // r9
  __int64 SourceFileName; // rax
  __int64 v23; // r9
  __int64 v24; // r10
  __int64 v25; // r11
  __int64 v26[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+80h] [rbp+18h] BYREF
  __int64 v28; // [rsp+88h] [rbp+20h] BYREF

  v2 = (int *)this + 99;
  v27 = 0;
  v28 = 0;
  v26[0] = 0;
  if ( !a2 && !*v2 )
    return 0;
  v6 = this + 60;
  Instance = CoCreateInstance(&CLSID_CServiceConfig, 0, 1u, &IID_IUnknown, this + 60);
  v8 = Instance;
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 7) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
        8195,
        "CTemplate::CreateTransServiceConfig",
        "CTemplate::CreateTransServiceConfig() - Could not CCI ServicesConfig, hr = %#08x\n",
        Instance);
    goto LABEL_37;
  }
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6)(*v6, &IID_IServiceInheritanceConfig, &v27);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 7) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
        8201,
        "CTemplate::CreateTransServiceConfig",
        "CTemplate::CreateTransServiceConfig() - Could not QI for IServiceInheritanceConfig, hr = %#08x\n",
        v9);
    goto LABEL_37;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, 0);
  v8 = v10;
  if ( v10 >= 0 )
  {
    v12 = *v2;
    if ( *v2 )
    {
      v13 = 0;
      v14 = v12 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 2;
          if ( v16 )
          {
            if ( v16 == 4 )
              v13 = 3;
          }
          else
          {
            v13 = 2;
          }
        }
        else
        {
          v13 = 1;
        }
      }
      v17 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6)(*v6, &IID_IServiceTransactionConfig, &v28);
      v8 = v17;
      if ( v17 < 0 )
      {
        if ( (g_dwDebugFlags & 7) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
            8232,
            "CTemplate::CreateTransServiceConfig",
            "CTemplate::CreateTransServiceConfig() - Could not QI for IID_IServiceTransactionConfig, hr = %#08x\n",
            v17);
        goto LABEL_37;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, v13);
      v8 = v18;
      if ( v18 < 0 )
      {
        if ( (g_dwDebugFlags & 7) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
            8238,
            "CTemplate::CreateTransServiceConfig",
            "CTemplate::CreateTransServiceConfig() - Could not set transaction type, hr = %#08x\n",
            v18);
        goto LABEL_37;
      }
    }
    if ( a2 )
    {
      v19 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6)(*v6, &IID_IServiceTrackerConfig, v26);
      v8 = v19;
      if ( v19 < 0 )
      {
        if ( (g_dwDebugFlags & 7) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
            8246,
            "CTemplate::CreateTransServiceConfig",
            "CTemplate::CreateTransServiceConfig() - Could not QI for IID_IServiceTrackerConfig, hr = %#08x\n",
            v19);
        goto LABEL_37;
      }
      v20 = this[47];
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      SourceFileName = CTemplate::GetSourceFileName(this, 0);
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *, __int64))(v24 + 24))(
              v25,
              1,
              v20,
              SourceFileName + 2 + 2 * v23);
      v8 = v10;
      if ( v10 < 0 && (g_dwDebugFlags & 7) != 0 )
      {
        v11 = 8273;
        goto LABEL_36;
      }
    }
  }
  else if ( (g_dwDebugFlags & 7) != 0 )
  {
    v11 = 8207;
LABEL_36:
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
      v11,
      "CTemplate::CreateTransServiceConfig",
      "CTemplate::CreateTransServiceConfig() - Could not set Inherit mode, hr = %#08x\n",
      v10);
  }
LABEL_37:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return v8;
}

```

## disassembly

```asm
0x1800133f8  mov     rax, rsp
0x1800133fb  mov     [rax+8], rbx
0x1800133ff  push    rbp
0x180013400  push    rsi
0x180013401  push    rdi
0x180013402  push    r14
0x180013404  push    r15
0x180013406  sub     rsp, 40h
0x18001340a  xor     r15d, r15d
0x18001340d  lea     rdi, [rcx+18Ch]
0x180013414  mov     [rax+18h], r15
0x180013418  mov     ebp, edx
0x18001341a  mov     [rax+20h], r15
0x18001341e  mov     rsi, rcx
0x180013421  mov     [rax-38h], r15
0x180013425  test    edx, edx
0x180013427  jnz     loc_18002B9AC
0x18001342d  cmp     [rdi], r15d
0x180013430  jnz     loc_18002B9AC
0x180013436  xor     eax, eax
0x180013438  mov     rbx, [rsp+68h+arg_0]
0x18001343d  add     rsp, 40h
0x180013441  pop     r15
0x180013443  pop     r14
0x180013445  pop     rdi
0x180013446  pop     rsi
0x180013447  pop     rbp
0x180013448  retn
0x18002b9ac  lea     r14, [rcx+1E0h]
0x18002b9b3  xor     edx, edx; pUnkOuter
0x18002b9b5  lea     r9, IID_IUnknown; riid
0x18002b9bc  mov     [rsp+68h+ppv], r14; ppv
0x18002b9c1  lea     rcx, CLSID_CServiceConfig; rclsid
0x18002b9c8  lea     r8d, [rdx+1]; dwClsContext
0x18002b9cc  call    cs:__imp_CoCreateInstance
0x18002b9d2  mov     ebx, eax
0x18002b9d4  test    eax, eax
0x18002b9d6  jns     short loc_18002B9FB
0x18002b9d8  test    byte ptr cs:g_dwDebugFlags, 7
0x18002b9df  jz      loc_18002BBF7
0x18002b9e5  mov     [rsp+68h+var_40], eax
0x18002b9e9  mov     r8d, 2003h
0x18002b9ef  lea     rax, aCtemplateCreat_1; "CTemplate::CreateTransServiceConfig() -"...
0x18002b9f6  jmp     loc_18002BBD7
0x18002b9fb  mov     rcx, [r14]
0x18002b9fe  lea     r8, [rsp+68h+arg_10]
0x18002ba06  lea     rdx, IID_IServiceInheritanceConfig
0x18002ba0d  mov     rax, [rcx]
0x18002ba10  mov     rax, [rax]
0x18002ba13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba18  mov     ebx, eax
0x18002ba1a  test    eax, eax
0x18002ba1c  jns     short loc_18002BA41
0x18002ba1e  test    byte ptr cs:g_dwDebugFlags, 7
0x18002ba25  jz      loc_18002BBF7
0x18002ba2b  mov     [rsp+68h+var_40], eax
0x18002ba2f  mov     r8d, 2009h
0x18002ba35  lea     rax, aCtemplateCreat_4; "CTemplate::CreateTransServiceConfig() -"...
0x18002ba3c  jmp     loc_18002BBD7
0x18002ba41  mov     rcx, [rsp+68h+arg_10]
0x18002ba49  xor     edx, edx
0x18002ba4b  mov     rax, [rcx]
0x18002ba4e  mov     rax, [rax+18h]
0x18002ba52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba57  mov     ebx, eax
0x18002ba59  test    eax, eax
0x18002ba5b  jns     short loc_18002BA75
0x18002ba5d  test    byte ptr cs:g_dwDebugFlags, 7
0x18002ba64  jz      loc_18002BBF7
0x18002ba6a  mov     r8d, 200Fh
0x18002ba70  jmp     loc_18002BBCC
0x18002ba75  mov     eax, [rdi]
0x18002ba77  test    eax, eax
0x18002ba79  jz      loc_18002BB2C
0x18002ba7f  mov     edi, r15d
0x18002ba82  sub     eax, 1
0x18002ba85  jz      short loc_18002BAA7
0x18002ba87  sub     eax, 1
0x18002ba8a  jz      short loc_18002BAA2
0x18002ba8c  sub     eax, 2
0x18002ba8f  jz      short loc_18002BA9B
0x18002ba91  cmp     eax, 4
0x18002ba94  jnz     short loc_18002BAA7
0x18002ba96  lea     edi, [rax-1]
0x18002ba99  jmp     short loc_18002BAA7
0x18002ba9b  mov     edi, 2
0x18002baa0  jmp     short loc_18002BAA7
0x18002baa2  mov     edi, 1
0x18002baa7  mov     rcx, [r14]
0x18002baaa  lea     r8, [rsp+68h+arg_18]
0x18002bab2  lea     rdx, IID_IServiceTransactionConfig
0x18002bab9  mov     rax, [rcx]
0x18002babc  mov     rax, [rax]
0x18002babf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bac4  mov     ebx, eax
0x18002bac6  test    eax, eax
0x18002bac8  jns     short loc_18002BAED
0x18002baca  test    byte ptr cs:g_dwDebugFlags, 7
0x18002bad1  jz      loc_18002BBF7
0x18002bad7  mov     [rsp+68h+var_40], eax
0x18002badb  mov     r8d, 2028h
0x18002bae1  lea     rax, aCtemplateCreat_2; "CTemplate::CreateTransServiceConfig() -"...
0x18002bae8  jmp     loc_18002BBD7
0x18002baed  mov     rcx, [rsp+68h+arg_18]
0x18002baf5  mov     edx, edi
0x18002baf7  mov     rax, [rcx]
0x18002bafa  mov     rax, [rax+18h]
0x18002bafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb03  mov     ebx, eax
0x18002bb05  test    eax, eax
0x18002bb07  jns     short loc_18002BB2C
0x18002bb09  test    byte ptr cs:g_dwDebugFlags, 7
0x18002bb10  jz      loc_18002BBF7
0x18002bb16  mov     [rsp+68h+var_40], eax
0x18002bb1a  mov     r8d, 202Eh
0x18002bb20  lea     rax, aCtemplateCreat_0; "CTemplate::CreateTransServiceConfig() -"...
0x18002bb27  jmp     loc_18002BBD7
0x18002bb2c  test    ebp, ebp
0x18002bb2e  jz      loc_18002BBF7
0x18002bb34  mov     rcx, [r14]
0x18002bb37  lea     r8, [rsp+68h+var_38]
0x18002bb3c  lea     rdx, IID_IServiceTrackerConfig
0x18002bb43  mov     rax, [rcx]
0x18002bb46  mov     rax, [rax]
0x18002bb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb4e  mov     ebx, eax
0x18002bb50  test    eax, eax
0x18002bb52  jns     short loc_18002BB74
0x18002bb54  test    byte ptr cs:g_dwDebugFlags, 7
0x18002bb5b  jz      loc_18002BBF7
0x18002bb61  mov     [rsp+68h+var_40], eax
0x18002bb65  mov     r8d, 2036h
0x18002bb6b  lea     rax, aCtemplateCreat_3; "CTemplate::CreateTransServiceConfig() -"...
0x18002bb72  jmp     short loc_18002BBD7
0x18002bb74  mov     rbx, [rsi+178h]
0x18002bb7b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002bb7f  inc     r9
0x18002bb82  cmp     [rbx+r9*2], r15w
0x18002bb87  jnz     short loc_18002BB7F
0x18002bb89  mov     r11, [rsp+68h+var_38]
0x18002bb8e  xor     edx, edx
0x18002bb90  mov     rcx, rsi
0x18002bb93  mov     r10, [r11]
0x18002bb96  call    ?GetSourceFileName@CTemplate@@QEAAPEAGW4SOURCEPATHTYPE@@@Z; CTemplate::GetSourceFileName(SOURCEPATHTYPE)
0x18002bb9b  add     rax, 2
0x18002bb9f  mov     r8, rbx
0x18002bba2  mov     edx, 1
0x18002bba7  mov     rcx, r11
0x18002bbaa  lea     r9, [rax+r9*2]
0x18002bbae  mov     rax, [r10+18h]
0x18002bbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb7  mov     ebx, eax
0x18002bbb9  test    eax, eax
0x18002bbbb  jns     short loc_18002BBF7
0x18002bbbd  test    byte ptr cs:g_dwDebugFlags, 7
0x18002bbc4  jz      short loc_18002BBF7
0x18002bbc6  mov     r8d, 2051h
0x18002bbcc  mov     [rsp+68h+var_40], eax
0x18002bbd0  lea     rax, aCtemplateCreat_5; "CTemplate::CreateTransServiceConfig() -"...
0x18002bbd7  mov     rcx, cs:g_pDebug
0x18002bbde  lea     r9, aCtemplateCreat; "CTemplate::CreateTransServiceConfig"
0x18002bbe5  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002bbec  mov     [rsp+68h+ppv], rax
0x18002bbf1  call    cs:__imp_PuDbgPrint
0x18002bbf7  mov     rcx, [rsp+68h+arg_10]
0x18002bbff  test    rcx, rcx
0x18002bc02  jz      short loc_18002BC10
0x18002bc04  mov     rax, [rcx]
0x18002bc07  mov     rax, [rax+10h]
0x18002bc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc10  mov     rcx, [rsp+68h+arg_18]
0x18002bc18  test    rcx, rcx
0x18002bc1b  jz      short loc_18002BC29
0x18002bc1d  mov     rax, [rcx]
0x18002bc20  mov     rax, [rax+10h]
0x18002bc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc29  mov     eax, ebx
0x18002bc2b  jmp     loc_180013438
```

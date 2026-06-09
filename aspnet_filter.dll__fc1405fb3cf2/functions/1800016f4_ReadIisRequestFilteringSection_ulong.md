# ReadIisRequestFilteringSection(ulong *)

- ea: `0x1800016f4`
- end: `0x180001aca`
- name: `?ReadIisRequestFilteringSection@@YAJPEAK@Z`
- size: `982`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800015f0`

## callees

- `0x1800016f4`
- `0x180003238`
- `0x1800043b0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800017bb`
- `OLEAUT32!__imp_VariantInit` at `0x1800018ad`
- `OLEAUT32!__imp_VariantInit` at `0x18000191d`
- `OLEAUT32!__imp_VariantInit` at `0x1800017bb`
- `OLEAUT32!__imp_VariantInit` at `0x1800018ad`
- `OLEAUT32!__imp_VariantInit` at `0x18000191d`
- `OLEAUT32!__imp_VariantClear` at `0x180001800`
- `OLEAUT32!__imp_VariantClear` at `0x18000199b`
- `OLEAUT32!__imp_VariantClear` at `0x180001800`
- `OLEAUT32!__imp_VariantClear` at `0x18000199b`
- `ole32!CoGetClassObject` at `0x18000177e`
- `ole32!CoGetClassObject` at `0x18000177e`
- `ole32!CoCreateInstance` at `0x1800017a7`
- `ole32!CoCreateInstance` at `0x1800017a7`
- `ole32!CoUninitialize` at `0x180001aa4`
- `ole32!CoUninitialize` at `0x180001aa4`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000195d`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000195d`

## string_xrefs

- `0x1800017c9`: `mappingExtension`
- `0x180001815`: `system.webServer/security/requestFiltering`

## pseudocode

```c
__int64 __fastcall ReadIisRequestFilteringSection(unsigned int *a1)
{
  int v2; // esi
  int v3; // r14d
  LONGLONG llVal; // r12
  HRESULT ClassObject; // ebx
  unsigned int v6; // r13d
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64 *, __int128 *, __int64 *); // rax
  unsigned int v9; // esi
  const wchar_t **v10; // r15
  int v11; // r14d
  __int64 v13; // [rsp+30h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-41h] BYREF
  __int64 *v15; // [rsp+40h] [rbp-39h] BYREF
  __int64 v16; // [rsp+48h] [rbp-31h] BYREF
  __int64 v17; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v19; // [rsp+70h] [rbp-9h] BYREF
  IRecordInfo *pRecInfo; // [rsp+80h] [rbp+7h]
  int v21; // [rsp+E0h] [rbp+67h]
  unsigned int v22; // [rsp+E8h] [rbp+6Fh] BYREF
  int v23; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+7Fh] BYREF

  v21 = 0;
  v2 = 0;
  v23 = 0;
  v3 = 0;
  ppv = 0;
  llVal = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v13 = 0;
  v24 = 0;
  if ( a1 )
  {
    *a1 = 0;
    ClassObject = EnsureCoInitialized(&v23);
    if ( !ClassObject )
    {
      ClassObject = CoGetClassObject(&CLSID_AppHostAdminManager, 1u, 0, &IID_IAppHostAdminManager, &ppv);
      if ( ClassObject < 0 )
        ClassObject = CoCreateInstance(&CLSID_AppHostAdminManager, 0, 0x15u, &IID_IAppHostAdminManager, &ppv);
      if ( !ClassObject )
      {
        VariantInit(&pvarg);
        ClassObject = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        L"mappingExtension",
                        &pvarg);
        if ( !ClassObject )
        {
          llVal = pvarg.llVal;
          (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
          VariantClear(&pvarg);
          ClassObject = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          L"system.webServer/security/requestFiltering",
                          L"MACHINE/WEBROOT/APPHOST",
                          &v17);
          if ( !ClassObject )
          {
            ClassObject = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 80LL))(
                            v17,
                            L"hiddenSegments",
                            &v16);
            if ( !ClassObject )
            {
              ClassObject = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v16 + 32LL))(v16, &v15);
              if ( !ClassObject )
              {
                ClassObject = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v15 + 24))(v15, &v22);
                if ( !ClassObject )
                {
                  v6 = 0;
                  if ( v22 )
                  {
                    while ( 1 )
                    {
                      VariantInit(&pvarg);
                      pvarg.vt = 3;
                      pvarg.lVal = v6;
                      v7 = *v15;
                      pRecInfo = pvarg.pRecInfo;
                      v8 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v7 + 32);
                      v19 = *(_OWORD *)&pvarg.vt;
                      ClassObject = v8(v15, &v19, &v13);
                      if ( ClassObject )
                        break;
                      ClassObject = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v13 + 88LL))(
                                      v13,
                                      L"segment",
                                      &v24);
                      if ( ClassObject )
                        break;
                      VariantInit(&pvarg);
                      ClassObject = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v24 + 32LL))(
                                      v24,
                                      &pvarg);
                      if ( ClassObject )
                        break;
                      if ( pvarg.vt != 8 )
                      {
                        ClassObject = -2147418113;
                        break;
                      }
                      v9 = 0;
                      v10 = (const wchar_t **)&g_hidden_dirs;
                      while ( _wcsicmp(pvarg.bstrVal, *v10) )
                      {
                        ++v9;
                        ++v10;
                        if ( v9 >= 7 )
                          goto LABEL_24;
                      }
                      if ( !v9 )
                      {
                        v2 = 1;
                        v21 = 1;
                        goto LABEL_25;
                      }
                      v3 |= 1 << (v9 - 1);
LABEL_24:
                      v2 = v21;
LABEL_25:
                      VariantClear(&pvarg);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                      v24 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                      ++v6;
                      v13 = 0;
                      if ( v6 >= v22 )
                        goto LABEL_26;
                    }
                  }
                  else
                  {
LABEL_26:
                    v11 = v3 & 0x3F;
                    if ( v2 )
                      *a1 |= 1u;
                    if ( v11 == 63 )
                      *a1 |= 2u;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      v15 = 0;
    }
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
    }
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    if ( llVal )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 16LL))(llVal);
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v23 )
      CoUninitialize();
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1800016f4  push    rbp
0x1800016f6  push    rbx
0x1800016f7  push    rsi
0x1800016f8  push    rdi
0x1800016f9  push    r12
0x1800016fb  push    r13
0x1800016fd  push    r14
0x1800016ff  push    r15
0x180001701  lea     rbp, [rsp-1Fh]
0x180001706  sub     rsp, 98h
0x18000170d  xor     r15d, r15d
0x180001710  mov     rdi, rcx
0x180001713  mov     [rbp+57h+arg_0], r15d
0x180001717  mov     esi, r15d
0x18000171a  mov     [rbp+57h+arg_10], r15d
0x18000171e  mov     r14d, r15d
0x180001721  mov     [rbp+57h+var_98], r15
0x180001725  mov     r12d, r15d
0x180001728  mov     [rbp+57h+var_90], r15
0x18000172c  mov     [rbp+57h+var_80], r15
0x180001730  mov     [rbp+57h+var_88], r15
0x180001734  mov     [rbp+57h+var_A0], r15
0x180001738  mov     [rbp+57h+arg_18], r15
0x18000173c  test    rcx, rcx
0x18000173f  jnz     short loc_18000174B
0x180001741  mov     ebx, 80070057h
0x180001746  jmp     loc_180001AAA
0x18000174b  mov     [rcx], r15d
0x18000174e  lea     rcx, [rbp+57h+arg_10]; int *
0x180001752  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x180001757  mov     ebx, eax
0x180001759  test    eax, eax
0x18000175b  jnz     loc_1800019EC
0x180001761  lea     rax, [rbp+57h+var_98]
0x180001765  xor     r8d, r8d; pvReserved
0x180001768  lea     r9, IID_IAppHostAdminManager; riid
0x18000176f  mov     [rsp+0D0h+ppv], rax; ppv
0x180001774  lea     edx, [rbx+1]; dwClsContext
0x180001777  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x18000177e  call    cs:__imp_CoGetClassObject
0x180001784  mov     ebx, eax
0x180001786  test    eax, eax
0x180001788  jns     short loc_1800017AF
0x18000178a  xor     edx, edx; pUnkOuter
0x18000178c  lea     rax, [rbp+57h+var_98]
0x180001790  lea     r9, IID_IAppHostAdminManager; riid
0x180001797  mov     [rsp+0D0h+ppv], rax; ppv
0x18000179c  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x1800017a3  lea     r8d, [rdx+15h]; dwClsContext
0x1800017a7  call    cs:__imp_CoCreateInstance
0x1800017ad  mov     ebx, eax
0x1800017af  test    ebx, ebx
0x1800017b1  jnz     loc_1800019EC
0x1800017b7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800017bb  call    cs:__imp_VariantInit
0x1800017c1  mov     rcx, [rbp+57h+var_98]
0x1800017c5  lea     r8, [rbp+57h+pvarg]
0x1800017c9  lea     rdx, aMappingextensi; "mappingExtension"
0x1800017d0  mov     rax, [rcx]
0x1800017d3  mov     rax, [rax+20h]
0x1800017d7  call    cs:__guard_dispatch_icall_fptr
0x1800017dd  mov     ebx, eax
0x1800017df  test    eax, eax
0x1800017e1  jnz     loc_1800019EC
0x1800017e7  mov     r12, qword ptr [rbp+57h+pvarg+8]
0x1800017eb  mov     rcx, r12
0x1800017ee  mov     rax, [r12]
0x1800017f2  mov     rax, [rax+8]
0x1800017f6  call    cs:__guard_dispatch_icall_fptr
0x1800017fc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180001800  call    cs:__imp_VariantClear
0x180001806  mov     rcx, [rbp+57h+var_98]
0x18000180a  lea     r9, [rbp+57h+var_80]
0x18000180e  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001815  lea     rdx, aSystemWebserve; "system.webServer/security/requestFilter"...
0x18000181c  mov     rax, [rcx]
0x18000181f  mov     rax, [rax+18h]
0x180001823  call    cs:__guard_dispatch_icall_fptr
0x180001829  mov     ebx, eax
0x18000182b  test    eax, eax
0x18000182d  jnz     loc_1800019EC
0x180001833  mov     rcx, [rbp+57h+var_80]
0x180001837  lea     r8, [rbp+57h+var_88]
0x18000183b  lea     rdx, aHiddensegments; "hiddenSegments"
0x180001842  mov     rax, [rcx]
0x180001845  mov     rax, [rax+50h]
0x180001849  call    cs:__guard_dispatch_icall_fptr
0x18000184f  mov     ebx, eax
0x180001851  test    eax, eax
0x180001853  jnz     loc_1800019EC
0x180001859  mov     rcx, [rbp+57h+var_88]
0x18000185d  lea     rdx, [rbp+57h+var_90]
0x180001861  mov     rax, [rcx]
0x180001864  mov     rax, [rax+20h]
0x180001868  call    cs:__guard_dispatch_icall_fptr
0x18000186e  mov     ebx, eax
0x180001870  test    eax, eax
0x180001872  jnz     loc_1800019EC
0x180001878  mov     rcx, [rbp+57h+var_90]
0x18000187c  lea     rdx, [rbp+57h+arg_8]
0x180001880  mov     rax, [rcx]
0x180001883  mov     rax, [rax+18h]
0x180001887  call    cs:__guard_dispatch_icall_fptr
0x18000188d  mov     ebx, eax
0x18000188f  test    eax, eax
0x180001891  jnz     loc_1800019EC
0x180001897  mov     r13d, r15d
0x18000189a  cmp     [rbp+57h+arg_8], r15d
0x18000189e  jbe     loc_1800019D8
0x1800018a4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800018a8  mov     esi, 8
0x1800018ad  call    cs:__imp_VariantInit
0x1800018b3  mov     rcx, [rbp+57h+var_90]
0x1800018b7  lea     eax, [rsi-5]
0x1800018ba  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800018bf  lea     r8, [rbp+57h+var_A0]
0x1800018c3  mov     word ptr [rbp+57h+pvarg], ax
0x1800018c7  lea     rdx, [rbp+57h+var_60]
0x1800018cb  mov     dword ptr [rbp+57h+pvarg+8], r13d
0x1800018cf  mov     rax, [rcx]
0x1800018d2  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800018d6  movsd   [rbp+57h+var_50], xmm1
0x1800018db  mov     rax, [rax+20h]
0x1800018df  movaps  [rbp+57h+var_60], xmm0
0x1800018e3  call    cs:__guard_dispatch_icall_fptr
0x1800018e9  mov     ebx, eax
0x1800018eb  test    eax, eax
0x1800018ed  jnz     loc_1800019EC
0x1800018f3  mov     rcx, [rbp+57h+var_A0]
0x1800018f7  lea     r8, [rbp+57h+arg_18]
0x1800018fb  lea     rdx, aSegment; "segment"
0x180001902  mov     rax, [rcx]
0x180001905  mov     rax, [rax+58h]
0x180001909  call    cs:__guard_dispatch_icall_fptr
0x18000190f  mov     ebx, eax
0x180001911  test    eax, eax
0x180001913  jnz     loc_1800019EC
0x180001919  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000191d  call    cs:__imp_VariantInit
0x180001923  mov     rcx, [rbp+57h+arg_18]
0x180001927  lea     rdx, [rbp+57h+pvarg]
0x18000192b  mov     rax, [rcx]
0x18000192e  mov     rax, [rax+20h]
0x180001932  call    cs:__guard_dispatch_icall_fptr
0x180001938  mov     ebx, eax
0x18000193a  test    eax, eax
0x18000193c  jnz     loc_1800019EC
0x180001942  cmp     si, word ptr [rbp+57h+pvarg]
0x180001946  jnz     loc_180001AC0
0x18000194c  mov     esi, r15d
0x18000194f  lea     r15, ?g_hidden_dirs@@3PAPEAGA; ushort * near * g_hidden_dirs
0x180001956  mov     rdx, [r15]; String2
0x180001959  mov     rcx, qword ptr [rbp+57h+pvarg+8]; String1
0x18000195d  call    cs:__imp__wcsicmp
0x180001963  test    eax, eax
0x180001965  jz      short loc_180001977
0x180001967  inc     esi
0x180001969  add     r15, 8
0x18000196d  cmp     esi, 7
0x180001970  jb      short loc_180001956
0x180001972  xor     r15d, r15d
0x180001975  jmp     short loc_180001994
0x180001977  xor     r15d, r15d
0x18000197a  test    esi, esi
0x18000197c  jnz     short loc_180001987
0x18000197e  lea     esi, [r15+1]
0x180001982  mov     [rbp+57h+arg_0], esi
0x180001985  jmp     short loc_180001997
0x180001987  lea     ecx, [rsi-1]
0x18000198a  mov     eax, 1
0x18000198f  shl     eax, cl
0x180001991  or      r14d, eax
0x180001994  mov     esi, [rbp+57h+arg_0]
0x180001997  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000199b  call    cs:__imp_VariantClear
0x1800019a1  mov     rcx, [rbp+57h+arg_18]
0x1800019a5  mov     rax, [rcx]
0x1800019a8  mov     rax, [rax+10h]
0x1800019ac  call    cs:__guard_dispatch_icall_fptr
0x1800019b2  mov     rcx, [rbp+57h+var_A0]
0x1800019b6  mov     [rbp+57h+arg_18], r15
0x1800019ba  mov     rax, [rcx]
0x1800019bd  mov     rax, [rax+10h]
0x1800019c1  call    cs:__guard_dispatch_icall_fptr
0x1800019c7  inc     r13d
0x1800019ca  mov     [rbp+57h+var_A0], r15
0x1800019ce  cmp     r13d, [rbp+57h+arg_8]
0x1800019d2  jb      loc_1800018A4
0x1800019d8  and     r14d, 3Fh
0x1800019dc  test    esi, esi
0x1800019de  jz      short loc_1800019E3
0x1800019e0  or      dword ptr [rdi], 1
0x1800019e3  cmp     r14d, 3Fh ; '?'
0x1800019e7  jnz     short loc_1800019EC
0x1800019e9  or      dword ptr [rdi], 2
0x1800019ec  mov     rcx, [rbp+57h+arg_18]
0x1800019f0  test    rcx, rcx
0x1800019f3  jz      short loc_180001A06
0x1800019f5  mov     rax, [rcx]
0x1800019f8  mov     rax, [rax+10h]
0x1800019fc  call    cs:__guard_dispatch_icall_fptr
0x180001a02  mov     [rbp+57h+arg_18], r15
0x180001a06  mov     rcx, [rbp+57h+var_A0]
0x180001a0a  test    rcx, rcx
0x180001a0d  jz      short loc_180001A20
0x180001a0f  mov     rax, [rcx]
0x180001a12  mov     rax, [rax+10h]
0x180001a16  call    cs:__guard_dispatch_icall_fptr
0x180001a1c  mov     [rbp+57h+var_A0], r15
0x180001a20  mov     rcx, [rbp+57h+var_90]
0x180001a24  test    rcx, rcx
0x180001a27  jz      short loc_180001A3A
0x180001a29  mov     rax, [rcx]
0x180001a2c  mov     rax, [rax+10h]
0x180001a30  call    cs:__guard_dispatch_icall_fptr
0x180001a36  mov     [rbp+57h+var_90], r15
0x180001a3a  mov     rcx, [rbp+57h+var_88]
0x180001a3e  test    rcx, rcx
0x180001a41  jz      short loc_180001A54
0x180001a43  mov     rax, [rcx]
0x180001a46  mov     rax, [rax+10h]
0x180001a4a  call    cs:__guard_dispatch_icall_fptr
0x180001a50  mov     [rbp+57h+var_88], r15
0x180001a54  mov     rcx, [rbp+57h+var_80]
0x180001a58  test    rcx, rcx
0x180001a5b  jz      short loc_180001A6E
0x180001a5d  mov     rax, [rcx]
0x180001a60  mov     rax, [rax+10h]
0x180001a64  call    cs:__guard_dispatch_icall_fptr
0x180001a6a  mov     [rbp+57h+var_80], r15
0x180001a6e  test    r12, r12
0x180001a71  jz      short loc_180001A84
0x180001a73  mov     rax, [r12]
0x180001a77  mov     rcx, r12
0x180001a7a  mov     rax, [rax+10h]
0x180001a7e  call    cs:__guard_dispatch_icall_fptr
0x180001a84  mov     rcx, [rbp+57h+var_98]
0x180001a88  test    rcx, rcx
0x180001a8b  jz      short loc_180001A9E
0x180001a8d  mov     rax, [rcx]
0x180001a90  mov     rax, [rax+10h]
0x180001a94  call    cs:__guard_dispatch_icall_fptr
0x180001a9a  mov     [rbp+57h+var_98], r15
0x180001a9e  cmp     [rbp+57h+arg_10], r15d
0x180001aa2  jz      short loc_180001AAA
0x180001aa4  call    cs:__imp_CoUninitialize
0x180001aaa  mov     eax, ebx
0x180001aac  add     rsp, 98h
0x180001ab3  pop     r15
0x180001ab5  pop     r14
0x180001ab7  pop     r13
0x180001ab9  pop     r12
0x180001abb  pop     rdi
0x180001abc  pop     rsi
0x180001abd  pop     rbx
0x180001abe  pop     rbp
0x180001abf  retn
0x180001ac0  mov     ebx, 8000FFFFh
0x180001ac5  jmp     loc_1800019EC
```

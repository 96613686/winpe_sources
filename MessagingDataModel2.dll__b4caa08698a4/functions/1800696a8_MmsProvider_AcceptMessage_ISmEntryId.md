# MmsProvider::AcceptMessage(ISmEntryId *)

- ea: `0x1800696a8`
- end: `0x18006990d`
- name: `?AcceptMessage@MmsProvider@@QEAAJPEAUISmEntryId@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(MmsProvider *__hidden this, struct ISmEntryId *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065580`

## callees

- `0x180005c50`
- `0x180026704`
- `0x180026a08`
- `0x1800696a8`
- `0x180069bdc`
- `0x180069c5c`
- `0x180069c88`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006987d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006987d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800697a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800697a3`

## pseudocode

```c
__int64 __fastcall MmsProvider::AcceptMessage(MmsProvider *this, struct ISmEntryId *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // edi
  int started; // eax
  int v7; // eax
  HRESULT v8; // eax
  __int64 v9; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+38h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-10h] BYREF

  if ( !a2 )
  {
    Log_HREvent_45(-2147024809);
    Log_AssertionEvent_36();
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 2147942487LL;
  }
  v3 = *((_QWORD *)this + 4);
  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, struct ISmEntryId *, __int64 *))(*(_QWORD *)v3 + 88LL))(v3, a2, &v12);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 632LL))(v12, &v10);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v9 = 0;
      ATL::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>(
        &v9,
        v12);
      if ( !v10 )
      {
        started = StartMmsTransportThroughSmsService();
        v5 = started;
        if ( started < 0 )
          goto LABEL_8;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        started = (*(__int64 (__fastcall **)(__int64, struct _FILETIME))(*(_QWORD *)v9 + 160LL))(
                    v9,
                    SystemTimeAsFileTime);
        v5 = started;
        if ( started < 0 )
          goto LABEL_8;
      }
      v7 = IsMessageExpired(v9);
      started = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 552LL))(v9, v7 != 0 ? 4 : 1);
      v5 = started;
      if ( started >= 0
        && (started = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 976LL))(v9, 0),
            v5 = started,
            started >= 0)
        && (started = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 232LL))(v9), v5 = started, started >= 0) )
      {
        if ( v10 != 1 )
        {
LABEL_19:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
          v5 = 0;
          goto LABEL_20;
        }
        ppv = 0;
        v8 = CoCreateInstance(
               &GUID_64fe8d29_91b5_42c4_a7ca_bc2de782205a,
               0,
               0x17u,
               &GUID_400a717e_2df9_4f4a_b58e_32fe0c150103,
               &ppv);
        v5 = v8;
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, qword_1800DC400, 1);
          v5 = v8;
          if ( v8 >= 0 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
            goto LABEL_19;
          }
        }
        Log_HREvent_45(v8);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      }
      else
      {
LABEL_8:
        Log_HREvent_45(started);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
      goto LABEL_20;
    }
  }
  Log_HREvent_45(v4);
LABEL_20:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return v5;
}

```

## disassembly

```asm
0x1800696a8  mov     [rsp-8+arg_10], rdi
0x1800696ad  push    rbp
0x1800696ae  mov     rbp, rsp
0x1800696b1  sub     rsp, 60h
0x1800696b5  mov     rax, cs:__security_cookie
0x1800696bc  xor     rax, rsp
0x1800696bf  mov     [rbp+var_8], rax
0x1800696c3  test    rdx, rdx
0x1800696c6  jnz     short loc_1800696EC
0x1800696c8  mov     ecx, 80070057h; int
0x1800696cd  mov     r9d, 11Fh
0x1800696d3  call    Log_HREvent_45
0x1800696d8  call    Log_AssertionEvent_36
0x1800696dd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800696e2  mov     eax, 80070057h
0x1800696e7  jmp     loc_1800698F3
0x1800696ec  mov     rcx, [rcx+20h]
0x1800696f0  lea     r8, [rbp+var_18]
0x1800696f4  mov     [rbp+var_18], 0
0x1800696fc  mov     rax, [rcx]
0x1800696ff  mov     rax, [rax+58h]
0x180069703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069708  mov     edi, eax
0x18006970a  test    eax, eax
0x18006970c  jns     short loc_180069716
0x18006970e  mov     r9d, 123h
0x180069714  jmp     short loc_180069740
0x180069716  mov     rcx, [rbp+var_18]
0x18006971a  lea     rdx, [rbp+var_28]
0x18006971e  mov     [rbp+var_28], 0
0x180069725  mov     rax, [rcx]
0x180069728  mov     rax, [rax+278h]
0x18006972f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069734  mov     edi, eax
0x180069736  test    eax, eax
0x180069738  jns     short loc_180069751
0x18006973a  mov     r9d, 127h
0x180069740  mov     edx, 1
0x180069745  mov     ecx, eax; int
0x180069747  call    Log_HREvent_45
0x18006974c  jmp     loc_1800698E8
0x180069751  mov     rdx, [rbp+var_18]
0x180069755  lea     rcx, [rbp+var_30]
0x180069759  mov     [rbp+var_30], 0
0x180069761  call    ??0?$CComQIPtr@UISmMessageMMS@@$1?_GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>::CComQIPtr<ISmMessageMMS,&__s_GUID const _GUID_32a5998a_e6dc_4e8b_9a7d_74673f2c3388>(IUnknown *)
0x180069766  cmp     [rbp+var_28], 0
0x18006976a  jnz     short loc_1800697CE
0x18006976c  call    ?StartMmsTransportThroughSmsService@@YAJXZ; StartMmsTransportThroughSmsService(void)
0x180069771  mov     edi, eax
0x180069773  test    eax, eax
0x180069775  jns     short loc_180069797
0x180069777  mov     r9d, 12Fh
0x18006977d  mov     edx, 1
0x180069782  mov     ecx, eax; int
0x180069784  call    Log_HREvent_45
0x180069789  lea     rcx, [rbp+var_30]
0x18006978d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180069792  jmp     loc_1800698E8
0x180069797  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006979b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800697a3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800697a9  mov     rcx, [rbp+var_30]
0x1800697ad  mov     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800697b1  mov     rax, [rcx]
0x1800697b4  mov     rax, [rax+0A0h]
0x1800697bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697c0  mov     edi, eax
0x1800697c2  test    eax, eax
0x1800697c4  jns     short loc_1800697CE
0x1800697c6  mov     r9d, 134h
0x1800697cc  jmp     short loc_18006977D
0x1800697ce  mov     rcx, [rbp+var_30]
0x1800697d2  call    IsMessageExpired
0x1800697d7  mov     rcx, [rbp+var_30]
0x1800697db  neg     eax
0x1800697dd  sbb     edx, edx
0x1800697df  and     edx, 3
0x1800697e2  mov     rax, [rcx]
0x1800697e5  inc     edx
0x1800697e7  mov     rax, [rax+228h]
0x1800697ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697f3  mov     edi, eax
0x1800697f5  test    eax, eax
0x1800697f7  jns     short loc_180069804
0x1800697f9  mov     r9d, 13Bh
0x1800697ff  jmp     loc_18006977D
0x180069804  mov     rcx, [rbp+var_30]
0x180069808  xor     edx, edx
0x18006980a  mov     rax, [rcx]
0x18006980d  mov     rax, [rax+3D0h]
0x180069814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069819  mov     edi, eax
0x18006981b  test    eax, eax
0x18006981d  jns     short loc_18006982A
0x18006981f  mov     r9d, 13Ch
0x180069825  jmp     loc_18006977D
0x18006982a  mov     rcx, [rbp+var_30]
0x18006982e  mov     rax, [rcx]
0x180069831  mov     rax, [rax+0E8h]
0x180069838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006983d  mov     edi, eax
0x18006983f  test    eax, eax
0x180069841  jns     short loc_18006984E
0x180069843  mov     r9d, 13Fh
0x180069849  jmp     loc_18006977D
0x18006984e  cmp     [rbp+var_28], 1
0x180069852  jnz     loc_1800698DD
0x180069858  xor     edx, edx; pUnkOuter
0x18006985a  mov     [rbp+var_20], 0
0x180069862  lea     rax, [rbp+var_20]
0x180069866  lea     r9, _GUID_400a717e_2df9_4f4a_b58e_32fe0c150103; riid
0x18006986d  mov     [rsp+60h+ppv], rax; ppv
0x180069872  lea     rcx, _GUID_64fe8d29_91b5_42c4_a7ca_bc2de782205a; rclsid
0x180069879  lea     r8d, [rdx+17h]; dwClsContext
0x18006987d  call    cs:__imp_CoCreateInstance
0x180069883  mov     edi, eax
0x180069885  test    eax, eax
0x180069887  jns     short loc_1800698A9
0x180069889  mov     r9d, 146h
0x18006988f  mov     edx, 1
0x180069894  mov     ecx, eax; int
0x180069896  call    Log_HREvent_45
0x18006989b  lea     rcx, [rbp+var_20]
0x18006989f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800698a4  jmp     loc_180069789
0x1800698a9  mov     rcx, [rbp+var_20]
0x1800698ad  lea     rdx, qword_1800DC400
0x1800698b4  mov     r8d, 1
0x1800698ba  mov     rax, [rcx]
0x1800698bd  mov     rax, [rax+18h]
0x1800698c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698c6  mov     edi, eax
0x1800698c8  test    eax, eax
0x1800698ca  jns     short loc_1800698D4
0x1800698cc  mov     r9d, 147h
0x1800698d2  jmp     short loc_18006988F
0x1800698d4  lea     rcx, [rbp+var_20]
0x1800698d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800698dd  lea     rcx, [rbp+var_30]
0x1800698e1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800698e6  xor     edi, edi
0x1800698e8  lea     rcx, [rbp+var_18]
0x1800698ec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800698f1  mov     eax, edi
0x1800698f3  mov     rcx, [rbp+var_8]
0x1800698f7  xor     rcx, rsp; StackCookie
0x1800698fa  call    __security_check_cookie
0x1800698ff  mov     rdi, [rsp+60h+arg_10]
0x180069907  add     rsp, 60h
0x18006990b  pop     rbp
0x18006990c  retn
```

# CDPComDeviceQuery::GetCurrentMachineDeviceId(char * *)

- ea: `0x180037730`
- end: `0x1800378b0`
- name: `?GetCurrentMachineDeviceId@CDPComDeviceQuery@@UEAAJPEAPEAD@Z`
- size: `384`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *__hidden this, char **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d64`
- `0x180003e60`
- `0x180006668`
- `0x180006f10`
- `0x180018970`
- `0x18001ddf8`
- `0x1800225a0`
- `0x180037730`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003783d`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003783d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037820`

## string_xrefs

- `0x180037772`: `.\cdpcomdevicequery.cpp`
- `0x180037863`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDeviceQuery::GetCurrentMachineDeviceId(CDPComDeviceQuery *this, char **a2)
{
  int DeviceQueryInternalSafe; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  char **v7; // rdx
  char *v8; // rax
  const char *v9; // r8
  unsigned int v10; // [rsp+30h] [rbp-50h] BYREF
  unsigned int cb; // [rsp+34h] [rbp-4Ch] BYREF
  int cb_4; // [rsp+38h] [rbp-48h] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+40h] [rbp-40h] BYREF
  char *Source[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp-18h]

  if ( !a2 )
  {
    v10 = -2147467261;
    cb_4 = 222;
    Log<long &,char const (&)[28],int>((__int64)this, 0, &v10, ".\\cdpcomdevicequery.cpp", &cb_4);
    return v10;
  }
  cb = 0;
  *(_OWORD *)v13 = 0;
  Source[0] = 0;
  Source[1] = (char *)v13;
  DeviceQueryInternalSafe = CDPComDeviceQuery::CreateDeviceQueryInternalSafe(this, (struct ICDPDeviceQuery **)Source);
  cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(Source);
  if ( DeviceQueryInternalSafe >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(std::_Ref_count_base *, _QWORD, unsigned int *))(*(_QWORD *)v13[0] + 88LL))(
           v13[0],
           0,
           &cb) != -2147221235 )
    {
      v10 = -2147418113;
      goto LABEL_13;
    }
    std::string::string(Source, cb, 0);
    v7 = Source;
    if ( v15 > 0xF )
      v7 = (char **)Source[0];
    DeviceQueryInternalSafe = (*(__int64 (__fastcall **)(std::_Ref_count_base *, char **, unsigned int *))(*(_QWORD *)v13[0] + 88LL))(
                                v13[0],
                                v7,
                                &cb);
    if ( DeviceQueryInternalSafe >= 0 )
    {
      v8 = (char *)CoTaskMemAlloc(cb);
      *a2 = v8;
      v9 = (const char *)Source;
      if ( v15 > 0xF )
        v9 = Source[0];
      strcpy_s(v8, cb, v9);
    }
    std::string::~string(Source);
  }
  v10 = DeviceQueryInternalSafe;
  if ( DeviceQueryInternalSafe < 0 )
  {
LABEL_13:
    cb_4 = 260;
    Log<long &,char const (&)[28],int>(v6, v5, &v10, ".\\cdpcomdevicequery.cpp", &cb_4);
    DeviceQueryInternalSafe = v10;
  }
  if ( v13[1] )
    std::_Ref_count_base::_Decref(v13[1]);
  return (unsigned int)DeviceQueryInternalSafe;
}

```

## disassembly

```asm
0x180037730  mov     [rsp-8+arg_10], rbx
0x180037735  mov     [rsp-8+arg_18], rdi
0x18003773a  push    rbp
0x18003773b  mov     rbp, rsp
0x18003773e  sub     rsp, 80h
0x180037745  mov     rax, cs:__security_cookie
0x18003774c  xor     rax, rsp
0x18003774f  mov     [rbp+var_10], rax
0x180037753  mov     rdi, rdx
0x180037756  test    rdx, rdx
0x180037759  jnz     short loc_18003778A
0x18003775b  mov     [rbp+var_50], 80004003h
0x180037762  mov     dword ptr [rbp+cb+4], 0DEh
0x180037769  lea     rax, [rbp+cb+4]
0x18003776d  mov     [rsp+80h+var_60], rax
0x180037772  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180037779  lea     r8, [rbp+var_50]
0x18003777d  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180037782  mov     eax, [rbp+var_50]
0x180037785  jmp     loc_180037886
0x18003778a  mov     dword ptr [rbp+cb], 0
0x180037791  xorps   xmm0, xmm0
0x180037794  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180037799  mov     [rbp+Source], 0
0x1800377a1  lea     rax, [rbp+var_40]
0x1800377a5  mov     [rbp+var_28], rax
0x1800377a9  lea     rdx, [rbp+Source]; struct ICDPDeviceQuery **
0x1800377ad  call    ?CreateDeviceQueryInternalSafe@CDPComDeviceQuery@@AEAAJPEAPEAVICDPDeviceQuery@@@Z; CDPComDeviceQuery::CreateDeviceQueryInternalSafe(ICDPDeviceQuery * *)
0x1800377b2  mov     ebx, eax
0x1800377b4  lea     rcx, [rbp+Source]
0x1800377b8  call    ??1?$address_of@VICDPDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(void)
0x1800377bd  test    ebx, ebx
0x1800377bf  js      loc_18003784C
0x1800377c5  mov     rcx, [rbp+var_40]
0x1800377c9  mov     rax, [rcx]
0x1800377cc  lea     r8, [rbp+cb]
0x1800377d0  xor     edx, edx
0x1800377d2  mov     rax, [rax+58h]
0x1800377d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377db  cmp     eax, 8004010Dh
0x1800377e0  jnz     loc_1800378A7
0x1800377e6  mov     edx, dword ptr [rbp+cb]
0x1800377e9  xor     r8d, r8d
0x1800377ec  lea     rcx, [rbp+Source]
0x1800377f0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x1800377f5  mov     rcx, [rbp+var_40]
0x1800377f9  mov     rax, [rcx]
0x1800377fc  lea     rdx, [rbp+Source]
0x180037800  cmp     [rbp+var_18], 0Fh
0x180037805  cmova   rdx, [rbp+Source]
0x18003780a  lea     r8, [rbp+cb]
0x18003780e  mov     rax, [rax+58h]
0x180037812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037817  mov     ebx, eax
0x180037819  test    eax, eax
0x18003781b  js      short loc_180037843
0x18003781d  mov     ecx, dword ptr [rbp+cb]; cb
0x180037820  call    cs:__imp_CoTaskMemAlloc
0x180037826  mov     [rdi], rax
0x180037829  lea     r8, [rbp+Source]
0x18003782d  cmp     [rbp+var_18], 0Fh
0x180037832  cmova   r8, [rbp+Source]; Source
0x180037837  mov     edx, dword ptr [rbp+cb]; SizeInBytes
0x18003783a  mov     rcx, rax; Destination
0x18003783d  call    cs:__imp_strcpy_s
0x180037843  lea     rcx, [rbp+Source]
0x180037847  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003784c  mov     [rbp+var_50], ebx
0x18003784f  test    ebx, ebx
0x180037851  jns     short loc_180037876
0x180037853  mov     dword ptr [rbp+cb+4], 104h
0x18003785a  lea     rax, [rbp+cb+4]
0x18003785e  mov     [rsp+80h+var_60], rax
0x180037863  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18003786a  lea     r8, [rbp+var_50]
0x18003786e  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180037873  mov     ebx, [rbp+var_50]
0x180037876  mov     rcx, [rbp+var_40+8]; this
0x18003787a  test    rcx, rcx
0x18003787d  jz      short loc_180037884
0x18003787f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037884  mov     eax, ebx
0x180037886  mov     rcx, [rbp+var_10]
0x18003788a  xor     rcx, rsp; StackCookie
0x18003788d  call    __security_check_cookie
0x180037892  lea     r11, [rsp+80h+var_s0]
0x18003789a  mov     rbx, [r11+20h]
0x18003789e  mov     rdi, [r11+28h]
0x1800378a2  mov     rsp, r11
0x1800378a5  pop     rbp
0x1800378a6  retn
0x1800378a7  mov     [rbp+var_50], 8000FFFFh
0x1800378ae  jmp     short loc_180037853
```

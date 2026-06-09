# ParseConditionForQueryAndLocale(int,ICondition *,ushort * *,ushort * *,ICondition * *,ICondition * *)

- ea: `0x18004260c`
- end: `0x180042b14`
- name: `?ParseConditionForQueryAndLocale@@YAJHPEAUICondition@@PEAPEAG1PEAPEAU1@2@Z`
- size: `1288`
- prototype: `__int64 __fastcall(int, struct ICondition *, unsigned __int16 **, unsigned __int16 **, struct ICondition **, struct ICondition **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042f80`

## callees

- `0x180005460`
- `0x180006900`
- `0x180009d00`
- `0x18000f718`
- `0x180011f3c`
- `0x1800120a4`
- `0x180030b00`
- `0x18003bff4`
- `0x18004260c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800427fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800428d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800429a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800427fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800428d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800429a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ac6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800426ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800426ae`

## pseudocode

```c
__int64 __fastcall ParseConditionForQueryAndLocale(
        __int64 a1,
        struct ICondition *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct ICondition **a5,
        struct ICondition **a6)
{
  struct ICondition **v6; // r14
  struct ICondition **v7; // r15
  unsigned __int16 **v8; // rsi
  unsigned __int16 **v9; // rdi
  HRESULT v11; // r12d
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  LPVOID v15; // r12
  __int64 (__fastcall *v16)(LPVOID, struct ICondition *, __int64, __int64, GUID *); // r15
  LPVOID v17; // r12
  __int64 (__fastcall *v18)(LPVOID, struct ICondition *, __int64, __int64, GUID *, _QWORD, _QWORD, LPVOID *, unsigned __int16 **, GUID *, _QWORD); // r15
  unsigned __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct ICondition *v23; // [rsp+80h] [rbp-80h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-78h] BYREF
  void *v25; // [rsp+90h] [rbp-70h] BYREF
  void *v26; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 **v28; // [rsp+B0h] [rbp-50h]
  unsigned __int16 **v29; // [rsp+B8h] [rbp-48h]
  struct ICondition **v30; // [rsp+C0h] [rbp-40h]
  struct ICondition **v31; // [rsp+C8h] [rbp-38h]
  void *v32[2]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a5;
  v7 = a6;
  *a3 = 0;
  v8 = a4;
  *a4 = 0;
  v9 = a3;
  *a5 = 0;
  *a6 = 0;
  v29 = a4;
  v28 = a3;
  v30 = a5;
  v31 = a6;
  v23 = 0;
  v27[0] = 0;
  v27[1] = 0;
  pv = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<ICondition>::InternalRelease(&ppv);
  v11 = CoCreateInstance(
          &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
          0,
          1u,
          &GUID_db73aa13_3375_4c76_884a_a6116590c15b,
          &ppv);
  if ( v11 >= 0 )
  {
    v32[0] = 0;
    v26 = 0;
    v11 = ULongLongMult(5u, 8u, (unsigned __int64 *)&v26);
    if ( v11 >= 0 )
    {
      v11 = CTCoAllocPolicy::Alloc(v12, 1u, (unsigned __int64)v26, v32);
      if ( v11 >= 0 )
      {
        v26 = 0;
        v25 = 0;
        v11 = ULongLongMult(5u, 8u, (unsigned __int64 *)&v25);
        if ( v11 >= 0 )
        {
          v11 = CTCoAllocPolicy::Alloc(v13, 1u, (unsigned __int64)v25, &v26);
          if ( v11 >= 0 )
          {
            v25 = 0;
            v20 = 0;
            v11 = ULongLongMult(5u, 8u, &v20);
            if ( v11 >= 0 )
            {
              v11 = CTCoAllocPolicy::Alloc(v14, 1u, v20, &v25);
              if ( v11 >= 0 )
              {
                v15 = ppv;
                v16 = *(__int64 (__fastcall **)(LPVOID, struct ICondition *, __int64, __int64, GUID *))(*(_QWORD *)ppv + 96LL);
                Microsoft::WRL::ComPtr<ICondition>::InternalRelease(v27);
                v11 = v16(v15, a2, 1, 5, &GUID_0fc988d4_c935_4b97_a973_46282ea175c8);
                if ( v11 >= 0 )
                {
                  v17 = ppv;
                  LODWORD(v21) = 0;
                  v18 = *(__int64 (__fastcall **)(LPVOID, struct ICondition *, __int64, __int64, GUID *, _QWORD, _QWORD, LPVOID *, unsigned __int16 **, GUID *, _QWORD))(*(_QWORD *)ppv + 96LL);
                  CoTaskMemFree(pv);
                  v11 = v18(
                          v17,
                          a2,
                          2,
                          1,
                          &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                          0,
                          0,
                          &pv,
                          &v21,
                          &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                          0);
                }
                v9 = v28;
                v8 = v29;
                v6 = v30;
                v7 = v31;
              }
            }
            CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v25);
          }
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v26);
      }
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v32);
    if ( v11 >= 0 )
    {
      *v9 = 0;
      *v8 = (unsigned __int16 *)pv;
      *v6 = v23;
      *v7 = (struct ICondition *)v27[0];
      pv = 0;
      v23 = 0;
      v27[0] = 0;
    }
  }
  Microsoft::WRL::ComPtr<ICondition>::InternalRelease(&ppv);
  CoTaskMemFree(pv);
  CoTaskMemFree(0);
  Microsoft::WRL::ComPtr<ICondition>::InternalRelease(v27);
  Microsoft::WRL::ComPtr<ICondition>::InternalRelease(&v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004260c  mov     [rsp-8+arg_0], rbx
0x180042611  push    rbp
0x180042612  push    rsi
0x180042613  push    rdi
0x180042614  push    r12
0x180042616  push    r13
0x180042618  push    r14
0x18004261a  push    r15
0x18004261c  lea     rbp, [rsp-200h]
0x180042624  sub     rsp, 300h
0x18004262b  mov     rax, cs:__security_cookie
0x180042632  xor     rax, rsp
0x180042635  mov     [rbp+230h+var_40], rax
0x18004263c  mov     r14, [rbp+230h+arg_20]
0x180042643  lea     rcx, [rbp+230h+var_2A8]
0x180042647  mov     r15, [rbp+230h+arg_28]
0x18004264e  xor     eax, eax
0x180042650  mov     [r8], rax
0x180042653  mov     rsi, r9
0x180042656  mov     [r9], rax
0x180042659  mov     rdi, r8
0x18004265c  mov     [r14], rax
0x18004265f  mov     r13, rdx
0x180042662  mov     [r15], rax
0x180042665  mov     ebx, eax
0x180042667  mov     [rbp+230h+var_278], r9
0x18004266b  mov     [rbp+230h+var_280], r8
0x18004266f  mov     [rbp+230h+var_270], r14
0x180042673  mov     [rbp+230h+var_268], r15
0x180042677  mov     [rbp+230h+var_2B0], rax
0x18004267b  mov     [rbp+230h+var_290], rax
0x18004267f  mov     [rbp+230h+var_288], rax
0x180042683  mov     [rsp+330h+pv], rax
0x180042688  mov     [rbp+230h+var_2A8], rax
0x18004268c  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x180042691  lea     rax, [rbp+230h+var_2A8]
0x180042695  xor     edx, edx; pUnkOuter
0x180042697  lea     r9, _GUID_db73aa13_3375_4c76_884a_a6116590c15b; riid
0x18004269e  mov     [rsp+330h+ppv], rax; ppv
0x1800426a3  lea     r8d, [rbx+1]; dwClsContext
0x1800426a7  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x1800426ae  call    cs:__imp_CoCreateInstance
0x1800426b4  mov     r12d, eax
0x1800426b7  test    eax, eax
0x1800426b9  js      loc_180042AAF
0x1800426bf  lea     r8, [rbp+230h+var_298]; unsigned __int64 *
0x1800426c3  mov     [rbp+230h+var_260], rbx
0x1800426c7  lea     edx, [rbx+8]; unsigned __int64
0x1800426ca  mov     [rbp+230h+var_298], rbx
0x1800426ce  lea     ecx, [rbx+5]; unsigned __int64
0x1800426d1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800426d6  mov     r12d, eax
0x1800426d9  test    eax, eax
0x1800426db  js      loc_180042A74
0x1800426e1  mov     r8, [rbp+230h+var_298]; unsigned __int64
0x1800426e5  lea     r9, [rbp+230h+var_260]; void **
0x1800426e9  lea     edx, [rbx+1]; unsigned int
0x1800426ec  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800426f1  mov     r12d, eax
0x1800426f4  test    eax, eax
0x1800426f6  js      loc_180042A74
0x1800426fc  lea     r8, [rbp+230h+var_2A0]; unsigned __int64 *
0x180042700  mov     [rbp+230h+var_298], rbx
0x180042704  lea     edx, [rbx+8]; unsigned __int64
0x180042707  mov     [rbp+230h+var_2A0], rbx
0x18004270b  lea     ecx, [rbx+5]; unsigned __int64
0x18004270e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180042713  mov     r12d, eax
0x180042716  test    eax, eax
0x180042718  js      loc_180042A6B
0x18004271e  mov     r8, [rbp+230h+var_2A0]; unsigned __int64
0x180042722  lea     r9, [rbp+230h+var_298]; void **
0x180042726  lea     edx, [rbx+1]; unsigned int
0x180042729  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004272e  mov     r12d, eax
0x180042731  test    eax, eax
0x180042733  js      loc_180042A6B
0x180042739  lea     r8, [rsp+330h+var_2C8]; unsigned __int64 *
0x18004273e  mov     [rbp+230h+var_2A0], rbx
0x180042742  lea     edx, [rbx+8]; unsigned __int64
0x180042745  mov     [rsp+330h+var_2C8], rbx
0x18004274a  lea     ecx, [rbx+5]; unsigned __int64
0x18004274d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180042752  mov     r12d, eax
0x180042755  test    eax, eax
0x180042757  js      loc_180042A62
0x18004275d  mov     r8, [rsp+330h+var_2C8]; unsigned __int64
0x180042762  lea     r9, [rbp+230h+var_2A0]; void **
0x180042766  lea     edx, [rbx+1]; unsigned int
0x180042769  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004276e  mov     r12d, eax
0x180042771  test    eax, eax
0x180042773  js      loc_180042A62
0x180042779  mov     r12, [rbp+230h+var_2A8]
0x18004277d  lea     rcx, [rbp+230h+var_290]
0x180042781  mov     [rsp+330h+var_2D0], ebx
0x180042785  mov     rax, [r12]
0x180042789  mov     r15, [rax+60h]
0x18004278d  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x180042792  mov     rdi, [rbp+230h+var_2A0]
0x180042796  lea     rcx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18004279d  mov     rsi, [rbp+230h+var_298]
0x1800427a1  lea     rax, [rbp+230h+var_290]
0x1800427a5  mov     r14, [rbp+230h+var_260]
0x1800427a9  lea     r9d, [rbx+5]
0x1800427ad  mov     [rsp+330h+var_2E0], rax
0x1800427b2  lea     r8d, [rbx+1]
0x1800427b6  mov     [rsp+330h+var_2E8], rcx
0x1800427bb  lea     rax, [rsp+330h+var_2D0]
0x1800427c0  mov     [rsp+330h+var_2F0], rax
0x1800427c5  mov     rdx, r13
0x1800427c8  mov     [rsp+330h+var_2F8], rdi
0x1800427cd  mov     rax, r15
0x1800427d0  mov     [rsp+330h+var_300], rsi
0x1800427d5  mov     qword ptr [rsp+330h+var_308], r14; unsigned int
0x1800427da  mov     [rsp+330h+ppv], rcx
0x1800427df  mov     rcx, r12
0x1800427e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427e7  mov     r12d, eax
0x1800427ea  test    eax, eax
0x1800427ec  js      loc_180042A52
0x1800427f2  cmp     [rsp+330h+var_2D0], 1
0x1800427f7  jnz     short loc_180042848
0x1800427f9  xor     ecx, ecx; pv
0x1800427fb  call    cs:__imp_CoTaskMemFree
0x180042801  mov     r8, [rsi]
0x180042804  lea     r9, [rbp+230h+var_288]
0x180042808  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004280d  mov     r12d, eax
0x180042810  test    eax, eax
0x180042812  js      loc_180042B0B
0x180042818  mov     r15, [r14]
0x18004281b  lea     rcx, [rbp+230h+var_2B0]
0x18004281f  mov     rax, [r15]
0x180042822  mov     rbx, [rax]
0x180042825  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x18004282a  lea     r8, [rbp+230h+var_2B0]
0x18004282e  mov     rcx, r15
0x180042831  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180042838  mov     rax, rbx
0x18004283b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042840  mov     r12d, eax
0x180042843  jmp     loc_18004297A
0x180042848  jbe     loc_180042987
0x18004284e  lea     rcx, [rbp+230h+var_250]; unsigned __int16 *
0x180042852  mov     edx, 104h; unsigned __int64
0x180042857  mov     [rsp+330h+var_2C0], rcx
0x18004285c  xor     r15d, r15d
0x18004285f  mov     [rsp+330h+var_2C8], rdx
0x180042864  cmp     r15d, [rsp+330h+var_2D0]
0x180042869  jnb     short loc_1800428CF
0x18004286b  test    r15d, r15d
0x18004286e  jz      short loc_180042898
0x180042870  lea     rax, [rsp+330h+var_2C8]
0x180042875  lea     r9, [rsp+330h+var_2C0]; unsigned __int16 **
0x18004287a  mov     [rsp+330h+ppv], rax; unsigned __int64 *
0x18004287f  lea     r8, asc_18005C590; " "
0x180042886  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18004288b  mov     rcx, [rsp+330h+var_2C0]; unsigned __int16 *
0x180042890  mov     r12d, eax
0x180042893  mov     rdx, [rsp+330h+var_2C8]; unsigned __int64
0x180042898  test    r12d, r12d
0x18004289b  js      short loc_1800428C2
0x18004289d  mov     r8, [rsi+r15*8]; unsigned __int16 *
0x1800428a1  lea     rax, [rsp+330h+var_2C8]
0x1800428a6  lea     r9, [rsp+330h+var_2C0]; unsigned __int16 **
0x1800428ab  mov     [rsp+330h+ppv], rax; unsigned __int64 *
0x1800428b0  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800428b5  mov     rcx, [rsp+330h+var_2C0]
0x1800428ba  mov     r12d, eax
0x1800428bd  mov     rdx, [rsp+330h+var_2C8]
0x1800428c2  inc     r15d
0x1800428c5  test    r12d, r12d
0x1800428c8  jns     short loc_180042864
0x1800428ca  jmp     loc_180042A21
0x1800428cf  xor     ecx, ecx; pv
0x1800428d1  call    cs:__imp_CoTaskMemFree
0x1800428d7  lea     r9, [rbp+230h+var_288]
0x1800428db  lea     r8, [rbp+230h+var_250]
0x1800428df  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800428e4  mov     r12d, eax
0x1800428e7  test    eax, eax
0x1800428e9  js      loc_180042B0B
0x1800428ef  mov     [rsp+330h+var_2C8], rbx
0x1800428f4  lea     rcx, [rsp+330h+var_2C8]
0x1800428f9  mov     rbx, [rbp+230h+var_2A8]
0x1800428fd  mov     rax, [rbx]
0x180042900  mov     r15, [rax]
0x180042903  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x180042908  lea     r8, [rsp+330h+var_2C8]
0x18004290d  mov     rcx, rbx
0x180042910  lea     rdx, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a
0x180042917  mov     rax, r15
0x18004291a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004291f  mov     r12d, eax
0x180042922  test    eax, eax
0x180042924  js      short loc_180042970
0x180042926  mov     r15, [rsp+330h+var_2C8]
0x18004292b  lea     rcx, [rbp+230h+var_2B0]
0x18004292f  mov     rax, [r15]
0x180042932  mov     rbx, [rax+50h]
0x180042936  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x18004293b  mov     r9d, [rsp+330h+var_2D0]
0x180042940  lea     rax, [rbp+230h+var_2B0]
0x180042944  mov     [rsp+330h+var_300], rax
0x180042949  mov     r8, r14
0x18004294c  lea     rax, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180042953  xor     edx, edx
0x180042955  mov     qword ptr [rsp+330h+var_308], rax
0x18004295a  mov     rcx, r15
0x18004295d  mov     rax, rbx
0x180042960  mov     dword ptr [rsp+330h+ppv], 0
0x180042968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004296d  mov     r12d, eax
0x180042970  lea     rcx, [rsp+330h+var_2C8]
0x180042975  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x18004297a  test    r12d, r12d
0x18004297d  js      loc_180042B0B
0x180042983  mov     rbx, [rbp+230h+var_288]
0x180042987  mov     r12, [rbp+230h+var_2A8]
0x18004298b  mov     rcx, [rsp+330h+pv]; pv
0x180042990  mov     dword ptr [rsp+330h+var_2C0], 0
0x180042998  mov     rax, [r12]
0x18004299c  mov     r15, [rax+60h]
0x1800429a0  call    cs:__imp_CoTaskMemFree
0x1800429a6  xor     ecx, ecx
0x1800429a8  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800429af  mov     [rsp+330h+var_2E0], rcx
0x1800429b4  lea     rax, [rsp+330h+var_2C0]
0x1800429b9  mov     [rsp+330h+var_2E8], rdx
0x1800429be  mov     [rsp+330h+var_2F0], rax
0x1800429c3  lea     rax, [rsp+330h+pv]
0x1800429c8  mov     [rsp+330h+var_2F8], rax
0x1800429cd  lea     r9d, [rcx+1]
0x1800429d1  mov     [rsp+330h+var_300], rcx
0x1800429d6  lea     r8d, [rcx+2]
0x1800429da  mov     qword ptr [rsp+330h+var_308], rcx
0x1800429df  mov     rax, r15
0x1800429e2  mov     [rsp+330h+ppv], rdx
0x1800429e7  mov     rcx, r12
0x1800429ea  mov     rdx, r13
0x1800429ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429f2  mov     r12d, eax
0x1800429f5  test    eax, eax
0x1800429f7  js      short loc_180042A21
0x1800429f9  cmp     dword ptr [rsp+330h+var_2C0], 0
0x1800429fe  jnz     short loc_180042A21
0x180042a00  cmp     [rsp+330h+var_2D0], 0
0x180042a05  jbe     short loc_180042A21
0x180042a07  mov     rcx, [rsp+330h+pv]; pv
0x180042a0c  mov     r15, [rdi]
0x180042a0f  call    cs:__imp_CoTaskMemFree
0x180042a15  mov     [rsp+330h+pv], r15
0x180042a1a  mov     qword ptr [rdi], 0
0x180042a21  xor     r13d, r13d
0x180042a24  cmp     [rsp+330h+var_2D0], r13d
0x180042a29  jbe     short loc_180042A52
0x180042a2b  lea     rcx, [r14+r13*8]
0x180042a2f  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180042a34  mov     rcx, [rsi+r13*8]; pv
0x180042a38  call    cs:__imp_CoTaskMemFree
0x180042a3e  mov     rcx, [rdi+r13*8]; pv
0x180042a42  call    cs:__imp_CoTaskMemFree
0x180042a48  inc     r13d
0x180042a4b  cmp     r13d, [rsp+330h+var_2D0]
0x180042a50  jb      short loc_180042A2B
0x180042a52  mov     rdi, [rbp+230h+var_280]
0x180042a56  mov     rsi, [rbp+230h+var_278]
0x180042a5a  mov     r14, [rbp+230h+var_270]
0x180042a5e  mov     r15, [rbp+230h+var_268]
0x180042a62  lea     rcx, [rbp+230h+var_2A0]; void *
0x180042a66  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180042a6b  lea     rcx, [rbp+230h+var_298]; void *
0x180042a6f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180042a74  lea     rcx, [rbp+230h+var_260]; void *
0x180042a78  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180042a7d  xor     ecx, ecx
0x180042a7f  test    r12d, r12d
0x180042a82  js      short loc_180042AAF
0x180042a84  mov     rax, rbx
0x180042a87  mov     ebx, ecx
0x180042a89  mov     [rdi], rax
0x180042a8c  mov     rax, [rsp+330h+pv]
0x180042a91  mov     [rsi], rax
0x180042a94  mov     rax, [rbp+230h+var_2B0]
0x180042a98  mov     [r14], rax
0x180042a9b  mov     rax, [rbp+230h+var_290]
0x180042a9f  mov     [r15], rax
0x180042aa2  mov     [rsp+330h+pv], rcx
0x180042aa7  mov     [rbp+230h+var_2B0], rcx
0x180042aab  mov     [rbp+230h+var_290], rcx
0x180042aaf  lea     rcx, [rbp+230h+var_2A8]
0x180042ab3  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x180042ab8  mov     rcx, [rsp+330h+pv]; pv
0x180042abd  call    cs:__imp_CoTaskMemFree
0x180042ac3  mov     rcx, rbx; pv
0x180042ac6  call    cs:__imp_CoTaskMemFree
0x180042acc  lea     rcx, [rbp+230h+var_290]
0x180042ad0  call    ?InternalRelease@?$ComPtr@UICondition@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICondition>::InternalRelease(void)
0x180042ad5  lea     rcx, [rbp+230h+var_2B0]
  ... truncated ...
```

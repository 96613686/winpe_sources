# MitigationHistory::UnregisterFlightId(ushort const *)

- ea: `0x180053804`
- end: `0x1800539b8`
- name: `?UnregisterFlightId@MitigationHistory@@AEAAJPEBG@Z`
- size: `436`
- prototype: `__int64 __fastcall(MitigationHistory *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051cd0`
- `0x1800531ec`
- `0x1800539c0`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x180029cc8`
- `0x18002a488`
- `0x1800411d0`
- `0x180053804`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005384d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005384d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationHistory::UnregisterFlightId(MitigationHistory *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rdi
  unsigned int (__fastcall *v7)(LPVOID, const unsigned __int16 *, __int64 *); // rbx
  const char *v8; // rbx
  int v9; // eax
  __int64 v10; // rdx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  LPVOID v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v17; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  v4 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v14);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v17 = 0;
    v15 = -2147483646;
    if ( (int)MitigationRegUtils::GetMitigationRegDWORD(
                &v15,
                *((unsigned int *)this + 20),
                L"RegisteredFlightIdCount",
                &v17) < 0 )
      v17 = 0;
    v18 = 0;
    v6 = v14;
    v7 = *(unsigned int (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)v14 + 136LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    v8 = (const char *)v7(v6, a2, &v18);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
      v8,
      1,
      0x80070002);
    if ( v18 && (int)v8 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v14 + 104LL))(v14, a2);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 309;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
          (const char *)(unsigned int)v9,
          ppva);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
        goto LABEL_13;
      }
      --v17;
      v15 = -2147483646;
      ppva = 0;
      v9 = MitigationRegUtils::SetMitigationRegDWORD(
             &v15,
             *((unsigned int *)this + 20),
             L"RegisteredFlightIdCount",
             v17);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 313;
        goto LABEL_9;
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    v5 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x123,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_13:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x180053804  mov     [rsp-18h+arg_0], rbx
0x180053809  mov     [rsp-18h+arg_8], rsi
0x18005380e  push    rbp
0x18005380f  push    rdi
0x180053810  push    r14
0x180053812  mov     rbp, rsp
0x180053815  sub     rsp, 40h
0x180053819  mov     r14, rdx
0x18005381c  mov     rsi, rcx
0x18005381f  mov     [rbp+var_10], 0
0x180053827  lea     rcx, [rbp+var_10]
0x18005382b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053830  lea     rax, [rbp+var_10]
0x180053834  mov     [rsp+40h+ppv], rax; int
0x180053839  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180053840  xor     edx, edx; pUnkOuter
0x180053842  lea     r8d, [rdx+1]; dwClsContext
0x180053846  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18005384d  call    cs:__imp_CoCreateInstance
0x180053853  mov     ebx, eax
0x180053855  test    eax, eax
0x180053857  jns     short loc_180053876
0x180053859  mov     rcx, [rbp+18h]; this
0x18005385d  mov     r9d, eax; char *
0x180053860  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053867  mov     edx, 123h; void *
0x18005386c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053871  jmp     loc_18005399A
0x180053876  mov     [rbp+arg_10], 0
0x18005387d  mov     [rbp+var_8], 0FFFFFFFF80000002h
0x180053885  mov     [rsp+40h+ppv], 0
0x18005388e  lea     r9, [rbp+arg_10]
0x180053892  lea     r8, aRegisteredflig; "RegisteredFlightIdCount"
0x180053899  mov     edx, [rsi+50h]
0x18005389c  lea     rcx, [rbp+var_8]
0x1800538a0  call    ?GetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAK2@Z; MitigationRegUtils::GetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong *,ushort const *)
0x1800538a5  test    eax, eax
0x1800538a7  jns     short loc_1800538B0
0x1800538a9  mov     [rbp+arg_10], 0
0x1800538b0  mov     [rbp+arg_18], 0
0x1800538b8  mov     rdi, [rbp+var_10]
0x1800538bc  mov     rax, [rdi]
0x1800538bf  mov     rbx, [rax+88h]
0x1800538c6  lea     rcx, [rbp+arg_18]
0x1800538ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800538cf  lea     r8, [rbp+arg_18]
0x1800538d3  mov     rdx, r14
0x1800538d6  mov     rcx, rdi
0x1800538d9  mov     rax, rbx
0x1800538dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538e1  mov     ebx, eax
0x1800538e3  mov     rcx, [rbp+18h]; this
0x1800538e7  mov     [rsp+40h+var_18], 80070002h; unsigned int
0x1800538ef  mov     dword ptr [rsp+40h+ppv], 1; int
0x1800538f7  mov     r9d, eax; char *
0x1800538fa  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053901  mov     edx, 131h; void *
0x180053906  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18005390b  cmp     [rbp+arg_18], 0
0x180053910  jz      short loc_18005398F
0x180053912  test    ebx, ebx
0x180053914  js      short loc_18005398F
0x180053916  mov     rcx, [rbp+var_10]
0x18005391a  mov     rax, [rcx]
0x18005391d  mov     rdx, r14
0x180053920  mov     rax, [rax+68h]
0x180053924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053929  mov     ebx, eax
0x18005392b  test    eax, eax
0x18005392d  jns     short loc_180053953
0x18005392f  mov     edx, 135h; void *
0x180053934  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005393b  mov     r9d, eax; char *
0x18005393e  mov     rcx, [rbp+18h]; this
0x180053942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053947  nop
0x180053948  lea     rcx, [rbp+arg_18]
0x18005394c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053951  jmp     short loc_18005399A
0x180053953  mov     r9d, [rbp+arg_10]
0x180053957  dec     r9d
0x18005395a  mov     [rbp+arg_10], r9d
0x18005395e  mov     [rbp+var_8], 0FFFFFFFF80000002h
0x180053966  mov     [rsp+40h+ppv], 0
0x18005396f  lea     r8, aRegisteredflig; "RegisteredFlightIdCount"
0x180053976  mov     edx, [rsi+50h]
0x180053979  lea     rcx, [rbp+var_8]
0x18005397d  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180053982  mov     ebx, eax
0x180053984  test    eax, eax
0x180053986  jns     short loc_18005398F
0x180053988  mov     edx, 139h
0x18005398d  jmp     short loc_180053934
0x18005398f  lea     rcx, [rbp+arg_18]
0x180053993  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053998  xor     ebx, ebx
0x18005399a  lea     rcx, [rbp+var_10]
0x18005399e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800539a3  mov     eax, ebx
0x1800539a5  mov     rbx, [rsp+40h+arg_0]
0x1800539aa  mov     rsi, [rsp+40h+arg_8]
0x1800539af  add     rsp, 40h
0x1800539b3  pop     r14
0x1800539b5  pop     rdi
0x1800539b6  pop     rbp
0x1800539b7  retn
```

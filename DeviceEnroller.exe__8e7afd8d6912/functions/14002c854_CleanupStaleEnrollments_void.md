# CleanupStaleEnrollments(void)

- ea: `0x14002c854`
- end: `0x14002ca8f`
- name: `?CleanupStaleEnrollments@@YAJXZ`
- size: `571`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x14000715c`
- `0x1400095b4`
- `0x14002c854`
- `0x14002e208`
- `0x140030964`
- `0x14005d010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14002c872`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14002c872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c990`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c9a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c9a3`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c99b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c9e5`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ca0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ca38`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c99b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c9e5`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ca0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ca38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002c90e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002c90e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CleanupStaleEnrollments(void)
{
  __int64 DatabaseManagerInstance; // rax
  int v1; // eax
  unsigned int v2; // ebx
  void (*v3)(void); // rax
  HRESULT v5; // eax
  __int64 (__fastcall *v6)(__int64, BSTR *); // r14
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v11; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v13; // [rsp+70h] [rbp+30h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h] BYREF

  v10 = 0;
  v16 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v1 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64))(*(_QWORD *)DatabaseManagerInstance + 24LL))(
         DatabaseManagerInstance,
         222306401,
         &v10,
         1);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v1,
      ppv);
    if ( !v16 )
    {
LABEL_5:
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return v2;
    }
    v3 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
LABEL_4:
    v3();
    goto LABEL_5;
  }
  v11 = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v11);
  v2 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      ppva);
    wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v11);
LABEL_10:
    if ( !v16 )
      goto LABEL_5;
    v3 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
    goto LABEL_4;
  }
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v16) )
  {
    v13 = 0;
    v14 = 0;
    bstrString = 0;
    v6 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 32LL);
    bstrString = 0;
    v7 = v6(v16, &bstrString);
    v2 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1927,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v7,
        ppva);
      if ( bstrString )
        SysFreeString(bstrString);
      wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v11);
      goto LABEL_10;
    }
    if ( (int)IsValidEnrollment(bstrString, &v14, (enum EnrollmentStateTag *)&v13) >= 0 )
    {
      if ( v13 == 4 )
        DeleteSchedules(bstrString);
      if ( bstrString )
        SysFreeString(bstrString);
    }
    else if ( bstrString )
    {
      SysFreeString(bstrString);
    }
  }
  wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&v11);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x14002c854  push    rbp
0x14002c856  push    rbx
0x14002c857  push    rsi
0x14002c858  push    rdi
0x14002c859  push    r14
0x14002c85b  mov     rbp, rsp
0x14002c85e  sub     rsp, 40h
0x14002c862  mov     [rbp+var_10], 0
0x14002c86a  mov     [rbp+arg_18], 0
0x14002c872  call    cs:__imp_GetDatabaseManagerInstance
0x14002c878  mov     r10, rax
0x14002c87b  mov     rcx, [rax]
0x14002c87e  mov     rax, [rcx+18h]
0x14002c882  mov     edi, 1
0x14002c887  mov     r9d, edi
0x14002c88a  lea     r8, [rbp+var_10]
0x14002c88e  mov     edx, 0D402061h
0x14002c893  mov     rcx, r10
0x14002c896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c89b  mov     ebx, eax
0x14002c89d  test    eax, eax
0x14002c89f  jns     short loc_14002C8EA
0x14002c8a1  mov     rcx, [rbp+28h]; this
0x14002c8a5  mov     r9d, eax; char *
0x14002c8a8  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002c8af  mov     edx, 191Bh; void *
0x14002c8b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c8b9  mov     rcx, [rbp+arg_18]
0x14002c8bd  test    rcx, rcx
0x14002c8c0  jz      short loc_14002C8CE
0x14002c8c2  mov     rdx, [rcx]
0x14002c8c5  mov     rax, [rdx+10h]
0x14002c8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8ce  mov     rcx, [rbp+var_10]
0x14002c8d2  test    rcx, rcx
0x14002c8d5  jz      short loc_14002C8E3
0x14002c8d7  mov     rax, [rcx]
0x14002c8da  mov     rax, [rax+10h]
0x14002c8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8e3  mov     eax, ebx
0x14002c8e5  jmp     loc_14002CA84
0x14002c8ea  mov     [rbp+var_8], 0
0x14002c8f2  lea     rax, [rbp+var_8]
0x14002c8f6  mov     qword ptr [rsp+40h+ppv], rax; int
0x14002c8fb  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002c902  mov     r8d, edi; dwClsContext
0x14002c905  xor     edx, edx; pUnkOuter
0x14002c907  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002c90e  call    cs:__imp_CoCreateInstance
0x14002c914  mov     ebx, eax
0x14002c916  test    eax, eax
0x14002c918  jns     short loc_14002C952
0x14002c91a  mov     rcx, [rbp+28h]; this
0x14002c91e  mov     r9d, eax; char *
0x14002c921  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002c928  mov     edx, 191Eh; void *
0x14002c92d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c932  nop
0x14002c933  lea     rcx, [rbp+var_8]
0x14002c937  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002c93c  nop
0x14002c93d  mov     rcx, [rbp+arg_18]
0x14002c941  test    rcx, rcx
0x14002c944  jz      short loc_14002C8CE
0x14002c946  mov     rax, [rcx]
0x14002c949  mov     rax, [rax+10h]
0x14002c94d  jmp     loc_14002C8C9
0x14002c952  mov     rcx, [rbp+var_10]
0x14002c956  mov     rax, [rcx]
0x14002c959  lea     rdx, [rbp+arg_18]
0x14002c95d  mov     rax, [rax+18h]
0x14002c961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c966  test    eax, eax
0x14002c968  jnz     loc_14002CA4E
0x14002c96e  mov     [rbp+arg_0], eax
0x14002c971  mov     [rbp+arg_8], eax
0x14002c974  mov     [rbp+bstrString], 0
0x14002c97c  mov     rsi, [rbp+arg_18]
0x14002c980  mov     rax, [rsi]
0x14002c983  mov     r14, [rax+20h]
0x14002c987  mov     rdi, [rbp+bstrString]
0x14002c98b  test    rdi, rdi
0x14002c98e  jz      short loc_14002C9AA
0x14002c990  call    cs:__imp_GetLastError
0x14002c996  mov     ebx, eax
0x14002c998  mov     rcx, rdi; bstrString
0x14002c99b  call    cs:__imp_SysFreeString
0x14002c9a1  mov     ecx, ebx; dwErrCode
0x14002c9a3  call    cs:__imp_SetLastError
0x14002c9a9  nop
0x14002c9aa  mov     [rbp+bstrString], 0
0x14002c9b2  lea     rdx, [rbp+bstrString]
0x14002c9b6  mov     rcx, rsi
0x14002c9b9  mov     rax, r14
0x14002c9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9c1  mov     ebx, eax
0x14002c9c3  test    eax, eax
0x14002c9c5  js      short loc_14002CA16
0x14002c9c7  lea     r8, [rbp+arg_0]; enum EnrollmentStateTag *
0x14002c9cb  lea     rdx, [rbp+arg_8]; int *
0x14002c9cf  mov     rcx, [rbp+bstrString]; StringUuid
0x14002c9d3  call    ?IsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; IsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x14002c9d8  test    eax, eax
0x14002c9da  jns     short loc_14002C9F1
0x14002c9dc  mov     rcx, [rbp+bstrString]; bstrString
0x14002c9e0  test    rcx, rcx
0x14002c9e3  jz      short loc_14002C9EC
0x14002c9e5  call    cs:__imp_SysFreeString
0x14002c9eb  nop
0x14002c9ec  jmp     loc_14002C952
0x14002c9f1  cmp     [rbp+arg_0], 4
0x14002c9f5  jnz     short loc_14002CA01
0x14002c9f7  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x14002c9fb  call    ?DeleteSchedules@@YAJPEBG@Z; DeleteSchedules(ushort const *)
0x14002ca00  nop
0x14002ca01  mov     rcx, [rbp+bstrString]; bstrString
0x14002ca05  test    rcx, rcx
0x14002ca08  jz      short loc_14002CA11
0x14002ca0a  call    cs:__imp_SysFreeString
0x14002ca10  nop
0x14002ca11  jmp     loc_14002C952
0x14002ca16  mov     rcx, [rbp+28h]; this
0x14002ca1a  mov     r9d, ebx; char *
0x14002ca1d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002ca24  mov     edx, 1927h; void *
0x14002ca29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002ca2e  nop
0x14002ca2f  mov     rcx, [rbp+bstrString]; bstrString
0x14002ca33  test    rcx, rcx
0x14002ca36  jz      short loc_14002CA3F
0x14002ca38  call    cs:__imp_SysFreeString
0x14002ca3e  nop
0x14002ca3f  lea     rcx, [rbp+var_8]
0x14002ca43  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002ca48  nop
0x14002ca49  jmp     loc_14002C93D
0x14002ca4e  lea     rcx, [rbp+var_8]
0x14002ca52  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002ca57  nop
0x14002ca58  mov     rcx, [rbp+arg_18]
0x14002ca5c  test    rcx, rcx
0x14002ca5f  jz      short loc_14002CA6D
0x14002ca61  mov     rax, [rcx]
0x14002ca64  mov     rax, [rax+10h]
0x14002ca68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ca6d  mov     rcx, [rbp+var_10]
0x14002ca71  test    rcx, rcx
0x14002ca74  jz      short loc_14002CA82
0x14002ca76  mov     rax, [rcx]
0x14002ca79  mov     rax, [rax+10h]
0x14002ca7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ca82  xor     eax, eax
0x14002ca84  add     rsp, 40h
0x14002ca88  pop     r14
0x14002ca8a  pop     rdi
0x14002ca8b  pop     rsi
0x14002ca8c  pop     rbx
0x14002ca8d  pop     rbp
0x14002ca8e  retn
```

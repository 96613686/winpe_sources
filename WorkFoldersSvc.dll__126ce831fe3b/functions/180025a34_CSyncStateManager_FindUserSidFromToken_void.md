# CSyncStateManager::FindUserSidFromToken(void *)

- ea: `0x180025a34`
- end: `0x180025c3d`
- name: `?FindUserSidFromToken@CSyncStateManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `521`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180023e64`
- `0x180025850`

## callees

- `0x180002f98`
- `0x180003604`
- `0x18000444c`
- `0x180007b9c`
- `0x180007e10`
- `0x1800083b4`
- `0x180008bdc`
- `0x180009424`
- `0x180011314`
- `0x1800155b8`
- `0x180025a34`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180025bd9`
- `ADVAPI32!GetTokenInformation` at `0x180025b45`
- `ADVAPI32!GetTokenInformation` at `0x180025b45`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180025b9a`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180025b9a`

## string_xrefs

- `0x180025ab6`: `CSyncStateManager::FindUserSidFromToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSyncStateManager::FindUserSidFromToken(__int64 a1, void *a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  void *v6; // rax
  PSID *v7; // rbx
  DWORD ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  int v10; // [rsp+34h] [rbp-4Ch]
  LPWSTR StringSid; // [rsp+38h] [rbp-48h] BYREF
  LPVOID TokenInformation; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v13[16]; // [rsp+48h] [rbp-38h] BYREF
  int LastFailureAsHRESULT; // [rsp+58h] [rbp-28h] BYREF
  int v15; // [rsp+5Ch] [rbp-24h]
  char v16; // [rsp+60h] [rbp-20h]
  const char *v17; // [rsp+68h] [rbp-18h]
  __int64 v18; // [rsp+70h] [rbp-10h]
  HLOCAL (__stdcall *pExceptionObject)(HLOCAL); // [rsp+A8h] [rbp+28h] BYREF

  v10 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  v15 = 805;
  v16 = v5;
  v17 = "CSyncStateManager::FindUserSidFromToken";
  v18 = 0;
  LastFailureAsHRESULT = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    HIWORD(v15) = 807;
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v15) = 807;
  v6 = operator new[](0x80u);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
    &TokenInformation,
    (__int64)v6);
  ReturnLength = 0;
  v7 = (PSID *)TokenInformation;
  if ( !GetTokenInformation(a2, TokenUser, TokenInformation, 0x80u, &ReturnLength) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v15) = 817;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v15) = 817;
  StringSid = 0;
  LastFailureAsHRESULT = 0;
  if ( !ConvertSidToStringSidW(*v7, &StringSid) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v15) = 825;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v15) = 825;
  pExceptionObject = LocalFree;
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(v13, StringSid, &pExceptionObject);
  std::wstring::wstring(a1, (__int64)StringSid);
  v10 = 1;
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(v13);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&TokenInformation);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a1;
}

```

## disassembly

```asm
0x180025a34  mov     [rsp-18h+arg_10], rbx
0x180025a39  mov     [rsp-18h+arg_0], rcx
0x180025a3e  push    rbp
0x180025a3f  push    rsi
0x180025a40  push    rdi
0x180025a41  mov     rbp, rsp
0x180025a44  sub     rsp, 80h
0x180025a4b  mov     rsi, rdx
0x180025a4e  mov     rdi, rcx
0x180025a51  mov     [rbp+var_4C], 0
0x180025a58  lea     rcx, WPP_GLOBAL_Control
0x180025a5f  mov     rax, cs:WPP_GLOBAL_Control
0x180025a66  cmp     rax, rcx
0x180025a69  jz      short loc_180025A93
0x180025a6b  test    byte ptr [rax+44h], 8
0x180025a6f  jz      short loc_180025AA3
0x180025a71  cmp     byte ptr [rax+41h], 6
0x180025a75  jb      short loc_180025A93
0x180025a77  mov     edx, 2Eh ; '.'
0x180025a7c  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x180025a83  mov     rcx, [rax+38h]
0x180025a87  call    WPP_SF_
0x180025a8c  mov     rax, cs:WPP_GLOBAL_Control
0x180025a93  test    byte ptr [rax+44h], 8
0x180025a97  jz      short loc_180025AA3
0x180025a99  cmp     byte ptr [rax+41h], 6
0x180025a9d  jb      short loc_180025AA3
0x180025a9f  mov     cl, 1
0x180025aa1  jmp     short loc_180025AA5
0x180025aa3  xor     cl, cl
0x180025aa5  mov     [rbp+var_28], 0
0x180025aac  mov     [rbp+var_24], 325h
0x180025ab3  mov     [rbp+var_20], cl
0x180025ab6  lea     rax, aCsyncstatemana; "CSyncStateManager::FindUserSidFromToken"
0x180025abd  mov     [rbp+var_18], rax
0x180025ac1  mov     [rbp+var_10], 0
0x180025ac9  mov     eax, [rbp+var_28]
0x180025acc  mov     [rbp+var_28], eax
0x180025acf  mov     eax, 327h
0x180025ad4  test    rsi, rsi
0x180025ad7  jnz     short loc_180025AF9
0x180025ad9  mov     ecx, 80070057h
0x180025ade  mov     [rbp+var_28], ecx
0x180025ae1  mov     word ptr [rbp+var_24+2], ax
0x180025ae5  mov     dword ptr [rbp+pExceptionObject], ecx
0x180025ae8  lea     rdx, _TI1J; pThrowInfo
0x180025aef  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025af3  call    _CxxThrowException_0
0x180025af9  mov     [rbp+var_28], 0
0x180025b00  mov     word ptr [rbp+var_24], ax
0x180025b04  mov     ebx, 80h
0x180025b09  mov     ecx, ebx; unsigned __int64
0x180025b0b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025b10  mov     rdx, rax
0x180025b13  lea     rcx, [rbp+TokenInformation]
0x180025b17  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180025b1c  nop
0x180025b1d  mov     [rbp+var_50], 0
0x180025b24  mov     eax, [rbp+var_28]
0x180025b27  mov     [rbp+var_28], eax
0x180025b2a  lea     rax, [rbp+var_50]
0x180025b2e  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180025b33  mov     r9d, ebx; TokenInformationLength
0x180025b36  mov     rbx, [rbp+TokenInformation]
0x180025b3a  mov     r8, rbx; TokenInformation
0x180025b3d  mov     edx, 1; TokenInformationClass
0x180025b42  mov     rcx, rsi; TokenHandle
0x180025b45  call    cs:__imp_GetTokenInformation
0x180025b4b  test    eax, eax
0x180025b4d  jnz     short loc_180025B74
0x180025b4f  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180025b54  mov     [rbp+var_28], eax
0x180025b57  mov     ecx, 331h
0x180025b5c  mov     word ptr [rbp+var_24+2], cx
0x180025b60  mov     dword ptr [rbp+pExceptionObject], eax
0x180025b63  lea     rdx, _TI1J; pThrowInfo
0x180025b6a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025b6e  call    _CxxThrowException_0
0x180025b74  mov     [rbp+var_28], 0
0x180025b7b  mov     ecx, 331h
0x180025b80  mov     word ptr [rbp+var_24], cx
0x180025b84  mov     [rbp+StringSid], 0
0x180025b8c  mov     [rbp+var_28], 0
0x180025b93  lea     rdx, [rbp+StringSid]; StringSid
0x180025b97  mov     rcx, [rbx]; Sid
0x180025b9a  call    cs:__imp_ConvertSidToStringSidW
0x180025ba0  test    eax, eax
0x180025ba2  jnz     short loc_180025BC9
0x180025ba4  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180025ba9  mov     [rbp+var_28], eax
0x180025bac  mov     ecx, 339h
0x180025bb1  mov     word ptr [rbp+var_24+2], cx
0x180025bb5  mov     dword ptr [rbp+pExceptionObject], eax
0x180025bb8  lea     rdx, _TI1J; pThrowInfo
0x180025bbf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025bc3  call    _CxxThrowException_0
0x180025bc9  mov     [rbp+var_28], 0
0x180025bd0  mov     ecx, 339h
0x180025bd5  mov     word ptr [rbp+var_24], cx
0x180025bd9  mov     rax, cs:__imp_LocalFree
0x180025be0  mov     [rbp+pExceptionObject], rax
0x180025be4  lea     r8, [rbp+pExceptionObject]
0x180025be8  mov     rdx, [rbp+StringSid]
0x180025bec  lea     rcx, [rbp+var_38]
0x180025bf0  call    ??$?0P6AXPEAX@Z$0A@@?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@PEAU_WTSINFOW@@$$QEAP6AXPEAX@Z@Z; std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(_WTSINFOW *,void (*&&)(void *))
0x180025bf5  nop
0x180025bf6  mov     rdx, [rbp+StringSid]
0x180025bfa  mov     rcx, rdi
0x180025bfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025c02  mov     [rbp+var_4C], 1
0x180025c09  lea     rcx, [rbp+var_38]
0x180025c0d  call    ??1?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(void)
0x180025c12  nop
0x180025c13  lea     rcx, [rbp+TokenInformation]
0x180025c17  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180025c1c  nop
0x180025c1d  lea     rcx, [rbp+var_28]; this
0x180025c21  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180025c26  mov     rax, rdi
0x180025c29  mov     rbx, [rsp+80h+arg_10]
0x180025c31  add     rsp, 80h
0x180025c38  pop     rdi
0x180025c39  pop     rsi
0x180025c3a  pop     rbp
0x180025c3b  retn
```

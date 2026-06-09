# _lambda_5ead74b4d734f6c27653397ddc974cd2_::operator()

- ea: `0x1800223ac`
- end: `0x180022525`
- name: `_lambda_5ead74b4d734f6c27653397ddc974cd2_::operator()`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800259b0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000ecc0`
- `0x18001f348`
- `0x1800223ac`
- `0x180035e0c`
- `0x1800ae010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022456`
- `ntdll!RtlNtStatusToDosError` at `0x180022456`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002244e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002244e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180022419`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall lambda_5ead74b4d734f6c27653397ddc974cd2_::operator()(__int64 a1, _QWORD *a2)
{
  NTSTATUS v3; // eax
  signed int v4; // eax
  signed int v5; // ebx
  _BYTE *v6; // rdx
  _QWORD v8[2]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+38h] [rbp-C8h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  PVOID PolicyHandle; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v12[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE *v13; // [rsp+F0h] [rbp-10h]

  v8[1] = a2;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *a2 = 0;
  a2[1] = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_c5399190df6e85c53a32f0af191c3f1b_,void,void *>::`vftable';
  pExceptionObject[1] = a2;
  pExceptionObject[2] = LsaClose;
  pExceptionObject[7] = pExceptionObject;
  stdext::GetPointer<void *>::GetPointer<void *>(&PolicyHandle, pExceptionObject);
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0xF0FFFu, &PolicyHandle);
  v4 = RtlNtStatusToDosError(v3);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v13 )
  {
    v8[0] = PolicyHandle;
    (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v13 + 16LL))(v13, v8);
    if ( v13 )
    {
      v6 = v12;
      LOBYTE(v6) = v13 != v12;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v13 + 32LL))(v13, v6);
    }
  }
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids,
        (unsigned int)v5);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x1800223ac  mov     [rsp-8+arg_0], rbx
0x1800223b1  mov     [rsp-8+arg_10], rdi
0x1800223b6  push    rbp
0x1800223b7  lea     rbp, [rsp-10h]
0x1800223bc  sub     rsp, 110h
0x1800223c3  mov     rax, cs:__security_cookie
0x1800223ca  xor     rax, rsp
0x1800223cd  mov     [rbp+10h+var_10], rax
0x1800223d1  mov     rdi, rdx
0x1800223d4  mov     [rsp+110h+var_E0], rdx
0x1800223d9  mov     [rsp+110h+var_F0], 0
0x1800223e1  xorps   xmm0, xmm0
0x1800223e4  movups  xmmword ptr [rsp+110h+ObjectAttributes.Length], xmm0
0x1800223e9  movups  xmmword ptr [rbp+10h+ObjectAttributes.ObjectName], xmm0
0x1800223ed  movups  xmmword ptr [rbp+10h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800223f1  mov     qword ptr [rdx], 0
0x1800223f8  mov     qword ptr [rdx+8], 0
0x180022400  mov     [rsp+110h+var_F0], 1
0x180022408  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c5399190df6e85c53a32f0af191c3f1b_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c5399190df6e85c53a32f0af191c3f1b_,void,void *>::`vftable'
0x18002240f  mov     [rsp+110h+pExceptionObject], rax
0x180022414  mov     [rsp+110h+var_D0], rdx
0x180022419  mov     rax, cs:__imp_LsaClose
0x180022420  mov     [rsp+110h+var_C8], rax
0x180022425  lea     rax, [rsp+110h+pExceptionObject]
0x18002242a  mov     [rsp+110h+var_A0], rax
0x18002242f  lea     rdx, [rsp+110h+pExceptionObject]
0x180022434  lea     rcx, [rbp+10h+PolicyHandle]
0x180022438  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x18002243d  lea     r9, [rbp+10h+PolicyHandle]; PolicyHandle
0x180022441  mov     r8d, 0F0FFFh; DesiredAccess
0x180022447  lea     rdx, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18002244c  xor     ecx, ecx; SystemName
0x18002244e  call    cs:__imp_LsaOpenPolicy
0x180022454  mov     ecx, eax; Status
0x180022456  call    cs:__imp_RtlNtStatusToDosError
0x18002245c  mov     ebx, eax
0x18002245e  test    eax, eax
0x180022460  jle     short loc_18002246B
0x180022462  movzx   ebx, ax
0x180022465  or      ebx, 80070000h
0x18002246b  mov     rcx, [rbp+10h+var_20]
0x18002246f  test    rcx, rcx
0x180022472  jz      short loc_1800224AE
0x180022474  mov     rax, [rbp+10h+PolicyHandle]
0x180022478  mov     [rsp+110h+var_E8], rax
0x18002247d  mov     rax, [rcx]
0x180022480  lea     rdx, [rsp+110h+var_E8]
0x180022485  mov     rax, [rax+10h]
0x180022489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002248e  mov     rcx, [rbp+10h+var_20]
0x180022492  test    rcx, rcx
0x180022495  jz      short loc_1800224AE
0x180022497  mov     rax, [rcx]
0x18002249a  lea     rdx, [rbp+10h+var_58]
0x18002249e  cmp     rcx, rdx
0x1800224a1  setnz   dl
0x1800224a4  mov     rax, [rax+20h]
0x1800224a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224ad  nop
0x1800224ae  test    ebx, ebx
0x1800224b0  js      short loc_1800224D6
0x1800224b2  mov     rax, rdi
0x1800224b5  mov     rcx, [rbp+10h+var_10]
0x1800224b9  xor     rcx, rsp; StackCookie
0x1800224bc  call    __security_check_cookie
0x1800224c1  lea     r11, [rsp+110h+var_s0]
0x1800224c9  mov     rbx, [r11+10h]
0x1800224cd  mov     rdi, [r11+20h]
0x1800224d1  mov     rsp, r11
0x1800224d4  pop     rbp
0x1800224d5  retn
0x1800224d6  lea     rax, WPP_GLOBAL_Control
0x1800224dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224e4  cmp     rcx, rax
0x1800224e7  jz      short loc_180022507
0x1800224e9  test    byte ptr [rcx+1Ch], 1
0x1800224ed  jz      short loc_180022507
0x1800224ef  mov     edx, 0Ah
0x1800224f4  mov     r9d, ebx
0x1800224f7  lea     r8, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids
0x1800224fe  mov     rcx, [rcx+10h]
0x180022502  call    WPP_SF_d
0x180022507  mov     edx, ebx; int
0x180022509  lea     rcx, [rsp+110h+pExceptionObject]; this
0x18002250e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180022513  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002251a  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x18002251f  call    _CxxThrowException_0
```

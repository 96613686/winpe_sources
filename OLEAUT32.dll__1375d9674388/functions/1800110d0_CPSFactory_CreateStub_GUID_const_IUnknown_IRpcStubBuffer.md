# CPSFactory::CreateStub(_GUID const &,IUnknown *,IRpcStubBuffer * *)

- ea: `0x1800110d0`
- end: `0x180011445`
- name: `?CreateStub@CPSFactory@@UEAAJAEBU_GUID@@PEAUIUnknown@@PEAPEAUIRpcStubBuffer@@@Z`
- size: `885`
- prototype: `int(CPSFactory *__hidden this, const struct _GUID *, struct IUnknown *, struct IRpcStubBuffer **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000f900`
- `0x1800110d0`
- `0x18001186c`
- `0x180011c60`
- `0x18004d900`
- `0x18009a618`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800111a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800111a3`

## pseudocode

```c
__int64 __fastcall CPSFactory::CreateStub(
        CPSFactory *this,
        struct _GUID *a2,
        struct IUnknown *a3,
        struct IRpcStubBuffer **a4)
{
  __int64 v6; // rax
  __int64 v8; // rax
  struct IRpcStubBuffer *v9; // rbx
  __int64 v10; // rax
  signed int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  signed int LastError; // eax
  struct _GUID Buf1; // [rsp+20h] [rbp-48h] BYREF

  *a4 = 0;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( !v6 )
    goto LABEL_4;
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IEnumVARIANT.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IEnumVARIANT.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IEnumVARIANT.Data4;
  if ( !v13 )
    goto LABEL_4;
  v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITypeInfo.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITypeInfo.Data1 )
    v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITypeInfo.Data4;
  if ( !v14 )
    goto LABEL_4;
  v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITypeInfo2.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITypeInfo2.Data1 )
    v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITypeInfo2.Data4;
  if ( !v15 )
    goto LABEL_4;
  v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITypeLib.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITypeLib.Data1 )
    v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITypeLib.Data4;
  if ( !v16 )
    goto LABEL_4;
  v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITypeLib2.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITypeLib2.Data1 )
    v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITypeLib2.Data4;
  if ( !v17 )
    goto LABEL_4;
  v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITypeComp.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITypeComp.Data1 )
    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITypeComp.Data4;
  if ( !v18 )
    goto LABEL_4;
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISupportErrorInfo.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISupportErrorInfo.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISupportErrorInfo.Data4;
  if ( !v19 )
  {
LABEL_4:
    v8 = MemAlloc(96);
    v9 = (struct IRpcStubBuffer *)v8;
    if ( v8 )
    {
      *(_DWORD *)(v8 + 8) = 1;
      *(_QWORD *)v8 = &CStubWrapper::`vftable';
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 0;
      *(_QWORD *)(v8 + 32) = 0;
      *(struct _GUID *)(v8 + 40) = *a2;
      *(_OWORD *)(v8 + 56) = 0;
      *(_OWORD *)(v8 + 72) = 0;
      *(_QWORD *)(v8 + 88) = 0;
      goto LABEL_8;
    }
    return 2147942414LL;
  }
  Buf1 = 0;
  result = ProxyStubCLSIDOfInterface(a2, &Buf1);
  if ( (int)result < 0 )
    return result;
  if ( memcmp_0(&Buf1, &CLSID_PSDispatch, 0x10u) )
  {
    if ( memcmp_0(&Buf1, &CLSID_PSAutomation, 0x10u) )
      return 2147500037LL;
    v20 = MemAlloc(96);
    v9 = (struct IRpcStubBuffer *)v20;
    if ( v20 )
    {
      *(_DWORD *)(v20 + 8) = 1;
      *(_QWORD *)v20 = &CStubWrapper::`vftable';
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 0;
      *(_QWORD *)(v20 + 32) = 0;
      *(struct _GUID *)(v20 + 40) = *a2;
      *(_OWORD *)(v20 + 56) = 0;
      *(_OWORD *)(v20 + 72) = 0;
      *(_QWORD *)(v20 + 88) = 0;
      *(_QWORD *)v20 = &CUnivStubWrapper::`vftable';
      goto LABEL_8;
    }
    return 2147942414LL;
  }
  v10 = MemAlloc(112);
  v9 = (struct IRpcStubBuffer *)v10;
  if ( !v10 )
    return 2147942414LL;
  *(_DWORD *)(v10 + 8) = 1;
  *(_QWORD *)v10 = &CStubWrapper::`vftable';
  *(_QWORD *)(v10 + 16) = 0;
  *(_QWORD *)(v10 + 24) = 0;
  *(_QWORD *)(v10 + 32) = 0;
  *(struct _GUID *)(v10 + 40) = *a2;
  *(_OWORD *)(v10 + 56) = 0;
  *(_OWORD *)(v10 + 72) = 0;
  *(_QWORD *)(v10 + 88) = 0;
  *(_QWORD *)v10 = &CDispStubWrapper::`vftable';
  *(_QWORD *)(v10 + 96) = &CDispStubWrapper::CDispWrapper::`vftable';
LABEL_8:
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)&v9[7], 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    *(_OWORD *)&v9[7].lpVtbl = 0;
    *(_OWORD *)&v9[9].lpVtbl = 0;
    v9[11].lpVtbl = 0;
    if ( v11 < 0 )
      goto LABEL_45;
  }
  if ( a3 && (v11 = CStubWrapper::Connect((CStubWrapper *)v9, a3), v11 < 0) )
  {
LABEL_45:
    ((void (__fastcall *)(struct IRpcStubBuffer *, __int64))v9->lpVtbl[1].QueryInterface)(v9, 1);
    return (unsigned int)v11;
  }
  else
  {
    *a4 = v9;
    return 0;
  }
}

```

## disassembly

```asm
0x1800110d0  mov     [rsp+arg_0], rbx
0x1800110d5  push    rbp
0x1800110d6  push    rsi
0x1800110d7  push    rdi
0x1800110d8  push    r12
0x1800110da  push    r14
0x1800110dc  sub     rsp, 40h
0x1800110e0  mov     rax, cs:__security_cookie
0x1800110e7  xor     rax, rsp
0x1800110ea  mov     [rsp+68h+var_38], rax
0x1800110ef  mov     qword ptr [r9], 0
0x1800110f6  mov     r14, r9
0x1800110f9  mov     rax, [rdx]
0x1800110fc  mov     rbp, r8
0x1800110ff  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180011106  mov     rdi, rdx
0x180011109  jnz     short loc_180011116
0x18001110b  mov     rax, [rdx+8]
0x18001110f  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180011116  mov     r12d, 1
0x18001111c  test    rax, rax
0x18001111f  jnz     loc_1800111EE
0x180011125  mov     ecx, 60h ; '`'
0x18001112a  call    MemAlloc
0x18001112f  mov     rbx, rax
0x180011132  test    rax, rax
0x180011135  jz      loc_180011386
0x18001113b  mov     [rbx+8], r12d
0x18001113f  lea     rax, ??_7CStubWrapper@@6B@; const CStubWrapper::`vftable'
0x180011146  mov     [rbx], rax
0x180011149  xorps   xmm1, xmm1
0x18001114c  mov     qword ptr [rbx+10h], 0
0x180011154  xor     eax, eax
0x180011156  mov     qword ptr [rbx+18h], 0
0x18001115e  mov     qword ptr [rbx+20h], 0
0x180011166  movups  xmm0, xmmword ptr [rdi]
0x180011169  movdqu  xmmword ptr [rbx+28h], xmm0
0x18001116e  movups  xmmword ptr [rbx+38h], xmm1
0x180011172  movups  xmmword ptr [rbx+48h], xmm1
0x180011176  mov     [rbx+58h], rax
0x18001117a  jmp     short loc_18001119D
0x18001117c  mov     ecx, 70h ; 'p'
0x180011181  call    MemAlloc
0x180011186  mov     rbx, rax
0x180011189  test    rax, rax
0x18001118c  jnz     loc_18001139A
0x180011192  xor     ebx, ebx
0x180011194  test    rbx, rbx
0x180011197  jz      loc_180011386
0x18001119d  xor     edx, edx; dwSpinCount
0x18001119f  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800111a3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800111a9  test    eax, eax
0x1800111ab  jz      loc_1800113F3
0x1800111b1  test    rbp, rbp
0x1800111b4  jz      short loc_1800111CB
0x1800111b6  mov     rdx, rbp; struct IUnknown *
0x1800111b9  mov     rcx, rbx; this
0x1800111bc  call    ?Connect@CStubWrapper@@UEAAJPEAUIUnknown@@@Z; CStubWrapper::Connect(IUnknown *)
0x1800111c1  mov     edi, eax
0x1800111c3  test    eax, eax
0x1800111c5  js      loc_18001143C
0x1800111cb  mov     [r14], rbx
0x1800111ce  xor     eax, eax
0x1800111d0  mov     rcx, [rsp+68h+var_38]
0x1800111d5  xor     rcx, rsp; StackCookie
0x1800111d8  call    __security_check_cookie
0x1800111dd  mov     rbx, [rsp+68h+arg_0]
0x1800111e2  add     rsp, 40h
0x1800111e6  pop     r14
0x1800111e8  pop     r12
0x1800111ea  pop     rdi
0x1800111eb  pop     rsi
0x1800111ec  pop     rbp
0x1800111ed  retn
0x1800111ee  mov     rax, [rdx]
0x1800111f1  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data1
0x1800111f8  jnz     short loc_180011205
0x1800111fa  mov     rax, [rdx+8]
0x1800111fe  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data4
0x180011205  test    rax, rax
0x180011208  jz      loc_180011125
0x18001120e  mov     rax, [rdx]
0x180011211  sub     rax, qword ptr cs:IID_ITypeInfo.Data1
0x180011218  jnz     short loc_180011225
0x18001121a  mov     rax, [rdx+8]
0x18001121e  sub     rax, qword ptr cs:IID_ITypeInfo.Data4
0x180011225  test    rax, rax
0x180011228  jz      loc_180011125
0x18001122e  mov     rax, [rdx]
0x180011231  sub     rax, qword ptr cs:IID_ITypeInfo2.Data1
0x180011238  jnz     short loc_180011245
0x18001123a  mov     rax, [rdx+8]
0x18001123e  sub     rax, qword ptr cs:IID_ITypeInfo2.Data4
0x180011245  test    rax, rax
0x180011248  jz      loc_180011125
0x18001124e  mov     rax, [rdx]
0x180011251  sub     rax, qword ptr cs:IID_ITypeLib.Data1
0x180011258  jnz     short loc_180011265
0x18001125a  mov     rax, [rdx+8]
0x18001125e  sub     rax, qword ptr cs:IID_ITypeLib.Data4
0x180011265  test    rax, rax
0x180011268  jz      loc_180011125
0x18001126e  mov     rax, [rdx]
0x180011271  sub     rax, qword ptr cs:IID_ITypeLib2.Data1
0x180011278  jnz     short loc_180011285
0x18001127a  mov     rax, [rdx+8]
0x18001127e  sub     rax, qword ptr cs:IID_ITypeLib2.Data4
0x180011285  test    rax, rax
0x180011288  jz      loc_180011125
0x18001128e  mov     rax, [rdx]
0x180011291  sub     rax, qword ptr cs:IID_ITypeComp.Data1
0x180011298  jnz     short loc_1800112A5
0x18001129a  mov     rax, [rdx+8]
0x18001129e  sub     rax, qword ptr cs:IID_ITypeComp.Data4
0x1800112a5  test    rax, rax
0x1800112a8  jz      loc_180011125
0x1800112ae  mov     rax, [rdx]
0x1800112b1  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800112b8  jnz     short loc_1800112C5
0x1800112ba  mov     rax, [rdx+8]
0x1800112be  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x1800112c5  test    rax, rax
0x1800112c8  jz      loc_180011125
0x1800112ce  xorps   xmm0, xmm0
0x1800112d1  lea     rdx, [rsp+68h+Buf1]; struct _GUID *
0x1800112d6  mov     rcx, rdi; rguid
0x1800112d9  movups  [rsp+68h+Buf1], xmm0
0x1800112de  call    ?ProxyStubCLSIDOfInterface@@YAJAEBU_GUID@@PEAU1@@Z; ProxyStubCLSIDOfInterface(_GUID const &,_GUID *)
0x1800112e3  test    eax, eax
0x1800112e5  js      loc_1800111D0
0x1800112eb  mov     ebx, 10h
0x1800112f0  lea     rdx, CLSID_PSDispatch; Buf2
0x1800112f7  mov     r8d, ebx; Size
0x1800112fa  lea     rcx, [rsp+68h+Buf1]; Buf1
0x1800112ff  call    memcmp_0
0x180011304  test    eax, eax
0x180011306  jz      loc_18001117C
0x18001130c  mov     r8d, ebx; Size
0x18001130f  lea     rdx, CLSID_PSAutomation; Buf2
0x180011316  lea     rcx, [rsp+68h+Buf1]; Buf1
0x18001131b  call    memcmp_0
0x180011320  test    eax, eax
0x180011322  jnz     short loc_180011390
0x180011324  lea     ecx, [rbx+50h]
0x180011327  call    MemAlloc
0x18001132c  mov     rbx, rax
0x18001132f  test    rax, rax
0x180011332  jz      loc_180011192
0x180011338  mov     [rbx+8], r12d
0x18001133c  lea     rax, ??_7CStubWrapper@@6B@; const CStubWrapper::`vftable'
0x180011343  mov     [rbx], rax
0x180011346  xorps   xmm1, xmm1
0x180011349  mov     qword ptr [rbx+10h], 0
0x180011351  xor     eax, eax
0x180011353  mov     qword ptr [rbx+18h], 0
0x18001135b  mov     qword ptr [rbx+20h], 0
0x180011363  movups  xmm0, xmmword ptr [rdi]
0x180011366  movdqu  xmmword ptr [rbx+28h], xmm0
0x18001136b  movups  xmmword ptr [rbx+38h], xmm1
0x18001136f  movups  xmmword ptr [rbx+48h], xmm1
0x180011373  mov     [rbx+58h], rax
0x180011377  lea     rax, ??_7CUnivStubWrapper@@6B@; const CUnivStubWrapper::`vftable'
0x18001137e  mov     [rbx], rax
0x180011381  jmp     loc_18001119D
0x180011386  mov     eax, 8007000Eh
0x18001138b  jmp     loc_1800111D0
0x180011390  mov     eax, 80004005h
0x180011395  jmp     loc_1800111D0
0x18001139a  mov     [rbx+8], r12d
0x18001139e  lea     rax, ??_7CStubWrapper@@6B@; const CStubWrapper::`vftable'
0x1800113a5  mov     [rbx], rax
0x1800113a8  xorps   xmm1, xmm1
0x1800113ab  mov     qword ptr [rbx+10h], 0
0x1800113b3  xor     eax, eax
0x1800113b5  mov     qword ptr [rbx+18h], 0
0x1800113bd  mov     qword ptr [rbx+20h], 0
0x1800113c5  movups  xmm0, xmmword ptr [rdi]
0x1800113c8  movdqu  xmmword ptr [rbx+28h], xmm0
0x1800113cd  movups  xmmword ptr [rbx+38h], xmm1
0x1800113d1  movups  xmmword ptr [rbx+48h], xmm1
0x1800113d5  mov     [rbx+58h], rax
0x1800113d9  lea     rax, ??_7CDispStubWrapper@@6B@; const CDispStubWrapper::`vftable'
0x1800113e0  mov     [rbx], rax
0x1800113e3  lea     rax, ??_7CDispWrapper@CDispStubWrapper@@6B@; const CDispStubWrapper::CDispWrapper::`vftable'
0x1800113ea  mov     [rbx+60h], rax
0x1800113ee  jmp     loc_18001119D
0x1800113f3  call    cs:__imp_GetLastError
0x1800113f9  mov     edi, eax
0x1800113fb  test    eax, eax
0x1800113fd  jg      short loc_180011431
0x1800113ff  xorps   xmm0, xmm0
0x180011402  xor     eax, eax
0x180011404  movups  xmmword ptr [rbx+38h], xmm0
0x180011408  movups  xmmword ptr [rbx+48h], xmm0
0x18001140c  mov     [rbx+58h], rax
0x180011410  test    edi, edi
0x180011412  jns     loc_1800111B1
0x180011418  mov     r8, [rbx]
0x18001141b  mov     rax, [r8+50h]
0x18001141f  mov     rcx, rbx
0x180011422  mov     edx, r12d
0x180011425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001142a  mov     eax, edi
0x18001142c  jmp     loc_1800111D0
0x180011431  movzx   edi, ax
0x180011434  or      edi, 80070000h
0x18001143a  jmp     short loc_1800113FF
0x18001143c  mov     rcx, [rbx]
0x18001143f  mov     rax, [rcx+50h]
0x180011443  jmp     short loc_18001141F
```

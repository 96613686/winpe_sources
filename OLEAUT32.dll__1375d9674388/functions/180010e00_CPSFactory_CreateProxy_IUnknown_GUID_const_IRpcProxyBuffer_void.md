# CPSFactory::CreateProxy(IUnknown *,_GUID const &,IRpcProxyBuffer * *,void * *)

- ea: `0x180010e00`
- end: `0x1800110c5`
- name: `?CreateProxy@CPSFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAUIRpcProxyBuffer@@PEAPEAX@Z`
- size: `709`
- prototype: `int(CPSFactory *__hidden this, struct IUnknown *, const struct _GUID *, struct IRpcProxyBuffer **, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000f900`
- `0x180010e00`
- `0x18001186c`
- `0x180022964`
- `0x180032e80`
- `0x18004d900`
- `0x18009a618`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001108f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001108f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011045`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180011045`

## pseudocode

```c
__int64 __fastcall CPSFactory::CreateProxy(
        CPSFactory *this,
        struct IUnknown *a2,
        struct _GUID *a3,
        struct IRpcProxyBuffer **a4,
        void **a5)
{
  __int64 v8; // rax
  CProxyWrapper *v9; // rbx
  GUID v10; // xmm0
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 result; // rax
  CProxyWrapper *v19; // rax
  signed int LastError; // eax
  unsigned int v21; // edx
  signed int v22; // edi
  struct _GUID Buf1; // [rsp+20h] [rbp-38h] BYREF

  *a4 = 0;
  *a5 = 0;
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( !v8 )
    goto LABEL_4;
  v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IEnumVARIANT.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IEnumVARIANT.Data1 )
    v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IEnumVARIANT.Data4;
  if ( !v11 )
    goto LABEL_4;
  v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITypeInfo.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITypeInfo.Data1 )
    v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITypeInfo.Data4;
  if ( !v12 )
    goto LABEL_4;
  v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITypeInfo2.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITypeInfo2.Data1 )
    v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITypeInfo2.Data4;
  if ( !v13 )
    goto LABEL_4;
  v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITypeLib.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITypeLib.Data1 )
    v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITypeLib.Data4;
  if ( !v14 )
    goto LABEL_4;
  v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITypeLib2.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITypeLib2.Data1 )
    v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITypeLib2.Data4;
  if ( !v15 )
    goto LABEL_4;
  v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITypeComp.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITypeComp.Data1 )
    v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITypeComp.Data4;
  if ( !v16 )
    goto LABEL_4;
  v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ISupportErrorInfo.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ISupportErrorInfo.Data1 )
    v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ISupportErrorInfo.Data4;
  if ( !v17 )
  {
LABEL_4:
    v9 = (CProxyWrapper *)MemAlloc(96);
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &CProxyWrapper::`vftable';
      v10 = *a3;
      *((_DWORD *)v9 + 7) = 0;
LABEL_6:
      *((_QWORD *)v9 + 6) = 0;
      *((_QWORD *)v9 + 5) = 0;
      *((_QWORD *)v9 + 4) = a2;
      *(GUID *)((char *)v9 + 12) = v10;
      if ( !a2 )
        *((_QWORD *)v9 + 4) = v9;
      *(_OWORD *)((char *)v9 + 56) = 0;
      *(_OWORD *)((char *)v9 + 72) = 0;
      *((_QWORD *)v9 + 11) = 0;
      goto LABEL_39;
    }
    return 2147942414LL;
  }
  Buf1 = 0;
  result = ProxyStubCLSIDOfInterface(a3, &Buf1);
  if ( (int)result < 0 )
    return result;
  if ( memcmp_0(&Buf1, &CLSID_PSDispatch, 0x10u) )
  {
    if ( memcmp_0(&Buf1, &CLSID_PSAutomation, 0x10u) )
      return 2147500037LL;
    v9 = (CProxyWrapper *)MemAlloc(96);
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &CProxyWrapper::`vftable';
      v10 = *a3;
      *((_DWORD *)v9 + 7) = 2;
      goto LABEL_6;
    }
    goto LABEL_37;
  }
  v19 = (CProxyWrapper *)MemAlloc(96);
  if ( !v19 )
  {
LABEL_37:
    v9 = 0;
    goto LABEL_38;
  }
  v9 = CProxyWrapper::CProxyWrapper(v19, a2, a3, 4u);
LABEL_38:
  if ( !v9 )
    return 2147942414LL;
LABEL_39:
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)v9 + 56), 0) )
    goto LABEL_40;
  LastError = GetLastError();
  v22 = LastError;
  if ( LastError > 0 )
    v22 = (unsigned __int16)LastError | 0x80070000;
  *(_OWORD *)((char *)v9 + 56) = 0;
  *(_OWORD *)((char *)v9 + 72) = 0;
  *((_QWORD *)v9 + 11) = 0;
  if ( v22 >= 0 )
  {
LABEL_40:
    *a4 = (struct IRpcProxyBuffer *)v9;
    return 0;
  }
  else
  {
    CProxyWrapper::`scalar deleting destructor'(v9, v21);
    return (unsigned int)v22;
  }
}

```

## disassembly

```asm
0x180010e00  mov     [rsp+arg_0], rbx
0x180010e05  push    rsi
0x180010e06  push    rdi
0x180010e07  push    r14
0x180010e09  sub     rsp, 40h
0x180010e0d  mov     rax, cs:__security_cookie
0x180010e14  xor     rax, rsp
0x180010e17  mov     [rsp+58h+var_28], rax
0x180010e1c  mov     rax, [rsp+58h+arg_20]
0x180010e24  mov     r14, r9
0x180010e27  mov     qword ptr [r9], 0
0x180010e2e  mov     rdi, r8
0x180010e31  mov     rsi, rdx
0x180010e34  mov     qword ptr [rax], 0
0x180010e3b  mov     rax, [r8]
0x180010e3e  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180010e45  jnz     short loc_180010E52
0x180010e47  mov     rax, [r8+8]
0x180010e4b  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180010e52  test    rax, rax
0x180010e55  jnz     short loc_180010EC0
0x180010e57  mov     ecx, 60h ; '`'
0x180010e5c  call    MemAlloc
0x180010e61  mov     rbx, rax
0x180010e64  test    rax, rax
0x180010e67  jz      loc_18001106F
0x180010e6d  lea     rax, ??_7CProxyWrapper@@6B@; const CProxyWrapper::`vftable'
0x180010e74  mov     dword ptr [rbx+8], 1
0x180010e7b  mov     [rbx], rax
0x180010e7e  movups  xmm0, xmmword ptr [rdi]
0x180010e81  mov     dword ptr [rbx+1Ch], 0
0x180010e88  mov     qword ptr [rbx+30h], 0
0x180010e90  mov     qword ptr [rbx+28h], 0
0x180010e98  mov     [rbx+20h], rsi
0x180010e9c  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180010ea1  test    rsi, rsi
0x180010ea4  jnz     short loc_180010EAA
0x180010ea6  mov     [rbx+20h], rbx
0x180010eaa  xorps   xmm0, xmm0
0x180010ead  xor     eax, eax
0x180010eaf  movups  xmmword ptr [rbx+38h], xmm0
0x180010eb3  movups  xmmword ptr [rbx+48h], xmm0
0x180010eb7  mov     [rbx+58h], rax
0x180010ebb  jmp     loc_18001103F
0x180010ec0  mov     rax, [r8]
0x180010ec3  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data1
0x180010eca  jnz     short loc_180010ED7
0x180010ecc  mov     rax, [r8+8]
0x180010ed0  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data4
0x180010ed7  test    rax, rax
0x180010eda  jz      loc_180010E57
0x180010ee0  mov     rax, [r8]
0x180010ee3  sub     rax, qword ptr cs:IID_ITypeInfo.Data1
0x180010eea  jnz     short loc_180010EF7
0x180010eec  mov     rax, [r8+8]
0x180010ef0  sub     rax, qword ptr cs:IID_ITypeInfo.Data4
0x180010ef7  test    rax, rax
0x180010efa  jz      loc_180010E57
0x180010f00  mov     rax, [r8]
0x180010f03  sub     rax, qword ptr cs:IID_ITypeInfo2.Data1
0x180010f0a  jnz     short loc_180010F17
0x180010f0c  mov     rax, [r8+8]
0x180010f10  sub     rax, qword ptr cs:IID_ITypeInfo2.Data4
0x180010f17  test    rax, rax
0x180010f1a  jz      loc_180010E57
0x180010f20  mov     rax, [r8]
0x180010f23  sub     rax, qword ptr cs:IID_ITypeLib.Data1
0x180010f2a  jnz     short loc_180010F37
0x180010f2c  mov     rax, [r8+8]
0x180010f30  sub     rax, qword ptr cs:IID_ITypeLib.Data4
0x180010f37  test    rax, rax
0x180010f3a  jz      loc_180010E57
0x180010f40  mov     rax, [r8]
0x180010f43  sub     rax, qword ptr cs:IID_ITypeLib2.Data1
0x180010f4a  jnz     short loc_180010F57
0x180010f4c  mov     rax, [r8+8]
0x180010f50  sub     rax, qword ptr cs:IID_ITypeLib2.Data4
0x180010f57  test    rax, rax
0x180010f5a  jz      loc_180010E57
0x180010f60  mov     rax, [r8]
0x180010f63  sub     rax, qword ptr cs:IID_ITypeComp.Data1
0x180010f6a  jnz     short loc_180010F77
0x180010f6c  mov     rax, [r8+8]
0x180010f70  sub     rax, qword ptr cs:IID_ITypeComp.Data4
0x180010f77  test    rax, rax
0x180010f7a  jz      loc_180010E57
0x180010f80  mov     rax, [r8]
0x180010f83  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x180010f8a  jnz     short loc_180010F97
0x180010f8c  mov     rax, [r8+8]
0x180010f90  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x180010f97  test    rax, rax
0x180010f9a  jz      loc_180010E57
0x180010fa0  xorps   xmm0, xmm0
0x180010fa3  lea     rdx, [rsp+58h+Buf1]; struct _GUID *
0x180010fa8  mov     rcx, rdi; rguid
0x180010fab  movups  [rsp+58h+Buf1], xmm0
0x180010fb0  call    ?ProxyStubCLSIDOfInterface@@YAJAEBU_GUID@@PEAU1@@Z; ProxyStubCLSIDOfInterface(_GUID const &,_GUID *)
0x180010fb5  test    eax, eax
0x180010fb7  js      loc_180011054
0x180010fbd  mov     ebx, 10h
0x180010fc2  lea     rdx, CLSID_PSDispatch; Buf2
0x180010fc9  mov     r8d, ebx; Size
0x180010fcc  lea     rcx, [rsp+58h+Buf1]; Buf1
0x180010fd1  call    memcmp_0
0x180010fd6  test    eax, eax
0x180010fd8  jz      short loc_180011029
0x180010fda  mov     r8d, ebx; Size
0x180010fdd  lea     rdx, CLSID_PSAutomation; Buf2
0x180010fe4  lea     rcx, [rsp+58h+Buf1]; Buf1
0x180010fe9  call    memcmp_0
0x180010fee  test    eax, eax
0x180010ff0  jnz     short loc_180011022
0x180010ff2  lea     ecx, [rbx+50h]
0x180010ff5  call    MemAlloc
0x180010ffa  mov     rbx, rax
0x180010ffd  test    rax, rax
0x180011000  jz      short loc_180011038
0x180011002  lea     rax, ??_7CProxyWrapper@@6B@; const CProxyWrapper::`vftable'
0x180011009  mov     dword ptr [rbx+8], 1
0x180011010  mov     [rbx], rax
0x180011013  movups  xmm0, xmmword ptr [rdi]
0x180011016  mov     dword ptr [rbx+1Ch], 2
0x18001101d  jmp     loc_180010E88
0x180011022  mov     eax, 80004005h
0x180011027  jmp     short loc_180011054
0x180011029  mov     ecx, 60h ; '`'
0x18001102e  call    MemAlloc
0x180011033  test    rax, rax
0x180011036  jnz     short loc_180011076
0x180011038  xor     ebx, ebx
0x18001103a  test    rbx, rbx
0x18001103d  jz      short loc_18001106F
0x18001103f  xor     edx, edx; dwSpinCount
0x180011041  lea     rcx, [rbx+38h]; lpCriticalSection
0x180011045  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001104b  test    eax, eax
0x18001104d  jz      short loc_18001108F
0x18001104f  mov     [r14], rbx
0x180011052  xor     eax, eax
0x180011054  mov     rcx, [rsp+58h+var_28]
0x180011059  xor     rcx, rsp; StackCookie
0x18001105c  call    __security_check_cookie
0x180011061  mov     rbx, [rsp+58h+arg_0]
0x180011066  add     rsp, 40h
0x18001106a  pop     r14
0x18001106c  pop     rdi
0x18001106d  pop     rsi
0x18001106e  retn
0x18001106f  mov     eax, 8007000Eh
0x180011074  jmp     short loc_180011054
0x180011076  mov     r9d, 4; unsigned int
0x18001107c  mov     r8, rdi; struct _GUID *
0x18001107f  mov     rdx, rsi; struct IUnknown *
0x180011082  mov     rcx, rax; this
0x180011085  call    ??0CProxyWrapper@@QEAA@PEAUIUnknown@@AEBU_GUID@@K@Z; CProxyWrapper::CProxyWrapper(IUnknown *,_GUID const &,ulong)
0x18001108a  mov     rbx, rax
0x18001108d  jmp     short loc_18001103A
0x18001108f  call    cs:__imp_GetLastError
0x180011095  mov     edi, eax
0x180011097  test    eax, eax
0x180011099  jle     short loc_1800110A4
0x18001109b  movzx   edi, ax
0x18001109e  or      edi, 80070000h
0x1800110a4  xorps   xmm0, xmm0
0x1800110a7  xor     eax, eax
0x1800110a9  movups  xmmword ptr [rbx+38h], xmm0
0x1800110ad  movups  xmmword ptr [rbx+48h], xmm0
0x1800110b1  mov     [rbx+58h], rax
0x1800110b5  test    edi, edi
0x1800110b7  jns     short loc_18001104F
0x1800110b9  mov     rcx, rbx; this
0x1800110bc  call    ??_GCProxyWrapper@@QEAAPEAXI@Z; CProxyWrapper::`scalar deleting destructor'(uint)
0x1800110c1  mov     eax, edi
0x1800110c3  jmp     short loc_180011054
```

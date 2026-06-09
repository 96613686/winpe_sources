# LocalFileBroker::GetEDPHostPolicyForFile(ushort const *,ushort * *)

- ea: `0x18001cb10`
- end: `0x18001cbf4`
- name: `?GetEDPHostPolicyForFile@LocalFileBroker@@UEAAJPEBGPEAPEAG@Z`
- size: `228`
- prototype: `int(LocalFileBroker *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006cc4`
- `0x18000e428`
- `0x18001cb10`
- `0x180024dbc`
- `0x18002d010`

## import_xrefs

- `iertutil!CreateUri` at `0x18001cb75`
- `iertutil!CreateUri` at `0x18001cb75`
- `urlmon!__imp_GetEnterpriseIdHostPolicyForFile` at `0x18001cbb8`
- `urlmon!__imp_GetEnterpriseIdHostPolicyForFile` at `0x18001cbb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LocalFileBroker::GetEDPHostPolicyForFile(
        LocalFileBroker *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  BrowserUtilEdp *v5; // rcx
  HRESULT Uri; // ebx
  IUri *ppURI[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+30h] BYREF
  int v10; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  v9 = 0;
  if ( (int)BrokerAuthenticateAttachedCallerGetPIC(2, &v9) < 0 || !BrowserUtilEdp::IsEdpEnforcementEnabled(v5) )
    return (unsigned int)-2147467259;
  ppURI[0] = 0;
  Uri = CreateUri(a2, 0x3002B84u, 0, ppURI);
  if ( Uri >= 0 )
  {
    v9 = 0;
    Uri = ((__int64 (__fastcall *)(IUri *, unsigned int *))ppURI[0]->lpVtbl->GetScheme)(ppURI[0], &v9);
    if ( !Uri )
    {
      if ( v9 == 9 )
      {
        v10 = 0;
        Uri = GetEnterpriseIdHostPolicyForFile(a2, a3, &v10);
        if ( !v10 )
          Uri = -2147467259;
      }
      else
      {
        Uri = -2147024809;
      }
    }
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)ppURI);
  if ( Uri < 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x18001cb10  mov     [rsp-18h+arg_0], rbx
0x18001cb15  mov     [rsp-18h+arg_8], rsi
0x18001cb1a  push    rbp
0x18001cb1b  push    rdi
0x18001cb1c  push    r15
0x18001cb1e  mov     rbp, rsp
0x18001cb21  sub     rsp, 30h
0x18001cb25  mov     rsi, r8
0x18001cb28  mov     rdi, rdx
0x18001cb2b  mov     qword ptr [r8], 0
0x18001cb32  mov     [rbp+arg_10], 0
0x18001cb39  lea     rdx, [rbp+arg_10]; unsigned int *
0x18001cb3d  mov     ecx, 2; unsigned int
0x18001cb42  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18001cb47  mov     r15d, 80004005h
0x18001cb4d  test    eax, eax
0x18001cb4f  js      loc_18001CBDC
0x18001cb55  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x18001cb5a  test    al, al
0x18001cb5c  jz      short loc_18001CBDC
0x18001cb5e  mov     [rbp+ppURI], 0
0x18001cb66  lea     r9, [rbp+ppURI]; ppURI
0x18001cb6a  xor     r8d, r8d; dwReserved
0x18001cb6d  mov     edx, 3002B84h; dwFlags
0x18001cb72  mov     rcx, rdi; pwzURI
0x18001cb75  call    cs:__imp_CreateUri
0x18001cb7b  mov     ebx, eax
0x18001cb7d  test    eax, eax
0x18001cb7f  js      short loc_18001CBCF
0x18001cb81  mov     [rbp+arg_10], 0
0x18001cb88  mov     rcx, [rbp+ppURI]
0x18001cb8c  mov     rax, [rcx]
0x18001cb8f  lea     rdx, [rbp+arg_10]
0x18001cb93  mov     rax, [rax+0C0h]
0x18001cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb9f  mov     ebx, eax
0x18001cba1  test    eax, eax
0x18001cba3  jnz     short loc_18001CBCF
0x18001cba5  cmp     [rbp+arg_10], 9
0x18001cba9  jnz     short loc_18001CBCA
0x18001cbab  mov     [rbp+arg_18], eax
0x18001cbae  lea     r8, [rbp+arg_18]
0x18001cbb2  mov     rdx, rsi
0x18001cbb5  mov     rcx, rdi
0x18001cbb8  call    cs:__imp_GetEnterpriseIdHostPolicyForFile
0x18001cbbe  mov     ebx, eax
0x18001cbc0  cmp     [rbp+arg_18], 0
0x18001cbc4  cmovz   ebx, r15d
0x18001cbc8  jmp     short loc_18001CBCF
0x18001cbca  mov     ebx, 80070057h
0x18001cbcf  lea     rcx, [rbp+ppURI]
0x18001cbd3  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001cbd8  test    ebx, ebx
0x18001cbda  jns     short loc_18001CBDF
0x18001cbdc  mov     ebx, r15d
0x18001cbdf  mov     eax, ebx
0x18001cbe1  mov     rbx, [rsp+30h+arg_0]
0x18001cbe6  mov     rsi, [rsp+30h+arg_8]
0x18001cbeb  add     rsp, 30h
0x18001cbef  pop     r15
0x18001cbf1  pop     rdi
0x18001cbf2  pop     rbp
0x18001cbf3  retn
```

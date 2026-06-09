# WwanIsPackageCapable(void *)

- ea: `0x1800ae7dc`
- end: `0x1800ae9e1`
- name: `?WwanIsPackageCapable@@YAHPEAX@Z`
- size: `517`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ad000`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x1800ae7dc`
- `0x1800ae9e8`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800ae8df`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800ae8df`
- `ntdll!RtlQueryPackageIdentity` at `0x1800ae870`
- `ntdll!RtlQueryPackageIdentity` at `0x1800ae870`
- `ntdll!RtlInitUnicodeString` at `0x1800ae8ab`
- `ntdll!RtlInitUnicodeString` at `0x1800ae8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae999`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae999`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ae953`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ae953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae987`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800ae926`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800ae926`

## string_xrefs

- `0x1800ae83b`: `_getRpcClientToken failed, dwErr = 0x%8x`
- `0x1800ae8e9`: `RtlDeriveCapabilitySidsFromName failed. Error = 0x%8x`

## pseudocode

```c
__int64 __fastcall WwanIsPackageCapable(void *a1)
{
  unsigned int v1; // edi
  unsigned int RpcClientToken; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int i; // esi
  __int64 v6; // rbx
  unsigned int v8; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pSid2[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v14[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v15[256]; // [rsp+130h] [rbp+30h] BYREF

  hObject = 0;
  memset_0(v15, 0, sizeof(v15));
  v11 = 256;
  v1 = 0;
  RpcClientToken = getRpcClientToken(&hObject, 0);
  if ( RpcClientToken )
  {
    WwanLog::Error("WwanIsPackageCapable", 0, L"_getRpcClientToken failed, dwErr = 0x%8x", RpcClientToken);
  }
  else
  {
    v3 = RtlQueryPackageIdentity(hObject, v15, &v11, 0, 0, 0);
    if ( v3 )
    {
      WwanLog::Error("WwanIsPackageCapable", 0, L"RtlQueryPackageIdentity failed. Error = 0x%8x", v3);
    }
    else
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"cellularDeviceControl");
      memset_0(pSid2, 0, 0x44u);
      memset_0(v14, 0, 0x44u);
      v4 = RtlDeriveCapabilitySidsFromName(&DestinationString, v14, pSid2);
      if ( v4 )
      {
        WwanLog::Error("WwanIsPackageCapable", 0, L"RtlDeriveCapabilitySidsFromName failed. Error = 0x%8x", v4);
      }
      else
      {
        hMem = 0;
        v8 = 0;
        if ( (int)QueryApplicationCapabilities(v15, &hMem, &v8, 0, 0, 0, 0, 0, 0) >= 0 )
        {
          for ( i = 0; i < v8; *((_QWORD *)hMem + v6) = 0 )
          {
            if ( !v1 )
              v1 = EqualSid(*((PSID *)hMem + i), pSid2);
            v6 = i;
            LocalFree(*((HLOCAL *)hMem + i++));
          }
          LocalFree(hMem);
        }
      }
    }
    if ( hObject )
      CloseHandle(hObject);
  }
  WwanLog::Info("WwanIsPackageCapable", 0, L"isCapable = %d from client %ws", v1, v15);
  return v1;
}

```

## disassembly

```asm
0x1800ae7dc  push    rbp
0x1800ae7de  push    rbx
0x1800ae7df  push    rsi
0x1800ae7e0  push    rdi
0x1800ae7e1  push    r12
0x1800ae7e3  push    r15
0x1800ae7e5  lea     rbp, [rsp-148h]
0x1800ae7ed  sub     rsp, 248h
0x1800ae7f4  mov     rax, cs:__security_cookie
0x1800ae7fb  xor     rax, rsp
0x1800ae7fe  mov     [rbp+170h+var_40], rax
0x1800ae805  mov     ebx, 100h
0x1800ae80a  lea     rcx, [rbp+170h+var_140]; void *
0x1800ae80e  xor     r15d, r15d
0x1800ae811  mov     r8d, ebx; Size
0x1800ae814  xor     edx, edx; Val
0x1800ae816  mov     [rsp+270h+hObject], r15
0x1800ae81b  call    memset_0
0x1800ae820  xor     edx, edx
0x1800ae822  mov     [rsp+270h+var_200], rbx
0x1800ae827  lea     rcx, [rsp+270h+hObject]
0x1800ae82c  mov     edi, r15d
0x1800ae82f  call    _getRpcClientToken
0x1800ae834  test    eax, eax
0x1800ae836  jz      short loc_1800AE855
0x1800ae838  mov     r9d, eax
0x1800ae83b  lea     r8, aGetrpcclientto; "_getRpcClientToken failed, dwErr = 0x%8"...
0x1800ae842  xor     edx, edx; struct _GUID *
0x1800ae844  lea     rcx, aWwanispackagec; "WwanIsPackageCapable"
0x1800ae84b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae850  jmp     loc_1800AE99F
0x1800ae855  mov     rcx, [rsp+270h+hObject]
0x1800ae85a  lea     r8, [rsp+270h+var_200]
0x1800ae85f  mov     [rsp+270h+var_248], r15
0x1800ae864  lea     rdx, [rbp+170h+var_140]
0x1800ae868  xor     r9d, r9d
0x1800ae86b  mov     [rsp+270h+var_250], r15
0x1800ae870  call    cs:__imp_RtlQueryPackageIdentity
0x1800ae876  test    eax, eax
0x1800ae878  jz      short loc_1800AE897
0x1800ae87a  lea     r8, aRtlquerypackag; "RtlQueryPackageIdentity failed. Error ="...
0x1800ae881  mov     r9d, eax
0x1800ae884  lea     rcx, aWwanispackagec; "WwanIsPackageCapable"
0x1800ae88b  xor     edx, edx; struct _GUID *
0x1800ae88d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae892  jmp     loc_1800AE98D
0x1800ae897  xorps   xmm0, xmm0
0x1800ae89a  lea     rdx, SourceString; "cellularDeviceControl"
0x1800ae8a1  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x1800ae8a6  movups  xmmword ptr [rsp+270h+DestinationString.Length], xmm0
0x1800ae8ab  call    cs:__imp_RtlInitUnicodeString
0x1800ae8b1  mov     ebx, 44h ; 'D'
0x1800ae8b6  lea     rcx, [rbp+170h+pSid2]; void *
0x1800ae8ba  mov     r8d, ebx; Size
0x1800ae8bd  xor     edx, edx; Val
0x1800ae8bf  call    memset_0
0x1800ae8c4  mov     r8d, ebx; Size
0x1800ae8c7  lea     rcx, [rbp+170h+var_190]; void *
0x1800ae8cb  xor     edx, edx; Val
0x1800ae8cd  call    memset_0
0x1800ae8d2  lea     r8, [rbp+170h+pSid2]
0x1800ae8d6  lea     rdx, [rbp+170h+var_190]
0x1800ae8da  lea     rcx, [rsp+270h+DestinationString]
0x1800ae8df  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800ae8e5  test    eax, eax
0x1800ae8e7  jz      short loc_1800AE8F2
0x1800ae8e9  lea     r8, aRtlderivecapab; "RtlDeriveCapabilitySidsFromName failed."...
0x1800ae8f0  jmp     short loc_1800AE881
0x1800ae8f2  mov     [rsp+270h+var_230], r15
0x1800ae8f7  lea     r8, [rsp+270h+var_220]
0x1800ae8fc  mov     [rsp+270h+var_238], r15
0x1800ae901  lea     rdx, [rsp+270h+hMem]
0x1800ae906  mov     [rsp+270h+var_240], r15
0x1800ae90b  lea     rcx, [rbp+170h+var_140]
0x1800ae90f  mov     [rsp+270h+var_248], r15
0x1800ae914  xor     r9d, r9d
0x1800ae917  mov     [rsp+270h+var_250], r15
0x1800ae91c  mov     [rsp+270h+hMem], r15
0x1800ae921  mov     [rsp+270h+var_220], r15d
0x1800ae926  call    cs:__imp_QueryApplicationCapabilities
0x1800ae92c  test    eax, eax
0x1800ae92e  js      short loc_1800AE98D
0x1800ae930  mov     esi, r15d
0x1800ae933  cmp     [rsp+270h+var_220], r15d
0x1800ae938  jbe     short loc_1800AE982
0x1800ae93a  mov     r12d, 1
0x1800ae940  test    edi, edi
0x1800ae942  jnz     short loc_1800AE95F
0x1800ae944  mov     rcx, [rsp+270h+hMem]
0x1800ae949  lea     rdx, [rbp+170h+pSid2]; pSid2
0x1800ae94d  mov     eax, esi
0x1800ae94f  mov     rcx, [rcx+rax*8]; pSid1
0x1800ae953  call    cs:__imp_EqualSid
0x1800ae959  test    eax, eax
0x1800ae95b  cmovnz  edi, r12d
0x1800ae95f  mov     rcx, [rsp+270h+hMem]
0x1800ae964  mov     ebx, esi
0x1800ae966  mov     rcx, [rcx+rbx*8]; hMem
0x1800ae96a  call    cs:__imp_LocalFree
0x1800ae970  mov     rax, [rsp+270h+hMem]
0x1800ae975  add     esi, r12d
0x1800ae978  mov     [rax+rbx*8], r15
0x1800ae97c  cmp     esi, [rsp+270h+var_220]
0x1800ae980  jb      short loc_1800AE940
0x1800ae982  mov     rcx, [rsp+270h+hMem]; hMem
0x1800ae987  call    cs:__imp_LocalFree
0x1800ae98d  cmp     [rsp+270h+hObject], r15
0x1800ae992  jz      short loc_1800AE99F
0x1800ae994  mov     rcx, [rsp+270h+hObject]; hObject
0x1800ae999  call    cs:__imp_CloseHandle
0x1800ae99f  lea     rax, [rbp+170h+var_140]
0x1800ae9a3  mov     r9d, edi
0x1800ae9a6  lea     r8, aIscapableDFrom; "isCapable = %d from client %ws"
0x1800ae9ad  mov     [rsp+270h+var_250], rax
0x1800ae9b2  xor     edx, edx; struct _GUID *
0x1800ae9b4  lea     rcx, aWwanispackagec; "WwanIsPackageCapable"
0x1800ae9bb  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800ae9c0  mov     eax, edi
0x1800ae9c2  mov     rcx, [rbp+170h+var_40]
0x1800ae9c9  xor     rcx, rsp; StackCookie
0x1800ae9cc  call    __security_check_cookie
0x1800ae9d1  add     rsp, 248h
0x1800ae9d8  pop     r15
0x1800ae9da  pop     r12
0x1800ae9dc  pop     rdi
0x1800ae9dd  pop     rsi
0x1800ae9de  pop     rbx
0x1800ae9df  pop     rbp
0x1800ae9e0  retn
```

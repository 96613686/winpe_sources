# CBrowserBrokerInstance::GetPackagePropertiesOfExtension(ushort const *,unsigned __int64 *,ushort * *,ushort * *)

- ea: `0x180009df0`
- end: `0x180009fd3`
- name: `?GetPackagePropertiesOfExtension@CBrowserBrokerInstance@@UEAAJPEBGPEA_KPEAPEAG2@Z`
- size: `483`
- prototype: `int(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, unsigned __int64 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003170`
- `0x180006fd8`
- `0x180007018`
- `0x180009df0`
- `0x18000c164`
- `0x18000c188`
- `0x18000e428`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180009eeb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180009f4d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180009eeb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180009f4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f87`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180009e68`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180009eb2`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180009e68`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180009eb2`

## string_xrefs

- `0x180009e41`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180009f04`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180009f66`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::GetPackagePropertiesOfExtension(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3,
        LPVOID *a4,
        unsigned __int16 **bufferLength)
{
  unsigned __int16 **v5; // r12
  int PIC; // ebx
  __int64 v10; // rdx
  LONG v11; // eax
  BYTE *v12; // rdi
  unsigned int v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  const WCHAR *v16; // rcx
  void *v17; // rcx
  const WCHAR *v18; // rcx
  void *v19; // rcx
  LPVOID v21; // [rsp+20h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+28h] [rbp-18h] BYREF
  LPWSTR ppwsz; // [rsp+30h] [rbp-10h] BYREF
  char v24; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  BYTE *v26; // [rsp+90h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  v5 = bufferLength;
  *a3 = 0;
  *a4 = 0;
  LODWORD(v26) = 0;
  *v5 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&v26);
  if ( PIC < 0 )
  {
    v10 = 3248;
    goto LABEL_3;
  }
  LODWORD(bufferLength) = 0;
  v11 = PackageIdFromFullName(a2, 0x100u, (UINT32 *)&bufferLength, 0);
  PIC = v11;
  if ( v11 > 0 )
    PIC = (unsigned __int16)v11 | 0x80070000;
  if ( PIC == -2147024774 )
  {
    v26 = (BYTE *)operator new[]((unsigned int)bufferLength);
    v12 = v26;
    v13 = PackageIdFromFullName(a2, 0x100u, (UINT32 *)&bufferLength, v26);
    if ( v13 )
    {
      PIC = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)v13, (unsigned int)v21);
LABEL_19:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v26);
      return (unsigned int)PIC;
    }
    pv = 0;
    v16 = (const WCHAR *)*((_QWORD *)v12 + 2);
    p_pv = &pv;
    ppwsz = 0;
    v24 = 1;
    PIC = SHStrDupW(v16, &ppwsz);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
    if ( PIC >= 0 )
    {
      v21 = 0;
      v18 = (const WCHAR *)*((_QWORD *)v12 + 3);
      p_pv = &v21;
      ppwsz = 0;
      v24 = 1;
      PIC = SHStrDupW(v18, &ppwsz);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
      if ( PIC >= 0 )
      {
        PIC = 0;
        *a4 = pv;
        *v5 = (unsigned __int16 *)v21;
        pv = 0;
        v21 = 0;
        *a3 = *((_QWORD *)v12 + 1);
        goto LABEL_19;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBA,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)PIC,
        (int)v21);
      v19 = v21;
      v21 = 0;
      if ( v19 )
        CoTaskMemFree(v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB8,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
        (const char *)(unsigned int)PIC,
        (int)v21);
    }
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    goto LABEL_19;
  }
  if ( PIC >= 0 )
    return (unsigned int)PIC;
  v10 = 3251;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
    (const char *)(unsigned int)PIC,
    (int)v21);
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180009df0  mov     [rsp-38h+arg_0], rbx
0x180009df5  push    rbp
0x180009df6  push    rsi
0x180009df7  push    rdi
0x180009df8  push    r12
0x180009dfa  push    r13
0x180009dfc  push    r14
0x180009dfe  push    r15
0x180009e00  mov     rbp, rsp
0x180009e03  sub     rsp, 40h
0x180009e07  mov     r12, qword ptr [rbp+bufferLength]
0x180009e0b  xor     r13d, r13d
0x180009e0e  mov     [r8], r13
0x180009e11  mov     rsi, rdx
0x180009e14  mov     [r9], r13
0x180009e17  lea     rdx, [rbp+arg_10]; unsigned int *
0x180009e1b  mov     r14, r9
0x180009e1e  mov     dword ptr [rbp+arg_10], r13d
0x180009e22  lea     ecx, [r13+1]; unsigned int
0x180009e26  mov     [r12], r13
0x180009e2a  mov     r15, r8
0x180009e2d  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180009e32  mov     ebx, eax
0x180009e34  test    eax, eax
0x180009e36  jns     short loc_180009E55
0x180009e38  mov     edx, 0CB0h; void *
0x180009e3d  mov     rcx, [rbp+38h]; this
0x180009e41  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180009e48  mov     r9d, ebx; char *
0x180009e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e50  jmp     loc_180009FB9
0x180009e55  xor     r9d, r9d; buffer
0x180009e58  mov     [rbp+bufferLength], r13d
0x180009e5c  lea     r8, [rbp+bufferLength]; bufferLength
0x180009e60  mov     edx, 100h; flags
0x180009e65  mov     rcx, rsi; packageFullName
0x180009e68  call    cs:__imp_PackageIdFromFullName
0x180009e6e  mov     ebx, eax
0x180009e70  test    eax, eax
0x180009e72  jle     short loc_180009E7D
0x180009e74  movzx   ebx, ax
0x180009e77  or      ebx, 80070000h
0x180009e7d  cmp     ebx, 8007007Ah
0x180009e83  jz      short loc_180009E94
0x180009e85  test    ebx, ebx
0x180009e87  jns     loc_180009FB9
0x180009e8d  mov     edx, 0CB3h
0x180009e92  jmp     short loc_180009E3D
0x180009e94  mov     ecx, [rbp+bufferLength]; unsigned __int64
0x180009e97  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009e9c  mov     r9, rax; buffer
0x180009e9f  mov     [rbp+arg_10], rax
0x180009ea3  lea     r8, [rbp+bufferLength]; bufferLength
0x180009ea7  mov     edx, 100h; flags
0x180009eac  mov     rcx, rsi; packageFullName
0x180009eaf  mov     rdi, rax
0x180009eb2  call    cs:__imp_PackageIdFromFullName
0x180009eb8  test    eax, eax
0x180009eba  jz      short loc_180009ECF
0x180009ebc  mov     rcx, [rbp+38h]; this
0x180009ec0  mov     r9d, eax; char *
0x180009ec3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009ec8  mov     ebx, eax
0x180009eca  jmp     loc_180009FB0
0x180009ecf  mov     [rbp+pv], r13
0x180009ed3  lea     rax, [rbp+pv]
0x180009ed7  mov     rcx, [rdi+10h]; psz
0x180009edb  lea     rdx, [rbp+ppwsz]; ppwsz
0x180009edf  mov     [rbp+var_18], rax
0x180009ee3  mov     [rbp+ppwsz], r13
0x180009ee7  mov     [rbp+var_8], 1
0x180009eeb  call    cs:__imp_SHStrDupW
0x180009ef1  lea     rcx, [rbp+var_18]
0x180009ef5  mov     ebx, eax
0x180009ef7  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180009efc  test    ebx, ebx
0x180009efe  jns     short loc_180009F31
0x180009f00  mov     rcx, [rbp+38h]; this
0x180009f04  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180009f0b  mov     r9d, ebx; char *
0x180009f0e  mov     edx, 0CB8h; void *
0x180009f13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f18  mov     rcx, [rbp+pv]; pv
0x180009f1c  mov     [rbp+pv], r13
0x180009f20  test    rcx, rcx
0x180009f23  jz      loc_180009FB0
0x180009f29  call    cs:__imp_CoTaskMemFree
0x180009f2f  jmp     short loc_180009FB0
0x180009f31  mov     [rbp+var_20], r13
0x180009f35  lea     rax, [rbp+var_20]
0x180009f39  mov     rcx, [rdi+18h]; psz
0x180009f3d  lea     rdx, [rbp+ppwsz]; ppwsz
0x180009f41  mov     [rbp+var_18], rax
0x180009f45  mov     [rbp+ppwsz], r13
0x180009f49  mov     [rbp+var_8], 1
0x180009f4d  call    cs:__imp_SHStrDupW
0x180009f53  lea     rcx, [rbp+var_18]
0x180009f57  mov     ebx, eax
0x180009f59  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180009f5e  test    ebx, ebx
0x180009f60  jns     short loc_180009F8F
0x180009f62  mov     rcx, [rbp+38h]; this
0x180009f66  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180009f6d  mov     r9d, ebx; char *
0x180009f70  mov     edx, 0CBAh; void *
0x180009f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f7a  mov     rcx, [rbp+var_20]; pv
0x180009f7e  mov     [rbp+var_20], r13
0x180009f82  test    rcx, rcx
0x180009f85  jz      short loc_180009F18
0x180009f87  call    cs:__imp_CoTaskMemFree
0x180009f8d  jmp     short loc_180009F18
0x180009f8f  mov     rax, [rbp+pv]
0x180009f93  mov     ebx, r13d
0x180009f96  mov     [r14], rax
0x180009f99  mov     rax, [rbp+var_20]
0x180009f9d  mov     [r12], rax
0x180009fa1  mov     [rbp+pv], r13
0x180009fa5  mov     [rbp+var_20], r13
0x180009fa9  mov     rax, [rdi+8]
0x180009fad  mov     [r15], rax
0x180009fb0  lea     rcx, [rbp+arg_10]
0x180009fb4  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180009fb9  mov     eax, ebx
0x180009fbb  mov     rbx, [rsp+40h+arg_0]
0x180009fc3  add     rsp, 40h
0x180009fc7  pop     r15
0x180009fc9  pop     r14
0x180009fcb  pop     r13
0x180009fcd  pop     r12
0x180009fcf  pop     rdi
0x180009fd0  pop     rsi
0x180009fd1  pop     rbp
0x180009fd2  retn
```

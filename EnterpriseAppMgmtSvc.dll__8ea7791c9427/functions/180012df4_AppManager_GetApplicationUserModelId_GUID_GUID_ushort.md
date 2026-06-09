# AppManager::GetApplicationUserModelId(_GUID,_GUID *,ushort * *)

- ea: `0x180012df4`
- end: `0x18001304b`
- name: `?GetApplicationUserModelId@AppManager@@QEAAJU_GUID@@PEAU2@PEAPEAG@Z`
- size: `599`
- prototype: `__int64 __fastcall(AppManager *__hidden this, struct _GUID *__struct_ptr, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003da0`

## callees

- `0x180005de8`
- `0x180012d54`
- `0x180012df4`
- `0x1800634c0`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012e91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012e91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012fc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012fc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180012faa`
- `OLEAUT32!__imp_SysAllocString` at `0x180012faa`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fe0`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppManager::GetApplicationUserModelId(
        AppManager *this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 **a4)
{
  OLECHAR *v7; // rcx
  HRESULT v8; // ebx
  unsigned __int16 **v9; // rsi
  BSTR v10; // rcx
  BSTR v11; // r9
  unsigned __int16 *v12; // rax
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v18; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[136]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  v16 = 0;
  v15 = 0;
  v18 = 0;
  bstrString = 0;
  v7 = 0;
  psz = 0;
  if ( a3 && a4 )
  {
    *a4 = 0;
    v8 = CoCreateInstance(&CLSID_PMSvc, 0, 0x17u, &IID_IPMEnumerationManager, &ppv);
    if ( v8 >= 0 )
    {
      v20 = (__int128)*a2;
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, &v20, &v16);
      if ( v8 >= 0 )
      {
        v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(
               v16,
               &GUID_2925390a_d947_4062_9dad_cf6f60e6a707,
               &v15);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v16 + 224LL))(v16, a3);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 24LL))(v15, &v18);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 32LL))(v15, &bstrString);
              if ( v8 >= 0 )
              {
                v9 = (unsigned __int16 **)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>((void **)&psz);
                v10 = bstrString;
                v11 = v18;
                *v9 = 0;
                v8 = StringCchPrintfW(v21, 0x82u, L"%s!%s", v11, v10);
                if ( v8 >= 0 )
                  v8 = CoAllocString(v21, v9);
                if ( v8 >= 0 )
                {
                  v12 = SysAllocString(psz);
                  *a4 = v12;
                  if ( !v12 )
                    v8 = -2147024882;
                }
              }
            }
          }
        }
      }
    }
    v7 = psz;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v7 )
    CoTaskMemFree(v7);
  SysFreeString(bstrString);
  SysFreeString(v18);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012df4  push    rbp
0x180012df6  push    rbx
0x180012df7  push    rsi
0x180012df8  push    rdi
0x180012df9  push    r14
0x180012dfb  lea     rbp, [rsp-90h]
0x180012e03  sub     rsp, 190h
0x180012e0a  mov     rax, cs:__security_cookie
0x180012e11  xor     rax, rsp
0x180012e14  mov     [rbp+0B0h+var_30], rax
0x180012e1b  mov     rdi, r9
0x180012e1e  mov     rsi, r8
0x180012e21  mov     r14, rdx
0x180012e24  mov     [rsp+1B0h+var_158], 0
0x180012e2d  mov     [rsp+1B0h+var_170], 0
0x180012e36  mov     [rsp+1B0h+var_178], 0
0x180012e3f  mov     [rsp+1B0h+var_160], 0
0x180012e48  mov     [rsp+1B0h+bstrString], 0
0x180012e51  xor     ecx, ecx
0x180012e53  mov     [rsp+1B0h+psz], rcx
0x180012e58  test    r8, r8
0x180012e5b  jnz     short loc_180012E67
0x180012e5d  mov     ebx, 80070057h
0x180012e62  jmp     loc_180012FC3
0x180012e67  test    rdi, rdi
0x180012e6a  jz      short loc_180012E5D
0x180012e6c  mov     qword ptr [r9], 0
0x180012e73  lea     rax, [rsp+1B0h+var_158]
0x180012e78  mov     [rsp+1B0h+ppv], rax; ppv
0x180012e7d  lea     r9, IID_IPMEnumerationManager; riid
0x180012e84  xor     edx, edx; pUnkOuter
0x180012e86  lea     r8d, [rdx+17h]; dwClsContext
0x180012e8a  lea     rcx, CLSID_PMSvc; rclsid
0x180012e91  call    cs:__imp_CoCreateInstance
0x180012e97  mov     ebx, eax
0x180012e99  test    eax, eax
0x180012e9b  js      loc_180012FBE
0x180012ea1  mov     rcx, [rsp+1B0h+var_158]
0x180012ea6  movaps  xmm0, xmmword ptr [r14]
0x180012eaa  movdqa  [rsp+1B0h+var_150], xmm0
0x180012eb0  mov     rax, [rcx]
0x180012eb3  lea     r8, [rsp+1B0h+var_170]
0x180012eb8  lea     rdx, [rsp+1B0h+var_150]
0x180012ebd  mov     rax, [rax+48h]
0x180012ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec6  mov     ebx, eax
0x180012ec8  test    eax, eax
0x180012eca  js      loc_180012FBE
0x180012ed0  mov     rcx, [rsp+1B0h+var_170]
0x180012ed5  mov     rax, [rcx]
0x180012ed8  lea     r8, [rsp+1B0h+var_178]
0x180012edd  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180012ee4  mov     rax, [rax]
0x180012ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eec  mov     ebx, eax
0x180012eee  test    eax, eax
0x180012ef0  js      loc_180012FBE
0x180012ef6  mov     rcx, [rsp+1B0h+var_170]
0x180012efb  mov     rax, [rcx]
0x180012efe  mov     rdx, rsi
0x180012f01  mov     rax, [rax+0E0h]
0x180012f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0d  mov     ebx, eax
0x180012f0f  test    eax, eax
0x180012f11  js      loc_180012FBE
0x180012f17  mov     rcx, [rsp+1B0h+var_178]
0x180012f1c  mov     rax, [rcx]
0x180012f1f  lea     rdx, [rsp+1B0h+var_160]
0x180012f24  mov     rax, [rax+18h]
0x180012f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f2d  mov     ebx, eax
0x180012f2f  test    eax, eax
0x180012f31  js      loc_180012FBE
0x180012f37  mov     rcx, [rsp+1B0h+var_178]
0x180012f3c  mov     rax, [rcx]
0x180012f3f  lea     rdx, [rsp+1B0h+bstrString]
0x180012f44  mov     rax, [rax+20h]
0x180012f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f4d  mov     ebx, eax
0x180012f4f  test    eax, eax
0x180012f51  js      short loc_180012FBE
0x180012f53  lea     rcx, [rsp+1B0h+psz]
0x180012f58  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x180012f5d  mov     rsi, rax
0x180012f60  mov     rcx, [rsp+1B0h+bstrString]
0x180012f65  mov     r9, [rsp+1B0h+var_160]
0x180012f6a  mov     qword ptr [rax], 0
0x180012f71  mov     [rsp+1B0h+ppv], rcx
0x180012f76  lea     r8, aSS; "%s!%s"
0x180012f7d  mov     edx, 82h; unsigned __int64
0x180012f82  lea     rcx, [rsp+1B0h+var_140]; unsigned __int16 *
0x180012f87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012f8c  mov     ebx, eax
0x180012f8e  test    eax, eax
0x180012f90  js      short loc_180012FA1
0x180012f92  mov     rdx, rsi; unsigned __int16 **
0x180012f95  lea     rcx, [rsp+1B0h+var_140]; unsigned __int16 *
0x180012f9a  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x180012f9f  mov     ebx, eax
0x180012fa1  test    ebx, ebx
0x180012fa3  js      short loc_180012FBE
0x180012fa5  mov     rcx, [rsp+1B0h+psz]; psz
0x180012faa  call    cs:__imp_SysAllocString
0x180012fb0  mov     [rdi], rax
0x180012fb3  mov     ecx, 8007000Eh
0x180012fb8  test    rax, rax
0x180012fbb  cmovz   ebx, ecx
0x180012fbe  mov     rcx, [rsp+1B0h+psz]; pv
0x180012fc3  test    rcx, rcx
0x180012fc6  jz      short loc_180012FCF
0x180012fc8  call    cs:__imp_CoTaskMemFree
0x180012fce  nop
0x180012fcf  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x180012fd4  call    cs:__imp_SysFreeString
0x180012fda  nop
0x180012fdb  mov     rcx, [rsp+1B0h+var_160]; bstrString
0x180012fe0  call    cs:__imp_SysFreeString
0x180012fe6  nop
0x180012fe7  mov     rcx, [rsp+1B0h+var_178]
0x180012fec  test    rcx, rcx
0x180012fef  jz      short loc_180012FFE
0x180012ff1  mov     rax, [rcx]
0x180012ff4  mov     rax, [rax+10h]
0x180012ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffd  nop
0x180012ffe  mov     rcx, [rsp+1B0h+var_170]
0x180013003  test    rcx, rcx
0x180013006  jz      short loc_180013015
0x180013008  mov     rax, [rcx]
0x18001300b  mov     rax, [rax+10h]
0x18001300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013014  nop
0x180013015  mov     rcx, [rsp+1B0h+var_158]
0x18001301a  test    rcx, rcx
0x18001301d  jz      short loc_18001302C
0x18001301f  mov     rax, [rcx]
0x180013022  mov     rax, [rax+10h]
0x180013026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302b  nop
0x18001302c  mov     eax, ebx
0x18001302e  mov     rcx, [rbp+0B0h+var_30]
0x180013035  xor     rcx, rsp; StackCookie
0x180013038  call    __security_check_cookie
0x18001303d  add     rsp, 190h
0x180013044  pop     r14
0x180013046  pop     rdi
0x180013047  pop     rsi
0x180013048  pop     rbx
0x180013049  pop     rbp
0x18001304a  retn
```

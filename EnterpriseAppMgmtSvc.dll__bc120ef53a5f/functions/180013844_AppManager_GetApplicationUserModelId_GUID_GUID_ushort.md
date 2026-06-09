# AppManager::GetApplicationUserModelId(_GUID,_GUID *,ushort * *)

- ea: `0x180013844`
- end: `0x180013aba`
- name: `?GetApplicationUserModelId@AppManager@@QEAAJU_GUID@@PEAU2@PEAPEAG@Z`
- size: `630`
- prototype: `__int64 __fastcall(AppManager *__hidden this, struct _GUID *__struct_ptr, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003ec0`

## callees

- `0x180005ff4`
- `0x180013794`
- `0x180013844`
- `0x180068bf8`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800138e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a24`
- `OLEAUT32!__imp_SysAllocString` at `0x180013a00`
- `OLEAUT32!__imp_SysAllocString` at `0x180013a00`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a36`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a48`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a36`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a48`

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
                v9 = (unsigned __int16 **)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&psz);
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
0x180013844  push    rbp
0x180013846  push    rbx
0x180013847  push    rsi
0x180013848  push    rdi
0x180013849  push    r14
0x18001384b  lea     rbp, [rsp-90h]
0x180013853  sub     rsp, 190h
0x18001385a  mov     rax, cs:__security_cookie
0x180013861  xor     rax, rsp
0x180013864  mov     [rbp+0B0h+var_30], rax
0x18001386b  mov     rdi, r9
0x18001386e  mov     rsi, r8
0x180013871  mov     r14, rdx
0x180013874  mov     [rsp+1B0h+var_158], 0
0x18001387d  mov     [rsp+1B0h+var_170], 0
0x180013886  mov     [rsp+1B0h+var_178], 0
0x18001388f  mov     [rsp+1B0h+var_160], 0
0x180013898  mov     [rsp+1B0h+bstrString], 0
0x1800138a1  xor     ecx, ecx
0x1800138a3  mov     [rsp+1B0h+psz], rcx
0x1800138a8  test    r8, r8
0x1800138ab  jnz     short loc_1800138B7
0x1800138ad  mov     ebx, 80070057h
0x1800138b2  jmp     loc_180013A1F
0x1800138b7  test    rdi, rdi
0x1800138ba  jz      short loc_1800138AD
0x1800138bc  mov     qword ptr [r9], 0
0x1800138c3  lea     rax, [rsp+1B0h+var_158]
0x1800138c8  mov     [rsp+1B0h+ppv], rax; ppv
0x1800138cd  lea     r9, IID_IPMEnumerationManager; riid
0x1800138d4  xor     edx, edx; pUnkOuter
0x1800138d6  lea     r8d, [rdx+17h]; dwClsContext
0x1800138da  lea     rcx, CLSID_PMSvc; rclsid
0x1800138e1  call    cs:__imp_CoCreateInstance
0x1800138e8  nop     dword ptr [rax+rax+00h]
0x1800138ed  mov     ebx, eax
0x1800138ef  test    eax, eax
0x1800138f1  js      loc_180013A1A
0x1800138f7  mov     rcx, [rsp+1B0h+var_158]
0x1800138fc  movaps  xmm0, xmmword ptr [r14]
0x180013900  movdqa  [rsp+1B0h+var_150], xmm0
0x180013906  mov     rax, [rcx]
0x180013909  lea     r8, [rsp+1B0h+var_170]
0x18001390e  lea     rdx, [rsp+1B0h+var_150]
0x180013913  mov     rax, [rax+48h]
0x180013917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001391c  mov     ebx, eax
0x18001391e  test    eax, eax
0x180013920  js      loc_180013A1A
0x180013926  mov     rcx, [rsp+1B0h+var_170]
0x18001392b  mov     rax, [rcx]
0x18001392e  lea     r8, [rsp+1B0h+var_178]
0x180013933  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x18001393a  mov     rax, [rax]
0x18001393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013942  mov     ebx, eax
0x180013944  test    eax, eax
0x180013946  js      loc_180013A1A
0x18001394c  mov     rcx, [rsp+1B0h+var_170]
0x180013951  mov     rax, [rcx]
0x180013954  mov     rdx, rsi
0x180013957  mov     rax, [rax+0E0h]
0x18001395e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013963  mov     ebx, eax
0x180013965  test    eax, eax
0x180013967  js      loc_180013A1A
0x18001396d  mov     rcx, [rsp+1B0h+var_178]
0x180013972  mov     rax, [rcx]
0x180013975  lea     rdx, [rsp+1B0h+var_160]
0x18001397a  mov     rax, [rax+18h]
0x18001397e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013983  mov     ebx, eax
0x180013985  test    eax, eax
0x180013987  js      loc_180013A1A
0x18001398d  mov     rcx, [rsp+1B0h+var_178]
0x180013992  mov     rax, [rcx]
0x180013995  lea     rdx, [rsp+1B0h+bstrString]
0x18001399a  mov     rax, [rax+20h]
0x18001399e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a3  mov     ebx, eax
0x1800139a5  test    eax, eax
0x1800139a7  js      short loc_180013A1A
0x1800139a9  lea     rcx, [rsp+1B0h+psz]
0x1800139ae  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800139b3  mov     rsi, rax
0x1800139b6  mov     rcx, [rsp+1B0h+bstrString]
0x1800139bb  mov     r9, [rsp+1B0h+var_160]
0x1800139c0  mov     qword ptr [rax], 0
0x1800139c7  mov     [rsp+1B0h+ppv], rcx
0x1800139cc  lea     r8, aSS; "%s!%s"
0x1800139d3  mov     edx, 82h; unsigned __int64
0x1800139d8  lea     rcx, [rsp+1B0h+var_140]; unsigned __int16 *
0x1800139dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800139e2  mov     ebx, eax
0x1800139e4  test    eax, eax
0x1800139e6  js      short loc_1800139F7
0x1800139e8  mov     rdx, rsi; unsigned __int16 **
0x1800139eb  lea     rcx, [rsp+1B0h+var_140]; unsigned __int16 *
0x1800139f0  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1800139f5  mov     ebx, eax
0x1800139f7  test    ebx, ebx
0x1800139f9  js      short loc_180013A1A
0x1800139fb  mov     rcx, [rsp+1B0h+psz]; psz
0x180013a00  call    cs:__imp_SysAllocString
0x180013a07  nop     dword ptr [rax+rax+00h]
0x180013a0c  mov     [rdi], rax
0x180013a0f  mov     ecx, 8007000Eh
0x180013a14  test    rax, rax
0x180013a17  cmovz   ebx, ecx
0x180013a1a  mov     rcx, [rsp+1B0h+psz]; pv
0x180013a1f  test    rcx, rcx
0x180013a22  jz      short loc_180013A31
0x180013a24  call    cs:__imp_CoTaskMemFree
0x180013a2b  nop     dword ptr [rax+rax+00h]
0x180013a30  nop
0x180013a31  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x180013a36  call    cs:__imp_SysFreeString
0x180013a3d  nop     dword ptr [rax+rax+00h]
0x180013a42  nop
0x180013a43  mov     rcx, [rsp+1B0h+var_160]; bstrString
0x180013a48  call    cs:__imp_SysFreeString
0x180013a4f  nop     dword ptr [rax+rax+00h]
0x180013a54  nop
0x180013a55  mov     rcx, [rsp+1B0h+var_178]
0x180013a5a  test    rcx, rcx
0x180013a5d  jz      short loc_180013A6C
0x180013a5f  mov     rax, [rcx]
0x180013a62  mov     rax, [rax+10h]
0x180013a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a6b  nop
0x180013a6c  mov     rcx, [rsp+1B0h+var_170]
0x180013a71  test    rcx, rcx
0x180013a74  jz      short loc_180013A83
0x180013a76  mov     rax, [rcx]
0x180013a79  mov     rax, [rax+10h]
0x180013a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a82  nop
0x180013a83  mov     rcx, [rsp+1B0h+var_158]
0x180013a88  test    rcx, rcx
0x180013a8b  jz      short loc_180013A9A
0x180013a8d  mov     rax, [rcx]
0x180013a90  mov     rax, [rax+10h]
0x180013a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a99  nop
0x180013a9a  mov     eax, ebx
0x180013a9c  mov     rcx, [rbp+0B0h+var_30]
0x180013aa3  xor     rcx, rsp; StackCookie
0x180013aa6  call    __security_check_cookie
0x180013aab  add     rsp, 190h
0x180013ab2  pop     r14
0x180013ab4  pop     rdi
0x180013ab5  pop     rsi
0x180013ab6  pop     rbx
0x180013ab7  pop     rbp
0x180013ab8  retn
```

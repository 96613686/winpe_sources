# DisableAllPollOnLoginTask(ushort const *)

- ea: `0x14000ea50`
- end: `0x14000ec5d`
- name: `?DisableAllPollOnLoginTask@@YAJPEBG@Z`
- size: `525`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140009fc4`
- `0x14000ea50`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x14000ea8f`
- `OLEAUT32!__imp_VariantInit` at `0x14000ea8f`
- `OLEAUT32!__imp_VariantClear` at `0x14000ec0b`
- `OLEAUT32!__imp_VariantClear` at `0x14000ec0b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000eafa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000eafa`

## string_xrefs

- `0x14000ebd7`: `First Login Schedule created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DisableAllPollOnLoginTask(const unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v5; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v7; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v8; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v9; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v10; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v11[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v12; // [rsp+F0h] [rbp-10h]
  __int128 v13; // [rsp+100h] [rbp+0h]
  __int128 v14; // [rsp+110h] [rbp+10h]
  int v15; // [rsp+120h] [rbp+20h]
  _BYTE v16[460]; // [rsp+124h] [rbp+24h] BYREF

  ppv = 0;
  v5 = 0;
  VariantInit(&pvarg);
  *(_OWORD *)v11 = *(_OWORD *)L"\\Microsoft\\Windows\\EnterpriseMgmt";
  v12 = *(_OWORD *)L"ft\\Windows\\EnterpriseMgmt";
  v13 = *(_OWORD *)L"ws\\EnterpriseMgmt";
  v14 = *(_OWORD *)L"priseMgmt";
  v15 = *(_DWORD *)L"t";
  memset_0(v16, 0, 0x1C4u);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v2 >= 0 )
  {
    v7 = pvarg;
    v8 = pvarg;
    v9 = pvarg;
    v10 = pvarg;
    v2 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           &v10,
           &v9,
           &v8,
           &v7);
    if ( v2 >= 0 )
    {
      v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b,
             &v5);
      if ( v2 >= 0 )
      {
        v2 = StringCchCatW(v11, 0x104u, L"\\");
        if ( v2 >= 0 )
        {
          v2 = StringCchCatW(v11, 0x104u, a1);
          if ( v2 >= 0 )
          {
            v2 = StringCchCatW(v11, 0x104u, L"\\");
            if ( v2 >= 0 )
            {
              v2 = StringCchCatW(v11, 0x104u, L"First Login Schedule created by enrollment client");
              if ( v2 >= 0 )
                v2 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v5 + 56LL))(v5, v11);
            }
          }
        }
      }
    }
  }
  VariantClear(&pvarg);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000ea50  push    rbp
0x14000ea52  push    rbx
0x14000ea53  push    rsi
0x14000ea54  push    rdi
0x14000ea55  lea     rbp, [rsp-208h]
0x14000ea5d  sub     rsp, 308h
0x14000ea64  mov     rax, cs:__security_cookie
0x14000ea6b  xor     rax, rsp
0x14000ea6e  mov     [rbp+220h+var_30], rax
0x14000ea75  mov     rdi, rcx
0x14000ea78  mov     [rsp+320h+var_2F0], 0
0x14000ea81  mov     [rsp+320h+var_2E8], 0
0x14000ea8a  lea     rcx, [rsp+320h+pvarg]; pvarg
0x14000ea8f  call    cs:__imp_VariantInit
0x14000ea95  nop
0x14000ea96  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_4; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14000ea9d  movaps  xmmword ptr [rbp+220h+var_240], xmm0
0x14000eaa1  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_4+10h; "ft\\Windows\\EnterpriseMgmt"
0x14000eaa8  movaps  [rbp+220h+var_230], xmm1
0x14000eaac  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_4+20h; "ws\\EnterpriseMgmt"
0x14000eab3  movaps  [rbp+220h+var_220], xmm0
0x14000eab7  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_4+30h; "priseMgmt"
0x14000eabe  movaps  [rbp+220h+var_210], xmm1
0x14000eac2  mov     eax, dword ptr cs:aMicrosoftWindo_4+40h; "t"
0x14000eac8  mov     [rbp+220h+var_200], eax
0x14000eacb  xor     edx, edx; Val
0x14000eacd  mov     r8d, 1C4h; Size
0x14000ead3  lea     rcx, [rbp+220h+var_1FC]; void *
0x14000ead7  call    memset_0
0x14000eadc  lea     rax, [rsp+320h+var_2F0]
0x14000eae1  mov     [rsp+320h+ppv], rax; ppv
0x14000eae6  lea     r9, IID_ITaskService; riid
0x14000eaed  xor     edx, edx; pUnkOuter
0x14000eaef  lea     r8d, [rdx+1]; dwClsContext
0x14000eaf3  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000eafa  call    cs:__imp_CoCreateInstance
0x14000eb00  mov     ebx, eax
0x14000eb02  test    eax, eax
0x14000eb04  js      loc_14000EC06
0x14000eb0a  mov     rcx, [rsp+320h+var_2F0]
0x14000eb0f  movups  xmm1, xmmword ptr [rsp+320h+pvarg]
0x14000eb14  movsd   xmm0, qword ptr [rsp+320h+pvarg+10h]
0x14000eb1a  movaps  [rsp+320h+var_2C0], xmm1
0x14000eb1f  movsd   [rsp+320h+var_2B0], xmm0
0x14000eb25  movaps  [rbp+220h+var_2A0], xmm1
0x14000eb29  movsd   [rbp+220h+var_290], xmm0
0x14000eb2e  movaps  [rbp+220h+var_280], xmm1
0x14000eb32  movsd   [rbp+220h+var_270], xmm0
0x14000eb37  movaps  [rbp+220h+var_260], xmm1
0x14000eb3b  movsd   [rbp+220h+var_250], xmm0
0x14000eb40  mov     rax, [rcx]
0x14000eb43  lea     rdx, [rsp+320h+var_2C0]
0x14000eb48  mov     [rsp+320h+ppv], rdx
0x14000eb4d  lea     r9, [rbp+220h+var_2A0]
0x14000eb51  lea     r8, [rbp+220h+var_280]
0x14000eb55  lea     rdx, [rbp+220h+var_260]
0x14000eb59  mov     rax, [rax+50h]
0x14000eb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb62  mov     ebx, eax
0x14000eb64  test    eax, eax
0x14000eb66  js      loc_14000EC06
0x14000eb6c  mov     rcx, [rsp+320h+var_2F0]
0x14000eb71  mov     rax, [rcx]
0x14000eb74  lea     r8, [rsp+320h+var_2E8]
0x14000eb79  lea     rdx, _GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b
0x14000eb80  mov     rax, [rax]
0x14000eb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb88  mov     ebx, eax
0x14000eb8a  test    eax, eax
0x14000eb8c  js      short loc_14000EC06
0x14000eb8e  lea     r8, asc_140061150; "\\"
0x14000eb95  mov     esi, 104h
0x14000eb9a  mov     edx, esi; unsigned __int64
0x14000eb9c  lea     rcx, [rbp+220h+var_240]; unsigned __int16 *
0x14000eba0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000eba5  mov     ebx, eax
0x14000eba7  test    eax, eax
0x14000eba9  js      short loc_14000EC06
0x14000ebab  mov     r8, rdi; unsigned __int16 *
0x14000ebae  mov     edx, esi; unsigned __int64
0x14000ebb0  lea     rcx, [rbp+220h+var_240]; unsigned __int16 *
0x14000ebb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ebb9  mov     ebx, eax
0x14000ebbb  test    eax, eax
0x14000ebbd  js      short loc_14000EC06
0x14000ebbf  lea     r8, asc_140061150; "\\"
0x14000ebc6  mov     edx, esi; unsigned __int64
0x14000ebc8  lea     rcx, [rbp+220h+var_240]; unsigned __int16 *
0x14000ebcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ebd1  mov     ebx, eax
0x14000ebd3  test    eax, eax
0x14000ebd5  js      short loc_14000EC06
0x14000ebd7  lea     r8, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x14000ebde  mov     edx, esi; unsigned __int64
0x14000ebe0  lea     rcx, [rbp+220h+var_240]; unsigned __int16 *
0x14000ebe4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ebe9  mov     ebx, eax
0x14000ebeb  test    eax, eax
0x14000ebed  js      short loc_14000EC06
0x14000ebef  mov     rcx, [rsp+320h+var_2E8]
0x14000ebf4  mov     rax, [rcx]
0x14000ebf7  lea     rdx, [rbp+220h+var_240]
0x14000ebfb  mov     rax, [rax+38h]
0x14000ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec04  mov     ebx, eax
0x14000ec06  lea     rcx, [rsp+320h+pvarg]; pvarg
0x14000ec0b  call    cs:__imp_VariantClear
0x14000ec11  nop
0x14000ec12  mov     rcx, [rsp+320h+var_2E8]
0x14000ec17  test    rcx, rcx
0x14000ec1a  jz      short loc_14000EC29
0x14000ec1c  mov     rax, [rcx]
0x14000ec1f  mov     rax, [rax+10h]
0x14000ec23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec28  nop
0x14000ec29  mov     rcx, [rsp+320h+var_2F0]
0x14000ec2e  test    rcx, rcx
0x14000ec31  jz      short loc_14000EC40
0x14000ec33  mov     rax, [rcx]
0x14000ec36  mov     rax, [rax+10h]
0x14000ec3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec3f  nop
0x14000ec40  mov     eax, ebx
0x14000ec42  mov     rcx, [rbp+220h+var_30]
0x14000ec49  xor     rcx, rsp; StackCookie
0x14000ec4c  call    __security_check_cookie
0x14000ec51  add     rsp, 308h
0x14000ec58  pop     rdi
0x14000ec59  pop     rsi
0x14000ec5a  pop     rbx
0x14000ec5b  pop     rbp
0x14000ec5c  retn
```

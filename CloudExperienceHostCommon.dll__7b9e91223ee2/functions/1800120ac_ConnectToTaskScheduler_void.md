# ConnectToTaskScheduler(void)

- ea: `0x1800120ac`
- end: `0x1800121a5`
- name: `?ConnectToTaskScheduler@@YA?AV?$ComPtr@UITaskService@@@WRL@Microsoft@@XZ`
- size: `249`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010394`

## callees

- `0x18000fa5c`
- `0x180010c8c`
- `0x1800120ac`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800120f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800120f9`

## string_xrefs

- `0x18001210a`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x18001217e`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPVOID *__fastcall ConnectToTaskScheduler(LPVOID *a1)
{
  HRESULT Instance; // eax
  LPVOID v3; // rcx
  int v4; // eax
  int ppv; // [rsp+20h] [rbp-49h]
  int v7[4]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v8; // [rsp+50h] [rbp-19h]
  __int128 v9; // [rsp+60h] [rbp-9h] BYREF
  __int64 v10; // [rsp+70h] [rbp+7h]
  __int128 v11; // [rsp+80h] [rbp+17h] BYREF
  __int64 v12; // [rsp+90h] [rbp+27h]
  __int128 v13; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v14; // [rsp+B0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a1 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  Instance = CoCreateInstance(
               &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
               0,
               1u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v3 = *a1;
  *(_OWORD *)v7 = xmmword_1800F9140;
  v8 = 0;
  v9 = xmmword_1800F9140;
  v10 = 0;
  v11 = xmmword_1800F9140;
  v12 = 0;
  v13 = xmmword_1800F9140;
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v3 + 80LL))(
         v3,
         &v13,
         &v11,
         &v9);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
      (const char *)(unsigned int)v4,
      (int)v7);
  return a1;
}

```

## disassembly

```asm
0x1800120ac  mov     [rsp-8+arg_8], rbx
0x1800120b1  mov     [rsp-8+arg_0], rcx
0x1800120b6  push    rbp
0x1800120b7  lea     rbp, [rsp-57h]
0x1800120bc  sub     rsp, 0C0h
0x1800120c3  mov     rbx, rcx
0x1800120c6  mov     [rbp+57h+var_90], 0
0x1800120cd  mov     qword ptr [rcx], 0
0x1800120d4  mov     [rbp+57h+var_90], 1
0x1800120db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800120e0  mov     qword ptr [rsp+0C0h+ppv], rbx; int
0x1800120e5  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800120ec  xor     edx, edx; pUnkOuter
0x1800120ee  lea     r8d, [rdx+1]; dwClsContext
0x1800120f2  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x1800120f9  call    cs:__imp_CoCreateInstance
0x1800120ff  test    eax, eax
0x180012101  jns     short loc_18001211C
0x180012103  mov     rcx, [rbp+5Fh]; this
0x180012107  mov     r9d, eax; char *
0x18001210a  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x180012111  mov     edx, 26h ; '&'; void *
0x180012116  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001211c  mov     rcx, [rbx]
0x18001211f  movups  xmm1, cs:xmmword_1800F9140
0x180012126  movsd   xmm0, cs:qword_1800F9150
0x18001212e  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x180012132  movsd   [rbp+57h+var_70], xmm0
0x180012137  movaps  [rbp+57h+var_60], xmm1
0x18001213b  movsd   [rbp+57h+var_50], xmm0
0x180012140  movaps  [rbp+57h+var_40], xmm1
0x180012144  movsd   [rbp+57h+var_30], xmm0
0x180012149  movaps  [rbp+57h+var_20], xmm1
0x18001214d  movsd   [rbp+57h+var_10], xmm0
0x180012152  mov     rax, [rcx]
0x180012155  lea     rdx, [rbp+57h+var_80]
0x180012159  mov     qword ptr [rsp+0C0h+ppv], rdx; int
0x18001215e  lea     r9, [rbp+57h+var_60]
0x180012162  lea     r8, [rbp+57h+var_40]
0x180012166  lea     rdx, [rbp+57h+var_20]
0x18001216a  mov     rax, [rax+50h]
0x18001216e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012173  test    eax, eax
0x180012175  jns     short loc_180012190
0x180012177  mov     rcx, [rbp+5Fh]; this
0x18001217b  mov     r9d, eax; char *
0x18001217e  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x180012185  mov     edx, 27h ; '''; void *
0x18001218a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012190  mov     rax, rbx
0x180012193  mov     rbx, [rsp+0C0h+arg_8]
0x18001219b  add     rsp, 0C0h
0x1800121a2  pop     rbp
0x1800121a3  retn
```

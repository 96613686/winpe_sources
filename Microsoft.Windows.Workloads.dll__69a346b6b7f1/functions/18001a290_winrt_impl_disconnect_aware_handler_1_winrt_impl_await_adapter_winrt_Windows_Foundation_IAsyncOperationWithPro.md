# winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete(void)

- ea: `0x18001a290`
- end: `0x18001a42a`
- name: `?Complete@?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@AEAAXXZ`
- size: `410`
- prototype: `int __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019270`
- `0x180019c00`
- `0x18001aa60`
- `0x18001ab20`

## callees

- `0x1800040a0`
- `0x180004a20`
- `0x18001a290`
- `0x18001ae30`
- `0x180034ef0`
- `0x180035060`
- `0x18003987b`
- `0x1800398b7`
- `0x1800398bd`
- `0x18003bed0`

## pseudocode

```c
int __fastcall winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete(
        __int64 *a1)
{
  char v2; // dl
  __int64 v3; // rax
  char v4; // cl
  __int64 (__fastcall **v5)(_QWORD); // rbx
  __int64 v6; // rbp
  LPVOID v7; // rax
  char v8; // si
  winrt *v9; // rcx
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  winrt *v12; // rcx
  LPVOID ppv; // [rsp+20h] [rbp-28h] BYREF
  APTTYPE pAptType; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  LODWORD(ppv) = 0;
  v3 = a1[2];
  v4 = *(_BYTE *)(v3 + 24);
  *(_BYTE *)(v3 + 24) = 0;
  if ( v4 )
  {
    a1[3] = 0;
    return v3;
  }
  v5 = (__int64 (__fastcall **)(_QWORD))a1[3];
  a1[3] = 0;
  v6 = a1[2] + 20;
  if ( !*a1 )
  {
    v7 = ppv;
    goto LABEL_7;
  }
  ppv = 0;
  WINRT_IMPL_CoGetObjectContext(&winrt::impl::guid_v<winrt::impl::IContextCallback>, &ppv);
  v7 = ppv;
  v2 = 3;
  if ( (LPVOID)*a1 == ppv )
  {
LABEL_7:
    v8 = 1;
    goto LABEL_8;
  }
  v8 = 0;
LABEL_8:
  if ( (v2 & 1) != 0 && v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&ppv);
  if ( v8 )
    goto LABEL_20;
  if ( *((_DWORD *)a1 + 2) == 1 )
  {
    LODWORD(v3) = TrySubmitThreadpoolCallback_0(winrt::impl::resume_background_callback, v5, 0);
    if ( !(_DWORD)v3 )
      winrt::throw_last_error(v9);
    return v3;
  }
  if ( WINRT_IMPL_CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&ppv) )
    goto LABEL_19;
  if ( pAptType == APTTYPE_STA )
    goto LABEL_23;
  if ( pAptType == APTTYPE_NA )
  {
    if ( (((_DWORD)ppv - 3) & 0xFFFFFFFD) == 0 )
      goto LABEL_23;
LABEL_19:
    LODWORD(v3) = winrt::impl::resume_apartment_sync(a1, v5, v6);
    if ( (_BYTE)v3 )
      return v3;
LABEL_20:
    LODWORD(v3) = (*v5)(v5);
    return v3;
  }
  if ( pAptType != APTTYPE_MAINSTA )
    goto LABEL_19;
LABEL_23:
  v10 = operator new(0x18u);
  ppv = v10;
  v11 = *a1;
  *v10 = *a1;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v10[1] = v5;
  v10[2] = v6;
  ppv = v10;
  LODWORD(v3) = TrySubmitThreadpoolCallback_0(winrt::impl::fallback_submit_threadpool_callback, v10, 0);
  if ( !(_DWORD)v3 )
    winrt::throw_last_error(v12);
  return v3;
}

```

## disassembly

```asm
0x18001a290  mov     [rsp+arg_8], rbx
0x18001a295  mov     [rsp+arg_10], rbp
0x18001a29a  mov     [rsp+arg_18], rsi
0x18001a29f  push    rdi
0x18001a2a0  sub     rsp, 40h
0x18001a2a4  mov     rax, cs:__security_cookie
0x18001a2ab  xor     rax, rsp
0x18001a2ae  mov     [rsp+48h+var_18], rax
0x18001a2b3  mov     rdi, rcx
0x18001a2b6  xor     edx, edx
0x18001a2b8  mov     dword ptr [rsp+48h+ppv], edx
0x18001a2bc  mov     rax, [rcx+10h]
0x18001a2c0  mov     ecx, edx
0x18001a2c2  xchg    cl, [rax+18h]
0x18001a2c5  test    cl, cl
0x18001a2c7  jz      short loc_18001A2D2
0x18001a2c9  mov     [rdi+18h], rdx
0x18001a2cd  jmp     loc_18001A3A0
0x18001a2d2  mov     rbx, [rdi+18h]
0x18001a2d6  mov     [rdi+18h], rdx
0x18001a2da  mov     rbp, [rdi+10h]
0x18001a2de  add     rbp, 14h
0x18001a2e2  cmp     [rdi], rdx
0x18001a2e5  jz      short loc_18001A316
0x18001a2e7  mov     [rsp+48h+ppv], rdx
0x18001a2ec  lea     rdx, [rsp+48h+ppv]; ppv
0x18001a2f1  lea     rcx, ??$guid_v@UIContextCallback@impl@winrt@@@impl@winrt@@3Uguid@2@B; riid
0x18001a2f8  call    WINRT_IMPL_CoGetObjectContext
0x18001a2fd  mov     rax, [rsp+48h+ppv]
0x18001a302  mov     [rsp+48h+ppv], rax
0x18001a307  mov     edx, 3
0x18001a30c  cmp     [rdi], rax
0x18001a30f  jz      short loc_18001A31B
0x18001a311  xor     sil, sil
0x18001a314  jmp     short loc_18001A31E
0x18001a316  mov     rax, [rsp+48h+ppv]
0x18001a31b  mov     sil, 1
0x18001a31e  test    dl, 1
0x18001a321  jz      short loc_18001A332
0x18001a323  test    rax, rax
0x18001a326  jz      short loc_18001A332
0x18001a328  lea     rcx, [rsp+48h+ppv]
0x18001a32d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001a332  test    sil, sil
0x18001a335  jnz     short loc_18001A394
0x18001a337  cmp     dword ptr [rdi+8], 1
0x18001a33b  jnz     short loc_18001A359
0x18001a33d  xor     r8d, r8d; pcbe
0x18001a340  mov     rdx, rbx; pv
0x18001a343  lea     rcx, ?resume_background_callback@impl@winrt@@YAXPEAX0@Z; pfns
0x18001a34a  call    TrySubmitThreadpoolCallback_0
0x18001a34f  test    eax, eax
0x18001a351  jz      loc_18001A424
0x18001a357  jmp     short loc_18001A3A0
0x18001a359  lea     rdx, [rsp+48h+ppv]; pAptQualifier
0x18001a35e  lea     rcx, [rsp+48h+pAptType]; pAptType
0x18001a363  call    WINRT_IMPL_CoGetApartmentType
0x18001a368  test    eax, eax
0x18001a36a  jnz     short loc_18001A382
0x18001a36c  mov     ecx, [rsp+48h+pAptType]
0x18001a370  mov     edx, dword ptr [rsp+48h+ppv]
0x18001a374  test    ecx, ecx
0x18001a376  jz      short loc_18001A3CC
0x18001a378  sub     ecx, 2
0x18001a37b  jz      short loc_18001A3C2
0x18001a37d  cmp     ecx, 1
0x18001a380  jz      short loc_18001A3CC
0x18001a382  mov     r8, rbp
0x18001a385  mov     rdx, rbx
0x18001a388  mov     rcx, rdi
0x18001a38b  call    ?resume_apartment_sync@impl@winrt@@YA_NAEBU?$com_ptr@UIContextCallback@impl@winrt@@@2@U?$coroutine_handle@X@experimental@std@@PEAH@Z; winrt::impl::resume_apartment_sync(winrt::com_ptr<winrt::impl::IContextCallback> const &,std::experimental::coroutine_handle<void>,int *)
0x18001a390  test    al, al
0x18001a392  jnz     short loc_18001A3A0
0x18001a394  mov     rcx, rbx
0x18001a397  mov     rax, [rbx]
0x18001a39a  call    cs:__guard_dispatch_icall_fptr
0x18001a3a0  mov     rcx, [rsp+48h+var_18]
0x18001a3a5  xor     rcx, rsp; StackCookie
0x18001a3a8  call    __security_check_cookie
0x18001a3ad  mov     rbx, [rsp+48h+arg_8]
0x18001a3b2  mov     rbp, [rsp+48h+arg_10]
0x18001a3b7  mov     rsi, [rsp+48h+arg_18]
0x18001a3bc  add     rsp, 40h
0x18001a3c0  pop     rdi
0x18001a3c1  retn
0x18001a3c2  lea     eax, [rdx-3]
0x18001a3c5  test    eax, 0FFFFFFFDh
0x18001a3ca  jnz     short loc_18001A382
0x18001a3cc  mov     ecx, 18h; Size
0x18001a3d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a3d6  mov     rsi, rax
0x18001a3d9  mov     [rsp+48h+ppv], rax
0x18001a3de  mov     rdx, [rdi]
0x18001a3e1  mov     [rax], rdx
0x18001a3e4  test    rdx, rdx
0x18001a3e7  jz      short loc_18001A3F9
0x18001a3e9  mov     rcx, [rdx]
0x18001a3ec  mov     rax, [rcx+8]
0x18001a3f0  mov     rcx, rdx
0x18001a3f3  call    cs:__guard_dispatch_icall_fptr
0x18001a3f9  mov     [rsi+8], rbx
0x18001a3fd  mov     [rsi+10h], rbp
0x18001a401  mov     [rsp+48h+ppv], rsi
0x18001a406  xor     r8d, r8d; pcbe
0x18001a409  mov     rdx, rsi; pv
0x18001a40c  lea     rcx, ?fallback_submit_threadpool_callback@impl@winrt@@YAXPEAX0@Z; pfns
0x18001a413  call    TrySubmitThreadpoolCallback_0
0x18001a418  test    eax, eax
0x18001a41a  jz      short loc_18001A41E
0x18001a41c  jmp     short loc_18001A3A0
0x18001a41e  call    ?throw_last_error@winrt@@YAXXZ; winrt::throw_last_error(void)
0x18001a424  call    ?throw_last_error@winrt@@YAXXZ; winrt::throw_last_error(void)
```

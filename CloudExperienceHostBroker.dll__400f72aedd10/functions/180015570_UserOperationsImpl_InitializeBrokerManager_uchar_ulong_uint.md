# UserOperationsImpl::InitializeBrokerManager(uchar *,ulong,uint *)

- ea: `0x180015570`
- end: `0x18001563e`
- name: `?InitializeBrokerManager@UserOperationsImpl@@UEAAJPEAEKPEAI@Z`
- size: `206`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180015570`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800155ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800155ce`

## string_xrefs

- `0x180015603`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserOperationsImpl::InitializeBrokerManager(
        UserOperationsImpl *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v12; // [rsp+48h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 && a3 )
  {
    v12 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    v6 = CoCreateInstance(
           &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
           0,
           1u,
           &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
           &v12);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int8 *, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, a2, a3);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v7 = 0;
        goto LABEL_9;
      }
      v8 = 374;
    }
    else
    {
      v8 = 373;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    return v7;
  }
  return 87;
}

```

## disassembly

```asm
0x180015570  mov     rax, rsp
0x180015573  mov     [rax+8], rbx
0x180015577  mov     [rax+18h], rsi
0x18001557b  push    rdi
0x18001557c  sub     rsp, 30h
0x180015580  mov     edi, r8d
0x180015583  mov     rsi, rdx
0x180015586  mov     dword ptr [r9], 0
0x18001558d  test    rdx, rdx
0x180015590  jz      loc_180015629
0x180015596  test    r8d, r8d
0x180015599  jz      loc_180015629
0x18001559f  mov     qword ptr [rax+10h], 0
0x1800155a7  lea     rcx, [rax+10h]
0x1800155ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800155b0  lea     rax, [rsp+38h+arg_8]
0x1800155b5  mov     qword ptr [rsp+38h+ppv], rax; int
0x1800155ba  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x1800155c1  xor     edx, edx; pUnkOuter
0x1800155c3  lea     r8d, [rdx+1]; dwClsContext
0x1800155c7  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x1800155ce  call    cs:__imp_CoCreateInstance
0x1800155d4  mov     ebx, eax
0x1800155d6  test    eax, eax
0x1800155d8  jns     short loc_1800155E1
0x1800155da  mov     edx, 175h
0x1800155df  jmp     short loc_180015603
0x1800155e1  mov     rcx, [rsp+38h+arg_8]
0x1800155e6  mov     rax, [rcx]
0x1800155e9  mov     r8d, edi
0x1800155ec  mov     rdx, rsi
0x1800155ef  mov     rax, [rax+18h]
0x1800155f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f8  mov     ebx, eax
0x1800155fa  test    eax, eax
0x1800155fc  jns     short loc_180015619
0x1800155fe  mov     edx, 176h; void *
0x180015603  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x18001560a  mov     r9d, eax; char *
0x18001560d  mov     rcx, [rsp+38h]; this
0x180015612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015617  jmp     short loc_18001561B
0x180015619  xor     ebx, ebx
0x18001561b  lea     rcx, [rsp+38h+arg_8]
0x180015620  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015625  mov     eax, ebx
0x180015627  jmp     short loc_18001562E
0x180015629  mov     eax, 57h ; 'W'
0x18001562e  mov     rbx, [rsp+38h+arg_0]
0x180015633  mov     rsi, [rsp+38h+arg_10]
0x180015638  add     rsp, 30h
0x18001563c  pop     rdi
0x18001563d  retn
```

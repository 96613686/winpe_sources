# CloudExperienceHostBroker::Cortana::OOBECortanaManager::get_HasMicrophone(uchar *)

- ea: `0x180031d30`
- end: `0x180031e25`
- name: `?get_HasMicrophone@OOBECortanaManager@Cortana@CloudExperienceHostBroker@@UEAAJPEAE@Z`
- size: `245`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana::OOBECortanaManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180018be8`
- `0x180031d30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031d75`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031d75`

## string_xrefs

- `0x180031d89`: `shell\cloudexperiencehost\broker\lib\oobecortanamanager.cpp`
- `0x180031de7`: `shell\cloudexperiencehost\broker\lib\oobecortanamanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManager::get_HasMicrophone(
        CloudExperienceHostBroker::Cortana::OOBECortanaManager *this,
        unsigned __int8 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, __int64, __int64, __int64 *); // rbx
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v12; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v3 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         1u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v12);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v11 = 0;
    v5 = v12;
    v6 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64 *))(*(_QWORD *)v12 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v7 = v6(v5, 1, 1, &v11);
    if ( v11 )
    {
      if ( v7 >= 0 )
        *a2 = 1;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobecortanamanager.cpp",
          (const char *)(unsigned int)v7,
          ppv);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobecortanamanager.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v4;
}

```

## disassembly

```asm
0x180031d30  mov     rax, rsp
0x180031d33  mov     [rax+8], rbx
0x180031d37  mov     [rax+20h], rsi
0x180031d3b  push    rdi
0x180031d3c  sub     rsp, 30h
0x180031d40  mov     rsi, rdx
0x180031d43  mov     byte ptr [rdx], 0
0x180031d46  mov     qword ptr [rax+18h], 0
0x180031d4e  lea     rcx, [rax+18h]
0x180031d52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031d57  lea     rax, [rsp+38h+arg_10]
0x180031d5c  mov     qword ptr [rsp+38h+ppv], rax; int
0x180031d61  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180031d68  xor     edx, edx; pUnkOuter
0x180031d6a  lea     r8d, [rdx+1]; dwClsContext
0x180031d6e  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180031d75  call    cs:__imp_CoCreateInstance
0x180031d7b  mov     ebx, eax
0x180031d7d  test    eax, eax
0x180031d7f  jns     short loc_180031D9C
0x180031d81  mov     rcx, [rsp+38h]; this
0x180031d86  mov     r9d, eax; char *
0x180031d89  lea     r8, aShellCloudexpe_0; "shell\\cloudexperiencehost\\broker\\lib"...
0x180031d90  mov     edx, 9Ah; void *
0x180031d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d9a  jmp     short loc_180031E09
0x180031d9c  mov     [rsp+38h+arg_8], 0
0x180031da5  mov     rdi, [rsp+38h+arg_10]
0x180031daa  mov     rax, [rdi]
0x180031dad  mov     rbx, [rax+20h]
0x180031db1  lea     rcx, [rsp+38h+arg_8]
0x180031db6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031dbb  lea     r9, [rsp+38h+arg_8]
0x180031dc0  mov     edx, 1
0x180031dc5  mov     r8d, edx
0x180031dc8  mov     rcx, rdi
0x180031dcb  mov     rax, rbx
0x180031dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dd3  cmp     [rsp+38h+arg_8], 0
0x180031dd9  jz      short loc_180031DFD
0x180031ddb  mov     rcx, [rsp+38h]; this
0x180031de0  test    eax, eax
0x180031de2  jns     short loc_180031DFA
0x180031de4  mov     r9d, eax; char *
0x180031de7  lea     r8, aShellCloudexpe_0; "shell\\cloudexperiencehost\\broker\\lib"...
0x180031dee  mov     edx, 9Fh; void *
0x180031df3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031df8  jmp     short loc_180031DFD
0x180031dfa  mov     byte ptr [rsi], 1
0x180031dfd  lea     rcx, [rsp+38h+arg_8]
0x180031e02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031e07  xor     ebx, ebx
0x180031e09  lea     rcx, [rsp+38h+arg_10]
0x180031e0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031e13  mov     eax, ebx
0x180031e15  mov     rbx, [rsp+38h+arg_0]
0x180031e1a  mov     rsi, [rsp+38h+arg_18]
0x180031e1f  add     rsp, 30h
0x180031e23  pop     rdi
0x180031e24  retn
```

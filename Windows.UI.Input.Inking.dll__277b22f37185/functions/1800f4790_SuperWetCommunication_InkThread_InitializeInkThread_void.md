# SuperWetCommunication::InkThread::InitializeInkThread(void)

- ea: `0x1800f4790`
- end: `0x1800f48ff`
- name: `?InitializeInkThread@InkThread@SuperWetCommunication@@UEAAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(SuperWetCommunication::InkThread *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800101bc`
- `0x180014a40`
- `0x1800595e4`
- `0x1800eb758`
- `0x1800f4790`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f47ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f47ef`
- `CoreMessaging!CoreUICreate` at `0x1800f47af`
- `CoreMessaging!CoreUICreate` at `0x1800f47af`

## string_xrefs

- `0x1800f47be`: `onecoreuap\windows\advcore\winrt\directink\render\superwetcommunication.inkthread.cpp`
- `0x1800f47fe`: `onecoreuap\windows\advcore\winrt\directink\render\superwetcommunication.inkthread.cpp`
- `0x1800f4840`: `onecoreuap\windows\advcore\winrt\directink\render\superwetcommunication.inkthread.cpp`
- `0x1800f48a3`: `onecoreuap\windows\advcore\winrt\directink\render\superwetcommunication.inkthread.cpp`
- `0x1800f48db`: `onecoreuap\windows\advcore\winrt\directink\render\superwetcommunication.inkthread.cpp`

## pseudocode

```c
__int64 __fastcall SuperWetCommunication::InkThread::InitializeInkThread(SuperWetCommunication::InkThread *this)
{
  _QWORD *v1; // r14
  int v3; // eax
  const char *v4; // r9
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, PSECURITY_DESCRIPTOR, char *); // rbx
  int v7; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64 (__fastcall *)(void *, const void *, int), SuperWetCommunication::InkThread *, _QWORD); // rdi
  int v10; // eax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 16);
  v3 = CoreUICreate(v1);
  if ( v3 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetcommunication.inkthread.cpp",
      (const char *)(unsigned int)v3,
      v13);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x1;;;S-1-5-90-0)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetcommunication.inkthread.cpp",
      v4);
  v5 = *v1;
  v6 = *(__int64 (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, char *))(*(_QWORD *)*v1 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 24);
  v7 = v6(v5, SecurityDescriptor, (char *)this + 24);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetcommunication.inkthread.cpp",
      (const char *)(unsigned int)v7,
      v13);
  wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void details::IMessageSessionCloseEndpointFunctionWithBlock(IMessageSession *,unsigned __int64),0>::reset(
    (char *)this + 40,
    *v1);
  v8 = *v1;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(void *, const void *, int), SuperWetCommunication::InkThread *, _QWORD))(*(_QWORD *)*v1 + 104LL);
  wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void details::IMessageSessionCloseEndpointFunctionWithBlock(IMessageSession *,unsigned __int64),0>::reset(
    (char *)this + 40,
    *((_QWORD *)this + 5));
  v14 = (_DWORD)this + 48;
  v10 = v9(v8, SuperWetCommunication::InkThread::StaticEndpointCallback, this, *((_QWORD *)this + 3));
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetcommunication.inkthread.cpp",
      (const char *)(unsigned int)v10,
      v14);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v1 + 136LL))(
          *v1,
          *((_QWORD *)this + 6),
          (char *)this + 56);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetcommunication.inkthread.cpp",
      (const char *)(unsigned int)v11,
      v14);
  return 0;
}

```

## disassembly

```asm
0x1800f4790  push    rbx
0x1800f4792  push    rbp
0x1800f4793  push    rsi
0x1800f4794  push    rdi
0x1800f4795  push    r14
0x1800f4797  push    r15
0x1800f4799  sub     rsp, 38h
0x1800f479d  lea     r14, [rcx+10h]
0x1800f47a1  mov     rbp, rcx
0x1800f47a4  mov     rcx, r14
0x1800f47a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f47ac  mov     rcx, r14
0x1800f47af  call    cs:__imp_CoreUICreate
0x1800f47b5  test    eax, eax
0x1800f47b7  jns     short loc_1800F47D3
0x1800f47b9  mov     rcx, [rsp+68h]; this
0x1800f47be  lea     r8, aOnecoreuapWind_33; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800f47c5  mov     r9d, eax; char *
0x1800f47c8  mov     edx, 12h; void *
0x1800f47cd  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800f47d3  xor     r9d, r9d; SecurityDescriptorSize
0x1800f47d6  mov     [rsp+68h+SecurityDescriptor], 0
0x1800f47df  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x1800f47e4  lea     rcx, StringSecurityDescriptor; "D:(A;;0x1;;;S-1-5-90-0)"
0x1800f47eb  lea     edx, [r9+1]; StringSDRevision
0x1800f47ef  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f47f5  test    eax, eax
0x1800f47f7  jnz     short loc_1800F480E
0x1800f47f9  mov     rcx, [rsp+68h]; this
0x1800f47fe  lea     r8, aOnecoreuapWind_33; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800f4805  lea     edx, [rax+1Fh]; void *
0x1800f4808  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f480e  mov     rdi, [r14]
0x1800f4811  lea     r15, [rbp+18h]
0x1800f4815  mov     rcx, r15
0x1800f4818  mov     rax, [rdi]
0x1800f481b  mov     rbx, [rax+40h]
0x1800f481f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f4824  mov     rdx, [rsp+68h+SecurityDescriptor]
0x1800f4829  mov     r8, r15
0x1800f482c  mov     rcx, rdi
0x1800f482f  mov     rax, rbx
0x1800f4832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4837  test    eax, eax
0x1800f4839  jns     short loc_1800F4855
0x1800f483b  mov     rcx, [rsp+68h]; this
0x1800f4840  lea     r8, aOnecoreuapWind_33; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800f4847  mov     r9d, eax; char *
0x1800f484a  mov     edx, 21h ; '!'; void *
0x1800f484f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800f4855  mov     rdx, [r14]
0x1800f4858  lea     rbx, [rbp+28h]
0x1800f485c  mov     rcx, rbx
0x1800f485f  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunctionWithBlock@details@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&details::IMessageSessionCloseEndpointFunctionWithBlock(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x1800f4864  mov     rsi, [r14]
0x1800f4867  mov     rcx, rbx
0x1800f486a  mov     rdx, [rbx]
0x1800f486d  mov     rax, [rsi]
0x1800f4870  mov     rdi, [rax+68h]
0x1800f4874  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunctionWithBlock@details@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&details::IMessageSessionCloseEndpointFunctionWithBlock(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x1800f4879  mov     r9, [r15]
0x1800f487c  lea     rdx, [rbx+8]
0x1800f4880  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800f4885  mov     r8, rbp
0x1800f4888  lea     rdx, ?StaticEndpointCallback@InkThread@SuperWetCommunication@@SAJPEAXPEBXH@Z; SuperWetCommunication::InkThread::StaticEndpointCallback(void *,void const *,int)
0x1800f488f  mov     rcx, rsi
0x1800f4892  mov     rax, rdi
0x1800f4895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f489a  test    eax, eax
0x1800f489c  jns     short loc_1800F48B8
0x1800f489e  mov     rcx, [rsp+68h]; this
0x1800f48a3  lea     r8, aOnecoreuapWind_33; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800f48aa  mov     r9d, eax; char *
0x1800f48ad  mov     edx, 29h ; ')'; void *
0x1800f48b2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800f48b8  mov     rcx, [r14]
0x1800f48bb  lea     r8, [rbp+38h]
0x1800f48bf  mov     rdx, [rbp+30h]
0x1800f48c3  mov     rax, [rcx]
0x1800f48c6  mov     rax, [rax+88h]
0x1800f48cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f48d2  test    eax, eax
0x1800f48d4  jns     short loc_1800F48F0
0x1800f48d6  mov     rcx, [rsp+68h]; this
0x1800f48db  lea     r8, aOnecoreuapWind_33; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800f48e2  mov     r9d, eax; char *
0x1800f48e5  mov     edx, 2Dh ; '-'; void *
0x1800f48ea  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800f48f0  xor     eax, eax
0x1800f48f2  add     rsp, 38h
0x1800f48f6  pop     r15
0x1800f48f8  pop     r14
0x1800f48fa  pop     rdi
0x1800f48fb  pop     rsi
0x1800f48fc  pop     rbp
0x1800f48fd  pop     rbx
0x1800f48fe  retn
```

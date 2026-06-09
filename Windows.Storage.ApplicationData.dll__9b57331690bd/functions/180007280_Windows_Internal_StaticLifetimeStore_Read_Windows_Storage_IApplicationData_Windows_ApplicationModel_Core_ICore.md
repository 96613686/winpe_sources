# Windows::Internal::StaticLifetimeStore::Read<Windows::Storage::IApplicationData>(Windows::ApplicationModel::Core::ICoreApplication *,ushort const *,uchar,Windows::Storage::IApplicationData * *)

- ea: `0x180007280`
- end: `0x180007437`
- name: `??$Read@UIApplicationData@Storage@Windows@@@StaticLifetimeStore@Internal@Windows@@SAJPEAUICoreApplication@Core@ApplicationModel@2@PEBGEPEAPEAUIApplicationData@Storage@2@@Z`
- size: `439`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Core::ICoreApplication *coreApp, const wchar_t *propName, unsigned __int8 pp, Windows::Storage::IApplicationData **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e6c0`

## callees

- `0x180003820`
- `0x180007280`
- `0x180007440`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007366`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000737b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000737b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StaticLifetimeStore::Read<Windows::Storage::IApplicationData>(
        Windows::ApplicationModel::Core::ICoreApplication *coreApp,
        const wchar_t *propName,
        unsigned __int8 pp,
        Windows::Storage::IApplicationData **a4)
{
  int PropertyBagForThread; // eax
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *ptr; // rsi
  int v8; // ebx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *v10; // r14
  HRESULT (__fastcall *get_Context)(Windows::ApplicationModel::Core::ICoreApplicationPrivate *, Windows::Foundation::Collections::IPropertySet **); // rbp
  unsigned __int64 v12; // rbx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *v13; // rcx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *v14; // rcx
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> v16; // [rsp+20h] [rbp-78h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> v17; // [rsp+28h] [rbp-70h] BYREF
  HSTRING string; // [rsp+30h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-60h] BYREF

  *a4 = 0;
  v16.ptr_ = 0;
  PropertyBagForThread = Windows::Internal::StaticLifetimeStore::GetPropertyBagForThread(
                           coreApp,
                           (unsigned __int8)propName,
                           (Windows::Foundation::Collections::IPropertySet **)&v16);
  ptr = v16.ptr_;
  v8 = PropertyBagForThread;
  if ( PropertyBagForThread >= 0 )
  {
    v16.ptr_ = 0;
    QueryInterface = ptr->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
    v8 = QueryInterface(ptr, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, (void **)&v16.ptr_);
    if ( v8 >= 0 )
    {
      v17.ptr_ = 0;
      v10 = v16.ptr_;
      get_Context = v16.ptr_->get_Context;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
      v12 = -1;
      do
        ++v12;
      while ( propName[v12] );
      if ( v12 > 0xFFFFFFFF )
      {
        LODWORD(v12) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(propName, v12, &hstringHeader, &string);
      v8 = ((__int64 (__fastcall *)(Windows::ApplicationModel::Core::ICoreApplicationPrivate *, HSTRING, Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *))get_Context)(
             v10,
             string,
             &v17);
      if ( v8 >= 0 )
        v8 = v17.ptr_->QueryInterface(v17.ptr_, &GUID_c3da6fb7_b744_4b45_b0b8_223a0938d0dc, (void **)a4);
      v13 = v17.ptr_;
      if ( v17.ptr_ )
      {
        v17.ptr_ = 0;
        v13->Release(v13);
      }
    }
    v14 = v16.ptr_;
    if ( v16.ptr_ )
    {
      v16.ptr_ = 0;
      v14->Release(v14);
    }
  }
  if ( ptr )
    ptr->Release(ptr);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007280  push    rbx
0x180007282  push    rsi
0x180007283  sub     rsp, 88h
0x18000728a  mov     rax, cs:__security_cookie
0x180007291  xor     rax, rsp
0x180007294  mov     [rsp+98h+var_48], rax
0x180007299  mov     [rsp+98h+var_20], rdi
0x18000729e  lea     r8, [rsp+98h+var_78]; coreApp
0x1800072a3  mov     [rsp+98h+var_28], r12
0x1800072a8  mov     rdi, propName
0x1800072ab  xor     r12d, r12d
0x1800072ae  mov     [rsp+98h+var_38], r15
0x1800072b3  mov     [pp], r12
0x1800072b6  mov     r15, pp
0x1800072b9  mov     [rsp+98h+var_78.ptr_], r12
0x1800072be  call    ?GetPropertyBagForThread@StaticLifetimeStore@Internal@Windows@@CAJPEAUICoreApplication@Core@ApplicationModel@3@EPEAPEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::StaticLifetimeStore::GetPropertyBagForThread(Windows::ApplicationModel::Core::ICoreApplication *,uchar,Windows::Foundation::Collections::IPropertySet * *)
0x1800072c3  mov     rsi, [rsp+98h+var_78.ptr_]
0x1800072c8  mov     ebx, eax
0x1800072ca  test    eax, eax
0x1800072cc  js      loc_1800073FB
0x1800072d2  mov     [rsp+98h+var_78.ptr_], r12
0x1800072d7  lea     coreApp, [rsp+98h+var_78]; this
0x1800072dc  mov     rax, [rsi]
0x1800072df  mov     rbx, [rax]
0x1800072e2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800072e7  lea     r8, [rsp+98h+var_78]
0x1800072ec  mov     coreApp, rsi
0x1800072ef  lea     propName, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800072f6  mov     rax, rbx
0x1800072f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072fe  mov     ebx, eax
0x180007300  test    eax, eax
0x180007302  js      loc_1800073E0
0x180007308  mov     [rsp+98h+var_18], rbp
0x180007310  lea     coreApp, [rsp+98h+var_70]; this
0x180007315  mov     [rsp+98h+var_70.ptr_], r12
0x18000731a  mov     [rsp+98h+var_30], r14
0x18000731f  mov     r14, [rsp+98h+var_78.ptr_]
0x180007324  mov     rax, [r14]
0x180007327  mov     rbp, [rax+30h]
0x18000732b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180007330  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007337  nop     word ptr [rax+rax+00000000h]
0x180007340  inc     rbx
0x180007343  cmp     [rdi+rbx*2], r12w
0x180007348  jnz     short loc_180007340
0x18000734a  mov     eax, 0FFFFFFFFh
0x18000734f  cmp     rbx, rax
0x180007352  jbe     short loc_18000736C
0x180007354  xor     r9d, r9d; lpArguments
0x180007357  xor     r8d, r8d; nNumberOfArguments
0x18000735a  mov     edx, 1; dwExceptionFlags
0x18000735f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180007364  mov     ebx, eax
0x180007366  call    cs:__imp_RaiseException
0x18000736c  lea     pp, [rsp+98h+string]; string
0x180007371  mov     edx, ebx; length
0x180007373  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180007378  mov     coreApp, rdi; sourceString
0x18000737b  call    cs:__imp_WindowsCreateStringReference
0x180007381  mov     propName, [rsp+98h+string]
0x180007386  lea     r8, [rsp+98h+var_70]
0x18000738b  mov     coreApp, r14
0x18000738e  mov     rax, rbp
0x180007391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007396  mov     r14, [rsp+98h+var_30]
0x18000739b  mov     ebx, eax
0x18000739d  mov     rbp, [rsp+98h+var_18]
0x1800073a5  test    eax, eax
0x1800073a7  js      short loc_1800073C5
0x1800073a9  mov     coreApp, [rsp+98h+var_70.ptr_]
0x1800073ae  lea     propName, _GUID_c3da6fb7_b744_4b45_b0b8_223a0938d0dc
0x1800073b5  mov     r8, r15
0x1800073b8  mov     rax, [coreApp]
0x1800073bb  mov     rax, [rax]
0x1800073be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c3  mov     ebx, eax
0x1800073c5  mov     coreApp, [rsp+98h+var_70.ptr_]
0x1800073ca  test    coreApp, coreApp
0x1800073cd  jz      short loc_1800073E0
0x1800073cf  mov     [rsp+98h+var_70.ptr_], r12
0x1800073d4  mov     rax, [coreApp]
0x1800073d7  mov     rax, [rax+10h]
0x1800073db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e0  mov     coreApp, [rsp+98h+var_78.ptr_]
0x1800073e5  test    coreApp, coreApp
0x1800073e8  jz      short loc_1800073FB
0x1800073ea  mov     [rsp+98h+var_78.ptr_], r12
0x1800073ef  mov     rax, [coreApp]
0x1800073f2  mov     rax, [rax+10h]
0x1800073f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fb  mov     r15, [rsp+98h+var_38]
0x180007400  mov     r12, [rsp+98h+var_28]
0x180007405  mov     rdi, [rsp+98h+var_20]
0x18000740a  test    rsi, rsi
0x18000740d  jz      short loc_18000741E
0x18000740f  mov     rax, [rsi]
0x180007412  mov     coreApp, rsi
0x180007415  mov     rax, [rax+10h]
0x180007419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741e  mov     eax, ebx
0x180007420  mov     coreApp, [rsp+98h+var_48]
0x180007425  xor     coreApp, rsp; StackCookie
0x180007428  call    __security_check_cookie
0x18000742d  add     rsp, 88h
0x180007434  pop     rsi
0x180007435  pop     rbx
0x180007436  retn
```

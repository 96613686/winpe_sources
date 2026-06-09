# CDevice::ShaderCacheControl(D3D12_SHADER_CACHE_KIND_FLAGS,D3D12_SHADER_CACHE_CONTROL_FLAGS)

- ea: `0x1800b6ac0`
- end: `0x1800b6cfd`
- name: `?ShaderCacheControl@CDevice@@UEAAJW4D3D12_SHADER_CACHE_KIND_FLAGS@@W4D3D12_SHADER_CACHE_CONTROL_FLAGS@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(CDevice *__hidden this, enum D3D12_SHADER_CACHE_KIND_FLAGS, enum D3D12_SHADER_CACHE_CONTROL_FLAGS)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003c84`
- `0x18000b010`
- `0x180029b30`
- `0x18004b9a0`
- `0x1800b6ac0`
- `0x1800b9818`
- `0x1800cca18`
- `0x18010033c`
- `0x180143080`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b6c12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b6c12`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800b6bfd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800b6bfd`

## string_xrefs

- `0x1800b6c08`: `DllGetClassObject`
- `0x1800b6bf6`: `D3DSCache.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDevice::ShaderCacheControl(CDevice *this, enum D3D12_SHADER_CACHE_KIND_FLAGS a2, unsigned int a3)
{
  __int64 result; // rax
  CD3D12ShaderCacheSession *v7; // rcx
  CD3D12ShaderCacheSession *v8; // rcx
  __int64 i; // rsi
  FARPROC ProcAddress; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  _Smtx_t *LibraryA; // [rsp+30h] [rbp-78h] BYREF
  char v15; // [rsp+38h] [rbp-70h]
  _com_error *v16; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v17[9]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+20h] BYREF

  LODWORD(v18) = 0;
  v17[0] = off_180272F38;
  v17[1] = this;
  v17[7] = v17;
  result = ValidateShaderCacheControl((unsigned int)&v18, a3, a2, *((_DWORD *)this + 2032), (__int64)v17);
  if ( (int)result >= 0 )
  {
    if ( (a3 & 1) != 0 )
    {
      *((_DWORD *)this + 2032) |= a2;
    }
    else if ( (a3 & 2) != 0 )
    {
      *((_DWORD *)this + 2032) &= ~a2;
    }
    if ( (a3 & 4) != 0 )
    {
      try
      {
        if ( (a2 & 1) != 0 )
        {
          v7 = (CD3D12ShaderCacheSession *)*((_QWORD *)this + 93);
          if ( v7 )
            CD3D12ShaderCacheSession::Clear(v7);
        }
        if ( (a2 & 2) != 0 )
        {
          v8 = (CD3D12ShaderCacheSession *)*((_QWORD *)this + 94);
          if ( v8 )
            CD3D12ShaderCacheSession::Clear(v8);
        }
        if ( (a2 & 8) != 0 )
        {
          std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&LibraryA, (char *)this + 4808);
          for ( i = *((_QWORD *)this + 603); (CDevice *)i != (CDevice *)((char *)this + 4816); i = *(_QWORD *)(i + 8) )
          {
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(i - 32) + 88LL))(*(_QWORD *)(i - 32)) == 31
              && (a2 & *(_DWORD *)(i + 288)) != 0 )
            {
              CD3D12ShaderCacheSession::Clear((CD3D12ShaderCacheSession *)(i - 176));
            }
          }
          if ( v15 )
            Smtx_unlock_shared(LibraryA);
          v19 = 0;
          LibraryA = (_Smtx_t *)LoadLibraryA("D3DSCache.dll");
          ProcAddress = GetProcAddress((HMODULE)LibraryA, "DllGetClassObject");
          v11 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
                  &CLSID_ShaderCacheDiskCleanupHandler,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  &v19);
          ThrowFailure(v11);
          v18 = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v19 + 24LL))(
                  v19,
                  0,
                  &GUID_df73233a_33a4_4814_b4af_d2a4f07a29e6,
                  &v18);
          ThrowFailure(v12);
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
          ThrowFailure(v13);
          ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v18);
          D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&LibraryA, 0);
          ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v19);
        }
      }
      catch ( _com_error *v16 )
      {
        LODWORD(v18) = *((_DWORD *)v16 + 2);
        return (unsigned int)v18;
      }
    }
    if ( (a2 & 4) != 0 && *((_DWORD *)this + 114) )
      TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,129,void>,void,void,D3D10DDI_HDEVICE,enum D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080>::Call<CDevice>(
        this,
        (char *)this + 8288,
        a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b6ac0  mov     r11, rsp
0x1800b6ac3  mov     [r11+10h], rbx
0x1800b6ac7  mov     [r11+18h], rsi
0x1800b6acb  push    rdi
0x1800b6acc  push    r14
0x1800b6ace  push    r15
0x1800b6ad0  sub     rsp, 90h
0x1800b6ad7  mov     r14d, r8d
0x1800b6ada  mov     edi, edx
0x1800b6adc  mov     rbx, rcx
0x1800b6adf  mov     dword ptr [r11+8], 0
0x1800b6ae7  lea     rax, off_180272F38
0x1800b6aee  mov     [r11-60h], rax
0x1800b6af2  mov     [r11-58h], rcx
0x1800b6af6  lea     rax, [r11-60h]
0x1800b6afa  mov     [r11-28h], rax
0x1800b6afe  lea     rax, [r11-60h]
0x1800b6b02  mov     [rsp+0A8h+var_88], rax
0x1800b6b07  mov     r9d, [rcx+1FC0h]
0x1800b6b0e  mov     r8d, edx
0x1800b6b11  mov     edx, r14d
0x1800b6b14  lea     rcx, [r11+8]
0x1800b6b18  call    ?ValidateShaderCacheControl@@YAJAEAUTDebugOutputFunctor@@W4D3D12_SHADER_CACHE_CONTROL_FLAGS@@W4D3D12_SHADER_CACHE_KIND_FLAGS@@2V?$function@$$A6A_NXZ@std@@@Z; ValidateShaderCacheControl(TDebugOutputFunctor &,D3D12_SHADER_CACHE_CONTROL_FLAGS,D3D12_SHADER_CACHE_KIND_FLAGS,D3D12_SHADER_CACHE_KIND_FLAGS,std::function<bool (void)>)
0x1800b6b1d  test    eax, eax
0x1800b6b1f  js      loc_1800B6CE4
0x1800b6b25  test    r14b, 1
0x1800b6b29  jz      short loc_1800B6B33
0x1800b6b2b  or      [rbx+1FC0h], edi
0x1800b6b31  jmp     short loc_1800B6B43
0x1800b6b33  test    r14b, 2
0x1800b6b37  jz      short loc_1800B6B43
0x1800b6b39  mov     eax, edi
0x1800b6b3b  not     eax
0x1800b6b3d  and     [rbx+1FC0h], eax
0x1800b6b43  test    r14b, 4
0x1800b6b47  jz      loc_1800B6CC1
0x1800b6b4d  test    dil, 1
0x1800b6b51  jz      short loc_1800B6B64
0x1800b6b53  mov     rcx, [rbx+2E8h]; this
0x1800b6b5a  test    rcx, rcx
0x1800b6b5d  jz      short loc_1800B6B64
0x1800b6b5f  call    ?Clear@CD3D12ShaderCacheSession@@QEAAXXZ; CD3D12ShaderCacheSession::Clear(void)
0x1800b6b64  test    dil, 2
0x1800b6b68  jz      short loc_1800B6B7B
0x1800b6b6a  mov     rcx, [rbx+2F0h]; this
0x1800b6b71  test    rcx, rcx
0x1800b6b74  jz      short loc_1800B6B7B
0x1800b6b76  call    ?Clear@CD3D12ShaderCacheSession@@QEAAXXZ; CD3D12ShaderCacheSession::Clear(void)
0x1800b6b7b  test    dil, 8
0x1800b6b7f  jz      loc_1800B6CB6
0x1800b6b85  lea     rdx, [rbx+12C8h]
0x1800b6b8c  lea     rcx, [rsp+0A8h+var_78]
0x1800b6b91  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800b6b96  nop
0x1800b6b97  mov     rsi, [rbx+12D8h]
0x1800b6b9e  lea     rax, [rbx+12D0h]
0x1800b6ba5  cmp     rsi, rax
0x1800b6ba8  jz      short loc_1800B6BD9
0x1800b6baa  mov     rcx, [rsi-20h]
0x1800b6bae  mov     rax, [rcx]
0x1800b6bb1  mov     rax, [rax+58h]
0x1800b6bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6bba  cmp     eax, 1Fh
0x1800b6bbd  jnz     short loc_1800B6BD3
0x1800b6bbf  test    [rsi+120h], edi
0x1800b6bc5  jz      short loc_1800B6BD3
0x1800b6bc7  lea     rcx, [rsi-0B0h]; this
0x1800b6bce  call    ?Clear@CD3D12ShaderCacheSession@@QEAAXXZ; CD3D12ShaderCacheSession::Clear(void)
0x1800b6bd3  mov     rsi, [rsi+8]
0x1800b6bd7  jmp     short loc_1800B6B9E
0x1800b6bd9  cmp     [rsp+0A8h+var_70], 0
0x1800b6bde  jz      short loc_1800B6BEA
0x1800b6be0  mov     rcx, [rsp+0A8h+var_78]; _Smtx_t *
0x1800b6be5  call    _Smtx_unlock_shared
0x1800b6bea  mov     [rsp+0A8h+arg_18], 0
0x1800b6bf6  lea     rcx, aD3dscacheDll; "D3DSCache.dll"
0x1800b6bfd  call    cs:__imp_LoadLibraryA
0x1800b6c03  mov     [rsp+0A8h+var_78], rax
0x1800b6c08  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1800b6c0f  mov     rcx, rax; hModule
0x1800b6c12  call    cs:__imp_GetProcAddress
0x1800b6c18  lea     r8, [rsp+0A8h+arg_18]
0x1800b6c20  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x1800b6c27  lea     rcx, CLSID_ShaderCacheDiskCleanupHandler
0x1800b6c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c33  mov     ecx, eax; int
0x1800b6c35  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b6c3a  mov     [rsp+0A8h+arg_0], 0
0x1800b6c46  mov     rcx, [rsp+0A8h+arg_18]
0x1800b6c4e  mov     rax, [rcx]
0x1800b6c51  lea     r9, [rsp+0A8h+arg_0]
0x1800b6c59  lea     r8, _GUID_df73233a_33a4_4814_b4af_d2a4f07a29e6
0x1800b6c60  xor     edx, edx
0x1800b6c62  mov     rax, [rax+18h]
0x1800b6c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c6b  mov     ecx, eax; int
0x1800b6c6d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b6c72  mov     rcx, [rsp+0A8h+arg_0]
0x1800b6c7a  mov     rax, [rcx]
0x1800b6c7d  mov     rax, [rax+18h]
0x1800b6c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c86  mov     ecx, eax; int
0x1800b6c88  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b6c8d  nop
0x1800b6c8e  lea     rcx, [rsp+0A8h+arg_0]
0x1800b6c96  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800b6c9b  nop
0x1800b6c9c  xor     edx, edx; HINSTANCE
0x1800b6c9e  lea     rcx, [rsp+0A8h+var_78]; this
0x1800b6ca3  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x1800b6ca8  nop
0x1800b6ca9  lea     rcx, [rsp+0A8h+arg_18]
0x1800b6cb1  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800b6cb6  jmp     short loc_1800B6CC1
0x1800b6cb8  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800b6cbf  jmp     short loc_1800B6CE4
0x1800b6cc1  test    dil, 4
0x1800b6cc5  jz      short loc_1800B6CE2
0x1800b6cc7  cmp     dword ptr [rbx+1C8h], 0
0x1800b6cce  jz      short loc_1800B6CE2
0x1800b6cd0  lea     rdx, [rbx+2060h]
0x1800b6cd7  mov     r8d, r14d
0x1800b6cda  mov     rcx, rbx
0x1800b6cdd  call    ??$Call@VCDevice@@@?$InvokerImpl@U?$FunctionTraits@$0FD@$0IB@X@?$TableFunctionTraitsImpl@$0A@@@XXUD3D10DDI_HDEVICE@@W4D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080@@@Detail@?$TableFunctionTraits@$0A@@@SAXPEAVCDevice@@UD3D10DDI_HDEVICE@@W4D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080@@@Z; TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,129,void>,void,void,D3D10DDI_HDEVICE,D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080>::Call<CDevice>(CDevice *,D3D10DDI_HDEVICE,D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080)
0x1800b6ce2  xor     eax, eax
0x1800b6ce4  lea     r11, [rsp+0A8h+var_18]
0x1800b6cec  mov     rbx, [r11+28h]
0x1800b6cf0  mov     rsi, [r11+30h]
0x1800b6cf4  mov     rsp, r11
0x1800b6cf7  pop     r15
0x1800b6cf9  pop     r14
0x1800b6cfb  pop     rdi
0x1800b6cfc  retn
```

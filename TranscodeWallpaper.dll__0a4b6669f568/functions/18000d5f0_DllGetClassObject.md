# DllGetClassObject

- ea: `0x18000d5f0`
- end: `0x18000d7e6`
- name: `DllGetClassObject`
- size: `502`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002170`
- `0x1800025c4`
- `0x180002d50`
- `0x180006d6c`
- `0x180006dec`
- `0x18000d230`
- `0x18000d5f0`
- `0x18000dd54`
- `0x18000f010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000d63f`
- `RPCRT4!NdrDllGetClassObject` at `0x18000d63f`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  int v7; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  unsigned __int8 v10; // cl
  unsigned __int8 v11; // dl
  unsigned __int8 v12; // r9
  unsigned __int8 v13; // r10
  unsigned __int8 v14; // r11
  unsigned __int8 v15; // bl
  unsigned __int8 v16; // di
  unsigned __int8 v17; // si
  HRESULT v18; // ebx
  HRESULT v19; // ebx
  _QWORD *v20; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-60h] BYREF
  __int128 v22; // [rsp+40h] [rbp-58h]
  BSTR bstrString; // [rsp+50h] [rbp-48h] BYREF
  int v24; // [rsp+58h] [rbp-40h]
  int v25; // [rsp+5Ch] [rbp-3Ch]
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF

  *ppv = 0;
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
  {
    *ppv = 0;
    v7 = memcmp_0(rclsid, &GUID_b00fefaa_4467_4f52_8956_90a5f800f252, 0x10u);
    try
    {
      if ( v7 )
      {
        v21 = 0;
        v22 = 0;
        bstrString = 0;
        v24 = -1430532899;
        v25 = -2147221231;
        v26 = 0;
        winrt::hresult_error::originate((__int64)&bstrString, 0x80040111, 0, &v21);
        v19 = *winrt::hresult_error::to_abi((__int64)&bstrString, &v20);
        if ( v26 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
        if ( bstrString )
          WINRT_IMPL_SysFreeString(bstrString);
        result = v19;
      }
      else
      {
        v8 = operator new(0x18u);
        *v8 = 0;
        v8[1] = 0;
        v9 = v8 + 2;
        v8[2] = &winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v8[1] = 1;
        *v8 = &winrt::impl::heap_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper>::`vftable';
        v20 = v8 + 2;
        v10 = riid->Data4[0];
        v11 = riid->Data4[1];
        v12 = riid->Data4[2];
        v13 = riid->Data4[3];
        v14 = riid->Data4[4];
        v15 = riid->Data4[5];
        v16 = riid->Data4[6];
        v17 = riid->Data4[7];
        bstrString = *(BSTR *)&riid->Data1;
        LOBYTE(v24) = v10;
        BYTE1(v24) = v11;
        BYTE2(v24) = v12;
        HIBYTE(v24) = v13;
        LOBYTE(v25) = v14;
        BYTE1(v25) = v15;
        BYTE2(v25) = v16;
        HIBYTE(v25) = v17;
        v18 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *, LPVOID *))v8[2])(v8 + 2, &bstrString, ppv);
        if ( v9 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v20);
        result = v18;
      }
    }
    catch ( ... )
    {
      return *winrt::to_hresult(&v20);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d5f0  mov     [rsp+arg_18], rbx
0x18000d5f5  push    rsi
0x18000d5f6  push    rdi
0x18000d5f7  push    r12
0x18000d5f9  push    r14
0x18000d5fb  push    r15
0x18000d5fd  sub     rsp, 70h
0x18000d601  mov     rax, cs:__security_cookie
0x18000d608  xor     rax, rsp
0x18000d60b  mov     [rsp+98h+var_30], rax
0x18000d610  mov     r12, r8
0x18000d613  mov     r15, rdx
0x18000d616  mov     rbx, rcx
0x18000d619  mov     qword ptr [r8], 0
0x18000d620  lea     rax, gPFactory
0x18000d627  mov     [rsp+98h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000d62c  lea     rax, CLSID_PSFactoryBuffer
0x18000d633  mov     [rsp+98h+pclsid], rax; pclsid
0x18000d638  lea     r9, aProxyFileList; pProxyFileList
0x18000d63f  call    cs:__imp_NdrDllGetClassObject
0x18000d645  test    eax, eax
0x18000d647  jns     loc_18000D7C3
0x18000d64d  mov     qword ptr [r12], 0
0x18000d655  mov     r8d, 10h; Size
0x18000d65b  lea     rdx, _GUID_b00fefaa_4467_4f52_8956_90a5f800f252; Buf2
0x18000d662  mov     rcx, rbx; Buf1
0x18000d665  call    memcmp_0
0x18000d66a  test    eax, eax
0x18000d66c  jnz     loc_18000D743
0x18000d672  lea     ecx, [rax+18h]; Size
0x18000d675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d67a  mov     qword ptr [rax], 0
0x18000d681  mov     qword ptr [rax+8], 0
0x18000d689  lea     r14, [rax+10h]
0x18000d68d  lea     rcx, ??_7?$produce@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@UITranscodeWallpaperStatics@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper,winrt::Windows::Internal::Themes::ITranscodeWallpaperStatics>::`vftable'
0x18000d694  mov     [r14], rcx
0x18000d697  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d69e  mov     qword ptr [rax+8], 1
0x18000d6a6  lea     rcx, ??_7?$heap_implements@UTranscodeWallpaper@implementation@Themes@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Themes::implementation::TranscodeWallpaper>::`vftable'
0x18000d6ad  mov     [rax], rcx
0x18000d6b0  mov     [rsp+98h+var_68], r14
0x18000d6b5  mov     cl, [r15+8]
0x18000d6b9  mov     dl, [r15+9]
0x18000d6bd  mov     r9b, [r15+0Ah]
0x18000d6c1  mov     r10b, [r15+0Bh]
0x18000d6c5  mov     r11b, [r15+0Ch]
0x18000d6c9  mov     bl, [r15+0Dh]
0x18000d6cd  mov     dil, [r15+0Eh]
0x18000d6d1  mov     sil, [r15+0Fh]
0x18000d6d5  mov     eax, [r15]
0x18000d6d8  mov     dword ptr [rsp+98h+bstrString], eax
0x18000d6dc  movzx   eax, word ptr [r15+4]
0x18000d6e1  mov     word ptr [rsp+98h+bstrString+4], ax
0x18000d6e6  movzx   eax, word ptr [r15+6]
0x18000d6eb  mov     word ptr [rsp+98h+bstrString+6], ax
0x18000d6f0  mov     byte ptr [rsp+98h+var_40], cl
0x18000d6f4  mov     byte ptr [rsp+98h+var_40+1], dl
0x18000d6f8  mov     byte ptr [rsp+98h+var_40+2], r9b
0x18000d6fd  mov     byte ptr [rsp+98h+var_40+3], r10b
0x18000d702  mov     byte ptr [rsp+98h+var_3C], r11b
0x18000d707  mov     byte ptr [rsp+98h+var_3C+1], bl
0x18000d70b  mov     byte ptr [rsp+98h+var_3C+2], dil
0x18000d710  mov     byte ptr [rsp+98h+var_3C+3], sil
0x18000d715  mov     rax, [r14]
0x18000d718  mov     r8, r12
0x18000d71b  lea     rdx, [rsp+98h+bstrString]
0x18000d720  mov     rcx, r14
0x18000d723  mov     rax, [rax]
0x18000d726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72b  mov     ebx, eax
0x18000d72d  test    r14, r14
0x18000d730  jz      short loc_18000D73C
0x18000d732  lea     rcx, [rsp+98h+var_68]
0x18000d737  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d73c  mov     eax, ebx
0x18000d73e  jmp     loc_18000D7C3
0x18000d743  mov     [rsp+98h+var_60], 0
0x18000d74b  xorps   xmm0, xmm0
0x18000d74e  movdqu  [rsp+98h+var_58], xmm0
0x18000d754  mov     edx, 80040111h
0x18000d759  mov     [rsp+98h+bstrString], 0
0x18000d762  mov     [rsp+98h+var_40], 0AABBCCDDh
0x18000d76a  mov     [rsp+98h+var_3C], edx
0x18000d76e  mov     [rsp+98h+var_38], 0
0x18000d777  lea     r9, [rsp+98h+var_60]
0x18000d77c  xor     r8d, r8d
0x18000d77f  lea     rcx, [rsp+98h+bstrString]
0x18000d784  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000d789  lea     rdx, [rsp+98h+var_68]
0x18000d78e  lea     rcx, [rsp+98h+bstrString]
0x18000d793  call    ?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ; winrt::hresult_error::to_abi(void)
0x18000d798  mov     ebx, [rax]
0x18000d79a  cmp     [rsp+98h+var_38], 0
0x18000d7a0  jz      short loc_18000D7AC
0x18000d7a2  lea     rcx, [rsp+98h+var_38]
0x18000d7a7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d7ac  mov     rcx, [rsp+98h+bstrString]; bstrString
0x18000d7b1  test    rcx, rcx
0x18000d7b4  jz      short loc_18000D7BB
0x18000d7b6  call    WINRT_IMPL_SysFreeString
0x18000d7bb  mov     eax, ebx
0x18000d7bd  jmp     short loc_18000D7C3
0x18000d7bf  mov     eax, dword ptr [rsp+98h+var_68]
0x18000d7c3  mov     rcx, [rsp+98h+var_30]
0x18000d7c8  xor     rcx, rsp; StackCookie
0x18000d7cb  call    __security_check_cookie
0x18000d7d0  mov     rbx, [rsp+98h+arg_18]
0x18000d7d8  add     rsp, 70h
0x18000d7dc  pop     r15
0x18000d7de  pop     r14
0x18000d7e0  pop     r12
0x18000d7e2  pop     rdi
0x18000d7e3  pop     rsi
0x18000d7e4  retn
```

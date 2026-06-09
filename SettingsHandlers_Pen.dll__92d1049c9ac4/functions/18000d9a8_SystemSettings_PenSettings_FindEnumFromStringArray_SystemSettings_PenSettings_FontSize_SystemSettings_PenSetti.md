# SystemSettings::PenSettings::FindEnumFromStringArray<SystemSettings::PenSettings::FontSize,SystemSettings::PenSettings::HandwritingFontSizeResourceMapping_>(HSTRING__ *,SystemSettings::PenSettings::HandwritingFontSizeResourceMapping_ const *,uint)

- ea: `0x18000d9a8`
- end: `0x18000daba`
- name: `??$FindEnumFromStringArray@W4FontSize@PenSettings@SystemSettings@@UHandwritingFontSizeResourceMapping_@23@@PenSettings@SystemSettings@@YA?AW4FontSize@01@PEAUHSTRING__@@PEBUHandwritingFontSizeResourceMapping_@01@I@Z`
- size: `274`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ff0`

## callees

- `0x180008128`
- `0x18000d9a8`
- `0x180012868`
- `0x1800168b4`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da85`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::PenSettings::FindEnumFromStringArray<enum SystemSettings::PenSettings::FontSize,SystemSettings::PenSettings::HandwritingFontSizeResourceMapping_>(
        SystemSettings::DataModel *this,
        HSTRING a2)
{
  unsigned int i; // esi
  struct IInspectable *v4; // rdi
  ULONG (__stdcall *AddRef)(IInspectable *); // rbx
  WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF
  struct IInspectable *v11; // [rsp+68h] [rbp+48h] BYREF

  string = a2;
  for ( i = 0; i < 3; ++i )
  {
    v11 = 0;
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
    if ( SystemSettings::DataModel::PropValueHelper::CreateString(
           (const unsigned __int16 *)qword_18007B990[2 * i + 1],
           &v11) >= 0 )
    {
      v4 = v11;
      AddRef = v11->lpVtbl[3].AddRef;
      WindowsDeleteString(string);
      string = 0;
      if ( ((int (__fastcall *)(struct IInspectable *, HSTRING *))AddRef)(v4, &string) >= 0 )
      {
        StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
        if ( SystemSettings::DataModel::IsHstringEqual(this, (HSTRING)StringRawBuffer, v7) )
        {
          v8 = qword_18007B990[2 * i];
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
          return v8;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000d9a8  mov     [rsp-28h+arg_0], rbx
0x18000d9ad  mov     [rsp-28h+arg_10], rsi
0x18000d9b2  mov     [rsp-28h+string], rdx
0x18000d9b7  push    rbp
0x18000d9b8  push    rdi
0x18000d9b9  push    r13
0x18000d9bb  push    r14
0x18000d9bd  push    r15
0x18000d9bf  mov     rbp, rsp
0x18000d9c2  sub     rsp, 20h
0x18000d9c6  mov     r15, rcx
0x18000d9c9  xor     esi, esi
0x18000d9cb  lea     r13, qword_18007B990
0x18000d9d2  cmp     esi, 3
0x18000d9d5  jnb     loc_18000DAA0
0x18000d9db  mov     [rbp+arg_18], 0
0x18000d9e3  mov     [rbp+string], 0
0x18000d9eb  lea     rcx, [rbp+arg_18]
0x18000d9ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d9f4  mov     r14d, esi
0x18000d9f7  add     r14, r14
0x18000d9fa  lea     rdx, [rbp+arg_18]; struct IInspectable **
0x18000d9fe  mov     rcx, [r13+r14*8+8]; unsigned __int16 *
0x18000da03  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18000da08  test    eax, eax
0x18000da0a  js      short loc_18000DA5A
0x18000da0c  mov     rdi, [rbp+arg_18]
0x18000da10  mov     rax, [rdi]
0x18000da13  mov     rbx, [rax+98h]
0x18000da1a  mov     rcx, [rbp+string]; string
0x18000da1e  call    cs:__imp_WindowsDeleteString
0x18000da24  mov     [rbp+string], 0
0x18000da2c  lea     rdx, [rbp+string]
0x18000da30  mov     rcx, rdi
0x18000da33  mov     rax, rbx
0x18000da36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da3b  test    eax, eax
0x18000da3d  js      short loc_18000DA5A
0x18000da3f  xor     edx, edx; length
0x18000da41  mov     rcx, [rbp+string]; string
0x18000da45  call    cs:__imp_WindowsGetStringRawBuffer
0x18000da4b  mov     rdx, rax; HSTRING
0x18000da4e  mov     rcx, r15; this
0x18000da51  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18000da56  test    al, al
0x18000da58  jnz     short loc_18000DA7C
0x18000da5a  mov     rcx, [rbp+string]; string
0x18000da5e  call    cs:__imp_WindowsDeleteString
0x18000da64  mov     [rbp+string], 0
0x18000da6c  lea     rcx, [rbp+arg_18]
0x18000da70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000da75  inc     esi
0x18000da77  jmp     loc_18000D9D2
0x18000da7c  mov     ebx, [r13+r14*8+0]
0x18000da81  mov     rcx, [rbp+string]; string
0x18000da85  call    cs:__imp_WindowsDeleteString
0x18000da8b  mov     [rbp+string], 0
0x18000da93  lea     rcx, [rbp+arg_18]
0x18000da97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000da9c  mov     eax, ebx
0x18000da9e  jmp     short loc_18000DAA3
0x18000daa0  or      eax, 0FFFFFFFFh
0x18000daa3  mov     rbx, [rsp+20h+arg_0]
0x18000daa8  mov     rsi, [rsp+20h+arg_10]
0x18000daad  add     rsp, 20h
0x18000dab1  pop     r15
0x18000dab3  pop     r14
0x18000dab5  pop     r13
0x18000dab7  pop     rdi
0x18000dab8  pop     rbp
0x18000dab9  retn
```

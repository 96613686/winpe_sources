# winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::BytesPerPixel(uint *)

- ea: `0x180006630`
- end: `0x18000669a`
- name: `?BytesPerPixel@?$produce@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@UIImageBufferResource@3456@@impl@winrt@@UEAAHPEAI@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800012e0`
- `0x180001b40`
- `0x180006630`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResource>::BytesPerPixel(
        __int64 a1,
        int *a2)
{
  __int64 v2; // r8
  int v3; // eax
  __int64 *v5; // rdx
  __int64 v6; // [rsp+0h] [rbp-28h] BYREF
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1 + 16;
  if ( !a1 )
    v2 = 32;
  if ( *(_DWORD *)v2 == 1 )
  {
    v3 = 3;
  }
  else if ( *(_DWORD *)v2 == 2 || *(_DWORD *)v2 == 3 || *(_DWORD *)v2 == 4 )
  {
    v3 = 4;
  }
  else
  {
    if ( *(_DWORD *)v2 != 5 )
    {
      winrt::hresult::hresult((winrt::hresult *)&v7, 87);
      try
      {
        winrt::throw_hresult();
      }
      catch ( ... )
      {
        v5 = &v6;
        *((_DWORD *)v5 + 12) = *(_DWORD *)winrt::to_hresult(v5 + 6);
        return v7;
      }
    }
    v3 = 1;
  }
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x180006630  sub     rsp, 28h
0x180006634  lea     r8, [rcx+10h]
0x180006638  mov     eax, 20h ; ' '
0x18000663d  test    rcx, rcx
0x180006640  cmovz   r8, rax
0x180006644  mov     ecx, [r8]
0x180006647  sub     ecx, 1
0x18000664a  jz      short loc_18000666E
0x18000664c  sub     ecx, 1
0x18000664f  jz      short loc_180006667
0x180006651  sub     ecx, 1
0x180006654  jz      short loc_180006667
0x180006656  sub     ecx, 1
0x180006659  jz      short loc_180006667
0x18000665b  cmp     ecx, 1
0x18000665e  jnz     short loc_180006682
0x180006660  mov     eax, 1
0x180006665  jmp     short loc_180006673
0x180006667  mov     eax, 4
0x18000666c  jmp     short loc_180006673
0x18000666e  mov     eax, 3
0x180006673  mov     [rdx], eax
0x180006675  xor     eax, eax
0x180006677  jmp     short loc_18000667D
0x180006679  mov     eax, [rsp+28h+arg_0]
0x18000667d  add     rsp, 28h
0x180006681  retn
0x180006682  mov     edx, 57h ; 'W'; int
0x180006687  lea     rcx, [rsp+28h+arg_0]; this
0x18000668c  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180006691  mov     ecx, [rax]
0x180006693  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

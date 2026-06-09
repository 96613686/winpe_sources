# winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity(void)

- ea: `0x180005d90`
- end: `0x180005e4b`
- name: `?Capacity@ImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@QEAAIXZ`
- size: `187`
- prototype: `unsigned __int64 __fastcall(winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005e50`
- `0x180006600`

## callees

- `0x1800012e0`
- `0x180001450`
- `0x180001500`
- `0x180001b40`
- `0x180005d90`
- `0x180008e5c`

## pseudocode

```c
unsigned __int64 __fastcall winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource::Capacity(
        winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource *this)
{
  __int64 v1; // rdx
  unsigned __int64 v2; // rax
  unsigned __int64 result; // rax
  winrt::hresult *v4; // rax
  winrt::hresult *v5; // rax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v7[48]; // [rsp+38h] [rbp-30h] BYREF
  char v8; // [rsp+70h] [rbp+8h] BYREF

  switch ( *((_DWORD *)this + 8) )
  {
    case 1:
      v1 = 3;
      break;
    case 2:
    case 3:
    case 4:
      v1 = 4;
      break;
    case 5:
      v1 = 1;
      break;
    default:
      v5 = winrt::hresult::hresult((winrt::hresult *)&v8, 87);
      winrt::throw_hresult(*(unsigned int *)v5);
  }
  v2 = v1 * *((unsigned int *)this + 6);
  if ( v2 > 0xFFFFFFFF
    || (result = (unsigned int)v2 * (unsigned __int64)*((unsigned int *)this + 7), result > 0xFFFFFFFF) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v7, L"Image size too large");
    v4 = winrt::hresult::hresult((winrt::hresult *)&v8, -2147024809);
    winrt::hresult_error::hresult_error(pExceptionObject, *(unsigned int *)v4, v7);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180005d90  sub     rsp, 68h
0x180005d94  mov     edx, [rcx+20h]
0x180005d97  sub     edx, 1
0x180005d9a  jz      short loc_180005DC2
0x180005d9c  sub     edx, 1
0x180005d9f  jz      short loc_180005DBB
0x180005da1  sub     edx, 1
0x180005da4  jz      short loc_180005DBB
0x180005da6  sub     edx, 1
0x180005da9  jz      short loc_180005DBB
0x180005dab  cmp     edx, 1
0x180005dae  jnz     loc_180005E34
0x180005db4  mov     edx, 1
0x180005db9  jmp     short loc_180005DC7
0x180005dbb  mov     edx, 4
0x180005dc0  jmp     short loc_180005DC7
0x180005dc2  mov     edx, 3
0x180005dc7  mov     eax, [rcx+18h]
0x180005dca  mov     r8d, 0FFFFFFFFh
0x180005dd0  imul    rax, rdx
0x180005dd4  xor     edx, edx
0x180005dd6  cmp     rax, r8
0x180005dd9  cmovbe  edx, eax
0x180005ddc  ja      short loc_180005DF1
0x180005dde  mov     eax, [rcx+1Ch]
0x180005de1  mov     ecx, edx
0x180005de3  imul    rax, rcx
0x180005de7  cmp     rax, r8
0x180005dea  ja      short loc_180005DF1
0x180005dec  add     rsp, 68h
0x180005df0  retn
0x180005df1  lea     rdx, aImageSizeTooLa; "Image size too large"
0x180005df8  lea     rcx, [rsp+68h+var_30]; this
0x180005dfd  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180005e02  mov     edx, 80070057h; int
0x180005e07  lea     rcx, [rsp+68h+arg_0]; this
0x180005e0c  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180005e11  lea     r8, [rsp+68h+var_30]
0x180005e16  lea     rcx, [rsp+68h+pExceptionObject]
0x180005e1b  mov     edx, [rax]
0x180005e1d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x180005e22  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180005e29  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180005e2e  call    _CxxThrowException
0x180005e34  mov     edx, 57h ; 'W'; int
0x180005e39  lea     rcx, [rsp+68h+arg_0]; this
0x180005e3e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180005e43  mov     ecx, [rax]
0x180005e45  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

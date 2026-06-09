# RadioEventWatcher::FindRadioInstance(Windows::Internal::String *)

- ea: `0x180017c70`
- end: `0x180017de7`
- name: `?FindRadioInstance@RadioEventWatcher@@AEAAJPEAVString@Internal@Windows@@@Z`
- size: `375`
- prototype: `int(RadioEventWatcher *__hidden this, struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800178e8`

## callees

- `0x180017c70`
- `0x180017df0`
- `0x18001e798`
- `0x18001e820`
- `0x18003a21c`
- `0x18003a284`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180017dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180017dc2`

## pseudocode

```c
__int64 __fastcall RadioEventWatcher::FindRadioInstance(RadioEventWatcher *this, HSTRING *a2, int a3, int a4)
{
  int v4; // ecx
  int Instances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  HSTRING v10; // rcx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF

  string = (HSTRING)this;
  v4 = tls_index;
  if ( dword_1800A3E90 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800A3E90);
    if ( dword_1800A3E90 == -1 )
    {
      xmmword_1800A3780 = *(_OWORD *)&DeviceFinder::FILTER_INTERFACE_ENABLED.Operator;
      xmmword_1800A3790 = xmmword_180069788;
      xmmword_1800A37A0 = xmmword_180069798;
      qword_1800A37B0 = (__int64)&DeviceFinder::DEVPROPVALUE_TRUE;
      xmmword_1800A37B8 = xmmword_180069740;
      xmmword_1800A37C8 = xmmword_180069750;
      xmmword_1800A37D8 = xmmword_180069760;
      qword_1800A37E8 = (__int64)&GUID_BTHPORT_DEVICE_INTERFACE;
      Init_thread_footer(&dword_1800A3E90);
    }
  }
  string = 0;
  Instances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12 = DeviceFinder::FindInstances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___(
                                                         v4,
                                                         (unsigned int)&xmmword_1800A3780,
                                                         a3,
                                                         a4);
  v7 = Instances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12;
  if ( Instances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12 < 0 )
  {
    v8 = (unsigned int)Instances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12;
    v9 = 234;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)".\\radioeventwatcher.cpp",
      (const char *)v8,
      v12);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    return v7;
  }
  if ( !WindowsGetStringLen(string) )
  {
    v7 = -2147023728;
    v9 = 239;
    v8 = 2147943568LL;
    goto LABEL_8;
  }
  WindowsDeleteString(*a2);
  v10 = string;
  *a2 = 0;
  v7 = WindowsDuplicateString(v10, a2);
  if ( string )
    WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x180017c70  mov     [rsp+arg_8], rbx
0x180017c75  mov     [rsp+string], rcx
0x180017c7a  push    rdi
0x180017c7b  sub     rsp, 30h
0x180017c7f  mov     ecx, cs:_tls_index
0x180017c85  mov     rdi, rdx
0x180017c88  mov     rax, gs:58h
0x180017c91  mov     edx, 4
0x180017c96  mov     rax, [rax+rcx*8]
0x180017c9a  mov     eax, [rdx+rax]
0x180017c9d  cmp     cs:dword_1800A3E90, eax
0x180017ca3  jle     loc_180017D42
0x180017ca9  lea     rcx, dword_1800A3E90
0x180017cb0  call    _Init_thread_header
0x180017cb5  cmp     cs:dword_1800A3E90, 0FFFFFFFFh
0x180017cbc  jnz     loc_180017D42
0x180017cc2  movups  xmm0, cs:?FILTER_INTERFACE_ENABLED@DeviceFinder@@2U_DEVPROP_FILTER_EXPRESSION@@B; _DEVPROP_FILTER_EXPRESSION const DeviceFinder::FILTER_INTERFACE_ENABLED
0x180017cc9  lea     rcx, dword_1800A3E90
0x180017cd0  movups  xmm1, cs:xmmword_180069788
0x180017cd7  movaps  cs:xmmword_1800A3780, xmm0
0x180017cde  movups  xmm0, cs:xmmword_180069798
0x180017ce5  movaps  cs:xmmword_1800A3790, xmm1
0x180017cec  movsd   xmm1, cs:off_1800697A8
0x180017cf4  movaps  cs:xmmword_1800A37A0, xmm0
0x180017cfb  movups  xmm0, cs:xmmword_180069740
0x180017d02  movsd   cs:qword_1800A37B0, xmm1
0x180017d0a  movups  xmm1, cs:xmmword_180069750
0x180017d11  movups  cs:xmmword_1800A37B8, xmm0
0x180017d18  movups  xmm0, cs:xmmword_180069760
0x180017d1f  movups  cs:xmmword_1800A37C8, xmm1
0x180017d26  movsd   xmm1, cs:off_180069770
0x180017d2e  movups  cs:xmmword_1800A37D8, xmm0
0x180017d35  movsd   cs:qword_1800A37E8, xmm1
0x180017d3d  call    _Init_thread_footer
0x180017d42  lea     rax, [rsp+38h+string]
0x180017d47  mov     [rsp+38h+string], 0
0x180017d50  lea     rdx, xmmword_1800A3780
0x180017d57  mov     [rsp+38h+var_10], rax
0x180017d5c  call    DeviceFinder__FindInstances__lambda_a13cb55ba1c98070f9e9d109b3a1cc12___
0x180017d61  mov     ebx, eax
0x180017d63  test    eax, eax
0x180017d65  jns     short loc_180017D71
0x180017d67  mov     r9d, eax
0x180017d6a  mov     edx, 0EAh
0x180017d6f  jmp     short loc_180017D8D
0x180017d71  mov     rcx, [rsp+38h+string]; string
0x180017d76  call    cs:__imp_WindowsGetStringLen
0x180017d7c  test    eax, eax
0x180017d7e  jnz     short loc_180017DAA
0x180017d80  mov     ebx, 80070490h
0x180017d85  mov     edx, 0EFh; void *
0x180017d8a  mov     r9d, ebx; char *
0x180017d8d  mov     rcx, [rsp+38h]; this
0x180017d92  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180017d99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d9e  lea     rcx, [rsp+38h+string]; this
0x180017da3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180017da8  jmp     short loc_180017DDA
0x180017daa  mov     rcx, [rdi]; string
0x180017dad  call    cs:__imp_WindowsDeleteString
0x180017db3  mov     rcx, [rsp+38h+string]; string
0x180017db8  mov     rdx, rdi; newString
0x180017dbb  mov     qword ptr [rdi], 0
0x180017dc2  call    cs:__imp_WindowsDuplicateString
0x180017dc8  mov     rcx, [rsp+38h+string]; string
0x180017dcd  mov     ebx, eax
0x180017dcf  test    rcx, rcx
0x180017dd2  jz      short loc_180017DDA
0x180017dd4  call    cs:__imp_WindowsDeleteString
0x180017dda  mov     eax, ebx
0x180017ddc  mov     rbx, [rsp+38h+arg_8]
0x180017de1  add     rsp, 30h
0x180017de5  pop     rdi
0x180017de6  retn
```

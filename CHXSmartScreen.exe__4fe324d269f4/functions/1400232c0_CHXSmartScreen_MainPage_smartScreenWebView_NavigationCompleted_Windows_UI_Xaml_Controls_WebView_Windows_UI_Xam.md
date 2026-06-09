# CHXSmartScreen::MainPage::smartScreenWebView_NavigationCompleted(Windows::UI::Xaml::Controls::WebView *,Windows::UI::Xaml::Controls::WebViewNavigationCompletedEventArgs *)

- ea: `0x1400232c0`
- end: `0x1400234cf`
- name: `?smartScreenWebView_NavigationCompleted@MainPage@CHXSmartScreen@@AE$AAAXPE$AAVWebView@Controls@Xaml@UI@Windows@@PE$AAVWebViewNavigationCompletedEventArgs@4567@@Z`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000108c`
- `0x1400039b6`
- `0x1400039ce`
- `0x1400086b0`
- `0x140013da8`
- `0x1400232c0`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?ToString@Enum@Platform@@QE$AAAPE$AAVString@2@XZ` at `0x1400233ed`
- `wincorlib!?ToString@Enum@Platform@@QE$AAAPE$AAVString@2@XZ` at `0x1400233ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall CHXSmartScreen::MainPage::smartScreenWebView_NavigationCompleted(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT result; // eax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdi
  int v10; // eax
  HSTRING v11; // rsi
  PCWSTR StringRawBuffer_0; // rax
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+50h] [rbp+7h] BYREF
  PCWSTR v18; // [rsp+70h] [rbp+27h]
  int v19; // [rsp+78h] [rbp+2Fh]
  int v20; // [rsp+7Ch] [rbp+33h]

  v16[0] = 0;
  result = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a3 + 56LL))(a3, v16);
  if ( result < 0 )
    __abi_WinRTraiseException(result);
  if ( !v16[0] )
  {
    result = dword_14004BBC8;
    if ( (unsigned int)dword_14004BBC8 > 5 )
    {
      result = qword_14004BBD8;
      if ( (qword_14004BBD8 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_14004BBE0 & 0x400000000000LL) == qword_14004BBE0 )
        {
          LODWORD(v15) = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, &v15);
          if ( v5 < 0 )
            __abi_WinRTraiseException(v5);
          v7 = Platform::Box<enum Windows::Web::WebErrorStatus>::Box<enum Windows::Web::WebErrorStatus>(v6, v15);
          v8 = v7;
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v9 = 0;
          v15 = 0;
          if ( v8 )
          {
            v10 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(v8, &_uuidof__AVEnum_Platform__, &v15);
            if ( v10 < 0 )
              __abi_WinRTraiseException(v10);
            v9 = v15;
          }
          v11 = (HSTRING)Platform::Enum::ToString(v9);
          StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v11, 0);
          if ( StringRawBuffer_0 )
          {
            v13 = -1;
            do
              ++v13;
            while ( StringRawBuffer_0[v13] );
            v14 = 2 * v13 + 2;
          }
          else
          {
            StringRawBuffer_0 = (PCWSTR)&qword_14003A3D8;
            v14 = 2;
          }
          v18 = StringRawBuffer_0;
          v19 = v14;
          v20 = 0;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_14004BBC8,
            (unsigned __int8 *)&byte_14003E449,
            0,
            0,
            3u,
            &v17);
          result = WindowsDeleteString_0(v11);
          if ( v9 )
            result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          if ( v8 )
            return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400232c0  mov     [rsp-8+arg_0], rbx
0x1400232c5  mov     [rsp-8+arg_8], rsi
0x1400232ca  push    rbp
0x1400232cb  push    rdi
0x1400232cc  push    r14
0x1400232ce  lea     rbp, [rsp-47h]
0x1400232d3  sub     rsp, 90h
0x1400232da  mov     rax, cs:__security_cookie
0x1400232e1  xor     rax, rsp
0x1400232e4  mov     [rbp+57h+var_20], rax
0x1400232e8  mov     rbx, r8
0x1400232eb  xor     r14d, r14d
0x1400232ee  mov     [rbp+57h+var_58], r14b
0x1400232f2  mov     rax, [r8]
0x1400232f5  lea     rdx, [rbp+57h+var_58]
0x1400232f9  mov     rcx, r8
0x1400232fc  mov     rax, [rax+38h]
0x140023300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023305  test    eax, eax
0x140023307  js      loc_1400234BF
0x14002330d  cmp     [rbp+57h+var_58], r14b
0x140023311  jnz     loc_140023493
0x140023317  mov     eax, cs:dword_14004BBC8
0x14002331d  cmp     eax, 5
0x140023320  jbe     loc_140023493
0x140023326  mov     rdx, cs:qword_14004BBE0
0x14002332d  mov     rax, cs:qword_14004BBD8
0x140023334  mov     rcx, 400000000000h
0x14002333e  test    rcx, rax
0x140023341  jz      loc_140023493
0x140023347  mov     rax, rdx
0x14002334a  and     rax, rcx
0x14002334d  cmp     rax, rdx
0x140023350  jnz     loc_140023493
0x140023356  mov     dword ptr [rbp+57h+var_60], r14d
0x14002335a  mov     rax, [rbx]
0x14002335d  lea     rdx, [rbp+57h+var_60]
0x140023361  mov     rcx, rbx
0x140023364  mov     rax, [rax+40h]
0x140023368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002336d  test    eax, eax
0x14002336f  js      loc_1400234C7
0x140023375  mov     [rbp+57h+var_70], r14
0x140023379  mov     edx, dword ptr [rbp+57h+var_60]
0x14002337c  call    ??0?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@QE$AAA@W4WebErrorStatus@Web@Windows@@@Z; Platform::Box<Windows::Web::WebErrorStatus>::Box<Windows::Web::WebErrorStatus>(Windows::Web::WebErrorStatus)
0x140023381  mov     rbx, rax
0x140023384  mov     [rbp+57h+var_70], rax
0x140023388  test    rax, rax
0x14002338b  jz      short loc_14002339D
0x14002338d  mov     rcx, [rax]
0x140023390  mov     rax, [rcx+8]
0x140023394  mov     rcx, rbx
0x140023397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002339c  nop
0x14002339d  test    rbx, rbx
0x1400233a0  jz      short loc_1400233B1
0x1400233a2  mov     rax, [rbx]
0x1400233a5  mov     rcx, rbx
0x1400233a8  mov     rax, [rax+10h]
0x1400233ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400233b1  mov     [rbp+57h+var_70], rbx
0x1400233b5  mov     rdi, r14
0x1400233b8  mov     [rbp+57h+var_60], r14
0x1400233bc  test    rbx, rbx
0x1400233bf  jz      short loc_1400233E6
0x1400233c1  mov     rax, [rbx]
0x1400233c4  lea     r8, [rbp+57h+var_60]
0x1400233c8  lea     rdx, __uuidof_?AVEnum@Platform@@
0x1400233cf  mov     rcx, rbx
0x1400233d2  mov     rax, [rax]
0x1400233d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400233da  test    eax, eax
0x1400233dc  js      loc_1400234B7
0x1400233e2  mov     rdi, [rbp+57h+var_60]
0x1400233e6  mov     [rbp+57h+var_68], rdi
0x1400233ea  mov     rcx, rdi
0x1400233ed  call    cs:__imp_?ToString@Enum@Platform@@QE$AAAPE$AAVString@2@XZ; Platform::Enum::ToString(void)
0x1400233f3  mov     rsi, rax
0x1400233f6  mov     [rbp+57h+var_68], rax
0x1400233fa  xor     edx, edx; length
0x1400233fc  mov     rcx, rax; string
0x1400233ff  call    WindowsGetStringRawBuffer_0
0x140023404  test    rax, rax
0x140023407  jz      short loc_140023420
0x140023409  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002340d  inc     rcx
0x140023410  cmp     [rax+rcx*2], r14w
0x140023415  jnz     short loc_14002340D
0x140023417  lea     ecx, ds:2[rcx*2]
0x14002341e  jmp     short loc_14002342C
0x140023420  lea     rax, qword_14003A3D8
0x140023427  mov     ecx, 2
0x14002342c  mov     [rbp+57h+var_30], rax
0x140023430  mov     [rbp+57h+var_28], ecx
0x140023433  mov     [rbp+57h+var_24], r14d
0x140023437  lea     rax, [rbp+57h+var_50]
0x14002343b  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x140023440  mov     [rsp+0A0h+var_80], 3; ULONG
0x140023448  xor     r9d, r9d; int
0x14002344b  xor     r8d, r8d; int
0x14002344e  lea     rdx, byte_14003E449; int
0x140023455  lea     rcx, dword_14004BBC8; int
0x14002345c  call    _tlgWriteTransfer_EventWriteTransfer
0x140023461  mov     rcx, rsi; string
0x140023464  call    WindowsDeleteString_0
0x140023469  nop
0x14002346a  test    rdi, rdi
0x14002346d  jz      short loc_14002347F
0x14002346f  mov     rax, [rdi]
0x140023472  mov     rcx, rdi
0x140023475  mov     rax, [rax+10h]
0x140023479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002347e  nop
0x14002347f  test    rbx, rbx
0x140023482  jz      short loc_140023493
0x140023484  mov     rax, [rbx]
0x140023487  mov     rcx, rbx
0x14002348a  mov     rax, [rax+10h]
0x14002348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023493  mov     rcx, [rbp+57h+var_20]
0x140023497  xor     rcx, rsp; StackCookie
0x14002349a  call    __security_check_cookie
0x14002349f  lea     r11, [rsp+0A0h+var_10]
0x1400234a7  mov     rbx, [r11+20h]
0x1400234ab  mov     rsi, [r11+28h]
0x1400234af  mov     rsp, r11
0x1400234b2  pop     r14
0x1400234b4  pop     rdi
0x1400234b5  pop     rbp
0x1400234b6  retn
0x1400234b7  mov     ecx, eax; int
0x1400234b9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1400234bf  mov     ecx, eax; int
0x1400234c1  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1400234c7  mov     ecx, eax; int
0x1400234c9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```

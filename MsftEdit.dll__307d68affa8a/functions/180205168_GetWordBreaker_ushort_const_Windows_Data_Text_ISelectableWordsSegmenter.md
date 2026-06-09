# GetWordBreaker(ushort const *,Windows::Data::Text::ISelectableWordsSegmenter * *)

- ea: `0x180205168`
- end: `0x18020523a`
- name: `?GetWordBreaker@@YAXPEBGPEAPEAUISelectableWordsSegmenter@Text@Data@Windows@@@Z`
- size: `210`
- prototype: `void __fastcall(const unsigned __int16 *, struct Windows::Data::Text::ISelectableWordsSegmenter **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180048f8c`

## callees

- `0x180048d5c`
- `0x1800e1204`
- `0x1800e1264`
- `0x180205168`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802051ec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802051ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180205211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180205223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180205211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180205223`

## pseudocode

```c
void __fastcall GetWordBreaker(const unsigned __int16 *a1, struct Windows::Data::Text::ISelectableWordsSegmenter **a2)
{
  bool v2; // zf
  int v4; // eax
  HSTRING v5; // rbx
  const unsigned __int16 *v6; // [rsp+40h] [rbp+20h] BYREF
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 v8; // [rsp+50h] [rbp+30h] BYREF
  HSTRING v9; // [rsp+58h] [rbp+38h] BYREF

  v6 = a1;
  v2 = !CW32System::_fOnWin81OrLater;
  v8 = 0;
  *a2 = 0;
  if ( !v2 )
  {
    v9 = 0;
    v4 = Microsoft::WRL::Wrappers::HString::Set(
           (Microsoft::WRL::Wrappers::HString *)&v9,
           L"Windows.Data.Text.SelectableWordsSegmenter",
           0x2Au);
    string = 0;
    if ( !v4 && !(unsigned int)Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v6) )
    {
      v5 = v9;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      if ( (int)RoGetActivationFactory(v5, &GUID_8c7a7648_6057_4339_bc70_f210010a4150, &v8) >= 0 )
        (*(void (__fastcall **)(__int64, HSTRING, struct Windows::Data::Text::ISelectableWordsSegmenter **))(*(_QWORD *)v8 + 48LL))(
          v8,
          string,
          a2);
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v9);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
}

```

## disassembly

```asm
0x180205168  mov     [rsp-18h+arg_0], rcx
0x18020516d  push    rbp
0x18020516e  push    rbx
0x18020516f  push    rdi
0x180205170  mov     rbp, rsp
0x180205173  sub     rsp, 20h
0x180205177  cmp     cs:?_fOnWin81OrLater@CW32System@@0_NA, 0; bool CW32System::_fOnWin81OrLater
0x18020517e  mov     rdi, rdx
0x180205181  mov     [rbp+arg_10], 0
0x180205189  mov     qword ptr [rdx], 0
0x180205190  jz      loc_180205229
0x180205196  mov     r8d, 2Ah ; '*'; unsigned int
0x18020519c  mov     [rbp+arg_18], 0
0x1802051a4  lea     rdx, ?RuntimeClass_Windows_Data_Text_SelectableWordsSegmenter@@3QBGB; "Windows.Data.Text.SelectableWordsSegmen"...
0x1802051ab  lea     rcx, [rbp+arg_18]; this
0x1802051af  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1802051b4  mov     [rbp+string], 0
0x1802051bc  test    eax, eax
0x1802051be  jnz     short loc_18020520D
0x1802051c0  lea     rdx, [rbp+arg_0]
0x1802051c4  lea     rcx, [rbp+string]
0x1802051c8  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802051cd  test    eax, eax
0x1802051cf  jnz     short loc_18020520D
0x1802051d1  mov     rbx, [rbp+arg_18]
0x1802051d5  lea     rcx, [rbp+arg_10]
0x1802051d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802051de  lea     r8, [rbp+arg_10]
0x1802051e2  mov     rcx, rbx
0x1802051e5  lea     rdx, _GUID_8c7a7648_6057_4339_bc70_f210010a4150
0x1802051ec  call    cs:__imp_RoGetActivationFactory
0x1802051f2  test    eax, eax
0x1802051f4  js      short loc_18020520D
0x1802051f6  mov     rcx, [rbp+arg_10]
0x1802051fa  mov     r8, rdi
0x1802051fd  mov     rdx, [rbp+string]
0x180205201  mov     rax, [rcx]
0x180205204  mov     rax, [rax+30h]
0x180205208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020520d  mov     rcx, [rbp+string]; string
0x180205211  call    cs:__imp_WindowsDeleteString
0x180205217  mov     rcx, [rbp+arg_18]; string
0x18020521b  mov     [rbp+string], 0
0x180205223  call    cs:__imp_WindowsDeleteString
0x180205229  lea     rcx, [rbp+arg_10]
0x18020522d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180205232  add     rsp, 20h
0x180205236  pop     rdi
0x180205237  pop     rbx
0x180205238  pop     rbp
0x180205239  retn
```

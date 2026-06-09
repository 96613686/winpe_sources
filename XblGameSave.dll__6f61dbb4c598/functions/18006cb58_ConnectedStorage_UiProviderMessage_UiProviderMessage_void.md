# ConnectedStorage::UiProviderMessage::~UiProviderMessage(void)

- ea: `0x18006cb58`
- end: `0x18006cc09`
- name: `??1UiProviderMessage@ConnectedStorage@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(ConnectedStorage::UiProviderMessage *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006c014`
- `0x18006d13c`
- `0x18006d2a0`
- `0x18006d4ec`
- `0x18006d74c`
- `0x18006d9b0`
- `0x18006dbf0`
- `0x18008bdec`
- `0x18008bdfe`

## callees

- `0x18000a040`
- `0x18006cb58`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectedStorage::UiProviderMessage::~UiProviderMessage(ConnectedStorage::UiProviderMessage *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  v2 = *((_QWORD *)this + 14);
  if ( v2 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *((_QWORD *)this + 13);
  if ( v3 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
  {
    *((_QWORD *)this + 12) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18006cb58  push    rbx
0x18006cb5a  sub     rsp, 20h
0x18006cb5e  mov     rbx, rcx
0x18006cb61  mov     rcx, [rcx+70h]
0x18006cb65  test    rcx, rcx
0x18006cb68  jz      short loc_18006CB7F
0x18006cb6a  mov     qword ptr [rbx+70h], 0
0x18006cb72  mov     rax, [rcx]
0x18006cb75  mov     rax, [rax+10h]
0x18006cb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb7e  nop
0x18006cb7f  mov     rcx, [rbx+68h]
0x18006cb83  test    rcx, rcx
0x18006cb86  jz      short loc_18006CB9D
0x18006cb88  mov     qword ptr [rbx+68h], 0
0x18006cb90  mov     rax, [rcx]
0x18006cb93  mov     rax, [rax+10h]
0x18006cb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb9c  nop
0x18006cb9d  mov     rcx, [rbx+60h]
0x18006cba1  test    rcx, rcx
0x18006cba4  jz      short loc_18006CBBB
0x18006cba6  mov     qword ptr [rbx+60h], 0
0x18006cbae  mov     rax, [rcx]
0x18006cbb1  mov     rax, [rax+10h]
0x18006cbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbba  nop
0x18006cbbb  lea     rcx, [rbx+58h]
0x18006cbbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cbc4  lea     rcx, [rbx+50h]
0x18006cbc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cbcd  mov     rcx, [rbx+28h]; string
0x18006cbd1  call    cs:__imp_WindowsDeleteString
0x18006cbd7  mov     qword ptr [rbx+28h], 0
0x18006cbdf  mov     rcx, [rbx+20h]; string
0x18006cbe3  call    cs:__imp_WindowsDeleteString
0x18006cbe9  mov     qword ptr [rbx+20h], 0
0x18006cbf1  mov     rcx, [rbx+18h]; string
0x18006cbf5  call    cs:__imp_WindowsDeleteString
0x18006cbfb  mov     qword ptr [rbx+18h], 0
0x18006cc03  add     rsp, 20h
0x18006cc07  pop     rbx
0x18006cc08  retn
```

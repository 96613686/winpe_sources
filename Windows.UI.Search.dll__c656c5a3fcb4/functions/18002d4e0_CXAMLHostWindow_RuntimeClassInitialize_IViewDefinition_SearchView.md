# CXAMLHostWindow::RuntimeClassInitialize(IViewDefinition *,SearchView)

- ea: `0x18002d4e0`
- end: `0x18002d602`
- name: `?RuntimeClassInitialize@CXAMLHostWindow@@QEAAJPEAUIViewDefinition@@W4SearchView@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a9dc`

## callees

- `0x18000e31c`
- `0x180010fd0`
- `0x18002d4e0`
- `0x18002d7ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002d555`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002d555`
- `SHCORE!IUnknown_SetSite` at `0x18002d502`
- `SHCORE!IUnknown_SetSite` at `0x18002d5ea`
- `SHCORE!IUnknown_SetSite` at `0x18002d502`
- `SHCORE!IUnknown_SetSite` at `0x18002d5ea`
- `USER32!RegisterWindowMessageW` at `0x18002d528`
- `USER32!RegisterWindowMessageW` at `0x18002d579`
- `USER32!RegisterWindowMessageW` at `0x18002d59b`
- `USER32!RegisterWindowMessageW` at `0x18002d528`
- `USER32!RegisterWindowMessageW` at `0x18002d579`
- `USER32!RegisterWindowMessageW` at `0x18002d59b`

## pseudocode

```c
__int64 __fastcall CXAMLHostWindow::RuntimeClassInitialize(__int64 a1, IUnknown *a2, int a3)
{
  HRESULT Error; // ebx
  UINT v6; // eax
  HANDLE Event; // rax
  UINT v8; // eax
  UINT v9; // eax
  const unsigned __int16 *v10; // rdx
  HKEY v11; // rcx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // r9d
  int v15; // [rsp+50h] [rbp+18h] BYREF

  *(_DWORD *)(a1 + 432) = a3;
  Error = IUnknown_SetSite(a2, (IUnknown *)a1);
  if ( Error < 0 )
    goto LABEL_13;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>::operator=(
    a1 + 208,
    a2);
  v6 = RegisterWindowMessageW(L"WaitForXamlShutdown");
  *(_DWORD *)(a1 + 380) = v6;
  if ( !v6 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_13;
  }
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *(_QWORD *)(a1 + 384) = Event;
  if ( !Event )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_13;
  }
  v8 = RegisterWindowMessageW(L"XAMLHostScaleNotification");
  *(_DWORD *)(a1 + 456) = v8;
  if ( !v8 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_13;
  }
  v9 = RegisterWindowMessageW(L"XAMLHostVisibilityChanged");
  *(_DWORD *)(a1 + 468) = v9;
  if ( v9 )
  {
    Error = 0;
    goto LABEL_11;
  }
  Error = ResultFromKnownLastError();
  if ( Error < 0 )
  {
LABEL_13:
    IUnknown_SetSite(a2, 0);
    return (unsigned int)Error;
  }
LABEL_11:
  v15 = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(v11, v10, v12, v13, &v15) >= 0 )
    *(_BYTE *)(a1 + 505) = v15 != 0;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002d4e0  mov     [rsp+arg_0], rbx
0x18002d4e5  mov     [rsp+arg_8], rsi
0x18002d4ea  push    rdi
0x18002d4eb  sub     rsp, 30h
0x18002d4ef  mov     rsi, rdx
0x18002d4f2  mov     [rcx+1B0h], r8d
0x18002d4f9  mov     rdx, rcx; punkSite
0x18002d4fc  mov     rdi, rcx
0x18002d4ff  mov     rcx, rsi; punk
0x18002d502  call    cs:__imp_IUnknown_SetSite
0x18002d508  mov     ebx, eax
0x18002d50a  test    eax, eax
0x18002d50c  js      loc_18002D5E5
0x18002d512  lea     rcx, [rdi+0D0h]
0x18002d519  mov     rdx, rsi
0x18002d51c  call    ??4?$ComPtr@U?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAU?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>::operator=(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *)
0x18002d521  lea     rcx, aWaitforxamlshu; "WaitForXamlShutdown"
0x18002d528  call    cs:__imp_RegisterWindowMessageW
0x18002d52e  mov     [rdi+17Ch], eax
0x18002d534  test    eax, eax
0x18002d536  jnz     short loc_18002D547
0x18002d538  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d53d  mov     ebx, eax
0x18002d53f  test    eax, eax
0x18002d541  js      loc_18002D5E5
0x18002d547  xor     edx, edx; lpName
0x18002d549  xor     ecx, ecx; lpEventAttributes
0x18002d54b  mov     r9d, 1F0003h; dwDesiredAccess
0x18002d551  lea     r8d, [rdx+1]; dwFlags
0x18002d555  call    cs:__imp_CreateEventExW
0x18002d55b  mov     [rdi+180h], rax
0x18002d562  test    rax, rax
0x18002d565  jnz     short loc_18002D572
0x18002d567  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d56c  mov     ebx, eax
0x18002d56e  test    eax, eax
0x18002d570  js      short loc_18002D5E5
0x18002d572  lea     rcx, aXamlhostscalen; "XAMLHostScaleNotification"
0x18002d579  call    cs:__imp_RegisterWindowMessageW
0x18002d57f  mov     [rdi+1C8h], eax
0x18002d585  test    eax, eax
0x18002d587  jnz     short loc_18002D594
0x18002d589  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d58e  mov     ebx, eax
0x18002d590  test    eax, eax
0x18002d592  js      short loc_18002D5E5
0x18002d594  lea     rcx, aXamlhostvisibi; "XAMLHostVisibilityChanged"
0x18002d59b  call    cs:__imp_RegisterWindowMessageW
0x18002d5a1  mov     [rdi+1D4h], eax
0x18002d5a7  test    eax, eax
0x18002d5a9  jz      short loc_18002D5AF
0x18002d5ab  xor     ebx, ebx
0x18002d5ad  jmp     short loc_18002D5BA
0x18002d5af  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d5b4  mov     ebx, eax
0x18002d5b6  test    eax, eax
0x18002d5b8  js      short loc_18002D5E5
0x18002d5ba  lea     rax, [rsp+38h+arg_10]
0x18002d5bf  mov     [rsp+38h+arg_10], 0
0x18002d5c7  mov     [rsp+38h+var_18], rax; int *
0x18002d5cc  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002d5d1  test    eax, eax
0x18002d5d3  js      short loc_18002D5F0
0x18002d5d5  cmp     [rsp+38h+arg_10], 0
0x18002d5da  setnz   al
0x18002d5dd  mov     [rdi+1F9h], al
0x18002d5e3  jmp     short loc_18002D5F0
0x18002d5e5  xor     edx, edx; punkSite
0x18002d5e7  mov     rcx, rsi; punk
0x18002d5ea  call    cs:__imp_IUnknown_SetSite
0x18002d5f0  mov     rsi, [rsp+38h+arg_8]
0x18002d5f5  mov     eax, ebx
0x18002d5f7  mov     rbx, [rsp+38h+arg_0]
0x18002d5fc  add     rsp, 30h
0x18002d600  pop     rdi
0x18002d601  retn
```

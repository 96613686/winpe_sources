# VideoFrameImpl::WaitGpuSync(ID3D11Device *,ulong)

- ea: `0x18003851c`
- end: `0x180038636`
- name: `?WaitGpuSync@VideoFrameImpl@@CAXPEAUID3D11Device@@K@Z`
- size: `282`
- prototype: `void __fastcall(struct ID3D11Device *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180036174`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x180037f80`
- `0x1800384d4`
- `0x18003851c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003860e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003860e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800385bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800385bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038543`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038543`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VideoFrameImpl::WaitGpuSync(struct ID3D11Device *a1)
{
  MF *v2; // rcx
  int v3; // r8d
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rbx
  unsigned int v5; // eax
  int v6; // edx
  unsigned int v7; // eax
  int v8; // edx
  MF *v9; // rcx
  int v10; // r8d
  int LastError; // eax
  void **v12; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-8h]
  __int64 v14; // [rsp+40h] [rbp+10h] BYREF

  v14 = 0;
  hHandle = CreateEventW(0, 0, 0, 0);
  v2 = (MF *)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  LOBYTE(v2) = hHandle == 0;
  MF::ThrowOriginateErrorIfTrue(v2, 14, v3);
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
  v5 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_05008617_fbfd_4051_a790_144884b4f6a9,
         &v14);
  MF::ThrowIfFailed((MF *)v5, v6);
  v7 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v14 + 128LL))(v14, hHandle);
  MF::ThrowIfFailed((MF *)v7, v8);
  LOBYTE(v9) = WaitForSingleObject(hHandle, 0x1388u) != 0;
  MF::ThrowOriginateErrorIfTrue(v9, 255, v10);
  v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v12) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    hHandle = 0;
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
}

```

## disassembly

```asm
0x18003851c  mov     [rsp-8+arg_8], rbx
0x180038521  mov     [rsp-8+arg_10], rdi
0x180038526  push    rbp
0x180038527  mov     rbp, rsp
0x18003852a  sub     rsp, 30h
0x18003852e  mov     rdi, rcx
0x180038531  mov     [rbp+arg_0], 0
0x180038539  xor     r9d, r9d; lpName
0x18003853c  xor     r8d, r8d; bInitialState
0x18003853f  xor     edx, edx; bManualReset
0x180038541  xor     ecx, ecx; lpEventAttributes
0x180038543  call    cs:__imp_CreateEventW
0x180038549  mov     [rbp+hHandle], rax
0x18003854d  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180038554  mov     [rbp+var_10], rcx
0x180038558  test    rax, rax
0x18003855b  setz    cl; this
0x18003855e  mov     edx, 8007000Eh; bool
0x180038563  call    ?ThrowOriginateErrorIfTrue@MF@@YAX_NJ@Z; MF::ThrowOriginateErrorIfTrue(bool,long)
0x180038568  mov     rax, [rdi]
0x18003856b  mov     rbx, [rax]
0x18003856e  lea     rcx, [rbp+arg_0]
0x180038572  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180038577  lea     r8, [rbp+arg_0]
0x18003857b  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x180038582  mov     rcx, rdi
0x180038585  mov     rax, rbx
0x180038588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003858d  mov     ecx, eax; this
0x18003858f  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180038594  mov     rcx, [rbp+arg_0]
0x180038598  mov     rax, [rcx]
0x18003859b  mov     rdx, [rbp+hHandle]
0x18003859f  mov     rax, [rax+80h]
0x1800385a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385ab  mov     ecx, eax; this
0x1800385ad  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800385b2  mov     edx, 1388h; dwMilliseconds
0x1800385b7  mov     rcx, [rbp+hHandle]; hHandle
0x1800385bb  call    cs:__imp_WaitForSingleObject
0x1800385c1  test    eax, eax
0x1800385c3  setnz   cl; this
0x1800385c6  mov     edx, 8000FFFFh; bool
0x1800385cb  call    ?ThrowOriginateErrorIfTrue@MF@@YAX_NJ@Z; MF::ThrowOriginateErrorIfTrue(bool,long)
0x1800385d0  nop
0x1800385d1  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800385d8  mov     [rbp+var_10], rax
0x1800385dc  cmp     [rbp+hHandle], 0
0x1800385e1  jz      short loc_18003861D
0x1800385e3  lea     rcx, [rbp+var_10]
0x1800385e7  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800385ec  test    al, al
0x1800385ee  jnz     short loc_180038615
0x1800385f0  call    cs:__imp_GetLastError
0x1800385f6  test    eax, eax
0x1800385f8  jle     short loc_180038602
0x1800385fa  movzx   eax, ax
0x1800385fd  or      eax, 80070000h
0x180038602  xor     r9d, r9d; lpArguments
0x180038605  xor     r8d, r8d; nNumberOfArguments
0x180038608  lea     edx, [r9+1]; dwExceptionFlags
0x18003860c  mov     ecx, eax; dwExceptionCode
0x18003860e  call    cs:__imp_RaiseException
0x180038614  int     3; Trap to Debugger
0x180038615  mov     [rbp+hHandle], 0
0x18003861d  lea     rcx, [rbp+arg_0]
0x180038621  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180038626  mov     rbx, [rsp+30h+arg_8]
0x18003862b  mov     rdi, [rsp+30h+arg_10]
0x180038630  add     rsp, 30h
0x180038634  pop     rbp
0x180038635  retn
```

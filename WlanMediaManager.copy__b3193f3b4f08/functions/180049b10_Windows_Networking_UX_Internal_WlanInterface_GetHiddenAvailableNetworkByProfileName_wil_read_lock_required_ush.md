# Windows::Networking::UX::Internal::WlanInterface::_GetHiddenAvailableNetworkByProfileName(wil::read_lock_required,ushort const *,Windows::Networking::UX::IAvailableNetwork * *)

- ea: `0x180049b10`
- end: `0x180049cbe`
- name: `?_GetHiddenAvailableNetworkByProfileName@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@PEBGPEAPEAUIAvailableNetwork@345@@Z`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180041c70`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x1800359ac`
- `0x180049b10`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049bff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049bff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049c5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049c5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049c8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_GetHiddenAvailableNetworkByProfileName(
        __int64 a1,
        __int64 a2,
        char *a3,
        _QWORD *a4)
{
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int i; // esi
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  PCWSTR StringRawBuffer; // rax
  char *v22; // rcx
  char *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  __int64 v29; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+78h] [rbp+48h] BYREF
  HSTRING string; // [rsp+88h] [rbp+58h] BYREF

  *a4 = 0;
  v30 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 1296) + 56LL))(
         *(_QWORD *)(a1 + 1296),
         &v30);
  v10 = v7;
  if ( v7 >= 0 )
  {
    for ( i = 0; i < v30; ++i )
    {
      v29 = 0;
      v13 = *(_QWORD *)(a1 + 1296);
      v14 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v8, v9);
      if ( v14(v13, i, &v29) >= 0 )
      {
        string = 0;
        *(_QWORD *)v27 = 0;
        v17 = v29;
        v18 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        if ( v18(v17, &string) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v22 = a3;
          v23 = (char *)((char *)StringRawBuffer - a3);
          do
          {
            v20 = *(unsigned __int16 *)&v23[(_QWORD)v22];
            v19 = *(unsigned __int16 *)v22 - (unsigned int)v20;
            if ( (_DWORD)v19 )
              break;
            v22 += 2;
          }
          while ( (_DWORD)v20 );
          if ( !(_DWORD)v19
            && (int)Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                      &v29,
                      v27) >= 0
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 128LL))(*(_QWORD *)v27) )
          {
            v24 = v29;
            v29 = 0;
            *a4 = v24;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              v27,
              v19,
              v20);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v29,
              v25,
              v26);
            return 0;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27, v19, v20);
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v15, v16);
    }
    return 2147943568LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v7,
      v27[0]);
    return v10;
  }
}

```

## disassembly

```asm
0x180049b10  mov     byte ptr [rsp-38h+arg_8], dl
0x180049b14  push    rbp
0x180049b15  push    rbx
0x180049b16  push    rsi
0x180049b17  push    rdi
0x180049b18  push    r13
0x180049b1a  push    r14
0x180049b1c  push    r15
0x180049b1e  mov     rbp, rsp
0x180049b21  sub     rsp, 30h
0x180049b25  mov     r14, r9
0x180049b28  mov     r15, r8
0x180049b2b  mov     r13, rcx
0x180049b2e  mov     qword ptr [r9], 0
0x180049b35  mov     [rbp+arg_8], 0
0x180049b3c  mov     rcx, [rcx+510h]
0x180049b43  mov     rax, [rcx]
0x180049b46  lea     rdx, [rbp+arg_8]
0x180049b4a  mov     rax, [rax+38h]
0x180049b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b53  mov     ebx, eax
0x180049b55  test    eax, eax
0x180049b57  jns     short loc_180049B78
0x180049b59  mov     rcx, [rbp+38h]; this
0x180049b5d  mov     r9d, eax; char *
0x180049b60  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180049b67  mov     edx, 1B6h; void *
0x180049b6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b71  mov     eax, ebx
0x180049b73  jmp     loc_180049CAF
0x180049b78  xor     esi, esi
0x180049b7a  cmp     esi, [rbp+arg_8]
0x180049b7d  jnb     loc_180049CAA
0x180049b83  mov     [rbp+arg_0], 0
0x180049b8b  mov     rdi, [r13+510h]
0x180049b92  mov     rax, [rdi]
0x180049b95  mov     rbx, [rax+30h]
0x180049b99  lea     rcx, [rbp+arg_0]
0x180049b9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049ba2  lea     r8, [rbp+arg_0]
0x180049ba6  mov     edx, esi
0x180049ba8  mov     rcx, rdi
0x180049bab  mov     rax, rbx
0x180049bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bb3  test    eax, eax
0x180049bb5  js      loc_180049C62
0x180049bbb  mov     [rbp+string], 0
0x180049bc3  mov     qword ptr [rbp+var_10], 0
0x180049bcb  mov     rdi, [rbp+arg_0]
0x180049bcf  mov     rax, [rdi]
0x180049bd2  mov     rbx, [rax+38h]
0x180049bd6  xor     ecx, ecx; string
0x180049bd8  call    cs:__imp_WindowsDeleteString
0x180049bde  mov     [rbp+string], 0
0x180049be6  lea     rdx, [rbp+string]
0x180049bea  mov     rcx, rdi
0x180049bed  mov     rax, rbx
0x180049bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bf5  test    eax, eax
0x180049bf7  js      short loc_180049C4D
0x180049bf9  xor     edx, edx; length
0x180049bfb  mov     rcx, [rbp+string]; string
0x180049bff  call    cs:__imp_WindowsGetStringRawBuffer
0x180049c05  mov     rcx, r15
0x180049c08  sub     rax, r15
0x180049c0b  movzx   edx, word ptr [rcx]
0x180049c0e  movzx   r8d, word ptr [rcx+rax]
0x180049c13  sub     edx, r8d
0x180049c16  jnz     short loc_180049C21
0x180049c18  add     rcx, 2
0x180049c1c  test    r8d, r8d
0x180049c1f  jnz     short loc_180049C0B
0x180049c21  test    edx, edx
0x180049c23  jnz     short loc_180049C4D
0x180049c25  lea     rdx, [rbp+var_10]
0x180049c29  lea     rcx, [rbp+arg_0]
0x180049c2d  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x180049c32  test    eax, eax
0x180049c34  js      short loc_180049C4D
0x180049c36  mov     rcx, qword ptr [rbp+var_10]
0x180049c3a  mov     rax, [rcx]
0x180049c3d  mov     rax, [rax+80h]
0x180049c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c49  test    al, al
0x180049c4b  jnz     short loc_180049C72
0x180049c4d  lea     rcx, [rbp+var_10]
0x180049c51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049c56  nop
0x180049c57  mov     rcx, [rbp+string]; string
0x180049c5b  call    cs:__imp_WindowsDeleteString
0x180049c61  nop
0x180049c62  lea     rcx, [rbp+arg_0]
0x180049c66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049c6b  inc     esi
0x180049c6d  jmp     loc_180049B7A
0x180049c72  mov     rax, [rbp+arg_0]
0x180049c76  mov     [rbp+arg_0], 0
0x180049c7e  mov     [r14], rax
0x180049c81  lea     rcx, [rbp+var_10]
0x180049c85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049c8a  nop
0x180049c8b  mov     rcx, [rbp+string]; string
0x180049c8f  call    cs:__imp_WindowsDeleteString
0x180049c95  mov     [rbp+string], 0
0x180049c9d  lea     rcx, [rbp+arg_0]
0x180049ca1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049ca6  xor     eax, eax
0x180049ca8  jmp     short loc_180049CAF
0x180049caa  mov     eax, 80070490h
0x180049caf  add     rsp, 30h
0x180049cb3  pop     r15
0x180049cb5  pop     r14
0x180049cb7  pop     r13
0x180049cb9  pop     rdi
0x180049cba  pop     rsi
0x180049cbb  pop     rbx
0x180049cbc  pop     rbp
0x180049cbd  retn
```

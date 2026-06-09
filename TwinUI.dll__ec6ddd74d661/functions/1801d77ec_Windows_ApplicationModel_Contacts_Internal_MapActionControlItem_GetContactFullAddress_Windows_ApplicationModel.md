# Windows::ApplicationModel::Contacts::Internal::MapActionControlItem::GetContactFullAddress(Windows::ApplicationModel::Contacts::IContactAddress *,HSTRING__ * *)

- ea: `0x1801d77ec`
- end: `0x1801d7a63`
- name: `?GetContactFullAddress@MapActionControlItem@Internal@Contacts@ApplicationModel@Windows@@AEAAJPEAUIContactAddress@345@PEAPEAUHSTRING__@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Contacts::Internal::MapActionControlItem *__hidden this, struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801d9db0`

## callees

- `0x180041d1c`
- `0x180041f54`
- `0x18006f1d0`
- `0x1801d77ec`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d781b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d79ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d781b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d78f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d79ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d7a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d792e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7943`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d796d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d792e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7943`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d796d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d7982`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::MapActionControlItem::GetContactFullAddress(
        Windows::ApplicationModel::Contacts::Internal::MapActionControlItem *this,
        struct Windows::ApplicationModel::Contacts::IContactAddress *a2,
        HSTRING *a3)
{
  __int64 v4; // rax
  __int64 (__fastcall *v6)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // r14
  PCWSTR v17; // rsi
  PCWSTR v18; // rdi
  PCWSTR v19; // rbx
  PCWSTR v20; // rax
  HSTRING v21; // rax
  HSTRING v22; // rcx
  HSTRING v24; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v25[2]; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-18h] BYREF
  HSTRING v27; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+48h] BYREF
  HSTRING v29; // [rsp+C0h] [rbp+50h] BYREF
  HSTRING v30; // [rsp+C8h] [rbp+58h] BYREF

  v27 = (HSTRING)this;
  *a3 = 0;
  v4 = *(_QWORD *)a2;
  v25[0] = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v4 + 48);
  WindowsDeleteString(0);
  v25[0] = 0;
  v7 = v6(a2, v25);
  if ( v7 >= 0 )
  {
    v8 = *(_QWORD *)a2;
    v24 = 0;
    v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v8 + 64);
    WindowsDeleteString(0);
    v24 = 0;
    v7 = v9(a2, &v24);
    if ( v7 >= 0 )
    {
      v10 = *(_QWORD *)a2;
      v30 = 0;
      v11 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v10 + 80);
      WindowsDeleteString(0);
      v30 = 0;
      v7 = v11(a2, &v30);
      if ( v7 >= 0 )
      {
        v12 = *(_QWORD *)a2;
        v29 = 0;
        v13 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v12 + 112);
        WindowsDeleteString(0);
        v29 = 0;
        v7 = v13(a2, &v29);
        if ( v7 >= 0 )
        {
          v14 = *(_QWORD *)a2;
          string = 0;
          v15 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v14 + 96);
          WindowsDeleteString(0);
          string = 0;
          v7 = v15(a2, &string);
          if ( v7 >= 0 )
          {
            memset(v26, 0, sizeof(v26));
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v17 = WindowsGetStringRawBuffer(v29, 0);
            v18 = WindowsGetStringRawBuffer(v30, 0);
            v19 = WindowsGetStringRawBuffer(v24, 0);
            v20 = WindowsGetStringRawBuffer(v25[0], 0);
            v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                   v26,
                   L"%s,%s,%s,%s,%s",
                   v20,
                   v19,
                   v18,
                   v17,
                   StringRawBuffer);
            if ( v7 >= 0 )
            {
              v25[1] = (HSTRING)v26[0];
              v27 = 0;
              v7 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v27);
              if ( v7 < 0 )
              {
                v22 = v27;
              }
              else
              {
                v21 = v27;
                v22 = 0;
                v27 = 0;
                *a3 = v21;
              }
              WindowsDeleteString(v22);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v26);
          }
          WindowsDeleteString(string);
        }
        WindowsDeleteString(v29);
      }
      WindowsDeleteString(v30);
    }
    WindowsDeleteString(v24);
  }
  WindowsDeleteString(v25[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801d77ec  mov     [rsp-38h+arg_0], rcx
0x1801d77f1  push    rbp
0x1801d77f2  push    rbx
0x1801d77f3  push    rsi
0x1801d77f4  push    rdi
0x1801d77f5  push    r12
0x1801d77f7  push    r14
0x1801d77f9  push    r15
0x1801d77fb  mov     rbp, rsp
0x1801d77fe  sub     rsp, 70h
0x1801d7802  xor     r12d, r12d
0x1801d7805  xor     ecx, ecx; string
0x1801d7807  mov     [r8], r12
0x1801d780a  mov     r15, r8
0x1801d780d  mov     rax, [rdx]
0x1801d7810  mov     rdi, rdx
0x1801d7813  mov     [rbp+var_28], r12
0x1801d7817  mov     rbx, [rax+30h]
0x1801d781b  call    cs:__imp_WindowsDeleteString
0x1801d7822  nop     dword ptr [rax+rax+00h]
0x1801d7827  lea     rdx, [rbp+var_28]
0x1801d782b  mov     [rbp+var_28], r12
0x1801d782f  mov     rcx, rdi
0x1801d7832  mov     rax, rbx
0x1801d7835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d783a  mov     ebx, eax
0x1801d783c  test    eax, eax
0x1801d783e  js      loc_1801D7A41
0x1801d7844  mov     rax, [rdi]
0x1801d7847  xor     ecx, ecx; string
0x1801d7849  mov     [rbp+var_30], r12
0x1801d784d  mov     rbx, [rax+40h]
0x1801d7851  call    cs:__imp_WindowsDeleteString
0x1801d7858  nop     dword ptr [rax+rax+00h]
0x1801d785d  lea     rdx, [rbp+var_30]
0x1801d7861  mov     [rbp+var_30], r12
0x1801d7865  mov     rcx, rdi
0x1801d7868  mov     rax, rbx
0x1801d786b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7870  mov     ebx, eax
0x1801d7872  test    eax, eax
0x1801d7874  js      loc_1801D7A31
0x1801d787a  mov     rax, [rdi]
0x1801d787d  xor     ecx, ecx; string
0x1801d787f  mov     [rbp+arg_18], r12
0x1801d7883  mov     rbx, [rax+50h]
0x1801d7887  call    cs:__imp_WindowsDeleteString
0x1801d788e  nop     dword ptr [rax+rax+00h]
0x1801d7893  lea     rdx, [rbp+arg_18]
0x1801d7897  mov     [rbp+arg_18], r12
0x1801d789b  mov     rcx, rdi
0x1801d789e  mov     rax, rbx
0x1801d78a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d78a6  mov     ebx, eax
0x1801d78a8  test    eax, eax
0x1801d78aa  js      loc_1801D7A21
0x1801d78b0  mov     rax, [rdi]
0x1801d78b3  xor     ecx, ecx; string
0x1801d78b5  mov     [rbp+arg_10], r12
0x1801d78b9  mov     rbx, [rax+70h]
0x1801d78bd  call    cs:__imp_WindowsDeleteString
0x1801d78c4  nop     dword ptr [rax+rax+00h]
0x1801d78c9  lea     rdx, [rbp+arg_10]
0x1801d78cd  mov     [rbp+arg_10], r12
0x1801d78d1  mov     rcx, rdi
0x1801d78d4  mov     rax, rbx
0x1801d78d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d78dc  mov     ebx, eax
0x1801d78de  test    eax, eax
0x1801d78e0  js      loc_1801D7A11
0x1801d78e6  mov     rax, [rdi]
0x1801d78e9  xor     ecx, ecx; string
0x1801d78eb  mov     [rbp+string], r12
0x1801d78ef  mov     rbx, [rax+60h]
0x1801d78f3  call    cs:__imp_WindowsDeleteString
0x1801d78fa  nop     dword ptr [rax+rax+00h]
0x1801d78ff  lea     rdx, [rbp+string]
0x1801d7903  mov     [rbp+string], r12
0x1801d7907  mov     rcx, rdi
0x1801d790a  mov     rax, rbx
0x1801d790d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7912  mov     ebx, eax
0x1801d7914  test    eax, eax
0x1801d7916  js      loc_1801D7A01
0x1801d791c  mov     rcx, [rbp+string]; string
0x1801d7920  xor     edx, edx; length
0x1801d7922  mov     [rbp+var_18], r12
0x1801d7926  mov     [rbp+var_10], r12
0x1801d792a  mov     [rbp+var_8], r12
0x1801d792e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d7935  nop     dword ptr [rax+rax+00h]
0x1801d793a  mov     rcx, [rbp+arg_10]; string
0x1801d793e  xor     edx, edx; length
0x1801d7940  mov     r14, rax
0x1801d7943  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d794a  nop     dword ptr [rax+rax+00h]
0x1801d794f  mov     rcx, [rbp+arg_18]; string
0x1801d7953  xor     edx, edx; length
0x1801d7955  mov     rsi, rax
0x1801d7958  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d795f  nop     dword ptr [rax+rax+00h]
0x1801d7964  mov     rcx, [rbp+var_30]; string
0x1801d7968  xor     edx, edx; length
0x1801d796a  mov     rdi, rax
0x1801d796d  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d7974  nop     dword ptr [rax+rax+00h]
0x1801d7979  mov     rcx, [rbp+var_28]; string
0x1801d797d  xor     edx, edx; length
0x1801d797f  mov     rbx, rax
0x1801d7982  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d7989  nop     dword ptr [rax+rax+00h]
0x1801d798e  mov     [rsp+70h+var_40], r14
0x1801d7993  lea     rdx, aSSSSS; "%s,%s,%s,%s,%s"
0x1801d799a  mov     r8, rax
0x1801d799d  mov     [rsp+70h+var_48], rsi
0x1801d79a2  mov     r9, rbx
0x1801d79a5  mov     [rsp+70h+var_50], rdi
0x1801d79aa  lea     rcx, [rbp+var_18]
0x1801d79ae  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801d79b3  mov     ebx, eax
0x1801d79b5  test    eax, eax
0x1801d79b7  js      short loc_1801D79F8
0x1801d79b9  mov     rax, [rbp+var_18]
0x1801d79bd  lea     rdx, [rbp+var_20]
0x1801d79c1  lea     rcx, [rbp+arg_0]; string
0x1801d79c5  mov     [rbp+var_20], rax
0x1801d79c9  mov     [rbp+arg_0], r12
0x1801d79cd  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d79d2  mov     ebx, eax
0x1801d79d4  test    eax, eax
0x1801d79d6  js      short loc_1801D79E8
0x1801d79d8  mov     rax, [rbp+arg_0]
0x1801d79dc  mov     ecx, r12d
0x1801d79df  mov     [rbp+arg_0], rcx
0x1801d79e3  mov     [r15], rax
0x1801d79e6  jmp     short loc_1801D79EC
0x1801d79e8  mov     rcx, [rbp+arg_0]; string
0x1801d79ec  call    cs:__imp_WindowsDeleteString
0x1801d79f3  nop     dword ptr [rax+rax+00h]
0x1801d79f8  lea     rcx, [rbp+var_18]
0x1801d79fc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801d7a01  mov     rcx, [rbp+string]; string
0x1801d7a05  call    cs:__imp_WindowsDeleteString
0x1801d7a0c  nop     dword ptr [rax+rax+00h]
0x1801d7a11  mov     rcx, [rbp+arg_10]; string
0x1801d7a15  call    cs:__imp_WindowsDeleteString
0x1801d7a1c  nop     dword ptr [rax+rax+00h]
0x1801d7a21  mov     rcx, [rbp+arg_18]; string
0x1801d7a25  call    cs:__imp_WindowsDeleteString
0x1801d7a2c  nop     dword ptr [rax+rax+00h]
0x1801d7a31  mov     rcx, [rbp+var_30]; string
0x1801d7a35  call    cs:__imp_WindowsDeleteString
0x1801d7a3c  nop     dword ptr [rax+rax+00h]
0x1801d7a41  mov     rcx, [rbp+var_28]; string
0x1801d7a45  call    cs:__imp_WindowsDeleteString
0x1801d7a4c  nop     dword ptr [rax+rax+00h]
0x1801d7a51  mov     eax, ebx
0x1801d7a53  add     rsp, 70h
0x1801d7a57  pop     r15
0x1801d7a59  pop     r14
0x1801d7a5b  pop     r12
0x1801d7a5d  pop     rdi
0x1801d7a5e  pop     rsi
0x1801d7a5f  pop     rbx
0x1801d7a60  pop     rbp
0x1801d7a61  retn
```

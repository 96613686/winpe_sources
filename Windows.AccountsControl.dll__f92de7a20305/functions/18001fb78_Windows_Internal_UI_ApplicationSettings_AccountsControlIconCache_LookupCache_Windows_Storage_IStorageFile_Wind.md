# Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::LookupCache(Windows::Storage::IStorageFile *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18001fb78`
- end: `0x18001fcaf`
- name: `?LookupCache@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIStorageFile@Storage@5@PEAPEAUIRandomAccessStream@Streams@75@@Z`
- size: `311`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *__hidden this, struct Windows::Storage::IStorageFile *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e2b0`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x18001fab0`
- `0x18001fb78`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc81`

## string_xrefs

- `0x18001fbd7`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`
- `0x18001fc2a`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontroliconcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::LookupCache(
        Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache *this,
        __int64 (__fastcall ***a2)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *),
        struct Windows::Storage::Streams::IRandomAccessStream **a3)
{
  __int64 (__fastcall *v6)(struct Windows::Storage::IStorageFile *, GUID *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  *a3 = 0;
  v17 = 0;
  v6 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  v7 = v6((struct Windows::Storage::IStorageFile *)a2, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v17);
  v8 = v7;
  if ( v7 >= 0 )
  {
    string = 0;
    v9 = v17;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 96LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v11 = Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::LookupCache(this, string, a3);
      v8 = v11;
      if ( v11 >= 0 )
      {
        WindowsDeleteString(string);
        v8 = 0;
        goto LABEL_11;
      }
      if ( v11 == -2147483637 )
      {
        WindowsDeleteString(string);
        v8 = -2147483637;
        goto LABEL_11;
      }
      v12 = 85;
    }
    else
    {
      v12 = 73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
      (const char *)(unsigned int)v11,
      savedregs);
    WindowsDeleteString(string);
LABEL_11:
    string = 0;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x46,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontroliconcache.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return v8;
}

```

## disassembly

```asm
0x18001fb78  mov     [rsp-18h+arg_0], rbx
0x18001fb7d  mov     [rsp-18h+arg_18], rsi
0x18001fb82  push    rbp
0x18001fb83  push    rdi
0x18001fb84  push    r14; int
0x18001fb86  mov     rbp, rsp
0x18001fb89  sub     rsp, 20h
0x18001fb8d  mov     rsi, r8
0x18001fb90  mov     rdi, rdx
0x18001fb93  mov     r14, rcx
0x18001fb96  mov     qword ptr [r8], 0
0x18001fb9d  mov     [rbp+arg_10], 0
0x18001fba5  mov     rax, [rdx]
0x18001fba8  mov     rbx, [rax]
0x18001fbab  lea     rcx, [rbp+arg_10]
0x18001fbaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001fbb4  lea     r8, [rbp+arg_10]
0x18001fbb8  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18001fbbf  mov     rcx, rdi
0x18001fbc2  mov     rax, rbx
0x18001fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbca  mov     ebx, eax
0x18001fbcc  test    eax, eax
0x18001fbce  jns     short loc_18001FBED
0x18001fbd0  mov     rcx, [rbp+18h]; this
0x18001fbd4  mov     r9d, eax; char *
0x18001fbd7  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001fbde  mov     edx, 46h ; 'F'; void *
0x18001fbe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbe8  jmp     loc_18001FC91
0x18001fbed  mov     [rbp+string], 0
0x18001fbf5  mov     rdi, [rbp+arg_10]
0x18001fbf9  mov     rax, [rdi]
0x18001fbfc  mov     rbx, [rax+60h]
0x18001fc00  xor     ecx, ecx; string
0x18001fc02  call    cs:__imp_WindowsDeleteString
0x18001fc08  mov     [rbp+string], 0
0x18001fc10  lea     rdx, [rbp+string]
0x18001fc14  mov     rcx, rdi
0x18001fc17  mov     rax, rbx
0x18001fc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc1f  mov     ebx, eax
0x18001fc21  test    eax, eax
0x18001fc23  jns     short loc_18001FC4A
0x18001fc25  mov     edx, 49h ; 'I'; void *
0x18001fc2a  lea     r8, aOnecoreuapShel_19; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001fc31  mov     r9d, eax; char *
0x18001fc34  mov     rcx, [rbp+18h]; this
0x18001fc38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc3d  nop
0x18001fc3e  mov     rcx, [rbp+string]; string
0x18001fc42  call    cs:__imp_WindowsDeleteString
0x18001fc48  jmp     short loc_18001FC89
0x18001fc4a  mov     r8, rsi; struct Windows::Storage::Streams::IRandomAccessStream **
0x18001fc4d  mov     rdx, [rbp+string]; HSTRING
0x18001fc51  mov     rcx, r14; this
0x18001fc54  call    ?LookupCache@AccountsControlIconCache@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIRandomAccessStream@Streams@Storage@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlIconCache::LookupCache(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18001fc59  mov     ebx, eax
0x18001fc5b  test    eax, eax
0x18001fc5d  jns     short loc_18001FC7D
0x18001fc5f  mov     edi, 8000000Bh
0x18001fc64  cmp     eax, edi
0x18001fc66  jnz     short loc_18001FC76
0x18001fc68  mov     rcx, [rbp+string]; string
0x18001fc6c  call    cs:__imp_WindowsDeleteString
0x18001fc72  mov     ebx, edi
0x18001fc74  jmp     short loc_18001FC89
0x18001fc76  mov     edx, 55h ; 'U'
0x18001fc7b  jmp     short loc_18001FC2A
0x18001fc7d  mov     rcx, [rbp+string]; string
0x18001fc81  call    cs:__imp_WindowsDeleteString
0x18001fc87  xor     ebx, ebx
0x18001fc89  mov     [rbp+string], 0
0x18001fc91  lea     rcx, [rbp+arg_10]
0x18001fc95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001fc9a  mov     eax, ebx
0x18001fc9c  mov     rbx, [rsp+20h+arg_0]
0x18001fca1  mov     rsi, [rsp+20h+arg_18]
0x18001fca6  add     rsp, 20h
0x18001fcaa  pop     r14
0x18001fcac  pop     rdi
0x18001fcad  pop     rbp
0x18001fcae  retn
```

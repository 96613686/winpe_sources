# CAccountsSettingsPane::_PopulateAccountSetting(Windows::UI::ApplicationSettings::ICredentialCommand *,int,tagACCOUNT_SETTING *)

- ea: `0x1800301d4`
- end: `0x1800303c2`
- name: `?_PopulateAccountSetting@CAccountsSettingsPane@@AEAAJPEAUICredentialCommand@ApplicationSettings@UI@Windows@@HPEAUtagACCOUNT_SETTING@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct Windows::UI::ApplicationSettings::ICredentialCommand *, int, struct tagACCOUNT_SETTING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a8b0`

## callees

- `0x180011ffc`
- `0x180018f90`
- `0x18001c434`
- `0x1800301d4`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003025d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800302e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003039c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003025d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800302e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003039c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800302a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800302a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030328`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAccountsSettingsPane::_PopulateAccountSetting(
        CAccountsSettingsPane *this,
        struct Windows::UI::ApplicationSettings::ICredentialCommand *a2,
        int a3,
        struct tagACCOUNT_SETTING *a4)
{
  __int64 (__fastcall *v7)(struct Windows::UI::ApplicationSettings::ICredentialCommand *, __int64 *); // rbx
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  PCWSTR v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h]
  __int64 v24; // [rsp+40h] [rbp-20h]
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]
  __int64 v27; // [rsp+58h] [rbp-8h]
  __int64 v28; // [rsp+90h] [rbp+30h] BYREF
  HSTRING v29; // [rsp+98h] [rbp+38h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+48h] BYREF

  *(_QWORD *)a4 = 0;
  *((_QWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 2) = 0;
  *((_DWORD *)a4 + 6) = 0;
  *((_DWORD *)a4 + 7) = 2;
  v28 = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::UI::ApplicationSettings::ICredentialCommand *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v8 = v7(a2, &v28);
  if ( v8 >= 0 )
  {
    *((_DWORD *)a4 + 8) = (a3 != 1) + 2;
    string = 0;
    v9 = v28;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v10(v9, &string);
    if ( v8 >= 0 )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
      v11 = -1;
      v26 = -1;
      v27 = -1;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v14 = -1;
      do
        ++v14;
      while ( StringRawBuffer[v14] );
      v8 = _AllocStringWorker<CTCoAllocPolicy>(&v25, v13, StringRawBuffer);
      if ( v8 >= 0 )
      {
        v29 = 0;
        v15 = v28;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 48LL);
        WindowsDeleteString(0);
        v29 = 0;
        v8 = v16(v15, &v29);
        if ( v8 >= 0 )
        {
          v22 = 0;
          v23 = 0;
          v24 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
          v23 = -1;
          v24 = -1;
          v17 = WindowsGetStringRawBuffer(v29, 0);
          do
            ++v11;
          while ( v17[v11] );
          v8 = _AllocStringWorker<CTCoAllocPolicy>(&v22, v18, v17);
          if ( v8 >= 0 )
          {
            v19 = v22;
            v22 = 0;
            v24 = 0;
            v23 = 0;
            *(_QWORD *)a4 = v19;
            v20 = v25;
            v25 = 0;
            v27 = 0;
            v26 = 0;
            *((_QWORD *)a4 + 2) = v20;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
        }
        WindowsDeleteString(v29);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
    }
    WindowsDeleteString(string);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800301d4  mov     [rsp-28h+arg_10], rbx
0x1800301d9  mov     [rsp-28h+arg_0], rcx
0x1800301de  push    rbp
0x1800301df  push    rsi
0x1800301e0  push    rdi
0x1800301e1  push    r14
0x1800301e3  push    r15
0x1800301e5  mov     rbp, rsp
0x1800301e8  sub     rsp, 60h
0x1800301ec  mov     r14, r9
0x1800301ef  mov     esi, r8d
0x1800301f2  mov     rdi, rdx
0x1800301f5  xor     r15d, r15d
0x1800301f8  mov     [r9], r15
0x1800301fb  mov     [r9+8], r15
0x1800301ff  mov     [r9+10h], r15
0x180030203  mov     [r9+18h], r15d
0x180030207  mov     dword ptr [r9+1Ch], 2
0x18003020f  mov     [rbp+arg_0], r15
0x180030213  mov     rax, [rdx]
0x180030216  mov     rbx, [rax+30h]
0x18003021a  lea     rcx, [rbp+arg_0]
0x18003021e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030223  lea     rdx, [rbp+arg_0]
0x180030227  mov     rcx, rdi
0x18003022a  mov     rax, rbx
0x18003022d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030232  mov     ebx, eax
0x180030234  test    eax, eax
0x180030236  js      loc_1800303A3
0x18003023c  mov     eax, r15d
0x18003023f  cmp     esi, 1
0x180030242  setnz   al
0x180030245  add     eax, 2
0x180030248  mov     [r14+20h], eax
0x18003024c  mov     [rbp+string], r15
0x180030250  mov     rdi, [rbp+arg_0]
0x180030254  mov     rax, [rdi]
0x180030257  mov     rbx, [rax+40h]
0x18003025b  xor     ecx, ecx; string
0x18003025d  call    cs:__imp_WindowsDeleteString
0x180030263  mov     [rbp+string], r15
0x180030267  lea     rdx, [rbp+string]
0x18003026b  mov     rcx, rdi
0x18003026e  mov     rax, rbx
0x180030271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030276  mov     ebx, eax
0x180030278  test    eax, eax
0x18003027a  js      loc_180030398
0x180030280  mov     [rbp+var_18], r15
0x180030284  mov     [rbp+var_10], r15
0x180030288  mov     [rbp+var_8], r15
0x18003028c  lea     rcx, [rbp+var_18]
0x180030290  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030295  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030299  mov     [rbp+var_10], rsi
0x18003029d  mov     [rbp+var_8], rsi
0x1800302a1  xor     edx, edx; length
0x1800302a3  mov     rcx, [rbp+string]; string
0x1800302a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800302ad  mov     r9, rsi
0x1800302b0  inc     r9
0x1800302b3  cmp     [rax+r9*2], r15w
0x1800302b8  jnz     short loc_1800302B0
0x1800302ba  lea     rcx, [rbp+var_18]
0x1800302be  mov     [rsp+60h+var_38], rcx
0x1800302c3  mov     r8, rax
0x1800302c6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800302cb  mov     ebx, eax
0x1800302cd  test    eax, eax
0x1800302cf  js      loc_18003038E
0x1800302d5  mov     [rbp+arg_8], r15
0x1800302d9  mov     rdi, [rbp+arg_0]
0x1800302dd  mov     rax, [rdi]
0x1800302e0  mov     rbx, [rax+30h]
0x1800302e4  xor     ecx, ecx; string
0x1800302e6  call    cs:__imp_WindowsDeleteString
0x1800302ec  mov     [rbp+arg_8], r15
0x1800302f0  lea     rdx, [rbp+arg_8]
0x1800302f4  mov     rcx, rdi
0x1800302f7  mov     rax, rbx
0x1800302fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ff  mov     ebx, eax
0x180030301  test    eax, eax
0x180030303  js      short loc_180030383
0x180030305  mov     [rbp+var_30], r15
0x180030309  mov     [rbp+var_28], r15
0x18003030d  mov     [rbp+var_20], r15
0x180030311  lea     rcx, [rbp+var_30]
0x180030315  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003031a  mov     [rbp+var_28], rsi
0x18003031e  mov     [rbp+var_20], rsi
0x180030322  xor     edx, edx; length
0x180030324  mov     rcx, [rbp+arg_8]; string
0x180030328  call    cs:__imp_WindowsGetStringRawBuffer
0x18003032e  inc     rsi
0x180030331  cmp     [rax+rsi*2], r15w
0x180030336  jnz     short loc_18003032E
0x180030338  lea     rcx, [rbp+var_30]
0x18003033c  mov     [rsp+60h+var_38], rcx
0x180030341  mov     r9, rsi
0x180030344  mov     r8, rax
0x180030347  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18003034c  mov     ebx, eax
0x18003034e  test    eax, eax
0x180030350  js      short loc_180030379
0x180030352  mov     rax, [rbp+var_30]
0x180030356  mov     [rbp+var_30], r15
0x18003035a  mov     [rbp+var_20], r15
0x18003035e  mov     [rbp+var_28], r15
0x180030362  mov     [r14], rax
0x180030365  mov     rax, [rbp+var_18]
0x180030369  mov     [rbp+var_18], r15
0x18003036d  mov     [rbp+var_8], r15
0x180030371  mov     [rbp+var_10], r15
0x180030375  mov     [r14+10h], rax
0x180030379  lea     rcx, [rbp+var_30]
0x18003037d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030382  nop
0x180030383  mov     rcx, [rbp+arg_8]; string
0x180030387  call    cs:__imp_WindowsDeleteString
0x18003038d  nop
0x18003038e  lea     rcx, [rbp+var_18]
0x180030392  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030397  nop
0x180030398  mov     rcx, [rbp+string]; string
0x18003039c  call    cs:__imp_WindowsDeleteString
0x1800303a2  nop
0x1800303a3  lea     rcx, [rbp+arg_0]
0x1800303a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800303ac  mov     eax, ebx
0x1800303ae  mov     rbx, [rsp+60h+arg_10]
0x1800303b6  add     rsp, 60h
0x1800303ba  pop     r15
0x1800303bc  pop     r14
0x1800303be  pop     rdi
0x1800303bf  pop     rsi
0x1800303c0  pop     rbp
0x1800303c1  retn
```

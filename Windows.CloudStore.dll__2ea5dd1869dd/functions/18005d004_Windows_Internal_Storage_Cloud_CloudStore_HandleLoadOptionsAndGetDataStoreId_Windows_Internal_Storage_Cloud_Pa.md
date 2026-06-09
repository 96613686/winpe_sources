# Windows::Internal::Storage::Cloud::CloudStore::HandleLoadOptionsAndGetDataStoreId(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Internal::Storage::Cloud::LoadOptions,HSTRING__ * *)

- ea: `0x18005d004`
- end: `0x18005d4b1`
- name: `?HandleLoadOptionsAndGetDataStoreId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@11W4LoadOptions@2345@PEAPEAU7@@Z`
- size: `1197`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005c204`

## callees

- `0x18000f4b4`
- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180024fd0`
- `0x18005b770`
- `0x18005babc`
- `0x18005bd94`
- `0x18005d004`
- `0x18005f7bc`
- `0x1800c8458`
- `0x1800e93e0`
- `0x1801201a0`
- `0x180168920`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d15d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d15d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d0a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d2a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d3d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d3eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d44b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d0a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d1f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d2a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d3d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d3eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d44b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::HandleLoadOptionsAndGetDataStoreId(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        HSTRING a4,
        int a5,
        unsigned int a6,
        HSTRING *a7)
{
  char v10; // si
  __int64 v11; // r9
  int EffectivePartition; // eax
  unsigned int v13; // ebx
  HSTRING v14; // r12
  int v15; // eax
  unsigned int v16; // ebx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  HSTRING v20; // r13
  int v21; // eax
  __int64 v22; // rcx
  PCWSTR StringRawBuffer; // rdi
  int v24; // eax
  int v25; // ebx
  HSTRING v26; // rax
  const char *v27; // r9
  __int64 result; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  unsigned int v32; // ebx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  int v37; // [rsp+20h] [rbp-D8h]
  int v38; // [rsp+20h] [rbp-D8h]
  __int64 v39; // [rsp+40h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B0h]
  HSTRING v41; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING *v42; // [rsp+58h] [rbp-A0h]
  HSTRING v43[2]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v44[32]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v45[32]; // [rsp+90h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v43[0] = a4;
  v42 = a7;
  v10 = 0;
  LODWORD(v39) = 0;
  *a7 = 0;
  Windows::Internal::Storage::Cloud::CloudStore::FailFastIfInvalidCallingThread(a6);
  WindowsDeleteString(0);
  v41 = 0;
  LOBYTE(v11) = 1;
  try
  {
    EffectivePartition = Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(a1, a2, a3, v11);
    v13 = EffectivePartition;
    if ( EffectivePartition < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x126E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)EffectivePartition,
        (int)&v41);
      WindowsDeleteString(v41);
      return v13;
    }
    WindowsDeleteString(0);
    v14 = v41;
    string = 0;
    v15 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)a1);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1111,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v15,
        (int)&v41);
    }
    else
    {
      v39 = 0;
      v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 480);
      v18 = **v17;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v19 = v18(v17, &GUID_3f14a274_31fe_4e07_b3fb_6830cde1bfe0, &v39);
      v16 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1114,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v19,
          (int)&v41);
        v29 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
      }
      else
      {
        v37 = a5;
        v20 = v43[0];
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, HSTRING))(*(_QWORD *)v39 + 48LL))(
                v39,
                a2,
                v14,
                v43[0]);
        v16 = v21;
        if ( v21 >= 0 )
        {
          v22 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( (a6 & 1) != 0 )
            goto LABEL_14;
          *(_OWORD *)v43 = 0;
          v24 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)a1);
          v25 = v24;
          if ( v24 < 0 )
          {
            v30 = 4511;
          }
          else
          {
            v24 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, HSTRING *))(**(_QWORD **)(a1 + 480) + 32LL))(
                    *(_QWORD *)(a1 + 480),
                    StringRawBuffer,
                    v43);
            v25 = v24;
            if ( v24 >= 0 )
            {
              v25 = 0;
              goto LABEL_12;
            }
            v30 = 4512;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v24,
            a5);
LABEL_12:
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1277,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v25,
              v37);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v41);
            return (unsigned int)v25;
          }
          else
          {
            if ( LODWORD(v43[0]) != 1 )
            {
LABEL_14:
              v26 = string;
              string = 0;
              *v42 = v26;
              WindowsDeleteString(0);
              string = 0;
              WindowsDeleteString(v41);
              return 0;
            }
            WindowsGetStringRawBuffer(v20, 0);
            v35 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStorage((Windows::Internal::Storage::Cloud::CloudStore *)a1);
            v36 = v35;
            if ( v35 >= 0 )
            {
              v31 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR))(**(_QWORD **)(a1 + 488) + 40LL))(
                      *(_QWORD *)(a1 + 488),
                      StringRawBuffer);
              v32 = v31;
              if ( v31 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x127C,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                  (const char *)(unsigned int)v31,
                  v37);
                if ( (Microsoft_Windows_CloudStoreEnableBits & 4) != 0 )
                {
                  std::wstring::wstring(v44);
                  LODWORD(v39) = 1;
                  v33 = (_QWORD *)WideStringToUtf8String(v45, v44);
                  v10 = 3;
                  if ( v33[3] > 0xFu )
                    v33 = (_QWORD *)*v33;
                  McTemplateU0sq_EventWriteTransfer(v34, DownloadFailed, v33, v32);
                }
                if ( (v10 & 2) != 0 )
                {
                  v10 &= ~2u;
                  std::string::_Tidy_deallocate(v45);
                }
                if ( (v10 & 1) != 0 )
                  std::wstring::~wstring(v44);
              }
              goto LABEL_14;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x127A,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v35,
              v37);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v41);
            return v36;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1115,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v21,
          a5);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1271,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)v16,
      v38);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v41);
    result = v16;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1289,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x18005d004  push    rbx
0x18005d006  push    rsi
0x18005d007  push    rdi
0x18005d008  push    r12
0x18005d00a  push    r13
0x18005d00c  push    r14
0x18005d00e  push    r15
0x18005d010  sub     rsp, 0C0h
0x18005d017  mov     rax, cs:__security_cookie
0x18005d01e  xor     rax, rsp
0x18005d021  mov     [rsp+0F8h+var_48], rax
0x18005d029  mov     [rsp+0F8h+var_98], r9
0x18005d02e  mov     rbx, r8
0x18005d031  mov     r15d, edx
0x18005d034  mov     r14, rcx
0x18005d037  mov     r13, qword ptr [rsp+0F8h+arg_20]
0x18005d03f  mov     rax, [rsp+0F8h+arg_30]
0x18005d047  mov     [rsp+0F8h+var_A0], rax
0x18005d04c  xor     edi, edi
0x18005d04e  mov     esi, edi
0x18005d050  mov     dword ptr [rsp+0F8h+var_B8], edi
0x18005d054  mov     [rax], rdi
0x18005d057  mov     ecx, [rsp+0F8h+arg_28]
0x18005d05e  call    ?FailFastIfInvalidCallingThread@CloudStore@Cloud@Storage@Internal@Windows@@CAXW4LoadOptions@2345@@Z; Windows::Internal::Storage::Cloud::CloudStore::FailFastIfInvalidCallingThread(Windows::Internal::Storage::Cloud::LoadOptions)
0x18005d063  mov     [rsp+0F8h+var_A8], rdi
0x18005d068  xor     ecx, ecx; string
0x18005d06a  call    cs:__imp_WindowsDeleteString
0x18005d070  mov     [rsp+0F8h+var_A8], rdi
0x18005d075  lea     rax, [rsp+0F8h+var_A8]
0x18005d07a  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x18005d07f  mov     r9b, 1
0x18005d082  mov     r8, rbx
0x18005d085  mov     edx, r15d
0x18005d088  mov     rcx, r14
0x18005d08b  call    ?GetEffectivePartition@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@_NPEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,bool,HSTRING__ * *)
0x18005d090  mov     ebx, eax
0x18005d092  test    eax, eax
0x18005d094  js      loc_18005D221
0x18005d09a  mov     [rsp+0F8h+string], rdi
0x18005d09f  xor     ecx, ecx; string
0x18005d0a1  call    cs:__imp_WindowsDeleteString
0x18005d0a7  mov     r12, [rsp+0F8h+var_A8]
0x18005d0ac  mov     [rsp+0F8h+string], rdi
0x18005d0b1  mov     rcx, r14; this
0x18005d0b4  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x18005d0b9  mov     ebx, eax
0x18005d0bb  test    eax, eax
0x18005d0bd  js      loc_18005D35E
0x18005d0c3  mov     [rsp+0F8h+var_B8], rdi
0x18005d0c8  mov     rdi, [r14+1E0h]
0x18005d0cf  mov     rax, [rdi]
0x18005d0d2  mov     rbx, [rax]
0x18005d0d5  lea     rcx, [rsp+0F8h+var_B8]
0x18005d0da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d0df  lea     r8, [rsp+0F8h+var_B8]
0x18005d0e4  lea     rdx, _GUID_3f14a274_31fe_4e07_b3fb_6830cde1bfe0
0x18005d0eb  mov     rcx, rdi
0x18005d0ee  mov     rax, rbx
0x18005d0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0f6  mov     ebx, eax
0x18005d0f8  xor     edi, edi
0x18005d0fa  test    eax, eax
0x18005d0fc  js      loc_18005D24D
0x18005d102  mov     rcx, [rsp+0F8h+var_B8]
0x18005d107  mov     rax, [rcx]
0x18005d10a  lea     rdx, [rsp+0F8h+string]
0x18005d10f  mov     [rsp+0F8h+var_D0], rdx
0x18005d114  mov     qword ptr [rsp+0F8h+var_D8], r13; int
0x18005d119  mov     r13, [rsp+0F8h+var_98]
0x18005d11e  mov     r9, r13
0x18005d121  mov     r8, r12
0x18005d124  mov     edx, r15d
0x18005d127  mov     rax, [rax+30h]
0x18005d12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d130  mov     ebx, eax
0x18005d132  test    eax, eax
0x18005d134  js      loc_18005D37F
0x18005d13a  mov     rcx, [rsp+0F8h+var_B8]
0x18005d13f  test    rcx, rcx
0x18005d142  jz      short loc_18005D156
0x18005d144  mov     [rsp+0F8h+var_B8], rdi
0x18005d149  mov     rax, [rcx]
0x18005d14c  mov     rax, [rax+10h]
0x18005d150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d155  nop
0x18005d156  xor     edx, edx; length
0x18005d158  mov     rcx, [rsp+0F8h+string]; string
0x18005d15d  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d163  mov     rdi, rax
0x18005d166  mov     r15d, 1
0x18005d16c  test    byte ptr [rsp+0F8h+arg_28], r15b
0x18005d174  jnz     short loc_18005D1CA
0x18005d176  xorps   xmm0, xmm0
0x18005d179  movups  xmmword ptr [rsp+0F8h+var_98], xmm0
0x18005d17e  mov     rcx, r14; this
0x18005d181  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x18005d186  mov     ebx, eax
0x18005d188  test    eax, eax
0x18005d18a  js      loc_18005D3AB
0x18005d190  mov     rcx, [r14+1E0h]
0x18005d197  mov     rax, [rcx]
0x18005d19a  lea     r8, [rsp+0F8h+var_98]
0x18005d19f  mov     rdx, rdi
0x18005d1a2  mov     rax, [rax+20h]
0x18005d1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1ab  mov     ebx, eax
0x18005d1ad  test    eax, eax
0x18005d1af  js      loc_18005D2C5
0x18005d1b5  xor     ebx, ebx
0x18005d1b7  test    ebx, ebx
0x18005d1b9  js      loc_18005D3B5
0x18005d1bf  cmp     dword ptr [rsp+0F8h+var_98], r15d
0x18005d1c4  jz      loc_18005D3F8
0x18005d1ca  mov     rax, [rsp+0F8h+string]
0x18005d1cf  mov     [rsp+0F8h+string], 0
0x18005d1d8  mov     rcx, [rsp+0F8h+var_A0]
0x18005d1dd  mov     [rcx], rax
0x18005d1e0  xor     ecx, ecx; string
0x18005d1e2  call    cs:__imp_WindowsDeleteString
0x18005d1e8  mov     [rsp+0F8h+string], 0
0x18005d1f1  mov     rcx, [rsp+0F8h+var_A8]; string
0x18005d1f6  call    cs:__imp_WindowsDeleteString
0x18005d1fc  xor     eax, eax
0x18005d1fe  mov     rcx, [rsp+0F8h+var_48]
0x18005d206  xor     rcx, rsp; StackCookie
0x18005d209  call    __security_check_cookie
0x18005d20e  add     rsp, 0C0h
0x18005d215  pop     r15
0x18005d217  pop     r14
0x18005d219  pop     r13
0x18005d21b  pop     r12
0x18005d21d  pop     rdi
0x18005d21e  pop     rsi
0x18005d21f  pop     rbx
0x18005d220  retn
0x18005d221  mov     rcx, [rsp+0F8h]; this
0x18005d229  mov     r9d, ebx; char *
0x18005d22c  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d233  mov     edx, 126Eh; void *
0x18005d238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d23d  nop
0x18005d23e  mov     rcx, [rsp+0F8h+var_A8]; string
0x18005d243  call    cs:__imp_WindowsDeleteString
0x18005d249  mov     eax, ebx
0x18005d24b  jmp     short loc_18005D1FE
0x18005d24d  mov     rcx, [rsp+0F8h]; this
0x18005d255  mov     r9d, eax; char *
0x18005d258  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d25f  mov     edx, 1114h; void *
0x18005d264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d269  nop
0x18005d26a  mov     rcx, [rsp+0F8h+var_B8]
0x18005d26f  test    rcx, rcx
0x18005d272  jz      short loc_18005D286
0x18005d274  mov     [rsp+0F8h+var_B8], rdi
0x18005d279  mov     rax, [rcx]
0x18005d27c  mov     rax, [rax+10h]
0x18005d280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d285  nop
0x18005d286  mov     rcx, [rsp+0F8h]; this
0x18005d28e  mov     r9d, ebx; char *
0x18005d291  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d298  mov     edx, 1271h; void *
0x18005d29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d2a2  nop
0x18005d2a3  mov     rcx, [rsp+0F8h+string]; string
0x18005d2a8  call    cs:__imp_WindowsDeleteString
0x18005d2ae  mov     [rsp+0F8h+string], rdi
0x18005d2b3  mov     rcx, [rsp+0F8h+var_A8]; string
0x18005d2b8  call    cs:__imp_WindowsDeleteString
0x18005d2be  mov     eax, ebx
0x18005d2c0  jmp     loc_18005D1FE
0x18005d2c5  mov     edx, 11A0h; void *
0x18005d2ca  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d2d1  mov     r9d, eax; char *
0x18005d2d4  mov     rcx, [rsp+0F8h]; this
0x18005d2dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d2e1  jmp     loc_18005D1B7
0x18005d2e6  mov     rcx, [r14+1E8h]
0x18005d2ed  mov     rax, [rcx]
0x18005d2f0  mov     rdx, rdi
0x18005d2f3  mov     rax, [rax+28h]
0x18005d2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2fc  mov     ebx, eax
0x18005d2fe  mov     rcx, [rsp+0F8h]; this
0x18005d306  test    eax, eax
0x18005d308  jns     loc_18005D1CA
0x18005d30e  jmp     loc_18005D458
0x18005d313  mov     rdx, rdi
0x18005d316  lea     rcx, [rsp+0F8h+var_88]
0x18005d31b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d320  nop
0x18005d321  mov     dword ptr [rsp+0F8h+var_B8], r15d
0x18005d326  lea     rdx, [rsp+0F8h+var_88]
0x18005d32b  lea     rcx, [rsp+0F8h+var_68]
0x18005d333  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x18005d338  mov     esi, 3
0x18005d33d  cmp     qword ptr [rax+18h], 0Fh
0x18005d342  jbe     short loc_18005D347
0x18005d344  mov     rax, [rax]
0x18005d347  mov     r9d, ebx
0x18005d34a  mov     r8, rax
0x18005d34d  lea     rdx, DownloadFailed
0x18005d354  call    McTemplateU0sq_EventWriteTransfer
0x18005d359  jmp     loc_18005D479
0x18005d35e  mov     rcx, [rsp+0F8h]; this
0x18005d366  mov     r9d, eax; char *
0x18005d369  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d370  mov     edx, 1111h; void *
0x18005d375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d37a  jmp     loc_18005D286
0x18005d37f  mov     rcx, [rsp+0F8h]; this
0x18005d387  mov     r9d, eax; char *
0x18005d38a  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d391  mov     edx, 1115h; void *
0x18005d396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d39b  nop
0x18005d39c  lea     rcx, [rsp+0F8h+var_B8]
0x18005d3a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d3a6  jmp     loc_18005D286
0x18005d3ab  mov     edx, 119Fh
0x18005d3b0  jmp     loc_18005D2CA
0x18005d3b5  mov     rcx, [rsp+0F8h]; this
0x18005d3bd  mov     r9d, ebx; char *
0x18005d3c0  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d3c7  mov     edx, 1277h; void *
0x18005d3cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d3d1  nop
0x18005d3d2  mov     rcx, [rsp+0F8h+string]; string
0x18005d3d7  call    cs:__imp_WindowsDeleteString
0x18005d3dd  mov     [rsp+0F8h+string], 0
0x18005d3e6  mov     rcx, [rsp+0F8h+var_A8]; string
0x18005d3eb  call    cs:__imp_WindowsDeleteString
0x18005d3f1  mov     eax, ebx
0x18005d3f3  jmp     loc_18005D1FE
0x18005d3f8  xor     edx, edx; length
0x18005d3fa  mov     rcx, r13; string
0x18005d3fd  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d403  mov     rcx, r14; this
0x18005d406  call    ?EnsureCloudStorage@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStorage(void)
0x18005d40b  mov     ebx, eax
0x18005d40d  test    eax, eax
0x18005d40f  jns     loc_18005D2E6
0x18005d415  mov     rcx, [rsp+0F8h]; this
0x18005d41d  mov     r9d, eax; char *
0x18005d420  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d427  mov     edx, 127Ah; void *
0x18005d42c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d431  nop
0x18005d432  mov     rcx, [rsp+0F8h+string]; string
0x18005d437  call    cs:__imp_WindowsDeleteString
0x18005d43d  mov     [rsp+0F8h+string], 0
0x18005d446  mov     rcx, [rsp+0F8h+var_A8]; string
0x18005d44b  call    cs:__imp_WindowsDeleteString
0x18005d451  mov     eax, ebx
0x18005d453  jmp     loc_18005D1FE
0x18005d458  mov     r9d, ebx; char *
0x18005d45b  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005d462  mov     edx, 127Ch; void *
0x18005d467  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d46c  test    cs:Microsoft_Windows_CloudStoreEnableBits, 4
0x18005d473  jnz     loc_18005D313
0x18005d479  test    sil, 2
0x18005d47d  jz      short loc_18005D490
0x18005d47f  and     esi, 0FFFFFFFDh
0x18005d482  lea     rcx, [rsp+0F8h+var_68]; void *
0x18005d48a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005d48f  nop
0x18005d490  test    r15b, sil
0x18005d493  jz      loc_18005D1CA
0x18005d499  lea     rcx, [rsp+0F8h+var_88]
0x18005d49e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d4a3  jmp     loc_18005D1CA
0x18005d4a8  mov     eax, dword ptr [rsp+0F8h+var_B8]
0x18005d4ac  jmp     loc_18005D1FE
```

# SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::UpdateAppUsage(void)

- ea: `0x1800bd74c`
- end: `0x1800bdb11`
- name: `?UpdateAppUsage@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@AEAAJXZ`
- size: `965`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bb730`
- `0x1800bbc40`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180035fec`
- `0x180036a44`
- `0x1800bd74c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd7cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bda80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd7cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bd9a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bda80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bd85c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bd85c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::UpdateAppUsage(
        SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *this,
        const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // ebx
  int v7; // esi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-29h] BYREF
  __int64 v22; // [rsp+28h] [rbp-21h] BYREF
  __int64 v23; // [rsp+30h] [rbp-19h] BYREF
  __int64 v24; // [rsp+38h] [rbp-11h] BYREF
  __int64 v25; // [rsp+40h] [rbp-9h] BYREF
  __int64 v26; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp+7h] BYREF
  HSTRING string; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v26 = 0;
  v27[0] = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v27[1] = 0;
  LOBYTE(v21) = 0;
  v3 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[62])a2);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
         *v3,
         &v26);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL))(
             v26,
             *((_QWORD *)this + 31),
             &v24);
      if ( v7 >= 0 )
        break;
      if ( !*((_DWORD *)this + 72) )
      {
        Sleep(0x3E8u);
        if ( ++v6 < 10 )
          continue;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
        (const char *)(unsigned int)v7,
        v21);
      WindowsDeleteString(0);
      v8 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v5 = v7;
      goto LABEL_40;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, &v22);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 56LL))(v22, &v21);
      v5 = v13;
      if ( v13 >= 0 )
      {
        while ( (_BYTE)v21 )
        {
          v25 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v23) >= 0 )
          {
            if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, &v25) >= 0 )
              *((_QWORD *)this + 34) += v25;
            if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 64LL))(v23, &v25) >= 0 )
              *((_QWORD *)this + 35) += v25;
          }
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v21);
        }
        WindowsDeleteString(0);
        v17 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v18 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
          (const char *)(unsigned int)v13,
          v21);
        WindowsDeleteString(0);
        v14 = v23;
        if ( v23 )
        {
          v23 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        v15 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v16 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
        (const char *)(unsigned int)v9,
        v21);
      WindowsDeleteString(0);
      v10 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v11 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v12 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
      (const char *)(unsigned int)v4,
      v21);
    WindowsDeleteString(0);
  }
LABEL_40:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v27);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
  return v5;
}

```

## disassembly

```asm
0x1800bd74c  mov     [rsp-8+arg_8], rbx
0x1800bd751  mov     [rsp-8+arg_10], rsi
0x1800bd756  push    rbp
0x1800bd757  push    rdi
0x1800bd758  push    r14
0x1800bd75a  lea     rbp, [rsp-47h]
0x1800bd75f  sub     rsp, 90h
0x1800bd766  mov     rax, cs:__security_cookie
0x1800bd76d  xor     rax, rsp
0x1800bd770  mov     [rbp+57h+var_20], rax
0x1800bd774  mov     rdi, rcx
0x1800bd777  xor     r14d, r14d
0x1800bd77a  mov     [rbp+57h+var_58], r14
0x1800bd77e  mov     [rbp+57h+var_50], r14
0x1800bd782  mov     [rbp+57h+var_68], r14
0x1800bd786  mov     [rbp+57h+var_78], r14
0x1800bd78a  mov     [rbp+57h+var_70], r14
0x1800bd78e  mov     [rbp+57h+var_48], r14
0x1800bd792  mov     byte ptr [rbp+57h+var_80], r14b
0x1800bd796  lea     rcx, [rbp+57h+string]; string
0x1800bd79a  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x1800bd79f  lea     rdx, [rbp+57h+var_58]
0x1800bd7a3  mov     rcx, [rax]
0x1800bd7a6  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1800bd7ab  mov     ebx, eax
0x1800bd7ad  test    eax, eax
0x1800bd7af  jns     short loc_1800BD826
0x1800bd7b1  mov     rcx, [rbp+5Fh]; this
0x1800bd7b5  mov     r9d, eax; char *
0x1800bd7b8  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bd7bf  mov     edx, 13Dh; void *
0x1800bd7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd7c9  nop
0x1800bd7ca  xor     ecx, ecx; string
0x1800bd7cc  call    cs:__imp_WindowsDeleteString
0x1800bd7d2  nop
0x1800bd7d3  mov     rcx, [rbp+57h+var_70]
0x1800bd7d7  test    rcx, rcx
0x1800bd7da  jz      short loc_1800BD7ED
0x1800bd7dc  mov     [rbp+57h+var_70], r14
0x1800bd7e0  mov     rax, [rcx]
0x1800bd7e3  mov     rax, [rax+10h]
0x1800bd7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd7ec  nop
0x1800bd7ed  mov     rcx, [rbp+57h+var_78]
0x1800bd7f1  test    rcx, rcx
0x1800bd7f4  jz      short loc_1800BD807
0x1800bd7f6  mov     [rbp+57h+var_78], r14
0x1800bd7fa  mov     rax, [rcx]
0x1800bd7fd  mov     rax, [rax+10h]
0x1800bd801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd806  nop
0x1800bd807  mov     rcx, [rbp+57h+var_68]
0x1800bd80b  test    rcx, rcx
0x1800bd80e  jz      short loc_1800BD821
0x1800bd810  mov     [rbp+57h+var_68], r14
0x1800bd814  mov     rax, [rcx]
0x1800bd817  mov     rax, [rax+10h]
0x1800bd81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd820  nop
0x1800bd821  jmp     loc_1800BDAD8
0x1800bd826  mov     ebx, r14d
0x1800bd829  mov     rcx, [rbp+57h+var_58]
0x1800bd82d  mov     rax, [rcx]
0x1800bd830  lea     r8, [rbp+57h+var_68]
0x1800bd834  mov     rdx, [rdi+0F8h]
0x1800bd83b  mov     rax, [rax+30h]
0x1800bd83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd844  mov     esi, eax
0x1800bd846  test    eax, eax
0x1800bd848  jns     loc_1800BD8E0
0x1800bd84e  cmp     [rdi+120h], r14d
0x1800bd855  jnz     short loc_1800BD869
0x1800bd857  mov     ecx, 3E8h; dwMilliseconds
0x1800bd85c  call    cs:__imp_Sleep
0x1800bd862  inc     ebx
0x1800bd864  cmp     ebx, 0Ah
0x1800bd867  jl      short loc_1800BD829
0x1800bd869  mov     rcx, [rbp+5Fh]; this
0x1800bd86d  mov     r9d, esi; char *
0x1800bd870  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bd877  mov     edx, 153h; void *
0x1800bd87c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd881  nop
0x1800bd882  xor     ecx, ecx; string
0x1800bd884  call    cs:__imp_WindowsDeleteString
0x1800bd88a  nop
0x1800bd88b  mov     rcx, [rbp+57h+var_70]
0x1800bd88f  test    rcx, rcx
0x1800bd892  jz      short loc_1800BD8A5
0x1800bd894  mov     [rbp+57h+var_70], r14
0x1800bd898  mov     rax, [rcx]
0x1800bd89b  mov     rax, [rax+10h]
0x1800bd89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8a4  nop
0x1800bd8a5  mov     rcx, [rbp+57h+var_78]
0x1800bd8a9  test    rcx, rcx
0x1800bd8ac  jz      short loc_1800BD8BF
0x1800bd8ae  mov     [rbp+57h+var_78], r14
0x1800bd8b2  mov     rax, [rcx]
0x1800bd8b5  mov     rax, [rax+10h]
0x1800bd8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8be  nop
0x1800bd8bf  mov     rcx, [rbp+57h+var_68]
0x1800bd8c3  test    rcx, rcx
0x1800bd8c6  jz      short loc_1800BD8D9
0x1800bd8c8  mov     [rbp+57h+var_68], r14
0x1800bd8cc  mov     rax, [rcx]
0x1800bd8cf  mov     rax, [rax+10h]
0x1800bd8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8d8  nop
0x1800bd8d9  mov     ebx, esi
0x1800bd8db  jmp     loc_1800BDAD8
0x1800bd8e0  mov     rcx, [rbp+57h+var_68]
0x1800bd8e4  mov     rax, [rcx]
0x1800bd8e7  lea     rdx, [rbp+57h+var_78]
0x1800bd8eb  mov     rax, [rax+30h]
0x1800bd8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8f4  mov     ebx, eax
0x1800bd8f6  test    eax, eax
0x1800bd8f8  jns     short loc_1800BD96F
0x1800bd8fa  mov     rcx, [rbp+5Fh]; this
0x1800bd8fe  mov     r9d, eax; char *
0x1800bd901  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bd908  mov     edx, 155h; void *
0x1800bd90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd912  nop
0x1800bd913  xor     ecx, ecx; string
0x1800bd915  call    cs:__imp_WindowsDeleteString
0x1800bd91b  nop
0x1800bd91c  mov     rcx, [rbp+57h+var_70]
0x1800bd920  test    rcx, rcx
0x1800bd923  jz      short loc_1800BD936
0x1800bd925  mov     [rbp+57h+var_70], r14
0x1800bd929  mov     rax, [rcx]
0x1800bd92c  mov     rax, [rax+10h]
0x1800bd930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd935  nop
0x1800bd936  mov     rcx, [rbp+57h+var_78]
0x1800bd93a  test    rcx, rcx
0x1800bd93d  jz      short loc_1800BD950
0x1800bd93f  mov     [rbp+57h+var_78], r14
0x1800bd943  mov     rax, [rcx]
0x1800bd946  mov     rax, [rax+10h]
0x1800bd94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd94f  nop
0x1800bd950  mov     rcx, [rbp+57h+var_68]
0x1800bd954  test    rcx, rcx
0x1800bd957  jz      short loc_1800BD96A
0x1800bd959  mov     [rbp+57h+var_68], r14
0x1800bd95d  mov     rax, [rcx]
0x1800bd960  mov     rax, [rax+10h]
0x1800bd964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd969  nop
0x1800bd96a  jmp     loc_1800BDAD8
0x1800bd96f  mov     rcx, [rbp+57h+var_78]
0x1800bd973  mov     rax, [rcx]
0x1800bd976  lea     rdx, [rbp+57h+var_80]
0x1800bd97a  mov     rax, [rax+38h]
0x1800bd97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd983  mov     ebx, eax
0x1800bd985  test    eax, eax
0x1800bd987  jns     loc_1800BDA78
0x1800bd98d  mov     rcx, [rbp+5Fh]; this
0x1800bd991  mov     r9d, eax; char *
0x1800bd994  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bd99b  mov     edx, 156h; void *
0x1800bd9a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd9a5  nop
0x1800bd9a6  xor     ecx, ecx; string
0x1800bd9a8  call    cs:__imp_WindowsDeleteString
0x1800bd9ae  nop
0x1800bd9af  mov     rcx, [rbp+57h+var_70]
0x1800bd9b3  test    rcx, rcx
0x1800bd9b6  jz      short loc_1800BD9C9
0x1800bd9b8  mov     [rbp+57h+var_70], r14
0x1800bd9bc  mov     rax, [rcx]
0x1800bd9bf  mov     rax, [rax+10h]
0x1800bd9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9c8  nop
0x1800bd9c9  mov     rcx, [rbp+57h+var_78]
0x1800bd9cd  test    rcx, rcx
0x1800bd9d0  jz      short loc_1800BD9E3
0x1800bd9d2  mov     [rbp+57h+var_78], r14
0x1800bd9d6  mov     rax, [rcx]
0x1800bd9d9  mov     rax, [rax+10h]
0x1800bd9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9e2  nop
0x1800bd9e3  mov     rcx, [rbp+57h+var_68]
0x1800bd9e7  test    rcx, rcx
0x1800bd9ea  jz      short loc_1800BD9FD
0x1800bd9ec  mov     [rbp+57h+var_68], r14
0x1800bd9f0  mov     rax, [rcx]
0x1800bd9f3  mov     rax, [rax+10h]
0x1800bd9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9fc  nop
0x1800bd9fd  jmp     loc_1800BDAD8
0x1800bda02  mov     [rbp+57h+var_60], r14
0x1800bda06  mov     rcx, [rbp+57h+var_78]
0x1800bda0a  mov     rax, [rcx]
0x1800bda0d  lea     rdx, [rbp+57h+var_70]
0x1800bda11  mov     rax, [rax+30h]
0x1800bda15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda1a  test    eax, eax
0x1800bda1c  js      short loc_1800BDA64
0x1800bda1e  mov     rcx, [rbp+57h+var_70]
0x1800bda22  mov     rax, [rcx]
0x1800bda25  lea     rdx, [rbp+57h+var_60]
0x1800bda29  mov     rax, [rax+38h]
0x1800bda2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda32  test    eax, eax
0x1800bda34  js      short loc_1800BDA41
0x1800bda36  mov     rax, [rbp+57h+var_60]
0x1800bda3a  add     [rdi+110h], rax
0x1800bda41  mov     rcx, [rbp+57h+var_70]
0x1800bda45  mov     rax, [rcx]
0x1800bda48  lea     rdx, [rbp+57h+var_60]
0x1800bda4c  mov     rax, [rax+40h]
0x1800bda50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda55  test    eax, eax
0x1800bda57  js      short loc_1800BDA64
0x1800bda59  mov     rax, [rbp+57h+var_60]
0x1800bda5d  add     [rdi+118h], rax
0x1800bda64  mov     rcx, [rbp+57h+var_78]
0x1800bda68  mov     rax, [rcx]
0x1800bda6b  lea     rdx, [rbp+57h+var_80]
0x1800bda6f  mov     rax, [rax+40h]
0x1800bda73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda78  cmp     byte ptr [rbp+57h+var_80], r14b
0x1800bda7c  jnz     short loc_1800BDA02
0x1800bda7e  xor     ecx, ecx; string
0x1800bda80  call    cs:__imp_WindowsDeleteString
0x1800bda86  nop
0x1800bda87  mov     rcx, [rbp+57h+var_70]
0x1800bda8b  test    rcx, rcx
0x1800bda8e  jz      short loc_1800BDAA1
0x1800bda90  mov     [rbp+57h+var_70], r14
0x1800bda94  mov     rax, [rcx]
0x1800bda97  mov     rax, [rax+10h]
0x1800bda9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdaa0  nop
0x1800bdaa1  mov     rcx, [rbp+57h+var_78]
0x1800bdaa5  test    rcx, rcx
0x1800bdaa8  jz      short loc_1800BDABB
0x1800bdaaa  mov     [rbp+57h+var_78], r14
0x1800bdaae  mov     rax, [rcx]
0x1800bdab1  mov     rax, [rax+10h]
0x1800bdab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdaba  nop
0x1800bdabb  mov     rcx, [rbp+57h+var_68]
0x1800bdabf  test    rcx, rcx
0x1800bdac2  jz      short loc_1800BDAD5
0x1800bdac4  mov     [rbp+57h+var_68], r14
0x1800bdac8  mov     rax, [rcx]
0x1800bdacb  mov     rax, [rax+10h]
0x1800bdacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdad4  nop
0x1800bdad5  mov     ebx, r14d
0x1800bdad8  lea     rcx, [rbp+57h+var_50]
0x1800bdadc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bdae1  nop
0x1800bdae2  lea     rcx, [rbp+57h+var_58]
0x1800bdae6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bdaeb  mov     eax, ebx
0x1800bdaed  mov     rcx, [rbp+57h+var_20]
0x1800bdaf1  xor     rcx, rsp; StackCookie
0x1800bdaf4  call    __security_check_cookie
0x1800bdaf9  lea     r11, [rsp+0A0h+var_10]
0x1800bdb01  mov     rbx, [r11+28h]
0x1800bdb05  mov     rsi, [r11+30h]
0x1800bdb09  mov     rsp, r11
0x1800bdb0c  pop     r14
0x1800bdb0e  pop     rdi
0x1800bdb0f  pop     rbp
0x1800bdb10  retn
```

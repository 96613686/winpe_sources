# SystemSettings::StorageSenseHandlers::CPackageInfo::GetSize(unsigned __int64 *)

- ea: `0x1800c0690`
- end: `0x1800c0aea`
- name: `?GetSize@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEA_K@Z`
- size: `1114`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180035fec`
- `0x180036a44`
- `0x1800c0690`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c06e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c07b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c084f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c08e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0a56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c06e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c07b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c084f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c08e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0a56`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageInfo::GetSize(
        SystemSettings::StorageSenseHandlers::CPackageInfo *this,
        unsigned __int64 *a2)
{
  __int64 (__fastcall *v4)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *); // rbx
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v30; // [rsp+20h] [rbp-29h] BYREF
  __int64 v31; // [rsp+28h] [rbp-21h] BYREF
  HSTRING string; // [rsp+30h] [rbp-19h] BYREF
  __int64 v33; // [rsp+38h] [rbp-11h] BYREF
  __int64 v34; // [rsp+40h] [rbp-9h] BYREF
  __int64 v35; // [rsp+48h] [rbp-1h] BYREF
  __int64 v36; // [rsp+50h] [rbp+7h] BYREF
  __int64 v37; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING v38; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v36 = 0;
  v37 = 0;
  v34 = 0;
  v31 = 0;
  v33 = 0;
  string = 0;
  LOBYTE(v30) = 0;
  v4 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(this, &string);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v38, (const unsigned __int16 (*)[62])v6);
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
            *v10,
            &v36);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v36 + 48LL))(v36, string, &v34);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL))(v34, &v31);
        v7 = v17;
        if ( v17 >= 0 )
        {
          v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v30);
          v7 = v21;
          if ( v21 >= 0 )
          {
            v25 = 0;
            while ( (_BYTE)v30 )
            {
              v35 = 0;
              if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v33) >= 0 )
              {
                if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, &v35) >= 0 )
                  v25 += v35;
                if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 64LL))(v33, &v35) >= 0 )
                  v25 += v35;
                if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 64LL))(v31, &v30) < 0 )
                  LOBYTE(v30) = 0;
              }
            }
            *a2 = v25;
            WindowsDeleteString(string);
            string = 0;
            v26 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            v27 = v31;
            if ( v31 )
            {
              v31 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            v28 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            v7 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1EA,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
              (const char *)(unsigned int)v21,
              v30);
            WindowsDeleteString(string);
            string = 0;
            v22 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            v23 = v31;
            if ( v31 )
            {
              v31 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            v24 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E9,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
            (const char *)(unsigned int)v17,
            v30);
          WindowsDeleteString(string);
          string = 0;
          v18 = v33;
          if ( v33 )
          {
            v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          v19 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          v20 = v34;
          if ( v34 )
          {
            v34 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
          (const char *)(unsigned int)v14,
          v30);
        WindowsDeleteString(string);
        string = 0;
        v15 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v16 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
        (const char *)(unsigned int)v11,
        v30);
      WindowsDeleteString(string);
      string = 0;
      v12 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v5,
      v30);
    WindowsDeleteString(string);
    string = 0;
    v8 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v36);
  return v7;
}

```

## disassembly

```asm
0x1800c0690  mov     [rsp-8+arg_10], rbx
0x1800c0695  mov     [rsp-8+arg_18], rsi
0x1800c069a  push    rbp
0x1800c069b  push    rdi
0x1800c069c  push    r14
0x1800c069e  lea     rbp, [rsp-47h]
0x1800c06a3  sub     rsp, 90h
0x1800c06aa  mov     rax, cs:__security_cookie
0x1800c06b1  xor     rax, rsp
0x1800c06b4  mov     [rbp+57h+var_20], rax
0x1800c06b8  mov     rsi, rdx
0x1800c06bb  mov     rdi, rcx
0x1800c06be  xor     r14d, r14d
0x1800c06c1  mov     [rbp+57h+var_50], r14
0x1800c06c5  mov     [rbp+57h+var_48], r14
0x1800c06c9  mov     [rbp+57h+var_60], r14
0x1800c06cd  mov     [rbp+57h+var_78], r14
0x1800c06d1  mov     [rbp+57h+var_68], r14
0x1800c06d5  mov     [rbp+57h+string], r14
0x1800c06d9  mov     byte ptr [rbp+57h+var_80], r14b
0x1800c06dd  mov     rax, [rcx]
0x1800c06e0  mov     rbx, [rax+50h]
0x1800c06e4  xor     ecx, ecx; string
0x1800c06e6  call    cs:__imp_WindowsDeleteString
0x1800c06ec  mov     [rbp+57h+string], r14
0x1800c06f0  lea     rdx, [rbp+57h+string]
0x1800c06f4  mov     rcx, rdi
0x1800c06f7  mov     rax, rbx
0x1800c06fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c06ff  mov     ebx, eax
0x1800c0701  test    eax, eax
0x1800c0703  jns     short loc_1800C077F
0x1800c0705  mov     rcx, [rbp+5Fh]; this
0x1800c0709  mov     r9d, eax; char *
0x1800c070c  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c0713  mov     edx, 1E4h; void *
0x1800c0718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c071d  nop
0x1800c071e  mov     rcx, [rbp+57h+string]; string
0x1800c0722  call    cs:__imp_WindowsDeleteString
0x1800c0728  mov     [rbp+57h+string], r14
0x1800c072c  mov     rcx, [rbp+57h+var_68]
0x1800c0730  test    rcx, rcx
0x1800c0733  jz      short loc_1800C0746
0x1800c0735  mov     [rbp+57h+var_68], r14
0x1800c0739  mov     rax, [rcx]
0x1800c073c  mov     rax, [rax+10h]
0x1800c0740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0745  nop
0x1800c0746  mov     rcx, [rbp+57h+var_78]
0x1800c074a  test    rcx, rcx
0x1800c074d  jz      short loc_1800C0760
0x1800c074f  mov     [rbp+57h+var_78], r14
0x1800c0753  mov     rax, [rcx]
0x1800c0756  mov     rax, [rax+10h]
0x1800c075a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c075f  nop
0x1800c0760  mov     rcx, [rbp+57h+var_60]
0x1800c0764  test    rcx, rcx
0x1800c0767  jz      short loc_1800C077A
0x1800c0769  mov     [rbp+57h+var_60], r14
0x1800c076d  mov     rax, [rcx]
0x1800c0770  mov     rax, [rax+10h]
0x1800c0774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0779  nop
0x1800c077a  jmp     loc_1800C0AB1
0x1800c077f  lea     rcx, [rbp+57h+var_40]; string
0x1800c0783  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x1800c0788  lea     rdx, [rbp+57h+var_50]
0x1800c078c  mov     rcx, [rax]
0x1800c078f  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1800c0794  mov     ebx, eax
0x1800c0796  test    eax, eax
0x1800c0798  jns     short loc_1800C0814
0x1800c079a  mov     rcx, [rbp+5Fh]; this
0x1800c079e  mov     r9d, eax; char *
0x1800c07a1  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c07a8  mov     edx, 1E6h; void *
0x1800c07ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c07b2  nop
0x1800c07b3  mov     rcx, [rbp+57h+string]; string
0x1800c07b7  call    cs:__imp_WindowsDeleteString
0x1800c07bd  mov     [rbp+57h+string], r14
0x1800c07c1  mov     rcx, [rbp+57h+var_68]
0x1800c07c5  test    rcx, rcx
0x1800c07c8  jz      short loc_1800C07DB
0x1800c07ca  mov     [rbp+57h+var_68], r14
0x1800c07ce  mov     rax, [rcx]
0x1800c07d1  mov     rax, [rax+10h]
0x1800c07d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c07da  nop
0x1800c07db  mov     rcx, [rbp+57h+var_78]
0x1800c07df  test    rcx, rcx
0x1800c07e2  jz      short loc_1800C07F5
0x1800c07e4  mov     [rbp+57h+var_78], r14
0x1800c07e8  mov     rax, [rcx]
0x1800c07eb  mov     rax, [rax+10h]
0x1800c07ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c07f4  nop
0x1800c07f5  mov     rcx, [rbp+57h+var_60]
0x1800c07f9  test    rcx, rcx
0x1800c07fc  jz      short loc_1800C080F
0x1800c07fe  mov     [rbp+57h+var_60], r14
0x1800c0802  mov     rax, [rcx]
0x1800c0805  mov     rax, [rax+10h]
0x1800c0809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c080e  nop
0x1800c080f  jmp     loc_1800C0AB1
0x1800c0814  mov     rcx, [rbp+57h+var_50]
0x1800c0818  mov     rax, [rcx]
0x1800c081b  lea     r8, [rbp+57h+var_60]
0x1800c081f  mov     rdx, [rbp+57h+string]
0x1800c0823  mov     rax, [rax+30h]
0x1800c0827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c082c  mov     ebx, eax
0x1800c082e  test    eax, eax
0x1800c0830  jns     short loc_1800C08AC
0x1800c0832  mov     rcx, [rbp+5Fh]; this
0x1800c0836  mov     r9d, eax; char *
0x1800c0839  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c0840  mov     edx, 1E7h; void *
0x1800c0845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c084a  nop
0x1800c084b  mov     rcx, [rbp+57h+string]; string
0x1800c084f  call    cs:__imp_WindowsDeleteString
0x1800c0855  mov     [rbp+57h+string], r14
0x1800c0859  mov     rcx, [rbp+57h+var_68]
0x1800c085d  test    rcx, rcx
0x1800c0860  jz      short loc_1800C0873
0x1800c0862  mov     [rbp+57h+var_68], r14
0x1800c0866  mov     rax, [rcx]
0x1800c0869  mov     rax, [rax+10h]
0x1800c086d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0872  nop
0x1800c0873  mov     rcx, [rbp+57h+var_78]
0x1800c0877  test    rcx, rcx
0x1800c087a  jz      short loc_1800C088D
0x1800c087c  mov     [rbp+57h+var_78], r14
0x1800c0880  mov     rax, [rcx]
0x1800c0883  mov     rax, [rax+10h]
0x1800c0887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c088c  nop
0x1800c088d  mov     rcx, [rbp+57h+var_60]
0x1800c0891  test    rcx, rcx
0x1800c0894  jz      short loc_1800C08A7
0x1800c0896  mov     [rbp+57h+var_60], r14
0x1800c089a  mov     rax, [rcx]
0x1800c089d  mov     rax, [rax+10h]
0x1800c08a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c08a6  nop
0x1800c08a7  jmp     loc_1800C0AB1
0x1800c08ac  mov     rcx, [rbp+57h+var_60]
0x1800c08b0  mov     rax, [rcx]
0x1800c08b3  lea     rdx, [rbp+57h+var_78]
0x1800c08b7  mov     rax, [rax+30h]
0x1800c08bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c08c0  mov     ebx, eax
0x1800c08c2  test    eax, eax
0x1800c08c4  jns     short loc_1800C0940
0x1800c08c6  mov     rcx, [rbp+5Fh]; this
0x1800c08ca  mov     r9d, eax; char *
0x1800c08cd  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c08d4  mov     edx, 1E9h; void *
0x1800c08d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c08de  nop
0x1800c08df  mov     rcx, [rbp+57h+string]; string
0x1800c08e3  call    cs:__imp_WindowsDeleteString
0x1800c08e9  mov     [rbp+57h+string], r14
0x1800c08ed  mov     rcx, [rbp+57h+var_68]
0x1800c08f1  test    rcx, rcx
0x1800c08f4  jz      short loc_1800C0907
0x1800c08f6  mov     [rbp+57h+var_68], r14
0x1800c08fa  mov     rax, [rcx]
0x1800c08fd  mov     rax, [rax+10h]
0x1800c0901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0906  nop
0x1800c0907  mov     rcx, [rbp+57h+var_78]
0x1800c090b  test    rcx, rcx
0x1800c090e  jz      short loc_1800C0921
0x1800c0910  mov     [rbp+57h+var_78], r14
0x1800c0914  mov     rax, [rcx]
0x1800c0917  mov     rax, [rax+10h]
0x1800c091b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0920  nop
0x1800c0921  mov     rcx, [rbp+57h+var_60]
0x1800c0925  test    rcx, rcx
0x1800c0928  jz      short loc_1800C093B
0x1800c092a  mov     [rbp+57h+var_60], r14
0x1800c092e  mov     rax, [rcx]
0x1800c0931  mov     rax, [rax+10h]
0x1800c0935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c093a  nop
0x1800c093b  jmp     loc_1800C0AB1
0x1800c0940  mov     rcx, [rbp+57h+var_78]
0x1800c0944  mov     rax, [rcx]
0x1800c0947  lea     rdx, [rbp+57h+var_80]
0x1800c094b  mov     rax, [rax+38h]
0x1800c094f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0954  mov     ebx, eax
0x1800c0956  test    eax, eax
0x1800c0958  jns     short loc_1800C09D4
0x1800c095a  mov     rcx, [rbp+5Fh]; this
0x1800c095e  mov     r9d, eax; char *
0x1800c0961  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c0968  mov     edx, 1EAh; void *
0x1800c096d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0972  nop
0x1800c0973  mov     rcx, [rbp+57h+string]; string
0x1800c0977  call    cs:__imp_WindowsDeleteString
0x1800c097d  mov     [rbp+57h+string], r14
0x1800c0981  mov     rcx, [rbp+57h+var_68]
0x1800c0985  test    rcx, rcx
0x1800c0988  jz      short loc_1800C099B
0x1800c098a  mov     [rbp+57h+var_68], r14
0x1800c098e  mov     rax, [rcx]
0x1800c0991  mov     rax, [rax+10h]
0x1800c0995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c099a  nop
0x1800c099b  mov     rcx, [rbp+57h+var_78]
0x1800c099f  test    rcx, rcx
0x1800c09a2  jz      short loc_1800C09B5
0x1800c09a4  mov     [rbp+57h+var_78], r14
0x1800c09a8  mov     rax, [rcx]
0x1800c09ab  mov     rax, [rax+10h]
0x1800c09af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c09b4  nop
0x1800c09b5  mov     rcx, [rbp+57h+var_60]
0x1800c09b9  test    rcx, rcx
0x1800c09bc  jz      short loc_1800C09CF
0x1800c09be  mov     [rbp+57h+var_60], r14
0x1800c09c2  mov     rax, [rcx]
0x1800c09c5  mov     rax, [rax+10h]
0x1800c09c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c09ce  nop
0x1800c09cf  jmp     loc_1800C0AB1
0x1800c09d4  mov     rbx, r14
0x1800c09d7  cmp     byte ptr [rbp+57h+var_80], r14b
0x1800c09db  jz      short loc_1800C0A4F
0x1800c09dd  mov     [rbp+57h+var_58], r14
0x1800c09e1  mov     rcx, [rbp+57h+var_78]
0x1800c09e5  mov     rax, [rcx]
0x1800c09e8  lea     rdx, [rbp+57h+var_68]
0x1800c09ec  mov     rax, [rax+30h]
0x1800c09f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c09f5  test    eax, eax
0x1800c09f7  js      short loc_1800C09D7
0x1800c09f9  mov     rcx, [rbp+57h+var_68]
0x1800c09fd  mov     rax, [rcx]
0x1800c0a00  lea     rdx, [rbp+57h+var_58]
0x1800c0a04  mov     rax, [rax+38h]
0x1800c0a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a0d  test    eax, eax
0x1800c0a0f  js      short loc_1800C0A15
0x1800c0a11  add     rbx, [rbp+57h+var_58]
0x1800c0a15  mov     rcx, [rbp+57h+var_68]
0x1800c0a19  mov     rax, [rcx]
0x1800c0a1c  lea     rdx, [rbp+57h+var_58]
0x1800c0a20  mov     rax, [rax+40h]
0x1800c0a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a29  test    eax, eax
0x1800c0a2b  js      short loc_1800C0A31
0x1800c0a2d  add     rbx, [rbp+57h+var_58]
0x1800c0a31  mov     rcx, [rbp+57h+var_78]
0x1800c0a35  mov     rax, [rcx]
0x1800c0a38  lea     rdx, [rbp+57h+var_80]
0x1800c0a3c  mov     rax, [rax+40h]
0x1800c0a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a45  test    eax, eax
0x1800c0a47  jns     short loc_1800C09D7
0x1800c0a49  mov     byte ptr [rbp+57h+var_80], r14b
0x1800c0a4d  jmp     short loc_1800C09D7
0x1800c0a4f  mov     [rsi], rbx
0x1800c0a52  mov     rcx, [rbp+57h+string]; string
0x1800c0a56  call    cs:__imp_WindowsDeleteString
0x1800c0a5c  mov     [rbp+57h+string], r14
0x1800c0a60  mov     rcx, [rbp+57h+var_68]
0x1800c0a64  test    rcx, rcx
0x1800c0a67  jz      short loc_1800C0A7A
0x1800c0a69  mov     [rbp+57h+var_68], r14
0x1800c0a6d  mov     rax, [rcx]
0x1800c0a70  mov     rax, [rax+10h]
0x1800c0a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a79  nop
0x1800c0a7a  mov     rcx, [rbp+57h+var_78]
0x1800c0a7e  test    rcx, rcx
0x1800c0a81  jz      short loc_1800C0A94
0x1800c0a83  mov     [rbp+57h+var_78], r14
0x1800c0a87  mov     rax, [rcx]
0x1800c0a8a  mov     rax, [rax+10h]
0x1800c0a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0a93  nop
0x1800c0a94  mov     rcx, [rbp+57h+var_60]
0x1800c0a98  test    rcx, rcx
0x1800c0a9b  jz      short loc_1800C0AAE
0x1800c0a9d  mov     [rbp+57h+var_60], r14
0x1800c0aa1  mov     rax, [rcx]
0x1800c0aa4  mov     rax, [rax+10h]
0x1800c0aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0aad  nop
0x1800c0aae  mov     ebx, r14d
  ... truncated ...
```

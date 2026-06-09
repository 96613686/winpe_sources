# MoUpdateUxManager::get_OptInToMU(int *)

- ea: `0x140177950`
- end: `0x140177e9e`
- name: `?get_OptInToMU@MoUpdateUxManager@@UEAAJPEAH@Z`
- size: `1358`
- prototype: `__int64 __fastcall(MoUpdateUxManager *__hidden this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140035fb0`

## callees

- `0x1400407f8`
- `0x140045404`
- `0x140072104`
- `0x14007224c`
- `0x14016b1e8`
- `0x140177950`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1401779d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1401779d5`
- `OLEAUT32!__imp_SysFreeString` at `0x140177a62`
- `OLEAUT32!__imp_SysFreeString` at `0x140177ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x140177b87`
- `OLEAUT32!__imp_SysFreeString` at `0x140177bed`
- `OLEAUT32!__imp_SysFreeString` at `0x140177cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x140177d1c`
- `OLEAUT32!__imp_SysFreeString` at `0x140177dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x140177e4e`
- `OLEAUT32!__imp_SysFreeString` at `0x140177a62`
- `OLEAUT32!__imp_SysFreeString` at `0x140177ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x140177b87`
- `OLEAUT32!__imp_SysFreeString` at `0x140177bed`
- `OLEAUT32!__imp_SysFreeString` at `0x140177cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x140177d1c`
- `OLEAUT32!__imp_SysFreeString` at `0x140177dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x140177e4e`

## string_xrefs

- `0x1401779ce`: `MoUpdateOrchestrator`
- `0x1401779a6`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x1401779f8`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140177a4d`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140177abb`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140177ba7`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140177c53`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140177d6d`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall MoUpdateUxManager::get_OptInToMU(MoUpdateUxManager *this, int *a2)
{
  BSTR v4; // rax
  OLECHAR *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 **); // r14
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  int v17; // edi
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // edi
  int v21; // eax
  unsigned int v22; // edi
  BSTR bstrString[2]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v24[3]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v25[32]; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v26; // [rsp+68h] [rbp-50h] BYREF
  int v27; // [rsp+70h] [rbp-48h] BYREF
  __int64 v28; // [rsp+78h] [rbp-40h] BYREF
  __int64 *v29; // [rsp+80h] [rbp-38h] BYREF
  __int64 v30; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( g_coreWorkerShuttingDown )
    return 2149884189LL;
  if ( a2 )
  {
    v26 = 0;
    wil::CoCreateInstance<UpdateSession,IUpdateSession3,wil::err_exception_policy>(&v26);
    v4 = SysAllocString(L"MoUpdateOrchestrator");
    v5 = v4;
    v24[2] = v4;
    if ( v4 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD *, BSTR))(*v26 + 64LL))(v26, v4);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v28 = 0;
        v8 = *v26;
        v28 = 0;
        v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v8 + 136))(v26, &v28);
        v10 = v9;
        if ( v9 >= 0 )
        {
          v29 = 0;
          v11 = v28;
          v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v28 + 128LL);
          v29 = 0;
          v13 = (_QWORD *)Windows::Strings::to_wstring(v25, &USO_SERVICE_MU);
          v14 = v13[2];
          if ( v13[3] > 7u )
            v13 = (_QWORD *)*v13;
          v24[0] = v13;
          v24[1] = v14;
          v15 = (_QWORD *)Windows::Strings::to_bstr(bstrString, v24);
          v17 = v12(v11, *v15, &v29);
          if ( bstrString[0] )
            SysFreeString(bstrString[0]);
          std::wstring::~wstring(v25, v16);
          if ( v17 >= 0 )
          {
            v30 = 0;
            v18 = *v29;
            v30 = 0;
            v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 80))(v29, &v30);
            v20 = v19;
            if ( v19 >= 0 )
            {
              if ( v30 )
              {
                LOWORD(v27) = 0;
                v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 88LL))(v30, &v27);
                v22 = v21;
                if ( v21 >= 0 )
                {
                  *a2 = (_WORD)v27 == 0xFFFF;
                  if ( v30 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  if ( v29 )
                    (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
                  if ( v28 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                  SysFreeString(v5);
                  if ( v26 )
                    (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1FC,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
                    (const char *)(unsigned int)v21,
                    (int)bstrString[0]);
                  if ( v30 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  if ( v29 )
                    (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
                  if ( v28 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                  SysFreeString(v5);
                  if ( v26 )
                    (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
                  return v22;
                }
              }
              else
              {
                *a2 = 0;
                if ( v29 )
                  (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
                if ( v28 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                SysFreeString(v5);
                if ( v26 )
                  (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
                return 0;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1F2,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
                (const char *)(unsigned int)v19,
                (int)bstrString[0]);
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              if ( v29 )
                (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
              if ( v28 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
              SysFreeString(v5);
              if ( v26 )
                (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
              return v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1EF,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
              (const char *)(unsigned int)v17,
              (int)bstrString[0]);
            if ( v29 )
              (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            SysFreeString(v5);
            if ( v26 )
              (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
            return (unsigned int)v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EA,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
            (const char *)(unsigned int)v9,
            (int)bstrString[0]);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          SysFreeString(v5);
          if ( v26 )
            (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
          return v10;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
          (const char *)(unsigned int)v6,
          (int)bstrString[0]);
        SysFreeString(v5);
        if ( v26 )
          (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
        return v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
        (const char *)0x8007000ELL,
        (int)bstrString[0]);
      if ( v26 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v26 + 16LL))(v26, *v26);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
      (const char *)0x80004003LL,
      (int)bstrString[0]);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140177950  mov     [rsp+arg_0], rbx
0x140177955  mov     [rsp+arg_10], rsi
0x14017795a  push    rdi
0x14017795b  push    r14
0x14017795d  push    r15
0x14017795f  sub     rsp, 0A0h
0x140177966  mov     rax, cs:__security_cookie
0x14017796d  xor     rax, rsp
0x140177970  mov     [rsp+0B8h+var_28], rax
0x140177978  mov     rsi, rdx
0x14017797b  xor     r15d, r15d
0x14017797e  cmp     cs:?g_coreWorkerShuttingDown@@3_NA, r15b; bool g_coreWorkerShuttingDown
0x140177985  jz      short loc_140177991
0x140177987  mov     eax, 8024A11Dh
0x14017798c  jmp     loc_140177E74
0x140177991  test    rsi, rsi
0x140177994  jnz     short loc_1401779BE
0x140177996  mov     rcx, [rsp+0B8h]; this
0x14017799e  mov     ebx, 80004003h
0x1401779a3  mov     r9d, ebx; char *
0x1401779a6  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1401779ad  mov     edx, 1E1h; void *
0x1401779b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401779b7  mov     eax, ebx
0x1401779b9  jmp     loc_140177E74
0x1401779be  mov     [rsp+0B8h+var_50], r15
0x1401779c3  lea     rcx, [rsp+0B8h+var_50]
0x1401779c8  call    ??$CoCreateInstance@VUpdateSession@@UIUpdateSession3@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateSession3@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSession,IUpdateSession3,wil::err_exception_policy>(ulong)
0x1401779cd  nop
0x1401779ce  lea     rcx, Source; "MoUpdateOrchestrator"
0x1401779d5  call    cs:__imp_SysAllocString
0x1401779db  mov     rbx, rax
0x1401779de  mov     [rsp+0B8h+var_78], rax
0x1401779e3  test    rax, rax
0x1401779e6  jnz     short loc_140177A28
0x1401779e8  mov     rcx, [rsp+0B8h]; this
0x1401779f0  mov     ebx, 8007000Eh
0x1401779f5  mov     r9d, ebx; char *
0x1401779f8  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1401779ff  mov     edx, 1E6h; void *
0x140177a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177a09  nop
0x140177a0a  mov     rcx, [rsp+0B8h+var_50]
0x140177a0f  test    rcx, rcx
0x140177a12  jz      short loc_140177A21
0x140177a14  mov     rdx, [rcx]
0x140177a17  mov     rax, [rdx+10h]
0x140177a1b  call    _guard_dispatch_icall
0x140177a20  nop
0x140177a21  mov     eax, ebx
0x140177a23  jmp     loc_140177E74
0x140177a28  mov     rcx, [rsp+0B8h+var_50]
0x140177a2d  mov     rax, [rcx]
0x140177a30  mov     rdx, rbx
0x140177a33  mov     rax, [rax+40h]
0x140177a37  call    _guard_dispatch_icall
0x140177a3c  mov     edi, eax
0x140177a3e  test    eax, eax
0x140177a40  jns     short loc_140177A87
0x140177a42  mov     rcx, [rsp+0B8h]; this
0x140177a4a  mov     r9d, eax; char *
0x140177a4d  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140177a54  mov     edx, 1E7h; void *
0x140177a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177a5e  nop
0x140177a5f  mov     rcx, rbx; bstrString
0x140177a62  call    cs:__imp_SysFreeString
0x140177a68  nop
0x140177a69  mov     rcx, [rsp+0B8h+var_50]
0x140177a6e  test    rcx, rcx
0x140177a71  jz      short loc_140177A80
0x140177a73  mov     rax, [rcx]
0x140177a76  mov     rax, [rax+10h]
0x140177a7a  call    _guard_dispatch_icall
0x140177a7f  nop
0x140177a80  mov     eax, edi
0x140177a82  jmp     loc_140177E74
0x140177a87  mov     [rsp+0B8h+var_40], r15
0x140177a8c  mov     rcx, [rsp+0B8h+var_50]
0x140177a91  mov     rax, [rcx]
0x140177a94  mov     [rsp+0B8h+var_40], r15
0x140177a99  lea     rdx, [rsp+0B8h+var_40]
0x140177a9e  mov     rax, [rax+88h]
0x140177aa5  call    _guard_dispatch_icall
0x140177aaa  mov     edi, eax
0x140177aac  test    eax, eax
0x140177aae  jns     short loc_140177B0C
0x140177ab0  mov     rcx, [rsp+0B8h]; this
0x140177ab8  mov     r9d, eax; char *
0x140177abb  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140177ac2  mov     edx, 1EAh; void *
0x140177ac7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177acc  nop
0x140177acd  mov     rcx, [rsp+0B8h+var_40]
0x140177ad2  test    rcx, rcx
0x140177ad5  jz      short loc_140177AE4
0x140177ad7  mov     rax, [rcx]
0x140177ada  mov     rax, [rax+10h]
0x140177ade  call    _guard_dispatch_icall
0x140177ae3  nop
0x140177ae4  mov     rcx, rbx; bstrString
0x140177ae7  call    cs:__imp_SysFreeString
0x140177aed  nop
0x140177aee  mov     rcx, [rsp+0B8h+var_50]
0x140177af3  test    rcx, rcx
0x140177af6  jz      short loc_140177B05
0x140177af8  mov     rax, [rcx]
0x140177afb  mov     rax, [rax+10h]
0x140177aff  call    _guard_dispatch_icall
0x140177b04  nop
0x140177b05  mov     eax, edi
0x140177b07  jmp     loc_140177E74
0x140177b0c  mov     [rsp+0B8h+var_38], r15
0x140177b14  mov     rdi, [rsp+0B8h+var_40]
0x140177b19  mov     rax, [rdi]
0x140177b1c  mov     r14, [rax+80h]
0x140177b23  mov     [rsp+0B8h+var_38], r15
0x140177b2b  lea     rdx, ?USO_SERVICE_MU@@3U_GUID@@B; _GUID const USO_SERVICE_MU
0x140177b32  lea     rcx, [rsp+0B8h+var_70]
0x140177b37  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; Windows::Strings::to_wstring(_GUID const &)
0x140177b3c  nop
0x140177b3d  mov     rcx, [rax+10h]
0x140177b41  cmp     qword ptr [rax+18h], 7
0x140177b46  jbe     short loc_140177B4B
0x140177b48  mov     rax, [rax]
0x140177b4b  mov     [rsp+0B8h+var_88], rax
0x140177b50  mov     [rsp+0B8h+var_80], rcx
0x140177b55  lea     rdx, [rsp+0B8h+var_88]
0x140177b5a  lea     rcx, [rsp+0B8h+bstrString]
0x140177b5f  call    ?to_bstr@Strings@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@4@@Z; Windows::Strings::to_bstr(wil::basic_zstring_view<wchar_t>)
0x140177b64  nop
0x140177b65  lea     r8, [rsp+0B8h+var_38]
0x140177b6d  mov     rdx, [rax]
0x140177b70  mov     rcx, rdi
0x140177b73  mov     rax, r14
0x140177b76  call    _guard_dispatch_icall
0x140177b7b  mov     edi, eax
0x140177b7d  mov     rcx, [rsp+0B8h+bstrString]; bstrString
0x140177b82  test    rcx, rcx
0x140177b85  jz      short loc_140177B8E
0x140177b87  call    cs:__imp_SysFreeString
0x140177b8d  nop
0x140177b8e  lea     rcx, [rsp+0B8h+var_70]
0x140177b93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140177b98  test    edi, edi
0x140177b9a  jns     short loc_140177C12
0x140177b9c  mov     rcx, [rsp+0B8h]; this
0x140177ba4  mov     r9d, edi; char *
0x140177ba7  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140177bae  mov     edx, 1EFh; void *
0x140177bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177bb8  nop
0x140177bb9  mov     rcx, [rsp+0B8h+var_38]
0x140177bc1  test    rcx, rcx
0x140177bc4  jz      short loc_140177BD3
0x140177bc6  mov     rax, [rcx]
0x140177bc9  mov     rax, [rax+10h]
0x140177bcd  call    _guard_dispatch_icall
0x140177bd2  nop
0x140177bd3  mov     rcx, [rsp+0B8h+var_40]
0x140177bd8  test    rcx, rcx
0x140177bdb  jz      short loc_140177BEA
0x140177bdd  mov     rax, [rcx]
0x140177be0  mov     rax, [rax+10h]
0x140177be4  call    _guard_dispatch_icall
0x140177be9  nop
0x140177bea  mov     rcx, rbx; bstrString
0x140177bed  call    cs:__imp_SysFreeString
0x140177bf3  nop
0x140177bf4  mov     rcx, [rsp+0B8h+var_50]
0x140177bf9  test    rcx, rcx
0x140177bfc  jz      short loc_140177C0B
0x140177bfe  mov     rax, [rcx]
0x140177c01  mov     rax, [rax+10h]
0x140177c05  call    _guard_dispatch_icall
0x140177c0a  nop
0x140177c0b  mov     eax, edi
0x140177c0d  jmp     loc_140177E74
0x140177c12  mov     [rsp+0B8h+var_30], r15
0x140177c1a  mov     rcx, [rsp+0B8h+var_38]
0x140177c22  mov     rax, [rcx]
0x140177c25  mov     [rsp+0B8h+var_30], r15
0x140177c2d  lea     rdx, [rsp+0B8h+var_30]
0x140177c35  mov     rax, [rax+50h]
0x140177c39  call    _guard_dispatch_icall
0x140177c3e  mov     edi, eax
0x140177c40  test    eax, eax
0x140177c42  jns     loc_140177CD8
0x140177c48  mov     rcx, [rsp+0B8h]; this
0x140177c50  mov     r9d, eax; char *
0x140177c53  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140177c5a  mov     edx, 1F2h; void *
0x140177c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177c64  nop
0x140177c65  mov     rcx, [rsp+0B8h+var_30]
0x140177c6d  test    rcx, rcx
0x140177c70  jz      short loc_140177C7F
0x140177c72  mov     rax, [rcx]
0x140177c75  mov     rax, [rax+10h]
0x140177c79  call    _guard_dispatch_icall
0x140177c7e  nop
0x140177c7f  mov     rcx, [rsp+0B8h+var_38]
0x140177c87  test    rcx, rcx
0x140177c8a  jz      short loc_140177C99
0x140177c8c  mov     rax, [rcx]
0x140177c8f  mov     rax, [rax+10h]
0x140177c93  call    _guard_dispatch_icall
0x140177c98  nop
0x140177c99  mov     rcx, [rsp+0B8h+var_40]
0x140177c9e  test    rcx, rcx
0x140177ca1  jz      short loc_140177CB0
0x140177ca3  mov     rax, [rcx]
0x140177ca6  mov     rax, [rax+10h]
0x140177caa  call    _guard_dispatch_icall
0x140177caf  nop
0x140177cb0  mov     rcx, rbx; bstrString
0x140177cb3  call    cs:__imp_SysFreeString
0x140177cb9  nop
0x140177cba  mov     rcx, [rsp+0B8h+var_50]
0x140177cbf  test    rcx, rcx
0x140177cc2  jz      short loc_140177CD1
0x140177cc4  mov     rax, [rcx]
0x140177cc7  mov     rax, [rax+10h]
0x140177ccb  call    _guard_dispatch_icall
0x140177cd0  nop
0x140177cd1  mov     eax, edi
0x140177cd3  jmp     loc_140177E74
0x140177cd8  mov     rcx, [rsp+0B8h+var_30]
0x140177ce0  test    rcx, rcx
0x140177ce3  jnz     short loc_140177D41
0x140177ce5  mov     [rsi], r15d
0x140177ce8  mov     rcx, [rsp+0B8h+var_38]
0x140177cf0  test    rcx, rcx
0x140177cf3  jz      short loc_140177D02
0x140177cf5  mov     rax, [rcx]
0x140177cf8  mov     rax, [rax+10h]
0x140177cfc  call    _guard_dispatch_icall
0x140177d01  nop
0x140177d02  mov     rcx, [rsp+0B8h+var_40]
0x140177d07  test    rcx, rcx
0x140177d0a  jz      short loc_140177D19
0x140177d0c  mov     rax, [rcx]
0x140177d0f  mov     rax, [rax+10h]
0x140177d13  call    _guard_dispatch_icall
0x140177d18  nop
0x140177d19  mov     rcx, rbx; bstrString
0x140177d1c  call    cs:__imp_SysFreeString
0x140177d22  nop
0x140177d23  mov     rcx, [rsp+0B8h+var_50]
0x140177d28  test    rcx, rcx
0x140177d2b  jz      short loc_140177D3A
0x140177d2d  mov     rax, [rcx]
0x140177d30  mov     rax, [rax+10h]
0x140177d34  call    _guard_dispatch_icall
0x140177d39  nop
0x140177d3a  xor     eax, eax
0x140177d3c  jmp     loc_140177E74
0x140177d41  mov     word ptr [rsp+0B8h+var_48], r15w
0x140177d47  mov     rax, [rcx]
0x140177d4a  lea     rdx, [rsp+0B8h+var_48]
0x140177d4f  mov     rax, [rax+58h]
0x140177d53  call    _guard_dispatch_icall
0x140177d58  mov     edi, eax
0x140177d5a  test    eax, eax
0x140177d5c  jns     loc_140177DF2
0x140177d62  mov     rcx, [rsp+0B8h]; this
0x140177d6a  mov     r9d, eax; char *
0x140177d6d  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140177d74  mov     edx, 1FCh; void *
0x140177d79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140177d7e  nop
0x140177d7f  mov     rcx, [rsp+0B8h+var_30]
0x140177d87  test    rcx, rcx
0x140177d8a  jz      short loc_140177D99
0x140177d8c  mov     rax, [rcx]
0x140177d8f  mov     rax, [rax+10h]
0x140177d93  call    _guard_dispatch_icall
0x140177d98  nop
0x140177d99  mov     rcx, [rsp+0B8h+var_38]
0x140177da1  test    rcx, rcx
0x140177da4  jz      short loc_140177DB3
0x140177da6  mov     rax, [rcx]
0x140177da9  mov     rax, [rax+10h]
0x140177dad  call    _guard_dispatch_icall
0x140177db2  nop
0x140177db3  mov     rcx, [rsp+0B8h+var_40]
0x140177db8  test    rcx, rcx
0x140177dbb  jz      short loc_140177DCA
0x140177dbd  mov     rax, [rcx]
0x140177dc0  mov     rax, [rax+10h]
0x140177dc4  call    _guard_dispatch_icall
0x140177dc9  nop
0x140177dca  mov     rcx, rbx; bstrString
0x140177dcd  call    cs:__imp_SysFreeString
0x140177dd3  nop
0x140177dd4  mov     rcx, [rsp+0B8h+var_50]
0x140177dd9  test    rcx, rcx
0x140177ddc  jz      short loc_140177DEB
0x140177dde  mov     rax, [rcx]
0x140177de1  mov     rax, [rax+10h]
  ... truncated ...
```

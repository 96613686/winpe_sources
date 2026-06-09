# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180021150`
- end: `0x180021361`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
- size: `529`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x180002380`
- `0x18000282c`
- `0x180012024`
- `0x180013f54`
- `0x180021150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800212ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800212ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800212c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800212c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021273`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021273`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002127e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002127e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021293`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002126b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002126b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180021246`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180021246`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002130d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002130d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::StartGetValueAsyncWork(
        volatile __int32 *a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v4; // r13
  int result; // eax
  char *v7; // rax
  char *v8; // rdi
  HRESULT v9; // r12d
  __int64 v10; // rcx
  __int64 v11; // rcx
  char *v12; // rbp
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  HMODULE v15; // r12
  HMODULE v16; // rbp
  DWORD v17; // ebx
  bool v18; // sf
  HMODULE *v19; // [rsp+20h] [rbp-68h]
  HMODULE phModule; // [rsp+28h] [rbp-60h] BYREF
  char v21; // [rsp+30h] [rbp-58h]

  v4 = a2;
  result = _InterlockedExchange(a1 + 56, 1);
  if ( !result )
  {
    LOBYTE(a2) = 1;
    (*(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a3 + 168LL))(a3, a2);
    v7 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(
               a1,
               a3,
               v4);
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 5) = 0;
    v9 = 0;
    if ( a3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
      v10 = *((_QWORD *)v8 + 1);
      *((_QWORD *)v8 + 1) = a3;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( *(volatile __int32 **)v8 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(volatile __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
      v11 = *(_QWORD *)v8;
      *(_QWORD *)v8 = a1;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    *((_QWORD *)v8 + 4) = 0;
    if ( v4 )
      v9 = SHStrDupW(v4, (LPWSTR *)v8 + 2);
    v12 = (char *)*((_QWORD *)v8 + 3);
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v12);
      SetLastError(LastError);
    }
    *((_QWORD *)v8 + 3) = 0;
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)v8 + 3);
    if ( v9 < 0 )
      goto LABEL_24;
    v19 = (HMODULE *)(v8 + 40);
    phModule = 0;
    v21 = 1;
    GetModuleHandleExW(
      4u,
      (LPCWSTR)SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::s_GetValueAsyncThread,
      &phModule);
    if ( v21 )
    {
      v15 = phModule;
      v16 = *v19;
      if ( *v19 )
      {
        v17 = GetLastError();
        FreeLibrary(v16);
        SetLastError(v17);
      }
      *v19 = v15;
    }
    result = QueueUserWorkItem(
               SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::s_GetValueAsyncThread,
               v8,
               0);
    if ( !result )
    {
      result = GetLastError();
      v18 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v18 = result < 0;
      }
      if ( v18 )
      {
LABEL_24:
        SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(v8);
        operator delete(v8);
        return SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(
                 a1,
                 a3,
                 v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021150  push    rbx
0x180021152  push    rbp
0x180021153  push    rsi
0x180021154  push    rdi
0x180021155  push    r12
0x180021157  push    r13
0x180021159  push    r14
0x18002115b  push    r15
0x18002115d  sub     rsp, 48h
0x180021161  mov     r15, r8
0x180021164  mov     r13, rdx
0x180021167  mov     rsi, rcx
0x18002116a  mov     eax, 1
0x18002116f  xchg    eax, [rcx+0E0h]
0x180021175  xor     ebx, ebx
0x180021177  test    eax, eax
0x180021179  jnz     loc_180021350
0x18002117f  mov     rax, [r8]
0x180021182  mov     dl, 1
0x180021184  mov     rcx, r8
0x180021187  mov     rax, [rax+0A8h]
0x18002118e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021193  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002119a  lea     ecx, [rbx+30h]; unsigned __int64
0x18002119d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800211a2  mov     rdi, rax
0x1800211a5  mov     [rsp+88h+arg_0], rax
0x1800211ad  test    rax, rax
0x1800211b0  jz      loc_180021342
0x1800211b6  mov     [rax], rbx
0x1800211b9  mov     [rax+8], rbx
0x1800211bd  mov     [rax+10h], rbx
0x1800211c1  mov     [rax+18h], rbx
0x1800211c5  mov     [rax+28h], rbx
0x1800211c9  test    rax, rax
0x1800211cc  jz      loc_180021342
0x1800211d2  mov     r12d, ebx
0x1800211d5  cmp     rbx, r15
0x1800211d8  jz      short loc_180021204
0x1800211da  mov     rax, [r15]
0x1800211dd  mov     rcx, r15
0x1800211e0  mov     rax, [rax+8]
0x1800211e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211e9  nop
0x1800211ea  mov     rcx, [rdi+8]
0x1800211ee  mov     [rdi+8], r15
0x1800211f2  test    rcx, rcx
0x1800211f5  jz      short loc_180021204
0x1800211f7  mov     rax, [rcx]
0x1800211fa  mov     rax, [rax+10h]
0x1800211fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021203  nop
0x180021204  cmp     [rdi], rsi
0x180021207  jz      short loc_180021236
0x180021209  test    rsi, rsi
0x18002120c  jz      short loc_18002121E
0x18002120e  mov     rax, [rsi]
0x180021211  mov     rcx, rsi
0x180021214  mov     rax, [rax+8]
0x180021218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002121d  nop
0x18002121e  mov     rcx, [rdi]
0x180021221  mov     [rdi], rsi
0x180021224  test    rcx, rcx
0x180021227  jz      short loc_180021236
0x180021229  mov     rax, [rcx]
0x18002122c  mov     rax, [rax+10h]
0x180021230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021235  nop
0x180021236  mov     [rdi+20h], rbx
0x18002123a  test    r13, r13
0x18002123d  jz      short loc_18002124F
0x18002123f  lea     rdx, [rdi+10h]; ppwsz
0x180021243  mov     rcx, r13; psz
0x180021246  call    cs:__imp_SHStrDupW
0x18002124c  mov     r12d, eax
0x18002124f  lea     r14, [rdi+18h]
0x180021253  mov     rbp, [r14]
0x180021256  lea     rdx, [rbp-1]
0x18002125a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002125e  ja      short loc_18002127B
0x180021260  call    cs:__imp_GetLastError
0x180021266  mov     ebx, eax
0x180021268  mov     rcx, rbp; hObject
0x18002126b  call    cs:__imp_CloseHandle
0x180021271  mov     ecx, ebx; dwErrCode
0x180021273  call    cs:__imp_SetLastError
0x180021279  xor     ebx, ebx
0x18002127b  mov     [r14], rbx
0x18002127e  call    cs:__imp_GetCurrentThread
0x180021284  mov     r9, r14; TokenHandle
0x180021287  mov     edx, 0Ch; DesiredAccess
0x18002128c  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180021290  mov     rcx, rax; ThreadHandle
0x180021293  call    cs:__imp_OpenThreadToken
0x180021299  test    r12d, r12d
0x18002129c  js      loc_18002132D
0x1800212a2  lea     rax, [rdi+28h]
0x1800212a6  mov     [rsp+88h+var_68], rax
0x1800212ab  mov     [rsp+88h+phModule], rbx
0x1800212b0  mov     [rsp+88h+var_58], 1
0x1800212b5  lea     r8, [rsp+88h+phModule]; phModule
0x1800212ba  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x1800212c1  mov     ecx, 4; dwFlags
0x1800212c6  call    cs:__imp_GetModuleHandleExW
0x1800212cc  cmp     [rsp+88h+var_58], bl
0x1800212d0  jz      short loc_180021300
0x1800212d2  mov     r12, [rsp+88h+phModule]
0x1800212d7  mov     r14, [rsp+88h+var_68]
0x1800212dc  mov     rbp, [r14]
0x1800212df  test    rbp, rbp
0x1800212e2  jz      short loc_1800212FD
0x1800212e4  call    cs:__imp_GetLastError
0x1800212ea  mov     ebx, eax
0x1800212ec  mov     rcx, rbp; hLibModule
0x1800212ef  call    cs:__imp_FreeLibrary
0x1800212f5  mov     ecx, ebx; dwErrCode
0x1800212f7  call    cs:__imp_SetLastError
0x1800212fd  mov     [r14], r12
0x180021300  xor     r8d, r8d; Flags
0x180021303  mov     rdx, rdi; Context
0x180021306  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18002130d  call    cs:__imp_QueueUserWorkItem
0x180021313  test    eax, eax
0x180021315  jnz     short loc_180021350
0x180021317  call    cs:__imp_GetLastError
0x18002131d  test    eax, eax
0x18002131f  jle     short loc_18002132B
0x180021321  movzx   eax, ax
0x180021324  or      eax, 80070000h
0x180021329  test    eax, eax
0x18002132b  jns     short loc_180021350
0x18002132d  mov     rcx, rdi
0x180021330  call    ??1ASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(void)
0x180021335  mov     edx, 30h ; '0'
0x18002133a  mov     rcx, rdi; Block
0x18002133d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021342  mov     r8, r13
0x180021345  mov     rdx, r15
0x180021348  mov     rcx, rsi
0x18002134b  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x180021350  add     rsp, 48h
0x180021354  pop     r15
0x180021356  pop     r14
0x180021358  pop     r13
0x18002135a  pop     r12
0x18002135c  pop     rdi
0x18002135d  pop     rsi
0x18002135e  pop     rbp
0x18002135f  pop     rbx
0x180021360  retn
```

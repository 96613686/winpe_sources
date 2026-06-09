# SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::StartGetValueAsyncWork(ushort const *,SystemSettings::DataModel::CSettingBase *)

- ea: `0x180021370`
- end: `0x180021581`
- name: `?StartGetValueAsyncWork@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEBGPEAVCSettingBase@23@@Z`
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
- `0x180021370`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002150f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002150f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800214e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800214e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021517`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002149e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002149e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800214b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800214b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002148b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002148b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180021466`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180021466`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002152d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18002152d`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::StartGetValueAsyncWork(
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
  result = _InterlockedExchange(a1 + 52, 1);
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
0x180021370  push    rbx
0x180021372  push    rbp
0x180021373  push    rsi
0x180021374  push    rdi
0x180021375  push    r12
0x180021377  push    r13
0x180021379  push    r14
0x18002137b  push    r15
0x18002137d  sub     rsp, 48h
0x180021381  mov     r15, r8
0x180021384  mov     r13, rdx
0x180021387  mov     rsi, rcx
0x18002138a  mov     eax, 1
0x18002138f  xchg    eax, [rcx+0D0h]
0x180021395  xor     ebx, ebx
0x180021397  test    eax, eax
0x180021399  jnz     loc_180021570
0x18002139f  mov     rax, [r8]
0x1800213a2  mov     dl, 1
0x1800213a4  mov     rcx, r8
0x1800213a7  mov     rax, [rax+0A8h]
0x1800213ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800213ba  lea     ecx, [rbx+30h]; unsigned __int64
0x1800213bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800213c2  mov     rdi, rax
0x1800213c5  mov     [rsp+88h+arg_0], rax
0x1800213cd  test    rax, rax
0x1800213d0  jz      loc_180021562
0x1800213d6  mov     [rax], rbx
0x1800213d9  mov     [rax+8], rbx
0x1800213dd  mov     [rax+10h], rbx
0x1800213e1  mov     [rax+18h], rbx
0x1800213e5  mov     [rax+28h], rbx
0x1800213e9  test    rax, rax
0x1800213ec  jz      loc_180021562
0x1800213f2  mov     r12d, ebx
0x1800213f5  cmp     rbx, r15
0x1800213f8  jz      short loc_180021424
0x1800213fa  mov     rax, [r15]
0x1800213fd  mov     rcx, r15
0x180021400  mov     rax, [rax+8]
0x180021404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021409  nop
0x18002140a  mov     rcx, [rdi+8]
0x18002140e  mov     [rdi+8], r15
0x180021412  test    rcx, rcx
0x180021415  jz      short loc_180021424
0x180021417  mov     rax, [rcx]
0x18002141a  mov     rax, [rax+10h]
0x18002141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021423  nop
0x180021424  cmp     [rdi], rsi
0x180021427  jz      short loc_180021456
0x180021429  test    rsi, rsi
0x18002142c  jz      short loc_18002143E
0x18002142e  mov     rax, [rsi]
0x180021431  mov     rcx, rsi
0x180021434  mov     rax, [rax+8]
0x180021438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002143d  nop
0x18002143e  mov     rcx, [rdi]
0x180021441  mov     [rdi], rsi
0x180021444  test    rcx, rcx
0x180021447  jz      short loc_180021456
0x180021449  mov     rax, [rcx]
0x18002144c  mov     rax, [rax+10h]
0x180021450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021455  nop
0x180021456  mov     [rdi+20h], rbx
0x18002145a  test    r13, r13
0x18002145d  jz      short loc_18002146F
0x18002145f  lea     rdx, [rdi+10h]; ppwsz
0x180021463  mov     rcx, r13; psz
0x180021466  call    cs:__imp_SHStrDupW
0x18002146c  mov     r12d, eax
0x18002146f  lea     r14, [rdi+18h]
0x180021473  mov     rbp, [r14]
0x180021476  lea     rdx, [rbp-1]
0x18002147a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002147e  ja      short loc_18002149B
0x180021480  call    cs:__imp_GetLastError
0x180021486  mov     ebx, eax
0x180021488  mov     rcx, rbp; hObject
0x18002148b  call    cs:__imp_CloseHandle
0x180021491  mov     ecx, ebx; dwErrCode
0x180021493  call    cs:__imp_SetLastError
0x180021499  xor     ebx, ebx
0x18002149b  mov     [r14], rbx
0x18002149e  call    cs:__imp_GetCurrentThread
0x1800214a4  mov     r9, r14; TokenHandle
0x1800214a7  mov     edx, 0Ch; DesiredAccess
0x1800214ac  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800214b0  mov     rcx, rax; ThreadHandle
0x1800214b3  call    cs:__imp_OpenThreadToken
0x1800214b9  test    r12d, r12d
0x1800214bc  js      loc_18002154D
0x1800214c2  lea     rax, [rdi+28h]
0x1800214c6  mov     [rsp+88h+var_68], rax
0x1800214cb  mov     [rsp+88h+phModule], rbx
0x1800214d0  mov     [rsp+88h+var_58], 1
0x1800214d5  lea     r8, [rsp+88h+phModule]; phModule
0x1800214da  lea     rdx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpModuleName
0x1800214e1  mov     ecx, 4; dwFlags
0x1800214e6  call    cs:__imp_GetModuleHandleExW
0x1800214ec  cmp     [rsp+88h+var_58], bl
0x1800214f0  jz      short loc_180021520
0x1800214f2  mov     r12, [rsp+88h+phModule]
0x1800214f7  mov     r14, [rsp+88h+var_68]
0x1800214fc  mov     rbp, [r14]
0x1800214ff  test    rbp, rbp
0x180021502  jz      short loc_18002151D
0x180021504  call    cs:__imp_GetLastError
0x18002150a  mov     ebx, eax
0x18002150c  mov     rcx, rbp; hLibModule
0x18002150f  call    cs:__imp_FreeLibrary
0x180021515  mov     ecx, ebx; dwErrCode
0x180021517  call    cs:__imp_SetLastError
0x18002151d  mov     [r14], r12
0x180021520  xor     r8d, r8d; Flags
0x180021523  mov     rdx, rdi; Context
0x180021526  lea     rcx, ?s_GetValueAsyncThread@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; Function
0x18002152d  call    cs:__imp_QueueUserWorkItem
0x180021533  test    eax, eax
0x180021535  jnz     short loc_180021570
0x180021537  call    cs:__imp_GetLastError
0x18002153d  test    eax, eax
0x18002153f  jle     short loc_18002154B
0x180021541  movzx   eax, ax
0x180021544  or      eax, 80070000h
0x180021549  test    eax, eax
0x18002154b  jns     short loc_180021570
0x18002154d  mov     rcx, rdi
0x180021550  call    ??1ASYNC_PARAMS@?$CGetValueAsyncHelper@VCCollectionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA@XZ; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CCollectionSetting>::ASYNC_PARAMS::~ASYNC_PARAMS(void)
0x180021555  mov     edx, 30h ; '0'
0x18002155a  mov     rcx, rdi; Block
0x18002155d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021562  mov     r8, r13
0x180021565  mov     rdx, r15
0x180021568  mov     rcx, rsi
0x18002156b  call    ?DoAsyncWorkInternal@?$CGetValueAsyncHelper@VCLabeledStringSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@PEBG@Z; SystemSettings::DataModel::CGetValueAsyncHelper<SystemSettings::DataModel::CLabeledStringSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *,ushort const *)
0x180021570  add     rsp, 48h
0x180021574  pop     r15
0x180021576  pop     r14
0x180021578  pop     r13
0x18002157a  pop     r12
0x18002157c  pop     rdi
0x18002157d  pop     rsi
0x18002157e  pop     rbp
0x18002157f  pop     rbx
0x180021580  retn
```

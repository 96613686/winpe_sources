# RegistryOwnershipManager::~RegistryOwnershipManager(void)

- ea: `0x180114720`
- end: `0x180114907`
- name: `??1RegistryOwnershipManager@@QEAA@XZ`
- size: `487`
- prototype: `void __fastcall(RegistryOwnershipManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801158d0`
- `0x1801ad8d2`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x18003de70`
- `0x1800fdd8c`
- `0x1801145a8`
- `0x180114720`
- `0x1801152d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801147e9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801147e9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801148b8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801148ce`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801148b8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801148ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011480d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011480d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114854`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180114873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180114873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801148ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801148ec`

## string_xrefs

- `0x18011473b`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryOwnershipManager::~RegistryOwnershipManager(RegistryOwnershipManager *this)
{
  char *v2; // r15
  const struct RegistryOwnershipManager::OriginalSecurityInfo *v3; // rdi
  const struct RegistryOwnershipManager::OriginalSecurityInfo *v4; // rbx
  int v5; // eax
  char *v6; // rdi
  char *v7; // rbx
  struct _TOKEN_PRIVILEGES *v8; // r8
  HANDLE *v9; // rdi
  const char *v10; // r9
  HANDLE v11; // rbp
  DWORD LastError; // ebx
  void *v13; // rcx
  void *v14; // rcx
  int PreviousState; // [rsp+20h] [rbp-48h]
  int PreviousStatea; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (char *)this + 56;
  v3 = (const struct RegistryOwnershipManager::OriginalSecurityInfo *)*((_QWORD *)this + 8);
  v4 = (const struct RegistryOwnershipManager::OriginalSecurityInfo *)*((_QWORD *)this + 7);
  if ( v4 != v3 )
  {
    do
    {
      v5 = RegistryOwnershipManager::RestoreSecurityInfo((HKEY *)this, v4);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
          (const char *)(unsigned int)v5,
          PreviousState);
        goto LABEL_8;
      }
      v4 = (const struct RegistryOwnershipManager::OriginalSecurityInfo *)((char *)v4 + 80);
    }
    while ( v4 != v3 );
    v6 = (char *)*((_QWORD *)v2 + 1);
    v7 = *(char **)v2;
    if ( *(char **)v2 != v6 )
    {
      do
      {
        std::vector<unsigned char>::~vector<unsigned char>(v7 + 56);
        std::vector<unsigned char>::~vector<unsigned char>(v7 + 32);
        std::wstring::~wstring(v7);
        v7 += 80;
      }
      while ( v7 != v6 );
      *((_QWORD *)v2 + 1) = *(_QWORD *)v2;
    }
  }
LABEL_8:
  v8 = (struct _TOKEN_PRIVILEGES *)*((_QWORD *)this + 10);
  v9 = (HANDLE *)((char *)this + 104);
  if ( v8 != *((struct _TOKEN_PRIVILEGES **)this + 11) && (char *)*v9 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( AdjustTokenPrivileges(*v9, 0, v8, 0, 0, 0) )
    {
      if ( GetLastError() == 1300 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
          (const char *)0x80070514LL,
          PreviousStatea);
      }
      else
      {
        if ( *((_QWORD *)this + 10) != *((_QWORD *)this + 11) )
          *((_QWORD *)this + 11) = *((_QWORD *)this + 10);
        v11 = *v9;
        if ( (char *)*v9 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v11);
          SetLastError(LastError);
        }
        *v9 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
        v10);
    }
  }
  if ( (char *)*v9 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*v9);
  std::vector<unsigned char>::~vector<unsigned char>((char *)this + 80);
  std::vector<RegistryOwnershipManager::OriginalSecurityInfo>::~vector<RegistryOwnershipManager::OriginalSecurityInfo>(v2);
  v13 = (void *)*((_QWORD *)this + 6);
  if ( v13 )
    FreeSid(v13);
  v14 = (void *)*((_QWORD *)this + 5);
  if ( v14 )
    FreeSid(v14);
  std::wstring::~wstring((char *)this + 8);
  if ( *(_QWORD *)this )
    RegCloseKey(*(HKEY *)this);
}

```

## disassembly

```asm
0x180114720  push    rbx
0x180114722  push    rbp
0x180114723  push    rsi
0x180114724  push    rdi
0x180114725  push    r14
0x180114727  push    r15
0x180114729  sub     rsp, 38h
0x18011472d  mov     rsi, rcx
0x180114730  lea     r15, [rcx+38h]
0x180114734  mov     rdi, [r15+8]
0x180114738  mov     rbx, [r15]
0x18011473b  lea     rbp, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180114742  cmp     rbx, rdi
0x180114745  jz      short loc_1801147AC
0x180114747  mov     rdx, rbx; struct RegistryOwnershipManager::OriginalSecurityInfo *
0x18011474a  mov     rcx, rsi; this
0x18011474d  call    ?RestoreSecurityInfo@RegistryOwnershipManager@@AEAAJAEBUOriginalSecurityInfo@1@@Z; RegistryOwnershipManager::RestoreSecurityInfo(RegistryOwnershipManager::OriginalSecurityInfo const &)
0x180114752  test    eax, eax
0x180114754  js      short loc_180114797
0x180114756  add     rbx, 50h ; 'P'
0x18011475a  cmp     rbx, rdi
0x18011475d  jnz     short loc_180114747
0x18011475f  mov     rdi, [r15+8]
0x180114763  mov     rbx, [r15]
0x180114766  cmp     rbx, rdi
0x180114769  jz      short loc_1801147AC
0x18011476b  lea     rcx, [rbx+38h]
0x18011476f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180114774  lea     rcx, [rbx+20h]
0x180114778  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18011477d  mov     rcx, rbx; void *
0x180114780  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180114785  add     rbx, 50h ; 'P'
0x180114789  cmp     rbx, rdi
0x18011478c  jnz     short loc_18011476B
0x18011478e  mov     rax, [r15]
0x180114791  mov     [r15+8], rax
0x180114795  jmp     short loc_1801147AC
0x180114797  mov     rcx, [rsp+68h]; this
0x18011479c  mov     r9d, eax; char *
0x18011479f  mov     r8, rbp; unsigned int
0x1801147a2  mov     edx, 0DEh; void *
0x1801147a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801147ac  lea     r14, [rsi+50h]
0x1801147b0  mov     r8, [r14]; NewState
0x1801147b3  lea     rdi, [rsi+68h]
0x1801147b7  cmp     r8, [r14+8]
0x1801147bb  jz      loc_180114886
0x1801147c1  mov     rcx, [rdi]; TokenHandle
0x1801147c4  lea     rax, [rcx-1]
0x1801147c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801147cc  ja      loc_180114886
0x1801147d2  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x1801147db  mov     [rsp+68h+PreviousState], 0; int
0x1801147e4  xor     r9d, r9d; BufferLength
0x1801147e7  xor     edx, edx; DisableAllPrivileges
0x1801147e9  call    cs:__imp_AdjustTokenPrivileges
0x1801147f0  nop     dword ptr [rax+rax+00h]
0x1801147f5  test    eax, eax
0x1801147f7  jnz     short loc_18011480D
0x1801147f9  mov     rcx, [rsp+68h]; this
0x1801147fe  mov     r8, rbp; unsigned int
0x180114801  mov     edx, 0EFh; void *
0x180114806  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011480b  jmp     short loc_180114886
0x18011480d  call    cs:__imp_GetLastError
0x180114814  nop     dword ptr [rax+rax+00h]
0x180114819  cmp     eax, 514h
0x18011481e  jnz     short loc_18011483A
0x180114820  mov     rcx, [rsp+68h]; this
0x180114825  mov     r9d, 80070514h; char *
0x18011482b  mov     r8, rbp; unsigned int
0x18011482e  mov     edx, 0F3h; void *
0x180114833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114838  jmp     short loc_180114886
0x18011483a  mov     rax, [r14]
0x18011483d  cmp     rax, [r14+8]
0x180114841  jz      short loc_180114847
0x180114843  mov     [r14+8], rax
0x180114847  mov     rbp, [rdi]
0x18011484a  lea     rax, [rbp-1]
0x18011484e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180114852  ja      short loc_18011487F
0x180114854  call    cs:__imp_GetLastError
0x18011485b  nop     dword ptr [rax+rax+00h]
0x180114860  mov     ebx, eax
0x180114862  mov     rcx, rbp; hObject
0x180114865  call    cs:__imp_CloseHandle
0x18011486c  nop     dword ptr [rax+rax+00h]
0x180114871  mov     ecx, ebx; dwErrCode
0x180114873  call    cs:__imp_SetLastError
0x18011487a  nop     dword ptr [rax+rax+00h]
0x18011487f  mov     qword ptr [rdi], 0
0x180114886  mov     rcx, [rdi]; hObject
0x180114889  lea     rax, [rcx-1]
0x18011488d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180114891  ja      short loc_18011489F
0x180114893  call    cs:__imp_CloseHandle
0x18011489a  nop     dword ptr [rax+rax+00h]
0x18011489f  mov     rcx, r14
0x1801148a2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1801148a7  mov     rcx, r15
0x1801148aa  call    ??1?$vector@UOriginalSecurityInfo@RegistryOwnershipManager@@V?$allocator@UOriginalSecurityInfo@RegistryOwnershipManager@@@std@@@std@@QEAA@XZ; std::vector<RegistryOwnershipManager::OriginalSecurityInfo>::~vector<RegistryOwnershipManager::OriginalSecurityInfo>(void)
0x1801148af  mov     rcx, [rsi+30h]; pSid
0x1801148b3  test    rcx, rcx
0x1801148b6  jz      short loc_1801148C5
0x1801148b8  call    cs:__imp_FreeSid
0x1801148bf  nop     dword ptr [rax+rax+00h]
0x1801148c4  nop
0x1801148c5  mov     rcx, [rsi+28h]; pSid
0x1801148c9  test    rcx, rcx
0x1801148cc  jz      short loc_1801148DB
0x1801148ce  call    cs:__imp_FreeSid
0x1801148d5  nop     dword ptr [rax+rax+00h]
0x1801148da  nop
0x1801148db  lea     rcx, [rsi+8]; void *
0x1801148df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801148e4  mov     rcx, [rsi]; hKey
0x1801148e7  test    rcx, rcx
0x1801148ea  jz      short loc_1801148F9
0x1801148ec  call    cs:__imp_RegCloseKey
0x1801148f3  nop     dword ptr [rax+rax+00h]
0x1801148f8  nop
0x1801148f9  add     rsp, 38h
0x1801148fd  pop     r15
0x1801148ff  pop     r14
0x180114901  pop     rdi
0x180114902  pop     rsi
0x180114903  pop     rbp
0x180114904  pop     rbx
0x180114905  retn
```

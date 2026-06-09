# DeviceCastle::Service::DeviceCastleService::GestureDescriptionText(void)

- ea: `0x180066030`
- end: `0x18006619b`
- name: `?GestureDescriptionText@DeviceCastleService@Service@DeviceCastle@@UEAAPEBGXZ`
- size: `363`
- prototype: `const unsigned __int16 *__fastcall(DeviceCastle::Service::DeviceCastleService *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004984`
- `0x1800049a0`
- `0x18000d4ec`
- `0x180066030`
- `0x18008b820`
- `0x18008b8b4`
- `0x18008c140`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800660dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006616a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800660dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006616a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800660e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800660e5`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180066082`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180066082`

## string_xrefs

- `0x18006610d`: `Failed to get the UI Policy Description string from the SEMgrSvc resource dll.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall DeviceCastle::Service::DeviceCastleService::GestureDescriptionText(
        DeviceCastle::Service::DeviceCastleService *this)
{
  unsigned __int16 **v2; // rsi
  const unsigned __int16 *v3; // rcx
  const unsigned __int16 *v4; // r8
  WCHAR *v5; // rdi
  const char *v6; // r9
  unsigned __int16 *v7; // rbp
  DWORD LastError; // ebx
  PriHelper *v9; // rbx
  PWSTR ppszPath[2]; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v12[264]; // [rsp+30h] [rbp-238h] BYREF

  v2 = (unsigned __int16 **)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    ppszPath[0] = 0;
    if ( SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, ppszPath) >= 0
      && (int)StringCchPrintfW(v12, 0x104u, L"%s\\SystemResources\\Windows-NFC-SEManagement", ppszPath[0]) >= 0 )
    {
      v5 = (WCHAR *)PriHelper::Create(v3, v12, v4);
      ppszPath[1] = v5;
      if ( v5 )
      {
        v7 = *v2;
        if ( *v2 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v7);
          SetLastError(LastError);
        }
        *v2 = 0;
        if ( !(unsigned int)PriHelper::LoadStringW((PriHelper *)v5, 0xC8u, v2, v6) )
          (*(void (__fastcall **)(char *, __int64, const wchar_t *))(*((_QWORD *)this + 1) + 8LL))(
            (char *)this + 8,
            4,
            L"Failed to get the UI Policy Description string from the SEMgrSvc resource dll.");
        v9 = (PriHelper *)v5;
      }
      else
      {
        (*(void (__fastcall **)(char *, __int64, const wchar_t *))(*((_QWORD *)this + 1) + 8LL))(
          (char *)this + 8,
          4,
          L"Failed to load the SEMgrSvc resource pri.");
        v9 = 0;
      }
      if ( v5 && v9 )
      {
        PriHelper::~PriHelper(v9);
        operator delete(v9);
      }
    }
    if ( ppszPath[0] )
      CoTaskMemFree(ppszPath[0]);
  }
  return *v2;
}

```

## disassembly

```asm
0x180066030  mov     [rsp+arg_8], rbx
0x180066035  mov     [rsp+arg_10], rbp
0x18006603a  push    rsi
0x18006603b  push    rdi
0x18006603c  push    r14
0x18006603e  sub     rsp, 250h
0x180066045  mov     rax, cs:__security_cookie
0x18006604c  xor     rax, rsp
0x18006604f  mov     [rsp+268h+var_28], rax
0x180066057  mov     r14, rcx
0x18006605a  lea     rsi, [rcx+28h]
0x18006605e  cmp     qword ptr [rsi], 0
0x180066062  jnz     loc_180066170
0x180066068  mov     [rsp+268h+ppszPath], 0
0x180066071  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x180066076  xor     r8d, r8d; hToken
0x180066079  xor     edx, edx; dwFlags
0x18006607b  lea     rcx, FOLDERID_Windows; rfid
0x180066082  call    cs:__imp_SHGetKnownFolderPath
0x180066088  test    eax, eax
0x18006608a  js      loc_180066160
0x180066090  mov     r9, [rsp+268h+ppszPath]
0x180066095  lea     r8, aSSystemresourc; "%s\\SystemResources\\Windows-NFC-SEMana"...
0x18006609c  mov     edx, 104h; unsigned __int64
0x1800660a1  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1800660a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800660ab  test    eax, eax
0x1800660ad  js      loc_180066160
0x1800660b3  lea     rdx, [rsp+268h+var_238]; unsigned __int16 *
0x1800660b8  call    ?Create@PriHelper@@SAPEAV1@PEBG00@Z; PriHelper::Create(ushort const *,ushort const *,ushort const *)
0x1800660bd  mov     rdi, rax
0x1800660c0  mov     [rsp+268h+var_240], rax
0x1800660c5  test    rax, rax
0x1800660c8  jz      short loc_180066127
0x1800660ca  mov     rbp, [rsi]
0x1800660cd  test    rbp, rbp
0x1800660d0  jz      short loc_1800660EB
0x1800660d2  call    cs:__imp_GetLastError
0x1800660d8  mov     ebx, eax
0x1800660da  mov     rcx, rbp; pv
0x1800660dd  call    cs:__imp_CoTaskMemFree
0x1800660e3  mov     ecx, ebx; dwErrCode
0x1800660e5  call    cs:__imp_SetLastError
0x1800660eb  mov     qword ptr [rsi], 0
0x1800660f2  mov     r8, rsi; unsigned __int16 *
0x1800660f5  mov     edx, 0C8h; unsigned int
0x1800660fa  mov     rcx, rdi; this
0x1800660fd  call    ?LoadStringW@PriHelper@@QEAAHIPEAGH@Z; PriHelper::LoadStringW(uint,ushort *,int)
0x180066102  test    eax, eax
0x180066104  jnz     short loc_180066122
0x180066106  lea     rcx, [r14+8]
0x18006610a  mov     rax, [rcx]
0x18006610d  lea     r8, aFailedToGetThe; "Failed to get the UI Policy Description"...
0x180066114  mov     edx, 4
0x180066119  mov     rax, [rax+8]
0x18006611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066122  mov     rbx, rdi
0x180066125  jmp     short loc_180066145
0x180066127  lea     rcx, [r14+8]
0x18006612b  mov     rax, [rcx]
0x18006612e  lea     r8, aFailedToLoadTh; "Failed to load the SEMgrSvc resource pr"...
0x180066135  mov     edx, 4
0x18006613a  mov     rax, [rax+8]
0x18006613e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066143  xor     ebx, ebx
0x180066145  test    rdi, rdi
0x180066148  jz      short loc_180066160
0x18006614a  test    rbx, rbx
0x18006614d  jz      short loc_180066160
0x18006614f  mov     rcx, rbx; this
0x180066152  call    ??1PriHelper@@QEAA@XZ; PriHelper::~PriHelper(void)
0x180066157  mov     rcx, rbx; Block
0x18006615a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006615f  nop
0x180066160  mov     rcx, [rsp+268h+ppszPath]; pv
0x180066165  test    rcx, rcx
0x180066168  jz      short loc_180066170
0x18006616a  call    cs:__imp_CoTaskMemFree
0x180066170  mov     rax, [rsi]
0x180066173  mov     rcx, [rsp+268h+var_28]
0x18006617b  xor     rcx, rsp; StackCookie
0x18006617e  call    __security_check_cookie
0x180066183  lea     r11, [rsp+268h+var_18]
0x18006618b  mov     rbx, [r11+28h]
0x18006618f  mov     rbp, [r11+30h]
0x180066193  mov     rsp, r11
0x180066196  pop     r14
0x180066198  pop     rdi
0x180066199  pop     rsi
0x18006619a  retn
```

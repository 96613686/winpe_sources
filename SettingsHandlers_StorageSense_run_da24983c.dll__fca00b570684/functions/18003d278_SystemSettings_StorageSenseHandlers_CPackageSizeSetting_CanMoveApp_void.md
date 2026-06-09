# SystemSettings::StorageSenseHandlers::CPackageSizeSetting::CanMoveApp(void)

- ea: `0x18003d278`
- end: `0x18003d366`
- name: `?CanMoveApp@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAEXZ`
- size: `238`
- prototype: `unsigned __int8 __fastcall(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180041650`

## callees

- `0x18003d278`
- `0x180043f9c`
- `0x1800b33a4`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d34d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d2ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d34d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d311`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18003d320`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatusForUser` at `0x18003d320`
- `AppXAllUserStore!IsNonInboxAllUserPackage` at `0x18003d300`
- `AppXAllUserStore!IsNonInboxAllUserPackage` at `0x18003d300`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall SystemSettings::StorageSenseHandlers::CPackageSizeSetting::CanMoveApp(
        SystemSettings::StorageSenseHandlers::CPackageSizeSetting *this)
{
  int v2; // edi
  __int64 (__fastcall *v3)(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *); // rbx
  int v4; // esi
  PCWSTR StringRawBuffer; // rax
  PCWSTR v6; // rax
  char v7; // bl
  int v9; // [rsp+40h] [rbp+20h] BYREF
  int v10; // [rsp+48h] [rbp+28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF

  if ( *((_BYTE *)this + 248)
    || !SystemSettings::StorageSenseHandlers::ExecutionHelpers::CanMoveApps(this)
    || SystemSettings::StorageSenseHandlers::CPackageSizeSetting::IsLanguageExperiencePack(this) )
  {
    return 0;
  }
  string = 0;
  v10 = 0;
  v2 = 0;
  v3 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *))(*(_QWORD *)this + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = v3(this, &string);
  if ( v4 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v4 = IsNonInboxAllUserPackage(StringRawBuffer, &v10);
  }
  v9 = 0;
  v6 = WindowsGetStringRawBuffer(string, 0);
  v7 = 1;
  if ( !(unsigned int)GetPackageStatusForUser(0, v6, &v9) && (v9 & 0x810BA) != 0 )
    v2 = 1;
  if ( v4 < 0 || v10 || v2 )
    v7 = 0;
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18003d278  mov     [rsp-18h+arg_18], rbx
0x18003d27d  push    rbp
0x18003d27e  push    rsi
0x18003d27f  push    rdi
0x18003d280  mov     rbp, rsp
0x18003d283  sub     rsp, 20h
0x18003d287  mov     rsi, rcx
0x18003d28a  cmp     byte ptr [rcx+0F8h], 0
0x18003d291  jnz     loc_18003D357
0x18003d297  call    ?CanMoveApps@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YA_NXZ; SystemSettings::StorageSenseHandlers::ExecutionHelpers::CanMoveApps(void)
0x18003d29c  test    al, al
0x18003d29e  jz      loc_18003D357
0x18003d2a4  mov     rcx, rsi; this
0x18003d2a7  call    ?IsLanguageExperiencePack@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAEXZ; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::IsLanguageExperiencePack(void)
0x18003d2ac  test    al, al
0x18003d2ae  jnz     loc_18003D357
0x18003d2b4  mov     [rbp+string], 0
0x18003d2bc  mov     [rbp+arg_8], 0
0x18003d2c3  xor     edi, edi
0x18003d2c5  mov     rax, [rsi]
0x18003d2c8  mov     rbx, [rax+30h]
0x18003d2cc  xor     ecx, ecx; string
0x18003d2ce  call    cs:__imp_WindowsDeleteString
0x18003d2d4  mov     [rbp+string], rdi
0x18003d2d8  lea     rdx, [rbp+string]
0x18003d2dc  mov     rcx, rsi
0x18003d2df  mov     rax, rbx
0x18003d2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e7  mov     esi, eax
0x18003d2e9  test    eax, eax
0x18003d2eb  js      short loc_18003D308
0x18003d2ed  xor     edx, edx; length
0x18003d2ef  mov     rcx, [rbp+string]; string
0x18003d2f3  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d2f9  lea     rdx, [rbp+arg_8]
0x18003d2fd  mov     rcx, rax
0x18003d300  call    cs:__imp_IsNonInboxAllUserPackage
0x18003d306  mov     esi, eax
0x18003d308  mov     [rbp+arg_0], edi
0x18003d30b  xor     edx, edx; length
0x18003d30d  mov     rcx, [rbp+string]; string
0x18003d311  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d317  lea     r8, [rbp+arg_0]
0x18003d31b  mov     rdx, rax
0x18003d31e  xor     ecx, ecx
0x18003d320  call    cs:__imp_GetPackageStatusForUser
0x18003d326  mov     ebx, 1
0x18003d32b  test    eax, eax
0x18003d32d  jnz     short loc_18003D339
0x18003d32f  test    [rbp+arg_0], 810BAh
0x18003d336  cmovnz  edi, ebx
0x18003d339  test    esi, esi
0x18003d33b  js      short loc_18003D347
0x18003d33d  cmp     [rbp+arg_8], 0
0x18003d341  jnz     short loc_18003D347
0x18003d343  test    edi, edi
0x18003d345  jz      short loc_18003D349
0x18003d347  xor     bl, bl
0x18003d349  mov     rcx, [rbp+string]; string
0x18003d34d  call    cs:__imp_WindowsDeleteString
0x18003d353  mov     al, bl
0x18003d355  jmp     short loc_18003D359
0x18003d357  xor     al, al
0x18003d359  mov     rbx, [rsp+20h+arg_18]
0x18003d35e  add     rsp, 20h
0x18003d362  pop     rdi
0x18003d363  pop     rsi
0x18003d364  pop     rbp
0x18003d365  retn
```

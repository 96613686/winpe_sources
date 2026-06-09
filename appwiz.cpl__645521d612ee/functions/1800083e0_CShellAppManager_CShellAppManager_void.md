# CShellAppManager::~CShellAppManager(void)

- ea: `0x1800083e0`
- end: `0x1800084cd`
- name: `??1CShellAppManager@@MEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CShellAppManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800084e0`

## callees

- `0x1800083e0`
- `0x180056158`
- `0x18005620c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800084a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008458`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008458`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000842a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000842a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008440`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000844b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000844b`

## string_xrefs

- `0x18000841c`: `Software\Policies\Microsoft\Windows\Installer\Terminal Server`

## pseudocode

```c
void __fastcall CShellAppManager::~CShellAppManager(CShellAppManager *this)
{
  bool v1; // zf
  struct _DPA *v3; // rcx
  int v4; // edi
  PVOID Ptr; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 16) == 0;
  *(_QWORD *)this = &CShellAppManager::`vftable';
  if ( !v1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\Installer\\Terminal Server",
            0,
            2u,
            &hKey) )
    {
      RegDeleteValueW(hKey, L"EnableAdminRemote");
      RegCloseKey(hKey);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (struct _DPA *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    if ( *(int *)v3 > 0 )
    {
      v4 = 0;
      do
      {
        Ptr = DPA_GetPtr(v3, v4);
        if ( Ptr )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
        v3 = (struct _DPA *)*((_QWORD *)this + 2);
        ++v4;
      }
      while ( v4 < *(_DWORD *)v3 );
    }
    DPA_Destroy(v3);
    *((_QWORD *)this + 2) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x1800083e0  mov     r11, rsp
0x1800083e3  mov     [r11+10h], rbx
0x1800083e7  mov     [r11+18h], rsi
0x1800083eb  push    rdi
0x1800083ec  sub     rsp, 30h
0x1800083f0  cmp     dword ptr [rcx+40h], 0
0x1800083f4  lea     rax, ??_7CShellAppManager@@6B@; const CShellAppManager::`vftable'
0x1800083fb  mov     [rcx], rax
0x1800083fe  mov     rbx, rcx
0x180008401  jz      short loc_180008451
0x180008403  lea     rax, [r11+8]
0x180008407  mov     qword ptr [r11+8], 0
0x18000840f  mov     r9d, 2; samDesired
0x180008415  mov     [r11-18h], rax
0x180008419  xor     r8d, r8d; ulOptions
0x18000841c  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180008423  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000842a  call    cs:__imp_RegOpenKeyExW
0x180008430  test    eax, eax
0x180008432  jnz     short loc_180008451
0x180008434  mov     rcx, [rsp+38h+hKey]; hKey
0x180008439  lea     rdx, ValueName; "EnableAdminRemote"
0x180008440  call    cs:__imp_RegDeleteValueW
0x180008446  mov     rcx, [rsp+38h+hKey]; hKey
0x18000844b  call    cs:__imp_RegCloseKey
0x180008451  lea     rsi, [rbx+18h]
0x180008455  mov     rcx, rsi; lpCriticalSection
0x180008458  call    cs:__imp_EnterCriticalSection
0x18000845e  mov     rcx, [rbx+10h]; hdpa
0x180008462  test    rcx, rcx
0x180008465  jz      short loc_1800084A4
0x180008467  cmp     dword ptr [rcx], 0
0x18000846a  jle     short loc_180008497
0x18000846c  xor     edi, edi
0x18000846e  movsxd  rdx, edi; i
0x180008471  call    DPA_GetPtr
0x180008476  mov     rdx, rax
0x180008479  test    rax, rax
0x18000847c  jz      short loc_18000848D
0x18000847e  mov     rcx, [rax]
0x180008481  mov     rax, [rcx+10h]
0x180008485  mov     rcx, rdx
0x180008488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000848d  mov     rcx, [rbx+10h]; hdpa
0x180008491  inc     edi
0x180008493  cmp     edi, [rcx]
0x180008495  jl      short loc_18000846E
0x180008497  call    DPA_Destroy
0x18000849c  mov     qword ptr [rbx+10h], 0
0x1800084a4  mov     rcx, rsi; lpCriticalSection
0x1800084a7  call    cs:__imp_LeaveCriticalSection
0x1800084ad  mov     rcx, rsi; lpCriticalSection
0x1800084b0  call    cs:__imp_DeleteCriticalSection
0x1800084b6  lock dec cs:g_cRefThisDll
0x1800084bd  mov     rbx, [rsp+38h+arg_8]
0x1800084c2  mov     rsi, [rsp+38h+arg_10]
0x1800084c7  add     rsp, 30h
0x1800084cb  pop     rdi
0x1800084cc  retn
```

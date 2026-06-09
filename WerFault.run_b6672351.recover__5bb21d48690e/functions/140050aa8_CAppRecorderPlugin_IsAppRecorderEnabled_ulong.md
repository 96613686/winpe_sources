# CAppRecorderPlugin::IsAppRecorderEnabled(ulong)

- ea: `0x140050aa8`
- end: `0x140050bec`
- name: `?IsAppRecorderEnabled@CAppRecorderPlugin@@AEAAJK@Z`
- size: `324`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140050520`

## callees

- `0x140002748`
- `0x1400054e4`
- `0x140014f14`
- `0x140050aa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140050b8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140050b8c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140050b37`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140050b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140050bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140050bcd`

## string_xrefs

- `0x140050b7c`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::IsAppRecorderEnabled(CAppRecorderPlugin *this, unsigned int a2)
{
  int v3; // edi
  char *v4; // rbx
  LPCWSTR lpName[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v7[8]; // [rsp+50h] [rbp-10h] BYREF
  int pvData; // [rsp+80h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+30h] BYREF

  pcbData = 4;
  lpName[0] = v7;
  lpName[1] = v7;
  *((_QWORD *)this + 7) = 0;
  v7[0] = 0;
  pvData = 0;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpName,
         L"%d-AppRecorderEnabled",
         a2);
  if ( v3 >= 0 )
  {
    v4 = (char *)OpenEventW(0x100000u, 0, lpName[0]);
    if ( v4 != (char *)-1LL && v4 + 1 != (char *)1 )
      *((_DWORD *)this + 14) = 1;
    if ( !RegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder",
            L"AppRecorderEnabled",
            0x18u,
            0,
            &pvData,
            &pcbData) )
      *((_DWORD *)this + 15) = pvData != 0;
    v3 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
        (unsigned int)v3);
    }
    v4 = 0;
  }
  if ( lpName[0] != v7 )
    operator delete((void *)lpName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v4 + 1) > 1 )
    CloseHandle(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140050aa8  mov     [rsp-18h+arg_8], rbx
0x140050aad  push    rbp
0x140050aae  push    rsi
0x140050aaf  push    rdi
0x140050ab0  mov     rbp, rsp
0x140050ab3  sub     rsp, 60h
0x140050ab7  lea     rax, [rbp+var_10]
0x140050abb  mov     [rbp+arg_10], 4
0x140050ac2  mov     [rbp+lpName], rax
0x140050ac6  mov     rsi, rcx
0x140050ac9  lea     rax, [rbp+var_10]
0x140050acd  mov     r8d, edx
0x140050ad0  mov     [rbp+var_18], rax
0x140050ad4  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x140050adb  xor     eax, eax
0x140050add  mov     [rcx+38h], rax
0x140050ae1  lea     rcx, [rbp+lpName]
0x140050ae5  mov     [rbp+var_10], ax
0x140050ae9  mov     [rbp+arg_0], eax
0x140050aec  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x140050af1  mov     edi, eax
0x140050af3  test    eax, eax
0x140050af5  jns     short loc_140050B2C
0x140050af7  mov     rcx, cs:WPP_GLOBAL_Control
0x140050afe  lea     rax, WPP_GLOBAL_Control
0x140050b05  cmp     rcx, rax
0x140050b08  jz      short loc_140050B28
0x140050b0a  test    byte ptr [rcx+1Ch], 1
0x140050b0e  jz      short loc_140050B28
0x140050b10  mov     rcx, [rcx+10h]
0x140050b14  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x140050b1b  mov     edx, 20h ; ' '
0x140050b20  mov     r9d, edi
0x140050b23  call    WPP_SF_d
0x140050b28  xor     ebx, ebx
0x140050b2a  jmp     short loc_140050BA7
0x140050b2c  mov     r8, [rbp+lpName]; lpName
0x140050b30  xor     edx, edx; bInheritHandle
0x140050b32  mov     ecx, 100000h; dwDesiredAccess
0x140050b37  call    cs:__imp_OpenEventW
0x140050b3e  nop     dword ptr [rax+rax+00h]
0x140050b43  mov     rbx, rax
0x140050b46  inc     rax
0x140050b49  cmp     rax, 1
0x140050b4d  jbe     short loc_140050B56
0x140050b4f  mov     dword ptr [rsi+38h], 1
0x140050b56  lea     rax, [rbp+arg_10]
0x140050b5a  mov     r9d, 18h; dwFlags
0x140050b60  mov     [rsp+60h+pcbData], rax; pcbData
0x140050b65  lea     r8, aApprecorderena; "AppRecorderEnabled"
0x140050b6c  lea     rax, [rbp+arg_0]
0x140050b70  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140050b77  mov     [rsp+60h+pvData], rax; pvData
0x140050b7c  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x140050b83  mov     [rsp+60h+pdwType], 0; pdwType
0x140050b8c  call    cs:__imp_RegGetValueW
0x140050b93  nop     dword ptr [rax+rax+00h]
0x140050b98  test    eax, eax
0x140050b9a  jnz     short loc_140050BA5
0x140050b9c  cmp     [rbp+arg_0], eax
0x140050b9f  setnz   al
0x140050ba2  mov     [rsi+3Ch], eax
0x140050ba5  xor     edi, edi
0x140050ba7  mov     rcx, [rbp+lpName]; void *
0x140050bab  lea     rax, [rbp+var_10]
0x140050baf  cmp     rcx, rax
0x140050bb2  jz      short loc_140050BC0
0x140050bb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140050bbb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140050bc0  lea     rax, [rbx+1]
0x140050bc4  cmp     rax, 1
0x140050bc8  jbe     short loc_140050BD9
0x140050bca  mov     rcx, rbx; hObject
0x140050bcd  call    cs:__imp_CloseHandle
0x140050bd4  nop     dword ptr [rax+rax+00h]
0x140050bd9  mov     rbx, [rsp+60h+arg_8]
0x140050be1  mov     eax, edi
0x140050be3  add     rsp, 60h
0x140050be7  pop     rdi
0x140050be8  pop     rsi
0x140050be9  pop     rbp
0x140050bea  retn
```

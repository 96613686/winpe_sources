# CAppRecorderPlugin::IsAppRecorderEnabled(ulong)

- ea: `0x14004d558`
- end: `0x14004d689`
- name: `?IsAppRecorderEnabled@CAppRecorderPlugin@@AEAAJK@Z`
- size: `305`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004cf60`

## callees

- `0x140002728`
- `0x140005430`
- `0x140014474`
- `0x14004d558`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004d636`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004d636`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004d5e7`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004d5e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d671`

## string_xrefs

- `0x14004d626`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

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
        &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
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
0x14004d558  mov     [rsp-18h+arg_8], rbx
0x14004d55d  push    rbp
0x14004d55e  push    rsi
0x14004d55f  push    rdi
0x14004d560  mov     rbp, rsp
0x14004d563  sub     rsp, 60h
0x14004d567  lea     rax, [rbp+var_10]
0x14004d56b  mov     [rbp+arg_10], 4
0x14004d572  mov     [rbp+lpName], rax
0x14004d576  mov     rsi, rcx
0x14004d579  lea     rax, [rbp+var_10]
0x14004d57d  mov     r8d, edx
0x14004d580  mov     [rbp+var_18], rax
0x14004d584  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x14004d58b  xor     eax, eax
0x14004d58d  mov     [rcx+38h], rax
0x14004d591  lea     rcx, [rbp+lpName]
0x14004d595  mov     [rbp+var_10], ax
0x14004d599  mov     [rbp+arg_0], eax
0x14004d59c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14004d5a1  mov     edi, eax
0x14004d5a3  test    eax, eax
0x14004d5a5  jns     short loc_14004D5DC
0x14004d5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d5ae  lea     rax, WPP_GLOBAL_Control
0x14004d5b5  cmp     rcx, rax
0x14004d5b8  jz      short loc_14004D5D8
0x14004d5ba  test    byte ptr [rcx+1Ch], 1
0x14004d5be  jz      short loc_14004D5D8
0x14004d5c0  mov     rcx, [rcx+10h]
0x14004d5c4  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004d5cb  mov     edx, 20h ; ' '
0x14004d5d0  mov     r9d, edi
0x14004d5d3  call    WPP_SF_d
0x14004d5d8  xor     ebx, ebx
0x14004d5da  jmp     short loc_14004D64B
0x14004d5dc  mov     r8, [rbp+lpName]; lpName
0x14004d5e0  xor     edx, edx; bInheritHandle
0x14004d5e2  mov     ecx, 100000h; dwDesiredAccess
0x14004d5e7  call    cs:__imp_OpenEventW
0x14004d5ed  mov     rbx, rax
0x14004d5f0  inc     rax
0x14004d5f3  cmp     rax, 1
0x14004d5f7  jbe     short loc_14004D600
0x14004d5f9  mov     dword ptr [rsi+38h], 1
0x14004d600  lea     rax, [rbp+arg_10]
0x14004d604  mov     r9d, 18h; dwFlags
0x14004d60a  mov     [rsp+60h+pcbData], rax; pcbData
0x14004d60f  lea     r8, aApprecorderena; "AppRecorderEnabled"
0x14004d616  lea     rax, [rbp+arg_0]
0x14004d61a  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14004d621  mov     [rsp+60h+pvData], rax; pvData
0x14004d626  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x14004d62d  mov     [rsp+60h+pdwType], 0; pdwType
0x14004d636  call    cs:__imp_RegGetValueW
0x14004d63c  test    eax, eax
0x14004d63e  jnz     short loc_14004D649
0x14004d640  cmp     [rbp+arg_0], eax
0x14004d643  setnz   al
0x14004d646  mov     [rsi+3Ch], eax
0x14004d649  xor     edi, edi
0x14004d64b  mov     rcx, [rbp+lpName]; void *
0x14004d64f  lea     rax, [rbp+var_10]
0x14004d653  cmp     rcx, rax
0x14004d656  jz      short loc_14004D664
0x14004d658  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004d65f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004d664  lea     rax, [rbx+1]
0x14004d668  cmp     rax, 1
0x14004d66c  jbe     short loc_14004D677
0x14004d66e  mov     rcx, rbx; hObject
0x14004d671  call    cs:__imp_CloseHandle
0x14004d677  mov     rbx, [rsp+60h+arg_8]
0x14004d67f  mov     eax, edi
0x14004d681  add     rsp, 60h
0x14004d685  pop     rdi
0x14004d686  pop     rsi
0x14004d687  pop     rbp
0x14004d688  retn
```

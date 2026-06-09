# FlagWriteVs

- ea: `0x18003cae4`
- end: `0x18003cc2f`
- name: `FlagWriteVs`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003ca7c`

## callees

- `0x18000d030`
- `0x18003cae4`
- `0x18003cc38`
- `0x18003cce0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cb3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cb3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cb21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cb21`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cc12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cc12`
- `ntdll!NtSetInformationThread` at `0x18003cc09`
- `ntdll!NtSetInformationThread` at `0x18003cc09`
- `ntdll!RtlInitUnicodeString` at `0x18003cba6`
- `ntdll!RtlInitUnicodeString` at `0x18003cba6`

## string_xrefs

- `0x18003cb09`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall FlagWriteVs(__int64 a1, __int16 a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v4; // rdi
  int v5; // ecx
  FARPROC ProcAddress; // rsi
  int v7; // ebx
  unsigned __int8 v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 ThreadInformation; // [rsp+38h] [rbp-40h] BYREF
  int v11; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-30h] BYREF
  __int128 v13; // [rsp+58h] [rbp-20h] BYREF

  ThreadInformation = 0;
  v11 = 0;
  v13 = 0;
  DestinationString = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v4 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "NtSetSystemEnvironmentValueEx");
    if ( ProcAddress )
    {
      v7 = a2 & 0x7FF;
      if ( v7 )
      {
        if ( v7 != 1023 && BfAcquirePrivilege(v5, (struct _BF_PRIVILEGE_STATE *)&ThreadInformation) >= 0 )
        {
          v11 = 1;
          *(_QWORD *)&v13 = 0x4AC81707F6A8718BLL;
          *((_QWORD *)&v13 + 1) = 0xE7AA5F97EA17A3A1uLL;
          RtlInitUnicodeString(&DestinationString, L"OsNonStandardBoot");
          ((void (__fastcall *)(struct _UNICODE_STRING *, __int128 *, int *, __int64, int))ProcAddress)(
            &DestinationString,
            &v13,
            &v11,
            4,
            7);
          v9 = 0;
          if ( !BYTE4(ThreadInformation) )
            BfAdjustPrivilege(ThreadInformation, 0, (bool *)&v9);
          if ( !BYTE5(ThreadInformation) )
          {
            ThreadInformation = 0;
            NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          }
        }
      }
    }
    FreeLibrary(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18003cae4  push    rbp
0x18003cae6  push    rbx
0x18003cae7  push    rsi
0x18003cae8  push    rdi
0x18003cae9  mov     rbp, rsp
0x18003caec  sub     rsp, 78h
0x18003caf0  mov     rax, cs:__security_cookie
0x18003caf7  xor     rax, rsp
0x18003cafa  mov     [rbp+var_10], rax
0x18003cafe  xorps   xmm0, xmm0
0x18003cb01  mov     [rbp+ThreadInformation], 0
0x18003cb09  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18003cb10  mov     [rbp+var_38], 0
0x18003cb17  movups  [rbp+var_20], xmm0
0x18003cb1b  mov     ebx, edx
0x18003cb1d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003cb21  call    cs:__imp_GetModuleHandleW
0x18003cb27  mov     rdi, rax
0x18003cb2a  test    rax, rax
0x18003cb2d  jz      loc_18003CC18
0x18003cb33  lea     rdx, aNtsetsystemenv; "NtSetSystemEnvironmentValueEx"
0x18003cb3a  mov     rcx, rax; hModule
0x18003cb3d  call    cs:__imp_GetProcAddress
0x18003cb43  mov     rsi, rax
0x18003cb46  test    rax, rax
0x18003cb49  jz      loc_18003CC0F
0x18003cb4f  and     ebx, 7FFh
0x18003cb55  jz      loc_18003CC0F
0x18003cb5b  cmp     ebx, 3FFh
0x18003cb61  jz      loc_18003CC0F
0x18003cb67  lea     rdx, [rbp+ThreadInformation]; struct _BF_PRIVILEGE_STATE *
0x18003cb6b  call    ?BfAcquirePrivilege@@YAJKPEAU_BF_PRIVILEGE_STATE@@@Z; BfAcquirePrivilege(ulong,_BF_PRIVILEGE_STATE *)
0x18003cb70  test    eax, eax
0x18003cb72  js      loc_18003CC0F
0x18003cb78  lea     rdx, SourceString; "OsNonStandardBoot"
0x18003cb7f  mov     [rbp+var_38], 1
0x18003cb86  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003cb8a  mov     dword ptr [rbp+var_20], 0F6A8718Bh
0x18003cb91  mov     dword ptr [rbp+var_20+4], 4AC81707h
0x18003cb98  mov     dword ptr [rbp+var_20+8], 0EA17A3A1h
0x18003cb9f  mov     dword ptr [rbp+var_20+0Ch], 0E7AA5F97h
0x18003cba6  call    cs:__imp_RtlInitUnicodeString
0x18003cbac  mov     r9d, 4
0x18003cbb2  mov     [rsp+78h+var_58], 7
0x18003cbba  lea     r8, [rbp+var_38]
0x18003cbbe  mov     rax, rsi
0x18003cbc1  lea     rdx, [rbp+var_20]
0x18003cbc5  lea     rcx, [rbp+DestinationString]
0x18003cbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbce  cmp     byte ptr [rbp+ThreadInformation+4], 0
0x18003cbd2  mov     [rbp+var_48], 0
0x18003cbd6  jnz     short loc_18003CBE6
0x18003cbd8  mov     ecx, dword ptr [rbp+ThreadInformation]; unsigned int
0x18003cbdb  lea     r8, [rbp+var_48]; unsigned __int8 *
0x18003cbdf  xor     edx, edx; unsigned __int8
0x18003cbe1  call    ?BfAdjustPrivilege@@YAJKEPEAE@Z; BfAdjustPrivilege(ulong,uchar,uchar *)
0x18003cbe6  cmp     byte ptr [rbp+ThreadInformation+5], 0
0x18003cbea  jnz     short loc_18003CC0F
0x18003cbec  mov     r9d, 8; ThreadInformationLength
0x18003cbf2  mov     [rbp+ThreadInformation], 0
0x18003cbfa  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18003cbfe  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003cc05  lea     edx, [r9-3]; ThreadInformationClass
0x18003cc09  call    cs:__imp_NtSetInformationThread
0x18003cc0f  mov     rcx, rdi; hLibModule
0x18003cc12  call    cs:__imp_FreeLibrary
0x18003cc18  xor     eax, eax
0x18003cc1a  mov     rcx, [rbp+var_10]
0x18003cc1e  xor     rcx, rsp; StackCookie
0x18003cc21  call    __security_check_cookie
0x18003cc26  add     rsp, 78h
0x18003cc2a  pop     rdi
0x18003cc2b  pop     rsi
0x18003cc2c  pop     rbx
0x18003cc2d  pop     rbp
0x18003cc2e  retn
```

# PrivacieDllMain

- ea: `0x18061bb60`
- end: `0x18061bce4`
- name: `PrivacieDllMain`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18061ba20`

## callees

- `0x18061bb60`
- `0x180751764`
- `0x1810648c4`
- `0x181070350`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18061bbdd`
- `KERNEL32!InitializeCriticalSection` at `0x18061bbdd`
- `KERNEL32!CreateMutexW` at `0x18061bc1a`
- `KERNEL32!CreateMutexW` at `0x18061bc1a`
- `KERNEL32!DeleteCriticalSection` at `0x18061bc95`
- `KERNEL32!DeleteCriticalSection` at `0x18061bc95`
- `KERNEL32!GetLastError` at `0x18061bc30`
- `KERNEL32!GetLastError` at `0x18061bc30`
- `KERNEL32!CloseHandle` at `0x18061bcc3`
- `KERNEL32!CloseHandle` at `0x18061bcc3`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18061bc4f`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18061bc4f`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18061bc0b`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18061bc69`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18061bc0b`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x18061bc69`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18061bb8c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18061bb9b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18061bb8c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18061bb9b`

## pseudocode

```c
__int64 __fastcall PrivacieDllMain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int v8; // r9d
  unsigned int v9; // [rsp+20h] [rbp-2C8h]
  WCHAR Name[168]; // [rsp+30h] [rbp-2B8h] BYREF
  unsigned __int16 v11[168]; // [rsp+180h] [rbp-168h] BYREF
  int v12; // [rsp+2F8h] [rbp+10h]

  v12 = a2;
  if ( !(unsigned __int8)IEConfiguration_GetBool(268435482, a2, a3, a4)
    && !(unsigned __int8)IEConfiguration_GetBool(268435481, v4, v5, v6) )
  {
    return 1;
  }
  if ( !v12 )
  {
    DeleteCriticalSection(&stru_1815905B0);
    if ( g_pPrivaceIEAdvisor )
    {
      CPrivacIEAdvisor::Release(g_pPrivaceIEAdvisor);
      g_pPrivaceIEAdvisor = 0;
    }
    if ( g_hPrivacIEMutex )
      CloseHandle(g_hPrivacIEMutex);
    CSharedMem::Release((CSharedMem *)g_sharedPrivacIECounter);
    goto LABEL_16;
  }
  if ( v12 != 1 )
    return 1;
  InitializeCriticalSection(&stru_1815905B0);
  g_bPrivacIEInit = 1;
  IsoPrefixUserQualifierToName(Name, 0xA2u, L"!PrivacIE!SharedMem!Mutex");
  g_hPrivacIEMutex = CreateMutexW(0, 0, Name);
  if ( !g_hPrivacIEMutex )
  {
LABEL_16:
    g_bPrivacIEInit = 0;
    return 1;
  }
  if ( GetLastError() != 183 )
    SetWindowsHandleAccess(g_hPrivacIEMutex, 0x114Fu, 0x801F0003);
  IsoPrefixUserQualifierToName(v11, 0xA4u, L"!PrivacIE!SharedMem!Counter");
  CSharedMem::_InitInternal((CSharedMem *)g_sharedPrivacIECounter, v11, 0x10u, v8, v9);
  return 1;
}

```

## disassembly

```asm
0x18061bb60  mov     [rsp+arg_10], r8
0x18061bb65  mov     [rsp+arg_8], edx
0x18061bb69  mov     [rsp+arg_0], rcx
0x18061bb6e  sub     rsp, 2E8h
0x18061bb75  mov     rax, cs:__security_cookie
0x18061bb7c  xor     rax, rsp
0x18061bb7f  mov     [rsp+2E8h+var_18], rax
0x18061bb87  mov     ecx, 1000001Ah
0x18061bb8c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18061bb92  test    al, al
0x18061bb94  jnz     short loc_18061BBC2
0x18061bb96  mov     ecx, 10000019h
0x18061bb9b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18061bba1  test    al, al
0x18061bba3  jnz     short loc_18061BBC2
0x18061bba5  mov     eax, 1
0x18061bbaa  mov     rcx, [rsp+2E8h+var_18]
0x18061bbb2  xor     rcx, rsp; StackCookie
0x18061bbb5  call    __security_check_cookie
0x18061bbba  add     rsp, 2E8h
0x18061bbc1  retn
0x18061bbc2  mov     eax, [rsp+2E8h+arg_8]
0x18061bbc9  test    eax, eax
0x18061bbcb  jz      loc_18061BC8E
0x18061bbd1  cmp     eax, 1
0x18061bbd4  jnz     short loc_18061BBA5
0x18061bbd6  lea     rcx, stru_1815905B0; lpCriticalSection
0x18061bbdd  call    cs:__imp_InitializeCriticalSection
0x18061bbe3  mov     eax, 1
0x18061bbe8  mov     cs:?g_bPrivacIEInit@@3HA, eax; int g_bPrivacIEInit
0x18061bbee  jmp     short loc_18061BBF6
0x18061bbf0  mov     eax, cs:?g_bPrivacIEInit@@3HA; int g_bPrivacIEInit
0x18061bbf6  test    eax, eax
0x18061bbf8  jz      short loc_18061BBA5
0x18061bbfa  lea     r8, aPrivacieShared_0; "!PrivacIE!SharedMem!Mutex"
0x18061bc01  mov     edx, 0A2h
0x18061bc06  lea     rcx, [rsp+2E8h+Name]
0x18061bc0b  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x18061bc11  lea     r8, [rsp+2E8h+Name]; lpName
0x18061bc16  xor     edx, edx; bInitialOwner
0x18061bc18  xor     ecx, ecx; lpMutexAttributes
0x18061bc1a  call    cs:__imp_CreateMutexW
0x18061bc20  mov     cs:?g_hPrivacIEMutex@@3PEAXEA, rax; void * g_hPrivacIEMutex
0x18061bc27  test    rax, rax
0x18061bc2a  jz      loc_18061BCD5
0x18061bc30  call    cs:__imp_GetLastError
0x18061bc36  cmp     eax, 0B7h
0x18061bc3b  jz      short loc_18061BC55
0x18061bc3d  mov     edx, 114Fh
0x18061bc42  mov     r8d, 801F0003h
0x18061bc48  mov     rcx, cs:?g_hPrivacIEMutex@@3PEAXEA; void * g_hPrivacIEMutex
0x18061bc4f  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18061bc55  lea     r8, aPrivacieShared_1; "!PrivacIE!SharedMem!Counter"
0x18061bc5c  mov     edx, 0A4h
0x18061bc61  lea     rcx, [rsp+2E8h+var_168]
0x18061bc69  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x18061bc6f  mov     r8d, 10h; unsigned int
0x18061bc75  lea     rdx, [rsp+2E8h+var_168]; unsigned __int16 *
0x18061bc7d  lea     rcx, ?g_sharedPrivacIECounter@@3VCSharedMem@@A; this
0x18061bc84  call    ?_InitInternal@CSharedMem@@AEAAJPEBGKHK@Z; CSharedMem::_InitInternal(ushort const *,ulong,int,ulong)
0x18061bc89  jmp     loc_18061BBA5
0x18061bc8e  lea     rcx, stru_1815905B0; lpCriticalSection
0x18061bc95  call    cs:__imp_DeleteCriticalSection
0x18061bc9b  mov     rcx, cs:?g_pPrivaceIEAdvisor@@3PEAVCPrivacIEAdvisor@@EA; this
0x18061bca2  test    rcx, rcx
0x18061bca5  jz      short loc_18061BCB7
0x18061bca7  call    ?Release@CPrivacIEAdvisor@@UEAAKXZ; CPrivacIEAdvisor::Release(void)
0x18061bcac  mov     cs:?g_pPrivaceIEAdvisor@@3PEAVCPrivacIEAdvisor@@EA, 0; CPrivacIEAdvisor * g_pPrivaceIEAdvisor
0x18061bcb7  mov     rcx, cs:?g_hPrivacIEMutex@@3PEAXEA; hObject
0x18061bcbe  test    rcx, rcx
0x18061bcc1  jz      short loc_18061BCC9
0x18061bcc3  call    cs:__imp_CloseHandle
0x18061bcc9  lea     rcx, ?g_sharedPrivacIECounter@@3VCSharedMem@@A; this
0x18061bcd0  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x18061bcd5  mov     cs:?g_bPrivacIEInit@@3HA, 0; int g_bPrivacIEInit
0x18061bcdf  jmp     loc_18061BBA5
0x1810cdd41  mov     [rsp+arg_0], rcx
0x1810cdd46  mov     qword ptr [rsp+arg_8], rdx
0x1810cdd4b  push    rbp
0x1810cdd4c  sub     rsp, 30h
0x1810cdd50  mov     rbp, rdx
0x1810cdd53  mov     rax, [rcx]
0x1810cdd56  xor     ecx, ecx
0x1810cdd58  cmp     dword ptr [rax], 0C0000017h
0x1810cdd5e  setz    cl
0x1810cdd61  mov     eax, ecx
0x1810cdd63  add     rsp, 30h
0x1810cdd67  pop     rbp
0x1810cdd68  retn
```

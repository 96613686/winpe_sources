# TaskChangeFileHashes(_WOF_TASK_ACTION)

- ea: `0x1800038dc`
- end: `0x180003ab9`
- name: `?TaskChangeFileHashes@@YAJW4_WOF_TASK_ACTION@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180003ac0`

## callees

- `0x1800031bc`
- `0x1800038dc`
- `0x180004788`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800039ae`
- `KERNEL32!GetLastError` at `0x1800039ae`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800039a4`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800039a4`
- `ntdll!RtlQueryWnfStateData` at `0x180003944`
- `ntdll!RtlQueryWnfStateData` at `0x180003944`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180003980`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180003980`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180003a8a`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180003a8a`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800039f5`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800039f5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180003a4d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180003a4d`

## pseudocode

```c
__int64 __fastcall TaskChangeFileHashes(int a1)
{
  int WnfStateData; // edi
  unsigned int v3; // edi
  int v4; // eax
  signed int LastError; // eax
  ULONG v6; // edx
  BOOL (__stdcall *v7)(const PVOID, PVOID); // r8
  __int64 v8; // rax
  _DWORD v10[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[260]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v13; // [rsp+25Ch] [rbp+15Ch]
  union _LARGE_INTEGER v14; // [rsp+260h] [rbp+160h]
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+270h] [rbp+170h] BYREF

  memset_0(&v11, 0, 0x218u);
  v10[0] = 0;
  WnfStateData = RtlQueryWnfStateData(v10, WNF_FVE_WIM_HASH_GENERATION_TRIGGER, FveWnfNoopCallback, 0, 0);
  if ( WnfStateData >= 0 )
  {
    v4 = RtlSubscribeWnfStateChangeNotification(
           &WnfUserSubcription,
           WNF_FVE_WIM_HASH_GENERATION_TRIGGER,
           v10[0],
           FveWnfControlCallback,
           0,
           0,
           0,
           0);
    v3 = v4 | 0x10000000;
    if ( v4 >= 0 )
      v3 = 0;
  }
  else
  {
    v3 = WnfStateData | 0x10000000;
  }
  if ( !v3 )
  {
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      Buffer[2] = 0;
      v14.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
      v11 = a1;
      if ( EventEnabled(RegHandle, &WofTaskEnumVolumeEventId) )
      {
        v8 = -1;
        do
          ++v8;
        while ( Buffer[v8] );
        UserData.Reserved = 0;
        UserData.Ptr = (ULONGLONG)Buffer;
        UserData.Size = 2 * v8 + 2;
        EventWrite(RegHandle, &WofTaskEnumVolumeEventId, 1u, &UserData);
      }
      v3 = WofEnumEntries(Buffer, v6, v7, &v11);
      if ( !v3 )
      {
        v3 = v13;
        if ( !v13 )
          FileHashesCleanup(v14, Buffer);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    RtlUnsubscribeWnfStateChangeNotification(WnfUserSubcription);
  }
  return v3;
}

```

## disassembly

```asm
0x1800038dc  mov     [rsp-8+arg_8], rbx
0x1800038e1  mov     [rsp-8+arg_10], rsi
0x1800038e6  push    rbp
0x1800038e7  push    rdi
0x1800038e8  push    r14
0x1800038ea  lea     rbp, [rsp-190h]
0x1800038f2  sub     rsp, 290h
0x1800038f9  mov     rax, cs:__security_cookie
0x180003900  xor     rax, rsp
0x180003903  mov     [rbp+1A0h+var_20], rax
0x18000390a  mov     esi, ecx
0x18000390c  xor     edx, edx; Val
0x18000390e  lea     rcx, [rsp+2A0h+var_250]; void *
0x180003913  mov     r8d, 218h; Size
0x180003919  call    memset_0
0x18000391e  mov     rbx, cs:WNF_FVE_WIM_HASH_GENERATION_TRIGGER
0x180003925  lea     r8, ?FveWnfNoopCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; FveWnfNoopCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000392c  xor     r14d, r14d
0x18000392f  lea     rcx, [rsp+2A0h+var_260]
0x180003934  mov     rdx, rbx
0x180003937  mov     [rsp+2A0h+var_260], r14d
0x18000393c  xor     r9d, r9d
0x18000393f  mov     [rsp+2A0h+var_280], r14
0x180003944  call    cs:__imp_RtlQueryWnfStateData
0x18000394a  mov     edi, eax
0x18000394c  test    eax, eax
0x18000394e  jns     short loc_180003956
0x180003950  bts     edi, 1Ch
0x180003954  jmp     short loc_180003992
0x180003956  mov     r8d, [rsp+2A0h+var_260]
0x18000395b  lea     r9, ?FveWnfControlCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; FveWnfControlCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180003962  mov     [rsp+2A0h+var_268], r14d
0x180003967  lea     rcx, ?WnfUserSubcription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WnfUserSubcription
0x18000396e  mov     [rsp+2A0h+var_270], r14d
0x180003973  mov     rdx, rbx
0x180003976  mov     [rsp+2A0h+var_278], r14
0x18000397b  mov     [rsp+2A0h+var_280], r14
0x180003980  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180003986  mov     edi, eax
0x180003988  bts     edi, 1Ch
0x18000398c  test    eax, eax
0x18000398e  cmovns  edi, r14d
0x180003992  test    edi, edi
0x180003994  jnz     loc_180003A90
0x18000399a  mov     edx, 104h; uSize
0x18000399f  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800039a4  call    cs:__imp_GetWindowsDirectoryW
0x1800039aa  test    eax, eax
0x1800039ac  jnz     short loc_1800039CC
0x1800039ae  call    cs:__imp_GetLastError
0x1800039b4  mov     edi, eax
0x1800039b6  test    eax, eax
0x1800039b8  jle     loc_180003A83
0x1800039be  movzx   edi, ax
0x1800039c1  or      edi, 80070000h
0x1800039c7  jmp     loc_180003A83
0x1800039cc  mov     rcx, cs:RegHandle; RegHandle
0x1800039d3  lea     rdx, WofTaskEnumVolumeEventId; EventDescriptor
0x1800039da  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800039e4  mov     [rsp+2A0h+var_248], r14w
0x1800039ea  mov     qword ptr [rbp+1A0h+var_40], rax
0x1800039f1  mov     [rsp+2A0h+var_250], esi
0x1800039f5  call    cs:__imp_EventEnabled
0x1800039fb  test    al, al
0x1800039fd  jz      short loc_180003A53
0x1800039ff  lea     rcx, [rsp+2A0h+Buffer]
0x180003a04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a08  inc     rax
0x180003a0b  cmp     [rcx+rax*2], r14w
0x180003a10  jnz     short loc_180003A08
0x180003a12  lea     rcx, [rsp+2A0h+Buffer]
0x180003a17  mov     dword ptr [rbp+1A0h+UserData.0Ch], r14d
0x180003a1e  mov     [rbp+1A0h+UserData.Ptr], rcx
0x180003a25  lea     eax, ds:2[rax*2]
0x180003a2c  mov     rcx, cs:RegHandle; RegHandle
0x180003a33  lea     r9, [rbp+1A0h+UserData]; UserData
0x180003a3a  mov     r8d, 1; UserDataCount
0x180003a40  mov     [rbp+1A0h+UserData.Size], eax
0x180003a46  lea     rdx, WofTaskEnumVolumeEventId; EventDescriptor
0x180003a4d  call    cs:__imp_EventWrite
0x180003a53  lea     r9, [rsp+2A0h+var_250]; UserData
0x180003a58  lea     rcx, [rsp+2A0h+Buffer]; VolumeName
0x180003a5d  call    WofEnumEntries
0x180003a62  mov     edi, eax
0x180003a64  test    eax, eax
0x180003a66  jnz     short loc_180003A83
0x180003a68  mov     edi, [rbp+1A0h+var_44]
0x180003a6e  test    edi, edi
0x180003a70  jnz     short loc_180003A83
0x180003a72  mov     rcx, qword ptr [rbp+1A0h+var_40]; union _LARGE_INTEGER
0x180003a79  lea     rdx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180003a7e  call    ?FileHashesCleanup@@YAXT_LARGE_INTEGER@@PEBG@Z; FileHashesCleanup(_LARGE_INTEGER,ushort const *)
0x180003a83  mov     rcx, cs:?WnfUserSubcription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WnfUserSubcription
0x180003a8a  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180003a90  mov     eax, edi
0x180003a92  mov     rcx, [rbp+1A0h+var_20]
0x180003a99  xor     rcx, rsp; StackCookie
0x180003a9c  call    __security_check_cookie
0x180003aa1  lea     r11, [rsp+2A0h+var_10]
0x180003aa9  mov     rbx, [r11+28h]
0x180003aad  mov     rsi, [r11+30h]
0x180003ab1  mov     rsp, r11
0x180003ab4  pop     r14
0x180003ab6  pop     rdi
0x180003ab7  pop     rbp
0x180003ab8  retn
```

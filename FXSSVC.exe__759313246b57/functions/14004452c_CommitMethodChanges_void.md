# CommitMethodChanges(void)

- ea: `0x14004452c`
- end: `0x14004472f`
- name: `?CommitMethodChanges@@YAHXZ`
- size: `515`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001fcc0`

## callees

- `0x140026c14`
- `0x14004452c`
- `0x1400698ec`
- `0x14006998c`
- `0x140074004`
- `0x140074f18`
- `0x140075070`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400446c8`
- `ADVAPI32!RegCloseKey` at `0x1400446c8`
- `KERNEL32!EnterCriticalSection` at `0x140044559`
- `KERNEL32!EnterCriticalSection` at `0x140044559`
- `KERNEL32!LeaveCriticalSection` at `0x1400446f9`
- `KERNEL32!LeaveCriticalSection` at `0x1400446f9`
- `ole32!StringFromGUID2` at `0x140044593`
- `ole32!StringFromGUID2` at `0x140044593`

## string_xrefs

- `0x140044623`: `Software\Microsoft\Fax\Routing Extensions`

## pseudocode

```c
__int64 CommitMethodChanges(void)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v1; // rbx
  const BYTE *v2; // r15
  const BYTE *Blink; // r12
  int v4; // r13d
  struct _LIST_ENTRY *v5; // rsi
  __int64 v6; // r14
  __int64 v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  int v10; // eax
  SIZE_T v11; // rbp
  void *v12; // rbx
  HKEY v13; // rsi
  OLECHAR sz[104]; // [rsp+40h] [rbp-128h] BYREF

  EnterCriticalSection(&g_CsRouting);
  Flink = g_lstRoutingMethods.Flink;
  while ( Flink != &g_lstRoutingMethods )
  {
    v1 = Flink;
    Flink = Flink->Flink;
    StringFromGUID2((const GUID *const)&v1[1], sz, 100);
    v2 = (const BYTE *)v1[3].Flink;
    Blink = (const BYTE *)v1[2].Blink;
    v4 = (int)v1[2].Flink;
    v5 = v1[3].Blink;
    v6 = (__int64)&v1[4].Blink[68].Flink + 4;
    if ( v1[4].Blink == (struct _LIST_ENTRY *)-1092LL )
    {
      v8 = 0;
    }
    else
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(v6 + 2 * v7) );
      v8 = 2 * v7 + 2;
    }
    if ( v5 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)&v5->Flink + v9) );
      v10 = 2 * v9 + 2;
    }
    else
    {
      v10 = 0;
    }
    v11 = (unsigned int)(v8 + 116 + v10);
    v12 = (void *)pMemAlloc(v11);
    if ( v12 )
    {
      if ( (int)StringCbPrintfW(
                  (unsigned __int16 *)v12,
                  (unsigned int)v11,
                  L"%s\\%s\\%s\\%s",
                  L"Software\\Microsoft\\Fax\\Routing Extensions",
                  v6,
                  L"Routing Methods",
                  v5) >= 0
        && (v13 = OpenRegistryKey(HKEY_LOCAL_MACHINE, (const WCHAR *)v12, 0, 0x20006u)) != 0 )
      {
        pMemFree(v12);
        SetRegistryStringValue(v13, 1u, L"FriendlyName", v2);
        SetRegistryStringValue(v13, 1u, L"Function Name", Blink);
        SetRegistryStringValue(v13, 1u, L"Guid", (const BYTE *)sz);
        SetRegistryDword(v13, L"Priority", v4);
        RegCloseKey(v13);
      }
      else
      {
        pMemFree(v12);
      }
    }
  }
  LeaveCriticalSection(&g_CsRouting);
  return 1;
}

```

## disassembly

```asm
0x14004452c  push    rbx
0x14004452e  push    rbp
0x14004452f  push    rsi
0x140044530  push    rdi
0x140044531  push    r12
0x140044533  push    r13
0x140044535  push    r14
0x140044537  push    r15
0x140044539  sub     rsp, 128h
0x140044540  mov     rax, cs:__security_cookie
0x140044547  xor     rax, rsp
0x14004454a  mov     [rsp+168h+var_58], rax
0x140044552  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044559  call    cs:__imp_EnterCriticalSection
0x140044560  nop     dword ptr [rax+rax+00h]
0x140044565  mov     rdi, cs:?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x14004456c  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140044573  cmp     rdi, rax
0x140044576  jz      loc_1400446F2
0x14004457c  xor     ebp, ebp
0x14004457e  lea     rbx, [rdi]
0x140044581  mov     r8d, 64h ; 'd'; cchMax
0x140044587  mov     rdi, [rdi]
0x14004458a  lea     rcx, [rbx+10h]; rguid
0x14004458e  lea     rdx, [rsp+168h+sz]; lpsz
0x140044593  call    cs:__imp_StringFromGUID2
0x14004459a  nop     dword ptr [rax+rax+00h]
0x14004459f  mov     r14, [rbx+48h]
0x1400445a3  mov     r15, [rbx+30h]
0x1400445a7  mov     r12, [rbx+28h]
0x1400445ab  mov     r13d, [rbx+20h]
0x1400445af  mov     rsi, [rbx+38h]
0x1400445b3  add     r14, 444h
0x1400445ba  jz      short loc_1400445D4
0x1400445bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400445c0  inc     rax
0x1400445c3  cmp     [r14+rax*2], bp
0x1400445c8  jnz     short loc_1400445C0
0x1400445ca  lea     rcx, ds:2[rax*2]
0x1400445d2  jmp     short loc_1400445D7
0x1400445d4  mov     rcx, rbp
0x1400445d7  test    rsi, rsi
0x1400445da  jz      short loc_1400445F3
0x1400445dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400445e0  inc     rax
0x1400445e3  cmp     [rsi+rax*2], bp
0x1400445e7  jnz     short loc_1400445E0
0x1400445e9  lea     rax, ds:2[rax*2]
0x1400445f1  jmp     short loc_1400445F6
0x1400445f3  mov     rax, rbp
0x1400445f6  add     rcx, 74h ; 't'
0x1400445fa  add     rax, rcx
0x1400445fd  mov     ecx, eax; dwBytes
0x1400445ff  mov     ebp, eax
0x140044601  call    pMemAlloc
0x140044606  mov     rbx, rax
0x140044609  test    rax, rax
0x14004460c  jz      loc_1400446E0
0x140044612  lea     rax, aRoutingMethods; "Routing Methods"
0x140044619  mov     [rsp+168h+var_138], rsi
0x14004461e  mov     [rsp+168h+var_140], rax
0x140044623  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Fax\\Routing Exten"...
0x14004462a  lea     r8, aSSSS_1; "%s\\%s\\%s\\%s"
0x140044631  mov     qword ptr [rsp+168h+var_148], r14; int
0x140044636  mov     edx, ebp; unsigned __int64
0x140044638  mov     rcx, rbx; unsigned __int16 *
0x14004463b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140044640  xor     ebp, ebp
0x140044642  test    eax, eax
0x140044644  js      loc_1400446D6
0x14004464a  mov     r9d, 20006h
0x140044650  xor     r8d, r8d
0x140044653  mov     rdx, rbx
0x140044656  mov     rcx, 0FFFFFFFF80000002h
0x14004465d  call    OpenRegistryKey
0x140044662  mov     rsi, rax
0x140044665  test    rax, rax
0x140044668  jz      short loc_1400446D6
0x14004466a  mov     rcx, rbx; lpMem
0x14004466d  call    pMemFree
0x140044672  mov     r9, r15; unsigned __int16 *
0x140044675  lea     r8, aFriendlyname; "FriendlyName"
0x14004467c  lea     edx, [rbp+1]; unsigned int
0x14004467f  mov     rcx, rsi; HKEY
0x140044682  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140044687  mov     r9, r12; unsigned __int16 *
0x14004468a  lea     r8, aFunctionName; "Function Name"
0x140044691  lea     edx, [rbp+1]; unsigned int
0x140044694  mov     rcx, rsi; HKEY
0x140044697  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14004469c  lea     r9, [rsp+168h+sz]; unsigned __int16 *
0x1400446a1  mov     rcx, rsi; HKEY
0x1400446a4  lea     r8, aGuid; "Guid"
0x1400446ab  lea     edx, [rbp+1]; unsigned int
0x1400446ae  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x1400446b3  mov     r8d, r13d
0x1400446b6  lea     rdx, aPriority; "Priority"
0x1400446bd  mov     rcx, rsi
0x1400446c0  call    SetRegistryDword
0x1400446c5  mov     rcx, rsi; hKey
0x1400446c8  call    cs:__imp_RegCloseKey
0x1400446cf  nop     dword ptr [rax+rax+00h]
0x1400446d4  jmp     short loc_1400446E2
0x1400446d6  mov     rcx, rbx; lpMem
0x1400446d9  call    pMemFree
0x1400446de  jmp     short loc_1400446E2
0x1400446e0  xor     ebp, ebp
0x1400446e2  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x1400446e9  cmp     rdi, rax
0x1400446ec  jnz     loc_14004457E
0x1400446f2  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400446f9  call    cs:__imp_LeaveCriticalSection
0x140044700  nop     dword ptr [rax+rax+00h]
0x140044705  mov     eax, 1
0x14004470a  mov     rcx, [rsp+168h+var_58]
0x140044712  xor     rcx, rsp; StackCookie
0x140044715  call    __security_check_cookie
0x14004471a  add     rsp, 128h
0x140044721  pop     r15
0x140044723  pop     r14
0x140044725  pop     r13
0x140044727  pop     r12
0x140044729  pop     rdi
0x14004472a  pop     rsi
0x14004472b  pop     rbp
0x14004472c  pop     rbx
0x14004472d  retn
```

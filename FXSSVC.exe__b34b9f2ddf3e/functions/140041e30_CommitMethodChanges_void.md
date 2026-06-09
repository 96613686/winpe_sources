# CommitMethodChanges(void)

- ea: `0x140041e30`
- end: `0x14004201a`
- name: `?CommitMethodChanges@@YAHXZ`
- size: `490`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001ef40`

## callees

- `0x140025980`
- `0x140041e30`
- `0x140065d14`
- `0x140065dbc`
- `0x14006fa88`
- `0x1400708c4`
- `0x1400709fc`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140041fc0`
- `ADVAPI32!RegCloseKey` at `0x140041fc0`
- `KERNEL32!EnterCriticalSection` at `0x140041e5d`
- `KERNEL32!EnterCriticalSection` at `0x140041e5d`
- `KERNEL32!LeaveCriticalSection` at `0x140041feb`
- `KERNEL32!LeaveCriticalSection` at `0x140041feb`
- `ole32!StringFromGUID2` at `0x140041e91`
- `ole32!StringFromGUID2` at `0x140041e91`

## string_xrefs

- `0x140041f1b`: `Software\Microsoft\Fax\Routing Extensions`

## pseudocode

```c
__int64 CommitMethodChanges(void)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v1; // rbx
  const unsigned __int16 *v2; // r15
  const unsigned __int16 *Blink; // r12
  unsigned int v4; // r13d
  struct _LIST_ENTRY *v5; // rsi
  __int64 v6; // r14
  __int64 v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  int v10; // eax
  SIZE_T v11; // rbp
  void *v12; // rbx
  HKEY v13; // rsi
  int v15; // [rsp+20h] [rbp-148h]
  int v16; // [rsp+20h] [rbp-148h]
  OLECHAR sz[104]; // [rsp+40h] [rbp-128h] BYREF

  EnterCriticalSection(&g_CsRouting);
  Flink = g_lstRoutingMethods.Flink;
  while ( Flink != &g_lstRoutingMethods )
  {
    v1 = Flink;
    Flink = Flink->Flink;
    StringFromGUID2((const GUID *const)&v1[1], sz, 100);
    v2 = (const unsigned __int16 *)v1[3].Flink;
    Blink = (const unsigned __int16 *)v1[2].Blink;
    v4 = (unsigned int)v1[2].Flink;
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
                  L"Software\\Microsoft\\Fax\\Routing Extensions") >= 0
        && (v13 = (HKEY)OpenRegistryKey(-2147483646, v12, 0, 131078)) != 0 )
      {
        pMemFree(v12);
        SetRegistryStringValue(v13, 1u, L"FriendlyName", v2, v6);
        SetRegistryStringValue(v13, 1u, L"Function Name", Blink, v15);
        SetRegistryStringValue(v13, 1u, L"Guid", sz, v16);
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
0x140041e30  push    rbx
0x140041e32  push    rbp
0x140041e33  push    rsi
0x140041e34  push    rdi
0x140041e35  push    r12
0x140041e37  push    r13
0x140041e39  push    r14
0x140041e3b  push    r15
0x140041e3d  sub     rsp, 128h
0x140041e44  mov     rax, cs:__security_cookie
0x140041e4b  xor     rax, rsp
0x140041e4e  mov     [rsp+168h+var_58], rax
0x140041e56  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140041e5d  call    cs:__imp_EnterCriticalSection
0x140041e63  mov     rdi, cs:?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140041e6a  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140041e71  cmp     rdi, rax
0x140041e74  jz      loc_140041FE4
0x140041e7a  xor     ebp, ebp
0x140041e7c  lea     rbx, [rdi]
0x140041e7f  mov     r8d, 64h ; 'd'; cchMax
0x140041e85  mov     rdi, [rdi]
0x140041e88  lea     rcx, [rbx+10h]; rguid
0x140041e8c  lea     rdx, [rsp+168h+sz]; lpsz
0x140041e91  call    cs:__imp_StringFromGUID2
0x140041e97  mov     r14, [rbx+48h]
0x140041e9b  mov     r15, [rbx+30h]
0x140041e9f  mov     r12, [rbx+28h]
0x140041ea3  mov     r13d, [rbx+20h]
0x140041ea7  mov     rsi, [rbx+38h]
0x140041eab  add     r14, 444h
0x140041eb2  jz      short loc_140041ECC
0x140041eb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x140041eb8  inc     rax
0x140041ebb  cmp     [r14+rax*2], bp
0x140041ec0  jnz     short loc_140041EB8
0x140041ec2  lea     rcx, ds:2[rax*2]
0x140041eca  jmp     short loc_140041ECF
0x140041ecc  mov     rcx, rbp
0x140041ecf  test    rsi, rsi
0x140041ed2  jz      short loc_140041EEB
0x140041ed4  or      rax, 0FFFFFFFFFFFFFFFFh
0x140041ed8  inc     rax
0x140041edb  cmp     [rsi+rax*2], bp
0x140041edf  jnz     short loc_140041ED8
0x140041ee1  lea     rax, ds:2[rax*2]
0x140041ee9  jmp     short loc_140041EEE
0x140041eeb  mov     rax, rbp
0x140041eee  add     rcx, 74h ; 't'
0x140041ef2  add     rax, rcx
0x140041ef5  mov     ecx, eax; dwBytes
0x140041ef7  mov     ebp, eax
0x140041ef9  call    pMemAlloc
0x140041efe  mov     rbx, rax
0x140041f01  test    rax, rax
0x140041f04  jz      loc_140041FD2
0x140041f0a  lea     rax, aRoutingMethods; "Routing Methods"
0x140041f11  mov     [rsp+168h+var_138], rsi
0x140041f16  mov     [rsp+168h+var_140], rax
0x140041f1b  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Fax\\Routing Exten"...
0x140041f22  lea     r8, aSSSS_1; "%s\\%s\\%s\\%s"
0x140041f29  mov     qword ptr [rsp+168h+var_148], r14; int
0x140041f2e  mov     edx, ebp; unsigned __int64
0x140041f30  mov     rcx, rbx; unsigned __int16 *
0x140041f33  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140041f38  xor     ebp, ebp
0x140041f3a  test    eax, eax
0x140041f3c  js      loc_140041FC8
0x140041f42  mov     r9d, 20006h
0x140041f48  xor     r8d, r8d
0x140041f4b  mov     rdx, rbx
0x140041f4e  mov     rcx, 0FFFFFFFF80000002h
0x140041f55  call    OpenRegistryKey
0x140041f5a  mov     rsi, rax
0x140041f5d  test    rax, rax
0x140041f60  jz      short loc_140041FC8
0x140041f62  mov     rcx, rbx; lpMem
0x140041f65  call    pMemFree
0x140041f6a  mov     r9, r15; unsigned __int16 *
0x140041f6d  lea     r8, aFriendlyname; "FriendlyName"
0x140041f74  lea     edx, [rbp+1]; unsigned int
0x140041f77  mov     rcx, rsi; HKEY
0x140041f7a  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140041f7f  mov     r9, r12; unsigned __int16 *
0x140041f82  lea     r8, aFunctionName; "Function Name"
0x140041f89  lea     edx, [rbp+1]; unsigned int
0x140041f8c  mov     rcx, rsi; HKEY
0x140041f8f  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140041f94  lea     r9, [rsp+168h+sz]; unsigned __int16 *
0x140041f99  mov     rcx, rsi; HKEY
0x140041f9c  lea     r8, aGuid; "Guid"
0x140041fa3  lea     edx, [rbp+1]; unsigned int
0x140041fa6  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x140041fab  mov     r8d, r13d
0x140041fae  lea     rdx, aPriority; "Priority"
0x140041fb5  mov     rcx, rsi
0x140041fb8  call    SetRegistryDword
0x140041fbd  mov     rcx, rsi; hKey
0x140041fc0  call    cs:__imp_RegCloseKey
0x140041fc6  jmp     short loc_140041FD4
0x140041fc8  mov     rcx, rbx; lpMem
0x140041fcb  call    pMemFree
0x140041fd0  jmp     short loc_140041FD4
0x140041fd2  xor     ebp, ebp
0x140041fd4  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140041fdb  cmp     rdi, rax
0x140041fde  jnz     loc_140041E7C
0x140041fe4  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140041feb  call    cs:__imp_LeaveCriticalSection
0x140041ff1  mov     eax, 1
0x140041ff6  mov     rcx, [rsp+168h+var_58]
0x140041ffe  xor     rcx, rsp; StackCookie
0x140042001  call    __security_check_cookie
0x140042006  add     rsp, 128h
0x14004200d  pop     r15
0x14004200f  pop     r14
0x140042011  pop     r13
0x140042013  pop     r12
0x140042015  pop     rdi
0x140042016  pop     rsi
0x140042017  pop     rbp
0x140042018  pop     rbx
0x140042019  retn
```

# StubNlmCacheOpenPersistentStore

- ea: `0x180011758`
- end: `0x180011823`
- name: `StubNlmCacheOpenPersistentStore`
- size: `203`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800113e0`
- `0x180011590`
- `0x180011f74`
- `0x18002c494`

## callees

- `0x180011758`
- `0x18001c500`
- `0x18001d09c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800117b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800117b4`

## pseudocode

```c
__int64 __fastcall StubNlmCacheOpenPersistentStore(__int64 a1, HKEY *a2)
{
  unsigned int Key; // eax
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  *a2 = 0;
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a1 + 128), 0, 0, 0, 0x2001Fu, 0, a2, 0);
  v5 = Key;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, Key);
  }
  return v5;
}

```

## disassembly

```asm
0x180011758  mov     [rsp+arg_0], rbx
0x18001175d  mov     [rsp+arg_8], rsi
0x180011762  push    rdi
0x180011763  sub     rsp, 50h
0x180011767  mov     rbx, rdx
0x18001176a  mov     rdi, rcx
0x18001176d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011774  lea     rsi, WPP_GLOBAL_Control
0x18001177b  cmp     rcx, rsi
0x18001177e  jnz     short loc_1800117DA
0x180011780  xor     eax, eax
0x180011782  xor     r9d, r9d; lpClass
0x180011785  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001178a  xor     r8d, r8d; Reserved
0x18001178d  mov     [rsp+58h+phkResult], rbx; phkResult
0x180011792  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011799  mov     [rsp+58h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001179e  mov     [rbx], rax
0x1800117a1  mov     rdx, [rdi+80h]; lpSubKey
0x1800117a8  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800117b0  mov     [rsp+58h+dwOptions], eax; dwOptions
0x1800117b4  call    cs:__imp_RegCreateKeyExW
0x1800117ba  mov     ebx, eax
0x1800117bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117c3  cmp     rcx, rsi
0x1800117c6  jnz     short loc_1800117FD
0x1800117c8  mov     rsi, [rsp+58h+arg_8]
0x1800117cd  mov     eax, ebx
0x1800117cf  mov     rbx, [rsp+58h+arg_0]
0x1800117d4  add     rsp, 50h
0x1800117d8  pop     rdi
0x1800117d9  retn
0x1800117da  test    byte ptr [rcx+1Ch], 4
0x1800117de  jz      short loc_180011780
0x1800117e0  cmp     byte ptr [rcx+19h], 6
0x1800117e4  jb      short loc_180011780
0x1800117e6  mov     rcx, [rcx+10h]
0x1800117ea  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800117f1  mov     edx, 73h ; 's'
0x1800117f6  call    WPP_SF_
0x1800117fb  jmp     short loc_180011780
0x1800117fd  test    byte ptr [rcx+1Ch], 4
0x180011801  jz      short loc_1800117C8
0x180011803  cmp     byte ptr [rcx+19h], 6
0x180011807  jb      short loc_1800117C8
0x180011809  mov     rcx, [rcx+10h]
0x18001180d  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180011814  mov     edx, 74h ; 't'
0x180011819  mov     r9d, ebx
0x18001181c  call    WPP_SF_d
0x180011821  jmp     short loc_1800117C8
```

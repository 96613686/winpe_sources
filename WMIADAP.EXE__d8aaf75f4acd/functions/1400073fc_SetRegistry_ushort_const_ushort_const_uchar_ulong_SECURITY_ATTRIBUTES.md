# SetRegistry(ushort const *,ushort const *,uchar *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1400073fc`
- end: `0x1400074b1`
- name: `?SetRegistry@@YAJPEBG0PEAEKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int8 *, DWORD, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b2e4`

## callees

- `0x140006a78`
- `0x14000723c`
- `0x1400073fc`
- `0x1400074b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000747f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000747f`

## pseudocode

```c
__int64 __fastcall SetRegistry(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *a5)
{
  int v7; // eax
  const unsigned __int16 *v8; // rcx
  int v9; // ebx
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF

  memset(hKey, 0, 24);
  v7 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         (HKEY)a2,
         L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance",
         0x20006u);
  v9 = v7;
  if ( !v7 || v7 != 5 && SetRegistry(v8, a5, (struct ATL::CRegKey *)hKey) >= 0 )
    v9 = RegSetValueExW(hKey[0], L"Performance Data", 0, 3u, a3, a4);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  ATL::CRegKey::Close(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400073fc  mov     rax, rsp
0x1400073ff  mov     [rax+8], rbx
0x140007403  mov     [rax+10h], rsi
0x140007407  push    rdi
0x140007408  sub     rsp, 50h
0x14000740c  mov     edi, r9d
0x14000740f  mov     rsi, r8
0x140007412  mov     qword ptr [rax-28h], 0
0x14000741a  mov     qword ptr [rax-20h], 0
0x140007422  mov     qword ptr [rax-18h], 0
0x14000742a  mov     r9d, 20006h; unsigned int
0x140007430  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x140007437  lea     rcx, [rax-28h]; this
0x14000743b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x140007440  mov     ebx, eax
0x140007442  test    eax, eax
0x140007444  jz      short loc_140007461
0x140007446  cmp     eax, 5
0x140007449  jz      short loc_140007487
0x14000744b  lea     r8, [rsp+58h+hKey]; struct ATL::CRegKey *
0x140007450  mov     rdx, [rsp+58h+arg_20]; struct _SECURITY_ATTRIBUTES *
0x140007458  call    ?SetRegistry@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@AEAVCRegKey@ATL@@@Z; SetRegistry(ushort const *,_SECURITY_ATTRIBUTES *,ATL::CRegKey &)
0x14000745d  test    eax, eax
0x14000745f  js      short loc_140007487
0x140007461  mov     [rsp+58h+cbData], edi; cbData
0x140007465  mov     [rsp+58h+lpData], rsi; lpData
0x14000746a  mov     r9d, 3; dwType
0x140007470  xor     r8d, r8d; Reserved
0x140007473  lea     rdx, aPerformanceDat; "Performance Data"
0x14000747a  mov     rcx, [rsp+58h+hKey]; hKey
0x14000747f  call    cs:__imp_RegSetValueExW
0x140007485  mov     ebx, eax
0x140007487  test    ebx, ebx
0x140007489  jle     short loc_140007494
0x14000748b  movzx   ebx, bx
0x14000748e  or      ebx, 80070000h
0x140007494  lea     rcx, [rsp+58h+hKey]; this
0x140007499  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000749e  nop
0x14000749f  mov     eax, ebx
0x1400074a1  mov     rbx, [rsp+58h+arg_0]
0x1400074a6  mov     rsi, [rsp+58h+arg_8]
0x1400074ab  add     rsp, 50h
0x1400074af  pop     rdi
0x1400074b0  retn
```

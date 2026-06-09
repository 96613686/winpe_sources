# SetRegistry(ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x14000735c`
- end: `0x1400073f6`
- name: `?SetRegistry@@YAJPEBG0KPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *, int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007ab8`

## callees

- `0x140006a78`
- `0x14000723c`
- `0x14000735c`
- `0x1400074b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400073ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400073ce`

## pseudocode

```c
__int64 __fastcall SetRegistry(const unsigned __int16 *a1, WCHAR *a2, int a3, struct _SECURITY_ATTRIBUTES *a4)
{
  int v5; // eax
  const unsigned __int16 *v6; // rcx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF

  Data = a3;
  memset(hKey, 0, 24);
  v5 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         (HKEY)a2,
         L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance",
         0x20006u);
  if ( v5 && v5 != 5 )
    SetRegistry(v6, 0, (struct ATL::CRegKey *)hKey);
  v7 = RegSetValueExW(hKey[0], a2, 0, 4u, (const BYTE *)&Data, 4u);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  ATL::CRegKey::Close(hKey);
  return v8;
}

```

## disassembly

```asm
0x14000735c  mov     rax, rsp
0x14000735f  mov     [rax+18h], r8d
0x140007363  push    rbx
0x140007364  sub     rsp, 50h
0x140007368  mov     rbx, rdx
0x14000736b  mov     qword ptr [rax-28h], 0
0x140007373  mov     qword ptr [rax-20h], 0
0x14000737b  mov     qword ptr [rax-18h], 0
0x140007383  mov     r9d, 20006h; unsigned int
0x140007389  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x140007390  lea     rcx, [rax-28h]; this
0x140007394  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x140007399  test    eax, eax
0x14000739b  jz      short loc_1400073AE
0x14000739d  cmp     eax, 5
0x1400073a0  jz      short loc_1400073AE
0x1400073a2  lea     r8, [rsp+58h+hKey]; struct ATL::CRegKey *
0x1400073a7  xor     edx, edx; struct _SECURITY_ATTRIBUTES *
0x1400073a9  call    ?SetRegistry@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@AEAVCRegKey@ATL@@@Z; SetRegistry(ushort const *,_SECURITY_ATTRIBUTES *,ATL::CRegKey &)
0x1400073ae  mov     r9d, 4; dwType
0x1400073b4  mov     [rsp+58h+cbData], r9d; cbData
0x1400073b9  lea     rax, [rsp+58h+Data]
0x1400073be  mov     [rsp+58h+lpData], rax; lpData
0x1400073c3  xor     r8d, r8d; Reserved
0x1400073c6  mov     rdx, rbx; lpValueName
0x1400073c9  mov     rcx, [rsp+58h+hKey]; hKey
0x1400073ce  call    cs:__imp_RegSetValueExW
0x1400073d4  mov     ebx, eax
0x1400073d6  test    eax, eax
0x1400073d8  jle     short loc_1400073E3
0x1400073da  movzx   ebx, ax
0x1400073dd  or      ebx, 80070000h
0x1400073e3  lea     rcx, [rsp+58h+hKey]; this
0x1400073e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400073ed  nop
0x1400073ee  mov     eax, ebx
0x1400073f0  add     rsp, 50h
0x1400073f4  pop     rbx
0x1400073f5  retn
```

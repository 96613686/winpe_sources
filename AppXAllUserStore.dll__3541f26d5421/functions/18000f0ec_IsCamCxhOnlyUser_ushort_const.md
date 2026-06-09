# IsCamCxhOnlyUser(ushort const *)

- ea: `0x18000f0ec`
- end: `0x18000f17e`
- name: `?IsCamCxhOnlyUser@@YA_NPEBG@Z`
- size: `146`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800110cc`

## callees

- `0x18000f0ec`
- `0x18000f21c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f165`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f165`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f12c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f12c`

## pseudocode

```c
char __fastcall IsCamCxhOnlyUser(const unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // r9d
  bool v4; // sf
  int v6; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  if ( !a1 )
    return 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\CandidateAccountManager",
         0,
         0x20019u,
         &hKey);
  v4 = v2 < 0;
  if ( v2 > 0 )
    v4 = 1;
  if ( !v4 && (SHRegGetBOOLWithREGSAM(hKey, a1, L"CxhOnlyUse", v3, &v6), RegCloseKey(hKey), v6) )
    return 1;
  else
    return 0;
}

```

## disassembly

```asm
0x18000f0ec  push    rbx
0x18000f0ee  sub     rsp, 30h
0x18000f0f2  mov     [rsp+38h+arg_0], 0
0x18000f0fa  mov     rbx, rcx
0x18000f0fd  test    rcx, rcx
0x18000f100  jz      short loc_18000F176
0x18000f102  lea     rax, [rsp+38h+hKey]
0x18000f107  mov     [rsp+38h+hKey], 0
0x18000f110  mov     r9d, 20019h; samDesired
0x18000f116  mov     [rsp+38h+phkResult], rax; phkResult
0x18000f11b  xor     r8d, r8d; ulOptions
0x18000f11e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000f125  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f12c  call    cs:__imp_RegOpenKeyExW
0x18000f132  test    eax, eax
0x18000f134  jle     short loc_18000F140
0x18000f136  movzx   eax, ax
0x18000f139  or      eax, 80070000h
0x18000f13e  test    eax, eax
0x18000f140  js      short loc_18000F176
0x18000f142  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000f147  lea     rax, [rsp+38h+arg_0]
0x18000f14c  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x18000f153  mov     [rsp+38h+phkResult], rax; int *
0x18000f158  mov     rdx, rbx; unsigned __int16 *
0x18000f15b  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18000f160  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f165  call    cs:__imp_RegCloseKey
0x18000f16b  cmp     [rsp+38h+arg_0], 0
0x18000f170  jz      short loc_18000F176
0x18000f172  mov     al, 1
0x18000f174  jmp     short loc_18000F178
0x18000f176  xor     al, al
0x18000f178  add     rsp, 30h
0x18000f17c  pop     rbx
0x18000f17d  retn
```

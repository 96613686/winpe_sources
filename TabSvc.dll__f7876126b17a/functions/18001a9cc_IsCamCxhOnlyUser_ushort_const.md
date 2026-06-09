# IsCamCxhOnlyUser(ushort const *)

- ea: `0x18001a9cc`
- end: `0x18001aa5e`
- name: `?IsCamCxhOnlyUser@@YA_NPEBG@Z`
- size: `146`
- prototype: `char __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012560`

## callees

- `0x180012ba0`
- `0x18001a9cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aa0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aa0c`

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
0x18001a9cc  push    rbx
0x18001a9ce  sub     rsp, 30h
0x18001a9d2  mov     [rsp+38h+arg_0], 0
0x18001a9da  mov     rbx, rcx
0x18001a9dd  test    rcx, rcx
0x18001a9e0  jz      short loc_18001AA56
0x18001a9e2  lea     rax, [rsp+38h+hKey]
0x18001a9e7  mov     [rsp+38h+hKey], 0
0x18001a9f0  mov     r9d, 20019h; samDesired
0x18001a9f6  mov     [rsp+38h+phkResult], rax; phkResult
0x18001a9fb  xor     r8d, r8d; ulOptions
0x18001a9fe  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001aa05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001aa0c  call    cs:__imp_RegOpenKeyExW
0x18001aa12  test    eax, eax
0x18001aa14  jle     short loc_18001AA20
0x18001aa16  movzx   eax, ax
0x18001aa19  or      eax, 80070000h
0x18001aa1e  test    eax, eax
0x18001aa20  js      short loc_18001AA56
0x18001aa22  mov     rcx, [rsp+38h+hKey]; HKEY
0x18001aa27  lea     rax, [rsp+38h+arg_0]
0x18001aa2c  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x18001aa33  mov     [rsp+38h+phkResult], rax; int *
0x18001aa38  mov     rdx, rbx; unsigned __int16 *
0x18001aa3b  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18001aa40  mov     rcx, [rsp+38h+hKey]; hKey
0x18001aa45  call    cs:__imp_RegCloseKey
0x18001aa4b  cmp     [rsp+38h+arg_0], 0
0x18001aa50  jz      short loc_18001AA56
0x18001aa52  mov     al, 1
0x18001aa54  jmp     short loc_18001AA58
0x18001aa56  xor     al, al
0x18001aa58  add     rsp, 30h
0x18001aa5c  pop     rbx
0x18001aa5d  retn
```

# IsCamCxhOnlyUser(ushort const *)

- ea: `0x180022e5c`
- end: `0x180022eee`
- name: `?IsCamCxhOnlyUser@@YA_NPEBG@Z`
- size: `146`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022f24`

## callees

- `0x180022e5c`
- `0x180023b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022ed5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022ed5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022e9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022e9c`

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
0x180022e5c  push    rbx
0x180022e5e  sub     rsp, 30h
0x180022e62  mov     [rsp+38h+arg_0], 0
0x180022e6a  mov     rbx, rcx
0x180022e6d  test    rcx, rcx
0x180022e70  jz      short loc_180022EE6
0x180022e72  lea     rax, [rsp+38h+hKey]
0x180022e77  mov     [rsp+38h+hKey], 0
0x180022e80  mov     r9d, 20019h; samDesired
0x180022e86  mov     [rsp+38h+phkResult], rax; phkResult
0x180022e8b  xor     r8d, r8d; ulOptions
0x180022e8e  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022e95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022e9c  call    cs:__imp_RegOpenKeyExW
0x180022ea2  test    eax, eax
0x180022ea4  jle     short loc_180022EB0
0x180022ea6  movzx   eax, ax
0x180022ea9  or      eax, 80070000h
0x180022eae  test    eax, eax
0x180022eb0  js      short loc_180022EE6
0x180022eb2  mov     rcx, [rsp+38h+hKey]; HKEY
0x180022eb7  lea     rax, [rsp+38h+arg_0]
0x180022ebc  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x180022ec3  mov     [rsp+38h+phkResult], rax; int *
0x180022ec8  mov     rdx, rbx; unsigned __int16 *
0x180022ecb  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180022ed0  mov     rcx, [rsp+38h+hKey]; hKey
0x180022ed5  call    cs:__imp_RegCloseKey
0x180022edb  cmp     [rsp+38h+arg_0], 0
0x180022ee0  jz      short loc_180022EE6
0x180022ee2  mov     al, 1
0x180022ee4  jmp     short loc_180022EE8
0x180022ee6  xor     al, al
0x180022ee8  add     rsp, 30h
0x180022eec  pop     rbx
0x180022eed  retn
```

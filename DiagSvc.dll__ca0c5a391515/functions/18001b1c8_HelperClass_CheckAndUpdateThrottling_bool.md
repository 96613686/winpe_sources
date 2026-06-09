# HelperClass::CheckAndUpdateThrottling(bool *)

- ea: `0x18001b1c8`
- end: `0x18001b2b9`
- name: `?CheckAndUpdateThrottling@HelperClass@@SAJPEA_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180010300`
- `0x180010790`

## callees

- `0x18001b1c8`
- `0x18001c0a4`
- `0x18001c104`
- `0x18001c264`
- `0x18001c37c`
- `0x18001c38c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b21f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b21f`

## string_xrefs

- `0x18001b20d`: `SYSTEM\CurrentControlSet\Services\diagsvc\Settings`

## pseudocode

```c
__int64 __fastcall HelperClass::CheckAndUpdateThrottling(bool *a1)
{
  LSTATUS ValueW; // eax
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  const unsigned __int16 *v5; // r8
  signed int v6; // ebx
  int DWORD; // eax
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // r9d
  time_t v12; // rbx
  const unsigned __int16 *v13; // rdx
  HKEY v14; // rcx
  const unsigned __int16 *v15; // r8
  unsigned int v17; // [rsp+68h] [rbp+28h] BYREF
  time_t pcbData; // [rsp+70h] [rbp+30h] BYREF
  time_t Time2; // [rsp+78h] [rbp+38h] BYREF

  Time2 = 0;
  v17 = 0;
  LODWORD(pcbData) = 8;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\diagsvc\\Settings",
             L"ThrottlingPeriodStartTime",
             8u,
             0,
             &Time2,
             (LPDWORD)&pcbData);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  DWORD = SHRegGetDWORD(v4, v3, v5, &v17);
  v10 = 2147942402LL;
  if ( v6 == -2147024894 )
  {
    if ( DWORD == -2147024894 )
      goto LABEL_5;
LABEL_12:
    *a1 = 1;
    return 0;
  }
  if ( v6 < 0 || DWORD < 0 )
    goto LABEL_12;
  v11 = v17 + 1;
  v17 = v11;
  if ( v11 <= 0x14 )
    goto LABEL_6;
  v12 = Time2;
  pcbData = 0;
  time(&pcbData);
  if ( difftime(pcbData, v12) < 300.0 )
  {
    SHRegSetDWORD(v14, v13, v15, v17);
    goto LABEL_12;
  }
LABEL_5:
  HelperClass::SetThrottlingTimeStamp();
  v11 = 1;
LABEL_6:
  SHRegSetDWORD((HKEY)v10, v8, v9, v11);
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x18001b1c8  push    rbp
0x18001b1ca  push    rbx
0x18001b1cb  push    rdi
0x18001b1cc  mov     rbp, rsp
0x18001b1cf  sub     rsp, 40h
0x18001b1d3  lea     rax, [rbp+arg_10]
0x18001b1d7  mov     [rbp+Time2], 0
0x18001b1df  mov     [rsp+40h+pcbData], rax; pcbData
0x18001b1e4  lea     r8, aThrottlingperi; "ThrottlingPeriodStartTime"
0x18001b1eb  lea     rax, [rbp+Time2]
0x18001b1ef  mov     [rbp+arg_8], 0
0x18001b1f6  mov     rdi, rcx
0x18001b1f9  mov     [rsp+40h+pvData], rax; pvData
0x18001b1fe  mov     r9d, 8; dwFlags
0x18001b204  mov     [rsp+40h+pdwType], 0; pdwType
0x18001b20d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\di"...
0x18001b214  mov     dword ptr [rbp+arg_10], r9d
0x18001b218  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001b21f  call    cs:__imp_RegGetValueW
0x18001b225  mov     ebx, eax
0x18001b227  test    eax, eax
0x18001b229  jle     short loc_18001B234
0x18001b22b  movzx   ebx, ax
0x18001b22e  or      ebx, 80070000h
0x18001b234  lea     r9, [rbp+arg_8]; unsigned int *
0x18001b238  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001b23d  mov     ecx, 80070002h
0x18001b242  cmp     ebx, ecx
0x18001b244  jnz     short loc_18001B25F
0x18001b246  cmp     eax, ecx
0x18001b248  jnz     short loc_18001B2AC
0x18001b24a  call    ?SetThrottlingTimeStamp@HelperClass@@CAJXZ; HelperClass::SetThrottlingTimeStamp(void)
0x18001b24f  mov     r9d, 1; unsigned int
0x18001b255  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001b25a  mov     byte ptr [rdi], 0
0x18001b25d  jmp     short loc_18001B2AF
0x18001b25f  test    ebx, ebx
0x18001b261  js      short loc_18001B2AC
0x18001b263  test    eax, eax
0x18001b265  js      short loc_18001B2AC
0x18001b267  mov     r9d, [rbp+arg_8]
0x18001b26b  inc     r9d
0x18001b26e  mov     [rbp+arg_8], r9d
0x18001b272  cmp     r9d, 14h
0x18001b276  jbe     short loc_18001B255
0x18001b278  mov     rbx, [rbp+Time2]
0x18001b27c  lea     rcx, [rbp+arg_10]; Time
0x18001b280  mov     [rbp+arg_10], 0
0x18001b288  call    time
0x18001b28d  mov     rcx, [rbp+arg_10]; Time1
0x18001b291  mov     rdx, rbx; Time2
0x18001b294  call    difftime
0x18001b299  comisd  xmm0, cs:__real@4072c00000000000
0x18001b2a1  jnb     short loc_18001B24A
0x18001b2a3  mov     r9d, [rbp+arg_8]; unsigned int
0x18001b2a7  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001b2ac  mov     byte ptr [rdi], 1
0x18001b2af  xor     eax, eax
0x18001b2b1  add     rsp, 40h
0x18001b2b5  pop     rdi
0x18001b2b6  pop     rbx
0x18001b2b7  pop     rbp
0x18001b2b8  retn
```

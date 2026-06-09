# IsContainerRefreshDateExpired(ushort const *,ushort const *)

- ea: `0x180004e94`
- end: `0x1800050fa`
- name: `?IsContainerRefreshDateExpired@@YA_NPEBG0@Z`
- size: `614`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180004580`

## callees

- `0x180004e94`
- `0x18001af70`
- `0x18002541c`
- `0x180028984`
- `0x18002ec90`
- `0x18002f344`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004f93`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180004f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ef3`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180004ee2`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000509c`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180004ee2`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18000509c`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180004f5f`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180004f5f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180005089`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180005089`

## pseudocode

```c
char __fastcall IsContainerRefreshDateExpired(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  signed int ObjectProperties; // esi
  ULONG pulNumLanguages; // [rsp+50h] [rbp-9h] BYREF
  __int128 v7; // [rsp+60h] [rbp+7h]
  int v8; // [rsp+70h] [rbp+17h]
  int v9; // [rsp+74h] [rbp+1Bh]
  __int64 v10; // [rsp+78h] [rbp+1Fh]

  pulNumLanguages = 0;
  if ( SetThreadPreferredUILanguages(8u, a2, &pulNumLanguages) )
    goto LABEL_5;
  LastError = GetLastError();
  ObjectProperties = LastError;
  if ( LastError > 0 )
    ObjectProperties = (unsigned __int16)LastError | 0x80070000;
  if ( ObjectProperties >= 0 )
  {
LABEL_5:
    v8 = 8;
    v9 = 0;
    v10 = 0;
    v7 = DEVPKEY_DeviceSetup_UserRefreshDate;
    ObjectProperties = DevGetObjectProperties(2, a1, 4);
    if ( ObjectProperties >= 0 )
      LOBYTE(ObjectProperties) = -1;
    SetThreadPreferredUILanguages(0, &pwszLanguagesBuffer, &pulNumLanguages);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
      (_DWORD)a1,
      ObjectProperties);
  return 1;
}

```

## disassembly

```asm
0x180004e94  mov     [rsp-8+arg_10], rbx
0x180004e99  push    rbp
0x180004e9a  push    rsi
0x180004e9b  push    rdi
0x180004e9c  push    r14
0x180004e9e  push    r15
0x180004ea0  lea     rbp, [rsp-37h]
0x180004ea5  sub     rsp, 90h
0x180004eac  mov     rax, cs:__security_cookie
0x180004eb3  xor     rax, rsp
0x180004eb6  mov     [rbp+57h+var_30], rax
0x180004eba  mov     r15, rcx
0x180004ebd  mov     [rbp+57h+var_70], 0
0x180004ec4  mov     ecx, 8; dwFlags
0x180004ec9  mov     [rbp+57h+var_68], 0
0x180004ed1  lea     r8, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x180004ed5  mov     [rbp+57h+pulNumLanguages], 0
0x180004edc  mov     rbx, rdx
0x180004edf  mov     r14b, 1
0x180004ee2  call    cs:__imp_SetThreadPreferredUILanguages
0x180004ee8  lea     rdi, WPP_GLOBAL_Control
0x180004eef  test    eax, eax
0x180004ef1  jnz     short loc_180004F10
0x180004ef3  call    cs:__imp_GetLastError
0x180004ef9  mov     esi, eax
0x180004efb  test    eax, eax
0x180004efd  jle     short loc_180004F08
0x180004eff  movzx   esi, ax
0x180004f02  or      esi, 80070000h
0x180004f08  test    esi, esi
0x180004f0a  js      loc_1800050A6
0x180004f10  mov     eax, cs:dword_18004BC08
0x180004f16  mov     r9d, 1
0x180004f1c  movups  xmm0, cs:DEVPKEY_DeviceSetup_UserRefreshDate
0x180004f23  mov     [rbp+57h+var_40], eax
0x180004f26  mov     rdx, r15
0x180004f29  lea     rax, [rbp+57h+var_68]
0x180004f2d  mov     [rbp+57h+var_3C], 0
0x180004f34  mov     [rsp+0B0h+var_80], rax
0x180004f39  lea     r8d, [r9+3]
0x180004f3d  lea     rax, [rbp+57h+var_70]
0x180004f41  mov     [rbp+57h+var_38], 0
0x180004f49  mov     [rsp+0B0h+var_88], rax
0x180004f4e  lea     ecx, [r9+1]
0x180004f52  lea     rax, [rbp+57h+var_50]
0x180004f56  mov     [rsp+0B0h+var_90], rax
0x180004f5b  movups  [rbp+57h+var_50], xmm0
0x180004f5f  call    cs:__imp_DevGetObjectProperties
0x180004f65  mov     esi, eax
0x180004f67  test    eax, eax
0x180004f69  js      loc_18000507A
0x180004f6f  cmp     [rbp+57h+var_70], 1
0x180004f73  mov     esi, 8000FFFFh
0x180004f78  mov     rax, [rbp+57h+var_68]
0x180004f7c  jnz     loc_18000507E
0x180004f82  cmp     dword ptr [rax+20h], 10h
0x180004f86  jnz     loc_18000507E
0x180004f8c  mov     rcx, [rax+18h]
0x180004f90  mov     rdx, rbx
0x180004f93  call    cs:__imp__o__wcsicmp
0x180004f99  test    eax, eax
0x180004f9b  jnz     loc_18000507A
0x180004fa1  mov     rax, [rbp+57h+var_68]
0x180004fa5  mov     edi, 7FFE0014h
0x180004faa  xor     esi, esi
0x180004fac  mov     rcx, [rax+28h]
0x180004fb0  mov     rdi, [rdi]
0x180004fb3  mov     eax, [rcx+4]
0x180004fb6  mov     dword ptr [rbp+57h+var_58+4], eax
0x180004fb9  mov     eax, [rcx]
0x180004fbb  mov     dword ptr [rbp+57h+var_58], eax
0x180004fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fc5  lea     rax, WPP_GLOBAL_Control
0x180004fcc  mov     rbx, [rbp+57h+var_58]
0x180004fd0  cmp     rcx, rax
0x180004fd3  jz      short loc_180004FF3
0x180004fd5  test    [rcx+1Ch], r14b
0x180004fd9  jz      short loc_180004FF3
0x180004fdb  mov     rcx, [rcx+10h]
0x180004fdf  mov     r9, r15
0x180004fe2  mov     [rsp+0B0h+var_90], rbx
0x180004fe7  call    WPP_SF_Si
0x180004fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ff3  sub     rdi, rbx
0x180004ff6  mov     r8, 8888888888888889h
0x180005000  mov     rax, 0D6BF94D5E57A42BDh
0x18000500a  mul     rdi
0x18000500d  mov     rax, r8
0x180005010  shr     rdx, 17h
0x180005014  mul     rdx
0x180005017  mov     rax, r8
0x18000501a  shr     rdx, 5
0x18000501e  mul     rdx
0x180005021  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000502b  shr     rdx, 5
0x18000502f  mul     rdx
0x180005032  mov     rbx, rdx
0x180005035  shr     rbx, 4
0x180005039  lea     rdi, WPP_GLOBAL_Control
0x180005040  cmp     rcx, rdi
0x180005043  jz      short loc_180005063
0x180005045  test    [rcx+1Ch], r14b
0x180005049  jz      short loc_180005063
0x18000504b  mov     rcx, [rcx+10h]
0x18000504f  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180005056  mov     edx, 0Bh
0x18000505b  mov     r9, rbx
0x18000505e  call    WPP_SF_i
0x180005063  mov     rcx, r15; unsigned __int16 *
0x180005066  call    ?GetContainerRefreshIntervalInDays@@YAIPEBG@Z; GetContainerRefreshIntervalInDays(ushort const *)
0x18000506b  mov     ecx, eax
0x18000506d  xor     eax, eax
0x18000506f  cmp     rbx, rcx
0x180005072  movzx   r14d, r14b
0x180005076  cmovb   r14d, eax
0x18000507a  mov     rax, [rbp+57h+var_68]
0x18000507e  test    rax, rax
0x180005081  jz      short loc_18000508F
0x180005083  mov     ecx, [rbp+57h+var_70]
0x180005086  mov     rdx, rax
0x180005089  call    cs:__imp_DevFreeObjectProperties
0x18000508f  lea     r8, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x180005093  xor     ecx, ecx; dwFlags
0x180005095  lea     rdx, pwszLanguagesBuffer; pwszLanguagesBuffer
0x18000509c  call    cs:__imp_SetThreadPreferredUILanguages
0x1800050a2  test    esi, esi
0x1800050a4  jns     short loc_1800050D4
0x1800050a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050ad  cmp     rcx, rdi
0x1800050b0  jz      short loc_1800050D4
0x1800050b2  test    byte ptr [rcx+1Ch], 1
0x1800050b6  jz      short loc_1800050D4
0x1800050b8  mov     rcx, [rcx+10h]
0x1800050bc  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x1800050c3  mov     edx, 0Ch
0x1800050c8  mov     dword ptr [rsp+0B0h+var_90], esi
0x1800050cc  mov     r9, r15
0x1800050cf  call    WPP_SF_Sd
0x1800050d4  mov     al, r14b
0x1800050d7  mov     rcx, [rbp+57h+var_30]
0x1800050db  xor     rcx, rsp; StackCookie
0x1800050de  call    __security_check_cookie
0x1800050e3  mov     rbx, [rsp+0B0h+arg_10]
0x1800050eb  add     rsp, 90h
0x1800050f2  pop     r15
0x1800050f4  pop     r14
0x1800050f6  pop     rdi
0x1800050f7  pop     rsi
0x1800050f8  pop     rbp
0x1800050f9  retn
```

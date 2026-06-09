# DoesRegKeyExist(HKEY__ * const,wchar_t const * const,bool *)

- ea: `0x180015104`
- end: `0x180015237`
- name: `?DoesRegKeyExist@@YAJQEAUHKEY__@@QEB_WPEA_N@Z`
- size: `307`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013850`
- `0x18001d140`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180015104`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001520d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001520d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015143`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015143`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015203`

## string_xrefs

- `0x180015160`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
__int64 __fastcall DoesRegKeyExist(HKEY a1, const WCHAR *a2, bool *a3)
{
  int v4; // ebx
  _QWORD v6[5]; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF

  v6[4] = -2;
  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  if ( v4 == 2 )
  {
    *a3 = 0;
    goto LABEL_12;
  }
  if ( !v4 )
  {
    *a3 = 1;
LABEL_12:
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL )
    {
      if ( RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
    }
    return 0;
  }
  v6[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v6[1] = "DoesRegKeyExist";
  v6[2] = 4944;
  v6[3] = "RetValue";
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  RtlReportErrorOrigination(v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015104  mov     r11, rsp
0x180015107  push    rdi
0x180015108  sub     rsp, 70h
0x18001510c  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180015114  mov     [r11+20h], rbx
0x180015118  mov     rax, cs:__security_cookie
0x18001511f  xor     rax, rsp
0x180015122  mov     [rsp+78h+var_18], rax
0x180015127  mov     rdi, r8
0x18001512a  mov     qword ptr [r11-20h], 0
0x180015132  lea     rax, [r11-20h]
0x180015136  mov     [r11-58h], rax
0x18001513a  mov     r9d, 20119h; samDesired
0x180015140  xor     r8d, r8d; ulOptions
0x180015143  call    cs:__imp_RegOpenKeyExW
0x180015149  mov     ebx, eax
0x18001514b  cmp     eax, 2
0x18001514e  jnz     short loc_180015158
0x180015150  mov     byte ptr [rdi], 0
0x180015153  jmp     loc_1800151E7
0x180015158  test    ebx, ebx
0x18001515a  jz      loc_1800151E4
0x180015160  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180015167  mov     [rsp+78h+var_48], rax
0x18001516c  lea     rax, aDoesregkeyexis; "DoesRegKeyExist"
0x180015173  mov     [rsp+78h+var_40], rax
0x180015178  mov     [rsp+78h+var_38], 1350h
0x180015181  lea     rax, aRetvalue; "RetValue"
0x180015188  mov     [rsp+78h+var_30], rax
0x18001518d  jle     short loc_180015198
0x18001518f  movzx   ebx, bx
0x180015192  or      ebx, 80070000h
0x180015198  mov     r8d, ebx
0x18001519b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800151a2  lea     rcx, [rsp+78h+var_48]
0x1800151a7  call    RtlReportErrorOrigination
0x1800151ac  nop
0x1800151ad  mov     rcx, [rsp+78h+hKey]; hKey
0x1800151b2  test    rcx, rcx
0x1800151b5  jz      short loc_1800151E0
0x1800151b7  mov     rax, rcx
0x1800151ba  mov     rdx, 0FFFFFFFF80000000h
0x1800151c1  and     rax, rdx
0x1800151c4  cmp     rax, rdx
0x1800151c7  jz      short loc_1800151E0
0x1800151c9  call    cs:__imp_RegCloseKey
0x1800151cf  test    eax, eax
0x1800151d1  jz      short loc_1800151E0
0x1800151d3  call    cs:__imp_GetLastError
0x1800151d9  mov     ecx, 7
0x1800151de  int     29h; Win8: RtlFailFast(ecx)
0x1800151e0  mov     eax, ebx
0x1800151e2  jmp     short loc_18001521C
0x1800151e4  mov     byte ptr [rdi], 1
0x1800151e7  mov     rcx, [rsp+78h+hKey]; hKey
0x1800151ec  test    rcx, rcx
0x1800151ef  jz      short loc_18001521A
0x1800151f1  mov     rdx, 0FFFFFFFF80000000h
0x1800151f8  mov     rax, rcx
0x1800151fb  and     rax, rdx
0x1800151fe  cmp     rax, rdx
0x180015201  jz      short loc_18001521A
0x180015203  call    cs:__imp_RegCloseKey
0x180015209  test    eax, eax
0x18001520b  jz      short loc_18001521A
0x18001520d  call    cs:__imp_GetLastError
0x180015213  mov     ecx, 7
0x180015218  int     29h; Win8: RtlFailFast(ecx)
0x18001521a  xor     eax, eax
0x18001521c  mov     rcx, [rsp+78h+var_18]
0x180015221  xor     rcx, rsp; StackCookie
0x180015224  call    __security_check_cookie
0x180015229  mov     rbx, [rsp+78h+arg_18]
0x180015231  add     rsp, 70h
0x180015235  pop     rdi
0x180015236  retn
```

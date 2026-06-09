# DoesRegDwordExist(HKEY__ * const,wchar_t const * const,wchar_t const * const,bool *)

- ea: `0x180015034`
- end: `0x1800150fc`
- name: `?DoesRegDwordExist@@YAJQEAUHKEY__@@QEB_W1PEA_N@Z`
- size: `200`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013600`
- `0x180021a28`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180015034`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001507d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001507d`

## string_xrefs

- `0x180015093`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
__int64 __fastcall DoesRegDwordExist(HKEY a1, const WCHAR *a2, const WCHAR *a3, bool *a4)
{
  int ValueW; // ebx
  _QWORD v7[4]; // [rsp+40h] [rbp-48h] BYREF
  DWORD v8; // [rsp+60h] [rbp-28h] BYREF
  int v9; // [rsp+64h] [rbp-24h] BYREF

  v9 = 0;
  v8 = 4;
  ValueW = RegGetValueW(a1, a2, a3, 0x10u, 0, &v9, &v8);
  if ( ValueW == 2 )
  {
    *a4 = 0;
    return 0;
  }
  if ( !ValueW )
  {
    *a4 = 1;
    return 0;
  }
  v7[2] = 4978;
  v7[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v7[1] = "DoesRegDwordExist";
  v7[3] = "RetValue";
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  RtlReportErrorOrigination(v7, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180015034  mov     r11, rsp
0x180015037  push    rbx
0x180015038  push    rdi
0x180015039  sub     rsp, 78h
0x18001503d  mov     rax, cs:__security_cookie
0x180015044  xor     rax, rsp
0x180015047  mov     [rsp+88h+var_20], rax
0x18001504c  lea     rax, [r11-28h]
0x180015050  mov     [rsp+88h+var_24], 0
0x180015058  mov     [r11-58h], rax
0x18001505c  mov     rdi, r9
0x18001505f  lea     rax, [r11-24h]
0x180015063  mov     [rsp+88h+var_28], 4
0x18001506b  mov     [r11-60h], rax
0x18001506f  mov     r9d, 10h; dwFlags
0x180015075  mov     qword ptr [r11-68h], 0
0x18001507d  call    cs:__imp_RegGetValueW
0x180015083  mov     ebx, eax
0x180015085  cmp     eax, 2
0x180015088  jnz     short loc_18001508F
0x18001508a  mov     byte ptr [rdi], 0
0x18001508d  jmp     short loc_1800150E6
0x18001508f  test    ebx, ebx
0x180015091  jz      short loc_1800150E3
0x180015093  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001509a  mov     [rsp+88h+var_38], 1372h
0x1800150a3  mov     [rsp+88h+var_48], rax
0x1800150a8  lea     rax, aDoesregdwordex; "DoesRegDwordExist"
0x1800150af  mov     [rsp+88h+var_40], rax
0x1800150b4  lea     rax, aRetvalue; "RetValue"
0x1800150bb  mov     [rsp+88h+var_30], rax
0x1800150c0  jle     short loc_1800150CB
0x1800150c2  movzx   ebx, bx
0x1800150c5  or      ebx, 80070000h
0x1800150cb  mov     r8d, ebx
0x1800150ce  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800150d5  lea     rcx, [rsp+88h+var_48]
0x1800150da  call    RtlReportErrorOrigination
0x1800150df  mov     eax, ebx
0x1800150e1  jmp     short loc_1800150E8
0x1800150e3  mov     byte ptr [rdi], 1
0x1800150e6  xor     eax, eax
0x1800150e8  mov     rcx, [rsp+88h+var_20]
0x1800150ed  xor     rcx, rsp; StackCookie
0x1800150f0  call    __security_check_cookie
0x1800150f5  add     rsp, 78h
0x1800150f9  pop     rdi
0x1800150fa  pop     rbx
0x1800150fb  retn
```

# UpdateReserveManager::GetShippedWithReservesValue(ulong *)

- ea: `0x1800176ac`
- end: `0x1800177f1`
- name: `?GetShippedWithReservesValue@UpdateReserveManager@@AEAAJPEAK@Z`
- size: `325`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012bf0`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x1800176ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001770f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800177a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001770f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800177a9`

## string_xrefs

- `0x18001772c`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017737`: `UpdateReserveManager::GetShippedWithReservesValue`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetShippedWithReservesValue(HKEY *this, unsigned int *a2)
{
  LSTATUS ValueW; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  HKEY v8; // rcx
  _QWORD v9[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+50h] [rbp-20h]
  const char *v11; // [rsp+58h] [rbp-18h]
  DWORD pcbData; // [rsp+60h] [rbp-10h] BYREF
  unsigned int pvData; // [rsp+64h] [rbp-Ch] BYREF

  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             this[13],
             L"Microsoft\\Windows\\CurrentVersion\\ReserveManager\\Overrides",
             L"ShippedWithReserves",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v5 = ValueW;
  if ( ValueW == 2 )
  {
    v8 = this[13];
    pcbData = 4;
    v5 = RegGetValueW(
           v8,
           L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
           L"ShippedWithReserves",
           0x10u,
           0,
           &pvData,
           &pcbData);
    if ( v5 == 2 )
      return 2147942402LL;
    v6 = (int)v5 <= 0;
    if ( v5 )
    {
      v10 = 3683;
      goto LABEL_4;
    }
LABEL_11:
    *a2 = pvData;
    return 0;
  }
  v6 = ValueW <= 0;
  if ( !ValueW )
    goto LABEL_11;
  v10 = 3662;
LABEL_4:
  v9[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v9[1] = "UpdateReserveManager::GetShippedWithReservesValue";
  v11 = "RetValue";
  if ( !v6 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  RtlReportErrorOrigination(v9, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v5);
  return v5;
}

```

## disassembly

```asm
0x1800176ac  mov     r11, rsp
0x1800176af  mov     [r11+18h], rbx
0x1800176b3  push    rbp
0x1800176b4  push    rsi
0x1800176b5  push    rdi
0x1800176b6  mov     rbp, rsp
0x1800176b9  sub     rsp, 70h
0x1800176bd  mov     rax, cs:__security_cookie
0x1800176c4  xor     rax, rsp
0x1800176c7  mov     [rbp+var_8], rax
0x1800176cb  lea     rax, [rbp+var_10]
0x1800176cf  mov     [rbp+var_C], 0
0x1800176d6  mov     [r11-58h], rax
0x1800176da  lea     r8, ValueName; "ShippedWithReserves"
0x1800176e1  lea     rax, [rbp+var_C]
0x1800176e5  mov     [rbp+var_10], 4
0x1800176ec  mov     rdi, rdx
0x1800176ef  mov     [r11-60h], rax
0x1800176f3  mov     rsi, rcx
0x1800176f6  mov     qword ptr [r11-68h], 0
0x1800176fe  mov     rcx, [rcx+68h]; hkey
0x180017702  lea     rdx, aMicrosoftWindo_1; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180017709  mov     r9d, 10h; dwFlags
0x18001770f  call    cs:__imp_RegGetValueW
0x180017715  mov     ebx, eax
0x180017717  cmp     eax, 2
0x18001771a  jz      short loc_18001776F
0x18001771c  test    eax, eax
0x18001771e  jz      loc_1800177CE
0x180017724  mov     [rbp+var_20], 0E4Eh
0x18001772c  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017733  mov     [rbp+var_30], rax
0x180017737  lea     rax, aUpdatereservem_22; "UpdateReserveManager::GetShippedWithRes"...
0x18001773e  mov     [rbp+var_28], rax
0x180017742  lea     rax, aRetvalue; "RetValue"
0x180017749  mov     [rbp+var_18], rax
0x18001774d  jle     short loc_180017758
0x18001774f  movzx   ebx, bx
0x180017752  or      ebx, 80070000h
0x180017758  mov     r8d, ebx
0x18001775b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017762  lea     rcx, [rbp+var_30]
0x180017766  call    RtlReportErrorOrigination
0x18001776b  mov     eax, ebx
0x18001776d  jmp     short loc_1800177D5
0x18001776f  mov     rcx, [rsi+68h]; hkey
0x180017773  lea     rax, [rbp+var_10]
0x180017777  mov     [rsp+70h+pcbData], rax; pcbData
0x18001777c  lea     r8, ValueName; "ShippedWithReserves"
0x180017783  lea     rax, [rbp+var_C]
0x180017787  mov     [rbp+var_10], 4
0x18001778e  mov     [rsp+70h+pvData], rax; pvData
0x180017793  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001779a  mov     r9d, 10h; dwFlags
0x1800177a0  mov     [rsp+70h+pdwType], 0; pdwType
0x1800177a9  call    cs:__imp_RegGetValueW
0x1800177af  mov     ebx, eax
0x1800177b1  cmp     eax, 2
0x1800177b4  jnz     short loc_1800177BD
0x1800177b6  mov     eax, 80070002h
0x1800177bb  jmp     short loc_1800177D5
0x1800177bd  test    ebx, ebx
0x1800177bf  jz      short loc_1800177CE
0x1800177c1  mov     [rbp+var_20], 0E63h
0x1800177c9  jmp     loc_18001772C
0x1800177ce  mov     eax, [rbp+var_C]
0x1800177d1  mov     [rdi], eax
0x1800177d3  xor     eax, eax
0x1800177d5  mov     rcx, [rbp+var_8]
0x1800177d9  xor     rcx, rsp; StackCookie
0x1800177dc  call    __security_check_cookie
0x1800177e1  mov     rbx, [rsp+70h+arg_10]
0x1800177e9  add     rsp, 70h
0x1800177ed  pop     rdi
0x1800177ee  pop     rsi
0x1800177ef  pop     rbp
0x1800177f0  retn
```

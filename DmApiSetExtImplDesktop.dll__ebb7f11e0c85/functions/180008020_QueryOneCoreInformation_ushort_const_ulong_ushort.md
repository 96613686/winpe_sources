# QueryOneCoreInformation(ushort const *,ulong,ushort *)

- ea: `0x180008020`
- end: `0x1800080f0`
- name: `?QueryOneCoreInformation@@YAJPEBGKPEAG@Z`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, unsigned int, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800083c0`
- `0x1800085c0`
- `0x180008610`
- `0x180008bc0`
- `0x1800092d0`

## callees

- `0x180002134`
- `0x180008020`
- `0x1800080f8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000804e`
- `msvcrt!_wcsicmp` at `0x18000806c`
- `msvcrt!_wcsicmp` at `0x18000808b`
- `msvcrt!_wcsicmp` at `0x18000804e`
- `msvcrt!_wcsicmp` at `0x18000806c`
- `msvcrt!_wcsicmp` at `0x18000808b`
- `ext-ms-windowscore-deviceinfo-l1-1-0!QueryDeviceInformation` at `0x1800080a7`
- `ext-ms-windowscore-deviceinfo-l1-1-0!QueryDeviceInformation` at `0x1800080a7`

## pseudocode

```c
__int64 __fastcall QueryOneCoreInformation(LPCWSTR lpValue, unsigned int a2, unsigned __int16 *a3)
{
  __int64 v4; // rsi
  __int64 v6; // rcx
  __int64 result; // rax
  bool v8; // sf

  v4 = a2;
  if ( (unsigned __int8)IsQueryDeviceInformationPresent() )
  {
    if ( _wcsicmp(lpValue, L"OneCoreManufacturer") )
    {
      if ( _wcsicmp(lpValue, L"OneCoreManufacturerModelName") )
      {
        if ( _wcsicmp(lpValue, L"OneCoreFwV") )
        {
          result = 2147942487LL;
          goto LABEL_11;
        }
        v6 = 7;
      }
      else
      {
        v6 = 2;
      }
    }
    else
    {
      v6 = 0;
    }
    result = QueryDeviceInformation(v6, a3, v4, 0);
    v8 = (int)result < 0;
    if ( (int)result <= 0 )
      goto LABEL_12;
    result = (unsigned __int16)result | 0x80070000;
LABEL_11:
    v8 = (int)result < 0;
LABEL_12:
    if ( !v8 )
      return result;
  }
  return RegLookupHelper(L"System\\Platform\\DeviceTargetingInfo", lpValue, v4, a3);
}

```

## disassembly

```asm
0x180008020  mov     [rsp+arg_0], rbx
0x180008025  mov     [rsp+arg_8], rsi
0x18000802a  push    rdi
0x18000802b  sub     rsp, 20h
0x18000802f  mov     rdi, r8
0x180008032  mov     esi, edx
0x180008034  mov     rbx, rcx
0x180008037  call    IsQueryDeviceInformationPresent
0x18000803c  test    al, al
0x18000803e  jz      loc_1800080CA
0x180008044  lea     rdx, aOnecoremanufac; "OneCoreManufacturer"
0x18000804b  mov     rcx, rbx; String1
0x18000804e  call    cs:__imp__wcsicmp
0x180008055  nop     dword ptr [rax+rax+00h]
0x18000805a  test    eax, eax
0x18000805c  jnz     short loc_180008062
0x18000805e  xor     ecx, ecx
0x180008060  jmp     short loc_18000809E
0x180008062  lea     rdx, aOnecoremanufac_0; "OneCoreManufacturerModelName"
0x180008069  mov     rcx, rbx; String1
0x18000806c  call    cs:__imp__wcsicmp
0x180008073  nop     dword ptr [rax+rax+00h]
0x180008078  test    eax, eax
0x18000807a  jnz     short loc_180008081
0x18000807c  lea     ecx, [rax+2]
0x18000807f  jmp     short loc_18000809E
0x180008081  lea     rdx, aOnecorefwv; "OneCoreFwV"
0x180008088  mov     rcx, rbx; String1
0x18000808b  call    cs:__imp__wcsicmp
0x180008092  nop     dword ptr [rax+rax+00h]
0x180008097  test    eax, eax
0x180008099  jnz     short loc_1800080C1
0x18000809b  lea     ecx, [rax+7]
0x18000809e  mov     r8, rsi
0x1800080a1  xor     r9d, r9d
0x1800080a4  mov     rdx, rdi
0x1800080a7  call    cs:__imp_QueryDeviceInformation
0x1800080ae  nop     dword ptr [rax+rax+00h]
0x1800080b3  test    eax, eax
0x1800080b5  jle     short loc_1800080C8
0x1800080b7  movzx   eax, ax
0x1800080ba  or      eax, 80070000h
0x1800080bf  jmp     short loc_1800080C6
0x1800080c1  mov     eax, 80070057h
0x1800080c6  test    eax, eax
0x1800080c8  jns     short loc_1800080DF
0x1800080ca  mov     r9, rdi; unsigned __int16 *
0x1800080cd  lea     rcx, aSystemPlatform; "System\\Platform\\DeviceTargetingInfo"
0x1800080d4  mov     r8d, esi; unsigned int
0x1800080d7  mov     rdx, rbx; lpValue
0x1800080da  call    ?RegLookupHelper@@YAJPEBG0KPEAG@Z; RegLookupHelper(ushort const *,ushort const *,ulong,ushort *)
0x1800080df  mov     rbx, [rsp+28h+arg_0]
0x1800080e4  mov     rsi, [rsp+28h+arg_8]
0x1800080e9  add     rsp, 20h
0x1800080ed  pop     rdi
0x1800080ee  retn
```

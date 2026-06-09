# AiLogFileEvent

- ea: `0x140008f74`
- end: `0x14000901a`
- name: `AiLogFileEvent`
- size: `166`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000775c`

## callees

- `0x140008f74`
- `0x140009020`
- `0x140013b10`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x140008fd8`
- `ntdll!EtwEventWriteTransfer` at `0x140008fd8`

## pseudocode

```c
__int64 AiLogFileEvent()
{
  __int64 result; // rax
  int v1; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v2[4]; // [rsp+38h] [rbp-30h] BYREF

  v2[3] = 48;
  v2[1] = 2;
  LOWORD(v1) = 24;
  v2[0] = &v1;
  v2[2] = L"appidpolicyconverter.exe";
  result = ((__int64 (__fastcall *)(unsigned __int64, __int64 *, _QWORD, _QWORD, int, _QWORD *, int))EtwEventWriteTransfer)(
             EventHandle,
             SrpSystemComponentDisabled,
             0,
             0,
             2,
             v2,
             v1);
  if ( (int)result < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    return WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  return result;
}

```

## disassembly

```asm
0x140008f74  mov     r11, rsp
0x140008f77  sub     rsp, 68h
0x140008f7b  mov     rax, cs:__security_cookie
0x140008f82  xor     rax, rsp
0x140008f85  mov     [rsp+68h+var_10], rax
0x140008f8a  mov     ecx, 2
0x140008f8f  mov     qword ptr [r11-18h], 30h ; '0'
0x140008f97  mov     eax, 18h
0x140008f9c  mov     [r11-28h], rcx
0x140008fa0  mov     word ptr [rsp+68h+var_38], ax
0x140008fa5  lea     rdx, SrpSystemComponentDisabled
0x140008fac  lea     rax, [r11-38h]
0x140008fb0  xor     r9d, r9d
0x140008fb3  mov     [r11-30h], rax
0x140008fb7  xor     r8d, r8d
0x140008fba  mov     rax, cs:off_140017538; "appidpolicyconverter.exe"
0x140008fc1  mov     [r11-20h], rax
0x140008fc5  lea     rax, [r11-30h]
0x140008fc9  mov     [r11-40h], rax
0x140008fcd  mov     [rsp+68h+var_48], ecx
0x140008fd1  mov     rcx, cs:?EventHandle@@3_KA; unsigned __int64 EventHandle
0x140008fd8  call    cs:__imp_EtwEventWriteTransfer
0x140008fde  test    eax, eax
0x140008fe0  jns     short loc_140009008
0x140008fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fe9  lea     rdx, WPP_GLOBAL_Control
0x140008ff0  cmp     rcx, rdx
0x140008ff3  jz      short loc_140009008
0x140008ff5  test    byte ptr [rcx+1Ch], 4
0x140008ff9  jz      short loc_140009008
0x140008ffb  mov     rcx, [rcx+10h]
0x140008fff  mov     [rsp+68h+var_48], eax
0x140009003  call    WPP_SF_ZD
0x140009008  mov     rcx, [rsp+68h+var_10]
0x14000900d  xor     rcx, rsp; StackCookie
0x140009010  call    __security_check_cookie
0x140009015  add     rsp, 68h
0x140009019  retn
```

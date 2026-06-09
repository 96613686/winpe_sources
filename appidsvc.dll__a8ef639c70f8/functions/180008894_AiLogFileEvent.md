# AiLogFileEvent

- ea: `0x180008894`
- end: `0x180008948`
- name: `AiLogFileEvent`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003c80`

## callees

- `0x180008894`
- `0x1800089a4`
- `0x18000c0e0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180008902`
- `ntdll!EtwEventWriteTransfer` at `0x180008902`

## pseudocode

```c
__int64 __fastcall AiLogFileEvent(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  int v3; // edx
  unsigned __int16 v4; // ax
  int v5; // ebx
  __int64 result; // rax
  int v7; // r8d
  __int16 v8; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]

  v3 = *a3;
  v4 = *a3;
  v9[1] = 2;
  v5 = (int)a3;
  v8 = v4 >> 1;
  v9[0] = &v8;
  v9[2] = *((_QWORD *)a3 + 1);
  v10 = v3;
  v11 = 0;
  result = EtwEventWriteTransfer(AiSvcSrpEventHandle, SrpSystemComponentDisabled, 0, 0, 2, v9);
  if ( (int)result < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    return WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&WPP_GLOBAL_Control, v7, v5, result);
  }
  return result;
}

```

## disassembly

```asm
0x180008894  mov     r11, rsp
0x180008897  push    rbx
0x180008898  sub     rsp, 60h
0x18000889c  mov     rax, cs:__security_cookie
0x1800088a3  xor     rax, rsp
0x1800088a6  mov     [rsp+68h+var_10], rax
0x1800088ab  movzx   edx, word ptr [r8]
0x1800088af  mov     ecx, 2
0x1800088b4  movzx   eax, dx
0x1800088b7  mov     [r11-28h], rcx
0x1800088bb  shr     ax, 1
0x1800088be  mov     rbx, r8
0x1800088c1  mov     [rsp+68h+var_38], ax
0x1800088c6  xor     r9d, r9d
0x1800088c9  lea     rax, [r11-38h]
0x1800088cd  mov     [r11-30h], rax
0x1800088d1  mov     rax, [r8+8]
0x1800088d5  xor     r8d, r8d
0x1800088d8  mov     [r11-20h], rax
0x1800088dc  lea     rax, [r11-30h]
0x1800088e0  mov     [r11-40h], rax
0x1800088e4  mov     [rsp+68h+var_48], ecx
0x1800088e8  mov     rcx, cs:?AiSvcSrpEventHandle@@3_KA; unsigned __int64 AiSvcSrpEventHandle
0x1800088ef  mov     [rsp+68h+var_18], edx
0x1800088f3  lea     rdx, SrpSystemComponentDisabled
0x1800088fa  mov     [rsp+68h+var_14], 0
0x180008902  call    cs:__imp_EtwEventWriteTransfer
0x180008908  test    eax, eax
0x18000890a  jns     short loc_180008935
0x18000890c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008913  lea     rdx, WPP_GLOBAL_Control
0x18000891a  cmp     rcx, rdx
0x18000891d  jz      short loc_180008935
0x18000891f  test    byte ptr [rcx+1Ch], 4
0x180008923  jz      short loc_180008935
0x180008925  mov     rcx, [rcx+10h]
0x180008929  mov     r9, rbx
0x18000892c  mov     [rsp+68h+var_48], eax
0x180008930  call    WPP_SF_ZD
0x180008935  mov     rcx, [rsp+68h+var_10]
0x18000893a  xor     rcx, rsp; StackCookie
0x18000893d  call    __security_check_cookie
0x180008942  add     rsp, 60h
0x180008946  pop     rbx
0x180008947  retn
```

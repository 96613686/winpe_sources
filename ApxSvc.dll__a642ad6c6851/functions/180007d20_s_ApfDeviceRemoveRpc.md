# s_ApfDeviceRemoveRpc

- ea: `0x180007d20`
- end: `0x180007df8`
- name: `s_ApfDeviceRemoveRpc`
- size: `216`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007420`

## callees

- `0x180006140`
- `0x180007124`
- `0x180007610`
- `0x180007d20`

## import_xrefs

- `Apx01000!imp_ApxObjectDelete` at `0x180007d97`
- `Apx01000!imp_ApxObjectDelete` at `0x180007d97`

## pseudocode

```c
__int64 __fastcall s_ApfDeviceRemoveRpc(__int64 *a1)
{
  char *v2; // rcx
  __int64 v3; // rbx

  v2 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids);
    v2 = (char *)WPP_GLOBAL_Control;
  }
  v3 = *a1;
  if ( v2 != (char *)&WPP_GLOBAL_Control && v2[28] < 0 && (unsigned __int8)v2[25] >= 4u )
    WPP_SF_q(*((_QWORD *)v2 + 2), 31);
  imp_ApxObjectDelete(0, v3);
  *a1 = 0;
  if ( _InterlockedExchangeAdd(&dword_18000E4C8, 0xFFFFFFFF) == 1 )
    anonymous_namespace_::SetShutdownTimer();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp+arg_8], rbx
0x180007d25  mov     [rsp+arg_10], rsi
0x180007d2a  push    rdi
0x180007d2b  sub     rsp, 20h
0x180007d2f  mov     rdi, rcx
0x180007d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d39  lea     rsi, WPP_GLOBAL_Control
0x180007d40  cmp     rcx, rsi
0x180007d43  jz      short loc_180007D6D
0x180007d45  test    byte ptr [rcx+1Ch], 1
0x180007d49  jz      short loc_180007D6D
0x180007d4b  cmp     byte ptr [rcx+19h], 5
0x180007d4f  jb      short loc_180007D6D
0x180007d51  mov     rcx, [rcx+10h]
0x180007d55  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x180007d5c  mov     edx, 1Eh
0x180007d61  call    WPP_SF_
0x180007d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d6d  mov     rbx, [rdi]
0x180007d70  cmp     rcx, rsi
0x180007d73  jz      short loc_180007D92
0x180007d75  test    byte ptr [rcx+1Ch], 80h
0x180007d79  jz      short loc_180007D92
0x180007d7b  cmp     byte ptr [rcx+19h], 4
0x180007d7f  jb      short loc_180007D92
0x180007d81  mov     rcx, [rcx+10h]
0x180007d85  mov     edx, 1Fh
0x180007d8a  mov     r9, rbx
0x180007d8d  call    WPP_SF_q
0x180007d92  mov     rdx, rbx
0x180007d95  xor     ecx, ecx
0x180007d97  call    cs:__imp_imp_ApxObjectDelete
0x180007d9d  or      eax, 0FFFFFFFFh
0x180007da0  mov     qword ptr [rdi], 0
0x180007da7  lock xadd cs:dword_18000E4C8, eax
0x180007daf  cmp     eax, 1
0x180007db2  jnz     short loc_180007DB9
0x180007db4  call    _anonymous_namespace___SetShutdownTimer
0x180007db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dc0  cmp     rcx, rsi
0x180007dc3  jz      short loc_180007DE6
0x180007dc5  test    byte ptr [rcx+1Ch], 1
0x180007dc9  jz      short loc_180007DE6
0x180007dcb  cmp     byte ptr [rcx+19h], 5
0x180007dcf  jb      short loc_180007DE6
0x180007dd1  mov     rcx, [rcx+10h]
0x180007dd5  lea     r8, WPP_f6dcdc45f51737ce5ae61d05ae8073f7_Traceguids
0x180007ddc  mov     edx, 20h ; ' '
0x180007de1  call    WPP_SF_
0x180007de6  mov     rbx, [rsp+28h+arg_8]
0x180007deb  xor     eax, eax
0x180007ded  mov     rsi, [rsp+28h+arg_10]
0x180007df2  add     rsp, 20h
0x180007df6  pop     rdi
0x180007df7  retn
```

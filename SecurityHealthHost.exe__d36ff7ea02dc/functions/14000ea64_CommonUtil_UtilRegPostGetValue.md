# CommonUtil::UtilRegPostGetValue

- ea: `0x14000ea64`
- end: `0x14000eb40`
- name: `CommonUtil::UtilRegPostGetValue`
- size: `220`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned int, _QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e35c`

## callees

- `0x14000cfa0`
- `0x14000df84`
- `0x14000e16c`
- `0x14000e6b4`
- `0x14000ea64`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegPostGetValue(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned __int64 a5)
{
  __int64 result; // rax
  int v9; // ecx
  int v10; // eax

  if ( !a5 )
    return 0;
  if ( a3 - 1 <= 1 )
  {
    LODWORD(result) = MpUtilsExports::RegAdjustStringValue(a2 >> 1, a5, a4);
  }
  else
  {
    if ( a3 != 7 )
    {
LABEL_12:
      if ( (unsigned int)MpUtilsExports::UtilRegIsValidValueImpl((MpUtilsExports *)a3, *a4, a5, a4) )
        return 0;
      goto LABEL_13;
    }
    LODWORD(result) = MpUtilsExports::RegAdjustMultiStringValue(a2 >> 1, a5, a4);
  }
  v9 = result;
  if ( !(_DWORD)result || (_DWORD)result == -2147024662 )
    return (unsigned int)result;
  v10 = 0;
  if ( v9 == -2147019873 )
    v10 = -2147019873;
  if ( v10 != -2147019873 )
    goto LABEL_12;
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_473dbbf2212f33a3d422106396b3062c_Traceguids, a1);
  return 2147947423LL;
}

```

## disassembly

```asm
0x14000ea64  mov     [rsp+arg_0], rbx
0x14000ea69  mov     [rsp+arg_8], rbp
0x14000ea6e  push    rsi
0x14000ea6f  sub     rsp, 20h
0x14000ea73  cmp     [rsp+28h+arg_20], 0
0x14000ea79  mov     rsi, r9
0x14000ea7c  mov     ebx, r8d
0x14000ea7f  mov     r10, rdx
0x14000ea82  mov     rbp, rcx
0x14000ea85  jnz     short loc_14000EA8E
0x14000ea87  xor     eax, eax
0x14000ea89  jmp     loc_14000EB30
0x14000ea8e  lea     eax, [r8-1]
0x14000ea92  cmp     eax, 1
0x14000ea95  jbe     short loc_14000EAB1
0x14000ea97  cmp     ebx, 7
0x14000ea9a  jnz     short loc_14000EAE3
0x14000ea9c  mov     rdx, [rsp+28h+arg_20]
0x14000eaa1  mov     r8, rsi
0x14000eaa4  shr     r10, 1
0x14000eaa7  mov     rcx, r10
0x14000eaaa  call    MpUtilsExports__RegAdjustMultiStringValue
0x14000eaaf  jmp     short loc_14000EAC4
0x14000eab1  mov     rdx, [rsp+28h+arg_20]
0x14000eab6  mov     r8, rsi
0x14000eab9  shr     r10, 1
0x14000eabc  mov     rcx, r10
0x14000eabf  call    MpUtilsExports__RegAdjustStringValue
0x14000eac4  mov     ecx, eax
0x14000eac6  test    eax, eax
0x14000eac8  jz      short loc_14000EB2E
0x14000eaca  cmp     eax, 800700EAh
0x14000eacf  jz      short loc_14000EB2E
0x14000ead1  xor     eax, eax
0x14000ead3  cmp     ecx, 8007139Fh
0x14000ead9  cmovz   eax, ecx
0x14000eadc  cmp     eax, 8007139Fh
0x14000eae1  jz      short loc_14000EAF6
0x14000eae3  mov     r8, [rsp+28h+arg_20]; unsigned __int64
0x14000eae8  mov     ecx, ebx; this
0x14000eaea  mov     rdx, [rsi]; unsigned int
0x14000eaed  call    ?UtilRegIsValidValueImpl@MpUtilsExports@@YAHK_KPEBX@Z; MpUtilsExports::UtilRegIsValidValueImpl(ulong,unsigned __int64,void const *)
0x14000eaf2  test    eax, eax
0x14000eaf4  jnz     short loc_14000EA87
0x14000eaf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eafd  lea     rdx, WPP_GLOBAL_Control
0x14000eb04  cmp     rcx, rdx
0x14000eb07  jz      short loc_14000EB27
0x14000eb09  test    byte ptr [rcx+1Ch], 1
0x14000eb0d  jz      short loc_14000EB27
0x14000eb0f  mov     rcx, [rcx+10h]
0x14000eb13  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000eb1a  mov     edx, 16h
0x14000eb1f  mov     r9, rbp
0x14000eb22  call    WPP_SF_S
0x14000eb27  mov     eax, 8007139Fh
0x14000eb2c  jmp     short loc_14000EB30
0x14000eb2e  mov     eax, ecx
0x14000eb30  mov     rbx, [rsp+28h+arg_0]
0x14000eb35  mov     rbp, [rsp+28h+arg_8]
0x14000eb3a  add     rsp, 20h
0x14000eb3e  pop     rsi
0x14000eb3f  retn
```

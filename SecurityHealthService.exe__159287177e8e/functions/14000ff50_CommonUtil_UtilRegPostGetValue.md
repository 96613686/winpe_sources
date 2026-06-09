# CommonUtil::UtilRegPostGetValue

- ea: `0x14000ff50`
- end: `0x14001002c`
- name: `CommonUtil::UtilRegPostGetValue`
- size: `220`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned int, _QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f7d0`

## callees

- `0x140005394`
- `0x14000f4f8`
- `0x14000f6e0`
- `0x14000fba0`
- `0x14000ff50`

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
0x14000ff50  mov     [rsp+arg_0], rbx
0x14000ff55  mov     [rsp+arg_8], rbp
0x14000ff5a  push    rsi
0x14000ff5b  sub     rsp, 20h
0x14000ff5f  cmp     [rsp+28h+arg_20], 0
0x14000ff65  mov     rsi, r9
0x14000ff68  mov     ebx, r8d
0x14000ff6b  mov     r10, rdx
0x14000ff6e  mov     rbp, rcx
0x14000ff71  jnz     short loc_14000FF7A
0x14000ff73  xor     eax, eax
0x14000ff75  jmp     loc_14001001C
0x14000ff7a  lea     eax, [r8-1]
0x14000ff7e  cmp     eax, 1
0x14000ff81  jbe     short loc_14000FF9D
0x14000ff83  cmp     ebx, 7
0x14000ff86  jnz     short loc_14000FFCF
0x14000ff88  mov     rdx, [rsp+28h+arg_20]
0x14000ff8d  mov     r8, rsi
0x14000ff90  shr     r10, 1
0x14000ff93  mov     rcx, r10
0x14000ff96  call    MpUtilsExports__RegAdjustMultiStringValue
0x14000ff9b  jmp     short loc_14000FFB0
0x14000ff9d  mov     rdx, [rsp+28h+arg_20]
0x14000ffa2  mov     r8, rsi
0x14000ffa5  shr     r10, 1
0x14000ffa8  mov     rcx, r10
0x14000ffab  call    MpUtilsExports__RegAdjustStringValue
0x14000ffb0  mov     ecx, eax
0x14000ffb2  test    eax, eax
0x14000ffb4  jz      short loc_14001001A
0x14000ffb6  cmp     eax, 800700EAh
0x14000ffbb  jz      short loc_14001001A
0x14000ffbd  xor     eax, eax
0x14000ffbf  cmp     ecx, 8007139Fh
0x14000ffc5  cmovz   eax, ecx
0x14000ffc8  cmp     eax, 8007139Fh
0x14000ffcd  jz      short loc_14000FFE2
0x14000ffcf  mov     r8, [rsp+28h+arg_20]; unsigned __int64
0x14000ffd4  mov     ecx, ebx; this
0x14000ffd6  mov     rdx, [rsi]; unsigned int
0x14000ffd9  call    ?UtilRegIsValidValueImpl@MpUtilsExports@@YAHK_KPEBX@Z; MpUtilsExports::UtilRegIsValidValueImpl(ulong,unsigned __int64,void const *)
0x14000ffde  test    eax, eax
0x14000ffe0  jnz     short loc_14000FF73
0x14000ffe2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ffe9  lea     rdx, WPP_GLOBAL_Control
0x14000fff0  cmp     rcx, rdx
0x14000fff3  jz      short loc_140010013
0x14000fff5  test    byte ptr [rcx+1Ch], 1
0x14000fff9  jz      short loc_140010013
0x14000fffb  mov     rcx, [rcx+10h]
0x14000ffff  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x140010006  mov     edx, 16h
0x14001000b  mov     r9, rbp
0x14001000e  call    WPP_SF_S
0x140010013  mov     eax, 8007139Fh
0x140010018  jmp     short loc_14001001C
0x14001001a  mov     eax, ecx
0x14001001c  mov     rbx, [rsp+28h+arg_0]
0x140010021  mov     rbp, [rsp+28h+arg_8]
0x140010026  add     rsp, 20h
0x14001002a  pop     rsi
0x14001002b  retn
```

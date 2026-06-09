# CommonUtil::UtilRegPostGetValue

- ea: `0x140005050`
- end: `0x1400050f8`
- name: `CommonUtil::UtilRegPostGetValue`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004dc0`

## callees

- `0x1400024e8`
- `0x14000253c`
- `0x140005050`
- `0x14001dac4`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegPostGetValue(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned __int64 a5)
{
  __int64 result; // rax
  const void *v9; // r9
  int v10; // ecx
  int v11; // eax
  unsigned __int64 *v12; // [rsp+20h] [rbp-8h]

  if ( !a5 )
    return 0;
  result = CommonUtil::UtilRegAdjustValue((CommonUtil *)a3, a2, a5, a4, v12);
  v10 = result;
  if ( (_DWORD)result && (_DWORD)result != -2147024662 )
  {
    v11 = 0;
    if ( v10 == -2147019873 )
      v11 = -2147019873;
    if ( v11 != -2147019873 && CommonUtil::UtilRegIsValidValue((CommonUtil *)a3, *a4, a5, v9) )
      return 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids, a1);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x140005050  mov     [rsp+arg_0], rbp
0x140005055  mov     [rsp+arg_8], rsi
0x14000505a  push    rdi; unsigned __int64 *
0x14000505b  sub     rsp, 20h
0x14000505f  cmp     [rsp+28h+arg_20], 0
0x140005065  mov     rdi, r9
0x140005068  mov     esi, r8d
0x14000506b  mov     rbp, rcx
0x14000506e  jnz     short loc_140005074
0x140005070  xor     eax, eax
0x140005072  jmp     short loc_1400050E8
0x140005074  mov     r8, [rsp+28h+arg_20]; unsigned __int64
0x140005079  mov     ecx, esi; this
0x14000507b  call    ?UtilRegAdjustValue@CommonUtil@@YAJK_KPEAXPEA_K@Z; CommonUtil::UtilRegAdjustValue(ulong,unsigned __int64,void *,unsigned __int64 *)
0x140005080  mov     ecx, eax
0x140005082  test    eax, eax
0x140005084  jz      short loc_1400050E8
0x140005086  cmp     eax, 800700EAh
0x14000508b  jz      short loc_1400050E8
0x14000508d  xor     eax, eax
0x14000508f  cmp     ecx, 8007139Fh
0x140005095  cmovz   eax, ecx
0x140005098  cmp     eax, 8007139Fh
0x14000509d  jz      short loc_1400050B2
0x14000509f  mov     r8, [rsp+28h+arg_20]; unsigned __int64
0x1400050a4  mov     ecx, esi; this
0x1400050a6  mov     rdx, [rdi]; unsigned int
0x1400050a9  call    ?UtilRegIsValidValue@CommonUtil@@YA_NK_KPEBX@Z; CommonUtil::UtilRegIsValidValue(ulong,unsigned __int64,void const *)
0x1400050ae  test    al, al
0x1400050b0  jnz     short loc_140005070
0x1400050b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050b9  lea     rax, WPP_GLOBAL_Control
0x1400050c0  cmp     rcx, rax
0x1400050c3  jz      short loc_1400050E3
0x1400050c5  test    byte ptr [rcx+1Ch], 1
0x1400050c9  jz      short loc_1400050E3
0x1400050cb  mov     rcx, [rcx+10h]
0x1400050cf  lea     r8, WPP_4145d653138e3b1ee6f2a9af82386a7e_Traceguids
0x1400050d6  mov     edx, 16h
0x1400050db  mov     r9, rbp
0x1400050de  call    WPP_SF_S
0x1400050e3  mov     eax, 8007139Fh
0x1400050e8  mov     rbp, [rsp+28h+arg_0]
0x1400050ed  mov     rsi, [rsp+28h+arg_8]
0x1400050f2  add     rsp, 20h
0x1400050f6  pop     rdi
0x1400050f7  retn
```

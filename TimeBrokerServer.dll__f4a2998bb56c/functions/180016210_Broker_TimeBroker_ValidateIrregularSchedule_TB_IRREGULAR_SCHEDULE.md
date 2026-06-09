# Broker::TimeBroker::ValidateIrregularSchedule(_TB_IRREGULAR_SCHEDULE)

- ea: `0x180016210`
- end: `0x180016423`
- name: `?ValidateIrregularSchedule@TimeBroker@Broker@@AEAAXU_TB_IRREGULAR_SCHEDULE@@@Z`
- size: `531`
- prototype: `char __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x180003800`
- `0x18001136c`
- `0x180013978`
- `0x180016210`

## pseudocode

```c
char __fastcall Broker::TimeBroker::ValidateIrregularSchedule(__int64 a1, unsigned int *a2)
{
  __int64 v2; // r9
  unsigned __int16 v3; // ax
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-20h] BYREF

  v2 = *a2;
  LOBYTE(v3) = 0;
  if ( (_DWORD)v2 )
  {
    switch ( (_DWORD)v2 )
    {
      case 1:
        if ( !*((_WORD *)a2 + 4) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
          Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        break;
      case 2:
        if ( !*((_BYTE *)a2 + 8) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
          Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        LOBYTE(v3) = *((_BYTE *)a2 + 9) - 1;
        if ( (unsigned __int8)v3 > 0x7Eu )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              92,
              &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
              *((unsigned __int8 *)a2 + 9));
          Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        break;
      case 3:
        if ( !a2[2] )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, 0);
          Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        v3 = *((_WORD *)a2 + 6) - 1;
        if ( v3 > 0xFFEu )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              94,
              &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
              *((unsigned __int16 *)a2 + 6));
          Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
          throw (Broker::InvalidParameter *)pExceptionObject;
        }
        break;
      case 4:
        break;
      default:
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v2);
        Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
        throw (Broker::InvalidParameter *)pExceptionObject;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180016210  push    rbp
0x180016212  mov     rbp, rsp
0x180016215  sub     rsp, 40h
0x180016219  mov     r9d, [rdx]
0x18001621c  xor     eax, eax
0x18001621e  mov     ecx, r9d
0x180016221  test    r9d, r9d
0x180016224  jz      short loc_18001627E
0x180016226  sub     ecx, 1
0x180016229  jz      short loc_180016274
0x18001622b  sub     ecx, 1
0x18001622e  jz      short loc_18001625C
0x180016230  sub     ecx, 1
0x180016233  jz      short loc_18001623C
0x180016235  cmp     ecx, 1
0x180016238  jnz     short loc_180016284
0x18001623a  jmp     short loc_18001627E
0x18001623c  cmp     [rdx+8], eax
0x18001623f  jz      loc_1800162C6
0x180016245  movzx   eax, word ptr [rdx+0Ch]
0x180016249  mov     ecx, 0FFEh
0x18001624e  dec     ax
0x180016251  cmp     ax, cx
0x180016254  ja      loc_18001630B
0x18001625a  jmp     short loc_18001627E
0x18001625c  cmp     [rdx+8], al
0x18001625f  jz      loc_180016352
0x180016265  mov     al, [rdx+9]
0x180016268  dec     al
0x18001626a  cmp     al, 7Eh ; '~'
0x18001626c  ja      loc_180016397
0x180016272  jmp     short loc_18001627E
0x180016274  cmp     [rdx+8], ax
0x180016278  jz      loc_1800163DE
0x18001627e  add     rsp, 40h
0x180016282  pop     rbp
0x180016283  retn
0x180016284  mov     rcx, cs:WPP_GLOBAL_Control
0x18001628b  test    byte ptr [rcx+1Ch], 20h
0x18001628f  jz      short loc_1800162AC
0x180016291  cmp     byte ptr [rcx+19h], 2
0x180016295  jb      short loc_1800162AC
0x180016297  mov     rcx, [rcx+10h]
0x18001629b  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800162a2  mov     edx, 5Fh ; '_'
0x1800162a7  call    WPP_SF_d
0x1800162ac  lea     rcx, [rbp+pExceptionObject]; this
0x1800162b0  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x1800162b5  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800162bc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800162c0  call    _CxxThrowException_0
0x1800162c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162cd  test    byte ptr [rcx+1Ch], 20h
0x1800162d1  jz      short loc_1800162F1
0x1800162d3  cmp     byte ptr [rcx+19h], 2
0x1800162d7  jb      short loc_1800162F1
0x1800162d9  mov     rcx, [rcx+10h]
0x1800162dd  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800162e4  mov     edx, 5Dh ; ']'
0x1800162e9  xor     r9d, r9d
0x1800162ec  call    WPP_SF_d
0x1800162f1  lea     rcx, [rbp+pExceptionObject]; this
0x1800162f5  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x1800162fa  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180016301  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016305  call    _CxxThrowException_0
0x18001630b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016312  test    byte ptr [rcx+1Ch], 20h
0x180016316  jz      short loc_180016338
0x180016318  cmp     byte ptr [rcx+19h], 2
0x18001631c  jb      short loc_180016338
0x18001631e  movzx   r9d, word ptr [rdx+0Ch]
0x180016323  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001632a  mov     rcx, [rcx+10h]
0x18001632e  mov     edx, 5Eh ; '^'
0x180016333  call    WPP_SF_d
0x180016338  lea     rcx, [rbp+pExceptionObject]; this
0x18001633c  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x180016341  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180016348  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001634c  call    _CxxThrowException_0
0x180016352  mov     rcx, cs:WPP_GLOBAL_Control
0x180016359  test    byte ptr [rcx+1Ch], 20h
0x18001635d  jz      short loc_18001637D
0x18001635f  cmp     byte ptr [rcx+19h], 2
0x180016363  jb      short loc_18001637D
0x180016365  mov     rcx, [rcx+10h]
0x180016369  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180016370  mov     edx, 5Bh ; '['
0x180016375  xor     r9d, r9d
0x180016378  call    WPP_SF_d
0x18001637d  lea     rcx, [rbp+pExceptionObject]; this
0x180016381  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x180016386  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001638d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016391  call    _CxxThrowException_0
0x180016397  mov     rcx, cs:WPP_GLOBAL_Control
0x18001639e  test    byte ptr [rcx+1Ch], 20h
0x1800163a2  jz      short loc_1800163C4
0x1800163a4  cmp     byte ptr [rcx+19h], 2
0x1800163a8  jb      short loc_1800163C4
0x1800163aa  movzx   r9d, byte ptr [rdx+9]
0x1800163af  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800163b6  mov     rcx, [rcx+10h]
0x1800163ba  mov     edx, 5Ch ; '\'
0x1800163bf  call    WPP_SF_d
0x1800163c4  lea     rcx, [rbp+pExceptionObject]; this
0x1800163c8  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x1800163cd  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800163d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800163d8  call    _CxxThrowException_0
0x1800163de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163e5  test    byte ptr [rcx+1Ch], 20h
0x1800163e9  jz      short loc_180016409
0x1800163eb  cmp     byte ptr [rcx+19h], 2
0x1800163ef  jb      short loc_180016409
0x1800163f1  mov     rcx, [rcx+10h]
0x1800163f5  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800163fc  mov     edx, 5Ah ; 'Z'
0x180016401  xor     r9d, r9d
0x180016404  call    WPP_SF_d
0x180016409  lea     rcx, [rbp+pExceptionObject]; this
0x18001640d  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x180016412  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x180016419  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001641d  call    _CxxThrowException_0
```

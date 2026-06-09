# imp_ApxBindClient

- ea: `0x18000a200`
- end: `0x18000a4c0`
- name: `imp_ApxBindClient`
- size: `704`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a12c`
- `0x18000a154`
- `0x18000a1b4`
- `0x18000a200`
- `0x18000a8e8`

## string_xrefs

- `0x18000a24d`: `Config`

## pseudocode

```c
__int64 __fastcall imp_ApxBindClient(Apx::ApfVerify *this, __int64 a2, const unsigned __int16 *a3)
{
  unsigned int IsNotNull; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids);
  }
  IsNotNull = Apx::ApfVerify::IsNotNull(this, L"Config", a3);
  if ( (IsNotNull & 0x80000000) != 0 )
    goto LABEL_54;
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( g_ApfFrameworkInitialized )
  {
    v8 = *(_DWORD *)this;
    v9 = 32;
    if ( *(_DWORD *)this == 32 )
    {
      v11 = *((unsigned int *)this + 1);
      if ( (_DWORD)v11 )
      {
        IsNotNull = -2147024809;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return IsNotNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_55;
        WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids, v11, 0);
        goto LABEL_54;
      }
      v12 = *((unsigned int *)this + 2);
      if ( (_DWORD)v12 != 1 )
      {
        IsNotNull = -2147024809;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return IsNotNull;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_55;
        WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids, v12, 1);
        goto LABEL_54;
      }
      v9 = *((unsigned int *)this + 4);
      v8 = *((_DWORD *)this + 3);
      if ( v8 == (_DWORD)v9 )
      {
        if ( v8 > 1 )
        {
          IsNotNull = -2147024809;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return IsNotNull;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_55;
          WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids, 1, 1);
          goto LABEL_54;
        }
        if ( *((_QWORD *)this + 3) )
        {
          IsNotNull = -2147024809;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return IsNotNull;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_55;
          v7 = 17;
        }
        else
        {
          if ( _InterlockedCompareExchange(&g_ApfClientCount, 1, 0) <= 0 )
          {
            if ( a2 )
            {
              *(_DWORD *)a2 = 1;
              *(_DWORD *)(a2 + 4) = 1;
            }
            IsNotNull = 0;
            goto LABEL_54;
          }
          IsNotNull = -2147024891;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return IsNotNull;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_55;
          v7 = 18;
        }
        goto LABEL_13;
      }
      IsNotNull = -2147024809;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return IsNotNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v10 = 15;
    }
    else
    {
      IsNotNull = -2147024809;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return IsNotNull;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v10 = 12;
    }
    WPP_SF_DDd(v6[2], v10, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids, v9, v8);
    goto LABEL_54;
  }
  IsNotNull = -2147024886;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return IsNotNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 11;
LABEL_13:
    WPP_SF_d(v6[2], v7, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids);
LABEL_54:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_(v6[2], 19, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids);
  return IsNotNull;
}

```

## disassembly

```asm
0x18000a200  push    rbx
0x18000a202  push    rbp
0x18000a203  push    rsi
0x18000a204  push    rdi
0x18000a205  push    r14
0x18000a207  push    r15
0x18000a209  sub     rsp, 38h
0x18000a20d  mov     rsi, rdx
0x18000a210  mov     rdi, rcx
0x18000a213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a21a  lea     r14, WPP_GLOBAL_Control
0x18000a221  lea     r15, WPP_6ef29a82e1583fbb046b3e073edb58f2_Traceguids
0x18000a228  mov     ebp, 1
0x18000a22d  cmp     rcx, r14
0x18000a230  jz      short loc_18000A24D
0x18000a232  test    [rcx+1Ch], bpl
0x18000a236  jz      short loc_18000A24D
0x18000a238  cmp     byte ptr [rcx+19h], 5
0x18000a23c  jb      short loc_18000A24D
0x18000a23e  mov     rcx, [rcx+10h]
0x18000a242  lea     edx, [rbp+9]
0x18000a245  mov     r8, r15
0x18000a248  call    WPP_SF_
0x18000a24d  lea     rdx, aConfig_0; "Config"
0x18000a254  mov     rcx, rdi; this
0x18000a257  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18000a25c  xor     r8d, r8d
0x18000a25f  mov     ebx, eax
0x18000a261  test    eax, eax
0x18000a263  js      loc_18000A488
0x18000a269  test    rsi, rsi
0x18000a26c  jz      short loc_18000A271
0x18000a26e  mov     [rsi], r8
0x18000a271  cmp     cs:?g_ApfFrameworkInitialized@@3_NA, r8b; bool g_ApfFrameworkInitialized
0x18000a278  jnz     short loc_18000A2BC
0x18000a27a  mov     ebx, 8007000Ah
0x18000a27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a286  cmp     rcx, r14
0x18000a289  jz      loc_18000A4B1
0x18000a28f  test    byte ptr [rcx+1Ch], 40h
0x18000a293  jz      loc_18000A48F
0x18000a299  cmp     byte ptr [rcx+19h], 2
0x18000a29d  jb      loc_18000A48F
0x18000a2a3  mov     edx, 0Bh
0x18000a2a8  mov     rcx, [rcx+10h]
0x18000a2ac  mov     r9d, ebx
0x18000a2af  mov     r8, r15
0x18000a2b2  call    WPP_SF_d
0x18000a2b7  jmp     loc_18000A488
0x18000a2bc  mov     eax, [rdi]
0x18000a2be  mov     r9d, 20h ; ' '
0x18000a2c4  cmp     eax, r9d
0x18000a2c7  jz      short loc_18000A30B
0x18000a2c9  mov     ebx, 80070057h
0x18000a2ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2d5  cmp     rcx, r14
0x18000a2d8  jz      loc_18000A4B1
0x18000a2de  test    byte ptr [rcx+1Ch], 40h
0x18000a2e2  jz      loc_18000A48F
0x18000a2e8  cmp     byte ptr [rcx+19h], 2
0x18000a2ec  jb      loc_18000A48F
0x18000a2f2  lea     edx, [r9-14h]
0x18000a2f6  mov     [rsp+68h+var_48], eax
0x18000a2fa  mov     rcx, [rcx+10h]
0x18000a2fe  mov     r8, r15
0x18000a301  call    WPP_SF_DDd
0x18000a306  jmp     loc_18000A488
0x18000a30b  mov     r9d, [rdi+4]
0x18000a30f  test    r9d, r9d
0x18000a312  jz      short loc_18000A358
0x18000a314  mov     ebx, 80070057h
0x18000a319  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a320  cmp     rcx, r14
0x18000a323  jz      loc_18000A4B1
0x18000a329  test    byte ptr [rcx+1Ch], 40h
0x18000a32d  jz      loc_18000A48F
0x18000a333  cmp     byte ptr [rcx+19h], 2
0x18000a337  jb      loc_18000A48F
0x18000a33d  mov     rcx, [rcx+10h]
0x18000a341  mov     edx, 0Dh
0x18000a346  mov     [rsp+68h+var_48], r8d
0x18000a34b  mov     r8, r15
0x18000a34e  call    WPP_SF_DDd
0x18000a353  jmp     loc_18000A488
0x18000a358  mov     r9d, [rdi+8]
0x18000a35c  cmp     r9d, ebp
0x18000a35f  jz      short loc_18000A398
0x18000a361  mov     ebx, 80070057h
0x18000a366  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a36d  cmp     rcx, r14
0x18000a370  jz      loc_18000A4B1
0x18000a376  test    byte ptr [rcx+1Ch], 40h
0x18000a37a  jz      loc_18000A48F
0x18000a380  cmp     byte ptr [rcx+19h], 2
0x18000a384  jb      loc_18000A48F
0x18000a38a  mov     edx, 0Eh
0x18000a38f  mov     [rsp+68h+var_48], ebp
0x18000a393  jmp     loc_18000A2FA
0x18000a398  mov     r9d, [rdi+10h]
0x18000a39c  mov     eax, [rdi+0Ch]
0x18000a39f  cmp     eax, r9d
0x18000a3a2  jz      short loc_18000A3D7
0x18000a3a4  mov     ebx, 80070057h
0x18000a3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3b0  cmp     rcx, r14
0x18000a3b3  jz      loc_18000A4B1
0x18000a3b9  test    byte ptr [rcx+1Ch], 40h
0x18000a3bd  jz      loc_18000A48F
0x18000a3c3  cmp     byte ptr [rcx+19h], 2
0x18000a3c7  jb      loc_18000A48F
0x18000a3cd  mov     edx, 0Fh
0x18000a3d2  jmp     loc_18000A2F6
0x18000a3d7  cmp     eax, ebp
0x18000a3d9  jbe     short loc_18000A415
0x18000a3db  mov     ebx, 80070057h
0x18000a3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3e7  cmp     rcx, r14
0x18000a3ea  jz      loc_18000A4B1
0x18000a3f0  test    byte ptr [rcx+1Ch], 40h
0x18000a3f4  jz      loc_18000A48F
0x18000a3fa  cmp     byte ptr [rcx+19h], 2
0x18000a3fe  jb      loc_18000A48F
0x18000a404  mov     edx, 10h
0x18000a409  mov     [rsp+68h+var_48], ebp
0x18000a40d  mov     r9d, ebp
0x18000a410  jmp     loc_18000A2FA
0x18000a415  cmp     [rdi+18h], r8
0x18000a419  jz      short loc_18000A446
0x18000a41b  mov     ebx, 80070057h
0x18000a420  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a427  cmp     rcx, r14
0x18000a42a  jz      loc_18000A4B1
0x18000a430  test    byte ptr [rcx+1Ch], 40h
0x18000a434  jz      short loc_18000A48F
0x18000a436  cmp     byte ptr [rcx+19h], 2
0x18000a43a  jb      short loc_18000A48F
0x18000a43c  mov     edx, 11h
0x18000a441  jmp     loc_18000A2A8
0x18000a446  xor     eax, eax
0x18000a448  lock cmpxchg cs:?g_ApfClientCount@@3JA, ebp; long g_ApfClientCount
0x18000a450  test    eax, eax
0x18000a452  jle     short loc_18000A47B
0x18000a454  mov     ebx, 80070005h
0x18000a459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a460  cmp     rcx, r14
0x18000a463  jz      short loc_18000A4B1
0x18000a465  test    byte ptr [rcx+1Ch], 40h
0x18000a469  jz      short loc_18000A48F
0x18000a46b  cmp     byte ptr [rcx+19h], 2
0x18000a46f  jb      short loc_18000A48F
0x18000a471  mov     edx, 12h
0x18000a476  jmp     loc_18000A2A8
0x18000a47b  test    rsi, rsi
0x18000a47e  jz      short loc_18000A485
0x18000a480  mov     [rsi], ebp
0x18000a482  mov     [rsi+4], ebp
0x18000a485  mov     ebx, r8d
0x18000a488  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a48f  cmp     rcx, r14
0x18000a492  jz      short loc_18000A4B1
0x18000a494  test    [rcx+1Ch], bpl
0x18000a498  jz      short loc_18000A4B1
0x18000a49a  cmp     byte ptr [rcx+19h], 5
0x18000a49e  jb      short loc_18000A4B1
0x18000a4a0  mov     rcx, [rcx+10h]
0x18000a4a4  mov     edx, 13h
0x18000a4a9  mov     r8, r15
0x18000a4ac  call    WPP_SF_
0x18000a4b1  mov     eax, ebx
0x18000a4b3  add     rsp, 38h
0x18000a4b7  pop     r15
0x18000a4b9  pop     r14
0x18000a4bb  pop     rdi
0x18000a4bc  pop     rsi
0x18000a4bd  pop     rbp
0x18000a4be  pop     rbx
0x18000a4bf  retn
```

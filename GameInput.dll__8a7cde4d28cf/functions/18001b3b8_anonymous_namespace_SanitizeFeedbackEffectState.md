# _anonymous_namespace_::SanitizeFeedbackEffectState

- ea: `0x18001b3b8`
- end: `0x18001b550`
- name: `_anonymous_namespace_::SanitizeFeedbackEffectState`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019b5c`
- `0x180020220`

## callees

- `0x180001414`
- `0x18001b3b8`
- `0x18004c8e0`

## string_xrefs

- `0x18001b4e2`: `onecore\xbox\gameinput\feedback\FeedbackParamsCache.cpp`

## pseudocode

```c
char __fastcall anonymous_namespace_::SanitizeFeedbackEffectState(
        unsigned __int64 a1,
        __int64 a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v3; // r10
  __int64 v4; // r9
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-59h] BYREF
  __int64 v9; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int64 v10; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp-41h] BYREF
  char v12[32]; // [rsp+50h] [rbp-39h] BYREF
  const char *v13; // [rsp+70h] [rbp-19h]
  __int64 v14; // [rsp+78h] [rbp-11h]
  int *v15; // [rsp+80h] [rbp-9h]
  __int64 v16; // [rsp+88h] [rbp-1h]
  const char *v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+98h] [rbp+Fh]
  unsigned __int64 *v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+A8h] [rbp+1Fh]
  unsigned __int64 *v21; // [rsp+B0h] [rbp+27h]
  __int64 v22; // [rsp+B8h] [rbp+2Fh]
  __int64 *v23; // [rsp+C0h] [rbp+37h]
  __int64 v24; // [rsp+C8h] [rbp+3Fh]

  v3 = *a3;
  v4 = *a3 & 7;
  if ( (*(_BYTE *)a3 & 4) != 0 )
    LODWORD(v4) = v4 | 0xFFFFFFF8;
  if ( (_DWORD)v4 && ((unsigned int)(v4 - 1) > 1 || v3 < 8) )
  {
    v3 = 0;
    *a3 = 0;
  }
  v5 = v3;
  if ( a2 )
  {
    if ( v3 >> 3 )
    {
      v5 = v3 & 7 | (8 * ((v3 >> 3) - a2));
      *a3 = v5;
    }
    else
    {
      v5 = v3;
    }
  }
  v6 = v5 >> 3;
  if ( v6 > a1 )
  {
    *a3 = 0;
    LOBYTE(v6) = byte_1800697B8;
    byte_1800697B8 = 1;
    if ( !(_BYTE)v6 )
    {
      LOBYTE(v6) = dword_180069000;
      if ( (unsigned int)dword_180069000 > 2 )
      {
        LOBYTE(v6) = qword_180069010;
        if ( (qword_180069010 & 8) != 0 )
        {
          v6 = qword_180069018 & 8;
          if ( v6 == qword_180069018 )
          {
            v10 = *a3 >> 3;
            v9 = a2;
            v23 = &v9;
            v11 = a1;
            v21 = &v10;
            v19 = &v11;
            v17 = "Invalid future client timestamp detected";
            v15 = &v8;
            v13 = "onecore\\xbox\\gameinput\\feedback\\FeedbackParamsCache.cpp";
            v8 = 179;
            v24 = 8;
            v22 = 8;
            v20 = 8;
            v18 = 41;
            v16 = 4;
            v14 = 56;
            LOBYTE(v6) = tlgWriteTransfer_GameInputEventWriteTransfer(
                           (__int64)&dword_180069000,
                           (unsigned __int8 *)byte_18005A383,
                           0,
                           0,
                           8,
                           (__int64)v12);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001b3b8  push    rbp
0x18001b3ba  lea     rbp, [rsp-57h]
0x18001b3bf  sub     rsp, 0E0h
0x18001b3c6  mov     rax, cs:__security_cookie
0x18001b3cd  xor     rax, rsp
0x18001b3d0  mov     [rbp+57h+var_10], rax
0x18001b3d4  mov     r10, [r8]
0x18001b3d7  mov     r11, rcx
0x18001b3da  mov     r9, r10
0x18001b3dd  and     r9d, 7
0x18001b3e1  test    r9b, 4
0x18001b3e5  jz      short loc_18001B3EF
0x18001b3e7  mov     eax, 0FFFFFFF8h
0x18001b3ec  or      r9, rax
0x18001b3ef  test    r9d, r9d
0x18001b3f2  jz      short loc_18001B40C
0x18001b3f4  sub     r9d, 1
0x18001b3f8  jz      short loc_18001B400
0x18001b3fa  cmp     r9d, 1
0x18001b3fe  jnz     short loc_18001B406
0x18001b400  cmp     r10, 8
0x18001b404  jnb     short loc_18001B40C
0x18001b406  xor     r10d, r10d
0x18001b409  mov     [r8], r10
0x18001b40c  mov     rax, r10
0x18001b40f  test    rdx, rdx
0x18001b412  jz      short loc_18001B433
0x18001b414  shr     rax, 3
0x18001b418  test    rax, rax
0x18001b41b  jz      short loc_18001B430
0x18001b41d  sub     rax, rdx
0x18001b420  and     r10d, 7
0x18001b424  shl     rax, 3
0x18001b428  or      rax, r10
0x18001b42b  mov     [r8], rax
0x18001b42e  jmp     short loc_18001B433
0x18001b430  mov     rax, r10
0x18001b433  shr     rax, 3
0x18001b437  cmp     rax, r11
0x18001b43a  jbe     loc_18001B53A
0x18001b440  mov     qword ptr [r8], 0
0x18001b447  mov     eax, 1
0x18001b44c  nop
0x18001b44d  xchg    al, cs:byte_1800697B8
0x18001b453  nop
0x18001b454  test    al, al
0x18001b456  jnz     loc_18001B53A
0x18001b45c  mov     eax, cs:dword_180069000
0x18001b462  cmp     eax, 2
0x18001b465  jbe     loc_18001B53A
0x18001b46b  mov     rcx, cs:qword_180069018
0x18001b472  mov     rax, cs:qword_180069010
0x18001b479  test    al, 8
0x18001b47b  jz      loc_18001B53A
0x18001b481  mov     rax, rcx
0x18001b484  and     eax, 8
0x18001b487  cmp     rax, rcx
0x18001b48a  jnz     loc_18001B53A
0x18001b490  mov     rax, [r8]
0x18001b493  lea     rcx, dword_180069000
0x18001b49a  shr     rax, 3
0x18001b49e  xor     r9d, r9d
0x18001b4a1  mov     [rbp+57h+var_A0], rax
0x18001b4a5  xor     r8d, r8d
0x18001b4a8  lea     rax, [rbp+57h+var_A8]
0x18001b4ac  mov     [rbp+57h+var_A8], rdx
0x18001b4b0  mov     [rbp+57h+var_20], rax
0x18001b4b4  lea     rdx, byte_18005A383
0x18001b4bb  lea     rax, [rbp+57h+var_A0]
0x18001b4bf  mov     [rbp+57h+var_98], r11
0x18001b4c3  mov     [rbp+57h+var_30], rax
0x18001b4c7  lea     rax, [rbp+57h+var_98]
0x18001b4cb  mov     [rbp+57h+var_40], rax
0x18001b4cf  lea     rax, aInvalidFutureC; "Invalid future client timestamp detecte"...
0x18001b4d6  mov     [rbp+57h+var_50], rax
0x18001b4da  lea     rax, [rbp+57h+var_B0]
0x18001b4de  mov     [rbp+57h+var_60], rax
0x18001b4e2  lea     rax, aOnecoreXboxGam_55; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18001b4e9  mov     [rbp+57h+var_70], rax
0x18001b4ed  lea     rax, [rbp+57h+var_90]
0x18001b4f1  mov     [rsp+0E0h+var_B8], rax
0x18001b4f6  mov     [rsp+0E0h+var_C0], 8
0x18001b4fe  mov     [rbp+57h+var_B0], 0B3h
0x18001b505  mov     [rbp+57h+var_18], 8
0x18001b50d  mov     [rbp+57h+var_28], 8
0x18001b515  mov     [rbp+57h+var_38], 8
0x18001b51d  mov     [rbp+57h+var_48], 29h ; ')'
0x18001b525  mov     [rbp+57h+var_58], 4
0x18001b52d  mov     [rbp+57h+var_68], 38h ; '8'
0x18001b535  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x18001b53a  mov     rcx, [rbp+57h+var_10]
0x18001b53e  xor     rcx, rsp; StackCookie
0x18001b541  call    __security_check_cookie
0x18001b546  add     rsp, 0E0h
0x18001b54d  pop     rbp
0x18001b54e  retn
```

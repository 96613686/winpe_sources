# ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)

- ea: `0x1800477f0`
- end: `0x1800478ef`
- name: `?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180047350`
- `0x180047530`
- `0x180047900`
- `0x180047a60`
- `0x180048250`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800477f0`

## string_xrefs

- `0x180047823`: `ChangeApplicationServices::ChangeState`
- `0x1800478a6`: `ChangeApplicationServices::ChangeState`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ChangeState(__int64 a1, int a2)
{
  PVOID *v4; // r10
  unsigned int v5; // ebx
  _DWORD *v6; // rcx
  int v7; // eax
  bool v9; // zf

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ChangeState");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a2 == 1 )
  {
    v6 = (_DWORD *)(a1 + 36);
    v9 = *(_DWORD *)(a1 + 36) == 0;
    goto LABEL_22;
  }
  if ( a2 == 2 || a2 == 3 )
  {
    v6 = (_DWORD *)(a1 + 36);
    if ( *(_DWORD *)(a1 + 36) == 1 || *v6 == 4 )
      goto LABEL_13;
    v9 = *v6 == 5;
LABEL_22:
    if ( !v9 )
    {
      v5 = -2147217407;
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  v5 = -2147217407;
  if ( a2 == 4 )
  {
    v6 = (_DWORD *)(a1 + 36);
    v7 = *(_DWORD *)(a1 + 36) - 2;
  }
  else
  {
    if ( a2 != 5 )
      goto LABEL_14;
    v6 = (_DWORD *)(a1 + 36);
    v7 = *(_DWORD *)(a1 + 36) - 3;
  }
  v5 = v7 != 0 ? 0x80041001 : 0;
  if ( !v7 )
  {
LABEL_13:
    *v6 = a2;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_14:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      57,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ChangeState",
      v5);
  return v5;
}

```

## disassembly

```asm
0x1800477f0  push    rbx
0x1800477f2  push    rbp
0x1800477f3  push    rsi
0x1800477f4  push    rdi
0x1800477f5  sub     rsp, 38h
0x1800477f9  mov     esi, edx
0x1800477fb  mov     rdi, rcx
0x1800477fe  mov     r10, cs:WPP_GLOBAL_Control
0x180047805  lea     rbp, WPP_GLOBAL_Control
0x18004780c  cmp     r10, rbp
0x18004780f  jz      short loc_180047842
0x180047811  test    byte ptr [r10+1Ch], 80h
0x180047816  jz      short loc_180047842
0x180047818  cmp     byte ptr [r10+19h], 5
0x18004781d  jb      short loc_180047842
0x18004781f  mov     rcx, [r10+10h]
0x180047823  lea     r9, aChangeapplicat_12; "ChangeApplicationServices::ChangeState"
0x18004782a  mov     edx, 38h ; '8'
0x18004782f  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047836  call    WPP_SF_s
0x18004783b  mov     r10, cs:WPP_GLOBAL_Control
0x180047842  xor     ebx, ebx
0x180047844  mov     ecx, esi
0x180047846  sub     ecx, 1
0x180047849  jz      loc_1800478E7
0x18004784f  sub     ecx, 1
0x180047852  jz      short loc_1800478CD
0x180047854  sub     ecx, 1
0x180047857  jz      short loc_1800478CD
0x180047859  mov     ebx, 80041001h
0x18004785e  sub     ecx, 1
0x180047861  jz      short loc_180047873
0x180047863  cmp     ecx, 1
0x180047866  jnz     short loc_18004788F
0x180047868  lea     rcx, [rdi+24h]
0x18004786c  mov     eax, [rcx]
0x18004786e  sub     eax, 3
0x180047871  jmp     short loc_18004787C
0x180047873  lea     rcx, [rdi+24h]
0x180047877  mov     eax, [rcx]
0x180047879  sub     eax, 2
0x18004787c  neg     eax
0x18004787e  sbb     eax, eax
0x180047880  and     ebx, eax
0x180047882  test    ebx, ebx
0x180047884  js      short loc_18004788F
0x180047886  mov     [rcx], esi
0x180047888  mov     r10, cs:WPP_GLOBAL_Control
0x18004788f  cmp     r10, rbp
0x180047892  jz      short loc_1800478C2
0x180047894  test    byte ptr [r10+1Ch], 80h
0x180047899  jz      short loc_1800478C2
0x18004789b  cmp     byte ptr [r10+19h], 5
0x1800478a0  jb      short loc_1800478C2
0x1800478a2  mov     rcx, [r10+10h]
0x1800478a6  lea     r9, aChangeapplicat_12; "ChangeApplicationServices::ChangeState"
0x1800478ad  mov     edx, 39h ; '9'
0x1800478b2  mov     [rsp+58h+var_38], ebx
0x1800478b6  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800478bd  call    WPP_SF_sD
0x1800478c2  mov     eax, ebx
0x1800478c4  add     rsp, 38h
0x1800478c8  pop     rdi
0x1800478c9  pop     rsi
0x1800478ca  pop     rbp
0x1800478cb  pop     rbx
0x1800478cc  retn
0x1800478cd  lea     rcx, [rdi+24h]
0x1800478d1  cmp     dword ptr [rcx], 1
0x1800478d4  jz      short loc_180047886
0x1800478d6  cmp     dword ptr [rcx], 4
0x1800478d9  jz      short loc_180047886
0x1800478db  cmp     dword ptr [rcx], 5
0x1800478de  jz      short loc_180047886
0x1800478e0  mov     ebx, 80041001h
0x1800478e5  jmp     short loc_18004788F
0x1800478e7  lea     rcx, [rdi+24h]
0x1800478eb  cmp     [rcx], ebx
0x1800478ed  jmp     short loc_1800478DE
```

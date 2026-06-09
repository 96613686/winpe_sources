# Register_BiosHandoff

- ea: `0x14001a928`
- end: `0x14001abfe`
- name: `Register_BiosHandoff`
- size: `726`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140018d90`
- `0x14007e5c8`

## callees

- `0x140017adc`
- `0x14001a214`
- `0x14001a928`
- `0x14001ac04`
- `0x14001ac48`
- `0x14001ad0c`
- `0x14001ae98`
- `0x14001d118`
- `0x14001f830`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001aa99`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001aa99`

## pseudocode

```c
__int64 __fastcall Register_BiosHandoff(_QWORD *a1)
{
  __int64 v1; // r13
  _QWORD *v2; // rdi
  char Uchar; // al
  __int64 v5; // rcx
  char v6; // al
  int v7; // ebx
  int i; // r12d
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r9d
  unsigned int v12; // ebx
  int Ulong; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // eax
  int v19; // edx
  signed __int32 v20[8]; // [rsp+0h] [rbp-68h] BYREF
  int v21; // [rsp+28h] [rbp-40h]
  char v22; // [rsp+70h] [rbp+8h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+78h] [rbp+10h] BYREF

  v1 = a1[8];
  v2 = a1 + 1;
  Interval.QuadPart = 0;
  if ( v1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*(_QWORD *)(*v2 + 72LL), 4, 6, 51, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
    Uchar = XilRegister_ReadUchar(a1, v1 + 3);
    v5 = *v2;
    v6 = Uchar | 1;
    v22 = v6;
    if ( *(_BYTE *)(v5 + 1041) )
    {
      Register_WriteSecureMmio(a1, v1 + 3, 0, &v22);
    }
    else
    {
      *(_BYTE *)(v1 + 3) = v6;
      _InterlockedOr(v20, 0);
    }
    v7 = 20;
    for ( i = 0; ; i += 100 )
    {
      if ( (XilRegister_ReadUchar(a1, v1 + 2) & 1) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_11;
        v10 = a1[1];
        v11 = 52;
        v21 = i;
        LOBYTE(v9) = 4;
        goto LABEL_10;
      }
      if ( !v7 )
        break;
      --v7;
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v10 = a1[1];
    if ( (*(_BYTE *)(v10 + 736) & 4) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v10 + 72),
          v9,
          6,
          54,
          (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
          208);
      }
      v15 = a1[1];
      v16 = 1;
LABEL_25:
      Etw_StartDeviceFail(v15, v9, v16);
      return (unsigned int)-1073741823;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 53;
      v21 = 2000;
      LOBYTE(v9) = 3;
LABEL_10:
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v10 + 72),
        v9,
        6,
        v11,
        (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
        v21);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(*(_QWORD *)(*v2 + 72LL), 3, 6, 50, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  }
LABEL_11:
  if ( (XilRegister_ReadUlong(a1, a1[4] + 4LL) & 1) != 0 )
    goto LABEL_12;
  v17 = *v2;
  if ( *(__int64 *)(*v2 + 736LL) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(*(_QWORD *)(v17 + 72), 2, 6, 55, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
    v15 = *v2;
    v16 = 2;
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*(_QWORD *)(v17 + 72), 2, 6, 56, (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids);
  v18 = Register_ControllerStop((__int64)a1);
  v12 = v18;
  if ( v18 >= 0 )
  {
LABEL_12:
    if ( v1 )
    {
      Ulong = XilRegister_ReadUlong(a1, v1 + 4);
      XilRegister_WriteUlong(a1, v1 + 4, Ulong & 0x1FFFDFFF);
    }
    return 0;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*v2 + 72LL),
      v19,
      6,
      57,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
      v18);
  }
  return v12;
}

```

## disassembly

```asm
0x14001a928  mov     [rsp+arg_10], rbx
0x14001a92d  push    rbp
0x14001a92e  push    rsi
0x14001a92f  push    rdi
0x14001a930  push    r12
0x14001a932  push    r13
0x14001a934  push    r14
0x14001a936  push    r15
0x14001a938  sub     rsp, 30h
0x14001a93c  mov     r13, [rcx+40h]
0x14001a940  lea     rdi, [rcx+8]
0x14001a944  mov     qword ptr [rsp+68h+Interval], 0
0x14001a94d  mov     rsi, rcx
0x14001a950  test    r13, r13
0x14001a953  jz      loc_14001AA44
0x14001a959  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001a960  mov     r14d, 6
0x14001a966  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001a96d  lea     r15, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001a974  jz      short loc_14001A990
0x14001a976  mov     rcx, [rdi]
0x14001a979  lea     r9d, [r14+2Dh]
0x14001a97d  mov     r8d, r14d
0x14001a980  mov     [rsp+68h+var_48], r15
0x14001a985  mov     dl, 4
0x14001a987  mov     rcx, [rcx+48h]
0x14001a98b  call    WPP_RECORDER_SF_
0x14001a990  lea     rbx, [r13+3]
0x14001a994  mov     rcx, rsi
0x14001a997  mov     rdx, rbx
0x14001a99a  call    XilRegister_ReadUchar
0x14001a99f  mov     rcx, [rdi]
0x14001a9a2  or      al, 1
0x14001a9a4  mov     [rsp+68h+arg_0], al
0x14001a9a8  cmp     byte ptr [rcx+411h], 0
0x14001a9af  jnz     loc_14001AACF
0x14001a9b5  mov     [rbx], al
0x14001a9b7  lock or [rsp+68h+var_68], 0
0x14001a9bc  mov     ebx, 14h
0x14001a9c1  xor     r12d, r12d
0x14001a9c4  lea     rax, [r13+2]
0x14001a9c8  mov     rcx, rsi
0x14001a9cb  mov     rdx, rax
0x14001a9ce  call    XilRegister_ReadUchar
0x14001a9d3  test    al, 1
0x14001a9d5  jnz     loc_14001AA7D
0x14001a9db  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001a9e2  jz      short loc_14001AA06
0x14001a9e4  mov     rcx, [rsi+8]
0x14001a9e8  mov     r9d, 34h ; '4'
0x14001a9ee  mov     [rsp+68h+var_40], r12d
0x14001a9f3  mov     dl, 4
0x14001a9f5  mov     rcx, [rcx+48h]
0x14001a9f9  mov     r8d, r14d
0x14001a9fc  mov     [rsp+68h+var_48], r15
0x14001aa01  call    WPP_RECORDER_SF_d
0x14001aa06  mov     rdx, [rsi+20h]
0x14001aa0a  mov     rcx, rsi
0x14001aa0d  add     rdx, 4
0x14001aa11  call    XilRegister_ReadUlong
0x14001aa16  test    al, 1
0x14001aa18  jz      loc_14001AB5B
0x14001aa1e  test    r13, r13
0x14001aa21  jnz     loc_14001AAAA
0x14001aa27  xor     ebx, ebx
0x14001aa29  mov     eax, ebx
0x14001aa2b  mov     rbx, [rsp+68h+arg_10]
0x14001aa33  add     rsp, 30h
0x14001aa37  pop     r15
0x14001aa39  pop     r14
0x14001aa3b  pop     r13
0x14001aa3d  pop     r12
0x14001aa3f  pop     rdi
0x14001aa40  pop     rsi
0x14001aa41  pop     rbp
0x14001aa42  retn
0x14001aa44  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001aa4b  mov     r14d, 6
0x14001aa51  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001aa58  lea     r15, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001aa5f  jz      short loc_14001AA06
0x14001aa61  mov     rcx, [rdi]
0x14001aa64  lea     r9d, [r14+2Ch]
0x14001aa68  mov     r8d, r14d
0x14001aa6b  mov     [rsp+68h+var_48], r15
0x14001aa70  mov     dl, 3
0x14001aa72  mov     rcx, [rcx+48h]
0x14001aa76  call    WPP_RECORDER_SF_
0x14001aa7b  jmp     short loc_14001AA06
0x14001aa7d  test    ebx, ebx
0x14001aa7f  jz      short loc_14001AAE7
0x14001aa81  dec     ebx
0x14001aa83  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFF0BDC0h
0x14001aa8c  add     r12d, 64h ; 'd'
0x14001aa90  lea     r8, [rsp+68h+Interval]; Interval
0x14001aa95  xor     edx, edx; Alertable
0x14001aa97  xor     ecx, ecx; WaitMode
0x14001aa99  call    cs:__imp_KeDelayExecutionThread
0x14001aaa0  nop     dword ptr [rax+rax+00h]
0x14001aaa5  jmp     loc_14001A9C4
0x14001aaaa  lea     rdx, [r13+4]
0x14001aaae  mov     rcx, rsi
0x14001aab1  call    XilRegister_ReadUlong
0x14001aab6  and     eax, 1FFFDFFFh
0x14001aabb  lea     rdx, [r13+4]
0x14001aabf  mov     r8d, eax
0x14001aac2  mov     rcx, rsi
0x14001aac5  call    XilRegister_WriteUlong
0x14001aaca  jmp     loc_14001AA27
0x14001aacf  lea     r9, [rsp+68h+arg_0]
0x14001aad4  xor     r8d, r8d
0x14001aad7  mov     rdx, rbx
0x14001aada  mov     rcx, rsi
0x14001aadd  call    Register_WriteSecureMmio
0x14001aae2  jmp     loc_14001A9BC
0x14001aae7  mov     rcx, [rsi+8]
0x14001aaeb  test    byte ptr [rcx+2E0h], 4
0x14001aaf2  jnz     short loc_14001AB16
0x14001aaf4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001aafb  jnz     short loc_14001AB38
0x14001aafd  mov     rcx, [rsi+8]
0x14001ab01  mov     r8d, 1
0x14001ab07  call    Etw_StartDeviceFail
0x14001ab0c  mov     ebx, 0C0000001h
0x14001ab11  jmp     loc_14001AA29
0x14001ab16  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001ab1d  jz      loc_14001AA06
0x14001ab23  mov     r9d, 35h ; '5'
0x14001ab29  mov     [rsp+68h+var_40], 7D0h
0x14001ab31  mov     dl, 3
0x14001ab33  jmp     loc_14001A9F5
0x14001ab38  mov     rcx, [rcx+48h]
0x14001ab3c  mov     r9d, 36h ; '6'
0x14001ab42  mov     [rsp+68h+var_40], 7D0h
0x14001ab4a  mov     r8d, r14d
0x14001ab4d  mov     dl, 2
0x14001ab4f  mov     [rsp+68h+var_48], r15
0x14001ab54  call    WPP_RECORDER_SF_d
0x14001ab59  jmp     short loc_14001AAFD
0x14001ab5b  mov     rcx, [rdi]
0x14001ab5e  cmp     qword ptr [rcx+2E0h], 0
0x14001ab66  jge     short loc_14001AB98
0x14001ab68  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001ab6f  jz      short loc_14001AB8A
0x14001ab71  mov     rcx, [rcx+48h]
0x14001ab75  mov     r9d, 37h ; '7'
0x14001ab7b  mov     r8d, r14d
0x14001ab7e  mov     [rsp+68h+var_48], r15
0x14001ab83  mov     dl, 2
0x14001ab85  call    WPP_RECORDER_SF_
0x14001ab8a  mov     rcx, [rdi]
0x14001ab8d  mov     r8d, 2
0x14001ab93  jmp     loc_14001AB07
0x14001ab98  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001ab9f  jz      short loc_14001ABBA
0x14001aba1  mov     rcx, [rcx+48h]
0x14001aba5  mov     r9d, 38h ; '8'
0x14001abab  mov     r8d, r14d
0x14001abae  mov     [rsp+68h+var_48], r15
0x14001abb3  mov     dl, 2
0x14001abb5  call    WPP_RECORDER_SF_
0x14001abba  mov     rcx, rsi
0x14001abbd  call    Register_ControllerStop
0x14001abc2  mov     ebx, eax
0x14001abc4  test    eax, eax
0x14001abc6  jns     loc_14001AA1E
0x14001abcc  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14001abd3  jz      loc_14001AA29
0x14001abd9  mov     rcx, [rdi]
0x14001abdc  mov     r9d, 39h ; '9'
0x14001abe2  mov     [rsp+68h+var_40], eax
0x14001abe6  mov     r8d, r14d
0x14001abe9  mov     dl, 2
0x14001abeb  mov     [rsp+68h+var_48], r15
0x14001abf0  mov     rcx, [rcx+48h]
0x14001abf4  call    WPP_RECORDER_SF_d
0x14001abf9  jmp     loc_14001AA29
```

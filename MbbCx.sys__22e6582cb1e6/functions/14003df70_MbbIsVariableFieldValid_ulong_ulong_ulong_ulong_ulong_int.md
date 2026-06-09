# MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)

- ea: `0x14003df70`
- end: `0x14003e0fa`
- name: `?MbbIsVariableFieldValid@@YAJKKKKKH@Z`
- size: `394`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `25`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400061b0`
- `0x1400275f0`
- `0x140027a54`
- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x14002b930`
- `0x14002be90`
- `0x14002c9e0`
- `0x14002d460`
- `0x14002fb40`
- `0x140030f80`
- `0x140032ee0`
- `0x140033f50`
- `0x140034530`
- `0x140035080`
- `0x140035b60`
- `0x140036030`
- `0x1400367e0`
- `0x140038010`
- `0x14003d580`
- `0x14003daa4`
- `0x140040e28`
- `0x140040fd4`
- `0x1400411d4`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x1400051ac`
- `0x14000d684`
- `0x14003df70`

## pseudocode

```c
__int64 __fastcall MbbIsVariableFieldValid(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  unsigned int v6; // edx
  int v7; // r9d
  int v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+30h] [rbp-18h]

  if ( a2 + (unsigned __int64)a3 > a1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        91,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
        a2,
        a3,
        a1);
    return 3221225485LL;
  }
  if ( a2 != ((a2 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        92,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
        v9);
    }
    return 3221225485LL;
  }
  v6 = a3 % a5;
  if ( a3 / a5 > a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = a4;
      v7 = 93;
      v10 = a3 / a5;
LABEL_13:
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        v7,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
        v10,
        v11);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = a5;
      v7 = 94;
      v10 = a3;
      goto LABEL_13;
    }
    return 3221225485LL;
  }
  if ( !a6 && !a3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        95,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
    }
    return 3221225485LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14003df70  push    rbx
0x14003df72  sub     rsp, 40h
0x14003df76  mov     r11d, edx
0x14003df79  mov     ebx, r9d
0x14003df7c  mov     r10d, r8d
0x14003df7f  add     r10, r11
0x14003df82  mov     eax, ecx
0x14003df84  cmp     r10, rax
0x14003df87  jbe     short loc_14003DFD5
0x14003df89  lea     rax, WPP_RECORDER_INITIALIZED
0x14003df90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003df97  jz      loc_14003E0EA
0x14003df9d  mov     [rsp+48h+var_10], ecx
0x14003dfa1  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003dfa8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfaf  mov     r9d, 5Bh ; '['
0x14003dfb5  mov     dword ptr [rsp+48h+var_18], r8d
0x14003dfba  mov     dword ptr [rsp+48h+var_20], edx
0x14003dfbe  mov     [rsp+48h+var_28], rax
0x14003dfc3  mov     rcx, [rcx+40h]
0x14003dfc7  lea     r8d, [r9-58h]
0x14003dfcb  call    WPP_RECORDER_SF_ddd
0x14003dfd0  jmp     loc_14003E0EA
0x14003dfd5  lea     rax, [r11+3]
0x14003dfd9  and     rax, 0FFFFFFFFFFFFFFFCh
0x14003dfdd  cmp     r11, rax
0x14003dfe0  jz      short loc_14003E027
0x14003dfe2  lea     rax, WPP_RECORDER_INITIALIZED
0x14003dfe9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003dff0  jz      loc_14003E0EA
0x14003dff6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dffd  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003e004  mov     dword ptr [rsp+48h+var_20], edx
0x14003e008  mov     r9d, 5Ch ; '\'
0x14003e00e  mov     dl, 2
0x14003e010  mov     [rsp+48h+var_28], rax
0x14003e015  mov     rcx, [rcx+40h]
0x14003e019  lea     r8d, [r9-59h]
0x14003e01d  call    WPP_RECORDER_SF_d
0x14003e022  jmp     loc_14003E0EA
0x14003e027  mov     r10d, [rsp+48h+arg_20]
0x14003e02c  xor     edx, edx
0x14003e02e  mov     eax, r8d
0x14003e031  div     r10d
0x14003e034  mov     ecx, eax
0x14003e036  cmp     eax, ebx
0x14003e038  jbe     short loc_14003E05E
0x14003e03a  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e041  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e048  jz      loc_14003E0EA
0x14003e04e  mov     dword ptr [rsp+48h+var_18], ebx
0x14003e052  mov     r9d, 5Dh ; ']'
0x14003e058  mov     dword ptr [rsp+48h+var_20], ecx
0x14003e05c  jmp     short loc_14003E082
0x14003e05e  test    edx, edx
0x14003e060  jz      short loc_14003E0A8
0x14003e062  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e069  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e070  jz      short loc_14003E0EA
0x14003e072  mov     dword ptr [rsp+48h+var_18], r10d
0x14003e077  mov     r9d, 5Eh ; '^'
0x14003e07d  mov     dword ptr [rsp+48h+var_20], r8d
0x14003e082  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e089  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003e090  mov     r8d, 3
0x14003e096  mov     [rsp+48h+var_28], rax
0x14003e09b  mov     dl, 2
0x14003e09d  mov     rcx, [rcx+40h]
0x14003e0a1  call    WPP_RECORDER_SF_DD
0x14003e0a6  jmp     short loc_14003E0EA
0x14003e0a8  cmp     [rsp+48h+arg_28], 0
0x14003e0ad  jnz     short loc_14003E0F1
0x14003e0af  test    r8d, r8d
0x14003e0b2  jnz     short loc_14003E0F1
0x14003e0b4  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e0bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e0c2  jz      short loc_14003E0EA
0x14003e0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e0cb  lea     r9d, [r8+5Fh]
0x14003e0cf  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003e0d6  mov     dl, 2
0x14003e0d8  lea     r8d, [r9-5Ch]
0x14003e0dc  mov     [rsp+48h+var_28], rax
0x14003e0e1  mov     rcx, [rcx+40h]
0x14003e0e5  call    WPP_RECORDER_SF_
0x14003e0ea  mov     eax, 0C000000Dh
0x14003e0ef  jmp     short loc_14003E0F3
0x14003e0f1  xor     eax, eax
0x14003e0f3  add     rsp, 40h
0x14003e0f7  pop     rbx
0x14003e0f8  retn
```

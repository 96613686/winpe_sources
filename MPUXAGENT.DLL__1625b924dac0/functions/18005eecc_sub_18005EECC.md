# sub_18005EECC

- ea: `0x18005eecc`
- end: `0x18005f138`
- name: `sub_18005EECC`
- size: `620`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18005f470`

## callees

- `0x180005fc8`
- `0x1800095a0`
- `0x180032da0`
- `0x180059814`
- `0x18005edc0`
- `0x18005eecc`
- `0x18005f138`
- `0x18005f7a4`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18005ef89`
- `MpClient!MpFreeMemory` at `0x18005ef97`
- `MpClient!MpFreeMemory` at `0x18005efa6`
- `MpClient!MpFreeMemory` at `0x18005effa`
- `MpClient!MpFreeMemory` at `0x18005f008`
- `MpClient!MpFreeMemory` at `0x18005f069`
- `MpClient!MpFreeMemory` at `0x18005f078`
- `MpClient!MpFreeMemory` at `0x18005f08e`
- `MpClient!MpFreeMemory` at `0x18005f0cc`
- `MpClient!MpFreeMemory` at `0x18005f111`
- `MpClient!MpFreeMemory` at `0x18005ef89`
- `MpClient!MpFreeMemory` at `0x18005ef97`
- `MpClient!MpFreeMemory` at `0x18005efa6`
- `MpClient!MpFreeMemory` at `0x18005effa`
- `MpClient!MpFreeMemory` at `0x18005f008`
- `MpClient!MpFreeMemory` at `0x18005f069`
- `MpClient!MpFreeMemory` at `0x18005f078`
- `MpClient!MpFreeMemory` at `0x18005f08e`
- `MpClient!MpFreeMemory` at `0x18005f0cc`
- `MpClient!MpFreeMemory` at `0x18005f111`

## string_xrefs

- `0x18005ef58`: `MsMpLics.dll`
- `0x18005f0a0`: `MsMpLics.dll`

## pseudocode

```c
__int64 __fastcall sub_18005EECC(_QWORD *a1)
{
  int v2; // eax
  int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v7; // r9
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF

  *a1 = 0;
  v12 = 0;
  v11 = 0;
  v2 = sub_18005F138(&v11);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
      sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x18u, (const GUID *)qword_180086050, v2);
    v4 = v11;
    if ( !v11 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v5 = v11;
  v13 = 0;
  v3 = sub_18005F7A4(&v13, L"%s\\%s", v11, L"MsMpLics.dll");
  if ( v3 < 0 )
  {
    if ( v13 )
      MpFreeMemory(v13);
LABEL_10:
    if ( !v5 )
    {
LABEL_13:
      if ( v12 )
        MpFreeMemory(v12);
      return (unsigned int)v3;
    }
    v4 = v5;
LABEL_12:
    MpFreeMemory(v4);
    goto LABEL_13;
  }
  v7 = v13;
  v12 = v13;
  v13 = 0;
  if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 4) != 0 )
  {
    sub_180059814(*((_QWORD *)off_180096D60 + 2), 25, qword_180086050, v7);
    if ( v13 )
      MpFreeMemory(v13);
  }
  if ( v5 )
    MpFreeMemory(v5);
  if ( (unsigned int)sub_180005FC8(v12) )
  {
    v11 = 0;
    v8 = sub_18005EDC0(&v11);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
        sub_180032DA0(*((_QWORD *)off_180096D60 + 2), 0x25u, (const GUID *)qword_180086050, v8);
      if ( v11 )
        MpFreeMemory(v11);
      if ( v12 )
        MpFreeMemory(v12);
      return v9;
    }
    if ( v12 )
    {
      MpFreeMemory(v12);
      v12 = 0;
    }
    v5 = v11;
    v3 = sub_18005F7A4(&v12, L"%s\\%s", v11, L"MsMpLics.dll");
    if ( v3 < 0 )
      goto LABEL_10;
    if ( v5 )
      MpFreeMemory(v5);
  }
  v10 = v12;
  *a1 = v12;
  v12 = 0;
  if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 4) != 0 )
  {
    sub_180059814(*((_QWORD *)off_180096D60 + 2), 38, qword_180086050, v10);
    if ( v12 )
      MpFreeMemory(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18005eecc  mov     [rsp-18h+arg_8], rbx
0x18005eed1  mov     [rsp-18h+arg_10], rsi
0x18005eed6  push    rbp
0x18005eed7  push    rdi
0x18005eed8  push    r14
0x18005eeda  mov     rbp, rsp
0x18005eedd  sub     rsp, 40h
0x18005eee1  mov     rax, cs:__security_cookie
0x18005eee8  xor     rax, rsp
0x18005eeeb  mov     [rbp+var_8], rax
0x18005eeef  mov     r14, rcx
0x18005eef2  mov     qword ptr [rcx], 0
0x18005eef9  lea     rcx, [rbp+var_20]
0x18005eefd  mov     [rbp+var_18], 0
0x18005ef05  mov     [rbp+var_20], 0
0x18005ef0d  call    sub_18005F138
0x18005ef12  mov     edi, eax
0x18005ef14  test    eax, eax
0x18005ef16  jns     short loc_18005EF54
0x18005ef18  mov     rcx, cs:off_180096D60
0x18005ef1f  lea     rsi, off_180096D60
0x18005ef26  cmp     rcx, rsi
0x18005ef29  jz      short loc_18005EF49
0x18005ef2b  test    byte ptr [rcx+1Ch], 1
0x18005ef2f  jz      short loc_18005EF49
0x18005ef31  mov     rcx, [rcx+10h]
0x18005ef35  lea     r8, qword_180086050
0x18005ef3c  mov     edx, 18h
0x18005ef41  mov     r9d, eax
0x18005ef44  call    sub_180032DA0
0x18005ef49  mov     rcx, [rbp+var_20]
0x18005ef4d  test    rcx, rcx
0x18005ef50  jz      short loc_18005EF9D
0x18005ef52  jmp     short loc_18005EF97
0x18005ef54  mov     rbx, [rbp+var_20]
0x18005ef58  lea     r9, aMsmplicsDll; "MsMpLics.dll"
0x18005ef5f  mov     r8, rbx
0x18005ef62  mov     [rbp+var_10], 0
0x18005ef6a  lea     rdx, aSS; "%s\\%s"
0x18005ef71  lea     rcx, [rbp+var_10]
0x18005ef75  call    sub_18005F7A4
0x18005ef7a  mov     edi, eax
0x18005ef7c  test    eax, eax
0x18005ef7e  jns     short loc_18005EFB3
0x18005ef80  mov     rcx, [rbp+var_10]
0x18005ef84  test    rcx, rcx
0x18005ef87  jz      short loc_18005EF8F
0x18005ef89  call    cs:MpFreeMemory
0x18005ef8f  test    rbx, rbx
0x18005ef92  jz      short loc_18005EF9D
0x18005ef94  mov     rcx, rbx
0x18005ef97  call    cs:MpFreeMemory
0x18005ef9d  mov     rcx, [rbp+var_18]
0x18005efa1  test    rcx, rcx
0x18005efa4  jz      short loc_18005EFAC
0x18005efa6  call    cs:MpFreeMemory
0x18005efac  mov     eax, edi
0x18005efae  jmp     loc_18005F119
0x18005efb3  mov     r9, [rbp+var_10]
0x18005efb7  mov     [rbp+var_18], r9
0x18005efbb  mov     [rbp+var_10], 0
0x18005efc3  mov     rcx, cs:off_180096D60
0x18005efca  lea     rsi, off_180096D60
0x18005efd1  cmp     rcx, rsi
0x18005efd4  jz      short loc_18005F000
0x18005efd6  test    byte ptr [rcx+1Ch], 4
0x18005efda  jz      short loc_18005F000
0x18005efdc  mov     rcx, [rcx+10h]
0x18005efe0  lea     r8, qword_180086050
0x18005efe7  mov     edx, 19h
0x18005efec  call    sub_180059814
0x18005eff1  mov     rcx, [rbp+var_10]
0x18005eff5  test    rcx, rcx
0x18005eff8  jz      short loc_18005F000
0x18005effa  call    cs:MpFreeMemory
0x18005f000  test    rbx, rbx
0x18005f003  jz      short loc_18005F00E
0x18005f005  mov     rcx, rbx
0x18005f008  call    cs:MpFreeMemory
0x18005f00e  mov     rcx, [rbp+var_18]
0x18005f012  call    sub_180005FC8
0x18005f017  test    eax, eax
0x18005f019  jz      loc_18005F0D2
0x18005f01f  lea     rcx, [rbp+var_20]
0x18005f023  mov     [rbp+var_20], 0
0x18005f02b  call    sub_18005EDC0
0x18005f030  mov     ebx, eax
0x18005f032  test    eax, eax
0x18005f034  jns     short loc_18005F085
0x18005f036  mov     rcx, cs:off_180096D60
0x18005f03d  cmp     rcx, rsi
0x18005f040  jz      short loc_18005F060
0x18005f042  test    byte ptr [rcx+1Ch], 1
0x18005f046  jz      short loc_18005F060
0x18005f048  mov     rcx, [rcx+10h]
0x18005f04c  lea     r8, qword_180086050
0x18005f053  mov     edx, 25h ; '%'
0x18005f058  mov     r9d, eax
0x18005f05b  call    sub_180032DA0
0x18005f060  mov     rcx, [rbp+var_20]
0x18005f064  test    rcx, rcx
0x18005f067  jz      short loc_18005F06F
0x18005f069  call    cs:MpFreeMemory
0x18005f06f  mov     rcx, [rbp+var_18]
0x18005f073  test    rcx, rcx
0x18005f076  jz      short loc_18005F07E
0x18005f078  call    cs:MpFreeMemory
0x18005f07e  mov     eax, ebx
0x18005f080  jmp     loc_18005F119
0x18005f085  mov     rcx, [rbp+var_18]
0x18005f089  test    rcx, rcx
0x18005f08c  jz      short loc_18005F09C
0x18005f08e  call    cs:MpFreeMemory
0x18005f094  mov     [rbp+var_18], 0
0x18005f09c  mov     rbx, [rbp+var_20]
0x18005f0a0  lea     r9, aMsmplicsDll; "MsMpLics.dll"
0x18005f0a7  mov     r8, rbx
0x18005f0aa  lea     rdx, aSS; "%s\\%s"
0x18005f0b1  lea     rcx, [rbp+var_18]
0x18005f0b5  call    sub_18005F7A4
0x18005f0ba  mov     edi, eax
0x18005f0bc  test    eax, eax
0x18005f0be  js      loc_18005EF8F
0x18005f0c4  test    rbx, rbx
0x18005f0c7  jz      short loc_18005F0D2
0x18005f0c9  mov     rcx, rbx
0x18005f0cc  call    cs:MpFreeMemory
0x18005f0d2  mov     r9, [rbp+var_18]
0x18005f0d6  mov     [r14], r9
0x18005f0d9  mov     [rbp+var_18], 0
0x18005f0e1  mov     rcx, cs:off_180096D60
0x18005f0e8  cmp     rcx, rsi
0x18005f0eb  jz      short loc_18005F117
0x18005f0ed  test    byte ptr [rcx+1Ch], 4
0x18005f0f1  jz      short loc_18005F117
0x18005f0f3  mov     rcx, [rcx+10h]
0x18005f0f7  lea     r8, qword_180086050
0x18005f0fe  mov     edx, 26h ; '&'
0x18005f103  call    sub_180059814
0x18005f108  mov     rcx, [rbp+var_18]
0x18005f10c  test    rcx, rcx
0x18005f10f  jz      short loc_18005F117
0x18005f111  call    cs:MpFreeMemory
0x18005f117  xor     eax, eax
0x18005f119  mov     rcx, [rbp+var_8]
0x18005f11d  xor     rcx, rsp; StackCookie
0x18005f120  call    __security_check_cookie
0x18005f125  mov     rbx, [rsp+40h+arg_8]
0x18005f12a  mov     rsi, [rsp+40h+arg_10]
0x18005f12f  add     rsp, 40h
0x18005f133  pop     r14
0x18005f135  pop     rdi
0x18005f136  pop     rbp
0x18005f137  retn
```

# sub_1400EAEB0

- ea: `0x1400eaeb0`
- end: `0x1400eb036`
- name: `sub_1400EAEB0`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400edc94`

## callees

- `0x14000b8f8`
- `0x140036780`
- `0x14008133c`
- `0x140081450`
- `0x1400eaeb0`
- `0x140115914`

## import_xrefs

- `MpClient!MpConfigClose` at `0x1400eaff7`
- `MpClient!MpConfigClose` at `0x1400eb00a`
- `MpClient!MpConfigClose` at `0x1400eaff7`
- `MpClient!MpConfigClose` at `0x1400eb00a`
- `MpClient!MpConfigOpen` at `0x1400eaef9`
- `MpClient!MpConfigOpen` at `0x1400eaf79`
- `MpClient!MpConfigOpen` at `0x1400eaef9`
- `MpClient!MpConfigOpen` at `0x1400eaf79`

## pseudocode

```c
__int64 sub_1400EAEB0()
{
  int v0; // ebx
  int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  char v4; // dl
  int v6; // [rsp+20h] [rbp-20h] BYREF
  __int64 v7; // [rsp+28h] [rbp-18h] BYREF

  v0 = 0;
  if ( !(unsigned int)sub_14000B8F8() )
  {
LABEL_26:
    v4 = 1;
    return v0 & (unsigned int)-(v4 != 0);
  }
  v6 = 0;
  v7 = 0;
  if ( (unsigned int)sub_140115914() )
  {
    v1 = MpConfigOpen(L"Features", &v7);
    if ( v1 < 0 )
    {
      v2 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_20;
      v3 = 21;
      goto LABEL_19;
    }
    v1 = sub_14008133C(v7, L"ForcePassiveMode", &v6);
    if ( v1 < 0 )
    {
      v2 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_20;
      v3 = 22;
      goto LABEL_19;
    }
    goto LABEL_23;
  }
  v1 = MpConfigOpen(L".", &v7);
  if ( v1 >= 0 )
  {
    v1 = sub_14008133C(v7, L"PassiveMode", &v6);
    if ( v1 < 0 )
    {
      v2 = off_14018DE50;
      if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
        goto LABEL_20;
      v3 = 20;
      goto LABEL_19;
    }
LABEL_23:
    if ( v7 )
      MpConfigClose(v7);
    LOBYTE(v0) = v6 == 2;
    goto LABEL_26;
  }
  v2 = off_14018DE50;
  if ( off_14018DE50 == (_UNKNOWN *)&off_14018DE50 || (*((_BYTE *)off_14018DE50 + 28) & 1) == 0 )
    goto LABEL_20;
  v3 = 19;
LABEL_19:
  sub_140081450(v2[2], v3, qword_1401688E8, (unsigned int)v1);
LABEL_20:
  if ( v7 )
    MpConfigClose(v7);
  v4 = 0;
  return v0 & (unsigned int)-(v4 != 0);
}

```

## disassembly

```asm
0x1400eaeb0  mov     [rsp-8+arg_0], rbx
0x1400eaeb5  push    rbp
0x1400eaeb6  mov     rbp, rsp
0x1400eaeb9  sub     rsp, 40h
0x1400eaebd  mov     rax, cs:__security_cookie
0x1400eaec4  xor     rax, rsp
0x1400eaec7  mov     [rbp+var_10], rax
0x1400eaecb  xor     ebx, ebx
0x1400eaecd  call    sub_14000B8F8
0x1400eaed2  test    eax, eax
0x1400eaed4  jz      loc_1400EB017
0x1400eaeda  mov     [rbp+var_20], ebx
0x1400eaedd  call    sub_140115914
0x1400eaee2  mov     [rbp+var_18], rbx
0x1400eaee6  lea     rdx, [rbp+var_18]
0x1400eaeea  test    eax, eax
0x1400eaeec  jnz     loc_1400EAF72
0x1400eaef2  lea     rcx, asc_140147054; "."
0x1400eaef9  call    cs:MpConfigOpen
0x1400eaeff  test    eax, eax
0x1400eaf01  jns     short loc_1400EAF2D
0x1400eaf03  mov     rcx, cs:off_14018DE50
0x1400eaf0a  lea     rdx, off_14018DE50
0x1400eaf11  cmp     rcx, rdx
0x1400eaf14  jz      loc_1400EAFEE
0x1400eaf1a  mov     dl, 1
0x1400eaf1c  test    [rcx+1Ch], dl
0x1400eaf1f  jz      loc_1400EAFEE
0x1400eaf25  lea     edx, [rbx+13h]
0x1400eaf28  jmp     loc_1400EAFDB
0x1400eaf2d  mov     rcx, [rbp+var_18]
0x1400eaf31  lea     r8, [rbp+var_20]
0x1400eaf35  lea     rdx, aPassivemode; "PassiveMode"
0x1400eaf3c  call    sub_14008133C
0x1400eaf41  test    eax, eax
0x1400eaf43  jns     loc_1400EB001
0x1400eaf49  mov     rcx, cs:off_14018DE50
0x1400eaf50  lea     rdx, off_14018DE50
0x1400eaf57  cmp     rcx, rdx
0x1400eaf5a  jz      loc_1400EAFEE
0x1400eaf60  mov     dl, 1
0x1400eaf62  test    [rcx+1Ch], dl
0x1400eaf65  jz      loc_1400EAFEE
0x1400eaf6b  mov     edx, 14h
0x1400eaf70  jmp     short loc_1400EAFDB
0x1400eaf72  lea     rcx, aFeatures; "Features"
0x1400eaf79  call    cs:MpConfigOpen
0x1400eaf7f  test    eax, eax
0x1400eaf81  jns     short loc_1400EAFA4
0x1400eaf83  mov     rcx, cs:off_14018DE50
0x1400eaf8a  lea     rdx, off_14018DE50
0x1400eaf91  cmp     rcx, rdx
0x1400eaf94  jz      short loc_1400EAFEE
0x1400eaf96  mov     dl, 1
0x1400eaf98  test    [rcx+1Ch], dl
0x1400eaf9b  jz      short loc_1400EAFEE
0x1400eaf9d  mov     edx, 15h
0x1400eafa2  jmp     short loc_1400EAFDB
0x1400eafa4  mov     rcx, [rbp+var_18]
0x1400eafa8  lea     r8, [rbp+var_20]
0x1400eafac  lea     rdx, aForcepassivemo; "ForcePassiveMode"
0x1400eafb3  call    sub_14008133C
0x1400eafb8  test    eax, eax
0x1400eafba  jns     short loc_1400EB001
0x1400eafbc  mov     rcx, cs:off_14018DE50
0x1400eafc3  lea     rdx, off_14018DE50
0x1400eafca  cmp     rcx, rdx
0x1400eafcd  jz      short loc_1400EAFEE
0x1400eafcf  mov     dl, 1
0x1400eafd1  test    [rcx+1Ch], dl
0x1400eafd4  jz      short loc_1400EAFEE
0x1400eafd6  mov     edx, 16h
0x1400eafdb  mov     rcx, [rcx+10h]
0x1400eafdf  lea     r8, qword_1401688E8
0x1400eafe6  mov     r9d, eax
0x1400eafe9  call    sub_140081450
0x1400eafee  mov     rcx, [rbp+var_18]
0x1400eaff2  test    rcx, rcx
0x1400eaff5  jz      short loc_1400EAFFD
0x1400eaff7  call    cs:MpConfigClose
0x1400eaffd  mov     dl, bl
0x1400eafff  jmp     short loc_1400EB019
0x1400eb001  mov     rcx, [rbp+var_18]
0x1400eb005  test    rcx, rcx
0x1400eb008  jz      short loc_1400EB010
0x1400eb00a  call    cs:MpConfigClose
0x1400eb010  cmp     [rbp+var_20], 2
0x1400eb014  setz    bl
0x1400eb017  mov     dl, 1
0x1400eb019  neg     dl
0x1400eb01b  sbb     eax, eax
0x1400eb01d  and     eax, ebx
0x1400eb01f  mov     rcx, [rbp+var_10]
0x1400eb023  xor     rcx, rsp; StackCookie
0x1400eb026  call    __security_check_cookie
0x1400eb02b  mov     rbx, [rsp+40h+arg_0]
0x1400eb030  add     rsp, 40h
0x1400eb034  pop     rbp
0x1400eb035  retn
```

# FaxSetReceiptsConfigurationW

- ea: `0x180014030`
- end: `0x18001430c`
- name: `FaxSetReceiptsConfigurationW`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013d30`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014030`
- `0x180033d10`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014211`
- `RPCRT4!NdrClientCall3` at `0x180014211`
- `KERNEL32!SetLastError` at `0x1800140b3`
- `KERNEL32!SetLastError` at `0x1800140f6`
- `KERNEL32!SetLastError` at `0x180014147`
- `KERNEL32!SetLastError` at `0x180014197`
- `KERNEL32!SetLastError` at `0x180014278`
- `KERNEL32!SetLastError` at `0x180014292`
- `KERNEL32!SetLastError` at `0x1800142c1`
- `KERNEL32!SetLastError` at `0x1800140b3`
- `KERNEL32!SetLastError` at `0x1800140f6`
- `KERNEL32!SetLastError` at `0x180014147`
- `KERNEL32!SetLastError` at `0x180014197`
- `KERNEL32!SetLastError` at `0x180014278`
- `KERNEL32!SetLastError` at `0x180014292`
- `KERNEL32!SetLastError` at `0x1800142c1`

## pseudocode

```c
__int64 __fastcall FaxSetReceiptsConfigurationW(__int64 a1, _DWORD *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 128;
LABEL_41:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 129;
    goto LABEL_41;
  }
  if ( *a2 != 72 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 130;
    goto LABEL_41;
  }
  if ( a2[2] > 2u )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 131;
    goto LABEL_41;
  }
  if ( (a2[1] & 0xFFFFFFFA) != 0 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 132;
    goto LABEL_41;
  }
  if ( (a2[1] & 1) != 0 && (unsigned int)(a2[8] - 1) > 0xFFFE )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids,
        (unsigned int)a2[8]);
    }
  }
  else
  {
    *a2 = GetWin32StructSize(&fax_receipts_config_fields);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x23u,
                              0,
                              **(_QWORD **)(a1 + 32),
                              a2).Pointer;
    *a2 = 72;
    if ( !Pointer )
      return 1;
    SetLastError(Pointer);
  }
  return 0;
}

```

## disassembly

```asm
0x180014030  mov     [rsp+arg_8], rbx
0x180014035  mov     [rsp+arg_10], rsi
0x18001403a  push    rdi
0x18001403b  push    r14
0x18001403d  push    r15
0x18001403f  sub     rsp, 40h
0x180014043  mov     rsi, rdx
0x180014046  mov     r14, rcx
0x180014049  lea     r15, WPP_GLOBAL_Control
0x180014050  mov     rcx, cs:WPP_GLOBAL_Control
0x180014057  mov     edi, 1000h
0x18001405c  cmp     rcx, r15
0x18001405f  jz      short loc_180014086
0x180014061  test    [rcx+1Ch], edi
0x180014064  jz      short loc_180014086
0x180014066  cmp     byte ptr [rcx+19h], 5
0x18001406a  jb      short loc_180014086
0x18001406c  mov     edx, 7Fh
0x180014071  lea     rbx, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180014078  mov     r8, rbx
0x18001407b  mov     rcx, [rcx+10h]
0x18001407f  call    WPP_SF_
0x180014084  jmp     short loc_18001408D
0x180014086  lea     rbx, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001408d  test    r14, r14
0x180014090  jz      loc_1800142BC
0x180014096  cmp     dword ptr [r14], 0
0x18001409a  jz      loc_1800142BC
0x1800140a0  cmp     dword ptr [r14+10h], 0
0x1800140a5  jnz     loc_1800142BC
0x1800140ab  test    rsi, rsi
0x1800140ae  jnz     short loc_1800140EC
0x1800140b0  lea     ecx, [rsi+57h]; dwErrCode
0x1800140b3  call    cs:__imp_SetLastError
0x1800140ba  nop     dword ptr [rax+rax+00h]
0x1800140bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140c6  cmp     rcx, r15
0x1800140c9  jz      loc_1800142F5
0x1800140cf  test    [rcx+1Ch], edi
0x1800140d2  jz      loc_1800142F5
0x1800140d8  cmp     byte ptr [rcx+19h], 2
0x1800140dc  jb      loc_1800142F5
0x1800140e2  mov     edx, 81h
0x1800140e7  jmp     loc_1800142E9
0x1800140ec  cmp     dword ptr [rsi], 48h ; 'H'
0x1800140ef  jz      short loc_18001412F
0x1800140f1  mov     ecx, 57h ; 'W'; dwErrCode
0x1800140f6  call    cs:__imp_SetLastError
0x1800140fd  nop     dword ptr [rax+rax+00h]
0x180014102  mov     rcx, cs:WPP_GLOBAL_Control
0x180014109  cmp     rcx, r15
0x18001410c  jz      loc_1800142F5
0x180014112  test    [rcx+1Ch], edi
0x180014115  jz      loc_1800142F5
0x18001411b  cmp     byte ptr [rcx+19h], 2
0x18001411f  jb      loc_1800142F5
0x180014125  mov     edx, 82h
0x18001412a  jmp     loc_1800142E9
0x18001412f  cmp     dword ptr [rsi+8], 2
0x180014133  ja      loc_18001428D
0x180014139  test    dword ptr [rsi+4], 0FFFFFFFAh
0x180014140  jz      short loc_180014180
0x180014142  mov     ecx, 57h ; 'W'; dwErrCode
0x180014147  call    cs:__imp_SetLastError
0x18001414e  nop     dword ptr [rax+rax+00h]
0x180014153  mov     rcx, cs:WPP_GLOBAL_Control
0x18001415a  cmp     rcx, r15
0x18001415d  jz      loc_1800142F5
0x180014163  test    [rcx+1Ch], edi
0x180014166  jz      loc_1800142F5
0x18001416c  cmp     byte ptr [rcx+19h], 2
0x180014170  jb      loc_1800142F5
0x180014176  mov     edx, 84h
0x18001417b  jmp     loc_1800142E9
0x180014180  test    byte ptr [rsi+4], 1
0x180014184  jz      short loc_1800141E0
0x180014186  mov     eax, [rsi+20h]
0x180014189  dec     eax
0x18001418b  cmp     eax, 0FFFEh
0x180014190  jbe     short loc_1800141E0
0x180014192  mov     ecx, 57h ; 'W'; dwErrCode
0x180014197  call    cs:__imp_SetLastError
0x18001419e  nop     dword ptr [rax+rax+00h]
0x1800141a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141aa  cmp     rcx, r15
0x1800141ad  jz      loc_1800142F5
0x1800141b3  test    [rcx+1Ch], edi
0x1800141b6  jz      loc_1800142F5
0x1800141bc  cmp     byte ptr [rcx+19h], 2
0x1800141c0  jb      loc_1800142F5
0x1800141c6  mov     edx, 85h
0x1800141cb  mov     r9d, [rsi+20h]
0x1800141cf  mov     r8, rbx
0x1800141d2  mov     rcx, [rcx+10h]
0x1800141d6  call    WPP_SF_d
0x1800141db  jmp     loc_1800142F5
0x1800141e0  lea     rcx, ?fax_receipts_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_receipts_config_fields
0x1800141e7  call    GetWin32StructSize
0x1800141ec  mov     [rsi], eax
0x1800141ee  mov     rax, [r14+20h]
0x1800141f2  mov     [rsp+58h+arg_0], 0
0x1800141fb  mov     [rsp+58h+var_38], rsi
0x180014200  mov     r9, [rax]
0x180014203  xor     r8d, r8d; pReturnValue
0x180014206  lea     edx, [r8+23h]; nProcNum
0x18001420a  lea     rcx, pProxyInfo; pProxyInfo
0x180014211  call    cs:__imp_NdrClientCall3
0x180014218  nop     dword ptr [rax+rax+00h]
0x18001421d  mov     rbx, rax
0x180014220  mov     [rsp+58h+arg_0], rax
0x180014225  mov     [rsp+58h+var_28], eax
0x180014229  mov     dword ptr [rsi], 48h ; 'H'
0x18001422f  jmp     short loc_180014272
0x180014231  mov     ebx, eax
0x180014233  mov     [rsp+58h+var_28], eax
0x180014237  lea     rdx, WPP_GLOBAL_Control
0x18001423e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014245  cmp     rcx, rdx
0x180014248  jz      short loc_180014272
0x18001424a  test    dword ptr [rcx+1Ch], 1000h
0x180014251  jz      short loc_180014272
0x180014253  cmp     byte ptr [rcx+19h], 2
0x180014257  jb      short loc_180014272
0x180014259  mov     edx, 86h
0x18001425e  mov     r9d, eax
0x180014261  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180014268  mov     rcx, [rcx+10h]
0x18001426c  call    WPP_SF_d
0x180014271  nop
0x180014272  test    ebx, ebx
0x180014274  jz      short loc_180014286
0x180014276  mov     ecx, ebx; dwErrCode
0x180014278  call    cs:__imp_SetLastError
0x18001427f  nop     dword ptr [rax+rax+00h]
0x180014284  jmp     short loc_1800142F5
0x180014286  mov     eax, 1
0x18001428b  jmp     short loc_1800142F7
0x18001428d  mov     ecx, 57h ; 'W'; dwErrCode
0x180014292  call    cs:__imp_SetLastError
0x180014299  nop     dword ptr [rax+rax+00h]
0x18001429e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142a5  cmp     rcx, r15
0x1800142a8  jz      short loc_1800142F5
0x1800142aa  test    [rcx+1Ch], edi
0x1800142ad  jz      short loc_1800142F5
0x1800142af  cmp     byte ptr [rcx+19h], 2
0x1800142b3  jb      short loc_1800142F5
0x1800142b5  mov     edx, 83h
0x1800142ba  jmp     short loc_1800142E9
0x1800142bc  mov     ecx, 6; dwErrCode
0x1800142c1  call    cs:__imp_SetLastError
0x1800142c8  nop     dword ptr [rax+rax+00h]
0x1800142cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142d4  cmp     rcx, r15
0x1800142d7  jz      short loc_1800142F5
0x1800142d9  test    [rcx+1Ch], edi
0x1800142dc  jz      short loc_1800142F5
0x1800142de  cmp     byte ptr [rcx+19h], 2
0x1800142e2  jb      short loc_1800142F5
0x1800142e4  mov     edx, 80h
0x1800142e9  mov     r8, rbx
0x1800142ec  mov     rcx, [rcx+10h]
0x1800142f0  call    WPP_SF_
0x1800142f5  xor     eax, eax
0x1800142f7  mov     rbx, [rsp+58h+arg_8]
0x1800142fc  mov     rsi, [rsp+58h+arg_10]
0x180014301  add     rsp, 40h
0x180014305  pop     r15
0x180014307  pop     r14
0x180014309  pop     rdi
0x18001430a  retn
```

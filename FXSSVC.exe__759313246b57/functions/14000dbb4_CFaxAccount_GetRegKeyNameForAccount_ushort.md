# CFaxAccount::GetRegKeyNameForAccount(ushort * *)

- ea: `0x14000dbb4`
- end: `0x14000dd6b`
- name: `?GetRegKeyNameForAccount@CFaxAccount@@AEBAKPEAPEAG@Z`
- size: `439`
- prototype: `unsigned int __fastcall(CFaxAccount *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d304`
- `0x14000e840`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x14000dbb4`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14000dc09`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000dc09`
- `KERNEL32!GetLastError` at `0x14000dc1c`
- `KERNEL32!GetLastError` at `0x14000dc1c`
- `KERNEL32!LocalFree` at `0x14000dd43`
- `KERNEL32!LocalFree` at `0x14000dd43`

## pseudocode

```c
__int64 __fastcall CFaxAccount::GetRegKeyNameForAccount(PSID *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  DWORD LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  LPWSTR StringSid; // [rsp+70h] [rbp+8h] BYREF

  StringSid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  if ( ConvertSidToStringSidW(this[1], &StringSid) )
  {
    v7 = -1;
    do
      ++v7;
    while ( StringSid[v7] );
    v8 = (unsigned int)(v7 + 34);
    v9 = v8;
    v10 = (unsigned __int16 *)pMemAlloc(2 * v8);
    v4 = v10;
    if ( v10 )
    {
      v6 = 0;
      v11 = StringCchPrintfW(v10, v9, L"%s\\%s", L"Software\\Microsoft\\Fax\\Accounts", StringSid);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
            (unsigned int)v11);
        }
        v6 = (unsigned __int16)v12;
        if ( (v12 & 0x1FFF0000) != 0x70000 )
          v6 = v12;
      }
      *a2 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          (unsigned int)v8);
      }
      v6 = 8;
    }
  }
  else
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, LastError);
    }
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    pMemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x14000dbb4  push    rbx
0x14000dbb6  push    rbp
0x14000dbb7  push    rsi
0x14000dbb8  push    rdi
0x14000dbb9  push    r12
0x14000dbbb  push    r14
0x14000dbbd  sub     rsp, 38h
0x14000dbc1  xor     ebp, ebp
0x14000dbc3  mov     r14, rdx
0x14000dbc6  mov     [rsp+68h+StringSid], rbp
0x14000dbcb  mov     rbx, rcx
0x14000dbce  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbd5  lea     r12, WPP_GLOBAL_Control
0x14000dbdc  cmp     rcx, r12
0x14000dbdf  jz      short loc_14000DC00
0x14000dbe1  test    byte ptr [rcx+1Ch], 4
0x14000dbe5  jz      short loc_14000DC00
0x14000dbe7  cmp     byte ptr [rcx+19h], 5
0x14000dbeb  jb      short loc_14000DC00
0x14000dbed  mov     rcx, [rcx+10h]
0x14000dbf1  lea     edx, [rbp+11h]
0x14000dbf4  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dbfb  call    WPP_SF_
0x14000dc00  mov     rcx, [rbx+8]; Sid
0x14000dc04  lea     rdx, [rsp+68h+StringSid]; StringSid
0x14000dc09  call    cs:__imp_ConvertSidToStringSidW
0x14000dc10  nop     dword ptr [rax+rax+00h]
0x14000dc15  test    eax, eax
0x14000dc17  jnz     short loc_14000DC6B
0x14000dc19  mov     rsi, rbp
0x14000dc1c  call    cs:__imp_GetLastError
0x14000dc23  nop     dword ptr [rax+rax+00h]
0x14000dc28  mov     ebx, eax
0x14000dc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc31  cmp     rcx, r12
0x14000dc34  jz      loc_14000DD39
0x14000dc3a  test    byte ptr [rcx+1Ch], 4
0x14000dc3e  jz      loc_14000DD39
0x14000dc44  cmp     byte ptr [rcx+19h], 2
0x14000dc48  jb      loc_14000DD39
0x14000dc4e  mov     rcx, [rcx+10h]
0x14000dc52  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dc59  mov     edx, 12h
0x14000dc5e  mov     r9d, eax
0x14000dc61  call    WPP_SF_d
0x14000dc66  jmp     loc_14000DD39
0x14000dc6b  mov     rcx, [rsp+68h+StringSid]
0x14000dc70  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000dc74  inc     rax
0x14000dc77  cmp     [rcx+rax*2], bp
0x14000dc7b  jnz     short loc_14000DC74
0x14000dc7d  lea     ebx, [rax+22h]
0x14000dc80  lea     rcx, [rbx+rbx]; dwBytes
0x14000dc84  mov     edi, ebx
0x14000dc86  call    pMemAlloc
0x14000dc8b  mov     rsi, rax
0x14000dc8e  test    rax, rax
0x14000dc91  jnz     short loc_14000DCC8
0x14000dc93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc9a  cmp     rcx, r12
0x14000dc9d  jz      short loc_14000DCC1
0x14000dc9f  test    byte ptr [rcx+1Ch], 4
0x14000dca3  jz      short loc_14000DCC1
0x14000dca5  cmp     byte ptr [rcx+19h], 2
0x14000dca9  jb      short loc_14000DCC1
0x14000dcab  mov     rcx, [rcx+10h]
0x14000dcaf  lea     edx, [rax+13h]
0x14000dcb2  mov     r9d, ebx
0x14000dcb5  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dcbc  call    WPP_SF_d
0x14000dcc1  mov     ebx, 8
0x14000dcc6  jmp     short loc_14000DD39
0x14000dcc8  mov     rax, [rsp+68h+StringSid]
0x14000dccd  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x14000dcd4  lea     r8, aSS_0; "%s\\%s"
0x14000dcdb  mov     [rsp+68h+var_48], rax
0x14000dce0  mov     rdx, rdi; unsigned __int64
0x14000dce3  mov     rcx, rsi; unsigned __int16 *
0x14000dce6  mov     ebx, ebp
0x14000dce8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000dced  mov     edi, eax
0x14000dcef  test    eax, eax
0x14000dcf1  jns     short loc_14000DD36
0x14000dcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dcfa  cmp     rcx, r12
0x14000dcfd  jz      short loc_14000DD23
0x14000dcff  test    byte ptr [rcx+1Ch], 4
0x14000dd03  jz      short loc_14000DD23
0x14000dd05  cmp     byte ptr [rcx+19h], 2
0x14000dd09  jb      short loc_14000DD23
0x14000dd0b  mov     rcx, [rcx+10h]
0x14000dd0f  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000dd16  mov     edx, 14h
0x14000dd1b  mov     r9d, eax
0x14000dd1e  call    WPP_SF_d
0x14000dd23  mov     eax, edi
0x14000dd25  movzx   ebx, di
0x14000dd28  and     eax, 1FFF0000h
0x14000dd2d  cmp     eax, 70000h
0x14000dd32  jz      short loc_14000DD36
0x14000dd34  mov     ebx, edi
0x14000dd36  mov     [r14], rsi
0x14000dd39  mov     rcx, [rsp+68h+StringSid]; hMem
0x14000dd3e  test    rcx, rcx
0x14000dd41  jz      short loc_14000DD4F
0x14000dd43  call    cs:__imp_LocalFree
0x14000dd4a  nop     dword ptr [rax+rax+00h]
0x14000dd4f  test    ebx, ebx
0x14000dd51  jz      short loc_14000DD5B
0x14000dd53  mov     rcx, rsi; lpMem
0x14000dd56  call    pMemFree
0x14000dd5b  mov     eax, ebx
0x14000dd5d  add     rsp, 38h
0x14000dd61  pop     r14
0x14000dd63  pop     r12
0x14000dd65  pop     rdi
0x14000dd66  pop     rsi
0x14000dd67  pop     rbp
0x14000dd68  pop     rbx
0x14000dd69  retn
```

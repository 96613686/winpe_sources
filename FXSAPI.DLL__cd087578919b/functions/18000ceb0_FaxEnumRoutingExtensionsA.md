# FaxEnumRoutingExtensionsA

- ea: `0x18000ceb0`
- end: `0x18000d120`
- name: `FaxEnumRoutingExtensionsA`
- size: `624`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000ceb0`
- `0x18000d130`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000cf3c`
- `KERNEL32!SetLastError` at `0x18000cf7e`
- `KERNEL32!SetLastError` at `0x18000d0d6`
- `KERNEL32!SetLastError` at `0x18000cf3c`
- `KERNEL32!SetLastError` at `0x18000cf7e`
- `KERNEL32!SetLastError` at `0x18000d0d6`
- `KERNEL32!GetLastError` at `0x18000cff2`
- `KERNEL32!GetLastError` at `0x18000d097`
- `KERNEL32!GetLastError` at `0x18000cff2`
- `KERNEL32!GetLastError` at `0x18000d097`

## pseudocode

```c
__int64 __fastcall FaxEnumRoutingExtensionsA(_DWORD *a1, _QWORD *a2, unsigned int *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  char *v11; // rcx
  unsigned __int64 v12; // rdi
  DWORD LastError; // eax
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp+20h] BYREF

  lpMem = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 309;
LABEL_39:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 310;
    goto LABEL_39;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 311;
    goto LABEL_39;
  }
  if ( (unsigned int)FaxEnumRoutingExtensionsW((__int64)a1, &lpMem, &v15) )
  {
    v9 = v15;
    v10 = 0;
    v11 = (char *)lpMem;
    *a3 = v15;
    *a2 = v11;
    if ( !v9 )
      return 1;
    while ( 1 )
    {
      v12 = (unsigned __int64)v10 << 6;
      if ( !(unsigned int)ConvertUnicodeStringInPlace(*(LPCWCH *)&v11[v12 + 8])
        || !(unsigned int)ConvertUnicodeStringInPlace(*(LPCWCH *)((char *)lpMem + v12 + 16))
        || !(unsigned int)ConvertUnicodeStringInPlace(*(LPCWCH *)((char *)lpMem + v12 + 24)) )
      {
        break;
      }
      if ( ++v10 >= v15 )
        return 1;
      v11 = (char *)lpMem;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    pMemFree(lpMem);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ceb0  mov     [rsp+arg_8], rbx
0x18000ceb5  push    rsi
0x18000ceb6  push    rdi
0x18000ceb7  push    r12
0x18000ceb9  push    r14
0x18000cebb  push    r15
0x18000cebd  sub     rsp, 20h
0x18000cec1  mov     rdi, r8
0x18000cec4  mov     [rsp+48h+lpMem], 0
0x18000cecd  mov     rsi, rdx
0x18000ced0  mov     [rsp+48h+arg_0], 0
0x18000ced8  mov     rbx, rcx
0x18000cedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cee2  lea     r15, WPP_GLOBAL_Control
0x18000cee9  lea     r12, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000cef0  mov     r14d, 1000h
0x18000cef6  cmp     rcx, r15
0x18000cef9  jz      short loc_18000CF18
0x18000cefb  test    [rcx+1Ch], r14d
0x18000ceff  jz      short loc_18000CF18
0x18000cf01  cmp     byte ptr [rcx+19h], 5
0x18000cf05  jb      short loc_18000CF18
0x18000cf07  mov     rcx, [rcx+10h]
0x18000cf0b  mov     edx, 134h
0x18000cf10  mov     r8, r12
0x18000cf13  call    WPP_SF_
0x18000cf18  test    rbx, rbx
0x18000cf1b  jz      loc_18000D0D1
0x18000cf21  cmp     dword ptr [rbx], 0
0x18000cf24  jz      loc_18000D0D1
0x18000cf2a  cmp     dword ptr [rbx+10h], 0
0x18000cf2e  jnz     loc_18000D0D1
0x18000cf34  test    rsi, rsi
0x18000cf37  jnz     short loc_18000CF76
0x18000cf39  lea     ecx, [rsi+57h]; dwErrCode
0x18000cf3c  call    cs:__imp_SetLastError
0x18000cf43  nop     dword ptr [rax+rax+00h]
0x18000cf48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf4f  cmp     rcx, r15
0x18000cf52  jz      loc_18000D10B
0x18000cf58  test    [rcx+1Ch], r14d
0x18000cf5c  jz      loc_18000D10B
0x18000cf62  cmp     byte ptr [rcx+19h], 2
0x18000cf66  jb      loc_18000D10B
0x18000cf6c  mov     edx, 136h
0x18000cf71  jmp     loc_18000D0FF
0x18000cf76  test    rdi, rdi
0x18000cf79  jnz     short loc_18000CFB8
0x18000cf7b  lea     ecx, [rdi+57h]; dwErrCode
0x18000cf7e  call    cs:__imp_SetLastError
0x18000cf85  nop     dword ptr [rax+rax+00h]
0x18000cf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf91  cmp     rcx, r15
0x18000cf94  jz      loc_18000D10B
0x18000cf9a  test    [rcx+1Ch], r14d
0x18000cf9e  jz      loc_18000D10B
0x18000cfa4  cmp     byte ptr [rcx+19h], 2
0x18000cfa8  jb      loc_18000D10B
0x18000cfae  mov     edx, 137h
0x18000cfb3  jmp     loc_18000D0FF
0x18000cfb8  lea     r8, [rsp+48h+arg_0]
0x18000cfbd  mov     rcx, rbx
0x18000cfc0  lea     rdx, [rsp+48h+lpMem]
0x18000cfc5  call    FaxEnumRoutingExtensionsW
0x18000cfca  test    eax, eax
0x18000cfcc  jnz     short loc_18000D01E
0x18000cfce  mov     rax, cs:WPP_GLOBAL_Control
0x18000cfd5  cmp     rax, r15
0x18000cfd8  jz      loc_18000D10B
0x18000cfde  test    [rax+1Ch], r14d
0x18000cfe2  jz      loc_18000D10B
0x18000cfe8  cmp     byte ptr [rax+19h], 2
0x18000cfec  jb      loc_18000D10B
0x18000cff2  call    cs:__imp_GetLastError
0x18000cff9  nop     dword ptr [rax+rax+00h]
0x18000cffe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d005  mov     edx, 138h
0x18000d00a  mov     r9d, eax
0x18000d00d  mov     r8, r12
0x18000d010  mov     rcx, [rcx+10h]
0x18000d014  call    WPP_SF_d
0x18000d019  jmp     loc_18000D10B
0x18000d01e  mov     eax, [rsp+48h+arg_0]
0x18000d022  xor     ebx, ebx
0x18000d024  mov     rcx, [rsp+48h+lpMem]
0x18000d029  mov     [rdi], eax
0x18000d02b  mov     [rsi], rcx
0x18000d02e  test    eax, eax
0x18000d030  jz      loc_18000D0CA
0x18000d036  mov     edi, ebx
0x18000d038  shl     rdi, 6
0x18000d03c  mov     rcx, [rdi+rcx+8]; lpWideCharStr
0x18000d041  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000d046  test    eax, eax
0x18000d048  jz      short loc_18000D07F
0x18000d04a  mov     rcx, [rsp+48h+lpMem]
0x18000d04f  mov     rcx, [rdi+rcx+10h]; lpWideCharStr
0x18000d054  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000d059  test    eax, eax
0x18000d05b  jz      short loc_18000D07F
0x18000d05d  mov     rcx, [rsp+48h+lpMem]
0x18000d062  mov     rcx, [rdi+rcx+18h]; lpWideCharStr
0x18000d067  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000d06c  test    eax, eax
0x18000d06e  jz      short loc_18000D07F
0x18000d070  inc     ebx
0x18000d072  cmp     ebx, [rsp+48h+arg_0]
0x18000d076  jnb     short loc_18000D0CA
0x18000d078  mov     rcx, [rsp+48h+lpMem]
0x18000d07d  jmp     short loc_18000D036
0x18000d07f  mov     rax, cs:WPP_GLOBAL_Control
0x18000d086  cmp     rax, r15
0x18000d089  jz      short loc_18000D0BE
0x18000d08b  test    [rax+1Ch], r14d
0x18000d08f  jz      short loc_18000D0BE
0x18000d091  cmp     byte ptr [rax+19h], 2
0x18000d095  jb      short loc_18000D0BE
0x18000d097  call    cs:__imp_GetLastError
0x18000d09e  nop     dword ptr [rax+rax+00h]
0x18000d0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0aa  mov     edx, 139h
0x18000d0af  mov     r9d, eax
0x18000d0b2  mov     r8, r12
0x18000d0b5  mov     rcx, [rcx+10h]
0x18000d0b9  call    WPP_SF_d
0x18000d0be  mov     rcx, [rsp+48h+lpMem]; lpMem
0x18000d0c3  call    pMemFree
0x18000d0c8  jmp     short loc_18000D10B
0x18000d0ca  mov     eax, 1
0x18000d0cf  jmp     short loc_18000D10D
0x18000d0d1  mov     ecx, 6; dwErrCode
0x18000d0d6  call    cs:__imp_SetLastError
0x18000d0dd  nop     dword ptr [rax+rax+00h]
0x18000d0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0e9  cmp     rcx, r15
0x18000d0ec  jz      short loc_18000D10B
0x18000d0ee  test    [rcx+1Ch], r14d
0x18000d0f2  jz      short loc_18000D10B
0x18000d0f4  cmp     byte ptr [rcx+19h], 2
0x18000d0f8  jb      short loc_18000D10B
0x18000d0fa  mov     edx, 135h
0x18000d0ff  mov     rcx, [rcx+10h]
0x18000d103  mov     r8, r12
0x18000d106  call    WPP_SF_
0x18000d10b  xor     eax, eax
0x18000d10d  mov     rbx, [rsp+48h+arg_8]
0x18000d112  add     rsp, 20h
0x18000d116  pop     r15
0x18000d118  pop     r14
0x18000d11a  pop     r12
0x18000d11c  pop     rdi
0x18000d11d  pop     rsi
0x18000d11e  retn
```

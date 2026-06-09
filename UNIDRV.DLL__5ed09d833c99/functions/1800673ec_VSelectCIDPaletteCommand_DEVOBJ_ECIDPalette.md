# VSelectCIDPaletteCommand(_DEVOBJ *,ECIDPalette)

- ea: `0x1800673ec`
- end: `0x1800674ff`
- name: `?VSelectCIDPaletteCommand@@YAXPEAU_DEVOBJ@@W4ECIDPalette@@@Z`
- size: `275`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180045b00`
- `0x180068e14`
- `0x180069090`
- `0x18006a240`
- `0x18006a304`

## callees

- `0x180033050`
- `0x1800338d4`
- `0x180049d00`
- `0x1800673ec`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800674d5`
- `KERNEL32!SetLastError` at `0x1800674d5`

## pseudocode

```c
void __fastcall VSelectCIDPaletteCommand(__int64 a1, int a2)
{
  _DWORD *v4; // rdi
  signed int v5; // eax
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ecx
  unsigned __int8 v12[32]; // [rsp+20h] [rbp-38h] BYREF

  if ( !a1 )
    goto LABEL_19;
  v4 = *(_DWORD **)(a1 + 8);
  if ( !v4[1116] )
    return;
  if ( !v4 )
  {
LABEL_19:
    SetLastError(0xDu);
    return;
  }
  if ( v4[1083] == a2 )
    return;
  v5 = iDrvPrintfSafeA((__int64)v12, 32, (__int64)"\x1B&p%dS", a2);
  if ( v5 > 0 )
    PCL_Output((struct _DEVOBJ *)a1, v12, v5);
  v4[1083] = a2;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v11 = 1;
LABEL_17:
    if ( v4[1082] != v11 )
    {
      v4[1084] = -1;
      v4[1082] = v11;
    }
    return;
  }
  v7 = v6 - 2;
  if ( !v7 )
  {
    v11 = 3;
    goto LABEL_17;
  }
  v8 = v7 - 2;
  if ( !v8 )
  {
    v11 = 0;
    goto LABEL_17;
  }
  v9 = v8 - 1;
  if ( !v9 || (v10 = v9 - 1) == 0 || (unsigned int)(v10 - 1) <= 1 )
  {
    v11 = v4[51] != 0 ? 4 : 2;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800673ec  mov     [rsp+arg_10], rbx
0x1800673f1  mov     [rsp+arg_18], rsi
0x1800673f6  push    rdi
0x1800673f7  sub     rsp, 50h
0x1800673fb  mov     rax, cs:__security_cookie
0x180067402  xor     rax, rsp
0x180067405  mov     [rsp+58h+var_18], rax
0x18006740a  mov     ebx, edx
0x18006740c  mov     rsi, rcx
0x18006740f  test    rcx, rcx
0x180067412  jz      loc_1800674D0
0x180067418  mov     rdi, [rcx+8]
0x18006741c  cmp     dword ptr [rdi+1170h], 0
0x180067423  jz      loc_1800674E1
0x180067429  test    rdi, rdi
0x18006742c  jz      loc_1800674D0
0x180067432  cmp     [rdi+10ECh], edx
0x180067438  jz      loc_1800674E1
0x18006743e  mov     r9d, edx
0x180067441  lea     r8, aPDs; "\x1B&p%dS"
0x180067448  mov     edx, 20h ; ' '
0x18006744d  lea     rcx, [rsp+58h+var_38]
0x180067452  call    iDrvPrintfSafeA
0x180067457  test    eax, eax
0x180067459  jle     short loc_18006746B
0x18006745b  mov     r8d, eax; unsigned int
0x18006745e  lea     rdx, [rsp+58h+var_38]; unsigned __int8 *
0x180067463  mov     rcx, rsi; struct _DEVOBJ *
0x180067466  call    ?PCL_Output@@YAHPEAU_DEVOBJ@@PEAXK@Z; PCL_Output(_DEVOBJ *,void *,ulong)
0x18006746b  mov     [rdi+10ECh], ebx
0x180067471  sub     ebx, 1
0x180067474  jz      short loc_1800674B1
0x180067476  sub     ebx, 2
0x180067479  jz      short loc_1800674AA
0x18006747b  sub     ebx, 2
0x18006747e  jz      short loc_1800674A6
0x180067480  sub     ebx, 1
0x180067483  jz      short loc_180067494
0x180067485  sub     ebx, 1
0x180067488  jz      short loc_180067494
0x18006748a  sub     ebx, 1
0x18006748d  jz      short loc_180067494
0x18006748f  cmp     ebx, 1
0x180067492  jnz     short loc_1800674E1
0x180067494  mov     eax, [rdi+0CCh]
0x18006749a  neg     eax
0x18006749c  sbb     ecx, ecx
0x18006749e  and     ecx, 2
0x1800674a1  add     ecx, 2
0x1800674a4  jmp     short loc_1800674B6
0x1800674a6  xor     ecx, ecx
0x1800674a8  jmp     short loc_1800674B6
0x1800674aa  mov     ecx, 3
0x1800674af  jmp     short loc_1800674B6
0x1800674b1  mov     ecx, 1
0x1800674b6  cmp     [rdi+10E8h], ecx
0x1800674bc  jz      short loc_1800674E1
0x1800674be  mov     dword ptr [rdi+10F0h], 0FFFFFFFFh
0x1800674c8  mov     [rdi+10E8h], ecx
0x1800674ce  jmp     short loc_1800674E1
0x1800674d0  mov     ecx, 0Dh; dwErrCode
0x1800674d5  call    cs:__imp_SetLastError
0x1800674dc  nop     dword ptr [rax+rax+00h]
0x1800674e1  mov     rcx, [rsp+58h+var_18]
0x1800674e6  xor     rcx, rsp; StackCookie
0x1800674e9  call    __security_check_cookie
0x1800674ee  mov     rbx, [rsp+58h+arg_10]
0x1800674f3  mov     rsi, [rsp+58h+arg_18]
0x1800674f8  add     rsp, 50h
0x1800674fc  pop     rdi
0x1800674fd  retn
```

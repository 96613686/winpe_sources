# VSelectCIDPaletteCommand(_DEVOBJ *,ECIDPalette)

- ea: `0x180065ca0`
- end: `0x180065dac`
- name: `?VSelectCIDPaletteCommand@@YAXPEAU_DEVOBJ@@W4ECIDPalette@@@Z`
- size: `268`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800447dc`
- `0x1800675f4`
- `0x180067864`
- `0x1800689a0`
- `0x180068a5c`

## callees

- `0x180032728`
- `0x180032f50`
- `0x1800487e0`
- `0x180065ca0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180065d89`
- `KERNEL32!SetLastError` at `0x180065d89`

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
  v5 = iDrvPrintfSafeA(v12, 32, "\x1B&p%dS", a2);
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
0x180065ca0  mov     [rsp+arg_10], rbx
0x180065ca5  mov     [rsp+arg_18], rsi
0x180065caa  push    rdi
0x180065cab  sub     rsp, 50h
0x180065caf  mov     rax, cs:__security_cookie
0x180065cb6  xor     rax, rsp
0x180065cb9  mov     [rsp+58h+var_18], rax
0x180065cbe  mov     ebx, edx
0x180065cc0  mov     rsi, rcx
0x180065cc3  test    rcx, rcx
0x180065cc6  jz      loc_180065D84
0x180065ccc  mov     rdi, [rcx+8]
0x180065cd0  cmp     dword ptr [rdi+1170h], 0
0x180065cd7  jz      loc_180065D8F
0x180065cdd  test    rdi, rdi
0x180065ce0  jz      loc_180065D84
0x180065ce6  cmp     [rdi+10ECh], edx
0x180065cec  jz      loc_180065D8F
0x180065cf2  mov     r9d, edx
0x180065cf5  lea     r8, aPDs; "\x1B&p%dS"
0x180065cfc  mov     edx, 20h ; ' '
0x180065d01  lea     rcx, [rsp+58h+var_38]
0x180065d06  call    iDrvPrintfSafeA
0x180065d0b  test    eax, eax
0x180065d0d  jle     short loc_180065D1F
0x180065d0f  mov     r8d, eax; unsigned int
0x180065d12  lea     rdx, [rsp+58h+var_38]; unsigned __int8 *
0x180065d17  mov     rcx, rsi; struct _DEVOBJ *
0x180065d1a  call    ?PCL_Output@@YAHPEAU_DEVOBJ@@PEAXK@Z; PCL_Output(_DEVOBJ *,void *,ulong)
0x180065d1f  mov     [rdi+10ECh], ebx
0x180065d25  sub     ebx, 1
0x180065d28  jz      short loc_180065D65
0x180065d2a  sub     ebx, 2
0x180065d2d  jz      short loc_180065D5E
0x180065d2f  sub     ebx, 2
0x180065d32  jz      short loc_180065D5A
0x180065d34  sub     ebx, 1
0x180065d37  jz      short loc_180065D48
0x180065d39  sub     ebx, 1
0x180065d3c  jz      short loc_180065D48
0x180065d3e  sub     ebx, 1
0x180065d41  jz      short loc_180065D48
0x180065d43  cmp     ebx, 1
0x180065d46  jnz     short loc_180065D8F
0x180065d48  mov     eax, [rdi+0CCh]
0x180065d4e  neg     eax
0x180065d50  sbb     ecx, ecx
0x180065d52  and     ecx, 2
0x180065d55  add     ecx, 2
0x180065d58  jmp     short loc_180065D6A
0x180065d5a  xor     ecx, ecx
0x180065d5c  jmp     short loc_180065D6A
0x180065d5e  mov     ecx, 3
0x180065d63  jmp     short loc_180065D6A
0x180065d65  mov     ecx, 1
0x180065d6a  cmp     [rdi+10E8h], ecx
0x180065d70  jz      short loc_180065D8F
0x180065d72  mov     dword ptr [rdi+10F0h], 0FFFFFFFFh
0x180065d7c  mov     [rdi+10E8h], ecx
0x180065d82  jmp     short loc_180065D8F
0x180065d84  mov     ecx, 0Dh; dwErrCode
0x180065d89  call    cs:__imp_SetLastError
0x180065d8f  mov     rcx, [rsp+58h+var_18]
0x180065d94  xor     rcx, rsp; StackCookie
0x180065d97  call    __security_check_cookie
0x180065d9c  mov     rbx, [rsp+58h+arg_10]
0x180065da1  mov     rsi, [rsp+58h+arg_18]
0x180065da6  add     rsp, 50h
0x180065daa  pop     rdi
0x180065dab  retn
```

# FaxSetArchiveConfigurationA

- ea: `0x180010f80`
- end: `0x180011157`
- name: `FaxSetArchiveConfigurationA`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x180010f80`
- `0x180011160`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001100b`
- `KERNEL32!SetLastError` at `0x18001104f`
- `KERNEL32!SetLastError` at `0x180011111`
- `KERNEL32!SetLastError` at `0x18001100b`
- `KERNEL32!SetLastError` at `0x18001104f`
- `KERNEL32!SetLastError` at `0x180011111`

## pseudocode

```c
__int64 __fastcall FaxSetArchiveConfigurationA(_DWORD *a1, unsigned int a2, __int64 a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const CHAR *v8; // rcx
  __int128 v9; // xmm1
  unsigned int v10; // ebx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v13; // [rsp+30h] [rbp-58h]
  __int64 v14; // [rsp+40h] [rbp-48h]

  *(_OWORD *)lpMem = 0;
  v14 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v7 = 160;
    goto LABEL_29;
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
    v7 = 161;
    goto LABEL_29;
  }
  if ( *(_DWORD *)a3 != 40 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 162;
    goto LABEL_29;
  }
  v8 = *(const CHAR **)(a3 + 8);
  v9 = *(_OWORD *)(a3 + 16);
  lpMem[0] = *(LPVOID *)a3;
  lpMem[1] = 0;
  v14 = *(_QWORD *)(a3 + 32);
  LODWORD(lpMem[0]) = 40;
  v13 = v9;
  if ( !v8 || (lpMem[1] = AnsiStringToUnicodeString(v8)) != 0 )
  {
    v10 = FaxSetArchiveConfigurationW((__int64)a1, a2, (__int64)lpMem);
    pMemFree(lpMem[1]);
    return v10;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 163;
LABEL_29:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180010f80  push    rbx
0x180010f82  push    rsi
0x180010f83  push    rdi
0x180010f84  push    r12
0x180010f86  push    r14
0x180010f88  push    r15
0x180010f8a  sub     rsp, 58h
0x180010f8e  xorps   xmm0, xmm0
0x180010f91  xor     eax, eax
0x180010f93  movups  xmmword ptr [rsp+88h+lpMem], xmm0
0x180010f98  mov     [rsp+88h+var_48], rax
0x180010f9d  mov     rdi, r8
0x180010fa0  movups  [rsp+88h+var_58], xmm0
0x180010fa5  mov     esi, edx
0x180010fa7  mov     rbx, rcx
0x180010faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fb1  lea     r12, WPP_GLOBAL_Control
0x180010fb8  lea     r15, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010fbf  mov     r14d, 1000h
0x180010fc5  cmp     rcx, r12
0x180010fc8  jz      short loc_180010FE7
0x180010fca  test    [rcx+1Ch], r14d
0x180010fce  jz      short loc_180010FE7
0x180010fd0  cmp     byte ptr [rcx+19h], 5
0x180010fd4  jb      short loc_180010FE7
0x180010fd6  mov     rcx, [rcx+10h]
0x180010fda  mov     edx, 9Fh
0x180010fdf  mov     r8, r15
0x180010fe2  call    WPP_SF_
0x180010fe7  test    rbx, rbx
0x180010fea  jz      loc_18001110C
0x180010ff0  cmp     dword ptr [rbx], 0
0x180010ff3  jz      loc_18001110C
0x180010ff9  cmp     dword ptr [rbx+10h], 0
0x180010ffd  jnz     loc_18001110C
0x180011003  test    rdi, rdi
0x180011006  jnz     short loc_180011045
0x180011008  lea     ecx, [rdi+57h]; dwErrCode
0x18001100b  call    cs:__imp_SetLastError
0x180011012  nop     dword ptr [rax+rax+00h]
0x180011017  mov     rcx, cs:WPP_GLOBAL_Control
0x18001101e  cmp     rcx, r12
0x180011021  jz      loc_180011146
0x180011027  test    [rcx+1Ch], r14d
0x18001102b  jz      loc_180011146
0x180011031  cmp     byte ptr [rcx+19h], 2
0x180011035  jb      loc_180011146
0x18001103b  mov     edx, 0A1h
0x180011040  jmp     loc_18001113A
0x180011045  cmp     dword ptr [rdi], 28h ; '('
0x180011048  jz      short loc_180011089
0x18001104a  mov     ecx, 57h ; 'W'; dwErrCode
0x18001104f  call    cs:__imp_SetLastError
0x180011056  nop     dword ptr [rax+rax+00h]
0x18001105b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011062  cmp     rcx, r12
0x180011065  jz      loc_180011146
0x18001106b  test    [rcx+1Ch], r14d
0x18001106f  jz      loc_180011146
0x180011075  cmp     byte ptr [rcx+19h], 2
0x180011079  jb      loc_180011146
0x18001107f  mov     edx, 0A2h
0x180011084  jmp     loc_18001113A
0x180011089  movups  xmm0, xmmword ptr [rdi]
0x18001108c  mov     rcx, [rdi+8]; lpMultiByteStr
0x180011090  movups  xmm1, xmmword ptr [rdi+10h]
0x180011094  movups  xmmword ptr [rsp+88h+lpMem], xmm0
0x180011099  mov     [rsp+88h+lpMem+8], 0
0x1800110a2  movsd   xmm0, qword ptr [rdi+20h]
0x1800110a7  movsd   [rsp+88h+var_48], xmm0
0x1800110ad  mov     dword ptr [rsp+88h+lpMem], 28h ; '('
0x1800110b5  movups  [rsp+88h+var_58], xmm1
0x1800110ba  test    rcx, rcx
0x1800110bd  jz      short loc_1800110ED
0x1800110bf  call    AnsiStringToUnicodeString
0x1800110c4  mov     [rsp+88h+lpMem+8], rax
0x1800110c9  test    rax, rax
0x1800110cc  jnz     short loc_1800110ED
0x1800110ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110d5  cmp     rcx, r12
0x1800110d8  jz      short loc_180011146
0x1800110da  test    [rcx+1Ch], r14d
0x1800110de  jz      short loc_180011146
0x1800110e0  cmp     byte ptr [rcx+19h], 2
0x1800110e4  jb      short loc_180011146
0x1800110e6  mov     edx, 0A3h
0x1800110eb  jmp     short loc_18001113A
0x1800110ed  lea     r8, [rsp+88h+lpMem]
0x1800110f2  mov     edx, esi
0x1800110f4  mov     rcx, rbx
0x1800110f7  call    FaxSetArchiveConfigurationW
0x1800110fc  mov     rcx, [rsp+88h+lpMem+8]; lpMem
0x180011101  mov     ebx, eax
0x180011103  call    pMemFree
0x180011108  mov     eax, ebx
0x18001110a  jmp     short loc_180011148
0x18001110c  mov     ecx, 6; dwErrCode
0x180011111  call    cs:__imp_SetLastError
0x180011118  nop     dword ptr [rax+rax+00h]
0x18001111d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011124  cmp     rcx, r12
0x180011127  jz      short loc_180011146
0x180011129  test    [rcx+1Ch], r14d
0x18001112d  jz      short loc_180011146
0x18001112f  cmp     byte ptr [rcx+19h], 2
0x180011133  jb      short loc_180011146
0x180011135  mov     edx, 0A0h
0x18001113a  mov     rcx, [rcx+10h]
0x18001113e  mov     r8, r15
0x180011141  call    WPP_SF_
0x180011146  xor     eax, eax
0x180011148  add     rsp, 58h
0x18001114c  pop     r15
0x18001114e  pop     r14
0x180011150  pop     r12
0x180011152  pop     rdi
0x180011153  pop     rsi
0x180011154  pop     rbx
0x180011155  retn
```

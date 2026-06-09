# ConvertStringToGuid(ushort const *,_GUID *)

- ea: `0x140015464`
- end: `0x14001560d`
- name: `?ConvertStringToGuid@@YAJPEBGPEAU_GUID@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000a034`
- `0x14000a14c`
- `0x14000cb14`

## callees

- `0x14000740c`
- `0x140015464`
- `0x14001817c`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400154cd`
- `KERNEL32!GetLastError` at `0x140015584`
- `KERNEL32!GetLastError` at `0x1400155aa`
- `KERNEL32!GetLastError` at `0x1400155bf`
- `KERNEL32!GetLastError` at `0x1400154cd`
- `KERNEL32!GetLastError` at `0x140015584`
- `KERNEL32!GetLastError` at `0x1400155aa`
- `KERNEL32!GetLastError` at `0x1400155bf`
- `RPCRT4!UuidFromStringW` at `0x1400155a0`
- `RPCRT4!UuidFromStringW` at `0x1400155a0`

## string_xrefs

- `0x1400154d3`: `Copy String StringCchLength() failed with hr = 0x%1!x!. GetLastError () 0x%2!x!`
- `0x14001558a`: `StringCchCopyN failed with with hr = 0x%1!x!. GetLastError () 0x%2!x!`

## pseudocode

```c
__int64 __fastcall ConvertStringToGuid(const unsigned __int16 *a1, struct _GUID *a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // r11
  DWORD LastError; // eax
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // r11
  unsigned __int16 *v8; // r8
  __int64 v9; // rdx
  unsigned __int16 *v10; // rcx
  DWORD v11; // eax
  unsigned __int16 *v12; // rcx
  signed int v13; // eax
  DWORD v14; // eax
  unsigned __int64 v16; // [rsp+20h] [rbp-238h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-230h] BYREF
  unsigned __int16 StringUuid[256]; // [rsp+40h] [rbp-218h] BYREF

  v16 = 0;
  Uuid = 0;
  if ( !a1 || !*a1 || !a2 )
    return (unsigned int)-2147024809;
  v3 = StringCchLengthW(a1, 0x7FFFFFFFu, &v16);
  if ( (v3 & 0x80000000) != 0 )
  {
    LastError = GetLastError();
    LogError(L"Copy String StringCchLength() failed with hr = 0x%1!x!. GetLastError () 0x%2!x!", v3, LastError);
    return v3;
  }
  if ( v16 <= 2 )
    return (unsigned int)-2147024809;
  if ( *v4 == 123 && v4[v16 - 1] == 125 )
  {
    v6 = v16 - 2;
    if ( v16 - 2 > 0x7FFFFFFE )
    {
      StringUuid[0] = 0;
      v3 = -2147024809;
LABEL_19:
      v11 = GetLastError();
      LogError(L"StringCchCopyN failed with with hr = 0x%1!x!. GetLastError () 0x%2!x!", v3, v11);
      return v3;
    }
    v7 = v4 + 1;
    v8 = StringUuid;
    v9 = 256;
    do
    {
      if ( !v6 )
        break;
      if ( !*v7 )
        break;
      *v8++ = *v7++;
      --v6;
      --v9;
    }
    while ( v9 );
    v10 = v8 - 1;
    if ( v9 )
      v10 = v8;
    v3 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
    if ( !v9 )
      goto LABEL_19;
    v12 = StringUuid;
  }
  else
  {
    v12 = v4;
  }
  if ( UuidFromStringW(v12, &Uuid) )
  {
    v13 = GetLastError();
    v3 = v13;
    if ( v13 > 0 )
      v3 = (unsigned __int16)v13 | 0x80070000;
    v14 = GetLastError();
    LogError(L"UuidFromString failed with with hr = 0x%1!x!. GetLastError () 0x%2!x!", v3, v14);
  }
  else
  {
    *a2 = Uuid;
  }
  return v3;
}

```

## disassembly

```asm
0x140015464  mov     [rsp+arg_10], rbx
0x140015469  mov     [rsp+arg_18], rsi
0x14001546e  push    rdi
0x14001546f  sub     rsp, 250h
0x140015476  mov     rax, cs:__security_cookie
0x14001547d  xor     rax, rsp
0x140015480  mov     [rsp+258h+var_18], rax
0x140015488  xor     esi, esi
0x14001548a  xorps   xmm0, xmm0
0x14001548d  mov     [rsp+258h+var_238], rsi
0x140015492  mov     rdi, rdx
0x140015495  mov     r11, rcx
0x140015498  movups  xmmword ptr [rsp+258h+Uuid.Data1], xmm0
0x14001549d  test    rcx, rcx
0x1400154a0  jz      loc_1400155E1
0x1400154a6  cmp     [rcx], si
0x1400154a9  jz      loc_1400155E1
0x1400154af  test    rdx, rdx
0x1400154b2  jz      loc_1400155E1
0x1400154b8  lea     r8, [rsp+258h+var_238]; unsigned __int64 *
0x1400154bd  mov     edx, 7FFFFFFFh; unsigned __int64
0x1400154c2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400154c7  mov     ebx, eax
0x1400154c9  test    eax, eax
0x1400154cb  jns     short loc_1400154E9
0x1400154cd  call    cs:__imp_GetLastError
0x1400154d3  lea     rcx, aCopyStringStri; "Copy String StringCchLength() failed wi"...
0x1400154da  mov     r8d, eax
0x1400154dd  mov     edx, ebx
0x1400154df  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400154e4  jmp     loc_1400155E6
0x1400154e9  mov     rax, [rsp+258h+var_238]
0x1400154ee  cmp     rax, 2
0x1400154f2  jbe     loc_1400155E1
0x1400154f8  mov     ecx, 7Bh ; '{'
0x1400154fd  cmp     cx, [r11]
0x140015501  jnz     loc_1400155D1
0x140015507  mov     ecx, 7Dh ; '}'
0x14001550c  cmp     cx, [r11+rax*2-2]
0x140015512  jnz     loc_1400155D1
0x140015518  add     rax, 0FFFFFFFFFFFFFFFEh
0x14001551c  cmp     rax, 7FFFFFFEh
0x140015522  jbe     short loc_140015530
0x140015524  mov     [rsp+258h+StringUuid], si
0x140015529  mov     ebx, 80070057h
0x14001552e  jmp     short loc_140015584
0x140015530  add     r11, 2
0x140015534  lea     r8, [rsp+258h+StringUuid]
0x140015539  mov     edx, 100h
0x14001553e  test    rax, rax
0x140015541  jz      short loc_140015561
0x140015543  movzx   ecx, word ptr [r11]
0x140015547  test    cx, cx
0x14001554a  jz      short loc_140015561
0x14001554c  mov     [r8], cx
0x140015550  add     r11, 2
0x140015554  add     r8, 2
0x140015558  dec     rax
0x14001555b  sub     rdx, 1
0x14001555f  jnz     short loc_14001553E
0x140015561  test    rdx, rdx
0x140015564  lea     rcx, [r8-2]
0x140015568  mov     rax, rdx
0x14001556b  cmovnz  rcx, r8
0x14001556f  neg     rax
0x140015572  sbb     ebx, ebx
0x140015574  not     ebx
0x140015576  and     ebx, 8007007Ah
0x14001557c  mov     [rcx], si
0x14001557f  test    rdx, rdx
0x140015582  jnz     short loc_140015596
0x140015584  call    cs:__imp_GetLastError
0x14001558a  lea     rcx, aStringcchcopyn; "StringCchCopyN failed with with hr = 0x"...
0x140015591  jmp     loc_1400154DA
0x140015596  lea     rcx, [rsp+258h+StringUuid]; StringUuid
0x14001559b  lea     rdx, [rsp+258h+Uuid]; Uuid
0x1400155a0  call    cs:__imp_UuidFromStringW
0x1400155a6  test    eax, eax
0x1400155a8  jz      short loc_1400155D6
0x1400155aa  call    cs:__imp_GetLastError
0x1400155b0  mov     ebx, eax
0x1400155b2  test    eax, eax
0x1400155b4  jle     short loc_1400155BF
0x1400155b6  movzx   ebx, ax
0x1400155b9  or      ebx, 80070000h
0x1400155bf  call    cs:__imp_GetLastError
0x1400155c5  lea     rcx, aUuidfromstring; "UuidFromString failed with with hr = 0x"...
0x1400155cc  jmp     loc_1400154DA
0x1400155d1  mov     rcx, r11
0x1400155d4  jmp     short loc_14001559B
0x1400155d6  movups  xmm0, xmmword ptr [rsp+258h+Uuid.Data1]
0x1400155db  movdqu  xmmword ptr [rdi], xmm0
0x1400155df  jmp     short loc_1400155E6
0x1400155e1  mov     ebx, 80070057h
0x1400155e6  mov     eax, ebx
0x1400155e8  mov     rcx, [rsp+258h+var_18]
0x1400155f0  xor     rcx, rsp; StackCookie
0x1400155f3  call    __security_check_cookie
0x1400155f8  lea     r11, [rsp+258h+var_8]
0x140015600  mov     rbx, [r11+20h]
0x140015604  mov     rsi, [r11+28h]
0x140015608  mov     rsp, r11
0x14001560b  pop     rdi
0x14001560c  retn
```

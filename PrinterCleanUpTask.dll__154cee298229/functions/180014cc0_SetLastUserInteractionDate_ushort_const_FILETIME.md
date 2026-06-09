# _SetLastUserInteractionDate(ushort const *,_FILETIME)

- ea: `0x180014cc0`
- end: `0x180014d7b`
- name: `?_SetLastUserInteractionDate@@YAJPEBGU_FILETIME@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011ea8`
- `0x180015400`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180014cc0`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014d3d`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014d3d`

## string_xrefs

- `0x180014d4f`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall _SetLastUserInteractionDate(const unsigned __int16 *a1, struct _FILETIME a2)
{
  int v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  int v5[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v6; // [rsp+28h] [rbp-40h] BYREF
  int v7; // [rsp+38h] [rbp-30h]
  int v8; // [rsp+3Ch] [rbp-2Ch]
  __int64 v9; // [rsp+40h] [rbp-28h]
  int v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+4Ch] [rbp-1Ch]
  int *v12; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(struct _FILETIME *)v5 = a2;
  v6 = xmmword_18001C118;
  v7 = 2;
  v8 = 0;
  v9 = 0;
  v10 = 16;
  v11 = 8;
  v12 = v5;
  v2 = DevSetObjectProperties(2, a1, 1, &v6);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
        (const char *)(unsigned int)v2,
        v5[0]);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x84,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180014cc0  mov     r11, rsp
0x180014cc3  sub     rsp, 68h
0x180014cc7  mov     rax, cs:__security_cookie
0x180014cce  xor     rax, rsp
0x180014cd1  mov     [rsp+68h+var_10], rax
0x180014cd6  mov     rax, rdx
0x180014cd9  shr     rax, 20h
0x180014cdd  mov     [rsp+68h+var_48], edx; int
0x180014ce1  mov     [rsp+68h+var_48+4], eax
0x180014ce5  mov     rax, qword ptr [rsp+68h+var_48]
0x180014cea  mov     [r11-48h], rax
0x180014cee  movups  xmm0, cs:xmmword_18001C118
0x180014cf5  movups  [rsp+68h+var_40], xmm0
0x180014cfa  mov     eax, cs:dword_18001C128
0x180014d00  mov     [rsp+68h+var_30], eax
0x180014d04  mov     [rsp+68h+var_2C], 0
0x180014d0c  mov     qword ptr [r11-28h], 0
0x180014d14  mov     [rsp+68h+var_20], 10h
0x180014d1c  mov     [rsp+68h+var_1C], 8
0x180014d24  lea     rax, [r11-48h]
0x180014d28  mov     [r11-18h], rax
0x180014d2c  lea     r9, [r11-40h]
0x180014d30  mov     r8d, 1
0x180014d36  mov     rdx, rcx
0x180014d39  lea     ecx, [r8+1]
0x180014d3d  call    cs:__imp_DevSetObjectProperties
0x180014d43  mov     rcx, [rsp+68h]; this
0x180014d48  test    eax, eax
0x180014d4a  jns     short loc_180014D60
0x180014d4c  mov     r9d, eax; char *
0x180014d4f  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180014d56  mov     edx, 80h; void *
0x180014d5b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014d60  xor     eax, eax
0x180014d62  jmp     short loc_180014D68
0x180014d64  mov     eax, [rsp+68h+var_48]
0x180014d68  mov     rcx, [rsp+68h+var_10]
0x180014d6d  xor     rcx, rsp; StackCookie
0x180014d70  call    __security_check_cookie
0x180014d75  add     rsp, 68h
0x180014d79  retn
```

# CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,ushort const *,ulong)

- ea: `0x14000ec7c`
- end: `0x14000ed1b`
- name: `?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBGK@Z`
- size: `159`
- prototype: `__int64 __fastcall(CommonUtil *this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004588`
- `0x14000ed24`

## callees

- `0x1400071c0`
- `0x14000ec7c`
- `0x14000f084`
- `0x140011234`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000eccc`
- `KERNEL32!LoadLibraryExW` at `0x14000eccc`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadLibraryEx(CommonUtil *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  DWORD v3; // edi
  HMODULE Library; // rax
  unsigned int LastFailure; // eax
  int v8; // r8d
  unsigned int v9; // ebx

  v3 = (unsigned int)a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
      (_DWORD)a2,
      (char)a3);
  Library = LoadLibraryExW((LPCWSTR)a2, 0, v3);
  *(_QWORD *)this = Library;
  if ( Library )
    return 0;
  LastFailure = HrGetLastFailure();
  v9 = LastFailure;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v8, (_DWORD)a2, v3, LastFailure);
  return v9;
}

```

## disassembly

```asm
0x14000ec7c  push    rbx
0x14000ec7e  push    rbp
0x14000ec7f  push    rsi
0x14000ec80  push    rdi
0x14000ec81  sub     rsp, 38h
0x14000ec85  mov     edi, r8d
0x14000ec88  mov     rsi, rdx
0x14000ec8b  mov     rbx, rcx
0x14000ec8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec95  lea     rbp, WPP_GLOBAL_Control
0x14000ec9c  cmp     rcx, rbp
0x14000ec9f  jz      short loc_14000ECC4
0x14000eca1  test    byte ptr [rcx+1Ch], 10h
0x14000eca5  jz      short loc_14000ECC4
0x14000eca7  mov     rcx, [rcx+10h]
0x14000ecab  mov     edx, 1Bh
0x14000ecb0  mov     [rsp+58h+var_38], r8d
0x14000ecb5  mov     r9, rsi
0x14000ecb8  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000ecbf  call    WPP_SF_Sd
0x14000ecc4  mov     r8d, edi; dwFlags
0x14000ecc7  xor     edx, edx; hFile
0x14000ecc9  mov     rcx, rsi; lpLibFileName
0x14000eccc  call    cs:__imp_LoadLibraryExW
0x14000ecd2  mov     [rbx], rax
0x14000ecd5  test    rax, rax
0x14000ecd8  jnz     short loc_14000ED10
0x14000ecda  call    HrGetLastFailure
0x14000ecdf  mov     ebx, eax
0x14000ece1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ece8  cmp     rcx, rbp
0x14000eceb  jz      short loc_14000ED0C
0x14000eced  test    byte ptr [rcx+1Ch], 1
0x14000ecf1  jz      short loc_14000ED0C
0x14000ecf3  mov     rcx, [rcx+10h]
0x14000ecf7  mov     edx, 1Ch
0x14000ecfc  mov     [rsp+58h+var_30], eax
0x14000ed00  mov     r9, rsi
0x14000ed03  mov     [rsp+58h+var_38], edi
0x14000ed07  call    WPP_SF_SDd
0x14000ed0c  mov     eax, ebx
0x14000ed0e  jmp     short loc_14000ED12
0x14000ed10  xor     eax, eax
0x14000ed12  add     rsp, 38h
0x14000ed16  pop     rdi
0x14000ed17  pop     rsi
0x14000ed18  pop     rbp
0x14000ed19  pop     rbx
0x14000ed1a  retn
```

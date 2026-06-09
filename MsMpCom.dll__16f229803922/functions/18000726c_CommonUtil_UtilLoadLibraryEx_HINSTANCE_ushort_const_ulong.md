# CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,ushort const *,ulong)

- ea: `0x18000726c`
- end: `0x1800072fc`
- name: `?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBGK@Z`
- size: `144`
- prototype: `int(CommonUtil *__hidden this, HINSTANCE *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007304`

## callees

- `0x18000726c`
- `0x1800076b8`
- `0x180007740`
- `0x1800090e4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800072af`
- `KERNEL32!LoadLibraryExW` at `0x1800072af`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadLibraryEx(CommonUtil *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  __int64 v6; // rcx
  int v7; // edx
  unsigned int LastFailure; // ebx
  int v9; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2);
  Library = LoadLibraryExW((LPCWSTR)a2, 0, 8u);
  *(_QWORD *)this = Library;
  if ( Library )
    return 0;
  LastFailure = HrGetLastFailure(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v9, (_DWORD)a2);
  return LastFailure;
}

```

## disassembly

```asm
0x18000726c  mov     [rsp+arg_0], rbx
0x180007271  mov     [rsp+arg_8], rsi
0x180007276  push    rdi
0x180007277  sub     rsp, 30h
0x18000727b  mov     rdi, rdx
0x18000727e  mov     rbx, rcx
0x180007281  mov     rcx, cs:WPP_GLOBAL_Control
0x180007288  lea     rsi, WPP_GLOBAL_Control
0x18000728f  cmp     rcx, rsi
0x180007292  jz      short loc_1800072A6
0x180007294  test    byte ptr [rcx+1Ch], 10h
0x180007298  jz      short loc_1800072A6
0x18000729a  mov     rcx, [rcx+10h]
0x18000729e  mov     r9, rdx
0x1800072a1  call    WPP_SF_SD
0x1800072a6  xor     edx, edx; hFile
0x1800072a8  mov     rcx, rdi; lpLibFileName
0x1800072ab  lea     r8d, [rdx+8]; dwFlags
0x1800072af  call    cs:__imp_LoadLibraryExW
0x1800072b5  mov     [rbx], rax
0x1800072b8  test    rax, rax
0x1800072bb  jnz     short loc_1800072EA
0x1800072bd  call    HrGetLastFailure
0x1800072c2  mov     ebx, eax
0x1800072c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072cb  cmp     rcx, rsi
0x1800072ce  jz      short loc_1800072E6
0x1800072d0  test    byte ptr [rcx+1Ch], 1
0x1800072d4  jz      short loc_1800072E6
0x1800072d6  mov     rcx, [rcx+10h]
0x1800072da  mov     r9, rdi
0x1800072dd  mov     [rsp+38h+var_10], eax
0x1800072e1  call    WPP_SF_SDd
0x1800072e6  mov     eax, ebx
0x1800072e8  jmp     short loc_1800072EC
0x1800072ea  xor     eax, eax
0x1800072ec  mov     rbx, [rsp+38h+arg_0]
0x1800072f1  mov     rsi, [rsp+38h+arg_8]
0x1800072f6  add     rsp, 30h
0x1800072fa  pop     rdi
0x1800072fb  retn
```

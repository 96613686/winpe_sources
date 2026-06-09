# CommonUtil::HrExpandEnvironmentStrings(ushort const *,unsigned __int64 *,ushort *)

- ea: `0x14000e6e4`
- end: `0x14000e778`
- name: `?HrExpandEnvironmentStrings@CommonUtil@@YAJPEBGPEA_KPEAG@Z`
- size: `148`
- prototype: `__int64 __fastcall(const WCHAR *this, unsigned __int16 *, WCHAR *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ea5c`

## callees

- `0x1400071c0`
- `0x14000e6e4`
- `0x140011234`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000e6fe`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000e6fe`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrExpandEnvironmentStrings(
        const WCHAR *this,
        unsigned __int16 *a2,
        WCHAR *a3,
        unsigned __int16 *a4)
{
  DWORD v4; // ebx
  int v7; // ebp
  DWORD v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int LastFailure; // ebx

  v4 = *(_DWORD *)a2;
  v7 = (int)this;
  v8 = ExpandEnvironmentStringsW(this, a3, *(_DWORD *)a2);
  if ( v8 )
  {
    if ( v8 > v4 )
    {
      if ( v4 )
        *a3 = 0;
    }
    else if ( a3[v8 - 1] )
    {
      return 2147549183LL;
    }
    *(_QWORD *)a2 = v8;
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure(v9, 0, v10, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
        v7,
        LastFailure);
    return LastFailure;
  }
}

```

## disassembly

```asm
0x14000e6e4  push    rbx
0x14000e6e6  push    rbp
0x14000e6e7  push    rsi
0x14000e6e8  push    rdi
0x14000e6e9  sub     rsp, 38h
0x14000e6ed  mov     ebx, [rdx]
0x14000e6ef  mov     rdi, r8
0x14000e6f2  mov     rsi, rdx
0x14000e6f5  mov     r8d, ebx; nSize
0x14000e6f8  mov     rdx, rdi; lpDst
0x14000e6fb  mov     rbp, rcx
0x14000e6fe  call    cs:__imp_ExpandEnvironmentStringsW
0x14000e704  xor     edx, edx
0x14000e706  mov     r9d, eax
0x14000e709  test    eax, eax
0x14000e70b  jnz     short loc_14000E74D
0x14000e70d  call    HrGetLastFailure
0x14000e712  mov     ebx, eax
0x14000e714  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e71b  lea     rax, WPP_GLOBAL_Control
0x14000e722  cmp     rcx, rax
0x14000e725  jz      short loc_14000E749
0x14000e727  test    byte ptr [rcx+1Ch], 1
0x14000e72b  jz      short loc_14000E749
0x14000e72d  mov     rcx, [rcx+10h]
0x14000e731  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000e738  mov     edx, 3Ah ; ':'
0x14000e73d  mov     [rsp+58h+var_38], ebx
0x14000e741  mov     r9, rbp
0x14000e744  call    WPP_SF_Sd
0x14000e749  mov     eax, ebx
0x14000e74b  jmp     short loc_14000E76F
0x14000e74d  cmp     r9d, ebx
0x14000e750  ja      short loc_14000E763
0x14000e752  lea     eax, [r9-1]
0x14000e756  cmp     [rdi+rax*2], dx
0x14000e75a  jz      short loc_14000E76A
0x14000e75c  mov     eax, 8000FFFFh
0x14000e761  jmp     short loc_14000E76F
0x14000e763  test    ebx, ebx
0x14000e765  jz      short loc_14000E76A
0x14000e767  mov     [rdi], dx
0x14000e76a  mov     [rsi], r9
0x14000e76d  xor     eax, eax
0x14000e76f  add     rsp, 38h
0x14000e773  pop     rdi
0x14000e774  pop     rsi
0x14000e775  pop     rbp
0x14000e776  pop     rbx
0x14000e777  retn
```

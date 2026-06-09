# CommonUtil::UtilCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x14000e8b4`
- end: `0x14000e988`
- name: `?UtilCreateDirectory@CommonUtil@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `212`
- prototype: `int __fastcall(WCHAR *this, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002f00`

## callees

- `0x140005394`
- `0x1400071c0`
- `0x14000e780`
- `0x14000e8b4`
- `0x140011234`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x14000e8c8`
- `KERNEL32!CreateDirectoryW` at `0x14000e8c8`

## pseudocode

```c
int __fastcall CommonUtil::UtilCreateDirectory(
        WCHAR *this,
        const unsigned __int16 *a2,
        struct _SECURITY_ATTRIBUTES *a3)
{
  int result; // eax
  int LastFailure; // eax
  const unsigned __int16 *v6; // r8
  int v7; // ebx
  const unsigned __int16 *v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = a2;
  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastFailure = HrGetLastFailure();
  v7 = LastFailure;
  if ( LastFailure == -2147024713 )
  {
    LODWORD(v8) = 0;
    result = CommonUtil::HrGetFileAttributes((CommonUtil *)&v8, (unsigned int *)this, v6);
    if ( result >= 0 )
    {
      if ( ((unsigned __int8)v8 & 0x10) != 0 )
      {
        return 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, this);
        return -2147024713;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
        (_DWORD)this,
        LastFailure);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14000e8b4  mov     [rsp+arg_0], rbx
0x14000e8b9  mov     [rsp+arg_8], rdx
0x14000e8be  push    rdi
0x14000e8bf  sub     rsp, 30h
0x14000e8c3  xor     edx, edx; lpSecurityAttributes
0x14000e8c5  mov     rdi, rcx
0x14000e8c8  call    cs:__imp_CreateDirectoryW
0x14000e8ce  test    eax, eax
0x14000e8d0  jz      short loc_14000E8D9
0x14000e8d2  xor     eax, eax
0x14000e8d4  jmp     loc_14000E97D
0x14000e8d9  call    HrGetLastFailure
0x14000e8de  mov     ebx, eax
0x14000e8e0  cmp     eax, 800700B7h
0x14000e8e5  jz      short loc_14000E920
0x14000e8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8ee  lea     rdx, WPP_GLOBAL_Control
0x14000e8f5  cmp     rcx, rdx
0x14000e8f8  jz      short loc_14000E91C
0x14000e8fa  test    byte ptr [rcx+1Ch], 1
0x14000e8fe  jz      short loc_14000E91C
0x14000e900  mov     rcx, [rcx+10h]
0x14000e904  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000e90b  mov     edx, 2Fh ; '/'
0x14000e910  mov     [rsp+38h+var_18], eax
0x14000e914  mov     r9, rdi
0x14000e917  call    WPP_SF_Sd
0x14000e91c  mov     eax, ebx
0x14000e91e  jmp     short loc_14000E97D
0x14000e920  mov     rdx, rdi; unsigned int *
0x14000e923  mov     dword ptr [rsp+38h+arg_8], 0
0x14000e92b  lea     rcx, [rsp+38h+arg_8]; this
0x14000e930  call    ?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z; CommonUtil::HrGetFileAttributes(ulong *,ushort const *)
0x14000e935  test    eax, eax
0x14000e937  js      short loc_14000E97D
0x14000e939  test    byte ptr [rsp+38h+arg_8], 10h
0x14000e93e  jnz     short loc_14000E978
0x14000e940  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e947  lea     rdx, WPP_GLOBAL_Control
0x14000e94e  cmp     rcx, rdx
0x14000e951  jz      short loc_14000E971
0x14000e953  test    byte ptr [rcx+1Ch], 1
0x14000e957  jz      short loc_14000E971
0x14000e959  mov     rcx, [rcx+10h]
0x14000e95d  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000e964  mov     edx, 39h ; '9'
0x14000e969  mov     r9, rdi
0x14000e96c  call    WPP_SF_S
0x14000e971  mov     eax, 800700B7h
0x14000e976  jmp     short loc_14000E97D
0x14000e978  mov     eax, 1
0x14000e97d  mov     rbx, [rsp+38h+arg_0]
0x14000e982  add     rsp, 30h
0x14000e986  pop     rdi
0x14000e987  retn
```

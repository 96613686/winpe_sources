# CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)

- ea: `0x14000efc4`
- end: `0x14000f07d`
- name: `?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z`
- size: `185`
- prototype: `__int64 __fastcall(CommonUtil *this, __int64 (**)(void), const CHAR *, const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004588`
- `0x14000ef14`

## callees

- `0x14000dd74`
- `0x14000efc4`
- `0x14000f114`
- `0x140011234`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000efdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000efdd`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRawGetProcAddress(
        CommonUtil *this,
        __int64 (**a2)(void),
        const CHAR *a3,
        const char *a4)
{
  FARPROC ProcAddress; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edx
  int LastFailure; // ebx
  int v13; // r8d
  __int64 result; // rax

  ProcAddress = GetProcAddress((HMODULE)a2, a3);
  *(_QWORD *)this = ProcAddress;
  if ( ProcAddress )
    return 0;
  LastFailure = HrGetLastFailure(v8, v7, v9, v10);
  result = 2147942527LL;
  if ( LastFailure == -2147024769 )
    return result;
  if ( (unsigned __int64)a3 >= 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v13, (_DWORD)a3, LastFailure);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
      (unsigned int)a3,
      LastFailure);
  }
  if ( LastFailure >= 0 )
    return 0;
  else
    return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x14000efc4  mov     [rsp+arg_0], rbx
0x14000efc9  push    rdi
0x14000efca  sub     rsp, 30h
0x14000efce  mov     rax, rdx
0x14000efd1  mov     rbx, rcx
0x14000efd4  mov     rcx, rax; hModule
0x14000efd7  mov     rdx, r8; lpProcName
0x14000efda  mov     rdi, r8
0x14000efdd  call    cs:__imp_GetProcAddress
0x14000efe3  mov     [rbx], rax
0x14000efe6  test    rax, rax
0x14000efe9  jnz     loc_14000F070
0x14000efef  call    HrGetLastFailure
0x14000eff4  mov     ebx, eax
0x14000eff6  mov     eax, 8007007Fh
0x14000effb  cmp     ebx, eax
0x14000effd  jz      short loc_14000F072
0x14000efff  cmp     rdi, 10000h
0x14000f006  jnb     short loc_14000F03F
0x14000f008  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f00f  lea     rax, WPP_GLOBAL_Control
0x14000f016  cmp     rcx, rax
0x14000f019  jz      short loc_14000F068
0x14000f01b  test    byte ptr [rcx+1Ch], 2
0x14000f01f  jz      short loc_14000F068
0x14000f021  mov     rcx, [rcx+10h]
0x14000f025  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000f02c  mov     r9d, edi
0x14000f02f  mov     [rsp+38h+var_18], ebx
0x14000f033  mov     edx, 1Dh
0x14000f038  call    WPP_SF_Dd
0x14000f03d  jmp     short loc_14000F068
0x14000f03f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f046  lea     rax, WPP_GLOBAL_Control
0x14000f04d  cmp     rcx, rax
0x14000f050  jz      short loc_14000F068
0x14000f052  test    byte ptr [rcx+1Ch], 2
0x14000f056  jz      short loc_14000F068
0x14000f058  mov     rcx, [rcx+10h]
0x14000f05c  mov     r9, rdi
0x14000f05f  mov     [rsp+38h+var_18], ebx
0x14000f063  call    WPP_SF_sd
0x14000f068  test    ebx, ebx
0x14000f06a  jns     short loc_14000F070
0x14000f06c  mov     eax, ebx
0x14000f06e  jmp     short loc_14000F072
0x14000f070  xor     eax, eax
0x14000f072  mov     rbx, [rsp+38h+arg_0]
0x14000f077  add     rsp, 30h
0x14000f07b  pop     rdi
0x14000f07c  retn
```

# CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)

- ea: `0x1800075ac`
- end: `0x180007665`
- name: `?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z`
- size: `185`
- prototype: `int(CommonUtil *__hidden this, __int64 (**)(void), HINSTANCE, const char *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800074fc`

## callees

- `0x1800075ac`
- `0x18000766c`
- `0x1800077d8`
- `0x1800090e4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800075c5`
- `KERNEL32!GetProcAddress` at `0x1800075c5`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRawGetProcAddress(
        CommonUtil *this,
        __int64 (**a2)(void),
        const CHAR *a3,
        const char *a4)
{
  FARPROC ProcAddress; // rax
  __int64 v7; // rcx
  int v8; // edx
  int LastFailure; // ebx
  int v10; // r8d
  __int64 result; // rax

  ProcAddress = GetProcAddress((HMODULE)a2, a3);
  *(_QWORD *)this = ProcAddress;
  if ( ProcAddress )
    return 0;
  LastFailure = HrGetLastFailure(v7);
  result = 2147942527LL;
  if ( LastFailure == -2147024769 )
    return result;
  if ( (unsigned __int64)a3 >= 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v10, (_DWORD)a3, LastFailure);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids,
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
0x1800075ac  mov     [rsp+arg_0], rbx
0x1800075b1  push    rdi
0x1800075b2  sub     rsp, 30h
0x1800075b6  mov     rax, rdx
0x1800075b9  mov     rbx, rcx
0x1800075bc  mov     rcx, rax; hModule
0x1800075bf  mov     rdx, r8; lpProcName
0x1800075c2  mov     rdi, r8
0x1800075c5  call    cs:__imp_GetProcAddress
0x1800075cb  mov     [rbx], rax
0x1800075ce  test    rax, rax
0x1800075d1  jnz     loc_180007658
0x1800075d7  call    HrGetLastFailure
0x1800075dc  mov     ebx, eax
0x1800075de  mov     eax, 8007007Fh
0x1800075e3  cmp     ebx, eax
0x1800075e5  jz      short loc_18000765A
0x1800075e7  cmp     rdi, 10000h
0x1800075ee  jnb     short loc_180007627
0x1800075f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075f7  lea     rax, WPP_GLOBAL_Control
0x1800075fe  cmp     rcx, rax
0x180007601  jz      short loc_180007650
0x180007603  test    byte ptr [rcx+1Ch], 2
0x180007607  jz      short loc_180007650
0x180007609  mov     rcx, [rcx+10h]
0x18000760d  lea     r8, WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids
0x180007614  mov     r9d, edi
0x180007617  mov     [rsp+38h+var_18], ebx
0x18000761b  mov     edx, 1Dh
0x180007620  call    WPP_SF_Dd
0x180007625  jmp     short loc_180007650
0x180007627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000762e  lea     rax, WPP_GLOBAL_Control
0x180007635  cmp     rcx, rax
0x180007638  jz      short loc_180007650
0x18000763a  test    byte ptr [rcx+1Ch], 2
0x18000763e  jz      short loc_180007650
0x180007640  mov     rcx, [rcx+10h]
0x180007644  mov     r9, rdi
0x180007647  mov     [rsp+38h+var_18], ebx
0x18000764b  call    WPP_SF_sd
0x180007650  test    ebx, ebx
0x180007652  jns     short loc_180007658
0x180007654  mov     eax, ebx
0x180007656  jmp     short loc_18000765A
0x180007658  xor     eax, eax
0x18000765a  mov     rbx, [rsp+38h+arg_0]
0x18000765f  add     rsp, 30h
0x180007663  pop     rdi
0x180007664  retn
```

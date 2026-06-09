# CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)

- ea: `0x1800074fc`
- end: `0x1800075a6`
- name: `?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z`
- size: `170`
- prototype: `int(CommonUtil *__hidden this, __int64 (**)(void), const unsigned __int16 *, const char *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008a6c`

## callees

- `0x180006898`
- `0x1800074fc`
- `0x1800075ac`
- `0x1800090e4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007517`
- `KERNEL32!GetModuleHandleW` at `0x180007517`

## pseudocode

```c
int __fastcall CommonUtil::UtilRawGetLoadedProcAddress(
        CommonUtil *this,
        const WCHAR *a2,
        unsigned __int16 *a3,
        const char *a4)
{
  int v6; // edi
  __int64 (**ModuleHandleW)(void); // rax
  __int64 v8; // rcx
  const char *v9; // r9
  int LastFailure; // ebx
  int result; // eax
  bool v12; // [rsp+20h] [rbp-28h]
  _QWORD v13[3]; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)a2;
  ModuleHandleW = (__int64 (**)(void))GetModuleHandleW(a2);
  if ( ModuleHandleW )
  {
    v13[0] = 0;
    result = CommonUtil::UtilRawGetProcAddress((CommonUtil *)v13, ModuleHandleW, (HINSTANCE)a3, v9, v12);
    if ( result == -2147024769 )
    {
      return -2147024769;
    }
    else if ( result >= 0 )
    {
      *(_QWORD *)this = v13[0];
      return 0;
    }
  }
  else
  {
    LastFailure = HrGetLastFailure(v8);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids,
        v6,
        LastFailure);
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x1800074fc  mov     [rsp+arg_0], rbx
0x180007501  mov     [rsp+arg_8], rsi
0x180007506  push    rdi
0x180007507  sub     rsp, 40h
0x18000750b  mov     rbx, rcx
0x18000750e  mov     rsi, r8
0x180007511  mov     rcx, rdx; lpModuleName
0x180007514  mov     rdi, rdx
0x180007517  call    cs:__imp_GetModuleHandleW
0x18000751d  test    rax, rax
0x180007520  jnz     short loc_180007562
0x180007522  call    HrGetLastFailure
0x180007527  mov     ebx, eax
0x180007529  mov     rcx, cs:WPP_GLOBAL_Control
0x180007530  lea     rax, WPP_GLOBAL_Control
0x180007537  cmp     rcx, rax
0x18000753a  jz      short loc_18000755E
0x18000753c  test    byte ptr [rcx+1Ch], 1
0x180007540  jz      short loc_18000755E
0x180007542  mov     rcx, [rcx+10h]
0x180007546  lea     r8, WPP_e2b92b5a14063cae8af40d4f75517e75_Traceguids
0x18000754d  mov     edx, 1Fh
0x180007552  mov     dword ptr [rsp+48h+var_28], ebx
0x180007556  mov     r9, rdi
0x180007559  call    WPP_SF_Sd
0x18000755e  mov     eax, ebx
0x180007560  jmp     short loc_180007596
0x180007562  mov     r8, rsi; HINSTANCE
0x180007565  mov     [rsp+48h+var_18], 0
0x18000756e  mov     rdx, rax; __int64 (**)(void)
0x180007571  lea     rcx, [rsp+48h+var_18]; this
0x180007576  call    ?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z; CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)
0x18000757b  mov     ecx, 8007007Fh
0x180007580  cmp     eax, ecx
0x180007582  jnz     short loc_180007588
0x180007584  mov     eax, ecx
0x180007586  jmp     short loc_180007596
0x180007588  test    eax, eax
0x18000758a  js      short loc_180007596
0x18000758c  mov     rax, [rsp+48h+var_18]
0x180007591  mov     [rbx], rax
0x180007594  xor     eax, eax
0x180007596  mov     rbx, [rsp+48h+arg_0]
0x18000759b  mov     rsi, [rsp+48h+arg_8]
0x1800075a0  add     rsp, 40h
0x1800075a4  pop     rdi
0x1800075a5  retn
```

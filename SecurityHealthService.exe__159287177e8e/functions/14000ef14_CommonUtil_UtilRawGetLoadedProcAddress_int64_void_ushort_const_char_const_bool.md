# CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),ushort const *,char const *,bool)

- ea: `0x14000ef14`
- end: `0x14000efbe`
- name: `?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBGPEBD_N@Z`
- size: `170`
- prototype: `int __fastcall(CommonUtil *this, const WCHAR *, unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400102f0`

## callees

- `0x1400071c0`
- `0x14000ef14`
- `0x14000efc4`
- `0x140011234`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000ef2f`
- `KERNEL32!GetModuleHandleW` at `0x14000ef2f`

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
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  const char *v11; // r9
  int LastFailure; // ebx
  int result; // eax
  bool v14; // [rsp+20h] [rbp-28h]
  _QWORD v15[3]; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)a2;
  ModuleHandleW = (__int64 (**)(void))GetModuleHandleW(a2);
  if ( ModuleHandleW )
  {
    v15[0] = 0;
    result = CommonUtil::UtilRawGetProcAddress((CommonUtil *)v15, ModuleHandleW, (HINSTANCE)a3, v11, v14);
    if ( result == -2147024769 )
    {
      return -2147024769;
    }
    else if ( result >= 0 )
    {
      *(_QWORD *)this = v15[0];
      return 0;
    }
  }
  else
  {
    LastFailure = HrGetLastFailure(v9, v8, v10, v11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids,
        v6,
        LastFailure);
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x14000ef14  mov     [rsp+arg_0], rbx
0x14000ef19  mov     [rsp+arg_8], rsi
0x14000ef1e  push    rdi
0x14000ef1f  sub     rsp, 40h
0x14000ef23  mov     rbx, rcx
0x14000ef26  mov     rsi, r8
0x14000ef29  mov     rcx, rdx; lpModuleName
0x14000ef2c  mov     rdi, rdx
0x14000ef2f  call    cs:__imp_GetModuleHandleW
0x14000ef35  test    rax, rax
0x14000ef38  jnz     short loc_14000EF7A
0x14000ef3a  call    HrGetLastFailure
0x14000ef3f  mov     ebx, eax
0x14000ef41  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef48  lea     rax, WPP_GLOBAL_Control
0x14000ef4f  cmp     rcx, rax
0x14000ef52  jz      short loc_14000EF76
0x14000ef54  test    byte ptr [rcx+1Ch], 1
0x14000ef58  jz      short loc_14000EF76
0x14000ef5a  mov     rcx, [rcx+10h]
0x14000ef5e  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000ef65  mov     edx, 1Fh
0x14000ef6a  mov     dword ptr [rsp+48h+var_28], ebx
0x14000ef6e  mov     r9, rdi
0x14000ef71  call    WPP_SF_Sd
0x14000ef76  mov     eax, ebx
0x14000ef78  jmp     short loc_14000EFAE
0x14000ef7a  mov     r8, rsi; HINSTANCE
0x14000ef7d  mov     [rsp+48h+var_18], 0
0x14000ef86  mov     rdx, rax; __int64 (**)(void)
0x14000ef89  lea     rcx, [rsp+48h+var_18]; this
0x14000ef8e  call    ?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z; CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)
0x14000ef93  mov     ecx, 8007007Fh
0x14000ef98  cmp     eax, ecx
0x14000ef9a  jnz     short loc_14000EFA0
0x14000ef9c  mov     eax, ecx
0x14000ef9e  jmp     short loc_14000EFAE
0x14000efa0  test    eax, eax
0x14000efa2  js      short loc_14000EFAE
0x14000efa4  mov     rax, [rsp+48h+var_18]
0x14000efa9  mov     [rbx], rax
0x14000efac  xor     eax, eax
0x14000efae  mov     rbx, [rsp+48h+arg_0]
0x14000efb3  mov     rsi, [rsp+48h+arg_8]
0x14000efb8  add     rsp, 40h
0x14000efbc  pop     rdi
0x14000efbd  retn
```

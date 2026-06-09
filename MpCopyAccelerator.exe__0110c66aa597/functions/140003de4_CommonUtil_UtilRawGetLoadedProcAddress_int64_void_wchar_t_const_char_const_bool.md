# CommonUtil::UtilRawGetLoadedProcAddress(__int64 (**)(void),wchar_t const *,char const *,bool)

- ea: `0x140003de4`
- end: `0x140003eaa`
- name: `?UtilRawGetLoadedProcAddress@CommonUtil@@YAJPEAP6A_JXZPEB_WPEBD_N@Z`
- size: `198`
- prototype: `int(CommonUtil *__hidden this, __int64 (**)(void), const wchar_t *, const char *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400038e0`
- `0x1400039e4`
- `0x14000530c`

## callees

- `0x140003de4`
- `0x140004670`
- `0x14000493c`
- `0x140005c20`
- `0x140020220`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140003e0b`
- `KERNEL32!GetModuleHandleW` at `0x140003e0b`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRawGetLoadedProcAddress(
        CommonUtil *this,
        const WCHAR *a2,
        wchar_t *a3,
        const char *a4)
{
  char v5; // bp
  int v7; // edi
  __int64 (**ModuleHandleW)(void); // rax
  const char *v9; // r9
  unsigned int LastFailure; // ebx
  __int64 result; // rax
  int ProcAddress; // ecx
  bool v13; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+30h] [rbp-38h] BYREF

  v5 = (char)a4;
  v7 = (int)a2;
  ModuleHandleW = (__int64 (**)(void))GetModuleHandleW(a2);
  if ( ModuleHandleW )
  {
    LOBYTE(v9) = v5;
    v14 = 0;
    ProcAddress = CommonUtil::UtilRawGetProcAddress((CommonUtil *)&v14, ModuleHandleW, (HINSTANCE)a3, v9, v13);
    result = 2147942527LL;
    if ( ProcAddress != -2147024769 )
    {
      if ( ProcAddress >= 0 )
      {
        *(_QWORD *)this = v14;
        return 0;
      }
      else
      {
        return (unsigned int)ProcAddress;
      }
    }
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids,
        v7,
        LastFailure);
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x140003de4  push    rbx
0x140003de6  push    rbp
0x140003de7  push    rsi
0x140003de8  push    rdi
0x140003de9  sub     rsp, 48h
0x140003ded  mov     rax, cs:__security_cookie
0x140003df4  xor     rax, rsp
0x140003df7  mov     [rsp+68h+var_30], rax
0x140003dfc  mov     rbx, rcx
0x140003dff  mov     bpl, r9b
0x140003e02  mov     rcx, rdx; lpModuleName
0x140003e05  mov     rsi, r8
0x140003e08  mov     rdi, rdx
0x140003e0b  call    cs:__imp_GetModuleHandleW
0x140003e11  test    rax, rax
0x140003e14  jnz     short loc_140003E56
0x140003e16  call    HrGetLastFailure
0x140003e1b  mov     ebx, eax
0x140003e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e24  lea     rax, WPP_GLOBAL_Control
0x140003e2b  cmp     rcx, rax
0x140003e2e  jz      short loc_140003E52
0x140003e30  test    byte ptr [rcx+1Ch], 1
0x140003e34  jz      short loc_140003E52
0x140003e36  mov     rcx, [rcx+10h]
0x140003e3a  lea     r8, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids
0x140003e41  mov     edx, 12h
0x140003e46  mov     dword ptr [rsp+68h+var_48], ebx
0x140003e4a  mov     r9, rdi
0x140003e4d  call    WPP_SF_Sd
0x140003e52  mov     eax, ebx
0x140003e54  jmp     short loc_140003E94
0x140003e56  mov     r9b, bpl; char *
0x140003e59  mov     [rsp+68h+var_38], 0
0x140003e62  mov     r8, rsi; HINSTANCE
0x140003e65  lea     rcx, [rsp+68h+var_38]; this
0x140003e6a  mov     rdx, rax; __int64 (**)(void)
0x140003e6d  call    ?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z; CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)
0x140003e72  mov     ecx, eax
0x140003e74  mov     eax, 8007007Fh
0x140003e79  cmp     ecx, eax
0x140003e7b  jz      short loc_140003E94
0x140003e7d  mov     eax, ecx
0x140003e7f  shr     eax, 1Fh
0x140003e82  test    al, al
0x140003e84  jz      short loc_140003E8A
0x140003e86  mov     eax, ecx
0x140003e88  jmp     short loc_140003E94
0x140003e8a  mov     rax, [rsp+68h+var_38]
0x140003e8f  mov     [rbx], rax
0x140003e92  xor     eax, eax
0x140003e94  mov     rcx, [rsp+68h+var_30]
0x140003e99  xor     rcx, rsp; StackCookie
0x140003e9c  call    __security_check_cookie
0x140003ea1  add     rsp, 48h
0x140003ea5  pop     rdi
0x140003ea6  pop     rsi
0x140003ea7  pop     rbp
0x140003ea8  pop     rbx
0x140003ea9  retn
```

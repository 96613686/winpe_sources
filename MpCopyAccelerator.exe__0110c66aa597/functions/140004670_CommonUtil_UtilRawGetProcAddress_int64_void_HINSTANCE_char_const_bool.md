# CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)

- ea: `0x140004670`
- end: `0x14000473e`
- name: `?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z`
- size: `206`
- prototype: `int(CommonUtil *__hidden this, __int64 (**)(void), HINSTANCE, const char *, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002cd0`
- `0x140003de4`

## callees

- `0x140004670`
- `0x1400048bc`
- `0x14000493c`
- `0x1400203f0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004689`
- `KERNEL32!GetProcAddress` at `0x140004689`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRawGetProcAddress(
        CommonUtil *this,
        __int64 (**a2)(void),
        const CHAR *a3,
        const char *a4)
{
  FARPROC ProcAddress; // rax
  int LastFailure; // ebx
  __int64 result; // rax

  ProcAddress = GetProcAddress((HMODULE)a2, a3);
  *(_QWORD *)this = ProcAddress;
  if ( ProcAddress )
    return 0;
  LastFailure = HrGetLastFailure();
  result = 2147942527LL;
  if ( LastFailure == -2147024769 )
    return result;
  if ( (unsigned __int64)a3 >= 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastFailure);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_bed851edf8673fd54b380593fb017a56_Traceguids,
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
0x140004670  mov     [rsp+arg_0], rbx
0x140004675  push    rdi
0x140004676  sub     rsp, 30h
0x14000467a  mov     rax, rdx
0x14000467d  mov     rbx, rcx
0x140004680  mov     rcx, rax; hModule
0x140004683  mov     rdx, r8; lpProcName
0x140004686  mov     rdi, r8
0x140004689  call    cs:__imp_GetProcAddress
0x14000468f  mov     [rbx], rax
0x140004692  test    rax, rax
0x140004695  jnz     loc_140004731
0x14000469b  call    HrGetLastFailure
0x1400046a0  mov     ebx, eax
0x1400046a2  mov     eax, 8007007Fh
0x1400046a7  cmp     ebx, eax
0x1400046a9  jz      loc_140004733
0x1400046af  cmp     rdi, 10000h
0x1400046b6  jnb     short loc_1400046EF
0x1400046b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046bf  lea     rax, WPP_GLOBAL_Control
0x1400046c6  cmp     rcx, rax
0x1400046c9  jz      short loc_140004724
0x1400046cb  test    byte ptr [rcx+1Ch], 2
0x1400046cf  jz      short loc_140004724
0x1400046d1  mov     rcx, [rcx+10h]
0x1400046d5  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x1400046dc  mov     edx, 20h ; ' '
0x1400046e1  mov     dword ptr [rsp+38h+var_18], ebx
0x1400046e5  mov     r9d, edi
0x1400046e8  call    WPP_SF_Dd
0x1400046ed  jmp     short loc_140004724
0x1400046ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046f6  lea     rax, WPP_GLOBAL_Control
0x1400046fd  cmp     rcx, rax
0x140004700  jz      short loc_140004724
0x140004702  test    byte ptr [rcx+1Ch], 2
0x140004706  jz      short loc_140004724
0x140004708  mov     rcx, [rcx+10h]; LoggerHandle
0x14000470c  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004713  mov     edx, 21h ; '!'
0x140004718  mov     dword ptr [rsp+38h+var_18], ebx; char
0x14000471c  mov     r9, rdi
0x14000471f  call    WPP_SF_sd
0x140004724  mov     eax, ebx
0x140004726  shr     eax, 1Fh
0x140004729  test    al, al
0x14000472b  jz      short loc_140004731
0x14000472d  mov     eax, ebx
0x14000472f  jmp     short loc_140004733
0x140004731  xor     eax, eax
0x140004733  mov     rbx, [rsp+38h+arg_0]
0x140004738  add     rsp, 30h
0x14000473c  pop     rdi
0x14000473d  retn
```

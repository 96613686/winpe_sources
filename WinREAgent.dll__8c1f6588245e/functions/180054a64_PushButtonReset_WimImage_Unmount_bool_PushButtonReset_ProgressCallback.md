# PushButtonReset::WimImage::Unmount(bool,PushButtonReset::ProgressCallback *)

- ea: `0x180054a64`
- end: `0x180054b1e`
- name: `?Unmount@WimImage@PushButtonReset@@QEAAJ_NPEAUProgressCallback@2@@Z`
- size: `186`
- prototype: `__int64 __fastcall(PushButtonReset::WimImage *__hidden this, bool, struct PushButtonReset::ProgressCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180053dc8`

## callees

- `0x180037344`
- `0x180053d58`
- `0x180054a64`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180054aa3`
- `KERNEL32!GetLastError` at `0x180054aef`
- `KERNEL32!GetLastError` at `0x180054aa3`
- `KERNEL32!GetLastError` at `0x180054aef`
- `WIMGAPI!WIMUnmountImageHandle` at `0x180054a99`
- `WIMGAPI!WIMUnmountImageHandle` at `0x180054a99`

## string_xrefs

- `0x180054adc`: `PushButtonReset::WimImage::Unmount`
- `0x180054ab5`: `unmount`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushButtonReset::WimImage::Unmount(
        PushButtonReset::WimImage *this,
        __int64 a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  __int64 v4; // rax
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // ebx
  _BYTE v9[8]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h]
  __int64 v11; // [rsp+50h] [rbp-18h]

  v9[0] = 0;
  v10 = 0;
  v11 = 0;
  v4 = (*(__int64 (__fastcall **)(char *, __int64, struct PushButtonReset::ProgressCallback *))(*((_QWORD *)this + 1)
                                                                                              + 32LL))(
         (char *)this + 8,
         a2,
         a3);
  if ( (unsigned int)WIMUnmountImageHandle(v4, 0) )
  {
    *((_BYTE *)this + 28) = 0;
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::WimImage::Unmount",
      "base\\reset\\util\\src\\wim.cpp",
      946,
      L"Failed to %s image",
      L"unmount");
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  CAutoWimCallback::~CAutoWimCallback((CAutoWimCallback *)v9);
  return v7;
}

```

## disassembly

```asm
0x180054a64  push    rbx
0x180054a66  sub     rsp, 60h
0x180054a6a  mov     rbx, rcx
0x180054a6d  mov     [rsp+68h+var_28], 0
0x180054a72  mov     [rsp+68h+var_20], 0
0x180054a7b  mov     [rsp+68h+var_18], 0
0x180054a84  add     rcx, 8
0x180054a88  mov     rax, [rcx]
0x180054a8b  mov     rax, [rax+20h]
0x180054a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a94  mov     rcx, rax
0x180054a97  xor     edx, edx
0x180054a99  call    cs:__imp_WIMUnmountImageHandle
0x180054a9f  test    eax, eax
0x180054aa1  jnz     short loc_180054B06
0x180054aa3  call    cs:__imp_GetLastError
0x180054aa9  test    eax, eax
0x180054aab  jle     short loc_180054AB5
0x180054aad  movzx   eax, ax
0x180054ab0  or      eax, 80070000h
0x180054ab5  lea     rcx, aUnmount; "unmount"
0x180054abc  mov     [rsp+68h+var_38], rcx
0x180054ac1  lea     rcx, aFailedToSImage; "Failed to %s image"
0x180054ac8  mov     [rsp+68h+var_40], rcx
0x180054acd  mov     [rsp+68h+var_48], 3B2h
0x180054ad5  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180054adc  lea     r8, aPushbuttonrese_42; "PushButtonReset::WimImage::Unmount"
0x180054ae3  mov     edx, eax
0x180054ae5  mov     ecx, 2
0x180054aea  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180054aef  call    cs:__imp_GetLastError
0x180054af5  mov     ebx, eax
0x180054af7  test    eax, eax
0x180054af9  jle     short loc_180054B0C
0x180054afb  movzx   ebx, ax
0x180054afe  or      ebx, 80070000h
0x180054b04  jmp     short loc_180054B0C
0x180054b06  mov     byte ptr [rbx+1Ch], 0
0x180054b0a  xor     ebx, ebx
0x180054b0c  lea     rcx, [rsp+68h+var_28]; this
0x180054b11  call    ??1CAutoWimCallback@@QEAA@XZ; CAutoWimCallback::~CAutoWimCallback(void)
0x180054b16  mov     eax, ebx
0x180054b18  add     rsp, 60h
0x180054b1c  pop     rbx
0x180054b1d  retn
```

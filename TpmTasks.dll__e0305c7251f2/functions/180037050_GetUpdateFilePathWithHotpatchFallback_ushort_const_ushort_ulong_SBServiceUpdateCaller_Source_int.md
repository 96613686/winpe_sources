# GetUpdateFilePathWithHotpatchFallback(ushort const *,ushort *,ulong,SBServiceUpdateCaller::Source,int *)

- ea: `0x180037050`
- end: `0x180037205`
- name: `?GetUpdateFilePathWithHotpatchFallback@@YAJPEBGPEAGKW4Source@SBServiceUpdateCaller@@PEAH@Z`
- size: `437`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180034634`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x180036318`
- `0x180036a98`
- `0x180037050`
- `0x18003c0b8`

## string_xrefs

- `0x1800370af`: `GetUpdateFilePathWithHotpatchFallback: Enter, fileName=%s`
- `0x1800370d9`: `GetUpdateFilePathWithHotpatchFallback: GetHotpatchUpdatePath failed with hr=0x%08x`
- `0x1800370f2`: `GetUpdateFilePathWithHotpatchFallback: Using hotpatch path: %s`
- `0x18003712a`: `GetUpdateFilePathWithHotpatchFallback: StringCchCopy of hotpatch path failed with hr=0x%08x`
- `0x180037136`: `GetUpdateFilePathWithHotpatchFallback: Hotpatch path empty, falling back to System32 path`
- `0x180037148`: `\SecureBootUpdates\`
- `0x180037165`: `GetUpdateFilePathWithHotpatchFallback: StringCchCopy of SECUREBOOT_UPDATE_LOC_IN_SYS32 failed with hr=0x%08x`
- `0x180037187`: `GetUpdateFilePathWithHotpatchFallback: StringCchCatW of fileName failed with hr=0x%08x`
- `0x180037198`: `GetUpdateFilePathWithHotpatchFallback: System32 update path: %s`
- `0x1800371bd`: `GetUpdateFilePathWithHotpatchFallback: GetSecureBootUpdateFilePath failed with hr=0x%08x`
- `0x1800371d0`: `GetUpdateFilePathWithHotpatchFallback: Final update path: %s`

## pseudocode

```c
__int64 __fastcall GetUpdateFilePathWithHotpatchFallback(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  __int64 v8; // rdx
  int HotpatchUpdatePath; // ebx
  unsigned __int64 v10; // r11
  __int64 v11; // r8
  unsigned __int16 v13[264]; // [rsp+20h] [rbp-458h] BYREF
  unsigned __int16 v14[264]; // [rsp+230h] [rbp-248h] BYREF

  memset_0(v13, 0, 0x208u);
  memset_0(v14, 0, 0x208u);
  SBServicingLogMessage((wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: Enter, fileName=%s", a1);
  if ( a5 )
    *a5 = 0;
  HotpatchUpdatePath = GetHotpatchUpdatePath(v13, v8, a1);
  if ( HotpatchUpdatePath >= 0 )
  {
    if ( v13[0] )
    {
      SBServicingLogMessage((wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: Using hotpatch path: %s", v13);
      HotpatchUpdatePath = StringCchCopyW(a2, 0x104u, v13);
      if ( HotpatchUpdatePath < 0 )
      {
        SBServicingLogMessage(
          L"GetUpdateFilePathWithHotpatchFallback: StringCchCopy of hotpatch path failed with hr=0x%08x",
          (unsigned int)HotpatchUpdatePath);
      }
      else if ( a5 )
      {
        *a5 = 1;
      }
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: Hotpatch path empty, falling back to System32 path");
      HotpatchUpdatePath = StringCchCopyW(v14, 0x104u, L"\\SecureBootUpdates\\");
      if ( HotpatchUpdatePath >= 0 )
      {
        HotpatchUpdatePath = StringCchCatW(v14, v10, a1);
        if ( HotpatchUpdatePath >= 0 )
        {
          SBServicingLogMessage((wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: System32 update path: %s", v14);
          HotpatchUpdatePath = GetSecureBootUpdateFilePath(v14, a2, v11, a4);
          if ( HotpatchUpdatePath >= 0 )
            SBServicingLogMessage((wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: Final update path: %s", a2);
          else
            SBServicingLogMessage(
              (wchar_t *)L"GetUpdateFilePathWithHotpatchFallback: GetSecureBootUpdateFilePath failed with hr=0x%08x",
              (unsigned int)HotpatchUpdatePath);
        }
        else
        {
          SBServicingLogMessage(
            L"GetUpdateFilePathWithHotpatchFallback: StringCchCatW of fileName failed with hr=0x%08x",
            (unsigned int)HotpatchUpdatePath);
        }
      }
      else
      {
        SBServicingLogMessage(
          L"GetUpdateFilePathWithHotpatchFallback: StringCchCopy of SECUREBOOT_UPDATE_LOC_IN_SYS32 failed with hr=0x%08x",
          (unsigned int)HotpatchUpdatePath);
      }
    }
  }
  else
  {
    SBServicingLogMessage(
      L"GetUpdateFilePathWithHotpatchFallback: GetHotpatchUpdatePath failed with hr=0x%08x",
      (unsigned int)HotpatchUpdatePath);
  }
  return (unsigned int)HotpatchUpdatePath;
}

```

## disassembly

```asm
0x180037050  mov     [rsp+arg_10], rbx
0x180037055  push    rbp
0x180037056  push    rsi
0x180037057  push    rdi
0x180037058  push    r14
0x18003705a  push    r15
0x18003705c  sub     rsp, 450h
0x180037063  mov     rax, cs:__security_cookie
0x18003706a  xor     rax, rsp
0x18003706d  mov     [rsp+478h+var_38], rax
0x180037075  mov     rdi, [rsp+478h+arg_20]
0x18003707d  mov     rsi, rdx
0x180037080  mov     rbp, rcx
0x180037083  mov     ebx, 208h
0x180037088  mov     r8d, ebx; Size
0x18003708b  lea     rcx, [rsp+478h+var_458]; void *
0x180037090  xor     edx, edx; Val
0x180037092  mov     r14d, r9d
0x180037095  call    memset_0
0x18003709a  mov     r8d, ebx; Size
0x18003709d  lea     rcx, [rsp+478h+var_248]; void *
0x1800370a5  xor     edx, edx; Val
0x1800370a7  call    memset_0
0x1800370ac  mov     rdx, rbp
0x1800370af  lea     rcx, aGetupdatefilep_0; "GetUpdateFilePathWithHotpatchFallback: "...
0x1800370b6  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800370bb  xor     r15d, r15d
0x1800370be  test    rdi, rdi
0x1800370c1  jz      short loc_1800370C6
0x1800370c3  mov     [rdi], r15d
0x1800370c6  mov     r8, rbp; unsigned __int16 *
0x1800370c9  lea     rcx, [rsp+478h+var_458]; unsigned __int16 *
0x1800370ce  call    ?GetHotpatchUpdatePath@@YAJPEAGKPEBG@Z; GetHotpatchUpdatePath(ushort *,ulong,ushort const *)
0x1800370d3  mov     ebx, eax
0x1800370d5  test    eax, eax
0x1800370d7  jns     short loc_1800370E5
0x1800370d9  lea     rcx, aGetupdatefilep_12; "GetUpdateFilePathWithHotpatchFallback: "...
0x1800370e0  jmp     loc_1800371C4
0x1800370e5  cmp     [rsp+478h+var_458], r15w
0x1800370eb  jz      short loc_180037136
0x1800370ed  lea     rdx, [rsp+478h+var_458]
0x1800370f2  lea     rcx, aGetupdatefilep_11; "GetUpdateFilePathWithHotpatchFallback: "...
0x1800370f9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800370fe  lea     r8, [rsp+478h+var_458]; unsigned __int16 *
0x180037103  mov     edx, 104h; unsigned __int64
0x180037108  mov     rcx, rsi; unsigned __int16 *
0x18003710b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037110  mov     ebx, eax
0x180037112  test    eax, eax
0x180037114  js      short loc_18003712A
0x180037116  test    rdi, rdi
0x180037119  jz      loc_1800371DC
0x18003711f  mov     dword ptr [rdi], 1
0x180037125  jmp     loc_1800371DC
0x18003712a  lea     rcx, aGetupdatefilep_2; "GetUpdateFilePathWithHotpatchFallback: "...
0x180037131  jmp     loc_1800371C4
0x180037136  lea     rcx, aGetupdatefilep_10; "GetUpdateFilePathWithHotpatchFallback: "...
0x18003713d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180037142  mov     r11d, 104h
0x180037148  lea     r8, aSecurebootupda_2; "\\SecureBootUpdates\\"
0x18003714f  mov     edx, r11d; unsigned __int64
0x180037152  lea     rcx, [rsp+478h+var_248]; unsigned __int16 *
0x18003715a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003715f  mov     ebx, eax
0x180037161  test    eax, eax
0x180037163  jns     short loc_18003716E
0x180037165  lea     rcx, aGetupdatefilep_8; "GetUpdateFilePathWithHotpatchFallback: "...
0x18003716c  jmp     short loc_1800371C4
0x18003716e  mov     r8, rbp; unsigned __int16 *
0x180037171  lea     rcx, [rsp+478h+var_248]; unsigned __int16 *
0x180037179  mov     rdx, r11; unsigned __int64
0x18003717c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037181  mov     ebx, eax
0x180037183  test    eax, eax
0x180037185  jns     short loc_180037190
0x180037187  lea     rcx, aGetupdatefilep_7; "GetUpdateFilePathWithHotpatchFallback: "...
0x18003718e  jmp     short loc_1800371C4
0x180037190  lea     rdx, [rsp+478h+var_248]
0x180037198  lea     rcx, aGetupdatefilep; "GetUpdateFilePathWithHotpatchFallback: "...
0x18003719f  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800371a4  mov     r9d, r14d
0x1800371a7  lea     rcx, [rsp+478h+var_248]
0x1800371af  mov     rdx, rsi
0x1800371b2  call    ?GetSecureBootUpdateFilePath@@YAJPEBGPEAGKW4Source@SBServiceUpdateCaller@@@Z; GetSecureBootUpdateFilePath(ushort const *,ushort *,ulong,SBServiceUpdateCaller::Source)
0x1800371b7  mov     ebx, eax
0x1800371b9  test    eax, eax
0x1800371bb  jns     short loc_1800371CD
0x1800371bd  lea     rcx, aGetupdatefilep_4; "GetUpdateFilePathWithHotpatchFallback: "...
0x1800371c4  mov     edx, ebx
0x1800371c6  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800371cb  jmp     short loc_1800371DC
0x1800371cd  mov     rdx, rsi
0x1800371d0  lea     rcx, aGetupdatefilep_3; "GetUpdateFilePathWithHotpatchFallback: "...
0x1800371d7  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800371dc  mov     eax, ebx
0x1800371de  mov     rcx, [rsp+478h+var_38]
0x1800371e6  xor     rcx, rsp; StackCookie
0x1800371e9  call    __security_check_cookie
0x1800371ee  mov     rbx, [rsp+478h+arg_10]
0x1800371f6  add     rsp, 450h
0x1800371fd  pop     r15
0x1800371ff  pop     r14
0x180037201  pop     rdi
0x180037202  pop     rsi
0x180037203  pop     rbp
0x180037204  retn
```

# WctGetCOMInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *,_WCT_LOCK_CONTEXT *)

- ea: `0x18003fddc`
- end: `0x1800400e9`
- name: `?WctGetCOMInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@KPEAU_WAITCHAIN_NODE_INFO@@PEAK3PEAU_WCT_LOCK_CONTEXT@@@Z`
- size: `781`
- prototype: `unsigned int __usercall@<eax>(struct _WCT_CLIENT_HANDLE *@<rcx>, struct _SYSTEM_PROCESS_INFORMATION *@<rdx>, unsigned int@<r8d>, struct _WAITCHAIN_NODE_INFO *@<r9>, unsigned int *, unsigned int *, struct _WCT_LOCK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ae08`

## callees

- `0x18003f5cc`
- `0x18003fb18`
- `0x18003fd04`
- `0x18003fddc`
- `0x18006c430`
- `0x18006c5ec`
- `0x180072036`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18003ffbd`
- `ntdll!RtlStringFromGUID` at `0x18003ffbd`
- `ntdll!NtQueryInformationThread` at `0x18003feab`
- `ntdll!NtQueryInformationThread` at `0x18003feab`
- `ntdll!RtlFreeUnicodeString` at `0x180040003`
- `ntdll!RtlFreeUnicodeString` at `0x180040003`
- `KERNEL32!ReadProcessMemory` at `0x18003feeb`
- `KERNEL32!ReadProcessMemory` at `0x18003ff27`
- `KERNEL32!ReadProcessMemory` at `0x18003ff87`
- `KERNEL32!ReadProcessMemory` at `0x18003feeb`
- `KERNEL32!ReadProcessMemory` at `0x18003ff27`
- `KERNEL32!ReadProcessMemory` at `0x18003ff87`

## pseudocode

```c
__int64 __fastcall WctGetCOMInfo(
        HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        char a3,
        struct _WAITCHAIN_NODE_INFO *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _WCT_LOCK_CONTEXT *a7)
{
  unsigned int v10; // eax
  unsigned __int64 Length; // rbx
  int v12; // ebx
  GUID v13; // xmm0
  unsigned int v14; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-71h] BYREF
  __int64 v17; // [rsp+38h] [rbp-69h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-61h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-59h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+58h] [rbp-49h] BYREF
  struct _SYSTEM_PROCESS_INFORMATION *v21; // [rsp+60h] [rbp-41h]
  _OWORD ThreadInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  __int128 Buf1; // [rsp+98h] [rbp-9h] BYREF

  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v17 = 0;
  Buf1 = 0;
  v21 = a2;
  GuidString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( dword_1800B2388
    && !(unsigned int)WctIsWow64(a1[1])
    && NtQueryInformationThread(*a1, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength) >= 0
    && ReturnLength == 48
    && ReadProcessMemory(
         a1[1],
         (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
         &Buffer,
         8u,
         &NumberOfBytesRead)
    && NumberOfBytesRead == 8
    && ReadProcessMemory(a1[1], (LPCVOID)(Buffer + (unsigned int)dword_1800B2388), &v17, 8u, 0)
    && HIDWORD(v17) != -1 )
  {
    v10 = dword_1800B2378;
    a4->ObjectType = WctComType;
    a4->ObjectStatus = WctStatusOwned;
    Buf1 = xmmword_18008C368;
    if ( v10 )
    {
      if ( ReadProcessMemory(a1[1], (LPCVOID)(Buffer + v10), &Buf1, 0x10u, 0) )
      {
        if ( memcmp_0(&Buf1, &xmmword_18008C368, 0x10u) )
        {
          GuidString.Buffer = 0;
          if ( RtlStringFromGUID((const GUID *const)&Buf1, &GuidString) >= 0 )
          {
            if ( GuidString.Length < 0x100u )
            {
              Length = GuidString.Length;
              memcpy_0(&a4->LockObject, GuidString.Buffer, GuidString.Length);
              a4->LockObject.ObjectName[Length >> 1] = 0;
            }
            if ( GuidString.Buffer )
              RtlFreeUnicodeString(&GuidString);
          }
        }
      }
    }
    *a5 = HIDWORD(v17);
    if ( (_DWORD)v17 )
    {
      *a6 = v17;
    }
    else
    {
      *a6 = 0;
      *a5 = 0;
    }
    v12 = *a6;
    if ( *a6 != *((_DWORD *)a1 + 4) )
    {
      if ( !memcmp_0(&Buf1, &xmmword_18008C368, 0x10u) || !(unsigned int)WctIsRpcssPid(v12) )
      {
        if ( !*a5 && (a3 & 2) != 0 )
          WctGetCOMServerInfo((struct _WCT_CLIENT_HANDLE *)a1, v21, a5, a6);
      }
      else
      {
        v13 = (GUID)Buf1;
        *(_DWORD *)a7 = 9;
        *(GUID *)((char *)a7 + 4) = v13;
      }
    }
    v14 = 0;
  }
  else
  {
    v14 = 1168;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18003fddc  mov     [rsp-8+arg_10], rbx
0x18003fde1  push    rbp
0x18003fde2  push    rsi
0x18003fde3  push    rdi
0x18003fde4  push    r12
0x18003fde6  push    r13
0x18003fde8  push    r14
0x18003fdea  push    r15
0x18003fdec  lea     rbp, [rsp-0Fh]
0x18003fdf1  sub     rsp, 0B0h
0x18003fdf8  mov     rax, cs:__security_cookie
0x18003fdff  xor     rax, rsp
0x18003fe02  mov     [rbp+3Fh+var_38], rax
0x18003fe06  mov     r12, [rbp+3Fh+arg_30]
0x18003fe0a  xorps   xmm0, xmm0
0x18003fe0d  mov     rsi, [rbp+3Fh+arg_20]
0x18003fe11  xor     ebx, ebx
0x18003fe13  mov     r14, [rbp+3Fh+arg_28]
0x18003fe17  xorps   xmm1, xmm1
0x18003fe1a  movups  [rbp+3Fh+ThreadInformation], xmm0
0x18003fe1e  mov     [rbp+3Fh+NumberOfBytesRead], rbx
0x18003fe22  mov     r15, r9
0x18003fe25  movups  [rbp+3Fh+var_68], xmm0
0x18003fe29  mov     [rbp+3Fh+var_B0], ebx
0x18003fe2c  mov     r13d, r8d
0x18003fe2f  movups  [rbp+3Fh+var_58], xmm0
0x18003fe33  mov     [rbp+3Fh+Buffer], rbx
0x18003fe37  mov     rdi, rcx
0x18003fe3a  mov     [rbp+3Fh+var_A8], rbx
0x18003fe3e  movups  [rbp+3Fh+Buf1], xmm0
0x18003fe42  mov     [rbp+3Fh+var_80], rdx
0x18003fe46  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm1
0x18003fe4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe51  lea     rax, WPP_GLOBAL_Control
0x18003fe58  cmp     rcx, rax
0x18003fe5b  jz      short loc_18003FE76
0x18003fe5d  test    byte ptr [rcx+1Ch], 4
0x18003fe61  jz      short loc_18003FE76
0x18003fe63  mov     rcx, [rcx+10h]
0x18003fe67  lea     edx, [rbx+26h]
0x18003fe6a  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003fe71  call    WPP_SF_
0x18003fe76  cmp     cs:dword_1800B2388, ebx
0x18003fe7c  jz      loc_180040089
0x18003fe82  mov     rcx, [rdi+8]; void *
0x18003fe86  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18003fe8b  test    eax, eax
0x18003fe8d  jnz     loc_180040089
0x18003fe93  mov     rcx, [rdi]; ThreadHandle
0x18003fe96  lea     rax, [rbp+3Fh+var_B0]
0x18003fe9a  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18003fea0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18003fea5  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x18003fea9  xor     edx, edx; ThreadInformationClass
0x18003feab  call    cs:__imp_NtQueryInformationThread
0x18003feb2  nop     dword ptr [rax+rax+00h]
0x18003feb7  test    eax, eax
0x18003feb9  js      loc_180040089
0x18003febf  cmp     [rbp+3Fh+var_B0], 30h ; '0'
0x18003fec3  jnz     loc_180040089
0x18003fec9  mov     rdx, qword ptr [rbp+3Fh+ThreadInformation+8]
0x18003fecd  lea     rax, [rbp+3Fh+NumberOfBytesRead]
0x18003fed1  mov     rcx, [rdi+8]; hProcess
0x18003fed5  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x18003fed9  add     rdx, 1758h; lpBaseAddress
0x18003fee0  mov     [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003fee5  mov     r9d, 8; nSize
0x18003feeb  call    cs:__imp_ReadProcessMemory
0x18003fef2  nop     dword ptr [rax+rax+00h]
0x18003fef7  test    eax, eax
0x18003fef9  jz      loc_180040089
0x18003feff  cmp     [rbp+3Fh+NumberOfBytesRead], 8
0x18003ff04  jnz     loc_180040089
0x18003ff0a  mov     edx, cs:dword_1800B2388
0x18003ff10  lea     r8, [rbp+3Fh+var_A8]; lpBuffer
0x18003ff14  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18003ff18  mov     r9d, 8; nSize
0x18003ff1e  mov     rcx, [rdi+8]; hProcess
0x18003ff22  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18003ff27  call    cs:__imp_ReadProcessMemory
0x18003ff2e  nop     dword ptr [rax+rax+00h]
0x18003ff33  test    eax, eax
0x18003ff35  jz      loc_180040089
0x18003ff3b  cmp     dword ptr [rbp+3Fh+var_A8+4], 0FFFFFFFFh
0x18003ff3f  jz      loc_180040089
0x18003ff45  mov     eax, cs:dword_1800B2378
0x18003ff4b  mov     dword ptr [r15], 5
0x18003ff52  mov     dword ptr [r15+4], 6
0x18003ff5a  movups  xmm0, cs:xmmword_18008C368
0x18003ff61  movdqu  [rbp+3Fh+Buf1], xmm0
0x18003ff66  test    eax, eax
0x18003ff68  jz      loc_18004000F
0x18003ff6e  mov     rcx, [rdi+8]; hProcess
0x18003ff72  lea     r8, [rbp+3Fh+Buf1]; lpBuffer
0x18003ff76  mov     edx, eax
0x18003ff78  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18003ff7d  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18003ff81  mov     r9d, 10h; nSize
0x18003ff87  call    cs:__imp_ReadProcessMemory
0x18003ff8e  nop     dword ptr [rax+rax+00h]
0x18003ff93  test    eax, eax
0x18003ff95  jz      short loc_18004000F
0x18003ff97  mov     r8d, 10h; Size
0x18003ff9d  lea     rdx, xmmword_18008C368; Buf2
0x18003ffa4  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18003ffa8  call    memcmp_0
0x18003ffad  test    eax, eax
0x18003ffaf  jz      short loc_18004000F
0x18003ffb1  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x18003ffb5  mov     [rbp+3Fh+GuidString.Buffer], rbx
0x18003ffb9  lea     rcx, [rbp+3Fh+Buf1]; Guid
0x18003ffbd  call    cs:__imp_RtlStringFromGUID
0x18003ffc4  nop     dword ptr [rax+rax+00h]
0x18003ffc9  test    eax, eax
0x18003ffcb  js      short loc_18004000F
0x18003ffcd  mov     eax, 100h
0x18003ffd2  cmp     [rbp+3Fh+GuidString.Length], ax
0x18003ffd6  jnb     short loc_18003FFF9
0x18003ffd8  movzx   ebx, [rbp+3Fh+GuidString.Length]
0x18003ffdc  lea     rcx, [r15+8]; void *
0x18003ffe0  mov     rdx, [rbp+3Fh+GuidString.Buffer]; Src
0x18003ffe4  mov     r8d, ebx; Size
0x18003ffe7  call    memcpy_0
0x18003ffec  shr     rbx, 1
0x18003ffef  xor     eax, eax
0x18003fff1  mov     [r15+rbx*2+8], ax
0x18003fff7  xor     ebx, ebx
0x18003fff9  cmp     [rbp+3Fh+GuidString.Buffer], rbx
0x18003fffd  jz      short loc_18004000F
0x18003ffff  lea     rcx, [rbp+3Fh+GuidString]; UnicodeString
0x180040003  call    cs:__imp_RtlFreeUnicodeString
0x18004000a  nop     dword ptr [rax+rax+00h]
0x18004000f  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x180040012  mov     [rsi], eax
0x180040014  mov     rax, [rbp+3Fh+var_A8]
0x180040018  test    eax, eax
0x18004001a  jnz     short loc_180040023
0x18004001c  mov     [r14], ebx
0x18004001f  mov     [rsi], ebx
0x180040021  jmp     short loc_180040026
0x180040023  mov     [r14], eax
0x180040026  mov     ebx, [r14]
0x180040029  cmp     ebx, [rdi+10h]
0x18004002c  jz      short loc_180040085
0x18004002e  mov     r8d, 10h; Size
0x180040034  lea     rdx, xmmword_18008C368; Buf2
0x18004003b  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18004003f  call    memcmp_0
0x180040044  test    eax, eax
0x180040046  jz      short loc_180040068
0x180040048  mov     ecx, ebx; unsigned int
0x18004004a  call    ?WctIsRpcssPid@@YAHK@Z; WctIsRpcssPid(ulong)
0x18004004f  test    eax, eax
0x180040051  jz      short loc_180040068
0x180040053  movups  xmm0, [rbp+3Fh+Buf1]
0x180040057  mov     dword ptr [r12], 9
0x18004005f  movdqu  xmmword ptr [r12+4], xmm0
0x180040066  jmp     short loc_180040085
0x180040068  cmp     dword ptr [rsi], 0
0x18004006b  jnz     short loc_180040085
0x18004006d  test    r13b, 2
0x180040071  jz      short loc_180040085
0x180040073  mov     rdx, [rbp+3Fh+var_80]; struct _SYSTEM_PROCESS_INFORMATION *
0x180040077  mov     r9, r14; unsigned int *
0x18004007a  mov     r8, rsi; unsigned int *
0x18004007d  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x180040080  call    ?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z; WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)
0x180040085  xor     ebx, ebx
0x180040087  jmp     short loc_18004008E
0x180040089  mov     ebx, 490h
0x18004008e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040095  lea     rax, WPP_GLOBAL_Control
0x18004009c  cmp     rcx, rax
0x18004009f  jz      short loc_1800400BF
0x1800400a1  test    byte ptr [rcx+1Ch], 4
0x1800400a5  jz      short loc_1800400BF
0x1800400a7  mov     rcx, [rcx+10h]
0x1800400ab  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x1800400b2  mov     edx, 27h ; '''
0x1800400b7  mov     r9d, ebx
0x1800400ba  call    WPP_SF_d
0x1800400bf  mov     eax, ebx
0x1800400c1  mov     rcx, [rbp+3Fh+var_38]
0x1800400c5  xor     rcx, rsp; StackCookie
0x1800400c8  call    __security_check_cookie
0x1800400cd  mov     rbx, [rsp+0E0h+arg_10]
0x1800400d5  add     rsp, 0B0h
0x1800400dc  pop     r15
0x1800400de  pop     r14
0x1800400e0  pop     r13
0x1800400e2  pop     r12
0x1800400e4  pop     rdi
0x1800400e5  pop     rsi
0x1800400e6  pop     rbp
0x1800400e7  retn
```

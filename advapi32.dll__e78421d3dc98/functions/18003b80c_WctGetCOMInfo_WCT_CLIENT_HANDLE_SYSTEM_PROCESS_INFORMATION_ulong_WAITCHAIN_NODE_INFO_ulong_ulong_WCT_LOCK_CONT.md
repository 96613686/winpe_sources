# WctGetCOMInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *,_WCT_LOCK_CONTEXT *)

- ea: `0x18003b80c`
- end: `0x18003baf4`
- name: `?WctGetCOMInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@KPEAU_WAITCHAIN_NODE_INFO@@PEAK3PEAU_WCT_LOCK_CONTEXT@@@Z`
- size: `744`
- prototype: `unsigned int __usercall@<eax>(struct _WCT_CLIENT_HANDLE *@<rcx>, struct _SYSTEM_PROCESS_INFORMATION *@<rdx>, unsigned int@<r8d>, struct _WAITCHAIN_NODE_INFO *@<r9>, unsigned int *, unsigned int *, struct _WCT_LOCK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005e660`

## callees

- `0x18003a784`
- `0x18003b57c`
- `0x18003b748`
- `0x18003b80c`
- `0x18005fb78`
- `0x18005fd08`
- `0x180065036`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18003b9d5`
- `ntdll!RtlStringFromGUID` at `0x18003b9d5`
- `ntdll!NtQueryInformationThread` at `0x18003b8db`
- `ntdll!NtQueryInformationThread` at `0x18003b8db`
- `ntdll!RtlFreeUnicodeString` at `0x18003ba15`
- `ntdll!RtlFreeUnicodeString` at `0x18003ba15`
- `KERNEL32!ReadProcessMemory` at `0x18003b915`
- `KERNEL32!ReadProcessMemory` at `0x18003b94b`
- `KERNEL32!ReadProcessMemory` at `0x18003b9a5`
- `KERNEL32!ReadProcessMemory` at `0x18003b915`
- `KERNEL32!ReadProcessMemory` at `0x18003b94b`
- `KERNEL32!ReadProcessMemory` at `0x18003b9a5`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  if ( dword_1800A3238
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
    && ReadProcessMemory(a1[1], (LPCVOID)(Buffer + (unsigned int)dword_1800A3238), &v17, 8u, 0)
    && HIDWORD(v17) != -1 )
  {
    v10 = dword_1800A3220;
    a4->ObjectType = WctComType;
    a4->ObjectStatus = WctStatusOwned;
    Buf1 = xmmword_18007E328;
    if ( v10 )
    {
      if ( ReadProcessMemory(a1[1], (LPCVOID)(Buffer + v10), &Buf1, 0x10u, 0) )
      {
        if ( memcmp_0(&Buf1, &xmmword_18007E328, 0x10u) )
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
      if ( !memcmp_0(&Buf1, &xmmword_18007E328, 0x10u) || !(unsigned int)WctIsRpcssPid(v12) )
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18003b80c  mov     [rsp-8+arg_10], rbx
0x18003b811  push    rbp
0x18003b812  push    rsi
0x18003b813  push    rdi
0x18003b814  push    r12
0x18003b816  push    r13
0x18003b818  push    r14
0x18003b81a  push    r15
0x18003b81c  lea     rbp, [rsp-0Fh]
0x18003b821  sub     rsp, 0B0h
0x18003b828  mov     rax, cs:__security_cookie
0x18003b82f  xor     rax, rsp
0x18003b832  mov     [rbp+3Fh+var_38], rax
0x18003b836  mov     r12, [rbp+3Fh+arg_30]
0x18003b83a  xorps   xmm0, xmm0
0x18003b83d  mov     rsi, [rbp+3Fh+arg_20]
0x18003b841  xor     ebx, ebx
0x18003b843  mov     r14, [rbp+3Fh+arg_28]
0x18003b847  xorps   xmm1, xmm1
0x18003b84a  movups  [rbp+3Fh+ThreadInformation], xmm0
0x18003b84e  mov     [rbp+3Fh+NumberOfBytesRead], rbx
0x18003b852  mov     r15, r9
0x18003b855  movups  [rbp+3Fh+var_68], xmm0
0x18003b859  mov     [rbp+3Fh+var_B0], ebx
0x18003b85c  mov     r13d, r8d
0x18003b85f  movups  [rbp+3Fh+var_58], xmm0
0x18003b863  mov     [rbp+3Fh+Buffer], rbx
0x18003b867  mov     rdi, rcx
0x18003b86a  mov     [rbp+3Fh+var_A8], rbx
0x18003b86e  movups  [rbp+3Fh+Buf1], xmm0
0x18003b872  mov     [rbp+3Fh+var_80], rdx
0x18003b876  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm1
0x18003b87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b881  lea     rax, WPP_GLOBAL_Control
0x18003b888  cmp     rcx, rax
0x18003b88b  jz      short loc_18003B8A6
0x18003b88d  test    byte ptr [rcx+1Ch], 4
0x18003b891  jz      short loc_18003B8A6
0x18003b893  mov     rcx, [rcx+10h]
0x18003b897  lea     edx, [rbx+26h]
0x18003b89a  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003b8a1  call    WPP_SF_
0x18003b8a6  cmp     cs:dword_1800A3238, ebx
0x18003b8ac  jz      loc_18003BA95
0x18003b8b2  mov     rcx, [rdi+8]; void *
0x18003b8b6  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18003b8bb  test    eax, eax
0x18003b8bd  jnz     loc_18003BA95
0x18003b8c3  mov     rcx, [rdi]; ThreadHandle
0x18003b8c6  lea     rax, [rbp+3Fh+var_B0]
0x18003b8ca  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18003b8d0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18003b8d5  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x18003b8d9  xor     edx, edx; ThreadInformationClass
0x18003b8db  call    cs:__imp_NtQueryInformationThread
0x18003b8e1  test    eax, eax
0x18003b8e3  js      loc_18003BA95
0x18003b8e9  cmp     [rbp+3Fh+var_B0], 30h ; '0'
0x18003b8ed  jnz     loc_18003BA95
0x18003b8f3  mov     rdx, qword ptr [rbp+3Fh+ThreadInformation+8]
0x18003b8f7  lea     rax, [rbp+3Fh+NumberOfBytesRead]
0x18003b8fb  mov     rcx, [rdi+8]; hProcess
0x18003b8ff  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x18003b903  add     rdx, 1758h; lpBaseAddress
0x18003b90a  mov     [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003b90f  mov     r9d, 8; nSize
0x18003b915  call    cs:__imp_ReadProcessMemory
0x18003b91b  test    eax, eax
0x18003b91d  jz      loc_18003BA95
0x18003b923  cmp     [rbp+3Fh+NumberOfBytesRead], 8
0x18003b928  jnz     loc_18003BA95
0x18003b92e  mov     edx, cs:dword_1800A3238
0x18003b934  lea     r8, [rbp+3Fh+var_A8]; lpBuffer
0x18003b938  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18003b93c  mov     r9d, 8; nSize
0x18003b942  mov     rcx, [rdi+8]; hProcess
0x18003b946  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18003b94b  call    cs:__imp_ReadProcessMemory
0x18003b951  test    eax, eax
0x18003b953  jz      loc_18003BA95
0x18003b959  cmp     dword ptr [rbp+3Fh+var_A8+4], 0FFFFFFFFh
0x18003b95d  jz      loc_18003BA95
0x18003b963  mov     eax, cs:dword_1800A3220
0x18003b969  mov     dword ptr [r15], 5
0x18003b970  mov     dword ptr [r15+4], 6
0x18003b978  movups  xmm0, cs:xmmword_18007E328
0x18003b97f  movdqu  [rbp+3Fh+Buf1], xmm0
0x18003b984  test    eax, eax
0x18003b986  jz      loc_18003BA1B
0x18003b98c  mov     rcx, [rdi+8]; hProcess
0x18003b990  lea     r8, [rbp+3Fh+Buf1]; lpBuffer
0x18003b994  mov     edx, eax
0x18003b996  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x18003b99b  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x18003b99f  mov     r9d, 10h; nSize
0x18003b9a5  call    cs:__imp_ReadProcessMemory
0x18003b9ab  test    eax, eax
0x18003b9ad  jz      short loc_18003BA1B
0x18003b9af  mov     r8d, 10h; Size
0x18003b9b5  lea     rdx, xmmword_18007E328; Buf2
0x18003b9bc  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18003b9c0  call    memcmp_0
0x18003b9c5  test    eax, eax
0x18003b9c7  jz      short loc_18003BA1B
0x18003b9c9  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x18003b9cd  mov     [rbp+3Fh+GuidString.Buffer], rbx
0x18003b9d1  lea     rcx, [rbp+3Fh+Buf1]; Guid
0x18003b9d5  call    cs:__imp_RtlStringFromGUID
0x18003b9db  test    eax, eax
0x18003b9dd  js      short loc_18003BA1B
0x18003b9df  mov     eax, 100h
0x18003b9e4  cmp     [rbp+3Fh+GuidString.Length], ax
0x18003b9e8  jnb     short loc_18003BA0B
0x18003b9ea  movzx   ebx, [rbp+3Fh+GuidString.Length]
0x18003b9ee  lea     rcx, [r15+8]; void *
0x18003b9f2  mov     rdx, [rbp+3Fh+GuidString.Buffer]; Src
0x18003b9f6  mov     r8d, ebx; Size
0x18003b9f9  call    memcpy_0
0x18003b9fe  shr     rbx, 1
0x18003ba01  xor     eax, eax
0x18003ba03  mov     [r15+rbx*2+8], ax
0x18003ba09  xor     ebx, ebx
0x18003ba0b  cmp     [rbp+3Fh+GuidString.Buffer], rbx
0x18003ba0f  jz      short loc_18003BA1B
0x18003ba11  lea     rcx, [rbp+3Fh+GuidString]; UnicodeString
0x18003ba15  call    cs:__imp_RtlFreeUnicodeString
0x18003ba1b  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x18003ba1e  mov     [rsi], eax
0x18003ba20  mov     rax, [rbp+3Fh+var_A8]
0x18003ba24  test    eax, eax
0x18003ba26  jnz     short loc_18003BA2F
0x18003ba28  mov     [r14], ebx
0x18003ba2b  mov     [rsi], ebx
0x18003ba2d  jmp     short loc_18003BA32
0x18003ba2f  mov     [r14], eax
0x18003ba32  mov     ebx, [r14]
0x18003ba35  cmp     ebx, [rdi+10h]
0x18003ba38  jz      short loc_18003BA91
0x18003ba3a  mov     r8d, 10h; Size
0x18003ba40  lea     rdx, xmmword_18007E328; Buf2
0x18003ba47  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x18003ba4b  call    memcmp_0
0x18003ba50  test    eax, eax
0x18003ba52  jz      short loc_18003BA74
0x18003ba54  mov     ecx, ebx; unsigned int
0x18003ba56  call    ?WctIsRpcssPid@@YAHK@Z; WctIsRpcssPid(ulong)
0x18003ba5b  test    eax, eax
0x18003ba5d  jz      short loc_18003BA74
0x18003ba5f  movups  xmm0, [rbp+3Fh+Buf1]
0x18003ba63  mov     dword ptr [r12], 9
0x18003ba6b  movdqu  xmmword ptr [r12+4], xmm0
0x18003ba72  jmp     short loc_18003BA91
0x18003ba74  cmp     dword ptr [rsi], 0
0x18003ba77  jnz     short loc_18003BA91
0x18003ba79  test    r13b, 2
0x18003ba7d  jz      short loc_18003BA91
0x18003ba7f  mov     rdx, [rbp+3Fh+var_80]; struct _SYSTEM_PROCESS_INFORMATION *
0x18003ba83  mov     r9, r14; unsigned int *
0x18003ba86  mov     r8, rsi; unsigned int *
0x18003ba89  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18003ba8c  call    ?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z; WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)
0x18003ba91  xor     ebx, ebx
0x18003ba93  jmp     short loc_18003BA9A
0x18003ba95  mov     ebx, 490h
0x18003ba9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003baa1  lea     rax, WPP_GLOBAL_Control
0x18003baa8  cmp     rcx, rax
0x18003baab  jz      short loc_18003BACB
0x18003baad  test    byte ptr [rcx+1Ch], 4
0x18003bab1  jz      short loc_18003BACB
0x18003bab3  mov     rcx, [rcx+10h]
0x18003bab7  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003babe  mov     edx, 27h ; '''
0x18003bac3  mov     r9d, ebx
0x18003bac6  call    WPP_SF_d
0x18003bacb  mov     eax, ebx
0x18003bacd  mov     rcx, [rbp+3Fh+var_38]
0x18003bad1  xor     rcx, rsp; StackCookie
0x18003bad4  call    __security_check_cookie
0x18003bad9  mov     rbx, [rsp+0E0h+arg_10]
0x18003bae1  add     rsp, 0B0h
0x18003bae8  pop     r15
0x18003baea  pop     r14
0x18003baec  pop     r13
0x18003baee  pop     r12
0x18003baf0  pop     rdi
0x18003baf1  pop     rsi
0x18003baf2  pop     rbp
0x18003baf3  retn
```

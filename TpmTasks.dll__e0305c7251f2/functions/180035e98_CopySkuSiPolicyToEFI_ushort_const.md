# CopySkuSiPolicyToEFI(ushort const *)

- ea: `0x180035e98`
- end: `0x180036013`
- name: `?CopySkuSiPolicyToEFI@@YAJPEBG@Z`
- size: `379`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034634`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x180035e98`
- `0x180036f28`
- `0x18003720c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180035efb`
- `ntdll!NtQuerySystemInformation` at `0x180035efb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035fec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fbd`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180035fb3`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180035fb3`

## pseudocode

```c
__int64 __fastcall CopySkuSiPolicyToEFI(LPCWSTR lpExistingFileName)
{
  NTSTATUS v2; // eax
  signed int v3; // ebx
  int SystemPartition; // eax
  unsigned __int16 *v5; // rdi
  unsigned __int64 v6; // rax
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-E0h] BYREF
  __int128 SystemInformation; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+38h] [rbp-C8h]
  WCHAR NewFileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  lpMem = 0;
  memset_0(NewFileName, 0, 0x208u);
  SystemInformation = 0;
  v12 = 0;
  v2 = NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  v3 = HResultFromNtStatus(v2);
  if ( v3 >= 0 )
  {
    if ( (_DWORD)v12 == 2 )
    {
      SystemPartition = GetSystemPartition((unsigned __int16 **)&lpMem);
      v5 = (unsigned __int16 *)lpMem;
      v3 = SystemPartition;
      if ( SystemPartition >= 0 )
      {
        if ( !lpMem )
          goto LABEL_15;
        v6 = -1;
        do
          ++v6;
        while ( *((_WORD *)lpMem + v6) );
        if ( v6 > 8 )
        {
          v3 = StringCchCopyW(NewFileName, 0x104u, L"\\\\.\\");
          if ( v3 >= 0 )
          {
            v3 = StringCchCatW(NewFileName, 0x104u, v5 + 8);
            if ( v3 >= 0 )
            {
              v3 = StringCchCatW(NewFileName, 0x104u, L"\\EFI\\Microsoft\\Boot\\SkuSiPolicy.p7b");
              if ( v3 >= 0 && !CopyFileW(lpExistingFileName, NewFileName, 0) )
              {
                LastError = GetLastError();
                v3 = LastError;
                if ( LastError > 0 )
                  v3 = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
        else
        {
LABEL_15:
          v3 = -2147467261;
        }
      }
      if ( v5 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v5);
      }
    }
    else
    {
      return 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180035e98  push    rbp
0x180035e9a  push    rbx
0x180035e9b  push    rsi
0x180035e9c  push    rdi
0x180035e9d  push    r14
0x180035e9f  push    r15
0x180035ea1  lea     rbp, [rsp-178h]
0x180035ea9  sub     rsp, 278h
0x180035eb0  mov     rax, cs:__security_cookie
0x180035eb7  xor     rax, rsp
0x180035eba  mov     [rbp+1A0h+var_40], rax
0x180035ec1  mov     rsi, rcx
0x180035ec4  xor     r14d, r14d
0x180035ec7  lea     rcx, [rsp+2A0h+NewFileName]; void *
0x180035ecc  mov     [rsp+2A0h+lpMem], r14
0x180035ed1  xor     edx, edx; Val
0x180035ed3  mov     r8d, 208h; Size
0x180035ed9  call    memset_0
0x180035ede  xorps   xmm0, xmm0
0x180035ee1  lea     r8d, [r14+20h]; SystemInformationLength
0x180035ee5  xor     r9d, r9d; ReturnLength
0x180035ee8  lea     rdx, [rsp+2A0h+SystemInformation]; SystemInformation
0x180035eed  lea     ecx, [r14+5Ah]; SystemInformationClass
0x180035ef1  movups  [rsp+2A0h+SystemInformation], xmm0
0x180035ef6  movups  [rsp+2A0h+var_268], xmm0
0x180035efb  call    cs:__imp_NtQuerySystemInformation
0x180035f01  mov     ecx, eax; int
0x180035f03  call    ?HResultFromNtStatus@@YAJJ@Z; HResultFromNtStatus(long)
0x180035f08  mov     ebx, eax
0x180035f0a  test    eax, eax
0x180035f0c  js      loc_180035FF2
0x180035f12  cmp     dword ptr [rsp+2A0h+var_268], 2
0x180035f17  jz      short loc_180035F21
0x180035f19  mov     ebx, r14d
0x180035f1c  jmp     loc_180035FF2
0x180035f21  lea     rcx, [rsp+2A0h+lpMem]; unsigned __int16 **
0x180035f26  call    ?GetSystemPartition@@YAJPEAPEAG@Z; GetSystemPartition(ushort * *)
0x180035f2b  mov     rdi, [rsp+2A0h+lpMem]
0x180035f30  mov     ebx, eax
0x180035f32  test    eax, eax
0x180035f34  js      loc_180035FD9
0x180035f3a  test    rdi, rdi
0x180035f3d  jz      loc_180035FD4
0x180035f43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035f47  inc     rax
0x180035f4a  cmp     [rdi+rax*2], r14w
0x180035f4f  jnz     short loc_180035F47
0x180035f51  cmp     rax, 8
0x180035f55  jbe     short loc_180035FD4
0x180035f57  mov     r15d, 104h
0x180035f5d  lea     r8, asc_18006FFE8; "\\\\.\\"
0x180035f64  mov     edx, r15d; unsigned __int64
0x180035f67  lea     rcx, [rsp+2A0h+NewFileName]; unsigned __int16 *
0x180035f6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035f71  mov     ebx, eax
0x180035f73  test    eax, eax
0x180035f75  js      short loc_180035FD9
0x180035f77  lea     r8, [rdi+10h]; unsigned __int16 *
0x180035f7b  mov     edx, r15d; unsigned __int64
0x180035f7e  lea     rcx, [rsp+2A0h+NewFileName]; unsigned __int16 *
0x180035f83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035f88  mov     ebx, eax
0x180035f8a  test    eax, eax
0x180035f8c  js      short loc_180035FD9
0x180035f8e  lea     r8, aEfiMicrosoftBo_0; "\\EFI\\Microsoft\\Boot\\SkuSiPolicy.p7b"
0x180035f95  mov     edx, r15d; unsigned __int64
0x180035f98  lea     rcx, [rsp+2A0h+NewFileName]; unsigned __int16 *
0x180035f9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035fa2  mov     ebx, eax
0x180035fa4  test    eax, eax
0x180035fa6  js      short loc_180035FD9
0x180035fa8  xor     r8d, r8d; bFailIfExists
0x180035fab  lea     rdx, [rsp+2A0h+NewFileName]; lpNewFileName
0x180035fb0  mov     rcx, rsi; lpExistingFileName
0x180035fb3  call    cs:__imp_CopyFileW
0x180035fb9  test    eax, eax
0x180035fbb  jnz     short loc_180035FD9
0x180035fbd  call    cs:__imp_GetLastError
0x180035fc3  mov     ebx, eax
0x180035fc5  test    eax, eax
0x180035fc7  jle     short loc_180035FD9
0x180035fc9  movzx   ebx, ax
0x180035fcc  or      ebx, 80070000h
0x180035fd2  jmp     short loc_180035FD9
0x180035fd4  mov     ebx, 80004003h
0x180035fd9  test    rdi, rdi
0x180035fdc  jz      short loc_180035FF2
0x180035fde  call    cs:__imp_GetProcessHeap
0x180035fe4  mov     r8, rdi; lpMem
0x180035fe7  xor     edx, edx; dwFlags
0x180035fe9  mov     rcx, rax; hHeap
0x180035fec  call    cs:__imp_HeapFree
0x180035ff2  mov     eax, ebx
0x180035ff4  mov     rcx, [rbp+1A0h+var_40]
0x180035ffb  xor     rcx, rsp; StackCookie
0x180035ffe  call    __security_check_cookie
0x180036003  add     rsp, 278h
0x18003600a  pop     r15
0x18003600c  pop     r14
0x18003600e  pop     rdi
0x18003600f  pop     rsi
0x180036010  pop     rbx
0x180036011  pop     rbp
0x180036012  retn
```

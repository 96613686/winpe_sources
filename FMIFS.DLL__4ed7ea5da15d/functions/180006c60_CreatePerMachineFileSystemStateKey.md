# CreatePerMachineFileSystemStateKey

- ea: `0x180006c60`
- end: `0x180006d83`
- name: `CreatePerMachineFileSystemStateKey`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180006c60`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006d49`
- `ntdll!RtlNtStatusToDosError` at `0x180006d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ce3`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006cbe`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006cbe`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006c87`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006c92`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006c87`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006c92`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006d07`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006d12`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006d07`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006d12`
- `IfsUtil!?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z` at `0x180006d3c`
- `IfsUtil!?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z` at `0x180006d3c`
- `IfsUtil!??1DP_DRIVE@@UEAA@XZ` at `0x180006cfc`
- `IfsUtil!??1DP_DRIVE@@UEAA@XZ` at `0x180006cfc`
- `IfsUtil!??0DP_DRIVE@@QEAA@XZ` at `0x180006c9c`
- `IfsUtil!??0DP_DRIVE@@QEAA@XZ` at `0x180006c9c`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180006cd9`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180006cd9`
- `IfsUtil!?CreateFileSystemRegistryKey@DP_DRIVE@@QEAAKKW4_FMIFS_CREATE_PMFSS_FLAGS@@PEAU_GUID@@PEAPEAUHKEY__@@@Z` at `0x180006d6c`
- `IfsUtil!?CreateFileSystemRegistryKey@DP_DRIVE@@QEAAKKW4_FMIFS_CREATE_PMFSS_FLAGS@@PEAU_GUID@@PEAPEAUHKEY__@@@Z` at `0x180006d6c`

## pseudocode

```c
__int64 __fastcall CreatePerMachineFileSystemStateKey(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v9; // ebx
  signed int FileSystemRegistryKey; // eax
  _BYTE v12[48]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[48]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[96]; // [rsp+90h] [rbp-70h] BYREF
  NTSTATUS Status; // [rsp+F0h] [rbp-10h]

  DSTRING::DSTRING((DSTRING *)v13);
  DSTRING::DSTRING((DSTRING *)v12);
  DP_DRIVE::DP_DRIVE((DP_DRIVE *)v14);
  if ( (a3 & 3) != 3 )
  {
    if ( !WSTRING::Initialize((WSTRING *)v13, a1, 0xFFFFFFFF) )
    {
      v9 = -2147024882;
      goto LABEL_9;
    }
    if ( IFS_SYSTEM::DosDriveNameToNtDriveName((const struct WSTRING *)v13, (struct WSTRING *)v12) )
    {
      if ( DP_DRIVE::Initialize((DP_DRIVE *)v14, (const struct WSTRING *)v12, 0, 1u, 0) )
      {
        v9 = 0;
        FileSystemRegistryKey = DP_DRIVE::CreateFileSystemRegistryKey(v14, a2, a3, a4, a5);
        if ( !FileSystemRegistryKey )
          goto LABEL_9;
        if ( FileSystemRegistryKey <= 0 )
        {
          v9 = FileSystemRegistryKey;
          goto LABEL_9;
        }
        goto LABEL_8;
      }
      FileSystemRegistryKey = RtlNtStatusToDosError(Status);
    }
    else
    {
      FileSystemRegistryKey = GetLastError();
    }
    v9 = FileSystemRegistryKey;
    if ( FileSystemRegistryKey <= 0 )
      goto LABEL_9;
LABEL_8:
    v9 = (unsigned __int16)FileSystemRegistryKey | 0x80070000;
    goto LABEL_9;
  }
  v9 = -2147023892;
LABEL_9:
  DP_DRIVE::~DP_DRIVE((DP_DRIVE *)v14);
  DSTRING::~DSTRING((DSTRING *)v12);
  DSTRING::~DSTRING((DSTRING *)v13);
  return v9;
}

```

## disassembly

```asm
0x180006c60  push    rbp
0x180006c62  push    rbx
0x180006c63  push    rsi
0x180006c64  push    rdi
0x180006c65  push    r14
0x180006c67  lea     rbp, [rsp-110h]
0x180006c6f  sub     rsp, 210h
0x180006c76  mov     rbx, rcx
0x180006c79  mov     rsi, r9
0x180006c7c  lea     rcx, [rsp+230h+var_1D0]
0x180006c81  mov     edi, r8d
0x180006c84  mov     r14d, edx
0x180006c87  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180006c8d  lea     rcx, [rsp+230h+var_200]
0x180006c92  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180006c98  lea     rcx, [rbp+130h+var_1A0]
0x180006c9c  call    cs:__imp_??0DP_DRIVE@@QEAA@XZ; DP_DRIVE::DP_DRIVE(void)
0x180006ca2  mov     eax, edi
0x180006ca4  and     eax, 3
0x180006ca7  cmp     al, 3
0x180006ca9  jnz     short loc_180006CB2
0x180006cab  mov     ebx, 800703ECh
0x180006cb0  jmp     short loc_180006CF8
0x180006cb2  or      r8d, 0FFFFFFFFh
0x180006cb6  lea     rcx, [rsp+230h+var_1D0]
0x180006cbb  mov     rdx, rbx
0x180006cbe  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180006cc4  test    al, al
0x180006cc6  jnz     short loc_180006CCF
0x180006cc8  mov     ebx, 8007000Eh
0x180006ccd  jmp     short loc_180006CF8
0x180006ccf  lea     rdx, [rsp+230h+var_200]
0x180006cd4  lea     rcx, [rsp+230h+var_1D0]
0x180006cd9  call    cs:__imp_?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z; IFS_SYSTEM::DosDriveNameToNtDriveName(WSTRING const *,WSTRING *)
0x180006cdf  test    al, al
0x180006ce1  jnz     short loc_180006D28
0x180006ce3  call    cs:__imp_GetLastError
0x180006ce9  mov     ebx, eax
0x180006ceb  test    eax, eax
0x180006ced  jle     short loc_180006CF8
0x180006cef  movzx   ebx, ax
0x180006cf2  or      ebx, 80070000h
0x180006cf8  lea     rcx, [rbp+130h+var_1A0]
0x180006cfc  call    cs:__imp_??1DP_DRIVE@@UEAA@XZ; DP_DRIVE::~DP_DRIVE(void)
0x180006d02  lea     rcx, [rsp+230h+var_200]
0x180006d07  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006d0d  lea     rcx, [rsp+230h+var_1D0]
0x180006d12  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006d18  mov     eax, ebx
0x180006d1a  add     rsp, 210h
0x180006d21  pop     r14
0x180006d23  pop     rdi
0x180006d24  pop     rsi
0x180006d25  pop     rbx
0x180006d26  pop     rbp
0x180006d27  retn
0x180006d28  mov     r9b, 1
0x180006d2b  mov     byte ptr [rsp+230h+var_210], 0
0x180006d30  xor     r8d, r8d
0x180006d33  lea     rdx, [rsp+230h+var_200]
0x180006d38  lea     rcx, [rbp+130h+var_1A0]
0x180006d3c  call    cs:__imp_?Initialize@DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@EE@Z; DP_DRIVE::Initialize(WSTRING const *,MESSAGE *,uchar,uchar)
0x180006d42  test    al, al
0x180006d44  jnz     short loc_180006D51
0x180006d46  mov     ecx, [rbp+130h+Status]; Status
0x180006d49  call    cs:__imp_RtlNtStatusToDosError
0x180006d4f  jmp     short loc_180006CE9
0x180006d51  mov     rax, [rbp+130h+arg_20]
0x180006d58  lea     rcx, [rbp+130h+var_1A0]
0x180006d5c  mov     r9, rsi
0x180006d5f  mov     [rsp+230h+var_210], rax
0x180006d64  mov     r8d, edi
0x180006d67  mov     edx, r14d
0x180006d6a  xor     ebx, ebx
0x180006d6c  call    cs:__imp_?CreateFileSystemRegistryKey@DP_DRIVE@@QEAAKKW4_FMIFS_CREATE_PMFSS_FLAGS@@PEAU_GUID@@PEAPEAUHKEY__@@@Z; DP_DRIVE::CreateFileSystemRegistryKey(ulong,_FMIFS_CREATE_PMFSS_FLAGS,_GUID *,HKEY__ * *)
0x180006d72  test    eax, eax
0x180006d74  jz      short loc_180006CF8
0x180006d76  jg      loc_180006CEF
0x180006d7c  mov     ebx, eax
0x180006d7e  jmp     loc_180006CF8
```

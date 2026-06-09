# GetUEFIVarAndUEFICRC(ushort const *,ushort const *,uchar *,uint,uchar *,uint)

- ea: `0x180041b80`
- end: `0x180041c5d`
- name: `?GetUEFIVarAndUEFICRC@@YAJPEBG0PEAEI1I@Z`
- size: `221`
- prototype: `__int64 __fastcall(LPCWSTR lpName, LPCWSTR, PVOID pBuffer, DWORD nSize, PVOID, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800414c4`
- `0x180041914`

## callees

- `0x180041b80`
- `0x180041c64`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180041bb7`
- `ntdll!RtlAcquirePrivilege` at `0x180041bb7`
- `ntdll!RtlReleasePrivilege` at `0x180041c4a`
- `ntdll!RtlReleasePrivilege` at `0x180041c4a`
- `ntdll!RtlNtStatusToDosError` at `0x180041c25`
- `ntdll!RtlNtStatusToDosError` at `0x180041c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041be6`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041bdc`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041c15`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041bdc`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041c15`

## pseudocode

```c
__int64 __fastcall GetUEFIVarAndUEFICRC(
        LPCWSTR lpName,
        LPCWSTR a2,
        PVOID pBuffer,
        DWORD nSize,
        PVOID pBuffera,
        unsigned int a6)
{
  int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  signed int LastError; // eax
  unsigned int v14; // ebx
  signed int v15; // eax
  PVOID ReturnedState; // [rsp+20h] [rbp-38h] BYREF

  a6 = 22;
  ReturnedState = 0;
  v10 = RtlAcquirePrivilege(&a6, 1u, 0, &ReturnedState);
  if ( (unsigned __int8)IsUEFIFW(v12, v11) )
  {
    if ( v10 >= 0 )
    {
      if ( GetFirmwareEnvironmentVariableW(lpName, L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}", pBuffer, nSize)
        && GetFirmwareEnvironmentVariableW(a2, L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}", pBuffera, 4u) )
      {
        v14 = 0;
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_11;
    }
    v15 = RtlNtStatusToDosError(v10);
    v14 = v15;
    if ( v15 > 0 )
      return (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v14 = -2147023091;
    if ( v10 >= 0 )
LABEL_11:
      RtlReleasePrivilege(ReturnedState);
  }
  return v14;
}

```

## disassembly

```asm
0x180041b80  mov     rax, rsp
0x180041b83  push    rbx
0x180041b84  push    rbp
0x180041b85  push    rsi
0x180041b86  push    rdi
0x180041b87  push    r14
0x180041b89  sub     rsp, 30h
0x180041b8d  mov     rbp, r8
0x180041b90  mov     dword ptr [rax+30h], 16h
0x180041b97  xor     r8d, r8d; Flags
0x180041b9a  mov     qword ptr [rax-38h], 0
0x180041ba2  mov     esi, r9d
0x180041ba5  mov     rbx, rdx
0x180041ba8  mov     r14, rcx
0x180041bab  lea     r9, [rax-38h]; ReturnedState
0x180041baf  lea     rcx, [rax+30h]; Privilege
0x180041bb3  lea     edx, [r8+1]; NumPriv
0x180041bb7  call    cs:__imp_RtlAcquirePrivilege
0x180041bbd  mov     edi, eax
0x180041bbf  call    IsUEFIFW
0x180041bc4  test    al, al
0x180041bc6  jz      short loc_180041C3C
0x180041bc8  test    edi, edi
0x180041bca  js      short loc_180041C23
0x180041bcc  mov     r9d, esi; nSize
0x180041bcf  lea     rdx, Guid; "{eaec226f-c9a3-477a-a826-ddc716cdc0e3}"
0x180041bd6  mov     r8, rbp; pBuffer
0x180041bd9  mov     rcx, r14; lpName
0x180041bdc  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180041be2  test    eax, eax
0x180041be4  jnz     short loc_180041BFD
0x180041be6  call    cs:__imp_GetLastError
0x180041bec  mov     ebx, eax
0x180041bee  test    eax, eax
0x180041bf0  jle     short loc_180041C45
0x180041bf2  movzx   ebx, ax
0x180041bf5  or      ebx, 80070000h
0x180041bfb  jmp     short loc_180041C45
0x180041bfd  mov     r8, [rsp+58h+pBuffer]; pBuffer
0x180041c05  lea     rdx, Guid; "{eaec226f-c9a3-477a-a826-ddc716cdc0e3}"
0x180041c0c  mov     r9d, 4; nSize
0x180041c12  mov     rcx, rbx; lpName
0x180041c15  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180041c1b  test    eax, eax
0x180041c1d  jz      short loc_180041BE6
0x180041c1f  xor     ebx, ebx
0x180041c21  jmp     short loc_180041C45
0x180041c23  mov     ecx, edi; Status
0x180041c25  call    cs:__imp_RtlNtStatusToDosError
0x180041c2b  mov     ebx, eax
0x180041c2d  test    eax, eax
0x180041c2f  jle     short loc_180041C50
0x180041c31  movzx   ebx, ax
0x180041c34  or      ebx, 80070000h
0x180041c3a  jmp     short loc_180041C50
0x180041c3c  mov     ebx, 8007070Dh
0x180041c41  test    edi, edi
0x180041c43  js      short loc_180041C50
0x180041c45  mov     rcx, [rsp+58h+ReturnedState]; ReturnedState
0x180041c4a  call    cs:__imp_RtlReleasePrivilege
0x180041c50  mov     eax, ebx
0x180041c52  add     rsp, 30h
0x180041c56  pop     r14
0x180041c58  pop     rdi
0x180041c59  pop     rsi
0x180041c5a  pop     rbp
0x180041c5b  pop     rbx
0x180041c5c  retn
```

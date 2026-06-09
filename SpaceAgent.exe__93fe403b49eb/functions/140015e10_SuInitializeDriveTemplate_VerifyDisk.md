# SuInitializeDriveTemplate_VerifyDisk

- ea: `0x140015e10`
- end: `0x140015f10`
- name: `SuInitializeDriveTemplate_VerifyDisk`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015b5c`

## callees

- `0x14001480c`
- `0x140015e10`
- `0x140015f18`
- `0x140019d88`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140015ed9`
- `KERNEL32!LocalFree` at `0x140015ed9`
- `KERNEL32!SetLastError` at `0x140015e9c`
- `KERNEL32!SetLastError` at `0x140015efa`
- `KERNEL32!SetLastError` at `0x140015e9c`
- `KERNEL32!SetLastError` at `0x140015efa`
- `KERNEL32!GetLastError` at `0x140015e59`
- `KERNEL32!GetLastError` at `0x140015ec4`
- `KERNEL32!GetLastError` at `0x140015eed`
- `KERNEL32!GetLastError` at `0x140015e59`
- `KERNEL32!GetLastError` at `0x140015ec4`
- `KERNEL32!GetLastError` at `0x140015eed`

## pseudocode

```c
__int64 __fastcall SuInitializeDriveTemplate_VerifyDisk(int a1, int a2, BOOL *a3)
{
  unsigned int DiskPath; // ebx
  BOOL v6; // edi
  DWORD v7; // ecx
  DWORD LastError; // esi
  HLOCAL v9; // rax
  int v11; // [rsp+20h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-20h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF
  int v14; // [rsp+68h] [rbp+20h] BYREF

  hMem = 0;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  DiskPath = SuGetDiskPath(a2, 0, (unsigned __int16 **)&hMem);
  if ( DiskPath )
  {
    v6 = 1;
    DiskPath = SuIsDiskCandidate((const unsigned __int16 *)hMem, &v13, &v14, &v11);
    if ( !DiskPath )
      goto LABEL_12;
    if ( !v13 )
    {
      v7 = 87;
LABEL_6:
      DiskPath = 0;
      v6 = 0;
      SetLastError(v7);
      goto LABEL_12;
    }
    if ( v14 )
    {
      if ( !a1 )
      {
        v7 = 85;
        goto LABEL_6;
      }
    }
    else if ( !a1 )
    {
      goto LABEL_12;
    }
    DiskPath = CleanDisk((const unsigned __int16 *)hMem);
    goto LABEL_12;
  }
  v6 = GetLastError() != 2;
LABEL_12:
  LastError = GetLastError();
  if ( hMem )
  {
    v9 = LocalFree(hMem);
    if ( DiskPath )
    {
      DiskPath = v9 == 0;
      LastError = GetLastError();
    }
  }
  *a3 = v6;
  SetLastError(LastError);
  return DiskPath;
}

```

## disassembly

```asm
0x140015e10  mov     [rsp+arg_0], rbx
0x140015e15  push    rsi
0x140015e16  push    rdi
0x140015e17  push    r14
0x140015e19  sub     rsp, 30h
0x140015e1d  mov     eax, edx
0x140015e1f  mov     [rsp+48h+hMem], 0
0x140015e28  mov     r14, r8
0x140015e2b  mov     [rsp+48h+arg_10], 0
0x140015e33  mov     esi, ecx
0x140015e35  mov     [rsp+48h+arg_18], 0
0x140015e3d  mov     ecx, eax; unsigned int
0x140015e3f  mov     [rsp+48h+var_28], 0
0x140015e47  lea     r8, [rsp+48h+hMem]; unsigned __int16 **
0x140015e4c  xor     edx, edx; int
0x140015e4e  call    ?SuGetDiskPath@@YAHKHPEAPEAG@Z; SuGetDiskPath(ulong,int,ushort * *)
0x140015e53  mov     ebx, eax
0x140015e55  test    eax, eax
0x140015e57  jnz     short loc_140015E6A
0x140015e59  call    cs:__imp_GetLastError
0x140015e5f  xor     edi, edi
0x140015e61  cmp     eax, 2
0x140015e64  setnz   dil
0x140015e68  jmp     short loc_140015EC4
0x140015e6a  mov     rcx, [rsp+48h+hMem]; unsigned __int16 *
0x140015e6f  lea     r9, [rsp+48h+var_28]; int *
0x140015e74  lea     r8, [rsp+48h+arg_18]; int *
0x140015e79  mov     edi, 1
0x140015e7e  lea     rdx, [rsp+48h+arg_10]; int *
0x140015e83  call    ?SuIsDiskCandidate@@YAHPEBGPEAH11@Z; SuIsDiskCandidate(ushort const *,int *,int *,int *)
0x140015e88  mov     ebx, eax
0x140015e8a  test    eax, eax
0x140015e8c  jz      short loc_140015EC4
0x140015e8e  cmp     [rsp+48h+arg_10], 0
0x140015e93  jnz     short loc_140015EA4
0x140015e95  lea     ecx, [rdi+56h]; dwErrCode
0x140015e98  xor     ebx, ebx
0x140015e9a  xor     edi, edi
0x140015e9c  call    cs:__imp_SetLastError
0x140015ea2  jmp     short loc_140015EC4
0x140015ea4  cmp     [rsp+48h+arg_18], 0
0x140015ea9  jz      short loc_140015EB4
0x140015eab  test    esi, esi
0x140015ead  jnz     short loc_140015EB8
0x140015eaf  lea     ecx, [rsi+55h]
0x140015eb2  jmp     short loc_140015E98
0x140015eb4  test    esi, esi
0x140015eb6  jz      short loc_140015EC4
0x140015eb8  mov     rcx, [rsp+48h+hMem]; unsigned __int16 *
0x140015ebd  call    ?CleanDisk@@YAHPEBGHH@Z; CleanDisk(ushort const *,int,int)
0x140015ec2  mov     ebx, eax
0x140015ec4  call    cs:__imp_GetLastError
0x140015eca  cmp     [rsp+48h+hMem], 0
0x140015ed0  mov     esi, eax
0x140015ed2  jz      short loc_140015EF5
0x140015ed4  mov     rcx, [rsp+48h+hMem]; hMem
0x140015ed9  call    cs:__imp_LocalFree
0x140015edf  xor     ecx, ecx
0x140015ee1  test    rax, rax
0x140015ee4  setz    cl
0x140015ee7  test    ebx, ebx
0x140015ee9  jz      short loc_140015EF5
0x140015eeb  mov     ebx, ecx
0x140015eed  call    cs:__imp_GetLastError
0x140015ef3  mov     esi, eax
0x140015ef5  mov     ecx, esi; dwErrCode
0x140015ef7  mov     [r14], edi
0x140015efa  call    cs:__imp_SetLastError
0x140015f00  mov     eax, ebx
0x140015f02  mov     rbx, [rsp+48h+arg_0]
0x140015f07  add     rsp, 30h
0x140015f0b  pop     r14
0x140015f0d  pop     rdi
0x140015f0e  pop     rsi
0x140015f0f  retn
```

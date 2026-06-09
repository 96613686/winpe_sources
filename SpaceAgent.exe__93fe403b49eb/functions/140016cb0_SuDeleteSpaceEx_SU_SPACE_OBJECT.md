# SuDeleteSpaceEx(_SU_SPACE_OBJECT *)

- ea: `0x140016cb0`
- end: `0x140016d5b`
- name: `?SuDeleteSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(struct _SU_SPACE_OBJECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140016bc4`
- `0x140018cfc`

## callees

- `0x14001297c`
- `0x14001480c`
- `0x140016cb0`
- `0x14001a24c`
- `0x14001ccc4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140016d2a`
- `KERNEL32!LocalFree` at `0x140016d2a`
- `KERNEL32!SetLastError` at `0x140016d48`
- `KERNEL32!SetLastError` at `0x140016d48`
- `KERNEL32!GetLastError` at `0x140016cde`
- `KERNEL32!GetLastError` at `0x140016d15`
- `KERNEL32!GetLastError` at `0x140016d3e`
- `KERNEL32!GetLastError` at `0x140016cde`
- `KERNEL32!GetLastError` at `0x140016d15`
- `KERNEL32!GetLastError` at `0x140016d3e`

## pseudocode

```c
__int64 __fastcall SuDeleteSpaceEx(struct _SU_SPACE_OBJECT *a1)
{
  unsigned int DiskPath; // ebx
  DWORD LastError; // edi
  HLOCAL v4; // rax
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  hMem = 0;
  DiskPath = SuGetDiskPath(*((_DWORD *)a1 + 669), 0, (unsigned __int16 **)&hMem);
  if ( DiskPath )
  {
    DiskPath = Disk_UninstallVolumes(hMem);
    if ( DiskPath )
    {
      DiskPath = UninstallDevice((PCWSTR)hMem);
      if ( DiskPath )
        goto LABEL_6;
    }
  }
  else if ( GetLastError() == 2 )
  {
LABEL_6:
    DiskPath = SuDeleteSpace(a1);
  }
  LastError = GetLastError();
  if ( hMem )
  {
    v4 = LocalFree(hMem);
    if ( DiskPath )
    {
      DiskPath = v4 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return DiskPath;
}

```

## disassembly

```asm
0x140016cb0  mov     [rsp+arg_8], rbx
0x140016cb5  push    rdi
0x140016cb6  sub     rsp, 20h
0x140016cba  mov     rdi, rcx
0x140016cbd  mov     [rsp+28h+hMem], 0
0x140016cc6  mov     ecx, [rcx+0A74h]; unsigned int
0x140016ccc  lea     r8, [rsp+28h+hMem]; unsigned __int16 **
0x140016cd1  xor     edx, edx; int
0x140016cd3  call    ?SuGetDiskPath@@YAHKHPEAPEAG@Z; SuGetDiskPath(ulong,int,ushort * *)
0x140016cd8  mov     ebx, eax
0x140016cda  test    eax, eax
0x140016cdc  jnz     short loc_140016CEB
0x140016cde  call    cs:__imp_GetLastError
0x140016ce4  cmp     eax, 2
0x140016ce7  jnz     short loc_140016D15
0x140016ce9  jmp     short loc_140016D0B
0x140016ceb  mov     rcx, [rsp+28h+hMem]
0x140016cf0  call    Disk_UninstallVolumes
0x140016cf5  mov     ebx, eax
0x140016cf7  test    eax, eax
0x140016cf9  jz      short loc_140016D15
0x140016cfb  mov     rcx, [rsp+28h+hMem]; DevicePath
0x140016d00  call    ?UninstallDevice@@YAHPEBG@Z; UninstallDevice(ushort const *)
0x140016d05  mov     ebx, eax
0x140016d07  test    eax, eax
0x140016d09  jz      short loc_140016D15
0x140016d0b  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140016d0e  call    ?SuDeleteSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuDeleteSpace(_SU_SPACE_OBJECT *)
0x140016d13  mov     ebx, eax
0x140016d15  call    cs:__imp_GetLastError
0x140016d1b  cmp     [rsp+28h+hMem], 0
0x140016d21  mov     edi, eax
0x140016d23  jz      short loc_140016D46
0x140016d25  mov     rcx, [rsp+28h+hMem]; hMem
0x140016d2a  call    cs:__imp_LocalFree
0x140016d30  xor     ecx, ecx
0x140016d32  test    rax, rax
0x140016d35  setz    cl
0x140016d38  test    ebx, ebx
0x140016d3a  jz      short loc_140016D46
0x140016d3c  mov     ebx, ecx
0x140016d3e  call    cs:__imp_GetLastError
0x140016d44  mov     edi, eax
0x140016d46  mov     ecx, edi; dwErrCode
0x140016d48  call    cs:__imp_SetLastError
0x140016d4e  mov     eax, ebx
0x140016d50  mov     rbx, [rsp+28h+arg_8]
0x140016d55  add     rsp, 20h
0x140016d59  pop     rdi
0x140016d5a  retn
```

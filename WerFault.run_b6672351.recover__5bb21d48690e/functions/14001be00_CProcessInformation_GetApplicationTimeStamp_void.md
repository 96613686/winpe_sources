# CProcessInformation::GetApplicationTimeStamp(void)

- ea: `0x14001be00`
- end: `0x14001bea2`
- name: `?GetApplicationTimeStamp@CProcessInformation@@QEAAKXZ`
- size: `162`
- prototype: `unsigned int __fastcall(CProcessInformation *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002b5d8`
- `0x14002bb50`

## callees

- `0x140011b44`
- `0x140014ee4`
- `0x14001b1b4`
- `0x14001be00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001be88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001be88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001be51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001be51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001be6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001be6c`

## pseudocode

```c
__int64 __fastcall CProcessInformation::GetApplicationTimeStamp(CProcessInformation *this)
{
  const WCHAR *v1; // rax
  unsigned int TimestampModule; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  HINSTANCE v5; // rbx
  HANDLE CurrentProcess; // rax

  v1 = CProcessInformation::AppFileName(this);
  if ( v1 )
  {
    TimestampModule = 0;
    Library = LoadLibraryExW(v1, 0, 2u);
    v4 = Library;
    if ( Library )
    {
      v5 = (HINSTANCE)((unsigned __int64)Library & 0xFFFFFFFFFFFFFFFCuLL);
      CurrentProcess = GetCurrentProcess();
      TimestampModule = UtilGetTimestampModule(CurrentProcess, v5);
      FreeLibrary(v4);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
    return 0;
  }
  return TimestampModule;
}

```

## disassembly

```asm
0x14001be00  mov     [rsp+arg_0], rbx
0x14001be05  push    rdi
0x14001be06  sub     rsp, 20h
0x14001be0a  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x14001be0f  test    rax, rax
0x14001be12  jnz     short loc_14001BE46
0x14001be14  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be1b  lea     rax, WPP_GLOBAL_Control
0x14001be22  cmp     rcx, rax
0x14001be25  jz      short loc_14001BE42
0x14001be27  test    byte ptr [rcx+1Ch], 1
0x14001be2b  jz      short loc_14001BE42
0x14001be2d  mov     rcx, [rcx+10h]
0x14001be31  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14001be38  mov     edx, 42h ; 'B'
0x14001be3d  call    WPP_SF_
0x14001be42  xor     ebx, ebx
0x14001be44  jmp     short loc_14001BE94
0x14001be46  xor     ebx, ebx
0x14001be48  xor     edx, edx; hFile
0x14001be4a  mov     rcx, rax; lpLibFileName
0x14001be4d  lea     r8d, [rbx+2]; dwFlags
0x14001be51  call    cs:__imp_LoadLibraryExW
0x14001be58  nop     dword ptr [rax+rax+00h]
0x14001be5d  mov     rdi, rax
0x14001be60  test    rax, rax
0x14001be63  jz      short loc_14001BE94
0x14001be65  mov     rbx, rax
0x14001be68  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14001be6c  call    cs:__imp_GetCurrentProcess
0x14001be73  nop     dword ptr [rax+rax+00h]
0x14001be78  mov     rcx, rax; hProcess
0x14001be7b  mov     rdx, rbx; lpBaseAddress
0x14001be7e  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x14001be83  mov     rcx, rdi; hLibModule
0x14001be86  mov     ebx, eax
0x14001be88  call    cs:__imp_FreeLibrary
0x14001be8f  nop     dword ptr [rax+rax+00h]
0x14001be94  mov     eax, ebx
0x14001be96  mov     rbx, [rsp+28h+arg_0]
0x14001be9b  add     rsp, 20h
0x14001be9f  pop     rdi
0x14001bea0  retn
```

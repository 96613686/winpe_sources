# CProcessInformation::GetApplicationTimeStamp(void)

- ea: `0x14001adc8`
- end: `0x14001ae57`
- name: `?GetApplicationTimeStamp@CProcessInformation@@QEAAKXZ`
- size: `143`
- prototype: `unsigned int __fastcall(CProcessInformation *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140029a14`
- `0x140029f8c`

## callees

- `0x1400113ec`
- `0x14001444c`
- `0x14001a1d4`
- `0x14001adc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001ae44`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001ae44`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001ae19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001ae19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ae2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ae2e`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
    return 0;
  }
  return TimestampModule;
}

```

## disassembly

```asm
0x14001adc8  mov     [rsp+arg_0], rbx
0x14001adcd  push    rdi
0x14001adce  sub     rsp, 20h
0x14001add2  call    ?AppFileName@CProcessInformation@@AEAAPEB_WXZ; CProcessInformation::AppFileName(void)
0x14001add7  test    rax, rax
0x14001adda  jnz     short loc_14001AE0E
0x14001addc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ade3  lea     rax, WPP_GLOBAL_Control
0x14001adea  cmp     rcx, rax
0x14001aded  jz      short loc_14001AE0A
0x14001adef  test    byte ptr [rcx+1Ch], 1
0x14001adf3  jz      short loc_14001AE0A
0x14001adf5  mov     rcx, [rcx+10h]
0x14001adf9  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001ae00  mov     edx, 42h ; 'B'
0x14001ae05  call    WPP_SF_
0x14001ae0a  xor     ebx, ebx
0x14001ae0c  jmp     short loc_14001AE4A
0x14001ae0e  xor     ebx, ebx
0x14001ae10  xor     edx, edx; hFile
0x14001ae12  mov     rcx, rax; lpLibFileName
0x14001ae15  lea     r8d, [rbx+2]; dwFlags
0x14001ae19  call    cs:__imp_LoadLibraryExW
0x14001ae1f  mov     rdi, rax
0x14001ae22  test    rax, rax
0x14001ae25  jz      short loc_14001AE4A
0x14001ae27  mov     rbx, rax
0x14001ae2a  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14001ae2e  call    cs:__imp_GetCurrentProcess
0x14001ae34  mov     rcx, rax; hProcess
0x14001ae37  mov     rdx, rbx; lpBaseAddress
0x14001ae3a  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x14001ae3f  mov     rcx, rdi; hLibModule
0x14001ae42  mov     ebx, eax
0x14001ae44  call    cs:__imp_FreeLibrary
0x14001ae4a  mov     eax, ebx
0x14001ae4c  mov     rbx, [rsp+28h+arg_0]
0x14001ae51  add     rsp, 20h
0x14001ae55  pop     rdi
0x14001ae56  retn
```

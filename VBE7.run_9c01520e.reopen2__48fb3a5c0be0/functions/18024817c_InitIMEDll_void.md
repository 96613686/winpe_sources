# InitIMEDll(void)

- ea: `0x18024817c`
- end: `0x18024835e`
- name: `?InitIMEDll@@YAXXZ`
- size: `482`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180100c18`

## callees

- `0x180024478`
- `0x18024817c`
- `0x18024845c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcat_s` at `0x1802481c6`
- `MSVCR100!strcat_s` at `0x1802481c6`
- `KERNEL32!FreeLibrary` at `0x180248240`
- `KERNEL32!FreeLibrary` at `0x180248331`
- `KERNEL32!FreeLibrary` at `0x180248240`
- `KERNEL32!FreeLibrary` at `0x180248331`
- `KERNEL32!GetProcAddress` at `0x180248222`
- `KERNEL32!GetProcAddress` at `0x1802482fb`
- `KERNEL32!GetProcAddress` at `0x180248222`
- `KERNEL32!GetProcAddress` at `0x1802482fb`
- `KERNEL32!SetErrorMode` at `0x1802481e3`
- `KERNEL32!SetErrorMode` at `0x180248204`
- `KERNEL32!SetErrorMode` at `0x180248256`
- `KERNEL32!SetErrorMode` at `0x18024829f`
- `KERNEL32!SetErrorMode` at `0x1802481e3`
- `KERNEL32!SetErrorMode` at `0x180248204`
- `KERNEL32!SetErrorMode` at `0x180248256`
- `KERNEL32!SetErrorMode` at `0x18024829f`
- `KERNEL32!GetSystemDirectoryA` at `0x1802481a6`
- `KERNEL32!GetSystemDirectoryA` at `0x1802481a6`

## string_xrefs

- `0x1802481ed`: `USER32.DLL`
- `0x180248260`: `IMM32.DLL`

## pseudocode

```c
void InitIMEDll(void)
{
  int i; // [rsp+20h] [rbp-1040h]
  UINT uModea; // [rsp+24h] [rbp-103Ch]
  UINT uMode; // [rsp+24h] [rbp-103Ch]
  FARPROC ProcAddress; // [rsp+28h] [rbp-1038h]
  CHAR Buffer[2064]; // [rsp+30h] [rbp-1030h] BYREF
  char v5[2064]; // [rsp+840h] [rbp-820h] BYREF

  if ( GetSystemDirectoryA(Buffer, 0x801u) && !strcat_s(Buffer, 0x801u, "\\") )
  {
    if ( g_fChicago )
    {
      uModea = SetErrorMode(0x8000u);
      g_hWINNLSLib = (HMODULE)IsolationAwareLoadLibraryA("USER32.DLL");
      SetErrorMode(uModea);
      if ( g_hWINNLSLib )
      {
        pIMEMsgEx = (__int64)GetProcAddress(g_hWINNLSLib, "SendIMEMessageExA");
        if ( !pIMEMsgEx )
        {
          FreeLibrary(g_hWINNLSLib);
          g_hWINNLSLib = 0;
        }
      }
    }
    uMode = SetErrorMode(0x8000u);
    if ( (unsigned int)BuildPath(v5, 0x801u, Buffer, "IMM32.DLL") )
    {
      g_hIMM32Lib = (HMODULE)IsolationAwareLoadLibraryA(v5);
      SetErrorMode(uMode);
      if ( g_hIMM32Lib )
      {
        for ( i = 0; off_1803BB640[2 * i]; ++i )
        {
          ProcAddress = GetProcAddress(g_hIMM32Lib, (LPCSTR)off_1803BB640[2 * i + 1]);
          *(_QWORD *)off_1803BB640[2 * i] = ProcAddress;
          if ( !ProcAddress )
          {
            FreeLibrary(g_hIMM32Lib);
            g_hIMM32Lib = 0;
            return;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18024817c  push    rbp
0x18024817e  mov     rbp, rsp
0x180248181  mov     eax, 1060h
0x180248186  call    _alloca_probe
0x18024818b  sub     rsp, rax
0x18024818e  mov     rax, cs:__security_cookie
0x180248195  xor     rax, rsp
0x180248198  mov     [rbp+var_10], rax
0x18024819c  mov     edx, 801h; uSize
0x1802481a1  lea     rcx, [rsp+1060h+Buffer]; lpBuffer
0x1802481a6  call    cs:__imp_GetSystemDirectoryA
0x1802481ac  test    eax, eax
0x1802481ae  jnz     short loc_1802481B5
0x1802481b0  jmp     loc_180248349
0x1802481b5  lea     r8, asc_1803A109C; "\\"
0x1802481bc  mov     edx, 801h; SizeInBytes
0x1802481c1  lea     rcx, [rsp+1060h+Buffer]; Destination
0x1802481c6  call    cs:__imp_strcat_s
0x1802481cc  test    eax, eax
0x1802481ce  jz      short loc_1802481D5
0x1802481d0  jmp     loc_180248349
0x1802481d5  cmp     cs:g_fChicago, 0
0x1802481dc  jz      short loc_180248251
0x1802481de  mov     ecx, 8000h; uMode
0x1802481e3  call    cs:__imp_SetErrorMode
0x1802481e9  mov     [rsp+1060h+uMode], eax
0x1802481ed  lea     rcx, aUser32Dll_1; "USER32.DLL"
0x1802481f4  call    IsolationAwareLoadLibraryA
0x1802481f9  mov     cs:?g_hWINNLSLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWINNLSLib
0x180248200  mov     ecx, [rsp+1060h+uMode]; uMode
0x180248204  call    cs:__imp_SetErrorMode
0x18024820a  cmp     cs:?g_hWINNLSLib@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hWINNLSLib
0x180248212  jz      short loc_180248251
0x180248214  lea     rdx, aSendimemessage; "SendIMEMessageExA"
0x18024821b  mov     rcx, cs:?g_hWINNLSLib@@3PEAUHINSTANCE__@@EA; hModule
0x180248222  call    cs:__imp_GetProcAddress
0x180248228  mov     cs:pIMEMsgEx, rax
0x18024822f  cmp     cs:pIMEMsgEx, 0
0x180248237  jnz     short loc_180248251
0x180248239  mov     rcx, cs:?g_hWINNLSLib@@3PEAUHINSTANCE__@@EA; hLibModule
0x180248240  call    cs:__imp_FreeLibrary
0x180248246  mov     cs:?g_hWINNLSLib@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hWINNLSLib
0x180248251  mov     ecx, 8000h; uMode
0x180248256  call    cs:__imp_SetErrorMode
0x18024825c  mov     [rsp+1060h+uMode], eax
0x180248260  lea     r9, aImm32Dll; "IMM32.DLL"
0x180248267  lea     r8, [rsp+1060h+Buffer]; char *
0x18024826c  mov     edx, 801h; unsigned __int64
0x180248271  lea     rcx, [rsp+1060h+var_820]; char *
0x180248279  call    ?BuildPath@@YAHPEAD_KPEBD2@Z; BuildPath(char *,unsigned __int64,char const *,char const *)
0x18024827e  test    eax, eax
0x180248280  jnz     short loc_180248287
0x180248282  jmp     loc_180248349
0x180248287  lea     rcx, [rsp+1060h+var_820]
0x18024828f  call    IsolationAwareLoadLibraryA
0x180248294  mov     cs:g_hIMM32Lib, rax
0x18024829b  mov     ecx, [rsp+1060h+uMode]; uMode
0x18024829f  call    cs:__imp_SetErrorMode
0x1802482a5  cmp     cs:g_hIMM32Lib, 0
0x1802482ad  jnz     short loc_1802482B4
0x1802482af  jmp     loc_180248349
0x1802482b4  mov     [rsp+1060h+var_1040], 0
0x1802482bc  jmp     short loc_1802482C8
0x1802482be  mov     eax, [rsp+1060h+var_1040]
0x1802482c2  inc     eax
0x1802482c4  mov     [rsp+1060h+var_1040], eax
0x1802482c8  movsxd  rax, [rsp+1060h+var_1040]
0x1802482cd  imul    rax, 10h
0x1802482d1  lea     rcx, off_1803BB640
0x1802482d8  cmp     qword ptr [rcx+rax], 0
0x1802482dd  jz      short loc_180248349
0x1802482df  movsxd  rax, [rsp+1060h+var_1040]
0x1802482e4  imul    rax, 10h
0x1802482e8  lea     rcx, off_1803BB640
0x1802482ef  mov     rdx, [rcx+rax+8]; lpProcName
0x1802482f4  mov     rcx, cs:g_hIMM32Lib; hModule
0x1802482fb  call    cs:__imp_GetProcAddress
0x180248301  mov     [rsp+1060h+var_1038], rax
0x180248306  movsxd  rax, [rsp+1060h+var_1040]
0x18024830b  imul    rax, 10h
0x18024830f  lea     rcx, off_1803BB640
0x180248316  mov     rax, [rcx+rax]
0x18024831a  mov     rcx, [rsp+1060h+var_1038]
0x18024831f  mov     [rax], rcx
0x180248322  cmp     [rsp+1060h+var_1038], 0
0x180248328  jnz     short loc_180248344
0x18024832a  mov     rcx, cs:g_hIMM32Lib; hLibModule
0x180248331  call    cs:__imp_FreeLibrary
0x180248337  mov     cs:g_hIMM32Lib, 0
0x180248342  jmp     short loc_180248349
0x180248344  jmp     loc_1802482BE
0x180248349  mov     rcx, [rbp+var_10]
0x18024834d  xor     rcx, rsp; StackCookie
0x180248350  call    __security_check_cookie
0x180248355  add     rsp, 1060h
0x18024835c  pop     rbp
0x18024835d  retn
```

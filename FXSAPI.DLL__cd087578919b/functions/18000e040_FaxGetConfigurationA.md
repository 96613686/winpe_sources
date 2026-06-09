# FaxGetConfigurationA

- ea: `0x18000e040`
- end: `0x18000e164`
- name: `FaxGetConfigurationA`
- size: `292`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, PFAX_CONFIGURATIONA *FaxConfig)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000e040`
- `0x18000e170`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e0b6`
- `KERNEL32!GetLastError` at `0x18000e110`
- `KERNEL32!GetLastError` at `0x18000e0b6`
- `KERNEL32!GetLastError` at `0x18000e110`

## pseudocode

```c
BOOL __stdcall FaxGetConfigurationA(HANDLE FaxHandle, PFAX_CONFIGURATIONA *FaxConfig)
{
  DWORD LastError; // eax
  DWORD v6; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !FaxGetConfigurationW(FaxHandle, (PFAX_CONFIGURATIONW *)FaxConfig) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    return 0;
  }
  if ( !(unsigned int)ConvertUnicodeStringInPlace((LPCWCH)(*FaxConfig)->ArchiveDirectory) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v6);
    }
    pMemFree(*FaxConfig);
    return 0;
  }
  (*FaxConfig)->SizeOfStruct = 64;
  return 1;
}

```

## disassembly

```asm
0x18000e040  mov     [rsp+arg_0], rbx
0x18000e045  mov     [rsp+arg_8], rbp
0x18000e04a  push    rdi
0x18000e04b  sub     rsp, 20h
0x18000e04f  mov     rbx, rdx
0x18000e052  mov     rdi, rcx
0x18000e055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e05c  lea     rbp, WPP_GLOBAL_Control
0x18000e063  cmp     rcx, rbp
0x18000e066  jz      short loc_18000E08C
0x18000e068  test    dword ptr [rcx+1Ch], 1000h
0x18000e06f  jz      short loc_18000E08C
0x18000e071  cmp     byte ptr [rcx+19h], 5
0x18000e075  jb      short loc_18000E08C
0x18000e077  mov     rcx, [rcx+10h]
0x18000e07b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e082  mov     edx, 0Fh
0x18000e087  call    WPP_SF_
0x18000e08c  mov     rdx, rbx; FaxConfig
0x18000e08f  mov     rcx, rdi; FaxHandle
0x18000e092  call    FaxGetConfigurationW
0x18000e097  test    eax, eax
0x18000e099  jnz     short loc_18000E0E5
0x18000e09b  mov     rax, cs:WPP_GLOBAL_Control
0x18000e0a2  cmp     rax, rbp
0x18000e0a5  jz      short loc_18000E0E1
0x18000e0a7  test    dword ptr [rax+1Ch], 1000h
0x18000e0ae  jz      short loc_18000E0E1
0x18000e0b0  cmp     byte ptr [rax+19h], 2
0x18000e0b4  jb      short loc_18000E0E1
0x18000e0b6  call    cs:__imp_GetLastError
0x18000e0bd  nop     dword ptr [rax+rax+00h]
0x18000e0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0c9  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e0d0  mov     edx, 10h
0x18000e0d5  mov     r9d, eax
0x18000e0d8  mov     rcx, [rcx+10h]
0x18000e0dc  call    WPP_SF_d
0x18000e0e1  xor     eax, eax
0x18000e0e3  jmp     short loc_18000E153
0x18000e0e5  mov     rcx, [rbx]
0x18000e0e8  mov     rcx, [rcx+30h]; lpWideCharStr
0x18000e0ec  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000e0f1  test    eax, eax
0x18000e0f3  jnz     short loc_18000E145
0x18000e0f5  mov     rax, cs:WPP_GLOBAL_Control
0x18000e0fc  cmp     rax, rbp
0x18000e0ff  jz      short loc_18000E13B
0x18000e101  test    dword ptr [rax+1Ch], 1000h
0x18000e108  jz      short loc_18000E13B
0x18000e10a  cmp     byte ptr [rax+19h], 2
0x18000e10e  jb      short loc_18000E13B
0x18000e110  call    cs:__imp_GetLastError
0x18000e117  nop     dword ptr [rax+rax+00h]
0x18000e11c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e123  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e12a  mov     edx, 11h
0x18000e12f  mov     r9d, eax
0x18000e132  mov     rcx, [rcx+10h]
0x18000e136  call    WPP_SF_d
0x18000e13b  mov     rcx, [rbx]; lpMem
0x18000e13e  call    pMemFree
0x18000e143  jmp     short loc_18000E0E1
0x18000e145  mov     rax, [rbx]
0x18000e148  mov     dword ptr [rax], 40h ; '@'
0x18000e14e  mov     eax, 1
0x18000e153  mov     rbx, [rsp+28h+arg_0]
0x18000e158  mov     rbp, [rsp+28h+arg_8]
0x18000e15d  add     rsp, 20h
0x18000e161  pop     rdi
0x18000e162  retn
```

# CWorkspaceManager::GetStartMenuBaseFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002fa8c`
- end: `0x18002fc5f`
- name: `?GetStartMenuBaseFolder@CWorkspaceManager@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002a070`
- `0x18002b1a8`

## callees

- `0x18000b1d8`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18002fa8c`
- `0x18009a520`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002fc36`
- `ole32!CoTaskMemFree` at `0x18002fc36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbb4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002fb4d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002fb4d`
- `SHELL32!SHGetKnownFolderPath` at `0x18002facb`
- `SHELL32!SHGetKnownFolderPath` at `0x18002facb`

## string_xrefs

- `0x18002fb07`: `SHGetKnownFolderPath failed`

## pseudocode

```c
__int64 __fastcall CWorkspaceManager::GetStartMenuBaseFolder(__int64 a1)
{
  int v2; // ebx
  unsigned int v3; // eax
  DWORD v4; // eax
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  signed int v8; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // [rsp+28h] [rbp-240h]
  PWSTR ppszPath; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-228h] BYREF

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_Programs, 0x8000u, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    v4 = ExpandEnvironmentStringsW(ppszPath, Dst, 0x104u);
    if ( v4 )
    {
      if ( v4 <= 0x104 )
      {
        std::wstring::assign(a1, Dst);
        v2 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            78,
            WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            CurrentThreadActivityIdPrefix,
            -2147418113);
        }
        v2 = -2147418113;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v7, v6);
      }
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v3,
      (__int64)"SHGetKnownFolderPath failed",
      v11);
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002fa8c  mov     [rsp+arg_8], rbx
0x18002fa91  push    rdi
0x18002fa92  sub     rsp, 260h
0x18002fa99  mov     rax, cs:__security_cookie
0x18002faa0  xor     rax, rsp
0x18002faa3  mov     [rsp+268h+var_18], rax
0x18002faab  mov     rdi, rcx
0x18002faae  mov     [rsp+268h+ppszPath], 0
0x18002fab7  lea     rcx, FOLDERID_Programs; rfid
0x18002fabe  xor     r8d, r8d; hToken
0x18002fac1  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x18002fac6  mov     edx, 8000h; dwFlags
0x18002facb  call    cs:__imp_SHGetKnownFolderPath
0x18002fad1  mov     ebx, eax
0x18002fad3  test    eax, eax
0x18002fad5  jns     short loc_18002FB3B
0x18002fad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fade  lea     rax, WPP_GLOBAL_Control
0x18002fae5  cmp     rcx, rax
0x18002fae8  jz      loc_18002FC2C
0x18002faee  test    byte ptr [rcx+1Ch], 8
0x18002faf2  jz      loc_18002FC2C
0x18002faf8  cmp     byte ptr [rcx+19h], 2
0x18002fafc  jb      loc_18002FC2C
0x18002fb02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fb07  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath failed"
0x18002fb0e  mov     [rsp+268h+var_240], ebx
0x18002fb12  mov     [rsp+268h+var_248], rcx
0x18002fb17  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002fb1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb25  mov     edx, 4Ch ; 'L'
0x18002fb2a  mov     r9d, eax
0x18002fb2d  mov     rcx, [rcx+10h]
0x18002fb31  call    WPP_SF_DsD
0x18002fb36  jmp     loc_18002FC2C
0x18002fb3b  mov     rcx, [rsp+268h+ppszPath]; lpSrc
0x18002fb40  lea     rdx, [rsp+268h+Dst]; lpDst
0x18002fb45  mov     ebx, 104h
0x18002fb4a  mov     r8d, ebx; nSize
0x18002fb4d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002fb53  test    eax, eax
0x18002fb55  jnz     short loc_18002FBC7
0x18002fb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb5e  lea     rax, WPP_GLOBAL_Control
0x18002fb65  mov     edi, 80070000h
0x18002fb6a  cmp     rcx, rax
0x18002fb6d  jz      short loc_18002FBB4
0x18002fb6f  test    byte ptr [rcx+1Ch], 8
0x18002fb73  jz      short loc_18002FBB4
0x18002fb75  cmp     byte ptr [rcx+19h], 2
0x18002fb79  jb      short loc_18002FBB4
0x18002fb7b  call    cs:__imp_GetLastError
0x18002fb81  mov     ebx, eax
0x18002fb83  test    eax, eax
0x18002fb85  jle     short loc_18002FB8C
0x18002fb87  movzx   ebx, ax
0x18002fb8a  or      ebx, edi
0x18002fb8c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb98  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002fb9f  mov     edx, 4Dh ; 'M'
0x18002fba4  mov     dword ptr [rsp+268h+var_248], ebx
0x18002fba8  mov     r9d, eax
0x18002fbab  mov     rcx, [rcx+10h]
0x18002fbaf  call    WPP_SF_Dd
0x18002fbb4  call    cs:__imp_GetLastError
0x18002fbba  mov     ebx, eax
0x18002fbbc  test    eax, eax
0x18002fbbe  jle     short loc_18002FC2C
0x18002fbc0  movzx   ebx, ax
0x18002fbc3  or      ebx, edi
0x18002fbc5  jmp     short loc_18002FC2C
0x18002fbc7  cmp     eax, ebx
0x18002fbc9  jbe     short loc_18002FC1D
0x18002fbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbd2  lea     rax, WPP_GLOBAL_Control
0x18002fbd9  cmp     rcx, rax
0x18002fbdc  jz      short loc_18002FC16
0x18002fbde  test    byte ptr [rcx+1Ch], 8
0x18002fbe2  jz      short loc_18002FC16
0x18002fbe4  cmp     byte ptr [rcx+19h], 2
0x18002fbe8  jb      short loc_18002FC16
0x18002fbea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbf6  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002fbfd  mov     edx, 4Eh ; 'N'
0x18002fc02  mov     dword ptr [rsp+268h+var_248], 8000FFFFh
0x18002fc0a  mov     r9d, eax
0x18002fc0d  mov     rcx, [rcx+10h]
0x18002fc11  call    WPP_SF_Dd
0x18002fc16  mov     ebx, 8000FFFFh
0x18002fc1b  jmp     short loc_18002FC2C
0x18002fc1d  lea     rdx, [rsp+268h+Dst]
0x18002fc22  mov     rcx, rdi
0x18002fc25  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002fc2a  xor     ebx, ebx
0x18002fc2c  mov     rcx, [rsp+268h+ppszPath]; pv
0x18002fc31  test    rcx, rcx
0x18002fc34  jz      short loc_18002FC3C
0x18002fc36  call    cs:__imp_CoTaskMemFree
0x18002fc3c  mov     eax, ebx
0x18002fc3e  mov     rcx, [rsp+268h+var_18]
0x18002fc46  xor     rcx, rsp; StackCookie
0x18002fc49  call    __security_check_cookie
0x18002fc4e  mov     rbx, [rsp+268h+arg_8]
0x18002fc56  add     rsp, 260h
0x18002fc5d  pop     rdi
0x18002fc5e  retn
```

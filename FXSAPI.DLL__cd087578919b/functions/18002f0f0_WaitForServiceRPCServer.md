# WaitForServiceRPCServer

- ea: `0x18002f0f0`
- end: `0x18002f2bb`
- name: `WaitForServiceRPCServer`
- size: `459`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015040`
- `0x180026b04`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002e5ac`
- `0x18002f0f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002f179`
- `KERNEL32!WaitForSingleObject` at `0x18002f179`
- `KERNEL32!CloseHandle` at `0x18002f205`
- `KERNEL32!CloseHandle` at `0x18002f205`
- `KERNEL32!SetLastError` at `0x18002f15c`
- `KERNEL32!SetLastError` at `0x18002f15c`
- `KERNEL32!GetLastError` at `0x18002f197`
- `KERNEL32!GetLastError` at `0x18002f22d`
- `KERNEL32!GetLastError` at `0x18002f197`
- `KERNEL32!GetLastError` at `0x18002f22d`
- `ADVAPI32!RegCloseKey` at `0x18002f25e`
- `ADVAPI32!RegCloseKey` at `0x18002f25e`

## pseudocode

```c
__int64 WaitForServiceRPCServer()
{
  DWORD started; // eax
  DWORD v1; // ecx
  DWORD v3; // eax
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD v6; // eax
  unsigned int v7; // eax
  HANDLE hHandle; // [rsp+38h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  hHandle = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  started = CreateSvcStartEvent(&hHandle, &hKey);
  if ( started )
  {
    v1 = started;
LABEL_7:
    SetLastError(v1);
    return 0;
  }
  v3 = WaitForSingleObject(hHandle, 0xEA60u);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 == 258 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_db036311db36307996a98c23702218b2_Traceguids);
      }
    }
    else if ( v3 == -1 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
    }
  }
  else
  {
    v4 = 0;
  }
  if ( !CloseHandle(hHandle)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_db036311db36307996a98c23702218b2_Traceguids, v6);
  }
  if ( hKey )
  {
    v7 = RegCloseKey(hKey);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_db036311db36307996a98c23702218b2_Traceguids, v7);
      }
    }
  }
  if ( v4 )
  {
    v1 = v4;
    goto LABEL_7;
  }
  return 1;
}

```

## disassembly

```asm
0x18002f0f0  mov     rax, rsp
0x18002f0f3  mov     [rax+8], rbx
0x18002f0f7  mov     [rax+20h], rbp
0x18002f0fb  push    rsi
0x18002f0fc  sub     rsp, 20h
0x18002f100  mov     qword ptr [rax+10h], 0
0x18002f108  mov     qword ptr [rax+18h], 0
0x18002f110  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f117  lea     rsi, WPP_GLOBAL_Control
0x18002f11e  lea     rbp, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002f125  cmp     rcx, rsi
0x18002f128  jz      short loc_18002F147
0x18002f12a  test    byte ptr [rcx+1Ch], 2
0x18002f12e  jz      short loc_18002F147
0x18002f130  cmp     byte ptr [rcx+19h], 5
0x18002f134  jb      short loc_18002F147
0x18002f136  mov     rcx, [rcx+10h]
0x18002f13a  mov     edx, 26h ; '&'
0x18002f13f  mov     r8, rbp
0x18002f142  call    WPP_SF_
0x18002f147  lea     rdx, [rsp+28h+hKey]
0x18002f14c  lea     rcx, [rsp+28h+hHandle]
0x18002f151  call    CreateSvcStartEvent
0x18002f156  test    eax, eax
0x18002f158  jz      short loc_18002F16F
0x18002f15a  mov     ecx, eax; dwErrCode
0x18002f15c  call    cs:__imp_SetLastError
0x18002f163  nop     dword ptr [rax+rax+00h]
0x18002f168  xor     eax, eax
0x18002f16a  jmp     loc_18002F2AA
0x18002f16f  mov     rcx, [rsp+28h+hHandle]; hHandle
0x18002f174  mov     edx, 0EA60h; dwMilliseconds
0x18002f179  call    cs:__imp_WaitForSingleObject
0x18002f180  nop     dword ptr [rax+rax+00h]
0x18002f185  mov     ebx, eax
0x18002f187  test    eax, eax
0x18002f189  jz      short loc_18002F1FE
0x18002f18b  cmp     eax, 102h
0x18002f190  jz      short loc_18002F1D3
0x18002f192  cmp     eax, 0FFFFFFFFh
0x18002f195  jnz     short loc_18002F200
0x18002f197  call    cs:__imp_GetLastError
0x18002f19e  nop     dword ptr [rax+rax+00h]
0x18002f1a3  mov     ebx, eax
0x18002f1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1ac  cmp     rcx, rsi
0x18002f1af  jz      short loc_18002F200
0x18002f1b1  test    byte ptr [rcx+1Ch], 2
0x18002f1b5  jz      short loc_18002F200
0x18002f1b7  cmp     byte ptr [rcx+19h], 2
0x18002f1bb  jb      short loc_18002F200
0x18002f1bd  mov     rcx, [rcx+10h]
0x18002f1c1  mov     edx, 27h ; '''
0x18002f1c6  mov     r9d, eax
0x18002f1c9  mov     r8, rbp
0x18002f1cc  call    WPP_SF_d
0x18002f1d1  jmp     short loc_18002F200
0x18002f1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1da  cmp     rcx, rsi
0x18002f1dd  jz      short loc_18002F200
0x18002f1df  test    byte ptr [rcx+1Ch], 2
0x18002f1e3  jz      short loc_18002F200
0x18002f1e5  cmp     byte ptr [rcx+19h], 2
0x18002f1e9  jb      short loc_18002F200
0x18002f1eb  mov     rcx, [rcx+10h]
0x18002f1ef  mov     edx, 28h ; '('
0x18002f1f4  mov     r8, rbp
0x18002f1f7  call    WPP_SF_
0x18002f1fc  jmp     short loc_18002F200
0x18002f1fe  xor     ebx, ebx
0x18002f200  mov     rcx, [rsp+28h+hHandle]; hObject
0x18002f205  call    cs:__imp_CloseHandle
0x18002f20c  nop     dword ptr [rax+rax+00h]
0x18002f211  test    eax, eax
0x18002f213  jnz     short loc_18002F254
0x18002f215  mov     rax, cs:WPP_GLOBAL_Control
0x18002f21c  cmp     rax, rsi
0x18002f21f  jz      short loc_18002F254
0x18002f221  test    byte ptr [rax+1Ch], 2
0x18002f225  jz      short loc_18002F254
0x18002f227  cmp     byte ptr [rax+19h], 2
0x18002f22b  jb      short loc_18002F254
0x18002f22d  call    cs:__imp_GetLastError
0x18002f234  nop     dword ptr [rax+rax+00h]
0x18002f239  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f240  mov     edx, 29h ; ')'
0x18002f245  mov     r9d, eax
0x18002f248  mov     r8, rbp
0x18002f24b  mov     rcx, [rcx+10h]
0x18002f24f  call    WPP_SF_d
0x18002f254  mov     rcx, [rsp+28h+hKey]; hKey
0x18002f259  test    rcx, rcx
0x18002f25c  jz      short loc_18002F29A
0x18002f25e  call    cs:__imp_RegCloseKey
0x18002f265  nop     dword ptr [rax+rax+00h]
0x18002f26a  test    eax, eax
0x18002f26c  jz      short loc_18002F29A
0x18002f26e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f275  cmp     rcx, rsi
0x18002f278  jz      short loc_18002F29A
0x18002f27a  test    byte ptr [rcx+1Ch], 2
0x18002f27e  jz      short loc_18002F29A
0x18002f280  cmp     byte ptr [rcx+19h], 2
0x18002f284  jb      short loc_18002F29A
0x18002f286  mov     rcx, [rcx+10h]
0x18002f28a  mov     edx, 2Ah ; '*'
0x18002f28f  mov     r9d, eax
0x18002f292  mov     r8, rbp
0x18002f295  call    WPP_SF_d
0x18002f29a  test    ebx, ebx
0x18002f29c  jz      short loc_18002F2A5
0x18002f29e  mov     ecx, ebx
0x18002f2a0  jmp     loc_18002F15C
0x18002f2a5  mov     eax, 1
0x18002f2aa  mov     rbx, [rsp+28h+arg_0]
0x18002f2af  mov     rbp, [rsp+28h+arg_18]
0x18002f2b4  add     rsp, 20h
0x18002f2b8  pop     rsi
0x18002f2b9  retn
```

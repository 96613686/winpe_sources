# FaxOpenPort

- ea: `0x180023e50`
- end: `0x18002401d`
- name: `FaxOpenPort`
- size: `461`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, DWORD DeviceId, DWORD Flags, LPHANDLE FaxPortHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024d20`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016278`
- `0x180023e50`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023f09`
- `RPCRT4!NdrClientCall3` at `0x180023f09`
- `KERNEL32!SetLastError` at `0x180023f8b`
- `KERNEL32!SetLastError` at `0x180023fd0`
- `KERNEL32!SetLastError` at `0x180023f8b`
- `KERNEL32!SetLastError` at `0x180023fd0`

## pseudocode

```c
BOOL __stdcall FaxOpenPort(HANDLE FaxHandle, DWORD DeviceId, DWORD Flags, LPHANDLE FaxPortHandle)
{
  BOOL v8; // edi
  unsigned int Pointer; // eax
  DWORD v10; // ecx
  _DWORD *NewHandle; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
  }
  v8 = 0;
  if ( !FaxHandle || !*(_DWORD *)FaxHandle || *((_DWORD *)FaxHandle + 4) )
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
    }
    return 0;
  }
  if ( !FaxPortHandle || (Flags & 3) == 0 )
  {
    v10 = 87;
    goto LABEL_12;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            2u,
                            0,
                            **((_QWORD **)FaxHandle + 4),
                            DeviceId,
                            Flags,
                            FaxPortHandle).Pointer;
  if ( Pointer )
  {
    v10 = Pointer;
LABEL_12:
    SetLastError(v10);
    return 0;
  }
  NewHandle = (_DWORD *)CreateNewHandle(*((_QWORD *)FaxHandle + 4), 1, Flags, *FaxPortHandle);
  if ( NewHandle )
    NewHandle[6] = DeviceId;
  *FaxPortHandle = NewHandle;
  LOBYTE(v8) = NewHandle != 0;
  return v8;
}

```

## disassembly

```asm
0x180023e50  mov     rax, rsp
0x180023e53  mov     [rax+20h], r9
0x180023e57  mov     [rax+18h], r8d
0x180023e5b  mov     [rax+10h], edx
0x180023e5e  mov     [rax+8], rcx
0x180023e62  push    rbx
0x180023e63  push    rsi
0x180023e64  push    rdi
0x180023e65  push    r12
0x180023e67  push    r14
0x180023e69  push    r15
0x180023e6b  sub     rsp, 58h
0x180023e6f  mov     r14, r9
0x180023e72  mov     r15d, r8d
0x180023e75  mov     r12d, edx
0x180023e78  mov     rsi, rcx
0x180023e7b  lea     rbx, WPP_GLOBAL_Control
0x180023e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e89  cmp     rcx, rbx
0x180023e8c  jz      short loc_180023EB2
0x180023e8e  test    dword ptr [rcx+1Ch], 1000h
0x180023e95  jz      short loc_180023EB2
0x180023e97  cmp     byte ptr [rcx+19h], 5
0x180023e9b  jb      short loc_180023EB2
0x180023e9d  mov     edx, 25h ; '%'
0x180023ea2  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180023ea9  mov     rcx, [rcx+10h]
0x180023ead  call    WPP_SF_
0x180023eb2  xor     edi, edi
0x180023eb4  test    rsi, rsi
0x180023eb7  jz      loc_180023FCB
0x180023ebd  cmp     [rsi], edi
0x180023ebf  jz      loc_180023FCB
0x180023ec5  cmp     [rsi+10h], edi
0x180023ec8  jnz     loc_180023FCB
0x180023ece  test    r14, r14
0x180023ed1  jz      loc_180023FC4
0x180023ed7  test    r15b, 3
0x180023edb  jz      loc_180023FC4
0x180023ee1  mov     rax, [rsi+20h]
0x180023ee5  mov     [rsp+88h+var_40], rdi
0x180023eea  mov     [rsp+88h+var_58], r14
0x180023eef  mov     [rsp+88h+var_60], r15d
0x180023ef4  mov     [rsp+88h+var_68], r12d
0x180023ef9  mov     r9, [rax]
0x180023efc  xor     r8d, r8d; pReturnValue
0x180023eff  lea     edx, [rdi+2]; nProcNum
0x180023f02  lea     rcx, pProxyInfo; pProxyInfo
0x180023f09  call    cs:__imp_NdrClientCall3
0x180023f10  nop     dword ptr [rax+rax+00h]
0x180023f15  mov     rbx, rax
0x180023f18  mov     [rsp+88h+var_40], rax
0x180023f1d  mov     [rsp+88h+var_48], eax
0x180023f21  jmp     short loc_180023F85
0x180023f23  mov     ebx, eax
0x180023f25  mov     [rsp+88h+var_48], eax
0x180023f29  lea     rdx, WPP_GLOBAL_Control
0x180023f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f37  cmp     rcx, rdx
0x180023f3a  jz      short loc_180023F63
0x180023f3c  test    dword ptr [rcx+1Ch], 1000h
0x180023f43  jz      short loc_180023F63
0x180023f45  cmp     byte ptr [rcx+19h], 2
0x180023f49  jb      short loc_180023F63
0x180023f4b  mov     edx, 27h ; '''
0x180023f50  mov     r9d, eax
0x180023f53  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180023f5a  mov     rcx, [rcx+10h]
0x180023f5e  call    WPP_SF_d
0x180023f63  xor     edi, edi
0x180023f65  mov     r14, [rsp+88h+arg_18]
0x180023f6d  mov     r15d, [rsp+88h+arg_10]
0x180023f75  mov     r12d, [rsp+88h+arg_8]
0x180023f7d  mov     rsi, [rsp+88h+arg_0]
0x180023f85  test    ebx, ebx
0x180023f87  jz      short loc_180023F99
0x180023f89  mov     ecx, ebx; dwErrCode
0x180023f8b  call    cs:__imp_SetLastError
0x180023f92  nop     dword ptr [rax+rax+00h]
0x180023f97  jmp     short loc_18002400C
0x180023f99  mov     r9, [r14]
0x180023f9c  mov     r8d, r15d
0x180023f9f  mov     edx, 1
0x180023fa4  mov     rcx, [rsi+20h]
0x180023fa8  call    ?CreateNewHandle@@YAPEAU_HANDLE_ENTRY@@PEAU_FAX_HANDLE_DATA@@W4FaxHandleType@@KPEAX@Z; CreateNewHandle(_FAX_HANDLE_DATA *,FaxHandleType,ulong,void *)
0x180023fad  test    rax, rax
0x180023fb0  jz      short loc_180023FB6
0x180023fb2  mov     [rax+18h], r12d
0x180023fb6  mov     [r14], rax
0x180023fb9  test    rax, rax
0x180023fbc  setnz   dil
0x180023fc0  mov     eax, edi
0x180023fc2  jmp     short loc_18002400E
0x180023fc4  mov     ecx, 57h ; 'W'
0x180023fc9  jmp     short loc_180023F8B
0x180023fcb  mov     ecx, 6; dwErrCode
0x180023fd0  call    cs:__imp_SetLastError
0x180023fd7  nop     dword ptr [rax+rax+00h]
0x180023fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fe3  cmp     rcx, rbx
0x180023fe6  jz      short loc_18002400C
0x180023fe8  test    dword ptr [rcx+1Ch], 1000h
0x180023fef  jz      short loc_18002400C
0x180023ff1  cmp     byte ptr [rcx+19h], 2
0x180023ff5  jb      short loc_18002400C
0x180023ff7  mov     edx, 26h ; '&'
0x180023ffc  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x180024003  mov     rcx, [rcx+10h]
0x180024007  call    WPP_SF_
0x18002400c  xor     eax, eax
0x18002400e  add     rsp, 58h
0x180024012  pop     r15
0x180024014  pop     r14
0x180024016  pop     r12
0x180024018  pop     rdi
0x180024019  pop     rsi
0x18002401a  pop     rbx
0x18002401b  retn
```

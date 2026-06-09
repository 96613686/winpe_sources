# IsLocalMachineNameW

- ea: `0x18002c1e0`
- end: `0x18002c315`
- name: `IsLocalMachineNameW`
- size: `309`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004394`
- `0x180015040`
- `0x180026b04`
- `0x180027b70`
- `0x180032d88`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002c1e0`
- `0x18003d510`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002c2db`
- `msvcrt!_wcsicmp` at `0x18002c2db`
- `KERNEL32!GetComputerNameW` at `0x18002c27c`
- `KERNEL32!GetComputerNameW` at `0x18002c27c`
- `KERNEL32!GetLastError` at `0x18002c2a4`
- `KERNEL32!GetLastError` at `0x18002c2a4`

## pseudocode

```c
_BOOL8 __fastcall IsLocalMachineNameW(wchar_t *String2)
{
  __int64 v2; // rax
  DWORD LastError; // eax
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-30h] BYREF

  nSize = 16;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  if ( !String2 )
    return 1;
  v2 = -1;
  do
    ++v2;
  while ( String2[v2] );
  if ( !v2 || *String2 == 46 && !String2[1] )
    return 1;
  if ( GetComputerNameW(Buffer, &nSize) )
    return _wcsicmp(Buffer, String2) == 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c1e0  mov     [rsp+arg_8], rbx
0x18002c1e5  mov     [rsp+arg_10], rbp
0x18002c1ea  push    rdi
0x18002c1eb  sub     rsp, 50h
0x18002c1ef  mov     rax, cs:__security_cookie
0x18002c1f6  xor     rax, rsp
0x18002c1f9  mov     [rsp+58h+var_10], rax
0x18002c1fe  mov     rbx, rcx
0x18002c201  mov     [rsp+58h+nSize], 10h
0x18002c209  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c210  lea     rbp, WPP_GLOBAL_Control
0x18002c217  cmp     rcx, rbp
0x18002c21a  jz      short loc_18002C23D
0x18002c21c  test    byte ptr [rcx+1Ch], 2
0x18002c220  jz      short loc_18002C23D
0x18002c222  cmp     byte ptr [rcx+19h], 5
0x18002c226  jb      short loc_18002C23D
0x18002c228  mov     rcx, [rcx+10h]
0x18002c22c  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c233  mov     edx, 27h ; '''
0x18002c238  call    WPP_SF_
0x18002c23d  xor     edi, edi
0x18002c23f  test    rbx, rbx
0x18002c242  jz      loc_18002C2F2
0x18002c248  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c24c  inc     rax
0x18002c24f  cmp     [rbx+rax*2], di
0x18002c253  jnz     short loc_18002C24C
0x18002c255  test    rax, rax
0x18002c258  jz      loc_18002C2F2
0x18002c25e  mov     eax, 2Eh ; '.'
0x18002c263  cmp     ax, [rbx]
0x18002c266  jnz     short loc_18002C272
0x18002c268  cmp     di, [rbx+2]
0x18002c26c  jz      loc_18002C2F2
0x18002c272  lea     rdx, [rsp+58h+nSize]; nSize
0x18002c277  lea     rcx, [rsp+58h+Buffer]; lpBuffer
0x18002c27c  call    cs:__imp_GetComputerNameW
0x18002c283  nop     dword ptr [rax+rax+00h]
0x18002c288  test    eax, eax
0x18002c28a  jnz     short loc_18002C2D3
0x18002c28c  mov     rax, cs:WPP_GLOBAL_Control
0x18002c293  cmp     rax, rbp
0x18002c296  jz      short loc_18002C2CF
0x18002c298  test    byte ptr [rax+1Ch], 2
0x18002c29c  jz      short loc_18002C2CF
0x18002c29e  cmp     byte ptr [rax+19h], 2
0x18002c2a2  jb      short loc_18002C2CF
0x18002c2a4  call    cs:__imp_GetLastError
0x18002c2ab  nop     dword ptr [rax+rax+00h]
0x18002c2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2b7  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c2be  mov     edx, 28h ; '('
0x18002c2c3  mov     r9d, eax
0x18002c2c6  mov     rcx, [rcx+10h]
0x18002c2ca  call    WPP_SF_d
0x18002c2cf  xor     eax, eax
0x18002c2d1  jmp     short loc_18002C2F7
0x18002c2d3  mov     rdx, rbx; String2
0x18002c2d6  lea     rcx, [rsp+58h+Buffer]; String1
0x18002c2db  call    cs:__imp__wcsicmp
0x18002c2e2  nop     dword ptr [rax+rax+00h]
0x18002c2e7  test    eax, eax
0x18002c2e9  mov     ecx, edi
0x18002c2eb  setz    cl
0x18002c2ee  mov     eax, ecx
0x18002c2f0  jmp     short loc_18002C2F7
0x18002c2f2  mov     eax, 1
0x18002c2f7  mov     rcx, [rsp+58h+var_10]
0x18002c2fc  xor     rcx, rsp; StackCookie
0x18002c2ff  call    __security_check_cookie
0x18002c304  mov     rbx, [rsp+58h+arg_8]
0x18002c309  mov     rbp, [rsp+58h+arg_10]
0x18002c30e  add     rsp, 50h
0x18002c312  pop     rdi
0x18002c313  retn
```

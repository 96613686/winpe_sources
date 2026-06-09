# FaxGetArchiveConfigurationA

- ea: `0x18000d900`
- end: `0x18000da07`
- name: `FaxGetArchiveConfigurationA`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000d900`
- `0x18000da10`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d9b9`
- `KERNEL32!GetLastError` at `0x18000d9b9`

## pseudocode

```c
__int64 __fastcall FaxGetArchiveConfigurationA(__int64 a1, unsigned int a2, LPVOID *a3)
{
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !(unsigned int)FaxGetArchiveConfigurationW(a1, a2, a3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
    return 0;
  }
  if ( !(unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a3 + 1)) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    pMemFree(*a3);
    return 0;
  }
  *(_DWORD *)*a3 = 40;
  return 1;
}

```

## disassembly

```asm
0x18000d900  push    rbx
0x18000d902  push    rsi
0x18000d903  push    rdi
0x18000d904  push    r14
0x18000d906  sub     rsp, 28h
0x18000d90a  mov     rbx, r8
0x18000d90d  mov     edi, edx
0x18000d90f  mov     rsi, rcx
0x18000d912  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d919  lea     r14, WPP_GLOBAL_Control
0x18000d920  cmp     rcx, r14
0x18000d923  jz      short loc_18000D949
0x18000d925  test    dword ptr [rcx+1Ch], 1000h
0x18000d92c  jz      short loc_18000D949
0x18000d92e  cmp     byte ptr [rcx+19h], 5
0x18000d932  jb      short loc_18000D949
0x18000d934  mov     rcx, [rcx+10h]
0x18000d938  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d93f  mov     edx, 96h
0x18000d944  call    WPP_SF_
0x18000d949  mov     r8, rbx
0x18000d94c  mov     edx, edi
0x18000d94e  mov     rcx, rsi
0x18000d951  call    FaxGetArchiveConfigurationW
0x18000d956  test    eax, eax
0x18000d958  jnz     short loc_18000D98E
0x18000d95a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d961  cmp     rcx, r14
0x18000d964  jz      short loc_18000D98A
0x18000d966  test    dword ptr [rcx+1Ch], 1000h
0x18000d96d  jz      short loc_18000D98A
0x18000d96f  cmp     byte ptr [rcx+19h], 2
0x18000d973  jb      short loc_18000D98A
0x18000d975  mov     rcx, [rcx+10h]
0x18000d979  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d980  mov     edx, 97h
0x18000d985  call    WPP_SF_
0x18000d98a  xor     eax, eax
0x18000d98c  jmp     short loc_18000D9FC
0x18000d98e  mov     rcx, [rbx]
0x18000d991  mov     rcx, [rcx+8]; lpWideCharStr
0x18000d995  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000d99a  test    eax, eax
0x18000d99c  jnz     short loc_18000D9EE
0x18000d99e  mov     rax, cs:WPP_GLOBAL_Control
0x18000d9a5  cmp     rax, r14
0x18000d9a8  jz      short loc_18000D9E4
0x18000d9aa  test    dword ptr [rax+1Ch], 1000h
0x18000d9b1  jz      short loc_18000D9E4
0x18000d9b3  cmp     byte ptr [rax+19h], 2
0x18000d9b7  jb      short loc_18000D9E4
0x18000d9b9  call    cs:__imp_GetLastError
0x18000d9c0  nop     dword ptr [rax+rax+00h]
0x18000d9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9cc  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d9d3  mov     edx, 98h
0x18000d9d8  mov     r9d, eax
0x18000d9db  mov     rcx, [rcx+10h]
0x18000d9df  call    WPP_SF_d
0x18000d9e4  mov     rcx, [rbx]; lpMem
0x18000d9e7  call    pMemFree
0x18000d9ec  jmp     short loc_18000D98A
0x18000d9ee  mov     rax, [rbx]
0x18000d9f1  mov     dword ptr [rax], 28h ; '('
0x18000d9f7  mov     eax, 1
0x18000d9fc  add     rsp, 28h
0x18000da00  pop     r14
0x18000da02  pop     rdi
0x18000da03  pop     rsi
0x18000da04  pop     rbx
0x18000da05  retn
```

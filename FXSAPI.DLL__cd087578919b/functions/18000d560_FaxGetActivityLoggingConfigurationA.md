# FaxGetActivityLoggingConfigurationA

- ea: `0x18000d560`
- end: `0x18000d66e`
- name: `FaxGetActivityLoggingConfigurationA`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000d560`
- `0x18000d680`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d61a`
- `KERNEL32!GetLastError` at `0x18000d61a`

## pseudocode

```c
__int64 __fastcall FaxGetActivityLoggingConfigurationA(__int64 a1, LPVOID *a2)
{
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !(unsigned int)FaxGetActivityLoggingConfigurationW(a1, a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
    return 0;
  }
  if ( !(unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 2)) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    pMemFree(*a2);
    return 0;
  }
  *(_DWORD *)*a2 = 24;
  return 1;
}

```

## disassembly

```asm
0x18000d560  mov     [rsp+arg_0], rbx
0x18000d565  mov     [rsp+arg_8], rbp
0x18000d56a  push    rdi
0x18000d56b  sub     rsp, 20h
0x18000d56f  mov     rbx, rdx
0x18000d572  mov     rdi, rcx
0x18000d575  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d57c  lea     rbp, WPP_GLOBAL_Control
0x18000d583  cmp     rcx, rbp
0x18000d586  jz      short loc_18000D5AC
0x18000d588  test    dword ptr [rcx+1Ch], 1000h
0x18000d58f  jz      short loc_18000D5AC
0x18000d591  cmp     byte ptr [rcx+19h], 5
0x18000d595  jb      short loc_18000D5AC
0x18000d597  mov     rcx, [rcx+10h]
0x18000d59b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d5a2  mov     edx, 0ADh
0x18000d5a7  call    WPP_SF_
0x18000d5ac  mov     rdx, rbx
0x18000d5af  mov     rcx, rdi
0x18000d5b2  call    FaxGetActivityLoggingConfigurationW
0x18000d5b7  test    eax, eax
0x18000d5b9  jnz     short loc_18000D5EF
0x18000d5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5c2  cmp     rcx, rbp
0x18000d5c5  jz      short loc_18000D5EB
0x18000d5c7  test    dword ptr [rcx+1Ch], 1000h
0x18000d5ce  jz      short loc_18000D5EB
0x18000d5d0  cmp     byte ptr [rcx+19h], 2
0x18000d5d4  jb      short loc_18000D5EB
0x18000d5d6  mov     rcx, [rcx+10h]
0x18000d5da  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d5e1  mov     edx, 0AEh
0x18000d5e6  call    WPP_SF_
0x18000d5eb  xor     eax, eax
0x18000d5ed  jmp     short loc_18000D65D
0x18000d5ef  mov     rcx, [rbx]
0x18000d5f2  mov     rcx, [rcx+10h]; lpWideCharStr
0x18000d5f6  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000d5fb  test    eax, eax
0x18000d5fd  jnz     short loc_18000D64F
0x18000d5ff  mov     rax, cs:WPP_GLOBAL_Control
0x18000d606  cmp     rax, rbp
0x18000d609  jz      short loc_18000D645
0x18000d60b  test    dword ptr [rax+1Ch], 1000h
0x18000d612  jz      short loc_18000D645
0x18000d614  cmp     byte ptr [rax+19h], 2
0x18000d618  jb      short loc_18000D645
0x18000d61a  call    cs:__imp_GetLastError
0x18000d621  nop     dword ptr [rax+rax+00h]
0x18000d626  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d62d  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000d634  mov     edx, 0AFh
0x18000d639  mov     r9d, eax
0x18000d63c  mov     rcx, [rcx+10h]
0x18000d640  call    WPP_SF_d
0x18000d645  mov     rcx, [rbx]; lpMem
0x18000d648  call    pMemFree
0x18000d64d  jmp     short loc_18000D5EB
0x18000d64f  mov     rax, [rbx]
0x18000d652  mov     dword ptr [rax], 18h
0x18000d658  mov     eax, 1
0x18000d65d  mov     rbx, [rsp+28h+arg_0]
0x18000d662  mov     rbp, [rsp+28h+arg_8]
0x18000d667  add     rsp, 20h
0x18000d66b  pop     rdi
0x18000d66c  retn
```

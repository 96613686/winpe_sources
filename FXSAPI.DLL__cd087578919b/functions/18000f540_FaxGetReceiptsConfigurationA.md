# FaxGetReceiptsConfigurationA

- ea: `0x18000f540`
- end: `0x18000f69a`
- name: `FaxGetReceiptsConfigurationA`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000f540`
- `0x18000f6a0`
- `0x1800279f0`
- `0x18002bb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f5c2`
- `KERNEL32!GetLastError` at `0x18000f654`
- `KERNEL32!GetLastError` at `0x18000f5c2`
- `KERNEL32!GetLastError` at `0x18000f654`

## pseudocode

```c
__int64 __fastcall FaxGetReceiptsConfigurationA(__int64 a1, LPVOID *a2)
{
  DWORD v4; // eax
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( (unsigned int)FaxGetReceiptsConfigurationW(a1, a2) )
  {
    if ( (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 3))
      && (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 5))
      && (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 6))
      && (unsigned int)ConvertUnicodeStringInPlace(*((LPCWCH *)*a2 + 7)) )
    {
      return 1;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, LastError);
    }
    pMemFree(*a2);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f540  mov     [rsp+arg_0], rbx
0x18000f545  mov     [rsp+arg_8], rbp
0x18000f54a  push    rdi
0x18000f54b  sub     rsp, 20h
0x18000f54f  mov     rbx, rdx
0x18000f552  mov     rdi, rcx
0x18000f555  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f55c  lea     rbp, WPP_GLOBAL_Control
0x18000f563  cmp     rcx, rbp
0x18000f566  jz      short loc_18000F58C
0x18000f568  test    dword ptr [rcx+1Ch], 1000h
0x18000f56f  jz      short loc_18000F58C
0x18000f571  cmp     byte ptr [rcx+19h], 5
0x18000f575  jb      short loc_18000F58C
0x18000f577  mov     rcx, [rcx+10h]
0x18000f57b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f582  mov     edx, 6Fh ; 'o'
0x18000f587  call    WPP_SF_
0x18000f58c  mov     rdx, rbx
0x18000f58f  mov     rcx, rdi
0x18000f592  call    FaxGetReceiptsConfigurationW
0x18000f597  test    eax, eax
0x18000f599  jnz     short loc_18000F5F2
0x18000f59b  mov     rax, cs:WPP_GLOBAL_Control
0x18000f5a2  cmp     rax, rbp
0x18000f5a5  jz      loc_18000F687
0x18000f5ab  test    dword ptr [rax+1Ch], 1000h
0x18000f5b2  jz      loc_18000F687
0x18000f5b8  cmp     byte ptr [rax+19h], 2
0x18000f5bc  jb      loc_18000F687
0x18000f5c2  call    cs:__imp_GetLastError
0x18000f5c9  nop     dword ptr [rax+rax+00h]
0x18000f5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5d5  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f5dc  mov     edx, 70h ; 'p'
0x18000f5e1  mov     r9d, eax
0x18000f5e4  mov     rcx, [rcx+10h]
0x18000f5e8  call    WPP_SF_d
0x18000f5ed  jmp     loc_18000F687
0x18000f5f2  mov     rcx, [rbx]
0x18000f5f5  mov     rcx, [rcx+18h]; lpWideCharStr
0x18000f5f9  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000f5fe  test    eax, eax
0x18000f600  jz      short loc_18000F639
0x18000f602  mov     rcx, [rbx]
0x18000f605  mov     rcx, [rcx+28h]; lpWideCharStr
0x18000f609  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000f60e  test    eax, eax
0x18000f610  jz      short loc_18000F639
0x18000f612  mov     rcx, [rbx]
0x18000f615  mov     rcx, [rcx+30h]; lpWideCharStr
0x18000f619  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000f61e  test    eax, eax
0x18000f620  jz      short loc_18000F639
0x18000f622  mov     rcx, [rbx]
0x18000f625  mov     rcx, [rcx+38h]; lpWideCharStr
0x18000f629  call    ?ConvertUnicodeStringInPlace@@YAHPEBG@Z; ConvertUnicodeStringInPlace(ushort const *)
0x18000f62e  test    eax, eax
0x18000f630  jz      short loc_18000F639
0x18000f632  mov     eax, 1
0x18000f637  jmp     short loc_18000F689
0x18000f639  mov     rax, cs:WPP_GLOBAL_Control
0x18000f640  cmp     rax, rbp
0x18000f643  jz      short loc_18000F67F
0x18000f645  test    dword ptr [rax+1Ch], 1000h
0x18000f64c  jz      short loc_18000F67F
0x18000f64e  cmp     byte ptr [rax+19h], 2
0x18000f652  jb      short loc_18000F67F
0x18000f654  call    cs:__imp_GetLastError
0x18000f65b  nop     dword ptr [rax+rax+00h]
0x18000f660  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f667  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000f66e  mov     edx, 71h ; 'q'
0x18000f673  mov     r9d, eax
0x18000f676  mov     rcx, [rcx+10h]
0x18000f67a  call    WPP_SF_d
0x18000f67f  mov     rcx, [rbx]; lpMem
0x18000f682  call    pMemFree
0x18000f687  xor     eax, eax
0x18000f689  mov     rbx, [rsp+28h+arg_0]
0x18000f68e  mov     rbp, [rsp+28h+arg_8]
0x18000f693  add     rsp, 20h
0x18000f697  pop     rdi
0x18000f698  retn
```

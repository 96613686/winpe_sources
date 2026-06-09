# _ImpersonateUser(ushort const *,ulong,bool &)

- ea: `0x18001c3fc`
- end: `0x18001c4ef`
- name: `?_ImpersonateUser@@YAJPEBGKAEA_N@Z`
- size: `243`
- prototype: `int(const unsigned __int16 *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001b05c`

## callees

- `0x180002a50`
- `0x18000a2c0`
- `0x18000a358`
- `0x18001c3fc`
- `0x18001c54c`

## pseudocode

```c
__int64 __fastcall _ImpersonateUser(const unsigned __int16 *a1, unsigned int a2, bool *a3)
{
  wchar_t *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF

  v6 = (wchar_t *)std::wstring::wstring(v10, a1);
  v7 = __ImpersonateUser(v6, a2, a3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( *a3 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, a1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, a1);
      return (unsigned int)-2147418113;
    }
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids, (unsigned int)v7);
  }
  return v8;
}

```

## disassembly

```asm
0x18001c3fc  mov     [rsp+arg_0], rbx
0x18001c401  mov     [rsp+arg_8], rsi
0x18001c406  push    rdi
0x18001c407  sub     rsp, 40h
0x18001c40b  mov     ebx, edx
0x18001c40d  mov     rdi, rcx
0x18001c410  mov     rdx, rcx
0x18001c413  mov     rsi, r8
0x18001c416  lea     rcx, [rsp+48h+var_28]
0x18001c41b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c420  mov     r8, rsi
0x18001c423  mov     edx, ebx; SessionId
0x18001c425  mov     rcx, rax; String2
0x18001c428  call    ?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; __ImpersonateUser(std::wstring,ulong,bool &)
0x18001c42d  mov     ebx, eax
0x18001c42f  test    eax, eax
0x18001c431  jns     short loc_18001C46E
0x18001c433  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c43a  lea     rdx, WPP_GLOBAL_Control
0x18001c441  cmp     rcx, rdx
0x18001c444  jz      loc_18001C4DC
0x18001c44a  test    byte ptr [rcx+1Ch], 4
0x18001c44e  jz      loc_18001C4DC
0x18001c454  mov     rcx, [rcx+10h]
0x18001c458  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c45f  mov     edx, 12h
0x18001c464  mov     r9d, eax
0x18001c467  call    WPP_SF_d
0x18001c46c  jmp     short loc_18001C4DC
0x18001c46e  cmp     byte ptr [rsi], 0
0x18001c471  jnz     short loc_18001C4AB
0x18001c473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c47a  lea     rdx, WPP_GLOBAL_Control
0x18001c481  cmp     rcx, rdx
0x18001c484  jz      short loc_18001C4A4
0x18001c486  test    byte ptr [rcx+1Ch], 4
0x18001c48a  jz      short loc_18001C4A4
0x18001c48c  mov     rcx, [rcx+10h]
0x18001c490  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c497  mov     edx, 13h
0x18001c49c  mov     r9, rdi
0x18001c49f  call    WPP_SF_S
0x18001c4a4  mov     ebx, 8000FFFFh
0x18001c4a9  jmp     short loc_18001C4DC
0x18001c4ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4b2  lea     rdx, WPP_GLOBAL_Control
0x18001c4b9  cmp     rcx, rdx
0x18001c4bc  jz      short loc_18001C4DC
0x18001c4be  test    byte ptr [rcx+1Ch], 1
0x18001c4c2  jz      short loc_18001C4DC
0x18001c4c4  mov     rcx, [rcx+10h]
0x18001c4c8  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c4cf  mov     edx, 14h
0x18001c4d4  mov     r9, rdi
0x18001c4d7  call    WPP_SF_S
0x18001c4dc  mov     rsi, [rsp+48h+arg_8]
0x18001c4e1  mov     eax, ebx
0x18001c4e3  mov     rbx, [rsp+48h+arg_0]
0x18001c4e8  add     rsp, 40h
0x18001c4ec  pop     rdi
0x18001c4ed  retn
```

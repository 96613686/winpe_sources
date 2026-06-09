# ZtPromoteStagingToActive

- ea: `0x1800048f0`
- end: `0x1800049a8`
- name: `ZtPromoteStagingToActive`
- size: `184`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int32 *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800049b0`

## callees

- `0x1800048f0`
- `0x18000cdd8`
- `0x180015008`

## string_xrefs

- `0x18000493c`: `ZTStagingConfig`

## pseudocode

```c
__int64 __fastcall ZtPromoteStagingToActive(HKEY hKey, unsigned __int32 *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  unsigned __int32 v6; // ebp
  unsigned __int32 v7; // r14d
  unsigned int v8; // eax
  USHORT v9; // dx
  int v10; // r9d

  if ( hKey && a2 && a3 )
  {
    v6 = _InterlockedCompareExchange(&dword_18001F364, 0, 0);
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)&g_rgZtHelperSettingsState, 0, 0);
    if ( v6 < v7 )
    {
      v5 = 5023;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v9 = 42;
      v10 = 5023;
    }
    else
    {
      v8 = DnsRegDeleteTree(hKey, L"ZTStagingConfig");
      v5 = v8;
      if ( !v8 )
      {
        _InterlockedExchange((volatile __int32 *)&g_rgZtHelperSettingsState, v6);
        *a3 |= 0x80uLL;
        *a2 = v7;
        return v5;
      }
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v9 = 43;
      v10 = v8;
    }
    WPP_SF_d(1026, v9, (ULONGLONG)WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v10);
    return v5;
  }
  return 87;
}

```

## disassembly

```asm
0x1800048f0  push    rbx
0x1800048f2  push    rbp
0x1800048f3  push    rsi
0x1800048f4  push    rdi
0x1800048f5  push    r14
0x1800048f7  sub     rsp, 20h
0x1800048fb  mov     rdi, r8
0x1800048fe  mov     r8, rcx
0x180004901  mov     rsi, rdx
0x180004904  test    rcx, rcx
0x180004907  jnz     short loc_180004913
0x180004909  mov     ebx, 57h ; 'W'
0x18000490e  jmp     loc_18000499B
0x180004913  test    rsi, rsi
0x180004916  jz      short loc_180004909
0x180004918  test    rdi, rdi
0x18000491b  jz      short loc_180004909
0x18000491d  xor     ecx, ecx
0x18000491f  xor     eax, eax
0x180004921  lock cmpxchg cs:dword_18001F364, ecx
0x180004929  mov     ebp, eax
0x18000492b  xor     eax, eax
0x18000492d  lock cmpxchg dword ptr cs:g_rgZtHelperSettingsState, ecx
0x180004935  mov     r14d, eax
0x180004938  cmp     ebp, eax
0x18000493a  jb      short loc_180004974
0x18000493c  lea     rdx, SubKey; "ZTStagingConfig"
0x180004943  mov     rcx, r8; hKey
0x180004946  call    DnsRegDeleteTree
0x18000494b  mov     ebx, eax
0x18000494d  test    eax, eax
0x18000494f  jnz     short loc_180004961
0x180004951  xchg    ebp, dword ptr cs:g_rgZtHelperSettingsState
0x180004957  bts     qword ptr [rdi], 7
0x18000495c  mov     [rsi], r14d
0x18000495f  jmp     short loc_18000499B
0x180004961  test    byte ptr cs:xmmword_18001F260, 4
0x180004968  jz      short loc_18000499B
0x18000496a  mov     edx, 2Bh ; '+'
0x18000496f  mov     r9d, eax
0x180004972  jmp     short loc_18000498A
0x180004974  mov     ebx, 139Fh
0x180004979  test    byte ptr cs:xmmword_18001F260, 4
0x180004980  jz      short loc_18000499B
0x180004982  mov     edx, 2Ah ; '*'
0x180004987  mov     r9d, ebx
0x18000498a  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004991  mov     ecx, 402h
0x180004996  call    WPP_SF_d
0x18000499b  mov     eax, ebx
0x18000499d  add     rsp, 20h
0x1800049a1  pop     r14
0x1800049a3  pop     rdi
0x1800049a4  pop     rsi
0x1800049a5  pop     rbp
0x1800049a6  pop     rbx
0x1800049a7  retn
```
